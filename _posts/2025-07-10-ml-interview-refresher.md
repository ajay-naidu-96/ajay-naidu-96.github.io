---
layout: distill
title: ML Refresher
description: Just some ML algorithms to refresh my memory, without all the fluff
tags: distill formatting
giscus_comments: false
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
mathjax: true
typograms: true

authors:
  - name: Ajay Gopi
    url: "https://ajay-naidu-96.github.io"
    affiliations:
      name: Rochester Institute of Technology, New York

bibliography: 2018-12-22-distill.bib

toc:
  - name: 1. Linear Regression - Closed Forms vs Iterative
  - name: 2. Logistic Regresssion
  - name: 3. Classification Metrics 
  - name: 4. K Nearest Neighbour

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

# 1. Linear Regression : Closed Forms vs Iterative

## Closed Form Solution

**Objective: $\boldsymbol{\min J(\theta)}$**,

 $$ 
 J(\boldsymbol{\theta}) = \frac{1}{2n} \left\| \mathbf{y} - \mathbf{X} \boldsymbol{\theta} \right\|^2
 $$

**Expand**,
$$ 
J(\boldsymbol{\theta}) = \frac{1}{2n} \left[ \mathbf{y}^\top \mathbf{y} - 2 \mathbf{y}^\top \mathbf{X} \boldsymbol{\theta} + \boldsymbol{\theta}^\top \mathbf{X}^\top \mathbf{X} \boldsymbol{\theta} \right]
$$

**Gradient**,
$$
\nabla_{\boldsymbol{\theta}} J(\boldsymbol{\theta}) = \frac{1}{n} \left( \mathbf{X}^\top \mathbf{X} \boldsymbol{\theta} - \mathbf{X}^\top \mathbf{y} \right)
$$

**Setting gradient to zero**,
$$
\mathbf{X}^\top \mathbf{X} \boldsymbol{\theta} = \mathbf{X}^\top \mathbf{y}
$$

**Solution**:
$$
\boxed{\boldsymbol{\theta} = \left( \mathbf{X}^\top \mathbf{X} \right)^{-1} \mathbf{X}^\top \mathbf{y}}
$$

```python
theta = np.linalg.inv(X.T @ X) @ X.T @ y
# theta = np.linalg.pinv(X) @ y  # for the pseudo inverse
```

### Notes:
1. Input `X` isn't always invertible, hence use pseudo inverse instead, likely more stable. 
2. Another way to think about this is `Cov(X,Y) / Var(X)`, where `X.T @ Y` is the covariance and `X.T @ X` is variance

## Iterative Solution

**Objective: $\boldsymbol{\min J(\theta)}$**,
$$ 
J(\boldsymbol{\theta}) = \frac{1}{2n} \left\| \mathbf{y} - \mathbf{X} \boldsymbol{\theta} \right\|^2
$$

**Gradient**:
$$
\nabla_{\boldsymbol{\theta}} J(\boldsymbol{\theta}) = \frac{1}{n} \mathbf{X}^\top \left( \mathbf{X} \boldsymbol{\theta} - \mathbf{y} \right)
$$

**Gradient Descent Update**:
$$
\boldsymbol{\theta}^{(i+1)} = \boldsymbol{\theta}^{(i)} - \alpha \nabla_{\boldsymbol{\theta}} J(\boldsymbol{\theta}^{(i)})
$$

**Update Rule**:
$$
\boxed{ \boldsymbol{\theta}^{(i+1)} = \boldsymbol{\theta}^{(i)} - \frac{\alpha}{n} \mathbf{X}^\top \left( \mathbf{X} \boldsymbol{\theta}^{(i)} - \mathbf{y} \right) }$$

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


# 2. Logistic Regression

Transform `X.T @ theta` by applying sigmoid function to transform it into probabilities or a classification problem. The loss changes from mean squared error to cross-entropy loss. 

```python

def sigmoid(x):
  f = lambda t: 1/(1+np.exp(-t))
  return f(x)


def cross_entropy_loss(y, y_pred):
  avg_loss = (-y * np.log(y_pred) - (1-y) * np.log(1-y_pred)).mean()
  return avg_loss


z = X @ theta 
y_pred = sigmoid(z)
loss = cross_entropy_loss(y, y_pred)

# gradients w.r.t weights and bias
# dw = (1 / m) * np.dot(X.T, (y_pred - y))
# db = (1 / m) * np.sum(y_pred - y)

```

# 3. Classification Metrics

### 1. Building Blocks for Classification

```python

tp = np.sum((y_true == 1) & (y_pred == 1))
fp = np.sum((y_true == 0) & (y_pred == 1))
tn = np.sum((y_true == 0) & (y_pred == 0))
fn = np.sum((y_true == 1) & (y_pred == 0))

```

### 2. Precision, Recall & f1 Score

```python

precision = tp / (tp + fp)

recall = tp / (tp + fn)

f1 = (2 * precision * recall) / (precision + recall)
```

### 3. AUCROC

```python

for threshold in np.arange(0, 1.1, 0.1):  

  y_pred = (predicted_probs >= threshold).astype(int)

  tp = np.sum((y_true == 1) & (y_pred == 1))
  fp = np.sum((y_true == 0) & (y_pred == 1))
  tn = np.sum((y_true == 0) & (y_pred == 0))
  fn = np.sum((y_true == 1) & (y_pred == 0))

  tpr = tp / (tp + fn)
  fpr = fp / (fp + tn)

  tprs.append(tpr)
  fprs.append(fpr)


def compute_auc_roc(tprs, fprs):
  aucroc = 0

  for i in range(1, len(tprs)):
    aucroc += 0.5 * abs(fprs[i]-fprs[i-1]) * (trps[i]+tprs[i-1])

  return acuroc
```

# 4. K Nearest Neighbour

Compute some distance metric and sort them and assign label based on most common vote among the top k closest neighbours

```python

def compute_distance(pt1, pt2):

  return np.sqrt(sum((p-q)**2 for p, q in zip(pt1, pt2)))
  ## return np.linalg.norm(np.array(pt1), np.array(pt2))


data = [
    ((1.2, 0.4), 'Apple'),
    ((1.0, 0.5), 'Apple'),
    ((1.6, 0.7), 'Orange'),
    ((1.3, 0.3), 'Apple'),
    ((1.8, 0.8), 'Orange')
]

query = (1.4, 0.6)
distances = []
k = 3

for (x, y) in data:
  distances.append((compute_distance(query, x), y))
  # heappush(distances, (compute_distance(query, x), y))

distances.sort()

# while distances and k > 0 :
#   dist, label = heappop(distances)
#   labels.append(label)
#   k -= 1

labels = [label for dist, label in distances[:k]]
Counter(labels).most_common(1)[0][0]

```

# 5. Naive Bayes Classifier

Step 1: Calculate the prior probabilites

```python
def get_priors(y):
  # here y is a pandas column
  return y.value_counts(normalize=True)
```

Step 2: Calculate likelihoods

```python
# p(x/y)

def get_likelihoods_with_smoothning(X, Y):
  # nested dict y == target_class and x == some_feature

  likelihoods = {}

  for feature in X.columns:

    likelihoods[feature] = {}

    for class_ in Y.unique():
    
      value_counts = X[feature][Y==class_].value_counts()+1
      value_counts /= (len(X[feature][Y==class_]) + X[feature].nunique()) 

      likelihoods[feature][class_] = value_counts

  return likelihoods

```

Step 3: Calculate posterior probabilitites

```python

def calculate_prob(X_test, likelihoods, priors):

  res = []

  for _, data_point in X_test.iterrows():

    class_probs = {}

    for class_, prior in priors.items():

      class_probs[class_] = prior
      
      for col in data_point.columns:

        feature = likelihoods[col][class_]

        class_probs[class_] *= feature.get(data_point[col], 1/len(feature))

    res.append(max(class_probs, key=class_probs.get))

  return res
```


# 6. Decision Trees

Step 1: It's a recursive func, so figure out base cases

Base Case 1: Creating the terminal node 

```python

  def create_terminal(group):
    return Counter([row[-1] for row in group]).most_common(1)[0][0]
    
```

Base Case 2:
 ```python

  def recurse_split(node, min_size, max_depth, depth):
    left, right = node['groups']

    del node['groups']

  ```

