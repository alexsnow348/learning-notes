
### AI မှာ သုံးသော Types of data  များ
---
* **Structured** 
	* table လိုမျိုး row, columns နှင့် သပ်သပ်မှတ်မှတ် ရှိသော data များ
	* လွယ်လွယ်နဲ့ pre-designed feilds တွေ များတယ်။
	* တွက်ရချက်ရတာ လွယ်တယ်။
* **Unstructured** 
	* image, video, text - သပ်သပ်မှတ်မှတ် မရှိတာတွေများ
	* data အများစု က ဒီ type ထဲမှာ ပါပါတယ်။
	* လွယ်လွယ် တွက်ချက်လို့ မရတာတွေ များပါတယ်။

	![[structured-vs-unstructured.png]]
	
* Semi-structured data
	* unstructured နှင့် structured data တွေကို ဆက်စပ်ပေးတဲ့ annotations data လိုမျိုးကို ဆိုလိုတာ ဖြစ်ပါတယ်။
	
		![[semi-structured.png]]

### Statistical Data Types
---
- **Qualitative (categorical)** - အရည်အသွေး အသာပေး ဖော်ပြသော နံပါတ်များ
	- **Ordinal** (ordered က အရေးကြီး - ***encoding လုပ်တဲ့ အချိန်မှာ order ကို သတိထားဖို့ လို့ပါတယ်။***) - eg. test grade
	- **Nominal** (not ordered) - eg. nationality
	- quantitative အနေနဲ့ ပြောင်းဖို့ဆို encoding လုပ်ဖို့ လိုအပ်ပါတယ်။
- **Quantitative** - အရေအတွက် ကို ဖော်ပြသော ကိန်းဂဏန်း များ
	- **Continuous** (can be divided) - eg. distance
	- **Discrete** (cannot be divided) - eg. cats

### Encoding methods  များ - Structured data များအတွက် သာ သုံးကြတာများတယ်။
---
မှန်ကန်သော encoding methods ရွေးချယ်မှု ဟာဆိုရင် model training performane ကို သိသိသာသာ လွှမ်းမိုးမှုတွေ ရှိနိုင်တယ်။

* **Nominal data**
	* one hot encoding 
		- dummy encoding - dimension တွေ အနည်းငယ် လျှော့ချနိုင်။
		* effect encoding - 1, -1, 0 တွေ နဲ့ encode လုပ်
		
		![[one-hot-encoding.png]]
	
	* multiple one hot encoding
	* mean encoding
	
- **Ordinal data**
	- target guided ordinal encoding
	- label encoding 
- **Binary data**
	- binary encoding 