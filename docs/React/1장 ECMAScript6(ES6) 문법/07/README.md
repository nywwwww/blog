---
title: 1.7 커먼JS
mete:
  - name: description
    content: 1.7 커먼JS
  - property: og:title
    content: 1.7 커먼JS
  - property: og:description
    content: 1.7 커먼JS
  - property: og:url
    content: https://nywwwww.github.io/blog/React/1장%20ECMAScript6(ES6)%20문법/06/
---

# 1.7 커먼JS

커먼JS는 모든 버전의 노드에서 지원하는 일반적인 모듈 패턴이다. 커먼JS를 사용하면 자바 객체를 module.exports를 사용해 익스포트할 수 이싿.

```javascript
const print(message) => log(message, new Date())

const log(message, timestamp) =>
    console.log(`${timestamp.toString()}: ${message}`)

module.export = {print, log}
```

커먼JS는 import 문을 지원하지 않는다. 대신 require 함수로 모듈을 임포트할 수 있다.

```javascript
const { log, print } = require('./text-helpers')
```
