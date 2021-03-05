# 뷰 라우터

- 뷰 라이브러리를 이용하여 싱글 페이지 애플리케이션을 구현할 때 사용하는 라이브러리

### 뷰 라우터 설치

```js
npm install vue-router
```

### 뷰 라우터 등록

- 라우터 인스턴스를 생성하고 뷰 인스턴스에 등록

```js
// 라우터 인스턴스 생성
var router = new VueRouter({
  // 라우터 옵션
});

// 인스턴스에 라우터 인스턴스를 등록
new Vue({
  router: router,
});
```

### 뷰 라우터 옵션

- 라우터 옵션 정의. 대부분의 SPA 앱에서는 아래의 2개 옵션을 필수로 지정

- routes : 라우팅 할 URL과 컴포넌트 값 지정
- mode : URL의 해쉬 값 제거 속성

```js
new VueRouter({
  mode: "history",
  routes: [
    { path: "/login", component: LoginComponent },
    { path: "/home", component: HomeComponent },
  ],
});
```

### router-view

- 브라우저의 주소 창에서 URL이 변경되면, 위에서 정의한 routes 속성에 따라 해당 컴포넌트가 화면에 뿌려진다. 이 때 뿌려지는 지점이 템플릿의 `<router-view>` 이다.

```js
<div id="app">
  <router-view></router-view> <!-- LoginComponent 또는 HomeComponent -->
</div>
```

### router-link

- 화면에서 특정 링크를 클릭해서 페이지를 이동할 수 있게 해주는 것

```js
<div>
  <router-link to="/login" />
</div>
```
