---
layout: post
title: "CPU Scheduling"
date: 2017-12-13
description:
image: /assets/images/cpu_kinds.png
author: Jeong geonwoo
tags:
  - react
  - redux
---

## CPU Scheduling Simulator

<br/>

#### 프로젝스 소개

사용자가 편리한 시뮬레이터를 구현하였다.
프로세스 수를 정해주면 기타 옵션들은 자동 또는 수동으로 설정가능하며
수동은 우선순위, 서비스시간, 도착시간을 직접 입력해야한다.
기법은 FCFS, HRN, SJF, Priority, SRT, RonudRobin 이있고 프로세스 수를 입력하고
기법을 선택한 후 실행 버튼을 누르면 실행되며
각 프로세스 별 대기시간과 평균 대기시간, 평균 반환시간을 나타내고
최종적으로 기법별 스케줄링을 그래프로 도식화한다.

<br/>

#### 시작화면

![](/assets/images/cpu_main.png)

<br/>

#### 프로세스 생성

![](/assets/images/createProcess.png)

<br/>

#### 다양한 CpuScheduling 기법

![](/assets/images/FCFS.png)
![](/assets/images/HRN.png)
![](/assets/images/SJF.png)

<br/>

#### 개발환경

언어: java 9.0.1

에디터: eclipse 사용

<br/>

#### 부가 설명

각 기법별로 점화식을 이용

<br/>
