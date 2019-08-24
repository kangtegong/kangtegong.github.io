---
layout: post
title: "시스템 기초 (3) : Disk -1"
image: ''
date: 2019-08-24 09:24:06
tags: 
- System
- Computer_Architecture
description: 시스템 프로그래밍과 리버싱의 기본 소양 - Disk편
categories:
- System_Basic
---
## 시스템 프로그래밍의 기초(3) : 디스크

###  내장 프로그래밍

내장 프로그래밍 (stored programming) 이란?

기억장치에 프로그램을 저장하고 차례로 실행하는 방식, 즉
기억장치에 저장되어 있는 프로그램을 차례로 읽어들인 후 컴퓨터를 실행시키는 방식을 말한다.

따라서 기억장치가 데이터를 어떻게 처리하고 저장하는지를 알아야
프로그램의 처리 과정을 제대로 이해할 수 있을 것이다.


### 디스크 vs 메모리

하나의 프로그램은 기억장치에서부터 CPU로 흘러들어 처리되고,
(더 정확하게는, 프로그램은 디스크 -> 메모리 -> CPU순으로 진행된다)

고리타분한 개론서를 읽었을 적에는 

> 컴퓨터의 5대 장치에는 입력장치, 출력장치, 기억장치, 연산장치, 제어장치가 있다

고 배웠을 것이다.

메모리와 디스크는 둘 다 기억장치라는 공통점이 있는데, 어떤 차이가 있을까? 

물리적인 차이점으로는, 메모리는 전기적으로 데이터를 저장하고,
디스크는 자기적으로 데이터를 저장한다.

아마 컴퓨터사양을 맞춰 본 경험이 있어 기능적인 차이점을 아는 사람이라면 메모리는 고속이지만 용량이 작고,
하드 디스크는 저속이지만 용량이 크다고 말할 것이다.

프로그램의 실행 관점에서의 두 기억장치의 차이점은, CPU가 곧바로 참조할 수 있느냐 없느냐에 있다.

디스크에 기억된 프로그램은 메모리에 읽어들인 다음에 실행된다.
CPU는 디스크에 기억된 프로그램을 그대로 실행할 수는 없다.

왜냐하면 CPU는 자신이 가진  Program Counter를 이용하여 메모리의 address를 지정하고 그 곳으로부터 프로그램을 읽어 내도록 제작되었기 때문이다.

언제나 디스크에 저장된 프로그램이 메모리에 읽어들인 다음 실행되기 때문에, 디스크는 CPU 실행을 위한 메인 메모리를 위한 저장 창고라고 보아도 무방할 것이다.