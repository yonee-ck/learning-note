# 조건문

## if-else
```js
// 일반적
if (true) {
    console.log('오조');
} else {
    console.log('도레');
}

// 중괄호 생략
if (true) console.log('오조');
else console.log('도레');

// 삼항연산자 표기법
(true) ? console.log('오조') : console.log('도레');
```

## switch
```js
// **break; 문을 뺴면 해당 case 아래의 모든 내용이 실행됨

switch (animal) {
  case '고양이': // animal = '고양이'
    alert('오조는 왕자님');
    break;
  case '강아지': // animal = '강아지'
    alert('도레는 아가');
    break;
  default: // 위의 어떤 조건에도 해당하지 않을 때
    alert('다 귀여워');
}
```
