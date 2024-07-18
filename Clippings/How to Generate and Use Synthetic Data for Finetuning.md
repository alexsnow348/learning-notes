---
category: "[[Clippings]]"
author: "[[Eugene Yan]]"
title: How to Generate and Use Synthetic Data for Finetuning
source: https://eugeneyan.com/writing/synthetic/
clipped: 2024-07-18
topics: knowledge-distillation
tags:
  - clippings
---

Self-Instruct and Unnatural Instructions were published a day apart (in Dec 2022) but take very different approaches to generate synthetic data. The former bootstraps synthetic data from the model itself while the latter distills it from an external, stronger model.

**[Self-Instruct](https://arxiv.org/abs/2212.10560) improves the instruction-following ability of a non-finetuned model (vanilla gpt-3) by bootstrapping off its own generations**

**In contrast to Self-Instruct, [Unnatural Instructions](https://arxiv.org/abs/2212.09689) generates synthetic data from an external model, gpt-3.5 (text-davinci-002).**

**[Alpaca](https://crfm.stanford.edu/2023/03/13/alpaca.html) finetuned llama-7b on 52k instruction-following samples generated from gpt-3.5 (text-davinci-003).**

## Self-improvement (aka non-distillation) techniques

Self-improvement approaches don’t rely on an external model to generate synthetic data. Instead, they bootstrap on the model that’s being finetuned over several iterations of generation, self-evaluation, and finetuning.