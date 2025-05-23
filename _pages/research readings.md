---
layout: default
title: research readings
permalink: /research/
nav: true
nav_order: 4
---

# Research Readings

A curated list of research papers I'm reading or have read, organized by topic. Each entry includes links, brief notes. And I plan to port summaries from my ipad in the near future.

---

## Streaming / Encoding

| Title | Authors | Org | Year | Notes |
|-------|---------|-------|------|-------|
| [Complexity-Based Consistent-Quality Encoding In The Cloud](https://ieeexplore.ieee.org/document/7532605) | De Cock et al. | Netflix | 2016 | Tradeoffs between per title encoding vs per chunk encoding; bitrate ladder per title |
| [Fast algorithm for HDR video pre-processing](https://norkin.org/pdf/PCS_2016_HDR_video_preprocessing.pdf) | Andrey Norkin. | Netflix | 2016 | Better performance over iterative method; Root Cause: non linear transfer func in HDR10 in low luminance ranges; Still computes pixel to pixel (ig pre DL)|
| [Film Grain Synthesis for AV1 Video Codec](https://norkin.org/pdf/DCC_2018_AV1_film_grain.pdf) | Andrey Norkin. | Netflix | 2018 | Autoregressive Model for modelling film grain. Properties of grain: non temporal, spatial correlations, only on smooth regions. Color Componenets unclear. Is it slow because of autoregressive nature? Potential for DL?|

---

## Mechanistic Interpretability

| Title | Authors | Year | Notes | 
|-------|---------|-------|------|
| [A Mathematical Framework for Transformer Circuits](https://transformer-circuits.pub/2021/framework/index.html) | Olah et al.| 2021 | |
| [Toy Models of Superposition](https://transformer-circuits.pub/2022/toy_model/index.html) | Elhage et al. | 2022 | |

---

## (Causal)Representation Learning

| Title | Authors | Year | Notes |
|-------|---------|-------|------|
| [Beta-VAE: Learning Basic Visual Concepts](https://openreview.net/forum?id=Sy2fzU9gl) | Higgins et al. | 2017 | KL Divergence Penalty term to a standard VAE loss func |

---


