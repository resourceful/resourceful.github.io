---
layout: post
title: "Biscuit: A Framework for Near-Data Processing of Big Data Workloads (ISCA'16)"
subtitle: "NVRAMOS'16 day2 Tech session 3-1"
date: 2016-10-21 13:30:00
author: "Seongjin Lee"
comments: true
---

Duckho Bae
(Samsung Elec.)

http://isca2016.eecs.umich.edu/index.php/main-program/

http://isca2016.eecs.umich.edu/wp-content/uploads/2016/07/3A-1.pdf

http://ieeexplore.ieee.org/document/7551390/

* smart SSD 1.0 : gc -> ssd
* smart ssd2.0  : smart stream
* smart ssd 3.0 : ssd 내에서 사용자 응용 실행 (energy+, perf+)

in-storage processing
storage server + processing server에서 융합가능함

* 최초의 near processing devices
* C++ support, library 제공

인터페이스 : PCIe
arm processor 추가했고, Biscuit에서 사용함 그러나 제약 사항이 존재한다.
* low compute power
* no cache coherence
* small amount of fast memory
* no mmu
* restrictive synchronization primitives


공유를 하지 않고 I/O port로 데이터 전송하도록 했다.
Dynamic loader 를 지원한다.

cpu 마다 hw pattern matcher가 있다

data flow model : intensive I/O workload

workload 를 task 단위로 쪼개서 일을 한 후 다음 isc 에 완료한 task를 전달함

ssd 동작을 정의한 바이너리를 biscuit 적용된 ssd에 복사하고 응용에서 사용할 코드를 ssd에 복사하면 ISC를 사용할 수 있다.



sql filtering 하기에는 용도가 제약받을 수 있다는 생각에 대해서 compression + dedup 도 하면 성능은 낮아지기 때문에 개별 HW를 써야 성능 문제를 해결할 수 있을 것으로 본다. 
