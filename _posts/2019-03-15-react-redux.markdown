---
layout: post
title: "React-redux"
date: 2019-03-15
description:
image: /assets/images/react-redux.png
author: Jeong geonwoo
tags:
  - react
  - redux
---

## React Redux

`React Redux` 는 Redux를 컴포넌트 상에서 간편하게 사용할 수 있는 라이브러리이다. React Redux는 컴포넌트에서 `store`를 `props`로 받아오거나 `Subscribe`를 직접 할 필요가 없어 생산성이 증가된다. React의 컴포넌트 자체는 Redux의 흐름에 동화되기 어려워 React Redux 라이브러리에서 제공하는 `connect` 함수를 사용한다. `connect` 함수의 인자인 `mapStateToProps` 와 `mapDispatchToProps는` 다음과 같다.

### mapStateToProps

`mapStateToProps`는 `connect` 함수에 첫 번째 인자로 들어가는 함수 혹은 객체이다. `mapStateToProps`는 기본적으로 `store`가 업데이트될 때마다 자동으로 호출 된다. 이를 원하지 않는다면 `null` 혹은 `undefined` 값을 제공해야 한다.

### mapDispatchToProps

`mapDispatchToProps`는 `connect` 함수의 두 번째 인자로 사용된다. 이는 기본적으로 `store`에 접근한 컴포넌트가 `store`의 상태를 바꾸기 위해 `dispatch`를 사용할 수 있게 만든다.

여러 컴포넌트가 리스트 형식으로 모여 있을 경우 각 요소의 컴포넌트를 각각 연결하기에는 비효율적인 면이 있다. 따라서 자식 컴포넌트를 감싸고 있는 하나의 부모 컴포넌트가 대표하여 `connect`하고 `connect`된 해당 컴포넌트를 `Container`라고 한다. `Container`는 가독성을 높이며 다른 컴포넌트와는 디렉토리를 분리하는 것이 효율적이다. React Redux 라이브러리를 코드는 다음과 같다.

![](/assets/images/react_redux_code.png)

위 사진은 `user` 닉네임의 사용여부를 체크하기 위한 코드이다.

![](/assets/images/redux-ducksptrn.png)

위 사진은 `reudx ducks pattern` 으로 작성된 `reducer` 이다. `reudx ducks pattern` 에 대해서 알고 싶으면
다음 [게시글](/2019-03-15-redux.markdown)을 참고 바란다.
