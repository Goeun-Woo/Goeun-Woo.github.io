---
layout: post
title: Javascript - DOM (Document Object Model)
categories:
  - Javascript
excerpt_separator:  <!--more-->

---

- 문서 객체 모델
- 웹브라우저가 HTML 페이지를 인식하는 방법
- 태그 = 요소 = 문서객체
- 각각의 태그 --> 요소 노드
- 실제 입력되는 텍스트 --> 텍스트 노드

---

##### 1.1 요소 태그 생성

- body 태그 내부에 태그 생성하기

```
// h1 요소 생성
var header = document.createElement("h1");
var image = document.createElement("img");

// body 태그에 붙이기
document.body.appendChild(header);
document.body.appendChild(image);
```

- 결과

```
<html>
...
	<body>

    	<h1></h1>
		<img></img>

    </body>
</html>
```

---

##### 1.2 텍스트 노드 생성

- 요소 태그 안에 텍스트 삽입하기

```
// 텍스트노드 생성
var textNode = document.createTextNode("Hello world");
// 텍스트 값 삽입
header.appendChild(textNode);
```

> 결과

```
<html>
...
	<body>

    	<h1>Hello world</h1>
		<img></img>

    </body>
</html>
```

---

##### 1.3 속성 태그 생성

- 속성 태그 생성 : createAttribute()

```
// 속성 태그 생성
var attr = document.createAttribute("src");

// 속성 값 삽입
attr.value = "http://placehold.it/300x300"
```

---

##### 1.4 간단하게 사용하기

> 1.4.1 header.innerHTML 내부에 텍스트 입력하기

```
//header.innerHTML = "Hello world";
```

> 1.4.2 setAttribute() 사용하기

```
image.setAttribute("src","http://placehold.it/300x300")
```

> 1.4.3 선언한 attribute 바로 가져오기

```
image.src = "http://placehold.it/300x300"
```

<p data-height="265" data-theme-id="0" data-slug-hash="ejyWNg" data-default-tab="result" data-user="cathy-go-eun-woo" data-pen-title="Javascript : DOM" class="codepen">See the Pen <a href="https://codepen.io/cathy-go-eun-woo/pen/ejyWNg/">Javascript : DOM</a> by Cathy Go Eun Woo (<a href="https://codepen.io/cathy-go-eun-woo">@cathy-go-eun-woo</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script src="https://static.codepen.io/assets/embed/ei.js"> </script>
