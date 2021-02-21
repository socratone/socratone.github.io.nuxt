---
title: VueJS 시작하기
description: VueJS를 간단히 실행해봅니다.
img: vuejs
alt: javascript icon
author: socratone
category: vuejs
---

# VueJS 시작하기

React에 비해 Vue를 실행하는 것은 너무 쉽다.  
아래 코드만 입력하면 끝이다.

```html
<!DOCTYPE html>
<html>
<head>
  <title>My first Vue app</title>
  <script src="https://unpkg.com/vue@next"></script>
</head>
<body>
  <div id="root">
    {{ message }}
  </div>

  <script>
    const App = {
      data() {
        return {
          message: 'Hello World!'
        }
      }
    }

    Vue.createApp(App).mount('#root')
  </script>
</body>
</html>
```

먼저 head 내부에서 vue를 위한 cdn을 불러오고 나머지는 순수 자바스크립트를 이용한 구현과 유사하다.  
위 예제를 입력하면 message에 'Hello World!'가 들어가 빈화면에 Hello World!가 나타나게 된다.

이제 변수 app이 참조하는 인스턴스를 통해서 DOM을 조작할 수 있다.  
console 창을 열고 app.message에 다른 문자를 넣으면 바뀌는 것을 확인할 수 있다.  
이처럼 Vue는 DOM을 간단히 다룰 수 있게 해준다.

아래는 컴포넌트를 이용한 예제다.

```html
<!DOCTYPE html>
<html>
<head>
  <title>My first Vue app</title>
  <script src="https://unpkg.com/vue@next"></script>
</head>
<body>
  <div id="root">
    <my-component></my-component>
  </div>
  
  <script>
    // Create a Vue application
    const app = Vue.createApp({})
  
    // Define a new global component called button-counter
    app.component('my-component', {
      data() {
        return {
          message: 'Hello World!'
        }
      },
      template: `
        <p>{{ message }}</p>`
    })
  
    app.mount('#root')
  </script>
</body>
</html>
```