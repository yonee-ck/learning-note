# Async & Await
- 자바스크립트 비동기 처리 패턴의 최신 문법
- Promise와 Callback에서 주는 단점들을 해결하고 자바스크립트의 비동기적 사고 방식에서 벗어나 동기적(절차적)으로 코드를 작성할 수 있게 도와준다.

### 기본 문법
```js
async function fetchData() {
  await getUserList();
}
```
- 함수 앞에 async를 붙여주고 함수의 내부 로직 중 비동기 처리 로직 앞에 await를 붙여준다. 
<br> ( Promise 객체를 반환하는 API 호출 함수 앞에 await를 붙임)
