---
layout: post
title: "Linux Kernel Encryption Support for Filesystem"
subtitle: "NVRAMOS'16 day2 Tech session 2-1"
date: 2016-10-21 11:00:00
author: "Seongjin Lee"
comments: true
---


Kyungsik Lee, Ph.D. LG

Encryption is now a thing in mobile systems. Android 6.0 CDD doesnot have to apply AES if crypto performance is not above 50MiB/second


using encryption drops the performance by 60% and 40% on random and sequential workloads. 1 CPU core, freq(0.6-1GHz). In general, HW acceleration reduces the overhead. In high end systems with dedicated hw, the performance drop is insignificant.

encryption is supporte in Linux since 2.6.4 (march 2004). In v4.6, it supports VFS crypto engine.


File system level encryption Vs disk encryption (FBE vs FDE)

FBE -- per file encryption; hacker cannot use a single key to read a file

* dm-crypt : volume or partition level single key encryption
* eCryptfs (stacked cryptographci file system) : for external devices, low performance because it works on top of an other file system
* Ext4 Encryption : dedicated to Ext4



encryption are cpu bound. really?
to confirm, they used sequential read prefetching to test the dependency of readahead. prefetching has less effect.

ext4 encryption : performance drop is not great with respect to the number of CPUs used.



* seq. read throughput dropped significantly in CPU based encryption, leading to performance degradation
* Read(decrypt) overhead seq.read >> random read* seq. write throughput falls slightly except eCryptfs
* IO throughput of eCryptfs is shown less scalable in multi-core system
* seq. read performance can be improved by applying multi-threaded decryption
