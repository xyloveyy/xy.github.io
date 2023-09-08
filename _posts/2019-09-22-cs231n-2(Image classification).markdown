---
layout: post
title: "2. Image classification"
subtitle: 'Image classification'
author: "Y. Yang"
header-style: text
tags:
  - Stanford-CS231N
---


# 1. challeges
- viewpoint variance
- scale variance
- ...


# 2. KNN
距离： L1 & L2

K: 就是在K个最近的图里面，挑选相同标签数最多的(投票)那个标签作为测试图片的标签

k-fold: 就是分成k个folds，然后每一个fold做一次验证集，每一次产生一个精确度，最后将k个精确度取平均。

个人觉得对于找颜色相近的图片，knn可能作用相对较大
# 3. 维度爆炸(Curse of dimensionality)
就是比如我规定训练数据需要覆盖整体数据20%的范围特征。那么一维中，10个数据里就是2个是训练数据。二维中，100个数据里面就要20个是训练数据。随着维度上升，需要的越来越多。

实际情况中，总数据量是固定的，也就是说，1维是10个，二维也是10个而非100个，随着维度升高，数据变得稀疏，那么需要的训练数据就会越来越多。比如二维下还要保证20%的覆盖，则需要每个维度上需要根号2//根号10(大约45%)那么多的比例的训练数据：
![image.png](https://i.loli.net/2019/09/23/xSFNUpO4unjqv5J.png)

而该问题对于knn尤甚。因为knn是基于距离的，而维度升高，数据稀疏化，距离就会更加的大，那么距离表示的意义就没那么重要了。