# Loss/cost Functions များ
___
## Mean Absolute Error (MAE) Loss

- Error Metrics တွေကိုရှာတဲ့နည်းတစ်နည်းဖြစ်တယ်။
- prediction လုပ်တာတွေရဲ့ error magnitude တွေကို average ယူတဲ့နည်းဖြစ်တယ်။
- absolute difference between data and model's prediction - တကယ့်အဖြေးမှန်နဲ့ model က ထုတ်ပေးတဲ့ တန်းဖိုးတွေရဲ့ ခြားနားချက်ကို တွက်ပေးပါတယ်။
- MAE value သေးလေ best line fit နဲ့နီးလေဖြစ်တယ်။
- regression problems တွေမှာ အသုံးများပါတယ်။

## Cross Entropy Loss

Entropy is a measure of uncertainty or randomness. In the context of information theory, it quantifies the amount of uncertainty involved in predicting the outcome of a random variable. In machine learning, we often use it to measure the impurity or disorder in our data.

Cross-entropy extends this concept to compare two probability distributions. It measures the average number of bits needed to identify an event from a set of possibilities, if a different probability distribution is assumed. In machine learning, we use it to compare the predicted distribution of our model with the actual distribution (the true labels).

## Kullback-Leibler Divergence (KL Divergence) Loss

- 