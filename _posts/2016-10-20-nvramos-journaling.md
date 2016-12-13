---
layout: post
title: "Reducing Journaling Harm on Virtualized I/O Systems (MSST'16 + Systor'16)"
subtitle: "NVRAMOS'16 day1 Tech session 1-2"
date: 2016-10-20 14:40:00
author: "Seongjin Lee"
comments: true
---



이은지 교수 충북대
https://sites.google.com/site/oslabcbnu/

reducing journaling harm on virtualized I/O systems

msst16+systor16

host cache journal data 를 쓸 이유가 없다 왜냐면 locality가 없기 때문이다.
그리고 journal data 가 cache 에 유용한 데이터를 밀어 내는 경우도 생길 수 있다

Fadvise call을 사용하여 virtualization app에서 journal data와 같은 것을 cache 하지 말아라 라고 알려주는 기능이 있음
현재는 virtualization software는 cache 하지 말라는 기능이 없음.


## reducing write amplification of flash
workload and waf의 관계 random:seq=1:9 까지도 waf는 매우 큼
