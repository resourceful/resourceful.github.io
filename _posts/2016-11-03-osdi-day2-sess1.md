---
layout: post
title: "OSDI 2016 Tech Session Graph Processing and Machine Learning"
subtitle: "Day2 Tech session 1"
date: 2016-11-03 09:00:00
author: "Seongjin Lee"
comments: true
---

9:00 am–10:20 am
Graph Processing and Machine Learning

Session Chair: Phil Levis, Stanford University

# TensorFlow: A System for Large-Scale Machine Learning
* Martín Abadi, Paul Barham, Jianmin Chen, Zhifeng Chen, Andy Davis, Jeffrey Dean, Matthieu Devin, Sanjay Ghemawat, Geoffrey Irving, Michael Isard, Manjunath Kudlur, Josh Levenberg, Rajat Monga, Sherry Moore, Derek G. Murray, Benoit Steiner, Paul Tucker, Vijay Vasudevan, Pete Warden, Martin Wicke, Yuan Yu, and Xiaoqiang Zheng, Google Brain

Derek G. Murray

21 authors

google photo에서도 활용

* distbelief to scale
* custom systems - not flexible
* torch, theano - new machine learning


parameter synchronizations
worker가 작업이 끝나면 파라미터 서버에게 전달, synchronous 는 늦게 끝나는 worker 를 기다려야 하기 때문에 느리다. k개의 백업gpu worker를 추가 함. k 개가 까지 느린 것은 보완 가능함


challenges
* automatic device placement
* compiler optimizations







# Exploring the Hidden Dimension in Graph Processing
* Mingxing Zhang, Yongwei Wu, and Kang Chen, Tsinghua University; Xuehai Qian, University of Southern California; Xue Li and Weimin Zheng, Tsinghua University

graph computing is even more ubiquitous




# Gemini: A Computation-Centric Distributed Graph Processing System
* Xiaowei Zhu, Wenguang Chen, and Weimin Zheng, Tsinghua University; Xiaosong Ma, Hamad Bin Khalifa University

# Fast and Concurrent RDF Queries with RDMA-Based Distributed Graph Exploration
* Jiaxin Shi, Youyang Yao, Rong Chen, and Haibo Chen, Shanghai Jiao Tong University; Feifei Li, University of Utah
