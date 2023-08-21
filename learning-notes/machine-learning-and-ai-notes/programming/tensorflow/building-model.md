

Create the Model
---
- Keras Sequential Model API အားအသုံးပြု၍ Model တည်​ဆောက်မည်။
- Tensorflow 2.0 မှစ၍ Keras API သည် model တည်​ဆောက်ရန် default အ​နေနှင့်ပါလာသည်။
- Sequential Model ၏ ပထမဦးဆုံး layer တွင် Model Training ပြုလုပ်ရာတွင်အသုံးပြုမည့် Dataset ၏ shape အားထည့်သွင်း​ပေးရမည်။
- သို့မှသာ model.summary() အသုံးပြုလို့ရမည်။
- input shape တွင် number of samples (batch size) ထည့်သွင်း​ပေးစရာမလို။
- E.g. Dataset ၏ shape သည် (60000, 28, 28) ဖြစ်လျှင် input_shape = (28, 28) သာထည့်​ပေးရမည်။
- **Dense layer** ဆိုတာ fully connected layer ကိုဆိုလိုတာဖြစ်ပါတယ်။ သူကိုသုံးပြီးတော့ အရင် layer က ပါတဲ့ neurons တွေနဲ့ ဆက်စပ်ပြီး connect လုပ်ထားတဲ့ a set of neurons or units of neurons တွေကို တည်ဆောက်ထားနိုင်ပါတယ်။
- သူမှာ အဓိက ပါတာတွေကတော့
	- **Neurons**
	- **Activation Function**
	- **Weight Initialization**
	- **Bias** 
	    
```python
from tensorflow.keras import Sequential
from tensorflow.keras.layers import Dense

model = Sequential([
    Dense(units=1, input_shape=(1,))
])
model_2 = Sequential()
model_2.add(Dense(units=1, input_shape=(1,)))
model.summary()
model_2.summary()

# Model: "sequential_3" _________________________________________________________________ 
# Layer (type)             Output Shape               Param # ================================================================= 
# dense_3 (Dense)           (None, 1)                2 =================================================================
# Total params: 2 (8.00 Byte) 
# Trainable params: 2 (8.00 Byte) 
# Non-trainable params: 0 (0.00 Byte) _________________________________________________________________
```

Compile the model
---
Model Compile လုပ်ရာတွင် ထည့်သွင်း​ပေးရမည့် အချက်များ

- Model Training ပြုလုပ်ရာတွင် အသုံးပြုမည့် Optimisation Algorithm
- Model output ၏ error ကိုတွက်ချက်ရာတွင်အသုံးပြုမည့် Loss Function
- (Optional) - Model ၏ Performance ကိုတိုင်းတာမည့် metrics

```python
model.compile(
    optimizer='sgd',# stochastic gradient descent
    loss= 'mean_squared_error',
    metrics=['mae']
)
```

Fit the model
---

- Model ကို Train လုပ်​စေခြင်း ဖြစ်သည်။
- History Object အားထုတ်​ပေးသည်။
- History Object ထဲတွင် Training ပြုလုပ်စဥ်အတွင်း ​ပြောင်းလဲခဲ့​သော Loss နှင့် Metrics တန်ဖိုးများပါဝင်သည်။

```python
model.fit(x, y, epochs=1000)
```

- Durning the one epoch
 ![[during-one-epoch.png]]