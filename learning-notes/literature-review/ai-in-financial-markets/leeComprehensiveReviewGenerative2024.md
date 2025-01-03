---
title: A Comprehensive Review of Generative AI in Finance
category: machine learning
year: 2024
tags:
  - finance
  - ml-ai
---
[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=460&annotation=SBSML6HL) „variational autoencoders (VAEs), generative adversarial networks (GANs), large language models (LLMs), and diffusion models.“ ([Lee et al., 2024, p. 460](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=460&annotation=GBUWJQWM) „Before the advent of GAI models, traditional methods for financial text mining were primarily used to analyze financial reports and forecast stock prices. However, these methods often relied on the bag-of-words approach to generate word embeddings, which failed to capture the contextual information within sentences.“ ([Lee et al., 2024, p. 460](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=461&annotation=R6DHFGXW) „VAEs applied probabilistic frameworks to generate new data points based on latent representations learned during training.“ ([Lee et al., 2024, p. 461](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=461&annotation=W3MLQPMT) „GAN model, which represented a paradigm shift in generative modeling. It is an adversarial process involving two neural networks: a generative model to capture the data distribution and a discriminative model to distinguish between real data and generated samples. This adversarial framework enabled GANs to produce remarkably realistic outputs across various domains, such as images and texts.“ ([Lee et al., 2024, p. 461](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=461&annotation=R7NEPMKH) „self-attention mechanisms to capture long-range dependencies in sequential data,“ ([Lee et al., 2024, p. 461](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=461&annotation=Z4BQHZUI) „Diffusion models have emerged as a novel approach in GAI, focusing on modeling temporal dependencies and irregular patterns in sequential data“ ([Lee et al., 2024, p. 461](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=461&annotation=5ZHS7RBQ) „Beyond conventional financial data sources such as public companies’ annual reports and earning announcements, financial researchers have turned to financial news press, regulatory filings, and social media to uncover hidden information and sentimental cues.“ ([Lee et al., 2024, p. 461](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=462&annotation=TWLZH4QI) „Gupta [21] simplified the process of assessing annual reports of all the firms by leveraging the capabilities of LLMs, where the insights generated by the LLM are compiled in a Quant-styled dataset and augmented by historical stock price data.“ ([Lee et al., 2024, p. 462](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=462&annotation=MD7DXT2V) „avlyshenko [23] demonstrated that Llama 2 can be fine-tuned and multitask; when analyzing financial texts, it can return both a structured response and sentiment data in specified JSON format, which can further be loaded directly into predictive models as features.“ ([Lee et al., 2024, p. 462](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=462&annotation=RDE6IUQB) „GAI offers a promising solution by not only managing large datasets effectively but also generating synthetic data close to real-world financial data“ ([Lee et al., 2024, p. 462](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=462&annotation=ILH33TXR) „Issues such as data privacy, model interpretability, regulatory compliance, and the potential for generating biased or misleading data necessitate careful consideration.“ ([Lee et al., 2024, p. 462](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=464&annotation=TRQ4W59J) „The first step is to generate document embeddings.“ ([Lee et al., 2024, p. 464](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=464&annotation=5SMB7ZX3) „Sentence-BERT (SBERT) framework [29] was employed to convert each paper’s abstract into a vector representation.“ ([Lee et al., 2024, p. 464](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=464&annotation=XNJYQR7N) „The second step is to cluster these document embeddings.“ ([Lee et al., 2024, p. 464](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=464&annotation=XVL2X6NP) „a dimension reduction technique named UMAP [30] was used, preserving more of the local and global features of high-dimension document embeddings in a lower-dimension space.“ ([Lee et al., 2024, p. 464](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=464&annotation=EYCZQ9AY) „After that, the HDBSCAN model [31] is used to cluster the reduced embeddings.“ ([Lee et al., 2024, p. 464](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=464&annotation=9NCZ957M) „The third step is to model the topic representation with documents in each cluster. The class-based TF-IDF (c-TF-IDF) method [8] is employed to model the importance of a word to a cluster.“ ([Lee et al., 2024, p. 464](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=464&annotation=FRP36P8M) „The use of bag-of-words would disregard the semantic relationship among words or lose the context information in a paragraph, resulting in a failure of document representation.“ ([Lee et al., 2024, p. 464](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=465&annotation=CHIMNLU4) „transparency, fairness, and accountability.“ ([Lee et al., 2024, p. 465](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=465&annotation=FKHF5SYR) „GAI is used to automate decision-making processes, and any misuse or bias in these systems can lead to substantial consequences.“ ([Lee et al., 2024, p. 465](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=466&annotation=UTV3T6YG) „Terms such as ‘network’, ‘GANs’, ‘learning’, and ‘adversarial’ suggest that many existing studies utilize GANs for generating synthetic financial data, particularly for stock market simulations.“ ([Lee et al., 2024, p. 466](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=466&annotation=YVG2GIQS) „synthetic datasets play a critical role in financial research, as they allow researchers and practitioners to simulate various market scenarios, test trading strategies, and analyze risk without relying on real-world data, which may be limited or sensitive.“ ([Lee et al., 2024, p. 466](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=467&annotation=DMJTK5M8) „on the capability of general-purpose LLMs (e.g., GPTs, Gemini) to address financial problems, the effectiveness of finance-specific LLMs (e.g., FinGPT, FinPT) compared to general-purpose LLMs, and the identification of benchmarks and financial datasets that can be used to fairly evaluate the performance of LLMs in finance.“ ([Lee et al., 2024, p. 467](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=467&annotation=HRFTUHUI) „an examination of issues such as hallucinations, ethical and social impacts, and financial regulation.“ ([Lee et al., 2024, p. 467](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=467&annotation=6D9M655P) „the use of GAI for synthetic financial data generation.“ ([Lee et al., 2024, p. 467](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=468&annotation=KBP9QQGS) „General-purpose LLMs offer versatility and adaptability for a wide range of financial tasks but may lack the specialized domain knowledge required for complex financial analyses.“ ([Lee et al., 2024, p. 468](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=468&annotation=DPR6JXAB) „finance-specific LLMs are exclusively trained on financial data.“ ([Lee et al., 2024, p. 468](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=468&annotation=GFFMEY9H) „BloombergGPT, trained on a diverse range of financial data, showcased superior performance in financial tasks compared to existing general-purpose LLMs [58]. Similarly, FinMA was introduced by fine-tuning LLaMA with a tailored dataset, enabling it to executive various financial tasks [59]. Furthermore, FinGPT emerged as an open-source LLM tailored for the finance sector, providing accessible and transparent resources for researchers and practitioners to develop their FinLLMs [25,26].“ ([Lee et al., 2024, p. 468](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=468&annotation=YXIR8GVV) „FLLM, a financial LLM employing multitask prompt-based fine-tuning for data pre-processing and pre-understanding, employing abductive augmentation reasoning (AAR) to overcome manual annotation costs.“ ([Lee et al., 2024, p. 468](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=468&annotation=YJ9U8G4B) „FinVis-GPT, a pioneering multimodal LLM designed to interpret financial charts, marking a significant advancement in the application of multimodal LLMs in finance.“ ([Lee et al., 2024, p. 468](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=468&annotation=LGR39WTC) „textual, numerical, tabular, and image financial data“ ([Lee et al., 2024, p. 468](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=469&annotation=D22L7S3F) „In the realm of GAI, the phenomenon of hallucination manifests when a model generates data or information that deviates from accurately representing the underlying patterns or realities.“ ([Lee et al., 2024, p. 469](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=469&annotation=ZZCB3R3G) „three major stages to design hallucination-minimized LLM-based solutions tailored for the financial domain’s decision-makers: prototyping, scaling, and LLM evolution using feedback.“ ([Lee et al., 2024, p. 469](zotero://select/groups/5174548/items/LSMZCMT9))

[Go to annotation](zotero://open-pdf/groups/5174548/items/BG9IHQGJ?page=470&annotation=Q68WMSQL) „three primary challenges confronting most LLM applications: domain-specific expertise tailored to users’ unique circumstances, adherence to moral and ethical standards, and compliance with regulatory guidelines and oversight“ ([Lee et al., 2024, p. 470](zotero://select/groups/5174548/items/LSMZCMT9))