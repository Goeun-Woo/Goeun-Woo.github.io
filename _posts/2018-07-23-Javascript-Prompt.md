---
layout: post
title: Javascript - Prompt 예제
categories:
  - Javascript
excerpt_separator:  <!--more-->

---

#### Prompt 예제 01

###### `prompt 함수`로 문자열을 입력받아 `"안녕"이 들어가 있으면 "안녕하세요"`,`"잘자" 또는 "잘 자"를 입력하면 "안녕히 주무세요"`를 출력하는 코드를 작성하세요.

```
let msg= prompt();

if(msg=='안녕'){
//입력 값이 '안녕'인 경우
  document.write('안녕하세요');
  //'안녕하세요'출력
}
else if(msg=='잘자' || msg == '잘 자'){
// 입력값이 '잘자' 또는 '잘 자' 인경우
	document.write('안녕히 주무세요');
	//'안녕히 주무세요' 출력
}
```

<p data-height="361" data-theme-id="0" data-slug-hash="WKpydm" data-default-tab="js,result" data-user="cathy-go-eun-woo" data-pen-title="Javascript : Prompt 예제 01" data-preview="true" class="codepen">See the Pen <a href="https://codepen.io/cathy-go-eun-woo/pen/WKpydm/">Javascript : Prompt 예제 01</a> by Cathy Go Eun Woo (<a href="https://codepen.io/cathy-go-eun-woo">@cathy-go-eun-woo</a>) on <a href="https://codepen.io">CodePen</a> . </p>
<script src="https://static.codepen.io/assets/embed/ei.js"> </script>
----

#### Prompt 예제 02

###### 문자열을 입력받아 `"안녕"이라는 글자가 들어있지 않으면 "인사를 안 하다니"`라고 출력하는 코드를 작성하세요.

###### <p style="color: #376092">`내 풀이방법 : if문을 사용하여 indexOf의 반환값이 -1일 때(해당 글자가 없을 때) 코드 출력`</p>

```
let two = prompt();
let example = two.indexOf("안녕");

if(example == -1){
document.write("인사를 안 하다니");
}
```

<p data-height="301" data-theme-id="0" data-slug-hash="mjWKLL" data-default-tab="js,result" data-user="cathy-go-eun-woo" data-pen-title="Javascript : Prompt 예제 02" data-preview="true" class="codepen">See the Pen <a href="https://codepen.io/cathy-go-eun-woo/pen/mjWKLL/">Javascript : Prompt 예제 02</a> by Cathy Go Eun Woo (<a href="https://codepen.io/cathy-go-eun-woo">@cathy-go-eun-woo</a>) on <a href="https://codepen.io">CodePen</a> . </p>
<script src="https://static.codepen.io/assets/embed/ei.js"> </script>
----

#### Prompt 예제 03

###### 숫자를 입력받아 `4로 나눌 수 있는 숫자라면 "4로 나눌 수 있는 숫자입니다"`를 출력하는 코드를 출력하세요

###### <p style="color: #376092">`내 풀이방법 : if문을 사용하여 나머지가 0일 때 코드 출력`</p>

```
let value = prompt();

if((value%4)==0){
document.write(`${value}는 4로 나눌 수 있는 숫자입니다.`);
}
```

<p data-height="265" data-theme-id="0" data-slug-hash="NBpzzJ" data-default-tab="js,result" data-user="cathy-go-eun-woo" data-pen-title="Javascript : Prompt 예제 03" data-preview="true" class="codepen">See the Pen <a href="https://codepen.io/cathy-go-eun-woo/pen/NBpzzJ/">Javascript : Prompt 예제 03</a> by Cathy Go Eun Woo (<a href="https://codepen.io/cathy-go-eun-woo">@cathy-go-eun-woo</a>) on <a href="https://codepen.io">CodePen</a> . </p>
<script src="https://static.codepen.io/assets/embed/ei.js"> </script>
----

#### Prompt 예제 04

###### 숫자를 입력받아 `양수라면 "양수입니다"`, `음수라면 "음수입니다."`, `0이라면 "0입니다"`를 출력하는 코드를 작성하세요.

```
let num = prompt();

if(num>0){
document.write("양수입니다.");
}
else if(num<0){
document.write("음수입니다.");
}
else{
document.write("0 입니다.");
}
```

<p data-height="265" data-theme-id="0" data-slug-hash="XBMYPK" data-default-tab="js,result" data-user="cathy-go-eun-woo" data-pen-title="Javascript : Prompt 예제 04" data-preview="true" class="codepen">See the Pen <a href="https://codepen.io/cathy-go-eun-woo/pen/XBMYPK/">Javascript : Prompt 예제 04</a> by Cathy Go Eun Woo (<a href="https://codepen.io/cathy-go-eun-woo">@cathy-go-eun-woo</a>) on <a href="https://codepen.io">CodePen</a> . </p>
<script src="https://static.codepen.io/assets/embed/ei.js"> </script>

---
