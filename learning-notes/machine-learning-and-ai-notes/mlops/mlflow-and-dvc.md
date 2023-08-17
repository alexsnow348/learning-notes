
MLflow
---------
MLflow က ဆိုရင် platform acoustics ဖြစ်ပါတယ်။

သူရဲ့ အဓိက components တွေကတော့
 - Tracking Server ( Rest API )
 - Backend (Database)
 - Artifact Storage (eg. HDFS, S3, SFTP)
 - Project - docker or conda ကို ပြီး manage လုပ်နိုင်သည်။
 - Model Registry

DVC - Data Version Control
--------
- A way to manage data version similar to git
- complements and augments an ordinary git repo


Kedro, Kedro-Viz
----

Minio 
-----

Streamlit
-----


![[dvc-minio-mlflow.png]]


![[mlflow-with-minio-postgresql.png]]

Kubeflow 
----

references များ 
-----

1. [Track DVC Pipeline Runs with MLflow](https://www.sicara.fr/blog-technique/dvc-pipeline-runs-mlflow)
2. [How to Build Customizable Web UI for ML with Streamlit and DVC](https://www.sicara.fr/blog-technique/dvc-streamlit-webui-ml)
3. [Automate DVC Pipelines Reproduction with Makefile](https://www.sicara.fr/blog-technique/automate-dvc-pipelines-reproduction-with-makefile)
4. [kedro-mlflow-example](https://github.com/tgoldenberg/kedro-mlflow-example)
