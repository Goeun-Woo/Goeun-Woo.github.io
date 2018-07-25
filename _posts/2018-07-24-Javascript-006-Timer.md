---
layout: post
title: Javascript - 내장함수(Timer)
categories:
  - Javascript
excerpt_separator:  <!--more-->

---

### 내장함수 - 타이머

##### 1. 타이머를 설정하는 함수

###### 1.1 setTimeout()

- 특정 시간 후에 `함수를 1번만 실행`하는 함수
- 사용 매개변수

1.  function
2.  시간(milliseconds): 1000 밀리초 = 1 초

###### 1.2 setInterval()

- 특정 시간마다 `함수를 반복적으로 실행`하는 함수
- 사용 매개변수

1.  function
2.  시간(milliseconds): 1000 밀리초 = 1 초

##### 2. 타이머를 제거하는 함수

###### 2.1 clearTimeout()

- setTimeout()으로 설정한 타이머를 제거하는 함수.
- 사용 매개변수

1.  id

###### 2.2 clearInterval()

- setInterval()으로 설정한 타이머를 제거하는 함수.
- 사용 매개변수

1.  id

<p data-height="265" data-theme-id="0" data-slug-hash="NBjBEq" data-default-tab="js,result" data-user="cathy-go-eun-woo" data-pen-title="NBjBEq" class="codepen">See the Pen <a href="https://codepen.io/cathy-go-eun-woo/pen/NBjBEq/">NBjBEq</a> by Cathy Go Eun Woo (<a href="https://codepen.io/cathy-go-eun-woo">@cathy-go-eun-woo</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script src="https://static.codepen.io/assets/embed/ei.js"> </script>
