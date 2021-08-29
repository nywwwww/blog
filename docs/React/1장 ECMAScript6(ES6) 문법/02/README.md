---
title: 1.2 화살표 함수
mete:
  - name: description
    content: 1.2 화살표 함수
  - property: og:title
    content: 1.2 화살표 함수
  - property: og:description
    content: 1.2 화살표 함수
  - property: og:url
    content: https://nywwwww.github.io/blog/React/1장%20ECMAScript6(ES6)%20문법/02/
---

# 1.2 화살표 함수

화살표 함수는 <strong>```ES6```</strong>에 새로 추가된 유용한 기능이다. 이를 사용하면 function 키워드 없이도 함수를 만들 수 있으며, return을 사용하지 않아도 식을 계산한 값이 자동으로 반환된다.

```javascript
var lodify = firstname => `캔터베리의 ${firstname}`
```

화샬표 (=>)를 사용하면 모든 함수 정의를 한 줄로 끝낼 수 있다. function 키워드를 없앴고, 화살표가 어떤 값을 반환하는지 지정해주기 때문에 return도 없앴다. 또다른 장점은 함수가 파라미터를 단 하나만 받는 경우 파라미터 주변의 괄호를 생략해도 된다는 것이다.  
파라미터가 2개 이상이라면 괄호가 필요하다.

```javascript
var lodify = (firstName, land) => `${land}의 ${firstName}`
```

화살표 함수는 this를 새로 바인딩하지 않는다.

```javascript
var gangwon = {
    resorts: {"용평", "평창", "강촌", "강릉", "홍천"},
    print: function(delay=1000) {
        setTimeout(function() {
            console.log(this.resorts.join(","))
        }, delay)
    }
}

gangwon.print() // Cannot read property 'join' of undefined 오류 발생
```
이 오류는 this가 window 객체이기 떄문에 resorts가 undefined다. 이런 방법 대신 화살표 함수를 사용하면 this 영역이 제대로 유지된다.

```javascript
var gangwon = {
    resorts: {"용평", "평창", "강촌", "강릉", "홍천"},
    print: function(delay=1000) {
        setTimeout(() => {
            console.log(this.resorts.join(","))
        }, delay)
    }
}

gangwon.print() // 용평, 평창, 강촌, 강릉, 홍천
```