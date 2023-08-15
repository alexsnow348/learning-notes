Data Preprocessing
---

### Creating Tensor Dataset form Existing Tensors - အရင် ရှိပြီးသာ tensor မှ dataset တည်ဆောက်မယ်။

- list ကနေ dataset လုပ်မယ်
```python
import tensorflow as tf
a = [1.2, 3.4, 7.5, 4.1, 5.0, 1.0]
ds = tf.data.Dataset.from_tensor_slices(a)
# <_TensorSliceDataset element_spec=TensorSpec(shape=(), dtype=tf.float32, name=None)>

```

- 