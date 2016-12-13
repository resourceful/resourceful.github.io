---
layout: post
title: "OSDI 2016 Tech Session Cloud Systems I"
subtitle: "Day1 Tech session 2"
date: 2016-11-02 10:50:00
author: "Seongjin Lee"
comments: true
---

Cloud Systems I

Session Chair: Michael Kaminsky, Intel Labs


# Altruistic Scheduling in Multi-Resource Clusters
* Robert Grandl, University of Wisconsin—Madison; Mosharaf Chowdhury, University of Michigan; Aditya Akella, University of Wisconsin—Madison; Ganesh Ananthanarayanan, Microsoft

질문:
- 무임승차가 가능한가?


# GRAPHENE: Packing and Dependency-Aware Scheduling for Data-Parallel Clusters
* Robert Grandl, Microsoft and University of Wisconsin—Madison; Srikanth Kandula and Sriram Rao, Microsoft; Aditya Akella, Microsoft and University of Wisconsin—Madison; Janardhan Kulkarni, Microsoft

match tasks to resources = 쉽지 않아서 관련 연구들이 많음

graphine 은 오래걸리는 작업을 먼저 할당하여 실행함

troublesome 작업의 정의 fragmentation score vs task duration.

transitivel closure.

troublesome 작업 먼저 부모, 자녀, 형제 나중에.

질문:
-


# Firmament: Fast, Centralized Cluster Scheduling at Scale
* Ionel Gog, University of Cambridge; Malte Schwarzkopf, MIT CSAIL; Adam Gleave and Robert N. M. Watson, University of Cambridge; Steven Hand, Google, Inc.


-load



# Morpheus: Towards Automated SLOs for Enterprise Clusters
* Sangeetha Abdu Jyothi, Microsoft and University of Illinois at Urbana–Champaign; Carlo Curino, Ishai Menache, and Shravan Matthur Narayanamurthy, Microsoft; Alexey Tumanov, Microsoft and Carnegie Mellon University; Jonathan Yaniv, Technion—Israel Institute of Technology; Ruslan Mavlyutov, Microsoft and University of Fribourg; Íñigo Goiri, Subru Krishnan, Janardhan Kulkarni, and Sriram Rao, Microsoft

명료하게 토크를 진행했음

operator 와 user의 입장 차이
운영자는 활용도를 원함. 사용자는 predictability 를 원함 약 25%가 예측불가함에 대한 불만을 표현함. 해결하는 방법으로는 현재 overprovisioning을 하고 있음. 75%가 overprovisioning을 하고 있음

linear program으로 예측함.
