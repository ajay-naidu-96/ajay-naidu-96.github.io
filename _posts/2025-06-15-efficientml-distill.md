---
layout: distill
title: EfficientML Notes
description: personal notes from the lectures by Prof. Song Han on Efficent ML
tags: distill formatting
giscus_comments: true
date: 2025-06-15
featured: true
mermaid:
  enabled: true
  zoomable: true
code_diff: true
map: true
chart:
  chartjs: true
  echarts: true
  vega_lite: true
tikzjax: true
typograms: true

authors:
  - name: Ajay Gopi
    url: "https://ajay-naidu-96.github.io"
    affiliations:
      name: Rochester Institute of Technology, New York

bibliography: 2018-12-22-distill.bib

toc:
  - name: Lecture 2 - Basics of Neural Networks

# Below is an example of injecting additional post-specific styles.
# If you use this post as a template, delete this _styles block.
_styles: >
  .fake-img {
    background: #bbb;
    border: 1px solid rgba(0, 0, 0, 0.1);
    box-shadow: 0 0px 4px rgba(0, 0, 0, 0.1);
    margin-bottom: 12px;
  }
  .fake-img p {
    font-family: monospace;
    color: white;
    text-align: left;
    margin: 12px 0;
    text-align: center;
    font-size: 16px;
  }
---

# Basics of Neural Networks

[Link](https://www.dropbox.com/scl/fi/pxvvqyq2yu6mwgk79bq5x/Lec02-Basics.pdf?rlkey=tsumfkhrglic55jnjs4yu66ni&e=4&st=cmwnvuvn&dl=0) to the original slides. 

## Neural Network Layers

### Fully Connected Layer 

    <p align="center">
      <img src="./LectureMedia/efficientml/fc_layer.png" alt="Fully Connected Layer" width="600"/>
    </p>

    Every neuron in the output layer is connected to every other neuron in the previous layer, resulting in a dense weight matrix. 

    Input Features, X = (n, cᵢ)
    Weight Matrix, W = (cₒ, cᵢ)
    Output Features, Y = (n, cₒ)
    Bias, b = (cₒ)

    where, cᵢ = number of input channels, cₒ = number of output channels, and n = batch_size

### Convolutional Layer

#### 1D Convolutions

    <p align="center">
      <img src="LectureMedia/efficientml/1D_conv.png" alt="1D Convolutional Layer" width="600"/>
    </p>

     Input Features, X = (n, cᵢ, wᵢ)
     Input Features, X = (n, cₒ, wᵢ)
     Weight Matrix, W = (n, cᵢ, wᵢ)

#### 2D Convolutions
#### Grouped Covolution
#### Depthwise Convolution
### Normalization Layer 
### Activation Function
### Transformers

## Latency vs Throughput

## Model Parameters
---
