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
print(f"gradient {x.numpy()} is {dx_dy.numpy()}") # gradient 3.0 is 27.0
```


- higher order gradients equation ကို တွက်နည်း

$$
\begin{equation}

y = x^3 ; \frac{dy}{dx} = 3x^2 ; \frac{d^2 y}{dx^2} = 6x

\end{equation}
$$
```python

```