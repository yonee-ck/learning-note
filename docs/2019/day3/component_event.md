# 뷰 컴포넌트

### 뷰 컴포넌 통신 방법 (event emit)
* app.js
```js
Vue.component('sibling-component', {
    props: ['propsdata'],
    template: '<p>{{ propsdata }}</p>',
    methods: {
        clickBtn: function() {
            this.$emit('change', 100);
        }
    }
});
<!-- ... -->
data: {
    anotherMessage: 'Hello Another'    
},
methods: {
    changeStr: function(value) {
        this.message = value;
    }
}
```
* index.html
```js
<sibling-component v-bind:propsdata="anotherMessage" v-on:change="changeStr"></sibling-component>
```

### 뷰 HTTP 통신 라이브러리
* axios
```js
axios.get(url).then(function(response) {
    // 데이터 호출 성공 시 실행 로직
}).catch(function(error) {
    // 데이터 호출 실패 시 실행 로직
});
```

### 뷰 템플릿 문법
```js
<h1>{{ msg }}</h1>

<!-- html(위)에서와 script(아래)에서의 문법 -->

export default {
    name: 'HelloWorld',
    data: {
        msg: String
    }
}
```

### 뷰 CLI
- 뷰로 빠르게 프로젝트를 구성하고 프로토 타이핑을 하고 싶을 때 사용하는 CLI 도구
- 뷰 cli 설치 (node 설치 후 진행)
```js
버전 3.x
npm install -g @vue/cli

버전 2.9
npm install vue-cli
```
- 뷰 cli로 프로젝트 생성
```js
버전 3.x
vue create 프로젝트 명

버전 2.9
vue init webpack-simple 파일 경로
```


