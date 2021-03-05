# 실무에서 주의해야 할 Vue.js 특성

### Router Initialization
- router.start replaced
```js
router.start({
  template: '<router-view></router-view>'
}, '#app')
```

- vue 인스턴스에 라우터 속성 전달
```js
new Vue({
  el: '#app',
  router: router,
  template: '<router-view></router-view>'
})
```
or
```js
new Vue({
  el: '#app',
  router: router,
  render: h => h('router-view')
})
```
