# Document 

- 브라우저가 불러온 웹 페이지
- 페이지 콘텐츠(DOM 트리)의 진입점 역할을 수행한다.
- Document는 Node와 EventTarget 인터페이스를 상속한다.

### 생성자
`Document()`
새로운 Document 객체를 생성

`Document.body`
현재 문서의 `<body>` 또는 `<frameset>`노드를 반환

`Document.contentType`
현재 문서의 MIME 헤더로부터 Content-Type을 반환

`Document.cookie`
문서의 쿠키 리스트를 세미콜론으로 분리해 반환하거나, 하나의 쿠키를 설정한다.

`Document.referrer`
현재 페이지로 연결한 페이지의 URI를 반환

> 참고: https://developer.mozilla.org/ko/docs/Web/API/Document
