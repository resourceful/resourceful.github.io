---
layout: post
title: "SHARE Interface in Flash Storage for Relational and NoSQL Databases (SIGMOD'16)"
subtitle: "NVRAMOS'16 day2 Tech session 3-2"
date: 2016-10-21 14:10:00
author: "Seongjin Lee"
comments: true
---

Sangwon Lee
(SKKU)

http://sigmod2016.org/sigmod_research_list.shtml

http://dl.acm.org/citation.cfm?id=2882910

copy-on-write in forestDB 에서 snowball problem을 share 로 해결


anvil 과 매우 닮았다.

Logical 2 Physical layer에서 physical 정보를 공유 할 수 있는 메카니즘을 제공하였다.

swap + trim 을 합한 swat이라는 이름으로 만들려다가 share라는 이름이 더 적합하고 부드러운 어감이라서 선택되었다고 함

openssd에 적용하여 실험한 성능 결과이다.

JFTL -> specific to FS journaling and metadata

X-ftl -> in-place update 하여 중복도 제거, share는 out-of-place에서 중복 제거 함. ftl도 app 에서도 많이 바뀌어야함


anvil 은 block layer에서 적용함 random write에 한계가 있지 않을가? 함


trim 보다는 약간 더 복잡하겠지만, 아주 복잡한 것은 아니라서 써도 문제 없지 않을까? 함



share-based application crash consistent file system

새로운 share라는 programming interface를 사용하여 중복 제거하는 기법을 openssd를 사용하여 검증해봤다는 것이 새롭다 할 수 있다.
