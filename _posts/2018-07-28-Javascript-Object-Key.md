---
layout: post
title: Javascript - 객체 (속성 추가와 제거)
categories:
  - Javascript
excerpt_separator:  <!--more-->

---

---

##### 1. 정적으로 속성 추가하기

> 객체 내부에서 직접 추가

```
var student = {
이름 : "우고은"
	};
console.log(student); // 이름:'우고은'
```

##### 2. 동적으로 속성 추가하기

> 객체 외부에서 속성 추가  
> `객체명.추가할 속성명 = '추가할 속성 값'` 입력

```
student.성별 = '여자';
console.log(student); // 이름:'우고은', 성별:'여자'
```

##### 3. 속성 제거하기

> `delete 객체명.속성명` 키워드 이용

```
delete student.이름;

console.log(student); // 성별:'여자'
```

##### 4. toString() 메서드

> 자바스크립트의 모든 객체들이 내장하고 있는 함수

```
student.toString = () =>{
  return '안녕하세요';
}
console.log(student); // '안녕하세요', 성별 : '여자'
```
