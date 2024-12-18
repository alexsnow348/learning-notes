---
category: "[[Clippings]]"
author: "[[Michael C. J. kao]]"
title: "Machine Learning System Design Interview — A Personal Extension (Chapter 2)"
source: https://mkao006.medium.com/machine-learning-system-design-interview-a-personal-extension-chapter-2-7ab9fbf85ca1
clipped: 2024-12-18
published: 
topics: 
tags: [clippings]
---


This marks the beginning of a multi-part series, delving into personal extensions for the solution outlined in the Machine Learning System Design Interview book. For a more comprehensive background, refer to the [introduction](https://medium.com/@mkao006/machine-learning-system-design-interview-a-personal-extension-intro-ad24b4989680).

Design a visual search system that takes an image as an input query and returns a ranked list of images based on their similarity to the input image.

The following depiction is a simplified version of the proposed solution:

![](https://miro.medium.com/v2/resize:fit:1400/1*3ohPdk1DsF8k7ln6-87rVw.png)

Image source: [https://excalidraw.com/#json=F91zxX9YeslGoy\_tfi\_uh,T0ryzlscgkVo0nEQVP3oEg](https://excalidraw.com/#json=F91zxX9YeslGoy_tfi_uh,T0ryzlscgkVo0nEQVP3oEg)

An embedding generation service (EGS) translates the input image into an embedding, while the nearest neighbour service (NNS) identifies the image with the highest similarity based on the shortest distance in the embedding space.

The embedding model is used in serving to translate the input image, and offline to generate the embedding of all images to create the indexes.

Testing and evaluating embeddings fall into two categories: intrinsic (assessing internal representation quality) and extrinsic (evaluating performance for downstream tasks). Our focus will primarily be on intrinsic testing, as extrinsic evaluation is covered in the book.

## Minimum Functional test

To ensure the trained embedding model behaves as expected, we conduct a minimum functional test. This test hinges on the expectation that the distance between two identical objects (e.g., cat vs. cat) should be smaller than the distance between two different objects (e.g., cat vs. dog).

In this case, the formulation of the minimum functional test lies in the expectation that the distance between two equal objects (e.g. cat vs cat) should be smaller than the distance between two different objects (i.e. cat vs dog), at least in theory.

![](https://miro.medium.com/v2/resize:fit:244/1*89NhKuYvWM96qvQlFNZ3cg.gif)

To construct the test, a test set will contain an anchor image containing concept k (e.g. cat), then a comparison set which contains at 1 image of the same concept and m alternative images. For example

-   anchor set: \[cat\]
-   comparison set: \[cat, dog, aeroplane, car\]

We first compute the embedding for all the images; then, we calculate the distance (e.g. cosine similarity) between the pairs.

1.  d(cat, cat)
2.  d(cat, dog)
3.  d(cat, aeroplane)
4.  d(cat, car)

The **expectation is that the distance for (1) should be the smallest out of the set.** We can create many cases to ensure the embedding aligns with our expectations.

## Invariance Test

Another form of testing, the invariance test, assesses the robustness of the embedding. The intuition behind this test is that the embedding shouldn’t change drastically with invariant operations (e.g., rotation or scaling of the image).

We can re-use the above test case, but we will perform an additional operation:

-   anchor set: \[cat\]
-   comparison set: \[**rotate**(cat), dog, aeroplane, car\]

The rest of the test remain the same.

Given that ML models are imperfect, we do not need a 100% pass rate on our tests. However, we should have a high threshold, such as 95%, and the performance should remain stable when compared to previous embedding models.

To facilitate experimentation, extensions to the current system are introduced. Experimentation for search and recommendation systems can occur through traditional AB tests or interleaving experiments.

1.  Traditional AB tests.
2.  Interleaving Experiment

## AB test

The following illustration shows how the system can be extended to support AB experimentation, assuming we have an experiment engine similar to the one designed [here](https://mkao006.medium.com/machine-learning-system-design-interview-a-personal-extension-intro-ad24b4989680).

![](https://miro.medium.com/v2/resize:fit:1400/1*6O-TCLAyKcBsxC9VK0EIXw.png)

.

When a user makes a query, the experiment engine is called to retrieve the experiment configuration and assign a treatment to the request; the assignment is also logged simultaneously.

When the embedding generation and nearest neighbour service receive the request, they will call the corresponding embedding model and the embedded image table associated with the treatment to perform the search.

The management of multiple models and experiments can be supported by tools such as [Mlflow](https://mlflow.org/).

While shown as two separate icons, the image index can be configured as two different [indexes](https://docs.pinecone.io/docs/indexes) in the same vector database. **However, for each model you experiment with, a full run of the embedding model across all your images is required to create a new index; this can be quite costly.**

## Interleaving Experiment

Another popular experimentation paradigm for information retrieval systems is interleaving experiments, which have been adopted by companies such as [Netflix](https://netflixtechblog.com/interleaving-in-online-experiments-at-netflix-a04ee392ec55) and [AirBnb](https://medium.com/airbnb-engineering/beyond-a-b-test-speeding-up-airbnb-search-ranking-experimentation-through-interleaving-7087afa09c8e) for their recommendation and search systems.

In contrast to an AB experiment where one treatment is called for each individual query, both models are called simultaneously. The results are then merged to create the final ranking.

This technique has been shown to increase the experiment's sensitivity and thus require fewer samples to conclude an experiment and faster iteration to improve the model.

![](https://miro.medium.com/v2/resize:fit:1400/1*QWboFfeg2Yk84JK7Mb4Osw.png)