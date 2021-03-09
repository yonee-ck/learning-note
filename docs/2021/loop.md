# 반복문

## for
```js
// 일반적
for (let i = 0; i < 10; i++) {
    console.log(i);
    i++;
}

// 중괄호 생략
for (let i = 0; i < 10; i++) console.log(i);
```

## while
```js
let i = 0;
while (i < 10) {
    console.log(i);
    i++;
}

// break; 반복문 속에서 원하는 값을 찾았을 때 반복문에서 탈출 (남은 반복문 실행X)
let i = 0;
while (i < 10) {
    if (i > 5) {
        break;  // 5까지 하고 중단
    }
    console.log(i);
    i++;
}

// continue; 반복문을 끝까지 돌기는 하지만, 그 안에서의 예외를 두고 싶을 때 사용
var i = 0;
while (i < 10) {
    i++;
    if (i % 2 === 0) {  // i가 짝수 일때
        continue;   // continue의 아랫부분은 실행하지 않고 다음 반복문으로 바로 넘어간다.
    }
    console.log(i); // 1~10 사이의 홀수만 보여준다. 
}
```

