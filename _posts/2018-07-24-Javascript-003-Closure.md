---
layout: post
title: Javascript - Closure
categories:
  - Javascript
excerpt_separator:  <!--more-->

---

### 클로저

##### 함수 내부에서 변수 선언

###### 1. 함수안의 함수에 변수를 넣어 놓고 편리하게 참조하는 것

###### 2. 함수 안에 있는 변수는 한번 쓰면 메모리에서 삭제하므로, 함수안의 함수에 변수를 <u>의도적으로</u> 심어놓는 것

###### 3. 함수가 한번 호출되어도 변수가 유지됨.

##### 클로저 장점

###### 1. `함수 내에서 선언된 변수들은 함수 밖에서 접근할 수 없으므로`, `변수를 보호`할 수 있음.

###### 2. 함수 내에서 선언된 변수들이 `함수를 호출할 때마다 생성`되므로, <u>한번에 여러 변수를 선언하고 활용할 수 있음.<u>

<p data-height="265" data-theme-id="0" data-slug-hash="jpmpEg" data-default-tab="js,result" data-user="cathy-go-eun-woo" data-pen-title="Javascript : Closure" class="codepen">See the Pen <a href="https://codepen.io/cathy-go-eun-woo/pen/jpmpEg/">Javascript : Closure</a> by Cathy Go Eun Woo (<a href="https://codepen.io/cathy-go-eun-woo">@cathy-go-eun-woo</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script src="https://static.codepen.io/assets/embed/ei.js"> </script>
