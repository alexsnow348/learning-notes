---
category: machine learning
topics: time-series-prediction
---


### First Idea TalkTitle: Channel Clustering for Multivariate Time Series Forecasting
----
Abstract:
Multivariate time series forecasting is pivotal for applications such as energy 
demand forecasting, traffic flow prediction, and weather modeling. 
Recently, the TSMixer model has emerged as an effective solution, 
leveraging MLP-Mixer architectures to capture dependencies across both 
time steps and features.However, this thesis looks to hypothesize that 
the TSMixer’s channel mixing mechanism can be further optimized to 
exploit co-variate interactions across channels and timestamps. To this 
end, this thesis proposes incorporating a channel clustering module 
inspired by the "**From Similarity to Superiority: Channel Clustering for** 
**Time Series Forecasting**" framework. My implementation aims to cluster 
channels based on similarity while applying phase shifts to capture 
co-variate information across different channels and timestamps, 
enhancing prediction accuracy.This novel approach will be 
empirically evaluated on the **ETTh, ETTm, and ODE dataset**s to benchmark 
its effectiveness against the state-of-the-art models. The ODE dataset 
being highly channel-dependent is going to be integral for 
experimentation with this channel clustering module. This thesis 
hypothesizes that this approach will improve the model's ability to 
capture temporal and cross-channel dynamics, leading to more accurate 
multivariate time series forecasts.