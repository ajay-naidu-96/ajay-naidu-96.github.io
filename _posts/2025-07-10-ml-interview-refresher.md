---
layout: distill
title: ML Refresher
description: Just some ML algorithms to refresh my memory
tags: distill formatting
giscus_comments: true
date: 2025-07-10
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
  - name: Linear Regression - Closed Forms vs Iterative

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

# Linear Regression : Closed Forms vs Iterative

## Closed Form Solution

**Objective: $\boldsymbol{\min J(\theta)}$**,

 $$ J(\boldsymbol{\theta}) = \frac{1}{2n} \left\| \mathbf{y} - \mathbf{X} \boldsymbol{\theta} \right\|^2$$

**Expand**,
$$J(\boldsymbol{\theta}) = \frac{1}{2n} \left[ \mathbf{y}^\top \mathbf{y} - 2 \mathbf{y}^\top \mathbf{X} \boldsymbol{\theta} + \boldsymbol{\theta}^\top \mathbf{X}^\top \mathbf{X} \boldsymbol{\theta} \right]$$

**Gradient,**
$$\nabla_{\boldsymbol{\theta}} J(\boldsymbol{\theta}) = \frac{1}{n} \left( \mathbf{X}^\top \mathbf{X} \boldsymbol{\theta} - \mathbf{X}^\top \mathbf{y} \right)$$

**Setting gradient to zero**,
$$\mathbf{X}^\top \mathbf{X} \boldsymbol{\theta} = \mathbf{X}^\top \mathbf{y}$$

**Solution**:
$$\boxed{\boldsymbol{\theta} = \left( \mathbf{X}^\top \mathbf{X} \right)^{-1} \mathbf{X}^\top \mathbf{y}}$$

```python
theta = np.linalg.inv(X.T @ X) @ X.T @ y
# theta = np.linalg.pinv(X) @ y  # for the pseudo inverse
```

### Notes:
1. Input `X` isn't always invertible, hence use pseudo inverse instead, likely more stable. 

## Iterative Solution

**Objective: $\boldsymbol{\min J(\theta)}$**,

 $$ J(\boldsymbol{\theta}) = \frac{1}{2n} \left\| \mathbf{y} - \mathbf{X} \boldsymbol{\theta} \right\|^2$$


**Gradient**:
$$\nabla_{\boldsymbol{\theta}} J(\boldsymbol{\theta}) = \frac{1}{n} \mathbf{X}^\top \left( \mathbf{X} \boldsymbol{\theta} - \mathbf{y} \right)$$

**Gradient Descent Update**:
$$\boldsymbol{\theta}^{(i+1)} = \boldsymbol{\theta}^{(i)} - \alpha \nabla_{\boldsymbol{\theta}} J(\boldsymbol{\theta}^{(i)})$$

**Update Rule**:
$$\boxed{ \boldsymbol{\theta}^{(i+1)} = \boldsymbol{\theta}^{(i)} - \frac{\alpha}{n} \mathbf{X}^\top \left( \mathbf{X} \boldsymbol{\theta}^{(i)} - \mathbf{y} \right) }$$

where $\alpha$ is the learning rate and $t$ is the iteration number.

```python

num_rows, num_cols = X.shape
## if no bias
## X = np.hstack(np.ones(num_rows, 1), X) and num_cols += 1 because of addn
theta = np.zeros((num_cols, 1))

for i in range(iterations):
  theta -= (alpha / num_rows) * X.T @ (X @ theta - y)

```

### Notes: 
1. The both equations are the same except for some mumbo jumbo