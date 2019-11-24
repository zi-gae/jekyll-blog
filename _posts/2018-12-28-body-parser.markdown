---
layout: post
title: "body-parser 사용법"
date: 2018-12-28
description: 
image: /assets/images/npm.png
author: Jeong geonwoo
tags: 
  - node
---

### body-parser
body-parser 란?
`body-parser` 는 nodejs 의 post 요청 데이터를 추출할 수 있도록 만들어 주는 미들웨어이다. `body-parser` 를 `req` 에 `body property` 를 사용할 수 있다.
```javascript
import express from "express"
import bodyParser from "body-parser"

const app = express();

app.use(bodyParser.json());
app.use(bodyParser.urlencoded({ extended: true }));
```
위와 같이 작성하면 `json` 으로 받아볼 수 있다.







