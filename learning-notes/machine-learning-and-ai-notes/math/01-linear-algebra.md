- [[#Systems of Linear Equations|Systems of Linear Equations]]
	- [[#Systems of Linear Equations#System of sentences|System of sentences]]
	- [[#Systems of Linear Equations#Linear equation => sentences + number|Linear equation => sentences + number]]
- [[#Singular vs Non-singular system|Singular vs Non-singular system]]
- [[#Vectors|Vectors]]
- [[#Matrix|Matrix]]
- [[#Application of Linear Algebra|Application of Linear Algebra]]
- [[#Reference|Reference]]

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
- Point A ကနေ Point B ရဲ့ distance/magnitude ကို ရှာမယ်ဆိုရင်
	
	![[l1-l2-norm.png]]
	- L1-norm distance ကို ရှာနည်း ဖြင့် ရှာနိုင်သလို့
		![[l1-norm.png]]
		
	- L2 - norm distance ရှာနည်းဖြင့်လည်း ရှာနိုင်ပါတယ်။
		![[l2-norm.png]]
- Vector  ၂ ခုရဲ့ distance ကို လိုချင်ရင်လည်း  L1-norm ဒါမှမဟုတ် L2-norm distance ကို ရှာလို့ရပါတယ်။
	![[vector-distance.png]]


## Matrix

- Matrix တွေရဲ့ dot product ကို လိုချင်ရင် row ကို column ဖြင့် မြှောက်ပေးရပါတယ်။

	![[dot-product.png]]
	![[matric-dot-product.png]]
- Matrix တွေရဲ့ inverse ကို ရှာမယ်ဆို သူရဲ့ identity matrix ကို အရင်သိဖို့ လိုပါတယ်။
- Identity matrix ဆိုတာ သူကို original matrix  နဲ့ မြှောက်ရင် original matrix ကိုပဲ ပြန်ထုတ်ပေးပါတယ်။ တကယ်လို့ သူကို matrix ရဲ့ inverse နဲ့ မြှောက်မယ်ဆိုရင်လည်း original matrix ကိုပဲ ပြန်ထုတ်ပေးပါတယ်။
![[identity-matrix.png]]
- Matrix Inverse ကို ရှာနည်း။ 
![[inverse-matrix.png]]

- တကယ်လို့ matrix က non-singular system ဖြစ်မှာသာလျှင် inverse ကို ရှာလိုရမှာပါ။ singular system ဖြစ်နေရင်တော့ inverse ကို ရှာလိုရမှာမဟုတ်ပါဘူး။
![[matrix-invertible.png]]


-  Matrix တွေရဲ့ properties တွေက  သူက non-singular system ဟုတ်မဟုတ်နဲ့ သက်ဆိုင်မှုရှိတယ်။

![[singular-and-non-singular-matrix-properties.png]]
## MIT 18.06 Linear Algebra Gilbert Strang Lecture
![[Pasted image 20230926101245.png]]
![[Pasted image 20230926101257.png]]
![[Pasted image 20230926101423.png]]


![[Pasted image 20230926101443.png]]
![[Pasted image 20230926101532.png]]
![[Pasted image 20230926101545.png]]
![[Pasted image 20230926101556.png]]
![[Pasted image 20230926101604.png]]
![[Pasted image 20230926101612.png]]
![[Pasted image 20230926101621.png]]
![[Pasted image 20230926101635.png]]
![[Pasted image 20230926101644.png]]
## Application of Linear Algebra

- **Data Representation** 
![[data-representation.png]]

- **Principal Component Analysis** - dimensionality reduction  method


![[principal-component-analysis.png]]

- Support Vector Machine မှာလဲ linear algebra ကို အသုံးပြုထားပါတယ်။

## Reference 
1. https://www.coursera.org/learn/machine-learning-linear-algebra 
2. https://www.visual-design.net/post/linear-algebra-for-machine-learning
3. https://www.visual-design.net/post/linear-algebra-for-ml-part2-principal-component-analysis
4. 