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
![[entropy-loss.png]]

## Kullback-Leibler Divergence (KL Divergence) Loss

- Measuring information lost using Kullback-Leibler Divergence
- KL Divergence is just a slight modification of our formula for entropy
![[KL-divergence-loss.png]]
- what we're looking at with the KL divergence is the [expectation](https://www.countbayesie.com/blog/2015/3/19/expectation-and-variance-from-high-school-to-grad-school) of the log difference between the probability of data in the original distribution with the approximating distribution
- in terms of 𝑙𝑜𝑔_2​​ we can interpret this as "how many bits of information we expect to lose"
 ![[KL-divergence-common-form.png]]
 - It may be tempting to think of KL Divergence as a distance metric, however we cannot use KL Divergence to measure the _distance_ between two distributions. The reason for this is that KL Divergence is _not **symmetric_**.
 - we can use KL Divergence as an objective function to find the optimal value for any approximating distribution we can come up with.