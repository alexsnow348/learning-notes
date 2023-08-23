**Apple M2 Silicon chip** အတွက် လုပ်သင့်တဲ့ installation step တွေ ဖြစ်ပါတယ်။

၁။  Miniforge ဆိုတဲ့ conda ကို install လုပ်ဖို့ လိုပါတယ်။ တကယ်လို့ brew မရှိသေးဘူးဆို အောက်က [brew install link](https://brew.sh/index_de) မှ တဆင့် install လုပ်ထားဖို့ လိုပါတယ်။

```bash
brew install miniforge
```

၂။ conda env အသစ်တစ်ခုကို စလုပ်ပြီး tensorflow နှင့်ဆိုင်တဲ့ library တွေကို install လုပ်ရပါမယ်။

```bash
conda create -n tf
conda activate tf
conda install -c apple tensorflow-deps # Apple's TensorFlow dependencies အတွက်
pip install tensorflow-macos
pip install tensorflow-metal  # Apple's Metal GPU APIs for TensorFlow အတွက်
```

၃။ install လုပ်ထားတွေကို လိုချင်တဲ့ အတိုင် ဖြစ်မဖြစ်ကို verify လုပ်ရပါမယ်။

```python
import tensorflow as tf
import tensorflow_datasets as tfds
print("TensorFlow version:", tf.__version__)
print("Num GPUs Available: ", len(tf.config.experimental.list_physical_devices('GPU')))
print("Num CPUs Available: ", len(tf.config.experimental.list_physical_devices('CPU')))
```
