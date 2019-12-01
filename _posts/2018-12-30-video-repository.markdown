---
layout: post
title: "동아리 알고리즘 강좌 사이트"
date: 2018-12-30
description:
image: /assets/images/video_repo/null-videolecture.png
author: Jeong geonwoo
tags:
  - node
---

학과 내에서 운영하는 창업동아리에서 필요로 하여 만들게 되었으며, 필자는 컴퓨터공학과이기 때문에 팀원들 모두 동일한 전공이고 알고리즘을 공부하자는 취지로 다운 받은 알고리즘 강의를 다 같이 보기 위해 프로젝트를 진행하였다. 해당 사이트의 아래 기능에 중점을 두고 개발하였다.

&nbsp; 1.소셜 로그인 (kakako, github).

&nbsp; 2.동영상 검색

&nbsp; 3.동영상 업로드

&nbsp; 4.동영상 시청

&nbsp; 5.동영상 댓글

<br/>

#### 로그인 & 회원가입

![](/assets/images/video_repo/joinPage.png)
![](/assets/images/video_repo/loginPage.png)

깃허브와 카카오톡 계정을 이용해서 가입 가능하다.

<br/>

#### 회원 승인 페이지

![](/assets/images/video_repo/userControllPage.png)

관리자(만든이)만 접속 가능하며 외부인의 열람을 막기 위해
승인 절차가 있어야 업로드 및 동영상 열람이 가능하다.

<br/>

#### 동영상 열람

![](/assets/images/video_repo/mainpage_login.png)

관리자의 승인을 받은 사용자만
알고리즘 기본 강의를 볼 수 있다.

가입 또는 시청하기 [링크](https://null-lecture.herokuapp.com/)

<br/>

#### 개발환경

- javascript ES6 이상 문법 사용
- 에디터 vscode 사용
- heroku 를 이용한 호스팅
- atlas 클라우드에 디비 업로드
- s3 를 이용한 동영상 관리

<br/>

#### 부가 설명

mongolab 사용이 중지되어 atlas 로 이동
