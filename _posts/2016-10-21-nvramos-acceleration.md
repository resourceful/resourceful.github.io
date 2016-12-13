---
layout: post
title: "Storage and Computing Acceleration for Big Data Analytics"
subtitle: "NVRAMOS'16 day2 Tech session 1-2"
date: 2016-10-21 09:10:00
author: "Seongjin Lee"
comments: true
---

Mookyung Jung
(SK Telecom)


big-data 에서 cpu bottleneck으로 storage I/O성능 다 쓰질 못함
dpa - data processing acceleration
cpu bottleneck문제 큼


I/O accelerator
- nvcache
- key-value interface

Data processing acceleerator
data relocation
- compression : 30% perf down 문제
- deduplication : 30% perf down 문제
computing
- sql/filter/table pivot - sw&hw 최적화 중
- machine learning / dnn
