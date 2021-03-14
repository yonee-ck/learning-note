# Promise

자바스크립트 비동기 처리에 사용되는 객체
‘특정 코드의 실행이 완료될 때까지 기다리지 않고 다음 코드를 먼저 수행하는 자바스크립트의 특성’

- 제이쿼리의 ajax 통신 API를 이용하여 지정된 url에서 1번 상품 데이터를 받아오는 코드
비동기 처리를 위해 프로미스 대신에 콜백 함수를 사용한 코드
```js
function getData(callbackFunc) {
    $.get('url 주소/products/1', function(response) {
        callbackFunc(response); // 서버에서 받은 데이터 response를 callbackFunc() 함수에 넘겨줌
    });
}

getData(function(tableData) {
    console.log(tableData); // $.get()의 response 값이 tableData에 전달됨
});
```

- 위 코드에 프로미스를 적용한 코드
```js
function getData(callback) {
    // new Promise() 추가
    return new Promise(function(resolve, reject) {
        $.get('url 주소/products/1', function(response) {
            // 데이터를 받으면 resolve() 호출
            resolve(response);
        });
    });
}

// getData()의 실행이 끝나면 호출되는 then()
getData().then(function(tableData) {
    // resolve()의 결과 값이 여기로 전달됨
    console.log(tableData); // $.get()의 reponse 값이 tableData에 전달됨
});
```
콜백 함수로 처리하던 구조에서 new Promise(), resolve(), then()와 같은 프로미스 API를 사용한 구조로 바뀌었다.

> 출처: https://joshua1988.github.io/web-development/javascript/promise-for-beginners/

