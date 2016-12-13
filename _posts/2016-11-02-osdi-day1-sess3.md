---
layout: post
title: "OSDI 2016 Tech Session Transactions and Storage"
subtitle: "Day1 Tech session 3"
date: 2016-11-02 14:00:00
author: "Seongjin Lee"
comments: true
---

Transactions and Storage

Session Chair: Dan Ports, University of Washington

# The SNOW Theorem and Latency-Optimal Read-Only Transactions
* Haonan Lu, University of Southern California; Christopher Hodsdon, University of Southern California; Khiem Ngo, University of Southern California; Shuai Mu, New York University; Wyatt Lloyd, University of Southern California

분산 데이터를 빨리 읽는 방법에 관한 논문
읽기가 약 80%가 됨

병행적으로 갱신되면 읽기가 쉽지 않음.

성능을 개선하려면 지연시간을 줄이는 사이에 경쟁이 존재한다. 지연시간을 줄이려면 돈이 든다.

SNOW의 성질
* Strict serializability--강력한 모델: real-time + total order
* Nonblocking operations
* one response
* write transaction

snow를 모두 지키는 것은 불가능 함 - 선택을 해야 함

개선을 하기 -- COPS (sosp'11) rococo(osdi'14)가 적합한 대상으로 보임

rococo 만 설명함
timestamp를 저장하고 serializability를 보장하기 위해서 그 시간을 전파함.

다른 트랜잭션에서는 다른 종류의 기법을 사용해야 함.

질문 :
- 버전을 여러개를 유지하면 (snapshot) ? realtime 으로 지원하려면 snapshot은 안됨
- 의존성이 있으면 ? offline으로 이야기 연구하지 않음
- fault가 있다면? --


# Correlated Crash Vulnerabilities
* Ramnatthan Alagappan, Aishwarya Ganesan, Yuvraj Patel, Thanumalayan Sankaranarayana Pillai, Andrea C. Arpaci-Dusseau, and Remzi H. Arpaci-Dusseau, University of Wisconsin—Madison

update protocol
reliability를 위해서는 복제를 함
만약 correlation이 있다면 ?
- 이런 케이스가 많다. 자연 재해가 많음. kernel bugs 도 이유가 됨

Pillai의 APM 논문의 연장임
PACE라는 기법을 APM에 추가함

파일 시스템의 크래시가 분산 시스템에 영향을 준다

질문:
- 체크섬으로 문제를 응용 프로그램이 해결할 수는 있음. 하지만 응용프로그램이 문제를 해결하는 것이 늘 쉬운 것은 아님.
-



# Incremental Consistency Guarantees for Replicated Objects
* Rachid Guerraoui, Matej Pavlovic, and Dragos-Adrian Seredinschi, École Polytechnique Fédérale de Lausanne (EPFL)

복제를 하는데 동시에 모두가 똑같은 데이터를 보는 것은 시간이 많이 걸리기 대문에 weak consistency를 통해 짧은 시간 동안만 예전 버전을 보이게 된다.

strong + weak consistency 를 보장하도록 하는 기법에 대한 논문
- 많은 기술들이 이와 같은 기법을 사용하고 있음

문제들
- send multiple request?
- how to leverage idividual responses
- semantics

Correctables abstraction
 - promises (scala, finagle, guava)
 - promise는 숫자 하나만 다루는데 correctable은 여러 값들을 관리함

speculative operation with ICG
실제 값을 읽어와야 하는 것과 계산한 값이 다르면 다시 읽어 오면 됨. 원래 걸리는 시간 보다 더 길지는 않음.

질문:
- write가 많으면 speculation이 많아질텐데? 하지만 그런 경우는 1% 미만




# FaSST: Fast, Scalable and Simple Distributed Transactions with Two-Sided (RDMA) Datagram RPCs
* Anuj Kalia, Carnegie Mellon University; Michael Kaminsky, Intel Labs; David G. Andersen, Carnegie Mellon University

RPC 를 사용하여 정보를 전달/요청함
성능이 RPC가 좋지 않아 많이 사용되지 않았음
rpc 는 rdma보다 4배 느림

이 기법에서 rpc를 개선함 오히려 버틀넥은 NIC였음.

예전 기법이 느린이유
- scalable transport layer를 사용하지 않음
- lock free I/O를 사용하지 않음
