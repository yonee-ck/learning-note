# Browser Event

## 이벤트 
무엇인가 발생했을 때, DOM 노드에서 보내는 신호

### Mouse Event
- click - 요소 위에서 마우스 왼쪽 버튼을 눌렀을 때(터치스크린이 있는 장치에선 탭 했을 때) 발생
- contextmenu – 요소 위에서 마우스 오른쪽 버튼을 눌렀을 때 발생
- mouseover, mouseout – 마우스 커서를 요소 위로 움직였을 때, 커서가 요소 밖으로 움직였을 때 발생
- mousedown, mouseup – 요소 위에서 마우스 왼쪽 버튼을 누르고 있을 때, 마우스 버튼을 뗄 때 발생
- mousemove – 마우스를 움직일 때 발생

### Form Event
- submit – 사용자가 `<form>`을 제출할 때 발생
- focus – 사용자가 `<input>`과 같은 요소에 포커스 할 때 발생

### Document Event
- DOMContentLoaded – HTML이 전부 로드 및 처리되어 DOM 생성이 완료되었을 때 발생

### css Event
- transitionend – CSS 애니메이션이 종료되었을 때 발생


## 이벤트 핸들러
이벤트에 반응하기 위해 실행되는 함수
아래와 같은 여러 가지 방법으로 핸들러를 할당할 수 있다.

### HTML 속성
HTML 안의 `on<event>` 속성에 핸들러를 할당

ex ) input 태그의 onclick 속성에 click 핸들러를 할당. 버튼을 클릭하면 onclick 안의 코드 실행
(코드가 길다면, 함수를 만들어서 호출)
```js
<input value="클릭" onclick="alert('클릭!')" type="button">
```

### DOM 프로퍼티
DOM 프로퍼티 `on<event>` 속성을 사용해 핸들러를 할당

ex) 위와 같은 동작의 코드 
```js 
<input id="elem" type="button" value="클릭해주세요.">
<script>
  elem.onclick = function() {
    alert('클릭!')
  };
</script>
```
onclick 프로퍼티는 단 하나밖에 없기 때문에, 복수의 이벤트 핸들러를 할당할 수 없다.
핸들러를 하나 더 추가 시, 기존 핸들러는 덮어씌워짐 (핸들러 제거: elem.onclick = null) 

```js
<input type="button" id="elem" onclick="alert('이전')" value="클릭해 주세요.">
<script>
  elem.onclick = function() { // 기존에 작성된 핸들러를 덮어씀
    alert('이후') // 이 경고창만 보입니다.
  };
</script>
```

## this로 요소에 접근하기
핸들러 내부에 쓰인 this의 값은 핸들러가 할당된 요소

ex) this.innerHTML에서 this는 button (버튼 클릭시 버튼 안의 콘텐츠가 얼럿창에 출력 -  alert('클릭!'))
```js
<button onclick="alert(this.innerHTML)">클릭!</button>
```

> 출처: https://ko.javascript.info/introduction-browser-events
> 
> 참고: https://developer.mozilla.org/ko/docs/Web/Events
