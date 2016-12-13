---
layout: post
title: "OSDI 2016 Tech Session Potpourri"
subtitle: "Day2 Tech session 3"
date: 2016-11-03 14:00:00
author: "Seongjin Lee"
comments: true
---

2:00 pm–3:20 pm
Potpourri

Session Chair: Sam H. Noh, UNIST (Ulsan National Institute of Science & Technology)

# EC-Cache: Load-Balanced, Low-Latency Cluster Caching with Online Erasure Coding
* K. V. Rashmi, University of California, Berkeley; Mosharaf Chowdhury and Jack Kosaian, University of Michigan; Ion Stoica and Kannan Ramchandran, University of California, Berkeley

동영상으로 촬영된 발표를 함, 저자인 rashmi는 출산으로 참석할 수 없었음.

selective replication + ec-cache(erasure coding) = load balance + read performance

erasure coding이 중복이 되어 있기 때문에 총 K개를 읽어야 할 때 델타개 만큼 더 읽기를 요청을 하고, 먼저 도착한 K개만 읽으면 성능도 높일 수 있고 로드의 균형을 얻는다는 개념

질문:
- read는 추가가 있지만 전체 성능은 좋아진다. erasure coding의 성질활용
- imutable 에 더 적합한 기법임
- 생성된 데이터의 encoding 의 오버헤드는 10-30% 정도 됨
- alluxio 가 use case임 1mb이상의 데이터에 적합함





# To Waffinity and Beyond: A Scalable Architecture for Incremental Parallelization of File System Code
* Matthew Curtis-Maury, Vinay Devadas, Vania Fang, and Aditya Kulkarni, NetApp, Inc.

commercializing the file system.
발표자인 mathew의 생일임

1994에 wafl에 만들어짐, single thread 였기 때문에 serialization이 필요없었음. 병렬화를 위해서는 락이 필요하여 코드가 수정되어야 함

그 변경을 소개함 - incremental parallelization - 필요에 따라 병렬화의 수준을 증가하여 성능을 개선함. 개선의 순서는 다음과 같음
* classical waffinity 2006
* hierarchical wafiinity 2011
* hybrid waffinity 2016

메타데이터 변경을 하는 벤치마크인 SFS2008으로 평가함
classical wafl은 scale 되지 않음, single thread 이기 때문

질문:
- 20 core 이상을 지원함, 얼마나 더 지원 할지? 메시지 병렬화가 핵심임
- 락 대신이 큐를 사용함, 완료된 것을 어떻게 알지? ordering은 없음 first come first serve접근함


# CLARINET: WAN-Aware Optimization for Analytics Queries
* Raajay Viswanathan, University of Wisconsin—Madison; Ganesh Ananthanarayanan, Microsoft; Aditya Akella, University of Wisconsin—Madison

여러 데이터 센터의 정보를 분석하는 기법이 필요함

한 데이터 센터로 모을 수 있겠지만, 이동하다보면 성능을 20Mbps밖에 못 얻을 수 있음

여러 데이터 센터를 하나의 논리적 데이터 센터로 이해하면 어떨까?
distributed storage layer를 둠. 이미 비슷한 기법들이 있음

WAN Aware Query Optmization이 필요함
쿼리 처리를 위해서는 네트워크의 속도를 고려해야 한다고 주장함.





# JetStream: Cluster-Scale Parallelization of Information Flow Queries
* Andrew Quinn, David Devecsery, Peter M. Chen, and Jason Flinn, University of Michigan

sources (input) -> sinks(outputs)
DIFT

forward path -> mark and sweep -> backward path 로 결과를 얻기 위한 location만 선택

질문:
 - forward path에서 90-95% of the nodes are removed
