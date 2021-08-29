---
title: 1.3 ES6 객체와 배열
mete:
  - name: description
    content: 1.3 ES6 객체와 배열
  - property: og:title
    content: 1.3 ES6 객체와 배열
  - property: og:description
    content: 1.3 ES6 객체와 배열
  - property: og:url
    content: https://nywwwww.github.io/blog/React/1장%20ECMAScript6(ES6)%20문법/03/
---

# 1.3 ES6 객체와 배열

## 1.3.1 구조 분해를 사용한 대입

구조분해를 사용하면 객체 안에 있는 필드 값을 원하는 변ㄴ수에 대입할 수 있다.
```javascript
var sandwich = {
    bread: "더치 크런치",
    meat: "참치",
    cheese: "스위스",
    toppings: ["상추", "토마토", "머스타드"]
}

var {bread, meat} = sandwich

console.log(bread, meat) // 더치 크런치 참치
```
두 변수를 변경해도 원래의 필드 값은 바뀌지 않는다.  
객체를 분해해서 함수의 인자로 넘길 수도 있다.

```javascript
var lodify = ({firstname}) => {
    console.log(`캔터베리의 ${firstname}`)
}

lodify(regularPerson) // 캔터베리의 현석
```

배열을 구조 분해해서 원소의 값을 변수에 대입할 수도 있다.
```javascript
var [firstResort] = ["용평", "평창", "강촌"]

console.log(firstResort) // 용평
```

불필요한 값을 콤마(,)를 사용해 생략하는 리스트 매칭을 사용할 수도 있다.
```javascript
var [,,thirdResort] = ["용평", "평창", "강촌"]

console.log(thirdResort) // 강촌
```

## 1.3.2 객체 리터럴 개선

객체 리터럴 개선은 구조 분해의 반대라 할 수 있다. 객체 리털러 개선은 구조를 다시 만들어내는 과정 또는 내용을 한데 묶는 과정이라 할 수 있다.
```javascript
var name = "Tallac"
var elevation = 9738
var print = () => {
    console.log(`${this.name} 산의 높이는 ${this.elevation}피트입니다.`)
}

var funHike = {name, elevation, print}

funHike.print() // 탈락 산의 높이는 9738피트입니다.
```

객체 메서드를 정의할 때 더이상 function 키워드, 화살표 함수를 사용하지 않아도 된다.
```javascript
// 새로운 방식
const skier = {
    name,
    sound,
    powderYell() {
        let yell = this.sound.toUpperCase()
        console.log(`${yell} ${yell} ${yell}!!!`)
    },
    speed(mph) {
        this.speed = mph
        console.log('속력(mph):', mph)
    }
}
```

## 1.3.3 스프레드 연산자

스프레드 연산자는 세 개의 점(...)으로 이루어진 연산자로, 몇 가지 다른 역할을 담당한다.
```javascript
var peaks = ["대청봉", "중청봉", "소청봉"]
var canyons = ["천불동계곡", "가야동계곡"]
var seoraksan = [...peaks, ...canyons]

console.log(seoraksan.join(', )) // 대청봉, 중청봉, 소청봉, 천불동계곡, 가야동계곡
```
Array.reverse 메서드는 원본 배열을 변경한다. 하지만 스프레드 연산자를 사용하면 원본 배열을 변경하지 않고 복사본을 만들어서 뒤집을 수 있다.
```javascript
var peaks = ["대청봉", "중청봉", "소청봉"]
var [last] = [...peaks].reverse()

console.log(last) // 소청봉
console.log(peaks.join(', ')) // 대청봉, 중청봉, 소청봉
```

스프레드 연산자를 사용해 배열의 나머지 원소를 얻을 수도 있다.
```javascript
var lakes = ["경포호", "화진포", "송지호", "청초호"]
var [first, ...rest] = lakes

console.log(rest.join(", ")) // "화진포, 송지호, 청초호"
```