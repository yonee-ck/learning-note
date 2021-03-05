# Slot

- 컴포넌트의 재사용성을 높여주는 기능. 특정 컴포넌트에 등록한 하위 컴포넌트의 마크업을 확장하거나 재정의할 수 있다.

### 슬롯 코드 형식

- slot 코드를 쓰는 쪽

```js
<template>
  <div>
    <slot name="header" />
    <slot name="content" />
  </div>
</template>
```

- slot 코드

```js
<template>
  <button-tab>
    <h1 slot="header">First Header</h1>
    <div slot="content">Tab Contents #1</div>
  </button-tab>
  <button-tab>
    <h1 slot="header">Second Header</h1>
    <div slot="content">Tab Contents #2</div>
  </button-tab>
  <button-tab>
    <h1 slot="header">Third header</h1>
    <div slot="content">Tab Contents #3</div>
  </button-tab>
</template>
```

- 슬롯을 사용하면 컴포넌트의 특정 마크업 영역을 재정의하여 같은 컴포넌트를 각기 다르게 표현할 수 있다.

### 참고

Vue.js 2.6 버전부터 Named Slots 문법 변경

```js
<!-- 기존(2.5 이하) -->
<template slot="header">
  <h1>First Header</h1>
</template>

<!-- 이후(2.6 이상) -->
<template v:slot:header>
  <h1>First Header</h1>
</template>
```
