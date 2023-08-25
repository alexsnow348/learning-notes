DVC - Data Version Control
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

Reference 
---
1. [[dvc-slide-1-intro.pdf]]
2. [[dvc-slide-2-practices-and-tools-for-efficient-collaboration-in-ML-projects.pdf]]
3. [[dvc-slide-3-pipelines-automation-and-configuration-management.pdf]]
4. [[dvc-slide-4.pdf]]
5. [[dvc-slide-5.pdf]]
6. [[dvc-slide-6.pdf]]
7. [[dvc-slide-7.pdf]]
8. [data-science-blueprint](https://data-science-blueprint.readthedocs.io/)
9. 