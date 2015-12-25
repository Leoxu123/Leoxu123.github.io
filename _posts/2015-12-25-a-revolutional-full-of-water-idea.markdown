---
layout: post
title: A Revolutional(full-of-water)idea
modified:
categories: 
description:
tags: []
image:
  feature:
  credit:
  creditlink:
comments:
share:
date: 2015-12-25T21:48:08+08:00
---

**深度拖延龟速看完两篇paper后，发现一个新大（水）陆（箱）！**

[1. Topic Word Embedding](http://nlp.csai.tsinghua.edu.cn/~lzy/publications/aaai2015_twe.pdf) 这篇文章主要解决当前被玩的最多word2ec模型中没有解决的一词多义(polysemy)问题。先用LDA得到每个词的topic，然后略微修改word2vec模型，在预测词的时候加入了topic信息，每个词的词向量最终由word和topic向量的连接。

[2. Learning Word Representations by Jointly Modeling Syntagmatic and Paradigmatic Relations](http://ofey.me/papers/wordrep_acl2015.pdf)这篇文章主要是提高word2vec的表示能力，基于word2vec模型的假设，出现在相似语境中的词更相似（在向量空间更近），这仅仅反映了语言学中的聚合(paradigmatic)关系。另外一个重要的关系是组合(syntagmatic)关系。例如:
<font color="red">远的不是距离，而是次元啊</font><p></p>这里**远**和**距离**就是组合关系
然后呢，做法相当类似。常见的解决组合关系的模型是LSA，直接将objective function加入一个词在文档中出现的概率.

比较两个模型，它们都是找出word2vec表征能力在linguistic欠缺,它们的objective function更是惊人的相似。那是不是可以找到word2vec的其他在linguistic rule上的欠缺以及相应的模型，找个方法把它们结合起来？
