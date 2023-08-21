

Create the Model
---
- Keras Sequential Model API အားအသုံးပြု၍ Model တည်​ဆောက်မည်။
- Tensorflow 2.0 မှစ၍ Keras API သည် model တည်​ဆောက်ရန် default အ​နေနှင့်ပါလာသည်။
- Sequential Model ၏ ပထမဦးဆုံး layer တွင် Model Training ပြုလုပ်ရာတွင်အသုံးပြုမည့် Dataset ၏ shape အားထည့်သွင်း​ပေးရမည်။
- သို့မှသာ model.summary() အသုံးပြုလို့ရမည်။
- input shape တွင် number of samples (batch size) ထည့်သွင်း​ပေးစရာမလို။
- E.g. Dataset ၏ shape သည် (60000, 28, 28) ဖြစ်လျှင် input_shape = (28, 28) သာထည့်​ပေးရမည်။