---
layout: post
title: "cookie-parser 사용법"
date: 2018-12-28
description: 
image: /assets/images/npm.png
author: Jeong geonwoo
---

### cookie-parser

요청된 쿠키를 쉽게 추출할 수 있도록 해주는 미들웨어.
request 객체에 cookies 속성이 부여된다.
```javascript
const express      = require('express')
const cookieParser = require('cookie-parser')
 
const app = express()
app.use(cookieParser())
 
app.get('/', function(req, res) {
  console.log('Cookies: ', req.cookies);
})
 
app.listen(8080)
```







