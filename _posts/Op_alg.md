---
layout: post
title: 深度学习优化算法
date: 2020-7-19
categories: blog
tags: [深度学习,算法]
description: 深度学习基本算法
---

本文内容来自Ian Goodfellow花书第八章8.3节基本算法，今天吃饭时无意中翻开的就是这一块，所以就仔细看了一下~(#^.^#)
#### 随机梯度下降

初始参数$\theta$，学习率$\epsilon$

> 从训练集总采包含m个样本的小批量$\{x^{(1)},\cdots,x^{(m)}\}$
> 以小批量上的梯度均值作为(无偏)梯度估计：$\boldsymbol{g} \leftarrow +\frac{1}{m} \nabla_{\boldsymbol{\theta}} \sum_{i} L\left(f\left(\boldsymbol{x}^{(i)} ; \boldsymbol{\theta}\right), \boldsymbol{y}^{(i)}\right)$
>
> 更新：$\theta \leftarrow \theta-\epsilon \hat{g}$

#### 动量 随机梯度下降

动量法旨在加速学习，引入速度向量$\boldsymbol{v}$ ，代表参数在参数空间移动的方向和速率，定义为负梯度的指数衰减平均。“动量”一词来自物理，物理中负梯度是移动参数空间中粒子的力，动量是质量乘以速度，假设单位质量时，速度向量可以看做粒子的动量。

```csharp
[comment]: <> (指数在哪呢？)
```

> 从训练集总采包含m个样本的小批量$\{x^{(1)},\cdots,x^{(m)}\}$
> 以小批量上的梯度均值作为(无偏)梯度估计：$\boldsymbol{g} \leftarrow +\frac{1}{m} \nabla_{\boldsymbol{\theta}} \sum_{i} L\left(f\left(\boldsymbol{x}^{(i)} ; \boldsymbol{\theta}\right), \boldsymbol{y}^{(i)}\right)$
>
> 计算速度更新：$\boldsymbol{v} \leftarrow \alpha \boldsymbol{v}-\epsilon \boldsymbol{g}$
>
> 更新：$\theta \leftarrow \theta-\epsilon \hat{g}$

#### 