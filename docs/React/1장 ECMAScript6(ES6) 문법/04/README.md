---
title: 1.4 프라미스
mete:
  - name: description
    content: 1.4 프라미스
  - property: og:title
    content: 1.4 프라미스
  - property: og:description
    content: 1.4 프라미스
  - property: og:url
    content: https://nywwwww.github.io/blog/React/1장%20ECMAScript6(ES6)%20문법/04/
---

# 1.4 프라미스

프라미스는 비동기적인 동작을 잘 다루기 위한 방법이다.  
프라미스를 사용하면 이런 여러 가지 성공이나 실패를 편리하게 단순한 성공이나 실패로 환원할 수 있다.

```javascript
const getFakeMembers = count => new Promise((resolves, rejects) => {
    const api = `https://api.randomuser.me/?nat=US&results=${count}`
    const request = new XMLHttpRequest()
    request.open('GET', api)
    request.onload = () =>
        (request.status === 200) ?
        resolves(JSON.parse(request.response).results) :
        reject(Error(request.statusText))
    request.onerror = (err) => rejects(err)
    request.send()
})
```
getFakeMembers 함수는 새로운 프라미스를 반환한다. 그 프라미슨느 randomuser.me API에 요청을 보낸다.

프라미스가 성공한 경우에 처리할 작업을 기술하기 위해 then 함수를 프라미스 뒤에 연쇄시킨다.  
이때 오류를 처리하기 위한 콜백도 함께 제공한다.
```javascript
getFakeMembers(5).then(
    members => console.log(members),
    err => console.error(
        new Error("randomuser.me에서 멤버를 가져올 수 없습니다.")
    )
)
```


