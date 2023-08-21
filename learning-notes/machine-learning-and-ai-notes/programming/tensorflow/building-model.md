Create the Model
---
- Keras Sequential Model API အားအသုံးပြု၍ Model တည်​ဆောက်မည်။
- Tensorflow 2.0 မှစ၍ Keras API သည် model တည်​ဆောက်ရန် default အ​နေနှင့်ပါလာသည်။
- Sequential Model ၏ ပထမဦးဆုံး layer တွင် Model Training ပြုလုပ်ရာတွင်အသုံးပြုမည့် Dataset ၏ shape အားထည့်သွင်း​ပေးရမည်။
- သို့မှသာ model.summary() အသုံးပြုလို့ရမည်။
- input shape တွင် number of samples (batch size) ထည့်သွင်း​ပေးစရာမလို။
- E.g. Dataset ၏ shape သည် (60000, 28, 28) ဖြစ်လျှင် input_shape = (28, 28) သာထည့်​ပေးရမည်။
- **Dense layer** ဆိုတာ fully connected layer ကိုဆိုလိုတာဖြစ်ပါတယ်။ သူကိုသုံးပြီးတော့ အရင် layer က ပါတဲ့ neurons တွေနဲ့ ဆက်စပ်ပြီး connect လုပ်ထားတဲ့ a set of neurons or units of neurons တွေကို တည်ဆောက်ထားနိုင်ပါတယ်။

		![[dense-layer.png]]

- သူမှာ အဓိက ပါတာတွေကတော့
	- **Neurons**
	- **Activation Function**
	- **Weight Initialisation**
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

Fit/Train the model
---

- Model ကို Train လုပ်​စေခြင်း ဖြစ်သည်။
- History Object အားထုတ်​ပေးသည်။
- History Object ထဲတွင် Training ပြုလုပ်စဥ်အတွင်း ​ပြောင်းလဲခဲ့​သော Loss နှင့် Metrics တန်ဖိုးများပါဝင်သည်။

```python
model.fit(x, y, epochs=1000)
```

- iteration - batch size မှာ ပါတဲ့  data ကိုပဲ ကြည့်ပြီးမှ loss ကို တွက်တယ်။
- epoch - data အားလုံးကို တစ်ပတ်ကြည့်ပြီးမှ loss ကို တွက်တယ်။
  တကယ်လို့ စုစုပေါင်း data ရဲ့ size က ၁၀၀၀ ဆိုပါစို့။ batch size ကို ၁၀၀ ထားမယ်ဆိုရင် ၁၀၀၀/၁၀၀ ဆိုရင် စုစုပေါင်း   iteration ၁၀ ခါပြီးမှသာလျှင်  epoch တစ်ခါ ပြီးမှာဖြစ်ပါတယ်။ 

- During one epoch မှာ forward pass လုပ်ပြီး error တွက်တယ်။ ပြီးတော့မှာ backward pass လုပ်ပြီးမှ weight နဲ့ bias ကို ပြန် update ပြင်ပါတယ်။

	 ![[during-one-epoch.png]]

Test the model
---

```python
test_data = np.array([15, 23, 50], dtype = np.float32)
predictions = model.predict(test_data)
print(predictions)
# [[16.043098] [24.07337 ] [51.175537]]
```


Callbacks
---
- သူကို model တွေရဲ့ training ကို ကိုယ်လိုချင်တဲ့ ရလဒ် ရတာနဲ့ ရပ်ခိုင်တာမျိုး လုပ်ခိုင်တဲ့နေရာမှာ သုံးပါတယ်။

```python
class mycallback(tf.keras.callbacks.Callback):
  def on_epoch_end(self, epoch, logs = {}):
    if(logs['loss'] < 0.3):
      print('\nLoss below 0.3, will stop training')
      self.model.stop_training = True

cb = mycallback()

model = get_model()
model.fit(x, y, epochs = 100, verbose = 1, callbacks = [cb])
```