Machine Learning with TensorFlow
---

- gradient descent
$$
\begin{equation}
y = x^3 ; \frac{dy}{dx} = 3x^2 ; \frac{d^2 y}{dx^2} = 6x
\end{equation}
$$

```python
import tensorflow as tf
x = tf.Variable(3.0)
with tf.GradientTape as tape:
	y = x ** 3
	
```