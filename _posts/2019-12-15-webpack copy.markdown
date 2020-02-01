---
layout: post
title: "WEBPACK BASIC"
date: 2020-01-10
description: webpack 기본 이해하기
image: /assets/images/hooks_rules/reactLint.png
author: Jeong geonwoo
tags:
  - webpack
  - babel
---

# WEBPACK 이란?

현대 Javascript Application의 Static Module Bundler입니다.
Webpack이 실행된다면 Dependencies Graph를 통해 필요한 형태의 하나 또는 여러개의 Bundle로 생성합니다.

#### BUNDLE 이란?

소프트웨어 및 일부 하드웨어와 함께 작동하는 데 필요한 모든 것을 포함하는 Package
각각의 모듈들에 대해 의존성 관계를 파악하여 하나 또는 여러개의 그룹으로 볼 수 있습니다.

아래 코드를 통해 살펴보자.

```javascript
var path = require("path");
var webpack = require("webpack");
const UglifyJsPlugin = require("uglifyjs-webpack-plugin");

module.exports = {
  entry: "./index",
  output: {
    path: path.resolve(__dirname, "dist"),
    filename: "bundle.js"
    //dist 폴더의 bundle.js 파일로 결과를 저장할 것이다.
  },
  module: {
    rules: [
      {
        test: /\.js$/,
        loader: "bael-loader",
        options: {
          presets: ["@babel/preset-env"]
        }
      }
    ]
  },
  optimization: {
    minimizer: [new UglifyJsPlugin()]
  }
};
```

#### Entry

- 웹팩이 빌드할 파일을 알려주는 역할을 한다.
- 직/간접적으로 의존성을 가진 모듈들을 이해한다.
- 여러개의 `entry가` 존재할 수 있습니다.
- 위처럼 작성하면 `./index.js` 파일 기준으로 import 되어 있는 모든 파일들을 찾아 하나의 파일로 합친다.
- Default value : `./src/index.js`

---

#### Output

- 웹팩에서 빌드를 완료하면 `output` 에 명시되어 있는 정보를 통해 빌드 파일을 생성한다.
- Default value : `./dist/main.js`

---

#### Loaders

- Webpack은 오직 Javascript와 Json만 이해할 수 있는 단점이 있다.
- Loader는 다른 Type의 파일을 Webpack이 이해하고 처리가능한 모듈로 변환시키는 작업을 한다.

---

#### Optimization

- js 코드를 어떻게 압축 할지 명시한다.

---

#### Mode

코드에는 없지만 유용한 `Mode`

- 다양한 Profile로 지정하여 진행할 수 있습니다.
- option: development, production, none
- Default value : production

---

결론: `entry` 에서 `module` 을 적용 후 `output` 으로 나온다.

---f

```javascript
module : {
    rules: {
        test: '가지고올 파일 정규식',
        use: [ // 생략 가능
            {
                loader: '사용할 로더 이름',
                options: { 사용할 로더 옵션 }
            }
        ]
    }
}
```

`babel-loader` 는 자주 사용하게 될 로더 옵션 입니다.
사전에 작업한 `.babelrc` 를 참고하여 es6 를 es5 로 변환해주고 또는 아래 처럼 `babelrc` 값을 줄 수 있다.

```
options: {
    presets: ["@babel/preset-env"]
}
```

---

    미완성 포스트입니다.
    공부하여 내용 추가 할 예정
