#tensoflow #ml-ai 

### **အခြေခံများ**
----------------
TensorFlow cheatsheet သဘောမျိုး အနေဖြင့် ပြန်လည် အလွယ်တကူ လေ့လာနိုင်ဖို့ ဒီ မှတ်စုကို ထုတ်ထားတာပါ။

- **Tensor ဆိုသည်မှာ** 
	- Machine Learning System ​တွေမှာအသုံးပြုတဲ့ Data Structure ဖြစ်ပါတယ် ။
	- Numerical Data ​တွေပါဝင်တဲ့ Data Structure ပါ ။
	- ဥပမာ - Matrix ​တွေဟာ 2 Dimensional Tensor ပါပဲ ။
	- Tensor ​တွေမှာ 3D, 4D, 5D... စသဖြင့် Dimension အများကြီးရှိနိုင်ပါတယ် ။

- **Tensor ပါတဲ့  attributes  ၃ ခု** 
	1. number of axes (rank) : (x.ndim) =  a 3d tensor has 3 axes and a matrix has 2 axes
	2. Shape : (x.shape) = Tensor ၁ ခု ၏ axis ၁ခုချင်းစီတွင် ရှိသည့် element အ​ရေအတွက်ကို​ဖော်ပြသည်။
	3. Data type : (x.dtype) = Tensor တွင်ပါရှိသည့် element များ၏ data type ကို​ဖော်ပြသည်။ float32, unit8, float64, etc

	![[tensor.png]]


- **Tensor ရဲ့  အခြေခံများ**
	- Shape: Tensor ၁ခု၏ axis ၁ခုချင်းစီတွင် ရှိသည့် element အ​ရေအတွက်ကို​ဖော်ပြသည်။
	- Rank: Tensor ၁ ခုတွင်ရှိသည့် axis (သို့) dimension အ​ရေအတွက်ကို​ဖော်ပြသည်။ 3D tensor တွင် axis (သို့) dimension 3 ခုရှိပြီး 2D tensor(Matrix) တွင် axis 2 ခုရှိသည်။ Scalar သည် rank 0 tensor ဖြစ်ပြီး vector သည် rank 1 ၊ matrix သည် rank 2 tensor ဖြစ်သည်။
	- Axis or Dimension: Tensor ၏ သက်ဆိုင်ရာ Dimension ကိုရည်ညွှန်းသည်။ ဥပမာ - 2D tensor တွင် axis 0 သည် row ကိုရည်ညွှန်းပြီး axis 1 သည် column ကိုရည်ညွှန်းသည်။
	- Size: Tensor ၁ခုရှိ element စုစု​ပေါင်းအ​ရေအတွက်ကို​ဖော်ပြသည်။

- **အသုံးပြုနိုင်သော အခြေခံ funtions များ**
	- tf.convert_to_tensor() – python list (သို့) numpy array အား tensor သို့​ပြောင်းလဲသည်။
	- tf.constant() - constant value များဖြင့် tensor ပြုလုပ်သည်။
	- x.dtype – Tensor တွင်ပါရှိသည့် element များ၏ data type ကို​ဖော်ပြသည်။
	- x.size – Tensor ၁ ခုရှိ element စုစု​ပေါင်းအ​ရေအတွက်ကို​ဖော်ပြသည်။
	- x.ndim – Tensor ၁ ခုတွင်ရှိသည့် axis (သို့) dimension အ​ရေအတွက်ကို​ဖော်ပြသည်။
	- x.shape – Tensor ၁ ခု ၏ shape ကို​ဖော်ပြသည်။
	
```python
import tensorflow as tf
numpy_array = [1,2,3,4]
numpy_to_tensor = tf.convert_to_tensor(numpy_array, dtype=tf.int32)
numpy_to_tensor.size
numpy_to_tensor.ndim
numpy_to_tensor.shape
```

### **အခြေခံ tensorflow constants များ တည်ဆောက်ပြီး manipulate လုပ်မယ်။**
----
- **Constants တည်ဆောက်ခြင်း**

```python
ones = tf.ones((2,3)) # 1 တွေကြီး သီးသန့် (၂,၃) shape ရှိတဲ့ matrix ကို ဖန်တီးပေး။
zeros = tf.zeros([3,4]) # 0 တွေကြီး သီးသန့် (၂,၃) shape ရှိတဲ့ matrix ကို ဖန်တီးပေး။
constants = tf.constant([1, 2, 3, 4, 5], dtype=tf.int32) # constant တွေကို ဖန်းတီးပေး။
# 0D tensor - Scalar
o_d =  tf.constant(2.0, dtype=tf.float32)
# 1D tensor - Vector
one_d = tf.constant([2.0,0.9], dtype=tf.float32)
# 2D tensor - Matrix
two_d = tf.constant([[2.0,0.9],[1.0,0.1]], dtype=tf.float32)
# 3D tensor
three_d = tf.constant([[[2.0,0.9],[1.0,0.1]], [[2.0,0.9],[1.0,0.1]], [[2.0,0.9],[1.0,0.1]]], dtype=tf.float32)
```

- **tf မှာ constant နဲ့ variable က ဘာကွာတာလဲ။**
	- Constants
		- Constants တွေဟာဆိုရင် သူတို့ရဲ့ value တွေကို သတ်မှတ်ပေးပြီးဆိုရင် နောက်ထပ်ပြန်ပြောင်လို့ မရတော့ပါဘူး။
		- Constants တွေက graph တွေ အဖြစ် သိမ်းထားတာမို့လို့ သူဟာ memory အရမ်းစားပါတယ်။ Constants တွေ အရမ်းများနေရင် graph တွေ တွက်တဲ့နေရာမှာ နှေးကွေးမှုတွေဖြစ်လာပြီး၊ computing resource တွေ အရမ်း သုံးရပါလိမ့်မယ်။
	- Variable
		- Variable တွေဟာဆိုရင် သူတို့ value တွေကို ပြောင်းလဲခွင့်ပြုထားပါတယ်။ အထူးသဖြင့် network parameters တွေ ဖြစ်တဲ့ weight တို့ biases တို့လို နေရာမျိုး မှာ အသုံးများကြပါတယ်။
	- Placeholder 
		- ယာယီ data type ပြောပြီး တည်ဆောက်ထားပြီး နောက်မှ values တွေ ထည့်ဖို့ လိုတဲ့ နေရာမှာ အသုံးများကြပါတယ်။
	
	
- **Variable တည်ဆောက်ခြင်း**

```python
s = tf.Variable(2, name="scalar") 
m = tf.Variable([[1, 2], [3, 4]], name="matrix") 
W = tf.Variable(tf.zeros([784,10])) # weight ကို စတင် zero တွေ ပေးထားတဲ့ နေရာမျိုးမှာသုံး
# constant မှ variable အဖြစ်ပြောင်းခြင်
my_tensor = tf.constant([[1.0, 2.0], [3.0, 4.0]]) 
my_var = tf.Variable(my_tensor)
```

* **Placeholder တွေ တည်ဆောက်ခြင်း**

```python
a = tf.placeholder(tf.float32, shape=[5])
b = tf.placeholder(dtype=tf.float32, shape=None, name=None)
X = tf.placeholder(tf.float32, shape=[None, 784], name='input')
Y = tf.placeholder(tf.float32, shape=[None, 10], name='label')
```
#### **Data shape တွေကို manipulate ကစားခြင်း**
---

- **2D ကနေ 3D သို့ expand လုပ်ခြင်း**
	
```python
zeros_tensor = tf.zeros([3,2])
zeros_numpy = zeros_tensor.numpy()
new_shape_array_0 = np.expand_dims(zeros_numpy, axis=0) # (1, 3, 2)
new_shape_array_1 = np.expand_dims(zeros_numpy, axis=1) # (3, 1, 2)
new_shape_array_2 = np.expand_dims(zeros_numpy, axis=2) # (3, 2, 1)
zeros_new_front = zeros_numpy[np.newaxis, ...] # (1, 3, 2)
zeros_new_back = zeros_numpy[..., np.newaxis] # (3, 2, 1)
```

* **6D ကနေ 4D သို့ reduce လုပ်ခြင်း**

```python
ones_tensor = tf.ones((3, 1, 2, 1, 4, 1))
ones_reduce = tf.squeeze(ones_tensor, axis=(1,3)) # (3, 2, 4, 1) - axis မှာ ပေးထားတဲ့ position မှာရှိတဲ့ 1 တွေကိုသာ ဆွဲထုတ်ပေးနိုင်သည်။
```

* **Shape တွေကို manipulate လုပ်ခြင်း**

```python
zeros_tensor_transpose = tf.transpose(zeros_tensor) # TensorShape([2, 3])
new_shaped_zeros = zeros_tensor.reshape(2,3) # TensorShape([2, 3])

```
* **Data Type တွေကို manipulate လုပ်ခြင်း**

```python
float_tensor = tf.constant([1.0,3.4,1.6], dtype=tf.float32)
int_tensor = tf.cast(float_tensor, tf.int32)
```

### သင်္ချာ တွေ တွက်ကြမယ်။

* **Element wise မြှောက်ခြင်း**

```python
tensor_one = tf.constant([1,3,5], dtype=tf.int32)
tensor_two = tf.constant([2,4,6], dtype=tf.int32)
multiply_tensor = tf.multiply(tensor_one, tensor_two)
multiply_tensor.numpy() # array([ 2, 12, 30], dtype=int32)

```

- **Mean ကို axis ပေါ်မှုတည်ပြီး ရှာခြင်း**

```python
# find mean along a given axis
matrix_tensor = tf.Variable([[1, 2, 3], [4, 5, 6]], name="matrix")
mean_ax_0 = tf.math.reduce_mean(matrix_tensor, axis=0)
print(mean_ax_0.numpy()) # [2 3 4]
mean_ax_1 = tf.math.reduce_mean(matrix_tensor, axis=1)
print(mean_ax_1.numpy()) # [2 5]
mean = tf.math.reduce_mean(matrix_tensor)
print(mean.numpy()) # 3
```

- S**um ကို axis ပေါ်မှုတည်းပြီး ရှာခြင်း**

```python

```