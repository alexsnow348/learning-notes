# Kedro, Kedro-Viz, Kedro-mlflow
----
- ML/Data Science project တွေအတွက် သေသေချာချာစနစ်တကြ organised ဖြစ်အောင်နဲ့ reproduce လုပ်တာ လွယ်အောင်လို့ လုပ်ပေးတဲ့ python framework တစ်ခုဖြစ်ပါတယ်။

### Installation

```bash
pip install kedro kedro-viz kedro-mlflow
```

### Useful command

```bash
kedro new # to create new kedro project
kedro pipeline create <pipeline_name> # to create new pipeline 
kedro run # run all the nodes from pipeline
kedro run --pipeline=<pipeline_name> # run speficfic pipeline only
kedro run --runner=SequentialRunner # runs nodes sequentially
kedro run --runner=ParallelRunner # runs independent nodes in parallel via multiprocessing
kedro run --runner=ThreadRunner # similar to parallel runner but used multithreading instead of multiprocessing especailly for Spark and Dask
kedro run --runner=module.path.to.my.runner 
kedro mlflow init # to update for mlflow tracking
```


reference list
---
1. [The importance of layered thinking in data engineering](https://towardsdatascience.com/the-importance-of-layered-thinking-in-data-engineering-a09f685edc71)
2. 