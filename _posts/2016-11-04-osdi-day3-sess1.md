---
layout: post
title: "OSDI 2016 Tech Session Security"
subtitle: "Day3 Tech session 1"
date: 2016-11-04 09:00:00
author: "Seongjin Lee"
comments: true
---


9:00 am–10:20 am
Security

Session Chair: Shan Lu, University of Chicago

# Ryoan: A Distributed Sandbox for Untrusted Computation on Secret Data
* Tyler Hunt, Zhiting Zhu, Yuanzhong Xu, Simon Peter, and Emmett Witchel, The University of Texas at Austin

remote services are useful but trusting them(their os or hypervisor) is hard

sandbox를 활용하여 보완 확보

thread model
-user don't trust service providers for secrecy or platform

module + platform + sandboxes(user level)

SGX
- enclaves - region of a process's virtual address space that can only be accessed by enclave code
- sgx :trusted computation on secret data

NaCl modules call sandbox

don't let modules to carry state
 - initialize -> read -> process -> write -> delete

 ryoan - removes system calls

 25 second to initialize + 0.1 seconds to process a request => checkpoint로 해결

 질문:
  - defie hellman 사용
  - control channel attacks- hardware 해야 함 sw 로 하면 너무 느려 의미 없음



# Unobservable Communication over Fully Untrusted Infrastructure
* Sebastian Angel, The University of Texas at Austin and New York University; Srinath Setty, Microsoft Research

message는 encryption 을 할 수 있지만 누가 누구와 통신한다는 metadata는 감출 수는 없다.
관련 연구는 많음 - tor(usenix 04), vuvuzela(sosp'15), Dissent (ccs'10)

many users + full infrastructure = pung
- provably hides metadata even if infrastructure compromised

put+get in combination leaks metadata

bucket / one query for all buckets / return only the wanted message using aliasing



# Alpenhorn: Bootstrapping Secure Communication without Leaking Metadata
* David Lazar and Nickolai Zeldovich, MIT CSAIL

content privacy + metadata privacy

forward secrecy

users must exchange keys out of band : challenge

anytrust-ibe(without key lookup) + key wheel

누구의 키를 가져가는지의 정보를 감추기 위해서는 lookup 을 하면 안된다. 그렇다고 모든 키를 다 다운받을 수도 없다.

private key generator 를 사용할 수 있지만 이 자체가 compromise가 되면 문제가 될 수 있음.

메시지를 encrypt를 하고 broadcast를 함. 라운드 마다 키를 재생성. 예전 것은 버림.

데모가 인상적임 coq 보안-증명 기법에 대해 처음 봄
https://en.wikipedia.org/wiki/Coq



질문:
 - 메일박스 개념을 사용하여 사용자가 늘어나도 broadcast 비용이 늘어나지 않도록 함.


## summary of Alpenhorn

Alpenhorn(알펜호른)의 사전적 의미: Alps 산중에서 목동 등이 쓰는 긴 나팔.(또는 álphòrn)

사용자간에 통신 세션을 만드는 과정에서는 먼저 통신하고자하는 상대방의 public key infrastructure(PKI)를 통해 public key를 획득한 후 디피-헬만과 같은 키 교환 프로토콜로 세션에 사용될 키를 생성한다. 생성된 키와 public key를 통해 사용자의 신원을 확인하는 방식을 사용해왔다.

기존 방식에서 상대측의 public key를 읽어오게 되면 그 자체로 이미 누구와 통신을 시도하는지에 대한 메타데이터가 노출이 된다. 어떤 식으로든 들키지 않고 public key를 획득했다하더라도 메타데이터 forward secrecy 를 해결하지는 못한다. 디피-헬만과 같은 키 교환 프로토콜은 전달하는 메시지에 사인을 하기 때문에 통신에 누가 참여하는지 알 수 있게 된다.

이와 같은 문제를 해결하는 방법으로 strawman 해법이 있기는 하다. 이 기법은 상대방의 pubic key로 메시지를 암호화하고 그 메시지를 브로드캐스트는 하는 방식이다. 공격자는 이때 메시지가 누구를 향한 것인지 알기 어렵게 된다. 하지만 이 기법은 성능상의 문제 뿐만 아니라 forward secrecy가 보장되지 않는다. 사용자의 private key를 어떤 식으로든 획득하게 되면 과거 뿐만 아니라 앞으로의 메시지도 모두 읽을 수 있게 되기 때문이다.

알펜호른에는 3가지 주요 아이디어가 있다.

1. 알펜호른은 각 사용자마다 연락할 수 있는 친구들의 주소록을 갖고 있다.  이 주소록에는 사용자의 각 친구들과 개별적으로 공유되는 pairwise secret이 저장되어 있다.

2. 처음으로 주소록에 친구의 정보를 저장하면 알펜호른은 친구의 정체를 알 수 없도록 identity-based-encryption(ibe)을 사용하여 개인적으로 친구의 public key를 얻는다. 친구의 주소를 주소록에 저장하려면  identity-based-encryption(IBE) 를 사용한다. 기존 public key와 IBE가 다른 점은 사용자의 이름과 이메일, 어떤 서버의 마스터 public key 의 조합으로 된 수학 함수라는 것이다. 그렇기 때문에 친구의 public key를 얻기위해 그 친구의 신분이 노출될 염려가 없다. IBE를 사용하여 메시지를 암호화를 한 후 메시지를 상대에게 전달하려면 메시지를 브로드캐스트 한다. 통신하려는 경우에만 브로드캐스트를 하면 통신하려는 정보가 노출되기 때문에 모든 사용자가 통신을 하고 있지 않더라도 모두 브로드캐스트하는 방식을 택하였다. 매 라운드 마다 모든 사용자가 브로드캐스트한다. 이 때 forward secrecy를 보장하기 위해서 각 라운드 끝에 각 라운드의 private key를 삭제 한다. 브로드캐스트하게 되면 사용자가 많아질 수록 메시지의 수가 급격히 늘어나게 되므로 저자들이 이전에 발표한 mixnet 기법을 사용했다. mixnet은 한 라운드가 8mb의 크기가 되도록 제한한다. 자세한 내용은 해당 논문을 참고.



3. 실제 통신하려는 순간에 프라이버시와 forward secrecy를 보장해야 한다. 친구에게 연락하면 알펜호른은 사용자와 교신 상대에 대한 메타데이터의 forward secrecy를 보장하기 위해서 keywheel 구성 기법을 사용하여 일정 시간마다 키값이 변경되도록 한다. keywheel 구성 기법은 사용자의 주소록에 있는 shared secret 정보를 지속적으로 변경시켜서 어느 순간에도 forward secrecy를 지킬 수 있도록 하면서, 동시에 통신하는 두 명의 사용자가 서로 같은 secret value를 갖도록 한다. keywheel에서는 각 라운드의 shared secret key에 HMAC-SHA256을 적용하여 얻은 값이다. 




# Big Data Analytics over Encrypted Datasets with Seabed
* Antonis Papadimitriou, University of Pennsylvania and Microsoft Research India; Ranjita Bhagwan, Nishanth Chandran, and Ramachandran Ramjee, Microsoft Research India; Andreas Haeberlen, University of Pennsylvania; Harmeet Singh and Abhishek Modi, Microsoft Research India; Saikrishna Badrinarayanan, University of California, Los Angeles and Microsoft Research India


중요한 정보를 db에서 다 encrypt하면 encypt없는 데이터에 대비 3000x 성능 하락이 있음.

ASHE와 SPLASHE 기법을 SEABED라는 기법으로 통합함

성능:  ASHE
aggregation이 느림 --> db의 값들을 더하려면 decrypt한 후 작업해야하므로 느림
homomorphic addition이 있으나 비용이 매우 비쌈.

ASHE : additive symmetric homomorphic encryption 을 사용하여 row 값을 사용하는 pseudo encryption function 으로 계산. 그래도 성능이 느린것은 암호화 전용 hw를 사용하고 압축을 통해 용량을 줄임

security: SPLASHE


질문:
 - 곱셉은 가능한가? 다른 기법들이 있기는 했지만 비효율적이라 사용하지 않음. 제한된 연산만 지원한다.
 - key + pseudo random function 이기 때문에 보완 문제 없음 key는 사용자에게만 있음
