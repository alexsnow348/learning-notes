---
category: "[[Clippings]]"
author: "[[Vadim Kravcenko]]"
title: Habits of great software engineers
source: https://vadimkravcenko.com/shorts/habits-of-great-software-engineers/?ref=dailydev
clipped: 2023-11-07
topics: 
tags:
  - clippings
  - software-engineering
---

The role of a software developer often gets distilled down to a singular activity: coding. While coding is undeniably the heartbeat of the profession, defining a developer by this act alone is akin to defining a painter by their ability to mix colors. It's a crucial part but just the tip of the iceberg. The true essence of a software developer's role combines many different skills, mindsets, and disciplines.

Imagine a world where every software developer is just a coder. In such a world, code might get written, but would it solve any problems? *Would the code be even useful or just an implementation of something fancy*? The difference between a developer and a great developer is the breadth and depth of their approach in delivering value.

I want to talk more about what makes a great software developer. What are the habits of highly effective developers? And I’m not going to talk about coding (too much).

**TL;DR;** **for those who want to know if there's value before they scroll down.** I talk about:

1.  *Focusing beyond the code* - as a developer you will code 20% of your time. You should excel at coding nonetheless, but it won't be enough to be great.
2.  *Efficiency / Antifragility* — Making sure everything around you runs smoothly and has forward momentum
3.  *Joy of tinkering* - build projects, try out frameworks, build stuff on the side. Keeps the spark alive.
4.  *Knowing the why* — It's important to know why your code does what it does, too many abstractions nowadays that rarely someone thinks below the level of their language e.g JS devs not thinking about the engine that runs their code.
5.  *Thinking in systems* — knowing how your code impacts not only your individual system but other parts of the business/application/life.
6.  *Tech detox* — Recharging away from your monitor makes you a better programmer.
7.  *The art of approximation* — Knowing important tech numbers to approximate calculations when making decisions when programming.
8.  If this sounds interesting there's a few more things like that at the bottom. But you'll have to read it.

***Disclaimer:*** *Purely subjective thoughts, yours may vary.*

## **Focusing beyond the code**

Coding is to a developer what a brush is to a painter or a chisel to a sculptor. It's the primary tool, the foundational skill upon which everything else is built. Every application, every website, and every digital solution starts with a line of code. Someone wrote it. You probably write it daily as well.

However, while coding is fundamental, it's essential to recognize that it's not the actual purpose. It's about writing *meaningful* lines of code. It's about *solving problems* with the code. A line of code means nothing if there’s no context to it.

Being a great developer means being efficient in coding. It’s not something you can skip. It's the entry ticket to the world of software development. But what separates the good from the great is the ability to see beyond the immediate lines of code. *How will it interact with other components? How will it scale? How maintainable is it?* These are the questions that a decent software developer constantly grapples with.

We’re not going too deep on the coding; there are better teachers than me out there who share practical wisdom on how to master the machine. Here are some books purely on coding/programming that will boost your skills immensely:

-   *Cracking the Coding Interview*, McDowell [Link to Amazon](https://www.amazon.com/dp/0984782850)
-   *Introduction to Algorithms*, Cormen [Link to Amazon](https://www.amazon.com/Introduction-Algorithms-fourth-Thomas-Cormen/dp/026204630X/)
-   *Clean Code*, Martin [Link to Amazon](https://www.amazon.com/dp/0132350882)
-   *Coders at Work*, Seibel [Link to Amazon](https://www.amazon.com/gp/product/1430219483)

## **The Pursuit of Efficiency**

All the best developers that I’ve met have been highly efficient. I don’t know how they manage to do it, but it seems they’re always one step ahead of you. It’s a feeling when you’re near them; the progress is felt in the air. Everything moves smoothly — challenges get resolved in a timely matter, and things are under control and moving toward the purpose that the engineer has set.

Great feeling.

Some may argue that efficiency = the [opposite of stability](https://psyche.co/ideas/why-efficiency-is-dangerous-and-slowing-down-makes-life-better). But this is not the kind of efficiency I'm talking about. I'm talking more in terms of [Antifragility](https://en.wikipedia.org/wiki/Antifragility). No running around and doing everything as fast as possible. You don't have to make tradeoffs by reducing the buffers that you have, and be wary of making changes that reduce your resiliency to unexpected things.

So we’re talking about staying efficient. At its core, efficiency is about progress — momentum, ensuring that the wheels of development are always turning. To make it clear what I’m talking about, let’s take a look at the opposite. Every developer knows the feeling of being "stuck" – whether it's a particularly challenging bug — where you start doubting your competence or a piece of code that just won't cooperate. The progress seems to have come to a halt. The pursuit of efficiency, in this case, means not letting these obstacles impede you. It's about thinking on your feet, finding resources to solve the issue, finding alternative solutions, and keeping the end goal in sight.

> 🏄 Think of it as adopting a proactive mindset, where doing something – even if it doesn’t solve your problem directly – is better than doing nothing.

This means breaking a complex problem into smaller, more manageable tasks. It means seeking input from a colleague when you're feeling stuck or temporarily setting aside a challenging task to focus on another aspect of the project. The key is to maintain forward momentum with small increments.

You might say, *“Solving hard problems requires time. You shouldn’t hurry”.* And you will be correct. Solving complex problems does require a lot of time. But even solving one big problem has forward momentum — For example getting a new exception after hours of debugging is cause for celebration as you move closer to figuring out the issue.

## **The Joy of Tinkering**

I will be honest: great developers aren't just skilled or knowledgeable; they're passionate. They're eyes light up at the mention of a new programming language. They spend hours diving deep into a challenging problem not just because they have to but because they *want* to. They're driven by an insatiable curiosity, a hunger to know more, do more, and be more.

I have nothing against people who are not passionate about programming; it’s okay, but these people will also not be pursuing greatness doing 9-5.

This passion manifests itself in various ways, but one of the most evident is the joy of exploration. Great developers are explorers at heart. They're not content with just knowing the tools and technologies of today; they're always on the lookout for what's on the horizon. They tinker, they experiment, they play. Whether it's a new framework, a novel algorithm, or an emerging tech trend, they dive in headfirst, eager to learn, understand, and master.

<iframe width="560" height="315" src="https://www.youtube.com/embed/nctqc8FBJ2U?si=KGolduaKTohsVX-V" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

So here's George Hotz having great time tinkering with LLaMa and building a chatbot, can you see the joy while he's coding? I find this so cool.

This kind of tinkering keeps the spark alive. In a field as vast and ever-evolving as software development, it's easy to feel overwhelmed or stuck in a rut. However, by embracing curiosity and actively seeking new challenges and learning opportunities, developers can keep their skills sharp and enthusiasm high.

Moreover, this exploration has a more profound, more intrinsic value: the sheer joy of the process. I think great developers also enjoy being passionate about programming. From my personal side, I can tell you I could not see my life without some kind of programming.

## **Knowing the Why**

Nowadays, developers often find themselves engrossed in specific layers or components, be it perfecting a REST API request or finetuning CSS for that impeccable web design. We’ve gotten very high in abstractions in the last decade or so. Nobody writes assembly, and many developers have never even seen it. Developers usually just work with what they have and don’t ask questions about why it works the way it does. There's an underlying layer of understanding that often goes overlooked: knowing why things are the way they are.

Now, it's a valid argument that a developer doesn't need to be an expert in every layer of the stack. One doesn't need to trace the journey from circuit boards to bits and bytes for every line of code written. But having a foundational understanding and a sense of the bigger picture can be incredibly empowering.

***Frontend Developers*** — why and how the CSS is rendered? So many cool things in the [Blink rendering engine](https://www.chromium.org/blink/) will change how you think about the page.  

***Backend Developers*** — why and how the Python interpreter works? There are so many fascinating things in the [CPython interpreter/compiler](https://github.com/python/cpython) that you’ll be surprised how your code runs.

Knowing the WHY/HOW behind the code offers several advantages:

1.  **Problem Solving:** When challenges arise, understanding the underlying logic can guide you towards an answer much faster. Even the errors will be clearer when you know how they are thrown.
2.  **Informed Decisions:** Your knowledge of the underlying systems will subconsciously influence every decision you make. Whether it's choosing a protocol, seeing a function and understanding immediately it can run in O(n), or ensuring security, a deeper understanding equips a developer to make highly effective decisions.
3.  **Bridging Gaps:** In multidisciplinary teams, grasping the broader landscape can foster better communication and collaboration, bridging the gap between specialists of different domains.
4.  **Innovation:** Often, groundbreaking solutions emerge at the intersection of disciplines. Knowing the 'why' of various layers can spark innovative ideas and approaches.

I’m not saying you should know everything. It’s more about not just blindly accepting things at face value but delving deeper and expanding one's horizons. I guarantee you this knowledge will be useful to you.

## **Thinking in Systems**

This is similar to the first part of not just focusing on the code but thinking about systems and their interactions. In my eyes, a great developer doesn’t just see the individual pieces; they see the entire puzzle, understanding not only how each piece fits into the current puzzle but also what the puzzle is and if there are more puzzles that need to be interacted with.

Systems thinking is about recognizing that software is made up of numerous components that interact with each other in complex ways. It's not enough to ensure that each component works well separately; it's crucial to understand how it works as part of the whole and what implications it has on the company. Simply — focus not only on unit tests but also E2E tests. It's about asking questions like: *Why is this component necessary for the business? If this component fails, how will it impact other systems? How can we design our software to be resilient?*

Furthermore, systems thinking extends beyond the software itself. Great developers understand that software doesn't exist in a vacuum. It interacts with users, with other systems, with external databases, and even with other non-IT departments.

It's about seeing the forest *and* the trees, understanding both the macro and the micro level of the things that you develop. Imagine you’re a YouTube Engineer, given a task to improve the algorithm to increase the average time a user spends on YouTube. A straightforward task, you might think, but when you take a step back and look at the issue from a macro level, you’ll see that there are many complex systems at play — from Scalability to UX to moral considerations to legal department.

Or a better, recent example — imagine [you’re an FTX Engineer](https://www.theregister.com/2023/10/10/ftx_python_code/), and you’re asked to allow accounts to go into the negative. Again, it is a straightforward feature from the perspective of your individual system — a single line of code. But again, let’s step back and think of the risk management system, compliance system, and every other system affected by this change.

## **Recharging Beyond the Pixels**

In the digital age, screens have become ubiquitous. From the workstation where you transform code into applications to the smartphones that keep us connected 24/7, technology is an ever-present force in our lives. And for developers, this immersion is even more profound.

Great developers aren't just masters of their craft but well-rounded individuals who understand the value of experiences beyond the digital realm. They recognize that while technology can expand horizons, it can also, paradoxically, become a limiting bubble.

> 🏄Constant immersion in the digital world can lead to a narrowed perspective. There’s so much more outside of the tech bubble.

I won’t talk too much about the dangers of constant screen time. Physically, it can lead to ailments like eye strain, disrupted sleep patterns, and sedentary lifestyle-related issues. Mentally, it can result in burnout, increased stress, and a feeling of being perpetually "wired." Moreover, a predominantly online life can lead to a sense of isolation and a disconnection from the tangible, real world around us.

But stepping away from the screens, even momentarily, can work wonders. A tech detox can be incredibly rejuvenating, be it a short walk in the park, a weekend getaway, or even a few hours spent on a non-digital hobby.

Moreover, these breaks from technology serve as a reminder of the bigger picture. They ground us, reminding us of the real-world implications of their work, of the people and communities we serve, and of the myriad experiences and challenges that shape human lives.

## **The Art of Approximation**

How fast can you read 10GB from RAM? From SSD? There’s a subtle yet crucial skill that many developers overlook: the art of approximation. It's not about knowing everything but about having a mental toolkit of numbers to guide decisions, shape solutions, and prevent costly missteps.

Amidst the lines of logic and structures, there are numbers that matter. If you're building a high-throughput application, what's the storage cost for logging at 100,000 RPS? While the exact numbers might vary based on various factors, having a rough estimate can be invaluable. It can guide architectural decisions, inform optimizations, and provide a reality check on feasibility.

I’ve seen this cool concept called *“The Napkin Math”* — for situations where you need to quickly approximate how much it will cost or how fast it will be. In today's cloud-centric world, where scalability and performance are paramount, costs can soon spiral out of control if not kept in check. Being able to approximate calculations on the fly can provide a solid roadmap. It can help you anticipate costs, allocate resources efficiently, and design performant and cost-effective systems.

<iframe width="560" height="315" src="https://www.youtube.com/embed/IxkSlnrRFqc?si=F1VNYSH3hLzOvAux" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

I won’t talk too in-depth about this - but watch the talk. It’s great.

## **Transfering Knowledge to Other Problems**

One of the most profound moments in a student's life is the realization that learning isn't just about absorbing information but understanding its essence and applying it to similar problems. This truth, often first encountered in math classes, extends far beyond the classroom and is especially pertinent in software development.

Think back to those math problems. You'd spend hours understanding a concept, practicing it with a specific set of problems, only to be presented with a different challenge during exams. The numbers changed, the context shifted, but the underlying principle remained unchanged. The real test wasn't just your knowledge of the concept but your ability to adapt and apply it to a new scenario.

I find this adaptability and transfer mindset quite important. Challenges are constant, but they rarely come in familiar packages. A coding solution that worked for one project might not fit another, even if they seem similar. The true mark of a developer's skill is their ability to take their knowledge and mold it to fit the task at hand.

If it looks like a duck, swims like a duck, and quacks like a duck, then it probably is a duck.

> 🏄 Experience plays a pivotal role in this. With each challenge faced, a developer adds to their repertoire, expanding their understanding and refining their approach. I tell my developers, “Every bug you solve today is a skill tomorrow.”

Static knowledge, rigid and unyielding, can become a limitation. The real magic lies in understanding and grasping the core principles so that they can be reshaped and repurposed as needed.

## **Making Hard Things Easy**

Julia Evans has a great talk on making hard things easy. That’s where I stole the title of this section as well.

<iframe width="560" height="315" src="https://www.youtube.com/embed/30YWsGDr8mA?si=RaL2--dIngY4Q9UU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>



There's a truth often attributed to the genius of Albert Einstein: "If you can't explain it simply, you don't understand it well enough." In software engineering especially, the pinnacle of understanding isn't just about mastering the hard things but about making those hard things easy for others.

I’ve met quite a few developers who explained complex things to me in such simple terms that I was surprised that a) I understood it and b) that the concepts were not as complicated as I feared.

For example, I didn’t know much about network programming or Linux sockets. I spent days googling, but the information I found wasn’t really clicking with me. It might say a lot about Google search quality, but then I found the [beej’s guide](https://beej.us/guide/bgnet/html/) , and it clicked into place for me.

I think it’s a mark of great engineers if they can explain something and be understood not just by their fellow programmers who work in the same field but also by average people.

Furthermore, making hard things easy is about leveling the playing field. It's about recognizing that knowledge shouldn't be a guarded treasure but a shared resource. By simplifying concepts by making them accessible, you empower others. You give them the tools to rise, to reach your level of understanding, and perhaps even surpass it.

Enjoyed the read? Subscribe to read more articles from me.

## **Playing the Long Game**

Deadlines loom, stakeholders press and the allure of quick fixes can be overwhelmingly tempting. But the best developers, the ones who leave a lasting legacy, understand the art of playing the long game. They recognize that while today's solutions (or shortcuts) matter, the vision of tomorrow truly defines success.

It's easy to opt for a solution that addresses the problem at hand, but does it stand the test of time? Will it scale? Is it maintainable? Will you even want to touch it later? These are the questions that guide the forward-thinking developer.

I’ve talked a bit [about technical debt](https://vadimkravcenko.com/en/manage-technical-debt-agile-company/) and the conscious choice of taking it on. Much like financial debt, technical debt refers to the "cost" associated with opting for quick-and-dirty solutions. While it might offer immediate relief — and give you the much-needed time-to-market, it accumulates interest over time, often manifesting as bugs, performance issues, integration challenges, and, worst of all, maintainability chaos. Every developer should understand the implications of technical debt.

>  🏄  Today's shortcuts can become tomorrow's roadblocks.

The pitfalls of short-term gratification in software development are numerous. Beyond technical debt, there's the risk of building on shaky foundations, e.g., with a new and shiny framework, or becoming too rigid and inflexible in the face of change, e.g., with vendor-lock-ins. While seductive, the allure of immediate results often comes at the expense of future growth and adaptability.

When thinking of long-term vs. short-term, think of chess — if you constantly focus only on your next move, you might not even get to the endgame and vice versa; if you focus too much on the endgame, you might not survive the next move.

## **Worthy Mentions**

### **Developing a Code Nose**

Every craftsman has a finely tuned sense of their craft. A seasoned chef can tell the quality of a dish with a mere taste, a carpenter can feel the grain of the wood and know its strength, and in software development, great developers can smell bad code. It's an almost intuitive ability to sniff out the quality of code, to discern the elegant from the messy, the efficient from the sluggish.

Bad code often comes with [telltale signs](https://refactoring.guru/refactoring/smells): convoluted logic that's hard to follow, lack of documentation making it incomprehensible to others, or repetitive patterns that scream inefficiency. Once you know what to look for, it stands out. And good developers have experienced enough bad code that it stands out for them.

On the flip side, good code has its own signature. It's clean, modular, and self-explanatory. It's efficient without being overly complex. It's the kind of code that not only performs its function but does so in an elegant and maintainable way. It’s aesthetically pleasing to read and follow.

*But how does one develop this "code nose"?* Quite simple. It comes with experience, exposure, and conscious effort. It's about immersing oneself in various codebases, both good and bad, and analyzing them. It's about seeking feedback, being open to criticism, and continuously learning. Over time, developers begin to see patterns, understand common pitfalls, and recognize best practices. They start to develop an instinct for what works and what doesn't.

And this developed instinct leads me to the next point.

### **Strong Opinions loosely held**

You develop your own touch over the years. Your own conviction that something is better. The software industry, by its very nature, is [subjective](https://vadimkravcenko.com/shorts/software-development-subjective/). What works for one project or team might not work for another. Solutions that are hailed as revolutionary by some might be deemed redundant by others. There are constant holy wars happening on which framework is better, which style of function is the best, which Linux distro is the king, and so on.

These are all strong opinions that we developers gather throughout our careers. Strong opinions are important because they showcase a developer's engagement with their craft, willingness to take a stand, and commitment to excellence. An informed opinion is a testament to a developer's expertise.

However, as valuable as strong opinions are, they must be tempered with flexibility. The tech world is in constant flux, with new tools, methodologies, and paradigms emerging regularly. Clinging rigidly to an opinion, especially in the face of new information or changing circumstances, can be a recipe for stagnation. It's akin to anchoring oneself to a sinking ship simply because it was once deemed unsinkable.

It's important to be confident in one's beliefs yet open to change. It's important to truly listen to contradictory viewpoints, to weigh them against one's own opinions, and to be willing to adapt if needed. This flexibility doesn't signify weakness; on the contrary, it showcases strength, maturity, and a commitment to continuous learning.

This is it.

I'd like to hear your thoughts on these habits/traits in the comments and I'm sure you have your own strong beliefs what a great developer is and isn't. Share them in the comments.

---

Other [Newsletter](https://vadimkravcenko.com/newsletter/) Issues:

-   [Networking as an introvert CTO](https://vadimkravcenko.com/shorts/networking-introvert-cto/)
-   [Rules of Thumb for Software Development Estimations](https://vadimkravcenko.com/shorts/project-estimates/)
-   [What does a CTO actually do?](https://vadimkravcenko.com/shorts/what-cto-does/)
-   [Things they didn’t teach you about Software Engineering](https://vadimkravcenko.com/shorts/things-they-didnt-teach-you/)
