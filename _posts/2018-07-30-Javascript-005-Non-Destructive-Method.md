---
layout: post
title: Javascript - 비파괴적 / 파괴적 메서드
categories:
  - Javascript
excerpt_separator:  <!--more-->

---

##### 1. 비파괴적 메서드 : 자신을 파괴시키지 않으면서 사용되는 메서드.

- string 객체 대부분의 메서드가 비파괴적 메서드
- 원래 변수를 변화시키지 않음.
- 결과값을 변경하려면 비파괴적 메서드를 호출한 변수를 다시 저장

```
var str = "hello world";
str.toUpperCase();
//toUppercase() : 비파괴적 메서드 , 원래 변수를 변화시키지 않음. 문자열을 대문자로 변환

document.write(str); //hello world

//결과값을 변화시키려면 아래 코드처럼 작성
str = str.toUpperCase(); // 비파괴적 메서드를 호출한 변수를 다시 저장
document.write(str); //HELLO WORLD
```

> 1.1 메서드 체이닝 (비파괴적 메서드) : 여러개의 메서드를 연속하여 호출

```
str = str
    .toLowerCase()
    .fontcolor("red")
    .anchor("test");

document.write(str);
```

##### 2. 파괴적 메서드 : 자기 자신을 변화시키는 메서드

- array 객체 대부분의 메서드가 파괴적 메서드
- 메서드 호출만으로 의미를 가짐 : 파괴적 메서드 호출 시 객체 내부의 값이 변경됨

```
var arr = [1,2,3,4,5];
arr.push(6);	// arr배열의 마지막 위치에 6 삽입
arr.push(7);	// arr배열의 마지막 위치에 7 삽입
arr.push(8);	// arr배열의 마지막 위치에 8 삽입
document.write(arr);  //[1,2,3,4,5,6,7,8]

arr.reverse();	//reverse() : 배열 순서를 거꾸로
document.write(arr); //[8,7,6,5,4,3,2,1]
```
