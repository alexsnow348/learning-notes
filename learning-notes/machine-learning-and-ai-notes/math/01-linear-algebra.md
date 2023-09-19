
# Linear Algeria
---
## Systems of Linear Equations
### System of sentences

- Non-sigular system - complete (ပြဿနာ တစ်ခုကို ဖြေးရှင်ရန် လိုအပ်သော information အားလုံးများ ပေးထားခြင်း)
- Singular
	- Redundant - (တူညီသော info များ ပေးထားခြင်း)
	- Contradictory - (တစ်ခုတည်ကို ဆန့်ကျင်ဘက် info ၂ မျိုးပေးထားခြင်း)

### Linear equation => sentences + number

- multiply with scalar 
- add constant
- subtract constant 
![[linear-equation.png]]

## Singular vs Non-singular system

- Singular System
	- determinant က အမြဲတမ်း zero ပဲဖြစ်နေပါမယ်။
	- multiple solution အဖြေးတွေကို ထုတ်ပေးနိုင် သလို့၊ အဖြေး လုံးဝ မရှိတာလဲ ဖြစ်နိုင်တယ်။
	- matrix မှာ inverse ရှာလို့မရပါ။
- Non-singular system
	- determinant က အမြဲတမ် non-zero ပဲဖြစ်နေပါမယ်။
	- unique solution အဖြေကို တစ်ခုခု ရှိကို နေနေတယ်။
	- matrix မှာ inverse ရှာလိုရတယ်။

## Vectors

- Vector တစ်ခုရဲ့ ဂုဏ်သတ္တိအနေနဲ့  direction နှင့် magnitude or size ဆိုပြီး ရှိပါတယ်။
- Point A ကနေ Point B ရဲ့ distance ကို ရှာမယ်ဆိုရင်
	
	![[l1-l2-norm.png]]
	- L1-norm distance ကို ရှာနည်း ဖြင့် ရှာနိုင်သလို့
		![[l1-norm.png]]
		
	- L2 - norm distance ရှာနည်းဖြင့်လည်း ရှာနိုင်ပါတယ်။
		![[l2-norm.png]]
- Vector  ၂ ခုရဲ့ distance ကိုလည်း လိုချင်ရင် L1-norm ဒါမှမဟုတ် L2-norm distance ကို ရှာလို့ရပါတယ်။
	![[vector-distance.png]]
## Matrix

- Matrix တွေရဲ့ dot product ကို လိုချင်ရင် row ကို column ဖြင့် မြှောက်ပေးရပါတယ်။

	![[dot-product.png]]
	![[matric-dot-product.png]]
- Matrix တွေရဲ့ inverse ကို ရှာမယ်ဆို သူရဲ့ identity matrix ကို အရင်သိဖို့ လိုပါတယ်။
- Identity matrix ဆိုတာ သူကို original matrix  နဲ့ မြှောက်ရင် original matrix ကိုပဲ ပြန်ထုတ်ပေးပါတယ်။ တကယ်လို့ သူကို matrix ရဲ့ inverse နဲ့ မြှောက်မယ်ဆိုရင်လည်း original matrix ကိုပဲ ပြန်ထုတ်ပေးပါတယ်။
![[identity-matrix.png]]