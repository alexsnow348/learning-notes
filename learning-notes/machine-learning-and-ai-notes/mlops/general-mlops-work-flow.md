kedro, dvc, mlflow တို့ဖြင့် တည်ဆောက်ထားသော General MLOps work-flow  တစ်ခုကို တည်ဆောက်မယ်။

၁။ ပထမဆုံး `kedro new`  ဖြင့် ml project structure တစ်ခုကို တည်ဆောက်ပါမယ်။
၂။ source code တွေကို သိမ်းဖို့အတွက် git ကို `git init` စတင်ပေးဖို့ လိုအပ်ပါမယ်။
 - data folder ကို git track ကနေ remote လုပ်ဖို့ လိုပါတယ်။
		 `git rm -r --cached 'data'` 
၃။ data တွေ သိမ်းထားဖို့ `dvc init` ဖြင့် dvc ကို စတင်ထားဖို့ လိုအပ်ပါတယ်။
၄။ remote storage မှာ data တွေ သိမ်းဖို့ setup လုပ်ရပါမယ်။


