---
category: machine learning
topics: time-series-prediction
---
## Topics: Memory aware time series forecasting

Time series forecasting is a critical task in many different domains like finance and energy management. The recent advancements in deep learning based approaches has created many sophisticated methods like transformer-based models which uses attention based mechanisms to capture long-range dependencies and has achieved state-of-the-art performance on long-term time series forecasting task. In this thesis, we have used an alternative approach of improving any simple linear or convolution-based models by extracting and leveraging recurring patterns within the time series data. We identify distinct prototype patterns that recur over time and use their corresponding forecast to guide the model to get closer to the actual ground-truth. To validate the hypothesis, we have used several benchmark datasets in their univariate setting, as well as creating a synthetic dataset to exhibit clear recurring patterns. The results have shown that incorporating the expected forecast from the recurring patterns significantly enhances the forecasting accuracy of linear and convolutional model in many experimental settings and also reaching closer to the state-of-the-art transformer-based results. This finding suggests that by just adding minimal preprocessing, simpler models can also achieve performance on par with the more complex models. This work has open further exploration into how we can use these prototypes to optimize model performance while maintaining simplicity and computational efficiency.

**Methods Use**

1. Linear Model - DLinear Model - decomposes into trends and seasonal components
2. CNN - Wavenet - dilated causal convolutions to access broad range of historical data - see longer lags
3. CNN - Temporal (TCN), ModernTCN - based on transformer's ability
