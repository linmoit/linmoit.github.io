---
layout: post
title:  "二分查找"
categories: JavaScript
tags: 动画
author: LinMo
---

* content
{:toc}

前端动画的开发一直是我所热衷探索与研究的内容，本文将描述什么是拟真的动画效果，目前所流行的 React 动画库，以及一些基于 framer-motion 动画库的 demos。

### 介绍
二分查找也称折半查找（Binary Search），它是一种效率较高的查找方法。但是，折半查找要求线性表必须采用顺序存储结构，而且表中元素按关键字有序排列。
### 前提
必须待查找的序列有序
### 时间复杂度
O(log2n)
### 原理
1）确定该期间的中间位置K
2）将查找的值t与array[k]比较，若相等，查找成功返回此位置；否则确定新的查找区域，继续二分查找。
3）区域确定过程：
若array[k]>t，由于数组有序，所以array[k,k+1,……,high]>t；故新的区间为array[low, ..., K-1]；
反之，若array[k]<t对应查找区间为array[k+1, ..., high]

```python
#!/usr/bin/env python
# -*- coding: utf-8 -*-
# @Date    : 2021-03-02
# @Author  : 林末
# @desc : 二分查找算法，python版

def serach(array, t):
    array.sort() #排序，保证列表是有序的
    low = 0
    height = len(array) - 1
    while low <= height:
        k = (low + height) // 2
        if array[k] < t:
            low = k + 1
        elif array[k] > t:
            height = k - 1
        else:
            return k #找到后返回位置
    return -1 #找不到返回-1
array = [1, 3, 5, 7, 9, 6, 8, 0]
print(serach(array, 5))
```

**End**
-
**林末：[https://www.helloworld.net/linmo](https://www.helloworld.net/linmo)**
