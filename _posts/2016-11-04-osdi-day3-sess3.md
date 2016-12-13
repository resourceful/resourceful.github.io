---
layout: post
title: "OSDI 2016 Tech Session Operating Systems II"
subtitle: "Day3 Tech session 3"
date: 2016-11-04 14:00:00
comments: true
---

Westin Aqua Star Restaurant - buffet lunch
2:00 pm–3:20 pm
Operating Systems II

Session Chair: Gernot Heiser, NICTA and University of New South Wales

# CertiKOS: An Extensible Architecture for Building Certified Concurrent OS Kernels
* Ronghui Gu, Zhong Shao, Hao Chen, Xiongnan (Newman) Wu, Jieung Kim, Vilhelm Sjöberg, and David Costanzo; Yale University

질문:
 - 문제가 되는 pattern of concurrent
 - implication for hw/sw designer
 - preemption - 없어도 그렇게 문제가 안되었지만, 관련 연구들이 있음.


# EbbRT: A Framework for Building Per-Application Library Operating Systems
* Dan Schatzberg, James Cadden, Han Dong, Orran Krieger, and Jonathan Appavoo, Boston University

질문:
 - 무엇을 라이브러리화 할지 정하는 것이 어렵나? 프로파일이 필요함



# SCONE: Secure Linux Containers with Intel SGX
* Sergei Arnautov, Bohdan Trach, Franz Gregor, Thomas Knauth, and Andre Martin, Technische Universität Dresden; Christian Priebe, Joshua Lind, Divya Muthukumaran, Dan O'Keeffe, and Mark L Stillwell, Imperial College London; David Goltzsche, Technische Universität Braunschweig; Dave Eyers, University of Otago; Rüdiger Kapitza, Technische Universität Braunschweig; Peter Pietzuch, Imperial College London; Christof Fetzer, Technische Universität Dresden

이 논문도 enclave 를 활용함

lock free data structure의 중요성을 보여줌



# Coordinated and Efficient Huge Page Management with Ingens
* Youngjin Kwon, Hangchen Yu, and Simon Peter, The University of Texas at Austin; Christopher J. Rossbach, The University of Texas at Austin and VMware; Emmett Witchel, The University of Texas at Austin

TLB 접근은 비쌈 - 가상화 시스템을 사용하면 더 비용이 큼

그래서 2MB page 를 사용하자는 주장임
주소변환 비용이 낮아짐, hw에서 sw로 해결의 책임이 바뀜

REDIS, tokudb 등 모두 huge page를 쓰지 않음
왜?

page fault latency
4kb page : 3.6 us
2mb page : 378 us -> page zeroing 이 느림

page fragmentation도 문제가 됨
리눅스는 컴팩션을 하여 연속적으로 페이지들을 만들기 위해 복사를 하지만, 페이지폴트가 발생함

ingens 방식은
page fault allocates base page - bit vector를 만듬 - page compaction in background

memory bloating - internal fragmentation
spatial utilization based allocation

질문:
 - 리눅스는 greedy - ingens는 하락의 정도를 나타냄
