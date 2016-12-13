---
layout: post
title: "OSDI 2016 Tech Session Troubleshooting"
subtitle: "Day3 Tech session 2"
date: 2016-11-04 10:50:00
author: "Seongjin Lee"
comments: true
---


10:50 am–11:50 am
Troubleshooting

Session Chair: Jeff Chase, Duke University

# Non-Intrusive Performance Profiling for Entire Software Stacks Based on the Flow Reconstruction Principle
* Xu Zhao, Kirk Rodrigues, Yu Luo, Ding Yuan, and Michael Stumm, University of Toronto

debugging is difficult

programmer's intuition -- execution flow를 알아내기 위해 로깅을 함, 어디에 어떤 문제가 있는지 알아 내기 위해 다양한 정보를 추가해야 함

시간, 프로세스 id , thread 1 등의 정보를 추가해야 함.
thread, process 의 동작 정보는 로그에서 순서에 어긋나게 섞여 저장됨

여러 노드의 정보를 stitch 하기 위해서 서버에 정보를 전달함 그리고 그 안에서 visualization과 flow 분석을 함

bottom-up : goose chase

사용자의 task가 어디서 얼마나 오래 걸리는지 visualization 을 해줌.

n:m relationship을 파악해내는 것이 어려운 일임
모든 관계가 다 유용한 것은 아니기 때문.

질문:
 - 어떤 종류의 디버그를 찾나? latency of request를 찾음. 성능에 대해서는 추가 작업을 하여 예측을 할 수 있을 듯 함
 - 무엇을 볼지는 어떻게 알지? object hierarchy를 관리


# Early Detection of Configuration Errors to Reduce Failure Damage
* Tianyin Xu, Xinxin Jin, Peng Huang, and Yuanyuan Zhou, University of California, San Diego; Shan Lu, University of Chicago; Long Jin, University of California, San Diego; Shankar Pasupathy, NetApp, Inc.

award paper

configuration error를 다루는 논문
코드 자체에는 에러가 없다는 가정
설정파일이 잘못되어 프로그램의 오동작을 일으키는 경우를 다룸

에러가 발생한 이후에 미안하다고 하는 것은 너무 늦다.
configuration은 미리 미리 체크해서 실수가 없게 동작할 수 있도록 할 수 있다

initialization -> rollout -> workload -> error
configuration 은 error 고치는 단계에 가면 치명적이게 된다.
하지만 latent configuration error를 찾는 것은 정말 어렵다.


5-39%가 latent error를 포함하고 있음

production에 사용하는 configuration code를 initialization 부분에 넣어서 되는지 검증하자. 단 컨텍스가 없기 때문에 초기화 할 때 실행이 제대로 되지 않는다.

sandbox the checking code 로 검증을함

pcheck가 작업을 함
 원래 프로그램 + configuration -> 분석 (extract instruction, context 생성,) -> output (check)

 70%정도의 에러를 없앨 수 있었음.
 에러 타입: type/format은 100%, invalid option 100%, 좀 더 잘 못하는 것도 있음

long running time 을 통해 생기는 문제는 짧은 시간에 찾으려는 이 기법에서는 판단 불가


질문:
 - silent errors 는 찾을 수 있을가? 그런 부분은 고려안함
 - inter-procedure analysis 를 함


# Kraken: Leveraging Live Traffic Tests to Identify and Resolve Resource Utilization Bottlenecks in Large Scale Web Services
* Kaushik Veeraraghavan, Justin Meza, David Chou, Wonho Kim, Sonia Margulis, Scott Michelson, Rajesh Nishtala, Daniel Obenshain, Dmitri Perelman, and Yee Jiun Song, Facebook Inc.


5 datacenter 가 있음 미국x4 유럽x1
newfeed를 만들기 위해서 매우 많은 서비스를 운용중이고, 각 서비스는 수시로 갱신도 된다.

live user traffic is the most representative workload
accurate distribution reads & writes

kraken으로 direct live user traffic at target

monitor health metrics
  - response latency
  - server error

reset load when thresholds are hit

live user정보만으로 특정 일의 필요한 용량을 예측할 수 있도록 함

질문:
 - live traffic -> election day, how to extrapolate : head room, prediction을 할 수 있음. 각 장비의 성능을 구체적으로 파악할 수 있었음
 - 다양한 investigation tool 을 사용하여 분석함
