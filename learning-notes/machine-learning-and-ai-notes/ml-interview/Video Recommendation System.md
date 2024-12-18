---
category: "[[Clippings]]"
author: "[[Michael C. J. kao]]"
title: "Machine Learning System Design Interview Extension— Video Recommendation System"
source: https://mkao006.medium.com/machine-learning-system-design-interview-extension-video-recommendation-system-9fc47d7467cd
clipped: 2024-12-18
published: 
topics: 
tags: [clippings]
---


In this post, I will continue to share additional personal considerations on the case presented in the Machine Learning System Design Interview book. If you have not read the [introduction](https://mkao006.medium.com/machine-learning-system-design-interview-a-personal-extension-intro-ad24b4989680), I recommend going through it first.

Design a video recommendation system that presents recommendations on a homepage like YouTube to increase engagement. Engagement is measured by the number of relevant videos the user has watched.

The proposed architecture contains the following components:

-   A candidate generation mechanism to reduce the number of videos to rank from billions to thousands.
-   A two-tower neural network that translates video and user features into embedding then predicts the probability (binary classification) of whether a user will interact with the video.
-   The videos are sorted by score, and the top k is returned.

![](https://miro.medium.com/v2/resize:fit:1400/1*_rzyQGxirTjnXB43iVqzsA.png)

This is a great example of how heuristic models, such as popularity or trending recommendations, not only provide the benefits listed in the introduction but are also an important part of the ML solution.

If I had to build the recommendation system from scratch, I would certainly build the individual heuristics recommendation based on popularity and trends. This would allow me to collect training data and then use the heuristic for candidate generation when I build the full ML solution as proposed in the solution.

We have already introduced the concept of **minimum functional test** and **invariance test for embeddings** in the [first post](https://mkao006.medium.com/machine-learning-system-design-interview-a-personal-extension-chapter-2-7ab9fbf85ca1), these can be applied similarly to video embedding, but care should be taken for the customer embedding. Unlike video embedding, customer embedding is dynamic, as customer preference and features such as age can change while the content of a video does not.

## Differential Test

In this section, we will introduce the concept of differential testing to test the two-tower neural network model that is used to predict a score whether a user will click a video (binary classification).

Differential tests are commonly used to check how different a newly trained model is from an old model. When a model is retrained frequently and continuously, you don’t want to check or examine the model manually.

After training a new model, we can compute the prediction on the unseen test data using the new and the incumbent models and compare the prediction between the two models.

The rationale behind this approach is that while changes are expected when retraining a new model, they should not be drastic. A video predicted to be highly likely to be clicked by user A should not suddenly have a low score and vice versa. Here are the high-level steps:

1.  Train a new model
2.  Generate prediction for the new and incumbent models using an unseen test set.
3.  Compute the correlation between the prediction: Cor(prediction\_new\_model, prediction\_old\_model)
4.  Fail the test and examine the model if the correlation is less than a threshold (e.g. 0.8); otherwise, we assume the model is safe to be deployed.

The same system extension in the visual search system [post](https://mkao006.medium.com/machine-learning-system-design-interview-a-personal-extension-chapter-2-7ab9fbf85ca1) can be used to carry out AB or interleaving extension for the video recommendation system.

## Watch out for Spillover Effects

When measuring success, it is important that we log all the relevant actions associated with each recommendation and make sure there are no leaks. If this is not done properly, we may experience what is known as the spillover effect.

Let’s assume our objective metric is the **percentage of video the user has watched at least half of the video** and only triggers the logging event when this happens. Now imagine that the treatment model (this model tends to recommend longer videos) recommends video A, which the user saves in the “watch later” but only clicks and watches the video when the control model recommends it later.

In this case, the success will be attributed to the control instead of treatment, which inflates the metric for control and results in bias in the experiment.

Here, we propose an alternative pattern that I use often to provide additional flexibility.

![](https://miro.medium.com/v2/resize:fit:1400/1*JUV8mO_783jLaXVJJsjnhQ.png)

We keep the relevant video candidate generation and the two-tower neural network to recommend the most relevant videos. However, we move the popularity and trending video heuristic recommendations as separate scoring mechanisms.

An ensemble scoring service then computes an ensemble score based on all individual scores into a single value for each video. The weights can be set manually or learnt from reinforcement learning.

Some advantages of this approach are:

-   More flexibility to perform local optimisation for certain segments (e.g. more popular videos for new users) by tweaking the weights.
-   Enables boosting of paid videos in the recommendation.