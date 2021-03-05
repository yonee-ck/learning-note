# Unit Testing
- 테스팅 도구: 요구 사항 변경에 따른 기능 추가 및 리팩토링을 할 때 소프트웨어의 안정성을 높여주는 도구 

### Jest
아래의 여러 테스팅 도구 중의 하나 
<br> 페이스북에서 만든 자바스크립트 테스팅 라이브러리
- Jest
- Mocha
- Jasmine
- Enzyme

### 라이브러리 설치
```js
npm install --save-dev jest
```

### 테스트 파일 생성
- 파일 위치 : 테스트 할 파일이 있는 폴더 내
- 폴더 이름 : __test__
- 파일 이름 : 파일 이름.test.js

### 테스트 코드 실행
Jest를 설치 후 콘솔 창에 명령어로 실행
```js
jest
```
- 프로젝트 내부의 test.js 확장자를 가지는 파일을 모두 실행

### 테스트 코드 예시
간단한 테스트 코드를 아래와 같이 작성해봤습니다.
```js
// helloworld.test.js
const str = 'Hello World';

test('str equals to be Hello World', () => {
  expect(str).toBe('Hello World');
});
```
- str의 값이 Hello World가 인지 확인하는 테스트 코드
- expect()에 테스트 할 내용을 넣고, toBe()에 예상 결과 값을 입력
- 콘솔에 jest 명령어 실행
