---
layout: post
title: "Interesting question"
subtitle: "Locality and hotness"
date: 2016-09-22
author: "Seongjin Lee"
comments: true
---

In a computer system and mostly for cache systems, there are two most important
localities. First locality is spatial locality and the second locality is
spatial. They are important because the system improves the performance by
storing frequently accessed or soon to be accessed in the cache, and evict
those that are not going to be used. 

Spatial locality describes the phenomenon where a resource that is going to be
accessed next has high likelihood of being near the previous access. For
example, a resource on position i+1 is likely to be accessed after referencing
a resource on position i.

Temporal locality, on the other hand, describes the case where a resource in a
location accessed once has high chance of being referenced again in the near
future. For example, a variable in a loop will be accessed as many as the loop count.

Understanding the locality is not only important in cache systems but also in
log-structured file systems, especially when a log-structured file system that
employs hot/cold separation mechanism, performs garbage collection. After
cleaning a segment in the file system, the valid blocks within the segment has
to be allocated to one of hot or cold segments. Typically, cold data represents
image, audio, visual, and write-once-read-only files, and frequently updated
blocks occupies the hot segment. 

Say a file is as large as few hundred Gigabytes which is used as storage for a
virtual machine guest. One can argue that log-structured file system is not
suit for such application, but let's not discuss the best local file system for
a virtual machines. Let's assume that the guest performs a lot of random write
on various and wide range of Logical Block Address (LBA) on the guest storage. However, to host system, it is just a random access to different locations which does not affect or make difference for the garbage collection and treat them specially. To garbage collection, all the write requests to the large is as if there are no localities in the workload. 

The question is that do we have to consider reference counts of large files as well as the localities?
