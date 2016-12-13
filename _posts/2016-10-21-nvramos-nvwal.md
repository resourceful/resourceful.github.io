---
layout: post
title: "NVWAL: Exploiting NVRAM in Write-Ahead-Logging (ASPLOS'16)"
subtitle: "NVRAMOS'16 day2 Tech session 4-2"
date: 2016-10-21 16:00:00
author: "Seongjin Lee"
comments: true
---

Bumseok Nam
(UNIST)

http://www.ece.cmu.edu/calcm/asplos2016/program.html

http://dl.acm.org/citation.cfm?id=2872392&dl=ACM&coll=DL&CFID=854955182&CFTOKEN=35510588


H/W+OS+DB의 개선
* byte-granularity differential logging
* User-level heap management for Write-Ahead-Logging
* transaction aware lazy synchronization


wal in nvram : storage에 저장하는 것보다는 더 빠르게 성능 개선됨
Differential logging은 log 데이터에서 바뀐부분만 찾아서 저장하자는 개념
HEAPO영역에 큰 영역을 할당을 미리 받아 놓아서 데이터를 logging

trie-status 를 사용하여 free-pending-in_use 의 flag를 저장하도록 하여 heapo 에서의 데이터 consistency를 관리한다.

transaction aware lazy synchronization
fsync 대신 clflush를 사용하도록 변경한 것
memcpy -> memory barrier -> cache line flush -> persistent barrier -> commit 순으로 동작해야 순서를 보장할 수 있다.

clflush를 꼭 사용하지 않아도 되는 케이스: cpu가 연산의 순서를 인식한 경우

이를 이용하여 clflush를 늦게 내려서 성능을 개선할 수 있게 된다.


optimal한 상황을 평가하기 위해서 clflush가 없앤 구조도 개발하여 성능평가 함.

lazy clflush를 하게 되면 그 수가 줄어 들어서 성능이 개선됨

_nvram의 쓰기 성능을 줄이더라도 app은 성능 차이를 크게 체감하지 못한다._

Mascots 에 노삼혁 교수님도 비슷하게 app은 성능차이를 못 본다는 논문을 소개함


Failure-atomic slotted paging for nvram

slot header 개선
* record content area 를 nvram에 적자
