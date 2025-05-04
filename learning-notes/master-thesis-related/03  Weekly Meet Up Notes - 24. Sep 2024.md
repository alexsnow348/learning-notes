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



### Defense Title: Time Series Classification Using GAN-Augmented Data and Attention-Based Convolutions

Abstract:This thesis explores the potential of contrastive learning for 
enhancing the analysis of time series data, a domain where labels are 
often scarce or unavailable. By exploiting the distinctions between 
similar and dissimilar instances, our work aims to extract significant 
features from time series data without the need for labelled examples. 
We build upon the **TS2Vec** methodology, extending its potential with an 
advanced encoder architecture that integrates attention-based causal 
dilated convolutions, thereby enriching the contextual details captured 
within the data representations. Considering the challenges 
associated with labelled data scarcity, we also examine the application 
of generative adversarial networks (GANs) to create synthetic data for 
diversity. Subsequently, our approach employs adaptive pooling to obtain
 representations of arbitrary sub-sequences within the time series. We 
validate our approach through empirical analysis, using benchmark 
datasets from the UCR and UEA time series classification archives. Our 
accuracy results demonstrate notable improvements over TS2Vec, and 
Synth-TS2Vec outperforms current state-of-the-art methods in 
unsupervised time series representation.


GAN Based
 - TimeGAN
 - TCGAN
 - TSGAN
 
Autoencoder Based Learning

Constrative methods
- T-loss (Subseries consistency)
- Transformation consistency TS-TCC
- Temporal consistency (TNC)
- Contextual consistency
