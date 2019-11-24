---
layout: post
title: "최신 babel 적용"
date: 2017-10-23
description: 
image: /assets/images/babel.png
author: Jeong geonwoo
tags: 
  - node
---

바벨 공식 문서를 보면 `Babel is a JavaScript compiler. Use next generation JavaScript, today.` 라고 적혀있다.
바벨은 다음 버전의 자바스크립트 문법을 현재 사용가능한 문법으로 변환 시켜주는 역할을 한다. ES6 부터 자바스크립트 문법에 많은 변화가 있었는데 브라우저는 해당 문법을 이해하지 못하기 때문에 babel 을 거쳐 브라우저가 사용가능한 문법으로 변환 시켜주어야 한다.

#### babel 적용

* STEP 1
```
npm install @babel/node
```
* STEP 2
```
npm install @babel/preset-env
```

최신바벨 중에서 가장 검증된..? 최신바벨

* STEP 3

.babelrc 파일 생성 후 아래와 같이 작성

```javascript
{
    "presets": ["@babel/preset-env"] // 설치한 패키지 명시
}
```

* STEP 4

```javascript
babel-node index.js // node index.js 를 대체
```

라고 치기 귀찮으니까 script 를 작성해주자.

```javascript
"scripts": {
    "start": "babel-node index.js"
}
```

실행!

```
npm start
```

에러가 발생한다..

```
Error: Cannot find module '@babel/core'
```

없다고 하니까 설치해보자

```
npm install @babel/core
```

이상 es6 문법이 문제 없이 동작한다.
    


