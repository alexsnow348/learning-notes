---
category: "[[Clippings]]"
author: "[[Michael C. J. kao]]"
title: "Machine Learning System Design Interview Extension — People You May Know"
source: https://mkao006.medium.com/machine-learning-system-design-interview-extension-people-you-may-know-787e0c9fdf3c
clipped: 2024-12-18
published: 
topics: 
tags: [clippings]
---

Welcome to another post on the extension of the Machine Learning System Design Interview Extension where I share some personal extensions on the book. If you have not read the [intro](https://medium.com/@mkao006/machine-learning-system-design-interview-a-personal-extension-intro-ad24b4989680), I would suggest you head over for more context before continuing with the remaining post.

The purpose of the system is to provide recommendations to users with whom they are likely to connect, similar to LinkedIn. The system will take a user as input and return the list of potential connections ranked as output.

The solution is to train a Graph Neural Network (GNN) that takes a pair of nodes as input and predicts whether a connection (the edge) will form as a binary classification; the scores returned for each pair are between 0 and 1 which can then be sorted. For readers who are unfamiliar with GNN, this is a fantastic [introduction](https://distill.pub/2021/gnn-intro/#graph-to-tensor)

The system contained an **online serving system** and an **offline batch pipeline** to precompute recommendations.

Precomputed prediction is a common pattern to reduce computation resources and lower latency when a prediction does not become stale immediately; you can think of it like a cache.

![](https://miro.medium.com/v2/resize:fit:1400/1*GuQ13L7ZwSyGsRgt6gJA4g.png)

## Online:

1.  The People You May Know (PYMK) service will hit the database to see if a pre-computed recommendation exists. If yes, return the pre-computed recommendation, otherwise generate the recommendation on the fly.
2.  When the pre-computed prediction does not exist, the PYMK service will send a request to the scoring service with the user ID and other required contextual information for recommendation.
3.  The scoring service first pings the Friends of Friends (FoF) service to find the potential connections for scoring.
4.  The scoring service then sends the FoF connection pairs to the graph neural network (GNN) for scoring.
5.  Return the recommended connection to the user.
6.  Save the recommended connection to the pre-computed database for later use.

## Offline:

There was little detail on the offline pipeline, so I added my high-level design.

The individual boxes such as “compute feature” are tasks defined in an orchestrator such as [Airflow](https://airflow.apache.org/) or [Flyte](https://flyte.org/).

1.  **Compute Feature and Target Label**: The task reads data from a database and computes all the features required to train the GNN. Two types of features are computed: 1) individual user features such as age, country, and number of connections and 2) user interaction features, such as the number of posts from user A seen by user B or whether A and B went to the same school. We can also compute the label here; the target is a binary outcome whether the pair is connected. **Beware of data leakage here; the feature computed at time t should only be used to predict connection in time t + 1.**
2.  **Model Training**: Load the feature and label from the previous task, train the Graph Neural Network (GNN), and then save the model to a model registry such as Mlflow for serving.
3.  **Prediction**: Get the active user and their potential connection in the last, say, 30 days (so we don’t waste computation resources on inactive users) and the model trained in the previous task, then compute the score of the connections. Then save this to the pre-compute score database for fast serving.

Similar to earlier posts, heuristic models can be extremely helpful to get the system started to collect training data and provide satisfactory performance before upgrading to an ML system. Here are some heuristic recommendations:

-   Friends of friends (FoF)
-   People you work with or from the same company.
-   People who went to the same school.

In addition to providing a starting point to the system, these heuristics can be used as input features or candidate search space in the later ML system and solve cold start problems when the user has no connection and no features can be computed.

Without the heuristic candidate restriction, the ML system would have to compute a maximum of NxN pairs of relationship prediction where N can be billions in the case of LinkedIn. On the other hand, if we only compute the prediction between friends of friends or people who are 2–3 connections (a.k.a degrees) away, we can significantly reduce the computation to NxM, where M is in the order of thousands.

To test the model, we can utilise domain knowledge and insight from exploratory analysis to devise **directional expectation tests**.

In social networks, the more friends shared between the two unconnected individuals, the higher the probability of forming a connection, given all else is equal. Similarly, we can assert that a pair of connections is more likely to connect if they have worked together (assuming most relationships are positive).

Here is a high-level walkthrough of the test for the first scenario:

1.  Train the GNN model.
2.  Make a prediction using the model on an unseen test set and denote this as the **controlled prediction**.
3.  Add random noises to the *number of connections* feature in the test set and then make another prediction and call this the **perturbated prediction**.
4.  Compute the difference in the prediction score between the controlled and perturbated scores.
5.  Fit a linear regression with the perturbation as *x* and the score difference as *y*, then test whether the beta coefficient is positive.

If the coefficient is positive, this means that the higher the number of connection, the higher the predicted probability on average and is align with our expectation so we will pass the test, otherwise the test has failed.

While stats sig is not required, I suggest only devising a test where the directional effect is strong, and the slope should be significant almost always to avoid false positives.

## Interference

One common issue with conducting experimentation such as AB testing in a social network setting is the existence of interference.

The Stable Unit Treatment Value Assumption (SUTVA) is the foundation of AB testing and in a single sentence:

> **The effect of a treatment on a unit should not be affected by the treatment assignment of others**.

It is easy to see how this is violated under the network setting; let’s say we have two recommendation models, control and treatment, and assume that the treatment is better and increases the likelihood of connections.

To illustrate the interference effect, let’s assume we have two connected users, A and B, but A is assigned to control while B is assigned to the treatment.

1.  The treatment increases the connection probability of B.
2.  Due to more new connections, B’s interactions, such as *liking* and *reposting*, increase.
3.  Due to an increase in B’s interaction, A also sees more posts from people they usually don’t see.
4.  This leads to an increase in the connection rate of A as they are now exposed to more posts and people.

The net effect is that the difference between the control and treatment is smaller as the effect from treatment has spilled over to the control and can lead to insignificant tests.

Another example of interference is when two users of the same Jira board have different functionalities; this can lead to confusion, and the change in behaviour in one user will affect the others.

For more details on interference, I would highly recommend picking up the [Trustworthy Online Controlled Experiments: A Practical Guide to A/B Testing](https://www.amazon.com/Trustworthy-Online-Controlled-Experiments-Practical/dp/1108724264) book (chapter 22).

## Addressing Interference

There are many different ways to break the interference effect; I have listed a few common approaches below:

-   **Time-based randomisation**: All users receive control in period t and then receive treatment in period t + 1. This, however, is problematic for this use case since we will be facing temporal spillover due to a delay in forming a connection.
-   **Geographical randomisation**: Another common approach is to assign treatment to different geographic areas so each geographic area only receives a single treatment; we assume that the assignment of the geographical units is random and unbiased.
-   **Graph Cluster randomisation**: This approach partitions the graph into isolated clusters to minimise the effect of interference. However, research has shown that it’s difficult to have pure isolated clusters, and the number of clusters is small, leading to a statistical power loss.
-   **Ego-cluster randomisation**: This approach is similar to the above but creates a cluster known as ego-cluster which contains a single ego center and alter that it is directly connected to. This approach increases the statistical power by allowing more clusters to be formed, but the trade-off is a higher interference effect.

![](https://miro.medium.com/v2/resize:fit:1400/1*fi3JXeJnl5QFmb74Y39e-A.png)

Source: [Using Ego-Clusters to Measure Network Effects at LinkedIn](https://arxiv.org/pdf/1903.08755.pdf)

## Extension to the System for Ego-Cluster Randomisation

The following depiction is an illustration of extending the system to support clusters.

The changes are shown in green:

1.  We now save predictions from the incumbent and challenger models to the precomputed database.
2.  Two sets of predictions using the new and old models are also generated if the prediction is not found in 1.
3.  We create an offline pipeline to compute the ego-cluster and save the cluster assignment. The ego cluster is created for each experiment.
4.  We add an experiment engine that returns the assignment when called; the PYMK then returns the correct experiment treatment based on the experiment assignment.

![](https://miro.medium.com/v2/resize:fit:1400/1*O8kSH4WAy4ujJDfNM3tRVw.png)