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

- ID3算法是一种基于信息熵的算法。
- 通过信息增益找到可以最合适的划分属性。

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

### 
