---
category: machine learning
topics: time-series-prediction
---
### Thesis Defense: Memory aware time series forecasting
----

Time series forecasting is a critical task in many different domains like finance and energy management. The recent advancements in deep learning based approaches has created many sophisticated methods like transformer-based models which uses attention based mechanisms ***to capture long-range dependencies and has achieved state-of-the-art performance on long-term time series forecasting task.*** In this thesis, we have used an alternative approach of improving any simple linear or convolution-based models b***y extracting and leveraging recurring patterns within the time series data***. We identify distinct prototype patterns that recur over time and use their corresponding forecast to guide the model to get closer to the actual ground-truth. To validate the hypothesis, we have used several benchmark datasets in their univariate setting, as well as creating a synthetic dataset to exhibit clear recurring patterns. The results have shown that incorporating the expected forecast from the recurring patterns significantly enhances the forecasting accuracy of linear and convolutional model in many experimental settings and also reaching closer to the state-of-the-art transformer-based results. This finding suggests that ***by just adding minimal preprocessing, simpler models can also achieve performance on par with the more complex models***. This work has open further exploration into how we can use these prototypes to optimize model performance while maintaining simplicity and computational efficiency.

**Current Literature**

1. Linear Model - DLinear Model - decomposes into trends and seasonal components
2. CNN - Wavenet - dilated causal convolutions to access broad range of historical data - see longer lags
3. CNN - Temporal (TCN), ModernTCN - based on transformer's ability
4. Transformer - PatchTST

**Research Problem**

- impact of memory 
- different types of arch - with impact of used of memory 

**Methodology**

- Prototype Extraction from time-series  dataset - moving time window - to create Memory Table with KMeans and KNN with Euclidean distance as similarity score
- Forecasting - Prototype Search - Linear model, CNN based model, Transformer-based model
- Reversible Instance Normalization (RevIN) - to solve distribution shift problem 
- Losses - MSE, MAE
- Dataset (univariate dataset) - ETTh1,h2,m1,m2 , Electricity 

**Results**

- CNN leads to better generalization of the dataset
- Lookback Window analysis (WaveNet) - lowest MSE with a shorter context length 

**Questions and Discussion**

- Q: why simple model perform better than transformer, CNN methods. 
	- adding memory to already complex models might not be beneficial   
- Discriminative  analysis with ensemble might produce better performance


### First Idea Talk:  Classification of Automotive Complaint Descriptions from NHTSA Using NLP for Component Identification and Internal Data Matching
---

The aim of this bachelor thesis is to develop an algorithm capable of batch data classification, specifically identifying relevant information related to failures about Bosch  
components in cars. The dataset, provided by NHTSA (National Highway Traffic Safety  
Administration, a part of the U.S. Department of Transportation), contains over 40,000  
entries and is already enriched with internal Bosch data which contains e.g. information about Bosch components. Following the classification, relevant data points will be  
reviewed by internal Bosch experts to initiate any necessary follow-up actions.

**Problem Setting**

- Ranking - based keyword search, relationship between complaint
	- Cons: not found for exact match, relationship methods produce false positive

**State of the Art**

- BERT - fine-tune  for classification
- Softmax classifier 

**Research Idea**

- Input: complaint description  - internal Bosch company complaint dataset 
- Output: probability of output class 



### **First Idea Talk**: Enhancing Patching for Time Series Forecasting
---

Multivariate time series forecasting is a crucial problem for tasks such as financial predictions or forecasting retail demands, traffic, or weather. Recently, the PatchTST model combines two trends in this research area. The first is the use of transformers, which have been shown to be an effective architecture for learning patterns in different domains. The second is the use of patching, which reduces the required memory and computational operations for a fixed look-back window and provides more meaningful local information. PatchTSTs patching mechanism simply groups overlapping subsequences of time points in the look-back window. My hypothesis is that this approach does not exploit the full potential of patching. An enhanced patching technique is used in the HDMixer model that uses a Length-Extendable Patcher to flexibly divide the look-back window into patches. This retains peak information and enables a more consistent use of local semantics. Another approach is the use of multiple convolution layers with a long look-back receptive field in combination with a pooling layer. Besides having the benefits of the Length-Extendable Patcher, it could also generate more informative patches. This master thesis will empirically verify the effectiveness of these approaches for more enhanced patching on the ETTh, ETTm, Weather, and Electricity benchmark datasets in comparison to state-of-the-art models.

