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
# tf.Tensor( [[0.16513085] [0.9014813 ] [0.6309742 ] [0.4345461 ]], shape=(4, 1), dtype=float32)
print(t_y)
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
# [0.16513085] 0 
# [0.6309742] 2
```

-  data တွေကို Batch (နည်းနည်းစီ တစ်စု) ခွဲတာတွေ လုပ်မယ်။
```python
ds_batch = ds_joint.batch(batch_size=3, drop_remainder=False)
batch_x, batch_y = next(iter(ds_batch))
print(batch_x.numpy())
# [[0.16513085] [0.9014813 ] [0.6309742 ]]
print(batch_x.numpy())
# [0 1 2]
```

- data တွေကို ထပ်ခါထပ်ခါ   Repeat တိုးမယ်။ 
```python
# batch -> repeat
ds_repeat = ds_joint.batch(batch_size=3,drop_remainder=False).repeat(count=2)
for i, (batch_x,batch_y) in enumerate(ds_repeat):
	print(i, batch_x.shape, batch_y.shape)
# 0 (3, 1) (3,)
# 1 (1, 1) (1,) 
# 2 (3, 1) (3,) 
# 3 (1, 1) (1,)

# repeat -> batch
ds_repeat = ds_joint.repeat(count=2).batch(batch_size=3, drop_remainder=False)
for i, (batch_x,batch_y) in enumerate(ds_repeat):
	print(i, batch_x.shape, batch_y.shape)
# 0 (3, 1) (3,)
# 1 (3, 1) (3,) 
# 2 (2, 1) (2,)
```

###  Creating a dataset from files on your local storage disk -  local storage က data တွေကို ဖတ်ပြီး tensor အဖြင့်ပြောင်းမယ်။

- file list ကို folder တွေက ထုတ်ယူမယ်။

```python
import pathlib
img_dir_path = pathlib.Path('cat_dog_images')
file_list = sorted([str(file) for file in img_dir_path.glob('**/*.jpg')])
print(file_list)
# ['cat_dog_images/Cat1.jpg', 'cat_dog_images/Cat2.jpg', 'cat_dog_images/Cat3.jpg', 'cat_dog_images/Dog1.jpg', 'cat_dog_images/Dog2.jpg', 'cat_dog_images/Dog3.jpg']
```