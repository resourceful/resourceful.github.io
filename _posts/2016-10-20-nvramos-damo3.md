---
layout: post
title: "Flash memory for automotive"
subtitle: "NVRAMOS'16 day1 at DAMO session 3"
date: 2016-10-20 14:00:00
author: "Seongjin Lee"
comments: true
---


이성우 대표
http://elixirflash.com

Flash memory for automative

차량용 NAND

온도
* 직사광선 노출안됨 저장온도 : 85'c 동작 온도 75'c
* 노출근처: 95'c 85'c
* 노출: 115'c 105'c

dashboard 위치 는 -20'c 에서 85'c

단, 온도 증가에 따라 retention 문제가 더 커짐
55'c 에서 6.5배 증가
85'c 168배 증가
1달 내 데이터는 깨지게됨


AEQ-Q100 표준 차량용 데이터 저장관련 내용
실험 방법
high temp data retention: 150'c bake 40hr
high temp operating life: 90'c R/W for 408 hr or 70c R/W for 1000hr

현대차가 메모리 단품 테스트를 최초로 했음
그러나 다른 회사들은 테스트된것 받을 께 했지만,
실제 플래시의 신뢰성 문제를 인식하기 시작함
메모리 테스터를 만들고 있는 eftech

S-SDcard 나 T-SDcard 만 신뢰할 수 있는 제품을 만들고 있으니 그 제품 recommend

네비게이션 : eMMC + wince를 씀 linux 거의 없음
일반적 저가 형 : mlc nand + sw ftl + Wince
FTL 펌웨어 갱신하는 과정에 평가 하는 사람 없으므로 문제가 생길 여지가 있음
낸드와 ftl은 서로 상관관계가 높은데 생각없이 ap 제조회사가 만든 ftl로 갱신하는 경우의 문제
책임 소재가 불분명함



산업용 로봇 시장 으로 인한 새로운 시장
* open automotive alliance
* ABB industrial robot
* apple's carplay
* softback pepe


스토리지 단품 판매하는 기관에서 평가한 결과를 그것을 사용하는 회사에서 믿을 수 있는지

남은 erase cycle 평가 방법--
에러 비트 발생 유무 / erase cycle 조합 / 고온에서 비트 힐링되는 정도를 보고 계산하는 듯
