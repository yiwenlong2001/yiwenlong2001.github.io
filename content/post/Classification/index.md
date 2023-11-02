---
title: Classification review notes (updating...)
description: One of notes of CS245 
date: 2023-10-30 00:00:00+0000
image: classification.png
tags: 
    - Data analysis
    - UCLA Course Note
    - Classification
categories:
    - Note
---

# Classification


## Decision Tree

- 决策树最主要的就是构建决策树，构建决策树有以下几种著名的算法。

### ID3算法

ID3算法是一种基于信息熵的算法。通过信息增益找到可以最合适的划分属性。

> Gain(S, A) = E(S) - E(S|A)  
> E(S|A) = - sum(|S_i|/|S| * E(S_1))  

- 计算所有的属性对应的信息增益，选择信息增益最大的属性对数据集进行划分。
- 递归地对之后的数据集进行划分直到：
    - 只剩一个属性无法继续划分
    - 所有的属性信息增益都很小

缺点：

- 无剪枝策略，容易过拟合；
- 只能用于处理离散分布的特征；
- 没有考虑缺失值。
- 信息增益准则对可取值数目较多的特征有所偏好，类似“编号”的特征其信息增益接近于 1，而信息增益比指数可以解决此缺点。

为了解决这些问题，提出这些改进：

### Gain ratio

$ SplitInformation = \sum_{i=1}^{c} \frac{|S_i|}{|S|} log_2 \frac{|S_i|}{|S|} $
$ GainRatio(S, A) = \frac{Gain(S, A)}{SplitInformatio(S, A)} $

### Gini Index

如果一个数据集有n各种类的数据，那么gini index被定义为
$$ gini(T) = 1 - \sum_{j=1}^n p_j^2$$
其中$ p_j $是种类j再数据集中的频繁程度

假如我们将数据集T分为大小分别为N1和N2的两个子集T1和T2， 那么此次分割中：
$$ gini_{split}(T) = \frac{N_1}{N} gini(T_1) + \frac{N_2}{N} gini(T_2) $$

在各种分割中，选择$ gini_{split}(T) $最小的分法。

### 过拟合

针对过拟合可以采用以下两种方法：
- Prepruning: Halt tree construction early—do not split a node if this would result in the goodness measure falling below a threshold   
- Postpruning: Remove branches from a “fully grown” tree—get a sequence of progressively pruned trees

确定树的大小：使用MDL原则

## 贝叶斯网络
