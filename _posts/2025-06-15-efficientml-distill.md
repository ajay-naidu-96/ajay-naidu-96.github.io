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
<img src="assets/img/LectureMedia/efficientml/fc_layer.jpg" alt="Fully Connected Layer" width="600" height="300"/>
</p>

Every neuron in the output layer is connected to every other neuron in the previous layer, resulting in a dense weight matrix. 

**Input Features**, $\mathbf{X} = (n, c_i)$ <br>
**Weight Matrix**, $\mathbf{W} = (c_o, c_i)$ <br>
**Output Features**, $\mathbf{Y} = (n, c_o)$ <br>
**Bias**, $\mathbf{b} = (c_o)$ <br>

where, $c_i$ = number of input channels, $c_o$ = number of output channels, and n = batch_size

### Convolutional Layer

Output neuron is connected to the input receptive field. Receptive field is usually the kernel shape. Based on the shape of the kernels, we have 1D and 2D convolution operations. 

#### 1D Convolutions

<p align="center">
  <img src="assets/img/LectureMedia/efficientml/1D_conv.jpg" alt="1D Convolutional Layer" width="600" height="300"/>
</p>

Simpler to visualize from a 2D Kernel, basically you need to match the number of channels and discard either the height or width component. 

**Input Features**, $\mathbf{X} = (n, c_i, w_i)$ <br>
**Weight Matrix**, $\mathbf{W} = (c_o, c_i, k_w)$ <br>
**Output Features**, $\mathbf{Y} = (n, c_o, w_o)$ <br>
**Bias**, $\mathbf{b} = (c_o)$ <br>

where, $c_i$ = number of input channels, $c_o$ = number of output channels, n = batch_size and $k_w$ is width of kernel.

#### 2D Convolutions
#### Grouped Covolution
#### Depthwise Convolution
### Normalization Layer 
### Activation Function
### Transformers

## Latency vs Throughput

## Model Parameters
---
