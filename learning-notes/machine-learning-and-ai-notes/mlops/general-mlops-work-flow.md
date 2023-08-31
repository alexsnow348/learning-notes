# General MLOps Workflow
--- 
## Steps

kedro, dvc, mlflow တို့ဖြင့် တည်ဆောက်ထားသော General MLOps work-flow  တစ်ခုကို တည်ဆောက်မယ်။

၁။ ပထမဆုံး `kedro new`  ဖြင့် ml project structure တစ်ခုကို တည်ဆောက်ပါမယ်။
	[[kedro-workflow#Useful command]]
	
၂။ source code တွေကို သိမ်းဖို့အတွက် git ကို `git init` စတင်ပေးဖို့ လိုအပ်ပါမယ်။ တကယ်လို့ data folder ကို git track ခဲ့မိရင် git ကနေ remove လုပ်ဖို့ လိုပါတယ်။ 
```bash
git rm -r --cached 'data'
```

၃။ data တွေ သိမ်းထားဖို့ `dvc init` ဖြင့် dvc ကို စတင်ထားဖို့ လိုအပ်ပါတယ်။

၄။ remote storage မှာ data တွေ သိမ်းဖို့ setup လုပ်ရပါမယ်။
	[[dvc#Data Versioning with DVC (with remote storage like S3)]]
	
၅။ kedro-mlflow ကို သုံးပြီး machine learning experiments တွေကို tracking လုပ်မယ်။

```bash
kedro mlflow init
```

