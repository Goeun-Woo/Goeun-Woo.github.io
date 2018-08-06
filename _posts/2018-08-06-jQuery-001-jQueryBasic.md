---
layout: post
title: jQuery 객체 기본
categories:
  - jQuery
excerpt_separator:  <!--more-->

---

### 1. jQuery 객체 호출하기

---

- $()
- jquery()

### 2. jQuery 객체 생성하기

---

> 2.1 문서객체 선택하기
>
> - CSS 선택자 사용하기

```
$("h1");
```

---

> 2.2 문서객체 생성하기
>
> - 태그형태의 문자열 사용하기

```
$("<h1></h1>");
```

---

> 2.3 문서객체 삽입하기
>
> - querySelector() 사용하기

```
var header = document.querySelector("h1");
$(header);
```

---

### 3. jQuery 함수 기본

---

> 3.1 CSS 함수 : 문서객체를 CSS 속성을 사용하여 스타일링 할 수 있는 함수
>
> - 첫번째 인자 : CSS 속성
> - 두번째 인사 : 값

```
$("h1").css("color","red");
```

---

> 3.2 html 함수 : 문서객체 내부에 글자를 삽입할 수 있는 함수
>
> - 첫번째 인자 : 삽입할 텍스트

```
$("h1").html("안녕하세요") //<h1> 안녕하세요 </h1>
```

---

> 3.3 appendTo () : 인자로 입력받은 문서 객체 하위에 해당 문서객체를 위치시키는 함수
>
> - 첫번째 인자 : 상위 문서 객체

```
$("<h1></h1>").appendTo("body").html("Hello world");
// <body> <h1> Hello world </h1> </body>
```
