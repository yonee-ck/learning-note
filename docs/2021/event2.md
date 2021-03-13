# Event의 종류

## addEventListner
특정 이벤트 발생 시 지정한 특정 함수 실행
하나의 요소에 같은 이벤트를 여러개 등록할 수 있다.
EventTarget의 주어진 이벤트 유형에, EventListener를 구현한 함수 또는 객체를 이벤트 처리기 목록에 추가해 작동한다.

```js
target.addEventListener(type, function, useCapture);
widow.addEventListener('mouseover', function () {
    alert('mouseover');
});
```

## removeEventListener
해당 요소에 등록된 이벤트를 지우는 역할
