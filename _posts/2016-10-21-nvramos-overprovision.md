---
layout: post
title: "A Relationship between Overprovisioning Area and Performance on Mobile Storage"
subtitle: "NVRAMOS'16 day2 Tech session 2-2"
date: 2016-10-21 11:20:00
author: "Seongjin Lee"
comments: true
---

Iksung Oh (SK Hynix)


모바일의 성능 향상

{$\frac {physcial capacity - user capacity}{user capacity}* 100 = Overprovisioning$}


Over provisioning SSD
* level 1 : 7.37%
* Level 2 : max 28% for example total capacity is 128 GB, user can see only 120GB or 100GB
* Level 3 : Dynamic Overprovisioning on user Area


Some restrictions
* OVP usage - system block, device protection, map table, reserved block, free block for user.
* use GC throttling to sustain the performance. If internal OP is small, the performance may drop sharply.


Relationship between OP and Performance is that less the ovp lower the performance


used bricksim to test

workload Thread IO trace: sequential write 1G -> random 200M

internal ovp 2%
system block 5
level 2 ovp 6%


Urgent case

* They set free block < 3%, and the requirement is that it shows 30% of sustain performance at gc. Result shows that ovp at 2.7% meets the requirement



perf vs ovp Relationship

* 1.6% of performance gain observed as op increased by 1%




exploitation for optimal ovp

* Control the performance of sustain state
* control the trigger point at entering the urgent state


WAF 3
