---
layout: post
title: "SSD & PCIe 스트리지 시스템의 변화"
subtitle: "NVRAMOS'16 day1 at DAMO session 2"
date: 2016-10-20 13:50:00
author: "Seongjin Lee"
comments: true
---


# gluesys
http://gluesys.com

김경훈 기술 연구소장,


Storage environment is changing. There are different laws that describe the changes and growth.

* Moore's law
* Hwang's law
* Gilder's law
* Metcalfe's law

storages are increasing in its volume, speed, and variety.

Storage mediums also changed from HDDs to SSDs, and they are moving to NVRAM. In terms of the price and the volume, HDD is still the best. But, the SSD is catching up in two different categories. SSDs using PCIe as the interface targets performance and using SATA as the interface targets capacity.

They made a point that faster storage hierarchy requires optimization of the I/O stack.


스토리지 아키텍처의 변화
* 하드웨어+전용 인터페이스를 갖고 있는 회사와 경쟁할 수 없었으나 이제는 표준화된 고속의 인터페이스의 등장으로 경쟁력 갖는 회사들이 생겨남

loosely coupled storage : 고성능의 이더넷 기반 스토리지 ceph, luster

pci hw chip은 있으나 소프트웨어 스택은 없음- 소규모회사의 어려움

미래로는 hyper converged -- 안정적인 스토리지 + 안정적 서비스 보장해주자
현재는 NAS를 주력으로 판매 중 + 백업 소프트웨어
몇십테라의 용량
nvme pcie를 관리하는 계층이 없음, 연구 대상임
