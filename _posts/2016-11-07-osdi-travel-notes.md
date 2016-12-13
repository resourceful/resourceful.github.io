---
layout: post
title: "OSDI 2016 Travel Notes"
subtitle: "치열한 지의 최전선에서 일주일간의 생존기"
date: 2016-11-07 21:10:00
author: "Seongjin Lee"
comments: true
---

2016년 10월 31일 부터 11월 6일까지 The Westin Savannah Harbor Golf Resort & Spa & Convention Center (1 Resort Drive, Savannah, GA 31421) 에서 열린 12th USENIX Symposium on Operating Systems Design and Implementation (OSDI '16) 학회에 참석하였다.

처음으로 동남부 지역을 방문하였다. 사바나에 대해 많은 것을 새로 알게 되었다. 이 도시는 공업이 발달되어 있고, 항구 도시이다. 공업과 항구 도시라는 것과 어울리지 않게 관광 사업이 발달되 있다. Savannah river와 little back river 사이에 Hutchinson Island가 있다. 강이지만 돌고래도 볼 수 있을 정도로 수심이 깊다. 그래서 인지 수천톤급의 화물선들이 오간다. 기억이 맞다면 3번째로 큰 항구도시라고 한다. 18시게와 19세기가 그 절정기였던 것으로 보인다. 항구가 발달하다보니 중공업 기업들의 본사들도 많이 보인다. 이름들은 못 들어본 기업들이기는 하다. 물줄기를 건너는 다리가 하나 있는데, 그 다리를 중심으로 우측은 다운타운과 관광업이 발달하였고 좌측으로는 중공업 회사들의 공장과 항구가 있다.


관광 산업이 발달한 계기는 civil war에서 찾을 수 있다. 셔먼 장군이 March to the Sea를 외치며 북에서 남으로 그리고 바닷가로 밀고 내려올 때 사바나는 폭격은 당하지 않았다. 전쟁을 포기하고 항복했기 때문이다. 항복의 조건으로 도시가 폭격을 당하지 않도록 요청을 했다. 그래서 지금도 백년이 넘는 오래된 건축물들을 볼 수 있다.

역사적 도시라는 느낌을 주려는 듯 공항에서 도시로 들아오는 차도에 홈을 파서 차가 달리는 동안 말을 타는 듯이 달그닥 하는 소리가 나도록 하였다. 대략 80KM/h 정도 달리면 그 소리가 나는 듯하다. 느리게 달리면 느린 말을 타는 듯하게 들린다.


인구는 약 13만명 정도인데 여성 비율(52.83%)이 남성 비율(47.17%)보다 약간 더 많다. 백인이 38.86%이고 흑인이나 아프리칸 아메리칸의 비율이 57.08%이다. 개인적으로는 백인을 가장 많이 본 지역이 아닌가 생각된다. Historical City, downtown을 중심으로 약 2Km를 돌아다녔는데, 종업원, 가게 주인, 호텔 직원 등 백인이 훨씬 많았다.

가장 기억에 남는 식당은 Mrs Wilkes Boarding house(http://mrswilkes.com/)였다. 그 가게는 이 지역에서 가장 오래된 식당 중에 하나로서 남부 음식을 전문으로 한다. 특징은 점심에만 장사를 한다는 것이고 현재는 손녀가 운영 중이다. 상당히 매력적이라고 생각했던 이유는 미국 남부 지역의 가정식 백반을 먹는 느낌을 줬기 때문이다. 음식이 담겨 있는 그릇들이 있으면 서로 모르는 사람들이 식탁에 앉아 나눠 먹는다. 한 über 기사에게 남부 지역에서는 그렇게 식사를 하는지 물었는데, 그렇게 생각하도록 만든거라고 한단다. 손님을 초대받은 경우 그런식으로 음식을 하는 경우가 더러 있기는 한데 지금은 그렇게 먹지 않는다고 한다.

이 지역에서 유명한 학교는 SCAD Savannah College of Art and Design이다. 도시를 걸어다니다 보면 캔버스를 들고 다니는 학생들이 많이 보인다. 학교에 있는 박물관을 가봤다. Radcliffe Bailey과 Michael Joo의 작품이 인상적이었다. 전시회가 African-America 문화에 관련한 것이라 관계된 인물들이 전시를 하고 있었다. 피아노 건반들을 마치 일렁이는 파도로 묘사를 하고 검은색 배가 아프리카를 상징하는 듯한 모형을 향해 돌진하는 가장 인상적이었던 전시물이었다. 큐레이터가 설명해주는 의미를 들어보니 Radcliffe는 피아노 건반에 집착이 있었다고 한다. 그래서 그런지 그의 모든 작품들은 피아노 건반들이 많았다. 오래된 물건들과 아프리카를 상징하는 물건들도 집에 아주 많았고 자기의 과거에 상당한 애착을 갖고 있었다고 학생 때 그와 한 방에 살았던 사람이 말했다고 한다. Michael Joo의 경우는 다루기 쉽지 않은 재료인 Silver Nitrate를 10년이나 실험하며 작품 활동을 하고 있다고 한다. Silver nitrate는 손에 묻으면 검은색으로 착색이 된다.


학회장은 Hutchinson Island에 있는 컨벤션 센터인데, 다운타운에서 학회장으로 이동을 하려면 시에서 운영하는 무료 페리선을 탈 수 있다. 오전 7시부터 8시까지는 20분단위로 그 이후부터는 30분 단위로 자정까지 운영을 한다. 페리선을 기다면서 U. TEXAS의 Lorenzo 교수를 만나 이야기했다. APSYS에 관심을 갖았으면 좋겠다고 하는 이야기가 기억에 남는다. Eurosys의 아시아 판이라고 했다. 그리고 SOSP2017은 상해에서 하는데 많은 사람들이 왔으면 했다. SOSP는 ACM계열 학회로 한번은 미국에서 한번은 해외에서 개최를 한다. OSDI는 USENIX학회인데 한번은 동부 한번은 서부에서 개최된다. 학회이야기를 많이 하길래 관련이 있는지 궁금했다. 아니나 다를까 steering committee 였다. 다른 날에 페리선에서 HP의 Kim Keeton을 만나 이야기 했을 때 Lorenzo 교수와 비슷하게 상해에서 처음 열리는 행사에 대한 걱정을 읽을 수가 있었다. 대규모 인원이 모일 수 있을지 식사는 괜찮을지 등 사소하지만 중요한 것들을 고민하고 있었다. Lorenzo 교수에게 학회의 성공여부를 어떻게 측정하느냐고 질문했을 때 기존의 community가 얼마나 참석하느냐를 보고 판단한다고 했다. 결국 사람이 모이는 학회여야 한다는 것 뿐만 아니라, 미국에서 얼마나 많은 사람들이 참석을 하느냐가 관심로 보였다.


Lorenzo 교수를 만난 날에 Cathedral of St. Johns the Baptist 에서 All Saints day 를 기념하는 미사가 있다는 소식을 들었다. 호텔에서 퇴실하고 AirBNB로 잡은 숙소로 이동하는 길에 이 정보를 들었다. 박창현, 노연진, 최경렬은 숙소 문을 열기 위해 기다리는 동안 나는 성당으로 향했다. 다행이 그리 멀지 않은 곳이었기에 미사가 시작하기 전에 도착 할 수 있었다. 여기서 새롭게 안 사실은 미사의 모든 내용이 (설교의 내용은 모르겠지만,) 미사책에 모두 날짜별로 나와 있었다. 올해의 미사의 내용과 말씀이 이미 교황청에서 배포가 된듯했다. 기독교는 모든 목사님이 개별적으로 다른 말씀을 전하는 것과 비교해서 모든 사람이 어느 성당에서든 같은 본문으로 설교를 듣는 것이 신기했다.

학회 첫날 이은지 교수님과 오전 식사하였다. 혼자 Atlanta에서 내려 운전해서 왔다는 것에 상당히 충격이었다. 둘째날 점심은 외대의 이윤석 교수님과 같은 테이블에서 식사를 했다. Stream Data 관련 연구를 하고 계신다. 엄영익 교수님 연구실의 강동현 씨를 만났다. 이 연구실은 학회에 방문하면 그 다음 해에 그 학회에 논문을 제출해야 한다고 한다. 적극적이고 새로운 논문 아이디어를 얻기 위해서 기꺼이 수백만원을 들이는 모습을 보며 새로운 자극을 받았다.

학회장에는 여러 회사들이 인재들을 모집하고 홍보하기 위한 자리를 만든다. 그 중에 google의 직원과 입사에 관한 내용을 질문하였다. google의 입사 지원은 다음과 같은 과정을 따른다.
* resume 제출
* phone interview : 관련 설명을 해주고 어떤 분야를 원하는지 물어보고, 어떤 직분이 있는지 설명을 해줌. 전반적으로 지원자에대한 정보를 얻음
* online interview (sw engineer이면 코딩 문제) about 45 min
* offline interview (sw engineer이면 코딩 문제) 5번의 interview가 있음
* hiring committee가 열려서 지원자에 대한 객관적 분석을 하고 가부를 결정함
* 입사가 결정되면 실무적인 서류작업 등이 진행된다
매우 긴 과정이기는 하지만 지원자에대한 다각적인 분석을 하기 위한 과정이라고 본다. 그리고 코딩 문제의 경우 현실적인 문제해결 능력, 읽기 쉬운 코드, 효율적인 코드, 버그 여부 등을 확인한다. 무엇보다도 학교에 있는 사람에게 중요한 것이 있다면 좋은 논문을 쓰는 것이다. 좋은 논문의 기준은 SOSP와 OSDI와 같은 학회에 적어도 한 편의 논문을 갖고 있는지의 여부로 판가름 난다. 교수님께서 늘 말씀하시듯이 좋은 논문 한 편이 연봉 일억의 가치를 한다는 말이 다시 생각 났다.

지구 반대편으로 날아오게 되면 시차가 늘 문제가 된다. 개인적으로는 시차 때문에 그렇게 고생한 적이 없다. 시차적응을 잘하는 개인적인 팁은 간단하다. 동쪽 방향으로 이동을 할 때는 역방향으로 시간이 가기 때문에 해가 더 길어진다. 미국으로 월요일에 출발을 했다면 월요일이 12시간 더 늘어나는 꼴이다. 비행기로 이동하는 사이에 짬짬히 자는 방법도 있겠지만, 너무 많이 자면 정말 자야 하는 시간에 잠이 안올 수도 있어서 생체리듬이 무너진다. 그래서 동쪽으로 이동할 때는 잠을 안자는 것이 더 좋다. 그 나라에 도착해서 그 나라에서의 잘 시간에 자는 것이 시차적응을 빨리 할 수 있는 비결이다. 반대로 서쪽으로 간다면 이동중에서 충분히 잠을 자는 것이 좋다. 만약 시차 적응을 실패하면 새벽에 일어나서 어둠속에서 활동하게 된다. 정작 낮에는 졸릴 테니 효율이 떨어질 것이다.

학회에 오는 사람 중 자기 논문을 발표하는 사람들은 논문 개수의 2배수 정도(주저자와 지도 교수 또는 다른 저자)이다. 이번 학회에는 약 40여편의 논문이 발표 되었으니, 약 100여명이 저자의 자격으로 참석하였다. 첫 날 학회측에서 발표한 참석 인원은 580여명이었다. 약 5배수 이상 되는 사람들이 동향 파악을 위해서거나 네트워크를 위해서 모였다.

Usenix OSDI의 경우 최고 수준의 학회이기 때문에 다양한 전문가들이 모인다. 이 자리에서 살아 남는 방법은 자기를 적극적으로 소개하는 것이다. 자기 자리에 앉아서 혼자 논문을 읽는 방식으로는 어울릴 수도 없을 뿐만 아니라 알아봐주지도 않는다. 여기의 사람들은 모르는 사람들에게 다가가서 무엇을 연구하는지 물어보고 서로의 관심사에 대한 정보를 공유하는 방식으로 소통한다. 비싼 돈을 주고 이런 학회에 오는 이유는 최신 최고의 기술을 가장 먼저 소개 받는 다는 것도 있겠지만, 그 기술을 소개하는 사람들과 개인적 관계를 맺을 수 있기 때문이다. 그 기회비용은 이메일로 관계를 맺는 것보다 더 가치있기 때문에 이런 곳을 온다고 생각한다.

한정된 시간에 tech session 에서 발표가 끝난 후에 질문을 하는 것도 의미가 있겠지만, 소통이라는 측면에서는 포스터 세션이 더 의미가 있는 것 같다. 포스터 세션에서 새로 알게 된 것들은 다음과 같다.

"OS Containers on Diet Using CNTR", Jörg Thalheim, Franz Gregor, Pramod Bhatotia, and Christof Fetzer, Technische Universität Dresden

* 컨테이너라는 개념은 새로운 패키지를 deploy할 때 많이 사용되는 핫한 기술이다. Jörg가 연구를 하다가 잉여 시간에 혼자 시험해본 기술이라고 한다. 컨테이너가 독립적으로 동작해야 하기 때문에 모든 라이브러리 및 프로그램들을 포함시켜야 한다. 모든 라이브러리를 포함해야 하기 때문에 용량이 커질 수가 있다는 문제를 해결하기 위해서 자신이 필요한 라이브러리들만 따로 모아서 새로운 컨테이너를 만들어 제공을 한다는 내용이었다. 컨테이너가 실제 동작하는 과정에는 불필요한 프로그램들이 추가되어 있을 때 exploitation이 가능한데, 그런 위험을 애초에 제거 할 수 있다는 내용이다. 기술 보다는 독자적인 연구를 하고 이렇게 발표를 하기 위해 왔다는 것이 고무적이었다.

"Alpenhorn: Bootstrapping Secure Communication without Leaking Metadata"
David Lazar and Nickolai Zeldovich, MIT CSAIL

* 제목에서의 메타데이터라고 하는 것은 사용자가 누구와 통신을 하고자 하는가의 정보이다. 핵심은 서버가 public key를 계속 새로 생성해서 제공하고 클라이언트는 생성된 public key를 조작하여 private key를 만든다는 것이다. 결국 처음에 말한 metadata는 완전히 숨길 수는 없지만, public key가 수 밀리초 마다 계속 바뀌기 때문에 그 외의 시간에는 메타데이터를 감출 수가 있다고 했다.

"Non-Intrusive Performance Profiling for Entire Software Stacks Based on the Flow Reconstruction Principle", Xu Zhao, Kirk Rodrigues, Yu Luo, Ding Yuan, and Michael Stumm, University of Toronto

* 사용자가 사용하고 있는 시스템의 syslog의 정보를 서버로 모아서 서버가 정보를 분석하도록 하는 시스템이다. 문제가 있다면 syslog의 정보가 유의미한 경우에만 활용했을 때만 가치가 있다는 것이다. syslog의 정보가 문제해결에 불충분하다면 서버에 모은 정보는 무의미해진다. 또한 엄청나게 많은 로그 데이터를 서버로 이동해야 한다는 문제가 있다. 그러나 자기들이 보기에는 그 데이터 이동이 그렇게 문제가 되지 않는다고 했다. 그러나 log2라는 논문에서보면 로그 데이터를 모두 쓸 수 있는 것이 아니라고 했기 때문에 그리고 로그가 모두 유의미 한 것은 아니라고 했기 때문에 이 방식에는 많은 문제가 있는 것 같다. log2에 대해서는 잘 모르는 듯 했다. 용량 줄이기 문제는 계속 연구 중이라고 한다.

"To Waffinity and Beyond: A Scalable Architecture for Incremental Parallelization of File System Code", Matthew Curtis-Maury, Vinay Devadas, Vania Fang, and Aditya Kulkarni, NetApp, Inc.

* 논문에 대한 이야기 보다는 최근 스토리지 동향에 대해 이야기를 나눴다. 내가 박사학위 받을 때 또는 그 보다 좀 더 이른 시점에는 학위 논문과 같은 주제인 hybrid storage 시스템에 유행이기도 했고 그것으로 돈을 많이 벌었다고 한다. 지금은 SSD로만 된 시스템이 대세라고 한다. 더이상은 hdd는 활용을 안하는 듯했다.


"Correlated Crash Vulnerabilities", Ramnatthan Alagappan, Aishwarya Ganesan, Yuvraj Patel, Thanumalayan Sankaranarayana Pillai, Andrea C. Arpaci-Dusseau, and Remzi H. Arpaci-Dusseau, University of Wisconsin—Madison

* 이 논문은 APM이라는 이전 논문의 확장판이다. strace 또는 dtrace로 시스템 콜을 추출하여 스토리지에 상태를 변경할 지점들을 파악하고 원래 저장해 놓았던 정보와 비교하여 어떤 오류가 발생하는지 확인하는 시스템이다. APM은 로컬 파일 시스템의 오류를 파악하는 것이었다면 이 논문은 분산 시스템에서 발생할 수 있는 오류를 파악하는 것이다. 오류를 파악했다면 수정을 해야겠지만, 그 수정 자체는 결국 사람이 해야 한다는 것이다. 어떤 오류를 고려해야 하는지를 파악하는 툴로는 좋은 것 같다.

"Tiny Tail Flash: Near-Perfect Elimination of Garbage Collection Tail Latencies in NAND SSDs", Shiqin Yan, Huaicheng Li, Mingzhe Hao, and Hao Tong, University of Chicago; Swaminathan Sundararaman, Parallel Machines; Andrew A. Chien and Haryadi S. Gunawi, University of Chicago

* ssd에 있는 낸드 플래시의 패키지를 마치 raid로 구성을 하여 패리티를 추가하였다. 그래서 하나의 패키지가 gc를 수행 중이면 나머지 n-1개의 패키지의 페이지들을 읽어서 서비스 한다는 것이다. 이것이 가능한 이유는 read가 gc보다 더 빠르기 때문에 가능하다는 주장이다.

"Slicer: Auto-Sharding for Datacenter Applications", Atul Adya, Daniel Myers, Jon Howell, Jeremy Elson, Colin Meek, Vishesh Khemani, Stefan Fulger, Pan Gu, Lakshminath Bhuvanagiri, Jason Hunter, and Roberto Peon, Larry Kai, Alexander Shraer, and Arif Merchant, Google; Kfir Lev-Ari, Technion—Israel Institute of Technology

* OSDI 2010년에 만났던 Jon Howell은 마이크로소프트에서 구글로 이직한지가 1년반이 되었다고 한다. 그 때는 머리가 많이 길었는데, 짧게 자른 머리를 이제 다시 기르려고 한다. 예전에 발표했던 논문 중에 기억에 남는 것이 있어서 문의를 했다.
(Jon Howell, Bryan Parno, and John R. Douceur, How to Run POSIX Apps in a Minimal Picoprocess, in Proceedings of the USENIX Annual Technical Conference, USENIX, June 2013. Jon Howell, Bryan Parno, and John R. Douceur, How to Run POSIX Apps in a Minimal Picoprocess, in Proceedings of the USENIX Annual Technical Conference, USENIX, June 2013.) 웹브라우저 위에서 운영체제가 필요로하는 응용프로그램을 실행시키는 기법에 대한 주제들이었는데 마이크로소프트에서는 윈도우를 팔아야하는 입장이었기 때문에 인기가 많이 없었고 관심도 크게 끌지 못했다고 한다. 기술의 요소들을 때어 놓고 보면 Jon의 말로는 기반을 모두 갖고 있었으나 지원을 받지 못하여 많은 아쉬움이 남았다고 한다. Slicer라는 논문에 대해서 이야기 하다가 알게 된 사실은 크롬 앱으로 hello world와 같은 간단한 프로그램을 짜게되면 갖가지 앱을 구동시키기 위한 라이브러리들이 붙기 때문에 용량이 기가바이트 급으로 커진다고 한다.

"Intermittent Computation without Hardware Support or Programmer Intervention", Joel Van Der Woude, Sandia National Laboratories; Matthew Hicks, University of Michigan

* Joel이 발표 중에 말하지 않은 내용이 있었는데, 어떤 종류의 nvram을 사용했는지 말하지 않았다. 발표 중에 누가 SSD같이 느린 것을 쓰냐고 했는데, 좌중의 반응은 진심인가? 라는 분위기였다. Jon Howell도 자신이 너무 감이 떨어졌나? 라고 의문이 들 정도였다고 했다. 그러나 NVRAM이 분명 속도가 빠른것은 인정을 한다. 실제로 이들은 FRAM을 사용하여 체크포인트를 가끔씩하는 시스템을 구축하였다. 실제 논문에서는 TI의 MSP430FR59xx 제품을 사용했다고 한다. 3d-xpoint에 대해서 어떻게 생각하는지 물었는데, Joel은 모른다고 해서 의외였다.

학회에 참석한 사람들은 자기가 관심있는 주제를 열심히 듣는 사람들이 있는가 하면 자기 할 일을 하는 사람들이 있다. 메일을 쓰는 사람들이나 웹 서핑을 하는 사람들은 몇 못봤다. 질문을하기 위해 논문을 읽는 사람들은 대부분 중국인들이다. 발표 중에 이미 작성한 질문에 대한 대답이 나왔더라도 상관없이 외워서 질문하는 중국인들이 있었다. 그 외의 모든 외국인들은 코딩을 하고 있었다. 티테이블 위에서 코딩하거나 학회장에 발표를 들으면서도 코딩을 하고 있었다. 프로그래밍이라고 하면 특히 시스템 프로그래밍 분야에서는 두 개의 언어를 잘 다뤄야 한다. C 그리고 python이다. 그 외의 다른 언어는 취급하지 않는다. 기법들은 C로 만들고 실험은 C로 하거나 python으로 한다.


이번 학회에서 발견한 사소한 트랜드 중에 하나는 alice와 같은 pseudo character로 예를 들어 질문과 설명을 하는 기법들이 많이 보였다는 것이다. Sesame street의 kermit도 나왔고 Alice도 두어번 나왔고, 기억은 안나는데 또 다른 케릭터도 있었다. 그렇게 케릭터를 사용하지는 않아도 시나리오를 설정하거나 내러티브 방식으로 설명하는 발표들이 인상적이기도 했고 요점이 잘 정리 된 느낌을 받았다.


참석자들 중에는 이 분야의 사람들이면 누가나 알만한 유명한 사람들이 몇 있다. 운영체제 책의 저자인 Andrew Tannenbaum 이라든가, log-structure file system 의 John Ousterhout 가 내가 아는 유명한 사람들이다. Peter Chen 은 소프트웨어공학을 하는 사람들에게는 특히 이름이 잘 알려져 있을 것이다. 흔히 ER diagram이라고 알려진 Entity-Relation Model을 만든 사람이다. 이런 사람들을 만날 수 있는 것 자체가 영광이었다.

먹거리를 빼어 놓을 수 없다. 그렇지만 그렇다고 많이 할애 할 정도로 다양하지는 않다. Mrs. Wilkes 는 이미 소개했다. 그 외의 날들은 학회에서 주는 아침과 점심 그리고 간식을 먹었다. 저녁에는 각자 가져온 햇반과 김치, 라면과 참치 통조림, 스팸 그리고 김으로 해결하였다. 상당히 이타적으로 계산했던지 각자 4인분씩 2-3일치를 가져왔다. 결국 남았다. 텍사스에 있는 재민이에게 우편으로 보냈다.
