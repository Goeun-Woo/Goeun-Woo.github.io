---
layout: post
title: Javascript - HTML 엘리먼트 가져오기, 삭제하기, 이동하기 
categories:
  - Javascript
excerpt_separator:  <!--more-->

---

### 1. 엘리먼트 가져오기

##### 1.1 queryselector

> CSS 선택자 형식으로 엘리먼트를 가져올 수 있다.  
> 가져오는 엘리먼트는 1 개

```
<h1 id="hello-a" className = "test"> Hello wolrd ! A </h1>

<script>

document.getElementById("hello-a")
= document.querySelector("#hello-a")

document.getElementsByTagName("h1")
= document.querySelector("h1")

document.getElementsbyClassName("test")
= document.querySelector(".test");

</script>
```

##### 1.2 querySelectorAll

> CSS 선택자 형식으로 엘리먼트를 배열 형태로 가져온다.  
> 가져오는 엘리먼트 복수 개

```
<h1> Hello world ! A </h1>
<h1> Hello world ! B </h1>
<h1> Hello world ! C </h1>

<script>

var arr = document.querySelectorAll("h1");

for (var i=0; i<arr.length; i++){
	arr[i].style.color = "red";
}

</script>
```

<p data-height="265" data-theme-id="0" data-slug-hash="oMyPav" data-default-tab="html" data-user="cathy-go-eun-woo" data-pen-title="Javascript : querySelectorAll()" class="codepen">See the Pen <a href="https://codepen.io/cathy-go-eun-woo/pen/oMyPav/">Javascript : querySelectorAll()</a> by Cathy Go Eun Woo (<a href="https://codepen.io/cathy-go-eun-woo">@cathy-go-eun-woo</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script src="https://static.codepen.io/assets/embed/ei.js"> </script>

### 2. `<style> vs <script>`

- Script 태그 안에서 스타일 속성을 사용할 때 몇가지 규칙이 있음.

##### 2.1 pixel

> 2.1.1 style 태그

```
<style>
h1{

height : 10px;

}
</style>
```

> 2.1.2 script 태그 : px 단위에 따옴표

```
<script>

var header = document.querySelector("h1");
header.height = "10px"

</script>
```

##### 2.2 특수기호 '-'

> 2.2.1 style 태그

```
<style>
h1{

font-family : 'sans-serif';

}
</style>
```

> 2.2.2 script 태그 : '-'으로 끊긴 단어의 첫 글자를 대문자로 변경

```
<script>

var header = document.querySelector("h1");
header.fontFamily = "sans-serif";
header.backgroundImage
header.boxSizing
header.listStyle
...

</script>
```

### 3. 엘리먼트 제거하기

- 준비물 : 제거하고자하는 엘리먼트 + 그 엘리먼트의 부모 객체

##### 3.1 제거방법 1 : removeChild()

```
var header = document.querySelector("h1");	//제거하고자 하는 엘리먼트
var body = document.body;	// 그 엘리먼트의 부모 객체
body.removeChild(header);
```

##### 3.2 제거방법 2 : parentNode.removeChild()

- 더 많이 사용되는 방법

```
var header = document.querySelector("h1");	//제거하고자 하는 엘리먼트
header.parentNode.removeChild(header);
```

### 4. 엘리먼트 이동하기

- appendChild() 이용하기

<p data-height="265" data-theme-id="0" data-slug-hash="rrKqaR" data-default-tab="html" data-user="cathy-go-eun-woo" data-pen-title="Javascript : appendChild()" class="codepen">See the Pen <a href="https://codepen.io/cathy-go-eun-woo/pen/rrKqaR/">Javascript : appendChild()</a> by Cathy Go Eun Woo (<a href="https://codepen.io/cathy-go-eun-woo">@cathy-go-eun-woo</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script src="https://static.codepen.io/assets/embed/ei.js"> </script>
