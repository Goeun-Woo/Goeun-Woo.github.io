---
layout: post
title: Javascript - Object 객체
categories:
  - Javascript
excerpt_separator:  <!--more-->

---

- 자바스크립트에 내장되어있는 모든 기본 객체들의 부모
- Object 객체가 가지고 있는 기능들을 모든 객체(Number 객체 ... )들이 상속을 받아 활용

##### 1. Object 객체기능

> 자주 사용되는 편은 아님.

```
constructor
hasOwnProperty
isPrototypeOf
propertyIsEnumerable
toLocaleString
toString,valueOf
```

##### 2. Constructor 를 활용한 자료형 구분

- 자료형이 다른 두 데이터를 비교하고 싶을 때
- typeOf 는 **데이터 타입이 다를 때 비교가 불가능**
- 객체형 데이터도 숫자로 취급하여 데이터 타입을 확인하고 싶을 때,
- **constructor(생성자 함수)를 활용** : 자바 스크립트 모든 객체가 가지고 있는 메서드
- constructor : 자기 자신을 생성할 때 사용하는 함수

```
function isNumber(value){
  return value.constructor === Number;
  //매개변수의 자료형이 숫자인지 판별
}

var primitiveNum=273;
var objectNum = new Number(273);

document.write(isNumber(primitiveNum)); //숫자(기본자료형) : true
document.write(isNumber(objectNum));  //숫자(객체자료형) : true
document.write(isNumber("string")); //문자열 :false
document.write(isNumber(false));  //boolean : false
```

<p data-height="265" data-theme-id="0" data-slug-hash="bjYvpo" data-default-tab="js,result" data-user="cathy-go-eun-woo" data-pen-title="Javascript : Object 객체" class="codepen">See the Pen <a href="https://codepen.io/cathy-go-eun-woo/pen/bjYvpo/">Javascript : Object 객체</a> by Cathy Go Eun Woo (<a href="https://codepen.io/cathy-go-eun-woo">@cathy-go-eun-woo</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script src="https://static.codepen.io/assets/embed/ei.js"> </script>
