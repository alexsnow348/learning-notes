MLFlow
---------
MLflow က ဆိုရင် platform acoustics ဖြစ်ပါတယ်။ Machine Learning model တွေကို training လုပ်တဲ့ နေရာမှာနဲ့ deployment လုပ်တာတွေကို သေသေချာချာ tracking လုပ်ပေးနိုင်တဲ့ python ကို အခြေခံထားတဲ့ open source library တစ်ခုဖြစ်ပါတယ်။

သူရဲ့ အဓိက components တွေကတော့
 - Tracking Server မှာ track လုပ်ချင်တဲ့ အရာအားလုံးကို track လုပ်ထားနိုင်တယ်။ ဥပမာ - code, data, config, results
 - Backend (Database) နေရာမှာ SQL လိုမျိုး relational database တွေနဲ့ ချိတ်ဆက်ပြီး သုံးစွဲနိုင်တယ်။
 - Artifact Storage (eg. HDFS, S3 -MinIO, SFTP) စသည်တို့ဖြစ်လုပ်နိုင်တယ်။
 - Project - docker or conda ကို ပြီး manage လုပ်နိုင်သည်။
 - Model Registry - training လုပ်ပြီး အကောင်းဆုံး performance ရတဲ့ model တွေကို သူများတွေ ယူသုံးနိုင်ဖို့ registry မှာ တစ်နေရာထဲမှာ သိမ်းထားပေးနိုင်ပါတယ်။

![[mlflow.png]]
DVC - Data Version Control
--------
- A way to manage data version similar to git - metadata တွေကို git လိုမျိုး command တွေနဲ့ သိမ်းထားနိုင်သည်။
- complements and augments an ordinary git repo

![[dvc-with-minio.png]]


MinIO - High Performance Object Storage for AI
-----
- S3 Object Storage ပုံစံ တစ်ခုဖြစ်ပါတယ်။
- data lake တွေ တည်ဆောက်တဲ့ နေရာမှာ အသုံးပြုနိုင်တယ်။
- unstructured data တွေ ဖြစ်တဲ့ photos, videos, logs files, backups and container images တွေကိုသိမ်းထားနိုင်ပါတယ်။

Sample MLOps pipeline with dvc, minio, mlflow and postgresql
----


![[dvc-minio-mlflow.png]]


![[mlflow-with-minio-postgresql.png]]


references များ 
-----

1. [Track DVC Pipeline Runs with MLflow](https://www.sicara.fr/blog-technique/dvc-pipeline-runs-mlflow)
2. [How to Build Customizable Web UI for ML with Streamlit and DVC](https://www.sicara.fr/blog-technique/dvc-streamlit-webui-ml)
3. [Automate DVC Pipelines Reproduction with Makefile](https://www.sicara.fr/blog-technique/automate-dvc-pipelines-reproduction-with-makefile)
4. [kedro-mlflow-example](https://github.com/tgoldenberg/kedro-mlflow-example)
5. [Setting up MinIO and MLflow](https://blog.min.io/setting-up-a-development-machine-with-mlflow-and-minio/)
6. [GitHub Settup repo](https://github.com/alexsnow348/mlflow-dvc-postgres-minio)

