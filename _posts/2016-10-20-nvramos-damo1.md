---
layout: post
title: "gcube - software defined storage"
subtitle: "NVRAMOS'16 day1 at DAMO session 1"
date: 2016-10-20 13:30:00
author: "Seongjin Lee"
comments: true
---

Talk by Dongin Shin, CTO http://g-cube.kr/?lang=ko


There are more than 30 companies that they claim to work on software defined storage (SDS). But, all uses different definitions---there are more than 300 different definitions of SDS in the web.

GCUBE's definition of SDS
* _스토리지 컨트롤러 펌웨어를 가져와 리눅스에서 가상 머신으로 실행한다_
* _스토리지 어레이를 범용 서버 하드웨어에서 실행한다_

They try to distinguish data plane and control plane of storage system to improve the performance. Use some of the computation power to manage the storage system.

Some of the other efforts are to optimize the openstack object store. They added compressiong for small sized chunks, and use deduplication mechanism (rabin finger printing).


One of the question they recieved in the talk was how are they surviving. Their answer was "주경야경", work day and night, attract and receive investments, develop the products that sell.

The other question was about workload characteristics that works well for deduplication. They didn't have a answer for the question, they were looking for it.
