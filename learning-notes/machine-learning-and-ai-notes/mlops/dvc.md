DVC - Data Version Control
--------
- A way to manage data version similar to git - metadata တွေကို git လိုမျိုး command တွေနဲ့ သိမ်းထားနိုင်သည်။
- complements and augments an ordinary git repo

![[dvc-with-minio.png]]
Machine Learning Development Workflow
----
- DVC က အထူးသဖြင့် data management and analysis လုပ်ဖို့ရယ်၊ Experiment တွေကို tracking လုပ်တဲ့ နေရာ မှာ  အသုံးများတယ်။
- အထူသဖြင့် data quality issues, not reproducible, sharing and collaboration စတဲ့ ပြဿနာတွေကို ဦးစားပေး ဖြေရှင်ပေးဖို့ လုပ်ထားတာ ဖြစ်တယ်။ 

### Experiment = code + dataset + outputs

- artifacts
- pipelines
- code
- configs

![[ml-work-flow-and-tools.png]]
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