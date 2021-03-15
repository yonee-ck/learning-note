# export
JavaScript 모듈에서 함수나 객체를 내보낼 때 사용한다. 
export를 이용해 내보낸 값은 다른 프로그램에서 import문으로 가져가 사용할 수 있다.

** export 문은 HTML 안에 작성한 스크립트에서는 사용할 수 없다.


```js
// 하나씩 내보내기
export let name1, name2, …, nameN; // var, const도 동일
export let name1 = …, name2 = …, …, nameN; // var, const도 동일
export function functionName(){...}
export class ClassName {...}

// 목록으로 내보내기
export { name1, name2, …, nameN };

// 내보내면서 이름 바꾸기
export { variable1 as name1, variable2 as name2, …, nameN };

// 비구조화로 내보내기
export const { name1, name2: bar } = o;

// 기본 내보내기
export default expression;
export default function (…) { … } // also class, function*
export default function name1(…) { … } // also class, function*
export { name1 as default, … };

// 모듈 조합
export * from …; // does not set the default export
export * as name1 from …;
export { name1, name2, …, nameN } from …;
export { import1 as name1, import2 as name2, …, nameN } from …;
export { default } from …;
```

## 유명(named)과 기본(default) 내보내기

모듈 하나에서, 유명 내보내기는 여러 개 존재 가능. 
기본 내보내기는 하나만 가능

###  유명 내보내기
```js
// 먼저 선언한 식별자 내보내기
export { myFunction, myVariable };

// 각각의 식별자 내보내기
// (변수, 상수, 함수, 클래스)
export let myVariable = Math.sqrt(2);
export function myFunction() { ... };
```

### 기본 내보내기
```js
// 먼저 선언한 식별자 내보내기
export { myFunction as default };

// 각각의 식별자 내보내기
export default function () { ... };
export default class { ... }
```
유명 내보내기는 여러 값을 내보낼 때 유용.
가져갈 때는 내보낸 이름과 동일한 이름을 사용해야 한다.
기본 내보내기는 어떤 이름으로도 가져올 수 있다.

```js
// test.js
let k; export default k = 12;
```
```js
// 임의의 다른 파일
import m from './test'; // k가 기본 내보내기이므로, 가져오는 이름으로 k 대신 m을 사용해도 문제 없음
console.log(m);         // 12 기록
```
식별자 충돌을 피하기 위해 유명 내보내기 중 이름을 바꿔줄 수도 있다.
```js
export { myFunction as function1,
myVariable as variable };
```

## 다시 내보내기 / 조합
부모 모듈이 자식 모듈을 가져와서 다시 내보낼 수도 있다. 즉, 여러 개의 모듈을 모아놓을 하나의 모듈을 만들 수 있다.
```js
export foo from 'bar.js';
```
위 아래 동일 구문
```js
import foo from 'bar.js';
export foo;
```

> 참조: https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Statements/export
