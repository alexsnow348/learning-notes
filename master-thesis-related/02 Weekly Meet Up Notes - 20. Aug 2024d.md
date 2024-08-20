---
category: machine learning
topics: time-series-prediction
---
### Thesis Defense : Classification of Irregularly Sampled Time Series with Missing Values

**Abstract:**
This thesis addresses the challenge of classifying irregularly sampled multivariate time series with missing values, a crucial task in fields such as weather, medicine, and finance. Current state-of-the-art models typically assume regularly sampled, fully observed data, which is often not the case in real-world scenarios where data can be irregularly sampled containing missing values (sparse time series). Standard imputation methods can lead to information loss and alter data distribution, emphasizing the need for specialized models. In this thesis, we propose a novel convolutional neural network-based model that handles input in a triple set-based format. The model learns channel-wise embeddings using convolutional blocks and applies a multi-head attention mechanism, using a set of reference time points as queries to obtain fixed-size representations. These representations are then passed to a classifier to obtain the final result. The proposed model was tested on company datasets, such as Contract Creation and Renewal, as well as on public datasets like PhysioNet and MIMIC III. Our model outperforms existing state-of-the-art models, including SEFT, MTAND, and DCSF, on public datasets and excels on company data by capturing inter-feature dependencies. It demonstrates superior performance in terms of the Area Under the Precision-Recall Curve (AUPRC) metric, particularly for the company datasets, thereby meeting key performance requirements.

#### Notes: 
- SimTSC - DTW (Dynamic Time Warping) - similarity measure, Dilated ResNet, GCN (Graph CNN)
- Attention based Transform is very useful for time series as well. I need to start learning more about Transform and ViT. 

