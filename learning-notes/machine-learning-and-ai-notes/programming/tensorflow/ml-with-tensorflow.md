Linear Regression with TensorFlow
---

###  gradient descent တွက်နည်း

- simple gradient equation ကို တွက်နည်း
$$
\begin{equation}
y = x^3 ; \frac{dy}{dx} = 3x^2
\end{equation}
$$

```python
import tensorflow as tf
x = tf.Variable(3.0)
with tf.GradientTape() as tape:
	y = x ** 3
dx_dy = tape.gradient(y, x)
print(f"gradient {x.numpy()} is {dx_dy.numpy()}")
# gradient 3.0 is 27.0
```


- higher order gradients equation ကို တွက်နည်း

$$
\begin{equation}

y = x^3 ; \frac{dy}{dx} = 3x^2 ; \frac{d^2 y}{dx^2} = 6x

\end{equation}
$$
```python
x = tf.Variable(3.0)

with tf.GradientTape() as t1:
	with tf.GradientTape() as t2:
		y = x ** 3
	dy_dx = t2.gradient(y, x)

d2y_dx2 = t1.gradient(dy_dx, x)
print(f"gradient {x.numpy()} is {d2y_dx2.numpy()}")
# gradient 3.0 is 18.0
```

- Variable မဟုတ်တာတွေကို gradient တွက်မယ်ဆို tape.watch() သုံးဖို့လိုတယ်။
```python
  
import tensorflow as tf
x = tf.constant(2.0)
# Create a GradientTape context
with tf.GradientTape() as tape:
    # Watch the constant tensor x
    tape.watch(x)
    # Define a function involving x
    y = x**2
# Compute the gradient of y with respect to x
dy_dx = tape.gradient(y, x)
print(dy_dx)  # This will print 4.0, which is the derivative of y = x^2 with respect to x.
```

- persistent tape - chain rule တွက်တဲ့နေရာမှာ သုံးလို့ပါတယ်။
$$
\begin{equation}

y = x^3 ; z = 2y ; \frac{dz}{dx} = \frac{dz}{dy} . \frac{dy}{dx}

\end{equation}
$$
```python
x = tf.Variable(3.0)

with tf.GradientTape(persistent=True) as tape:
	y = x ** 3
	z = 2 * y

dy_dx = tape.gradient(y, x)
dz_dx = tape.gradient(z, x)
dz_dy = tape.gradient(z, y)

del tape # delete အရမ်းအရေးကြီးပါတယ်။

print(f"dy_dx: {dy_dx.numpy()}") # dy_dx: 27.0
print(f"dz_dx: {dz_dx.numpy()}") # dz_dx: 54.0
print(f"dz_dy: {dz_dy.numpy()}") # dz_dy: 2.0
```

- linear regression တွက်မယ်။
$$
\begin{equation}

y = wx + b

\end{equation}
$$
```python
# data generatiimport matplotlib.pyplot as plt
import matplotlib.pyplot as plt
np.random.seed(42)
true_w, true_b = 7.0, 4.0

  

def create_data(batch_size=64):
	x = np.random.randn(batch_size, 1)
	y = np.random.randn(batch_size, 1) + true_w * x + true_b # added noise for challenging, random noise
	return x, y

x, y = create_data()
plt.plot(x,y, ".") # dot graph ကို ဆွဲပေးတယ်။

# Linear Regression Step by Step
iterations = 100 # gradient step
learning_rate = 0.03
w = tf.Variable(10.0)
b = tf.Variable(1.0)

w_history = []
b_history = []

for iter in range(iterations):
    x_batch, y_batch = create_data()
    x_batch = tf.convert_to_tensor(x_batch, dtype=tf.float32)
    y_batch = tf.convert_to_tensor(y_batch, dtype=tf.float32)
    
    with tf.GradientTape(persistent=True) as tape:
        y = w * x_batch + b
        loss = tf.reduce_mean(tf.square(y-y_batch))
        
    dw = tape.gradient(loss, w)
    db = tape.gradient(loss, b)
    del tape
    
    w.assign_sub(learning_rate*dw) # (w:= w - db * lr)
    b.assign_sub(learning_rate*db) # (b:= b - db * lr)
    
    w_history.append(w.numpy())
    b_history.append(b.numpy()) 
    if iter % 10 == 0:
        print('Iter {}, W={}, b={}'.format(iter, w.numpy(), b.numpy()))
```
