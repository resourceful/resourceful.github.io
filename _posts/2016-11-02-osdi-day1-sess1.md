---
layout: post
title: "OSDI 2016 Tech Session Operating Systems I"
subtitle: "Day1 Tech session 1"
date: 2016-11-02 09:00:00
author: "Seongjin Lee"
comments: true
---


9:00 am–10:20 am
Operating Systems I

Session Chair: Margo Selzer, Harvard School of Engineeringand Applied Sciences and Oracle



# Push-Button Verification of File Systems via Crash Refinement
* best paper award No.1
* Helgi Sigurbjarnarson, James Bornholt, Emina Torlak, and Xi Wang, University of Washington
* presented by by Helgi

bug free file system
want to code not to proof
질문 :
- layers로 나눔 specification 정의
- limit: 모든 스테이트 검사가 가능한가? atomic한 것을 가정하면 가능



# Intermittent Computation without Hardware Support or Programmer Intervention
* Joel Van Der Woude, Sandia National Laboratories; Matthew Hicks, University of Michigan
email jvdw@umich.edu

ratchet

power 없이는 모든 소형 기기들을 사용못함. 교체는 비용 발생함. 전력 harvesting 을 하지만, unreliable 함

언제 다운 될지 알지 못함. h/w, s/w 등의 방법이 있음. s/w는 코드는 어떤 문제가 있을지 검증이 어려움

체크포인트 를 해 놓으면 다시 그 시점 부터 시작할 수 있음
idempotent section 을 사용하여 반복해도 문제가 없도록 한다.

Write After Read를 찾아서 idempotent가능성을 확인한다. 그리고 그 사이에 checkpoint를 삽입한다.

stack 정보가 nvm에 있는데 전원 나간 후에 다시 읽을 때 체크포인트 정보와 스택 정보가 다른 지 확인한다.

checkpoint 중복되었는지 검토하여 성능 개선

검증은 cycle accurate simulator사용, random power failures를 발생하고 war에 대한 idempotence를 검토한다.

checkpoint를 강제로 삽입하여 compiler가 처리할수 있음.

질문
interprocedural write after reads : global인지 확인해야 함. function entry를 확인하여 checkpoint 를 잘 넣어야 함

failure checkpoint : atomic 을 가정하여 buffer를 pointer를 저장

## summary of ratchet

전원이 수시로 꺼지는 소형 유비쿼터스 기기가 갖는 문제를 하드웨어 지원이나 프로그래머의 노력없이 해결하는 방법에 대한 논문이다.

모바일 디바이스의 경우 대부분의 공간을 바테리가 차지하고 있다. 바테리에대한 의존성을 줄이기 위해서 사용된 기존의 방법은 energy harvesting과 같은 기법이다.

기존에는 두가지 방식으로 intermittent computing의 문제를 해결하고 있다. 첫 째 방법은 전력이 차단되기 직전에 지금까지 하고 있었던 모든 내용을 비휘발성 메모리에 체크포인트한다. 그러나 너무 이른 체크포인트는 남은 전력을 활용하지 못하도록 하기 때문에 현재 잔여 전력이 얼마인지를 모니터링할 수 있는 특화된 하드웨어를 필요로한다. 두 번째는 프로그래머가 체크포인트 지점을 삽입하여 전력 차단에 대한 대비하는 방법이다. 체크포인트 지점을 빈번하게 삽입하면 저장하는 오버헤드가 늘어나고 너무 느슨하게 삽입하면 실행 중간에 멈추고 복구가 안되는 상황이 될 수도 있다.

이 논문의 해법은 컴파일러에 의존한다. 컴파일러가 수정되지 않은 코드를 전달 받으면 재실행가능한 단위의 코드로 구분을 하고 그 사이에 체크포인트 함수를 삽입한다. 재실행가능한 단위로 나누고 그 영역을 idempontent(멱등) 섹션이라고 부른다. 컴파일러는 비휘발성 메모리로 향한 load 또는 store를 찾아서 어떤 섹션도 같은 주소에 대한 write after read (WAR)를 포함하지 않도록 write와 read사이에 체크포인트를 삽입하여 멱등 섹션으로 만든다. 휘발성 상태들은 체크포인트하여 저장하도록 한다.

체크포인트가 consistent한 상태가 되는 것을 보장하도록 더블 버퍼링 기법을 사용한다. 한 버퍼는 이전 체크포인트 값을 저장하고 다른 버퍼는 새로운 체크포인트를 쓰는데 사용된다. 체크포인트의 커밋은 다 기록된 후 포인터 업데이트로 최신의 유효한 체크포인트로 만든다.

모든 휘발성 상태(special purpose registers와 general purpose registers)는 체크포인트 시에 저장이 되어야 한다. 컨디션 코드를 체크포인트하는 비용이 크다는 것을 실험적으로 알았기 때문에 체크포인트 코드를 컨디션 코드 수행 이후에 삽입하도록 하였다. 

복구를 하는 방법은 다음과 같다. 저장된 레지스터의 값들은 원래의 레지스터로 복원한 한다. 프로그램 카운터가 복원되면 가장 최신의 체크포인트 이후의 코드를 실행한다.

이 논문의 기법인 Ratchet은 체크포인트 복구 코드와 체크포인트 최적화 함수와 체크포인트 콜 등을 삽입하며 이로 인해 프로그램의 크기가 약 1.79% 정도 증가된다.

멱등 센션의 크기가 커질 수록 재실행 시간이 길어지게 된다.



# Machine-Aware Atomic Broadcast Trees for Multicores
* Stefan Kaestle, Reto Achermann, Roni Haecki, Moritz Hoffmann, Sabela Ramos, and Timothy Roscoe, ETH Zurich

멀티코어를 활용하여 성능 개선을 위해 어떻게 코어를 활용할까를 고민한 논문

코어가 많을 수록 topology 관리가 복잡해짐. 단, one-fit-all solution이 없음. 이 문제를 자동적으로 해결하는 기법 개발함

parallel program 에서 중요한 것은 broadcast와 reduction

smelt는 peer-to-peer message passing을 사용함. 단, network에서 사용하는 것이랑은 다름. 코어에서는  send and receive 시간이 중요함.

lscpu
numactl -hardware

send-receive time 을 측정 함. symmetric하지 않게 동작함을 보였다. 즉 코어가 각자 열심히 작업을 한다는 것을 뜻함.

smelt algorithm -> tree topology 계산
* remote core first
* avoid expensive communication
* maximize parallelism

관련 결과는 machinedb.systems.ethz.ch

좋은 것 보다 안좋은 것 하나만 왜 그런지 설명함 Bloomfield 기계가 성능이 안좋음

openmp: epcc openmp barrier


질문:
- tree topology 가 적은데, 최고의 tree는? 4개의 기술을 비교함 슬라이드 22
- topology를 설정하면 어떻게 전파하는가? peer-to-peer message 전달
- write once read many times : p-to-p기법을 잘 알고 있어서 사용함. 그 외의 기법은 미래에 연구하려고 함




# Light-Weight Contexts: An OS Abstraction for Safety and Performance
* James Litton, University of Maryland and Max Planck Institute for Software Systems (MPI-SWS); Anjo Vahldiek-Oberwagner, Eslam Elnikety, and Deepak Garg, Max Planck Institute for Software Systems (MPI-SWS); Bobby Bhattacharjee, University of Maryland; Peter Druschel, Max Planck Institute for Software Systems (MPI-SWS)

주소 공간을 isolation하는 방법에 대한 고민의 논문

fork를 사용하여 주소 공간 생성 - 스케줄링으로 주소 공간을 활용함, thread 는 isolation이 안됨

light-weight-context -lwc

session isolation - web server
sensitive data isolation
snapshot and rollback
reference monitoring

lwc 는 process context switch , k-thread  보다 반 밖에 시간이 안 걸림, 4usec 걸리는 것이 2 usec이 걸림

질문:
- 스냅샷을 재 생성하는 이유? 상태를 최신으로 유지하기 위해. 재사용하면 문제가생길 수 있음.
- tlb : tlb를 flush를 하지 않아도 쓸 수 있음.
