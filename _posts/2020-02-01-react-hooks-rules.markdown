---
layout: post
title: "WEBPACK BASIC"
date: 2020-01-10
description: webpack 기본 이해하기
image: /assets/images/webpack/webpack.jpeg
author: Jeong geonwoo
tags:
  - eslint
  - hooks
---

# react-hooks/rules-of-hooks error

언제부터인가 `cra(create-react-app)` 에 `eslint-plugin-react-hooks` 이라는 `hooks` lint 가 포함되어 있는데
해당룰은 컴포넌트가 아니더라도 훅스를 포함하는 함수는 PascalCase 로 작성 되어야 한다는 룰이다.

# 해결법

첫번째 해결법은 룰을 지켜주는것이다. 하지만 필자는 죽어도 컴포넌트 외에 함수를 `PascalCase` 로 쓰기 싫기 때문에
`yarn eject` 하여 두번째 방법인 `eslint-plugin-react-hooks` 를 삭제하였다.
