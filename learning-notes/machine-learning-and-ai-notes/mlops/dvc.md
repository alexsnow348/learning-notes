# DVC - Data Version Control
--------
- A way to manage data version similar to git - metadata တွေကို git လိုမျိုး command တွေနဲ့ သိမ်းထားနိုင်သည်။
- complements and augments an ordinary git repo

![[dvc-with-minio.png]]
![[ml-work-flow-and-tools.png]]

Machine Learning Development Workflow
----
- DVC က အထူးသဖြင့် data management and analysis လုပ်ဖို့ရယ်၊ Experiment တွေကို tracking လုပ်တဲ့ နေရာ မှာ  အသုံးများတယ်။
- အထူသဖြင့် data quality issues, not reproducible, sharing and collaboration စတဲ့ ပြဿနာတွေကို ဦးစားပေး ဖြေရှင်ပေးဖို့ လုပ်ထားတာ ဖြစ်တယ်။ 


![[ml-experiments.png]]
### Experiment = code + dataset + outputs

- artifacts
- pipelines
- code
- configs

### Reproducibility 

- အရေးကြီးကတော့ reproducibility ဖြစ်ဖို့ လုပ်ပေးတဲ့ အရာတစ်ခုပဲ ဖြစ်ပါတယ်။
- Checklist:
	1. environment dependency control
	2. code version control
	3. control run params
	4. automated pipelines
	5. artifact version control
	6. experiment results tracking
	7. automated ci/cd and MLOps

![[reproductibility.png]]

### Collaboration for data and model 

![[data-sharing.png]]
### Installing DVC

```bash
pip install dvc
pip install "dvc[s3]" # for s3 relate remote artifacts storage
```

### Initialise  DVC 

```bash
dvc init
```

### Data Versioning with DVC (with remote storage like S3)

1. Set up remote storage bucket - S3 လိုမျိုး services 

```shell
dvc remote add -d s3-data-storage s3://<bucket-path>/
```

2. Add the storage server end point

```shell
dvc remote modify s3-data-storage endpointurl <url-with-port>
```

3. Configure the remote storage access credentials

```shell
dvc remote modify --local s3-data-storage access_key_id <id>
dvc remote modify --local s3-data-storage secret_access_key <key>
```

4. Add data

```shell
dvc add data 
```

5. Push the data 

```shell
dvc push -v # v for verbose for showing more detail info
```

6. Pull the data from remote

```bash
dvc pull -v
```
### Working with difference branch with DVC

```shell
dvc checkout # branch တွေပြောင်တဲ့အခါကြရင် dvc ကို လည်း checkout လုပ်ဖို့လိုပါတယ်။
```


Reference 
---
1. [[dvc-slide-1-intro.pdf]]
2. [[dvc-slide-2-practices-and-tools-for-efficient-collaboration-in-ML-projects.pdf]]
3. [[dvc-slide-3-pipelines-automation-and-configuration-management.pdf]]
4. [[dvc-slide-4-versioning-and-sharing-data.pdf]]
5. [[dvc-slide-5-visualize-metrics-and-plot.pdf]]
6. [[dvc-slide-6-experiment-management-and-collaboration.pdf]]
7. [[dvc-slide-7-advanced-topics-and-usecases.pdf]]
8. [data-science-blueprint](https://data-science-blueprint.readthedocs.io/)
9. https://realpython.com/python-data-version-control/ 