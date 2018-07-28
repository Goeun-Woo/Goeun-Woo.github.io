---
layout: post
title: Javascript - 객체 (객체와 관련된 키워드)
categories:
  - Javascript
excerpt_separator:  <!--more-->

---

---

##### 1. in 키워드

> `문자열 in 객체` 형태로 작성
> 객체 내부에 해당 문자열을 가지고 있는 속성이 있는지 확인
> 결과값 boolean 형태로 리턴
> 속성이 존재하면 'true', 속성이 존재하지 않으면 'false' 출력

```
var student = {
  name : '우고은',
  kor : '96',
  eng : '98',
  math : '94',
  sci : '90'
};

var key = "kor";
"name" in student;  //true
key in student; // true
// 식별자로서 사용하는경우 변수로 선언되어있어야 함."kor"로 인식되어 true 출력

"sex" in student; // false
```

##### 2. with 키워드

> `with (객체이름) { 해당 구문 안에서는 속성명으로만 호출 가능}` 형태로 작성
> 복잡하게 사용해야 하는 코드를 짧게 줄여주는 코드

```
var output= '';
with (student){
  output += name;
  output += kor;
  }
 console.log(output); //우고은 96
```
