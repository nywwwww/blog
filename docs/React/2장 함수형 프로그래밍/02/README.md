---
title: 2.2 선언적 프로그래밍 비교
mete:
  - name: description
    content: 2.2 선언적 프로그래밍 비교
  - property: og:title
    content: 2.2 선언적 프로그래밍 비교
  - property: og:description
    content: 2.2 선언적 프로그래밍 비교
  - property: og:url
    content: https://nywwwww.github.io/blog/React/2장%20함수형%20프로그래밍/02/
---

# 2.2 선언적 프로그래밍

함수형 프로그래밍은 선언적 프로그래밍이라는 더 넓은 프로그래밍 패러다임의 한 가지다. 선언적 프로그래밍은 필요한 것을 달성하는 과정을 하나하나 기술하는 것보다 필욯나 것이 어떤 것인지 기수하는 데 방점을 두고 어플리케이션의 구조를 세워나가는 프로그래밍 스타일이다.

```javascript
const string = "This is the midday show with Cheryl Waters"
const urlFriendly = string.replace(/ /g, "-")

console.log(urlFriendly)
```

여기서는 string.replace와 정규식을 사용해서 모든 공백을 하이픈으로 변경한다. string.replace를 사용하면 모든 공백이 하이픈으로 변경되어야 한다는 사실을 기술할 수 있다. 공백을 하이픈으로 변경하는 자세한 방법은 replace 함수 안에 들어가고, 구체적 절차 대신 replace(치환이라는 뜻)라는 함수를 사용해 추상적인 개념을 표현한다.
  
선언적 프로그램은 코드 자체가 어떤 일이 벌어질지 설명하기 때문에 좀 더 추론하기 쉽다. 선언적 접근 방식이 더 읽기 쉽고, 그래서 더 추론하기 쉽다. 각 함수가 어떻게 구현되어있는지는 함수라는 추상화 아래에 감춰진다.
  
DOM을 만드는 과정을 살펴보자 명령형 접근 방식은 다음과 같이 DOM을 구착하는 절차와 관련 있다.

```javascript
var taget = document.getElementById('target')
var wrapper = document.createElement('div')
var headline = document.createElement('h1')

wrapper.id = "welcome"
headline.innerText = "Hello World"

wrapper.appendChild(headline)
target.appendChild(wrapper)
```

이제 리액트 컴포넌트를 사용해 DOM을 선언적으로 구성하는 방법을 살펴보자

```javascript
const { render } = ReactDOM

const Welcome = () => (
    <div id="welcome">
        <h1>Hello World</h1>
    </div>
)

render(
    <Welcome />,
    document.getElementById('target')
)
```

리액트는 선언적이다. 여기서 Welcome 컴포넌트는 렌더링할 DOM을 기술한다. render 함수는 컴포넌트에 있는 지시에 따라 DOM을 만든다. 이 과정에서 실제 DOM이 어떻게 렌더링되는지 대한 내용은 추상화로 사라진다. 이 코드를 보면 Welcome 컴포넌트를 ID가 target인 엘리먼트 안에 렌더링하고 싶어 하는 의도가 명확히 드러난다.