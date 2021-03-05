# 뷰 CLI

- 뷰로 빠르게 프로젝트를 구성하고 프로토 타이핑을 할 때 사용하는 CLI 도구

### 뷰 CLI 설치

- Node.js 설치 후 NPM(Node Package Manager)을 이용하여 뷰 CLI 설치

```js
버전 3.x
npm install -g @vue/cli

버전 2.9
npm install vue-cli
```

### 뷰 CLI로 프로젝트 생성 명령어

```js
버전 3.x
vue create helloworld
```

```js
버전 2.9
vue init webpack-simple 파일 경로
```

- 뷰 CLI 2.9의 프로젝트 생성 방식은 깃헙 레포지토리에 등록된 폴더와 파일을 그대로 다운로드.
- 뷰 CLI 3.0은 뷰 플러그인을 이용하여 필요한 기능들을 추가해 나가는 방식.
