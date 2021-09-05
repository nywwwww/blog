---
title: 2.1 함수형이란?
mete:
  - name: description
    content: 2.1 함수형이란?
  - property: og:title
    content: 2.1 함수형이란?
  - property: og:description
    content: 2.1 함수형이란?
  - property: og:url
    content: https://nywwwww.github.io/blog/React/2장%20함수형%20프로그래밍/01/
---

# 2.1 함수형이란?
함수형 프로그래머들은 작은 함수를 아주 많이 작성하기 때문에 화살표 함수 구문을 사용할 수 있으면 코딩이 훨씬 더 간편해진다.

```javascript
const log = message => console.log(message)
```

함수를 변수에 넣을 수 있는 것과 마찬가지로 객체에 넣을 수도 있다. 심지어 함수를 배열에 넣을 수도 있다. 다른 값과 마찬가지로 함수를 다른 함수에 인자로 넘길 수도 있다.

```javascript
const insideFn = logger =>
    logger("함수를 다른 함수에 인자로 넘길 수도 있습니다.");

insideFn(message => console.log(message))
```

함수가 함수를 반환할 수도 있다. 이 또한 일반적인 값과 마찬가지다

```javascript
var createScream = function(logger) {
    return function(message) {
        logger(message.toUpperCase() + "!!!")
    }
}

const sream = createScream(meesage => console.log(message))

scream('함수가 함수를 반활할 수도 있습니다')
scream('createScream은 함수를 반환합니다')
scream('scream은 createScream이 반환한 함수를 가리킵니다')

```

마지막 두 예제, 즉 함수를 인자로 받거나 함수를 반환하는 함수를 고차 함수라고 부른다. <strong>```ES6```</strong> 문법을 사용하면 createScream 고차 함수를 화살표 함수로 표현할 수 있다.

```javascript
const createScream = logger => message => logger(message.toUpperCase() + "!!!")
```