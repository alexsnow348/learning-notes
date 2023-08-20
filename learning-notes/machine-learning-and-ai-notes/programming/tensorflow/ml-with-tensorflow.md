Machine Learning with TensorFlow
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

- persistent tape 
$$
\begin{equation}

y = x^3 ; z = 2y ; \frac{dz}{dx} = \frac{dz}{dy} . \frac{dy}{dx}

\end{equation}
$$
