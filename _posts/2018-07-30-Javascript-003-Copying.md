---
layout: post
title: Javascript - 값복사와 참조복사
categories:
  - Javascript
excerpt_separator:  <!--more-->

---

##### 1. 기본 자료형(숫자,Bool,문자열) - 값 복사

- **값 복사(깊은 복사) : 할당된 데이터 값을 복사**
- 기본 자료형은 가볍기 때문에 실질적인 데이터 값을 복사
- clone

```
var originalValue = 10;
var newValue = originalValue; // newValue = 10

originalValue=273;  //originalValue 값 변경

document.write(originalValue);	// originalValue = 273
document.write(newValue);	// newValue = 10
```

##### 2. 특수자료형 (객체,배열, ...) - 참조 복사

- **참조복사 : 자료형에 할당된 주소값(참조)을 복사**
- 배열 내부에 있는 `메모리 주소`가 복사됨`
- 복사된 배열의 값이 동일하게 변경됨

```
var originalArray = [1,2,3,4];  //주소값 : 0x10
var newArray = originalArray;   //주소값 : 0x10

originalArray[0] = 273; // 원본 배열의 0번째 값 변경

document.write(originalArray);
// originalArray = [273,2,3,4]

document.write(newArray);
// newArray = [273,2,3,4]
```

##### 3. 배열을 값복사로 사용하고 싶을 때

- 새로운 배열을 생성하여 원본 배열의 데이터 값을 복사
- 주소값이 다르기 때문에 영향을 받지 않음.

```
var orgArr=[1,2,3,4];
var newArr=[];	//새로운 배열 생성

for(var i=0; i<orgArr.length; i++){
  newArr[i] = orgArr[i];
}	//배열의 값 복사

orgArr[0] = 223; // 원본 배열의 0번째 값 변경

document.write(orgArr);	//orgArr = [223,2,3,4]
document.write(newArr);	//newArr = [1,2,3,4]
```

<p data-height="265" data-theme-id="0" data-slug-hash="VBrQoY" data-default-tab="js,result" data-user="cathy-go-eun-woo" data-pen-title="Javascript : 값복사와 참조복사" class="codepen">See the Pen <a href="https://codepen.io/cathy-go-eun-woo/pen/VBrQoY/">Javascript : 값복사와 참조복사</a> by Cathy Go Eun Woo (<a href="https://codepen.io/cathy-go-eun-woo">@cathy-go-eun-woo</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script src="https://static.codepen.io/assets/embed/ei.js"> </script>
