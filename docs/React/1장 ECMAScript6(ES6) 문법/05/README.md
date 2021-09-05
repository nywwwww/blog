---
title: 1.5 클래스
mete:
  - name: description
    content: 1.4 클래스
  - property: og:title
    content: 1.4 클래스
  - property: og:description
    content: 1.4 클래스
  - property: og:url
    content: https://nywwwww.github.io/blog/React/1장%20ECMAScript6(ES6)%20문법/05/
---

# 1.5 클래스

<strong>```ES6```</strong>에는 클래스 선언이 추가되었다. 함수는 객체며 상속은 프로토타입을 통해 처리된다.

```javascript
class Vacation {

    constructor(destination, length) {
        this.destination = destination
        this.length = length
    }

    print() {
        console.log(`${this.destination}은(는) ${this.length}일 걸립니다.`)
    }
}
```

클래스를 정의하고 나면 new 키워드를 사용해 해당 클래스의 새로운 인스턴스를 만들 수 있다.
그 후 그 인스턴스의 메서드(클래스에 정의된)를 호출할 수 있다.

```javascript
const trip = new Vacation("칠레 산티아고", 7)

console.log(trip.print()) // 칠레 산티아고는(는) 7일 걸립니다.
```

클래스를 확장할 수도 있다. 기존의 클래스(부모또는 상위 클래스)를 확장한 새로운 클래스(자식또는 하위클래스)는 상위 클래스의 모든 프로퍼티와 메서드를 상속한다. 이렇게 상속한 프로퍼티나 메서드를 하위 클래스 선언 안에서 변경할 수도 있다.

```javascript
class Expedition extends Vaction {
    
    constructor(destination, length, gear) {
        super(destination, length)
        this.gear = gear
    }

    print() {
        super.print()
        console.log(`당신의 ${this.gear.join("와(과) 당신의 ")}를(을) 가져오십시오.`)
    }
}
```