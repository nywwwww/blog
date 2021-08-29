---
title: 1.1 변수 선언하기
mete:
  - name: description
    content: 1.1 변수 선언하기
  - property: og:title
    content: 1.1 변수 선언하기
  - property: og:description
    content: 1.1 변수 선언하기
  - property: og:url
    content: https://nywwwww.github.io/blog/React/1장%20ECMAScript6(ES6)%20문법/01/
---

# 1.1 변수 선언하기

## 1.1.1 const
<strong>```ES6```</strong> 이전에는 모든 값을 변수에 넣어 사용했다. 하지만 변수는 값을 변경할 수 있다.

```javascript
var pizza = true
pizza = false
console.log(pizza) // false
```
상수에 값을 재설정하는 것은 불가능하다.
```javascript
const pizza = true
pizza = false
```

## 1.1.2 let
자바스크립트도 <strong>```ES6```</strong>부터는 **구문적인 변수 영역 규칙**을 지원한다.
일반적인 언어에서 함수의 경우 코드 블록이 별도의 변수 영역을 이룬다. 하지만 자바스크립트에서는
블록 안에서 변수르르 새로 만들면 그 변수의 영역이 그 블록 안으로만 한정되지 않는다.
```javascript
var topic = "자바스크립트"
if (topic) {
    var topic = "리액트"
    console.log('블록', topic) // 블록 리액트
}
console.log('글로벌', topic) // 글로벌 리액트
```
let 키워드를 사용하면 변수 영역을 코드 블록 안으로 한정시킬 수 있다.
```javascript
var topic = "자바스크립트"
if (topic) {
    let topic = "리액트"
    console.log('블록', topic) // 블록 리액트
}
console.log('글로벌', topic) // 글로벌 자바스크립트
```
<strong>```{}```</strong>가 새로운 영역을 만들어내지는 못하는 다른 부분으로는 for 루프도 있다.

## 1.1.3 템플릿 문자열
템플릿 문자열을 문자열 연결 대신 사용할 수 있다.  
전통적인 문자열 연결은 더하기 기호(+)로 문자열과 변수를 서로 이어붙이는 방식을 사용한다.
```javascript
console.log(lastName + ", " + firstName + " " + middleName)
```
템플릿에서는 ${}를 사용해 문자열 안에 변수를 집어넣을 수 있기 때문에 문자열을 단 한나만 사용해도 된다. 템플릿 문자열의 ${}에는 값을 만들어내는 자바스크립트 식이라면 어떤 것이든 들어갈 수 있다.
```javascript
console.log(`${lastName}, ${firstName} ${middleName}`)
```

## 1.1.4 디폴트 파라미터
C++나 파이썬 같은 언어에서는 함수의 인자로 디폴트 값을 선언할 수 있다.  
<strong>```ES6```</strong>에도 디폴트 파라미터가 추가되었다.
```javascript
function printLog(message="로그 메세지") {
    console.log( `로그 메세지는 ${message}입니다.` )
}
```
***

