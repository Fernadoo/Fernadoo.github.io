---
layout:     post
title:      Data Science 常用算法
subtitle:   LaTex还不能正常显示😑
date:       2019-02-15
author:     Fernando
header-img: img/190215/header.jpg
catalog: true
tags:
    - Data Science
---

# Algorithms in Data Science 

#### Support Vector Machine (SVM)

* Hard margin SVM
* Soft margin SVM
* Non-linear SVM

#### Decision Tree

* Feature selection
* Tree spanning
  * Information gain
  * Gini index
* Pruning

#### Term Frequency - Inverse Document Frequency  (TF-IDF)

* Preprocessing (vectorise)
* Term frequency
  * $TF(x) = \frac{N(x)}{N}$
* Inverse document frequency
  * $IDF(x) = \log \frac{N}{N(x)}$
  * Smoothing: $\log \frac{N+1}{N(x)+1}+1$
* $TF-IDF(x) = TF(x) * IDF(x)$

#### Latent Semantic Analysis (LSA)

* $\arg min_{C_k} X_F = sqrt{\sum_{i=1}^M \sum_{j=1}^N\|X_{ij}\|^2},\ where\ X=C-C_k $
* $C=U \Sigma V^T$, $C_k = U\Sigma_kV^T$

####  Adaptive Boosting (Adaboost) [not clear]

* Steps
  1. Intilization
  2. Iteration
  3. Combine classifications

* Pro and cons
  * High accuracy
  * Simple, no feature selection
  * no overfitting
