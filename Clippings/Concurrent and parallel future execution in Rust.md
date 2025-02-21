---
category: "[[Clippings]]"
author: "[[Heiko Seeberger]]"
title: "Concurrent and parallel future execution in Rust"
source: https://heikoseeberger.de/2025-01-15-concurrent-parallel-futures/
clipped: 2025-02-21
published: 2025-01-15
topics: 
tags: [clippings]
---

A lot has been written about concurrency and parallelism, so we only briefly define what is needed for this article: **Concurrent programming** allows us to run two or more computations in overlapping periods of time and **parallel execution** means that two or more computations are actually executed at the same instant. So a concurrent program could be executed in parallel, but it need not be.

Tokio, Rust’s prevalent async runtime, provides **task**s as the main vehicle for concurrent programming. When using the multi-thread scheduler, tasks are executed on a thread pool. As most modern processors offer several CPU cores, a number of tasks – up to the number of CPU cores – can be executed in parallel. So parallel execution is a property of the hardware.

In Tokio, **Future**s – Rust’s abstraction for asynchronous computations – are executed within the context of a task which drives them to completion. It is possible to await two or more futures concurrently, but if they are driven by the same task, they are not executed in parallel.

Assuming we want our programs to be as performat as possible, should we then always spawn a task when awaiting concurrent futures? Not necessarily, because that depends on how much work these futures contain that can be parallized.

I/O heavy futures mostly await low-level asyncronous and non-blocking operating system calls to get back, so a single task can easily drive a lot of these futures, i.e. these futures are executed “effectively in parallel”.

Yet when it comes to CPU heavy asynchronous computations, a single future effectively blocks its driving task and prevents other futures from making progress. Then is makes sense to spawn a task for each such future.

Let’s look at an example, extremely simplified, but with a realistic real-world background: a streaming pipeline, continuously fetching data from some remote endpoint, which is I/O heavy, then transforming the retrieved data, which is CPU heavy. To keep things simple, we provide two dummy functions for these stages:

1  
2  
3  
4  
5  
6  
7  
8  
9  
10  
11  
12  

  
pub async fn fetch() {  
   
 sleep(ONE\_SECOND).await;  
}  
  
  
pub async fn transform() {  
 let end = OffsetDateTime::now\_utc() + ONE\_SECOND;  
   
 while OffsetDateTime::now\_utc() <= end {}  
}  

The basic streaming pipeline looks like this:

1  
2  
3  

let pipeline = stream::repeat\_with(OffsetDateTime::now\_utc)  
 .then(|\_| fetch())  
 .then(|\_| transform());  

Notice, that `then` – a stream combinator from `futures::StreamExt` – is sort of an asynchronous version of `map`, i.e. transforms the stream’s items by awaiting the given future.

In order to measure the performance – the time the pipeline needs to process four items – we use the following program:

1  
2  
3  
4  
5  
6  
7  
8  
9  
10  
11  

#\[tokio::main\]  
async fn main() {  
 let start = OffsetDateTime::now\_utc();  
  
 let pipeline = ...  
  
 pipeline.take(4).count().await;  
  
 let duration = OffsetDateTime::now\_utc() - start;  
 println!("Duration: {duration}");  
}  

Running this with the above pipeline will take eight seconds, because so far there are no concurrent stages and therefore items flow through the pipeline one by one, each taking one second for `fetch` and `transform`.

Concurrency can be introduced with the `buffered` combinator which expects the stream items to be futures. It awaits up to the given number of futures concurrently and emits their output into the stream in the original order.

Assuming `NUM_CPUS` is set to the actual number of available CPU cores, which could be determined using the [num\_cpus crate](https://crates.io/crates/num_cpus), and also assuming that `NUM_CPUS` is larger or equal four (the number of items we take from the stream in the above program) the pipeline now looks like this:

1  
2  
3  
4  
5  

let pipeline = stream::repeat\_with(OffsetDateTime::now\_utc)  
 .map(|\_| fetch())  
 .buffered(NUM\_CPUS)  
 .map(|\_| transform())  
 .buffered(NUM\_CPUS);  

Notice that replace `then` with `map`, because we no longer want to await the `fetch` and `transform` futures, but we want to feed them into `buffered` which awaits them concurrently.

Now guess how long the above program takes. Still eight seconds? Or only two? Or maybe … five? It’s the latter. As explained above, `fetch` is executed “effectively in parallel”, so it only takes one second for all four items to pass that stage. Yet `transform` keeps the single executing task busy for one second for each item, hence it takes four seconds for that stage.

Therefore we need to spawn a task for each stream item to execute `transform`:

1  
2  
3  
4  
5  

let pipeline = stream::repeat\_with(OffsetDateTime::now\_utc)  
 .map(|\_| fetch())  
 .buffered(NUM\_CPUS)  
 .map(|\_| task::spawn(transform()))  
 .buffered(NUM\_CPUS);  

Now we got the time to run the program down to only two seconds. And this is the optimum we can get. In particular it would not help to increase the argument for the second `buffered` call to some value larger than the number of CPU cores, because that hardware property limits the amount of parallelism we can get. Yet increasing the argument for the first `buffered` call might make sense, because prefetching some more items via I/O could possibly pay off in cases of occasional I/O bottlenecks.

If you want to check this out yourself, you can find the code at [demo-concurrent-parallel-futures on GitHub](https://github.com/hseeberger/demo-concurrent-parallel-futures).