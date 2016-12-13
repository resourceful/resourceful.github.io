---
layout: post
title: "Application Managed Flash (FAST'16)"
subtitle: "NVRAMOS'16 day1 Tech session 1-1"
date: 2016-10-20 14:30:00
author: "Seongjin Lee"
comments: true
---


이성진 교수 인하대
http://csl.inha.ac.kr
application managed flash

FTL is a root of evil
interoperability 문제
* resource 증가
* I/O 증가
* 동작 속도를 예측할 수 없음

FTL 최적화 하기에는 정보가 적다
custom interface를 추가
data separation 을 위한 hw 사용
표준화도 어렵고 기능이 추가 되면 ftl은 더 복잡해진다
기능을 더 많이 넣으면 hw복잡도 는 증가 -> 제조사는 값 비싸게 팔 수 있지만,
복잡도는 증가되는 쪽으로 흐름

기능을 자세히 보면 ftl의 대부분의 기능은 쓰지 않아도 된다.
* 관리의 중복 -- log-structured host application -- hw 가 동시에 동작
* 불필요한 동작 발생,
* 리소스 낭비가 된다


관리 중복
* log-structured file, cow  일반적인 현상
* key value store - lsm-tree
* storage virtualization
* databases
: app 이 이미 ftl의 동작을 하고 있다

app이 ftl의 작업을 대신한다면?
AMF 의 등장


amf: light-weight ftl + log-structured host app
약간만 수정하자




AMF block I/O : log-structured 방식의 쓰기 + trim + no overwrite
: sequential 이니 ftl의 동작이 매우 단순해 진다.

* segment level address remapping
* wear-levling bad-block

1300 라인 수정 alfs
f2fs checkpoint - out-of place update
no obsolete page - no garbage collection


hw에서 mapping table 갱신하는 경우 ftl다룸
nvme 에 porting 중 - interface에서 처리해야 하는 오버헤드 있어서 성능 다 못쓰는 문제

gc할 때  page cache hit ratio 큼 메모리가 충분히 크다고 봄
