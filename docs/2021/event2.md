# Event의 종류

### addEventListner
특정 이벤트 발생 시 지정한 특정 함수 실행
하나의 요소에 같은 이벤트를 여러개 등록할 수 있다.
EventTarget의 주어진 이벤트 유형에, EventListener를 구현한 함수 또는 객체를 이벤트 처리기 목록에 추가해 작동한다.

```js
target.addEventListener(type, function, useCapture);
widow.addEventListener('mouseover', function () {
    alert('mouseover');
});
```

### removeEventListener
해당 요소에 등록된 이벤트를 지우는 역할

## 문서의 로드 시점에 관련된 이벤트

###  DOMContentLoaded
HTML이 모두 로드되고, DOM 트리 완성되었으며 외부 리소스(img, style ...)가 아직 로드되어지지 않았을 때
DOM이 준비 상태이기 때문에, DOM 노드를 제어할 수 있다.
참고) 스크립트를 바디 위에 작성하거나, 하단에 작성하는 경우가 많다.
HTML 문서를 파싱하는 과정에서 script 태그를 만나면 DOM 구축 작업이 중단 , script 작업이 실행된 후 다시 재실행
DOMContentLoaded 이벤트가 발생하는 시점이 script 작업 완료 시간만큼 지연된다는 의미이다.
또한 상황에 따라, DOM 구축이 되지 않은 상태에서 DOM 을 가져오기 때문에, 정상적인 동작이 이루어지지 않는다.

### load
브라우저에 모든 리소스가 로드되었을 때
모든 리소스가 로드된 시점이기에, 외부 리소스 관련한 정보들을 얻을 수 있다.
모든 리소스 로드 후 실행되기 떄문에 일반적으로 빠른 실행을 위해 load보다는 DOMContentLoaded를 사용한다.

### beforeunload / unload
페이지를 떠날 때
변화에 따른 저장 여부 및 페이지 이탈 여부를 확인
