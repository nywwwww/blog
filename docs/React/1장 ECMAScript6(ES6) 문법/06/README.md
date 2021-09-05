---
title: 1.6 ES6 모듈
mete:
  - name: description
    content: 1.6 ES6 모듈
  - property: og:title
    content: 1.6 ES6 모듈
  - property: og:description
    content: 1.6 ES6 모듈
  - property: og:url
    content: https://nywwwww.github.io/blog/React/1장%20ECMAScript6(ES6)%20문법/06/
---

# 1.6 ES6 모듈

자바스크립트 모듈은 다른 자바스크립트 파일에서 쉽게 불러서 활용할 수 있는 재사용 가능한 코드 조각을 말한다. <strong>```ES6```</strong>이전의 자바스크립트를 모듈화하는 방법은 모듈의 임포트와 익스포트를 처리하는 라이브러리를 활용하는 것뿐이었다. 하지만 <strong>```ES6```</strong>부터는 자바스크립트 자체에서 모듈을 지원하기 시작했다.

```javascript
export const print(message) => log(message, new Date())

export const log(message, timestamp) =>
    console.log(`${timestamp.toString()}: ${message}`)
```

export를 사용해 다른 모듈에서 활용하도록 이름(함수, 객체, 변수, 상수 등이 될 수 있다)을 외부에 익스포트 할 수 있다. 모듈에서 단 하나의 이름만 외부에 익스포트하고 싶을 때 export default를 사용한다.
  
모듈은 import 명령을 사용해 다른 자바스크립트 파일을 불러와 사용할 수 있다.

```javascript
import { print, log } from './text-helpers'
impot freel from './mt-freel'

print('메시지를 print')
log('메시지를 log')

freel.print()
```

import *를 사용하면 다른 모듈에서 가져온 모든 이름을 사용자가 정한 로컬 이름 공간 안에 가둘 수 있다.