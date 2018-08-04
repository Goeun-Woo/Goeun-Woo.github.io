---
layout: post
title: Javascript - BOM (Browser Object Model)
categories:
  - Javascript
excerpt_separator:  <!--more-->

---

- 브라우저 객체 모델
- 웹브라우저에서 사용하는 자바스크립트에서만 사용할 수 있는 객체 모델
- 모든 브라우저 객체들은 window 객체에 귀속
 
 ```
   - BOM 객체의 종류

      window.location
      window.navigator
      window.history
      window.screen
      window.documqent

```

----

### 2. window.onload( )  
- HTML 읽는 순서 : 위에서 아래로 읽음
- HTML > HEAD > TITLE > SCRIPT > BODY > ...
- document.querySelecor("") :  css selector를 통해 DOM을 찾을 수 있음.
- head 태그 안의 script에 작성할 경우 body에 있는 선택자에 선택되지 않음.

```
<html>
  <head>
    <title>Document Object Model</title>
    <script>
      // 에러 발생, 이 '<script></script>' 태그 내부에서 'h1' 태그를 찾을 수 없습니다.
        document.querySelector("h1").style.color = "red";
    </script>
  </head>
  <body>
    <h1>Process -1 </h1>
    <script>document.write('script test 2')</script>
    <h2>Process -2</h2>
    <script>document.write('script test 2')</script>
  </body>
</html>
```

- 해결방법 1 : `script 태그를 body 태그 안으로` 옮긴다

```
<body>
    <h1>Process -1 </h1>
    <script>document.write('script test 2')</script>
    <h2>Process -2</h2>
    <script>document.write('script test 2')</script>

     <script>
     //script 태그를 body 태그 안으로 이동
        document.querySelector("h1").style.color = "red";
    </script>
  </body>
```

- 해결방법 2 : head 태그 안의 script 에 작성할 때, `window.onload( )`(화면이 로드될 때 함수 실행) 이벤트를 사용한다.

```
  <head>
    <title>Document Object Model</title>
    <script>
  // window.onload() 이벤트 사용
  	window.onload = () => { document.querySelector("h1").style.color = "red" };
    </script>
  </head>
```
