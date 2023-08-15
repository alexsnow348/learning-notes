Data Preprocessing
---

### Creating Tensor Dataset form Existing Tensors - အရင် ရှိပြီးသာ tensor မှ dataset တည်ဆောက်မယ်။

- list ကနေ dataset ဆောက်မယ်။
```python
import tensorflow as tf
a = [1.2, 3.4, 7.5, 4.1, 5.0, 1.0]
ds = tf.data.Dataset.from_tensor_slices(a)
# <_TensorSliceDataset element_spec=TensorSpec(shape=(), dtype=tf.float32, name=None)>

ds_batch_3 = ds.batch(3)
for index, element in enumerate(ds_batch_3):
	print(index, element)
# 0 tf.Tensor([1.2 3.4 7.5], shape=(3,), dtype=float32) 
# 1 tf.Tensor([4.1 5. 1. ], shape=(3,), dtype=float32)
```

-  tensors တွေကို ပေါင်းပြီး join dataset တည်ဆောက်မယ်။
```python
tf.random.set_seed(1)
t_x = tf.random.uniform([4,1], dtype=tf.float32)
t_y = tf.range(4)
print(t_x)
print(t_y)
# tf.Tensor( [[0.16513085] [0.9014813 ] [0.6309742 ] [0.4345461 ]], shape=(4, 1), dtype=float32)
# tf.Tensor([0 1 2 3], shape=(4,), dtype=int32)

# တည်ဆောက်ထားတဲ့ tensor ၂ ခုကို ပေါင်းမယ်။
ds_x = tf.data.Dataset.from_tensor_slices(t_x)
ds_y = tf.data.Dataset.from_tensor_slices(t_y)
ds_joint = tf.data.Dataset.zip((ds_x, ds_y))
ds_joint_alternative = tf.data.Dataset.from_tensor_slices((t_x, t_y))
for data in ds_joint:
	x, y = data
print(x.numpy(), y.numpy())
# [0.16513085] 0 
# [0.9014813] 1 
# [0.6309742] 2
# [0.4345461] 3
```

- Feature scaling
```python
ds_feature_scaling = ds_joint.map(lambda x,y: (x*2-1.0,y))
for data in ds_feature_scaling:
	x, y = data
print(x.numpy(), y.numpy())
# [-0.6697383] 0
# [0.80296254] 1 
# [0.26194835] 2 
# [-0.13090777] 3
```

- Shuffle - data တွေကို random ရွှေ့မယ်။
```python
ds_shuffle = ds_joint.shuffle(buffer_size=len(t_x))
for data in ds_shuffle:
	x, y = data
print(x.numpy(), y.numpy())
# [0.9014813] 1 
# [0.4345461] 3 
[0.16513085] 0 
[0.6309742] 2
```