#tensoflow #ml-ai 

TensorFlow cheatsheet သဘောမျိုး အနေဖြင့် ပြန်လည် အလွယ်တကူ လေ့လာနိုင်ဖို့ ဒီ မှတ်စုကို ထုတ်ထားတာပါ။

**Tensor ဆိုသည်မှာ** 

- Machine Learning System ​တွေမှာအသုံးပြုတဲ့ Data Structure ဖြစ်ပါတယ် ။
- Numerical Data ​တွေပါဝင်တဲ့ Data Structure ပါ ။
- ဥပမာ - Matrix ​တွေဟာ 2 Dimensional Tensor ပါပဲ ။
- Tensor ​တွေမှာ 3D, 4D, 5D... စသဖြင့် Dimension အများကြီးရှိနိုင်ပါတယ် ။

![[tensor.png]]


**Tensor ပါတဲ့  attributes  ၃ ခု** 

1. number of axes (rank) : (x.ndim) =  a 3d tensor has 3 axes and a matrix has 2 axes
2. Shape : (x.shape) = Tensor ၁ ခု ၏ axis ၁ခုချင်းစီတွင် ရှိသည့် element အ​ရေအတွက်ကို​ဖော်ပြသည်။
3. Data type : (x.dtype) = Tensor တွင်ပါရှိသည့် element များ၏ data type ကို​ဖော်ပြသည်။ float32, unit8, float64, etc


**အခြေခံများ**

- Shape: Tensor ၁ခု၏ axis ၁ခုချင်းစီတွင် ရှိသည့် element အ​ရေအတွက်ကို​ဖော်ပြသည်။
- Rank: Tensor ၁ ခုတွင်ရှိသည့် axis (သို့) dimension အ​ရေအတွက်ကို​ဖော်ပြသည်။ 3D tensor တွင် axis (သို့) dimension 3 ခုရှိပြီး 2D tensor(Matrix) တွင် axis 2 ခုရှိသည်။ Scalar သည် rank 0 tensor ဖြစ်ပြီး vector သည် rank 1 ၊ matrix သည် rank 2 tensor ဖြစ်သည်။
- Axis or Dimension: Tensor ၏ သက်ဆိုင်ရာ Dimension ကိုရည်ညွှန်းသည်။ ဥပမာ - 2D tensor တွင် axis 0 သည် row ကိုရည်ညွှန်းပြီး axis 1 သည် column ကိုရည်ညွှန်းသည်။
- Size: Tensor ၁ခုရှိ element စုစု​ပေါင်းအ​ရေအတွက်ကို​ဖော်ပြသည်။

  
**အသုံးပြုနိုင်သော အခြေခံ funtions များ**

- tf.convert_to_tensor() – python list (သို့) numpy array အား tensor သို့​ပြောင်းလဲသည်။
- tf.constant() - constant value များဖြင့် tensor ပြုလုပ်သည်။
- x.dtype – Tensor တွင်ပါရှိသည့် element များ၏ data type ကို​ဖော်ပြသည်။
- x.size – Tensor ၁ ခုရှိ element စုစု​ပေါင်းအ​ရေအတွက်ကို​ဖော်ပြသည်။
- x.ndim – Tensor ၁ ခုတွင်ရှိသည့် axis (သို့) dimension အ​ရေအတွက်ကို​ဖော်ပြသည်။
- x.shape – Tensor ၁ ခု ၏ shape ကို​ဖော်ပြသည်။

