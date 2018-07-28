---
layout: post
title: Javascript - 객체 (기본)
categories:
  - Javascript
excerpt_separator:  <!--more-->

---

---

- 문자열, 숫자 bool, 객체, 함수, Undefined
- `배열의 자료형` 또한 `객체`

##### 1.객체 생성하기

> 객체 내부의 데이터는 `속성 : "속성 값"`형태로 입력  
> 속성 > 문자열 또는 식별자 형태로 입력 가능  
> 속성 값 > 키에 들어가는 데이터

```
  var object = {

    key : "value A ",
    key_B : "value B",
    key_C : "value C, value D"

  };
```

##### 2.객체 접근하기

> 객체 요소에 접근할 때, 배열과 비슷한 방법으로 요소에 접근할 수 있음.

```
var key ='key_B';

  document.write("object['key'] : " + object['key']); //키 값을 변수로서 활용할 경우 사용 => 'value A' 출력
  document.write("<br/>object.key : " + object.key);   // 일반적으로 사용하는 접근방법 => 'value A' 출력
  document.write("<br/>object[key] : " + object[key]+"<br/>");  // key를 "변수"로 인식, object['key_B'] => 'value B' 출력
```

##### 3.객체의 데이터를 반복문으로 출력하기.

```
  for (var i in object){
    //object.i => undefined 출력
    document.write("<br/>" + i + " : " + object[i]);
  }
```

<p data-height="380" data-theme-id="0" data-slug-hash="ce05777435058431760d18d74b839a6e" data-default-tab="result" data-user="cathy-go-eun-woo" data-pen-title="Javascript - 객체 01 기본" class="codepen">See the Pen <a href="https://codepen.io/cathy-go-eun-woo/pen/ce05777435058431760d18d74b839a6e/">Javascript - 객체 01 기본</a> by Cathy Go Eun Woo (<a href="https://codepen.io/cathy-go-eun-woo">@cathy-go-eun-woo</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script src="https://static.codepen.io/assets/embed/ei.js"> </script>
