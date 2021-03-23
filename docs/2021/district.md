# 엄격모드
자바스크립트 내에서 아래 버전의 호환성은 가져가면서 새롭게 정의된 스펙을 따르게 하기 위해서 사
ES5에서 새로운 기능이 추가되고 기존 기능 중 일부가 변경. 이로 인한 하위 호환성 문제가 발생하게 될 수 있기때문에
변경사항 대부분은 ES5의 기본 모드에선 활성화되지 않도록 설계되었다. 
대신 'use strict'라는 특별한 지시자를 사용해 엄격 모드(strict mode)를 활성화 했을 때만 이 변경사항이 활성화된다.


## 스크립트 엄격모드
```js
'use strict';
var v = "Hi!  I'm a strict mode script!";
```

## 함수 엄격모드
```js
function strict() {
  'use strict';
  function nested() { return "And so am I!"; }
  return "Hi!  I'm a strict mode function!  " + nested();
}
function notStrict() { return "I'm not strict."; }
```

## 모듈 엄격모드
```js
function strict() {
    // 모듈이기때문에 기본적으로 엄격
}
export default strict;
```
