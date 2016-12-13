---
layout: post
title: "OSDI 2016 Tech Session Cloud Systems II"
subtitle: "Day3 Tech session 4"
date: 2016-11-04 15:50:00
author: "Seongjin Lee"
comments: true
---

3:50 pm–5:10 pm
Cloud Systems II

Session Chair: Chris Rossbach, VMware Research and The University of Texas at Austin

# Diamond: Automating Data Management and Storage for Wide-Area, Reactive Applications
* Irene Zhang, Niel Lebeck, Pedro Fonseca, Brandon Holt, Raymond Cheng, Ariadna Norberg, Arvind Krishnamurthy, and Henry M. Levy, University of Washington

reactive applications 라는 것 자체가 문제 덩어리인듯
내가 바꾼것을 상대도 즉시 변경 된 것을 반영해야 함.

write->notify-> notify-> read 네트워크이기 때문에 어느 부분에서 데이터 손실이 되어도 이상하지 않고 그렇기 때문에 문제가 됨

diamond = reactive data management service
 - ensures updates to shared data are consistent and durable

RDT (reactive data type)

rmap (reactive data map) 쓰려는 데이터를 정리함 순서 등

read-write transaction
begin() - commit()으로 묶음 : atomic을 가정

reactive transaction
 - registerReactiveTxn

ACID + R(reactivity) 를 보장함

실제구현은 논문을 보라고 ..




# Slicer: Auto-Sharding for Datacenter Applications
* Atul Adya, Daniel Myers, Jon Howell, Jeremy Elson, Colin Meek, Vishesh Khemani, Stefan Fulger, Pan Gu, Lakshminath Bhuvanagiri, Jason Hunter, Roberto Peon, Larry Kai, Alexander Shraer, and Arif Merchant, Google; Kfir Lev-Ari, Technion—Israel Institute of Technology

질문:
 - 8-10 second 만에 서버가 fail된 것을 알 수 있음
 - 언제 fail 될지 미리 알 수 있는 알고리즘을 구글은 갖고 있음.
 - data analyzer 에 기반함.

# History-Based Harvesting of Spare Cycles and Storage in Large-Scale Datacenters
* Yunqi Zhang, University of Michigan and Microsoft Research; George Prekas, École Polytechnique Fédérale de Lausanne (EPFL) and Microsoft Research; Giovanni Matteo Fumarola and Marcus Fontoura, Microsoft; Inigo Goiri and Ricardo Bianchini, Microsoft Research

batch 작업을 취소하지 않도록.
질문:
 - cpu만 고려되어 있지만, 다른 종류도 같은 방식으로 최적화 할 수 있음

# DQBarge: Improving Data-Quality Tradeoffs in Large-Scale Internet Services
* Michael Chow, University of Michigan; Kaushik Veeraraghavan, Facebook, Inc.; Michael Cafarella and Jason Flinn, University of Michigan
