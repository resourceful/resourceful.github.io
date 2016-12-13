---
layout: post
title: "Host Software Optimizations for SSD"
subtitle: "NVRAMOS'16 day2 Tech session 1-1"
date: 2016-10-21 09:00:00
author: "Seongjin Lee"
comments: true
---


Wooseok Chang
(Samsung Elec.)

hotstorage 16
https://www.usenix.org/conference/hotstorage16/workshop-program/presentation/ahn
optimization for hadoop -IEEE bigdata'16 "Lazer: Distributed Memory-Efficient Assembly of Large-Scale Genomes"???
논문으로 많이 내고 있음

The faster ssd, the more sensitive to system architecture. not only to cpu

where does the pendulum of optimization go after cpu gets scalability? nvmf(nvm over fabric) 확장가능하도록 ?

scm such as zssd is adding another layer to memory hierarchy  for what?
what are you going to do when one flash die is worn out in 64tb ssd?

all storage vendors try to release sr-iov supported ssds. at least claimed
시장에는 없음.

피의 전쟁 - you may add more ideas for performance but power in the way 전력 문제

how could we handle more than 500k loc of ssd firmware? and more features?

pcie 4lane -> 8lane가는것 회의적? 사용 도메인, 일인이면 의미 없음. 성능 빠른 인터페이스를 쓰더라도 스토리지가 따라 오지 못할 것.; 따라 오게 만든다면 새로운 응용처가 있어야 함
