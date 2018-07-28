---
layout: post
title: Javascript - 객체지향 기본 2 (Prototype)
categories:
  - Javascript
excerpt_separator:  <!--more-->

---

### 1. Prototype

- Javascript => 프로토타입 기반의 객체지향 프로그래밍
- IE => 프로토타입 지원
- 최신 웹브라우저 => 클래스, 프로토타입 지원

##### 1.1 생성자 함수 선언

> **1.1.1 생성자함수 만들기**
> 생성자 함수는 선언할 때 생성자 함수 이름을 **대문자**로 선언해야 함.

```
function Student(이름,국어,영어,수학){
  this.이름=이름;
  this.국어=국어;
  this.영어=영어;
  this.수학=수학;
}
```

> **1.1.2 모든 객체가 공유하는 기능**
 > `prototype`키워드를 사용하여 **<u>생성자 함수 밖에서 선언</u>**
 > `생성자함수이름.prototype.함수이름 = function () {...}` 형태로 작성
> prototype 으로 선언된 기능들을 모든 객체가 공유하게 됨

```
function Student(이름,국어,영어수학) { ... }

//

Student.prototype.getSum = function () {
     return this.국어 + this.영어 + this.수학;
}
Student.prototype.getAvg = function () {
    return this.getSum() / 3;  
}
Student.prototype.toString = function () {
    return output = this.이름 + "\t" + this.getSum() + "\t" + this.getAvg() + "\n";
}
```

##### 1.2 인스턴스 생성하기

> 인스턴스를 생성할 때 `new 생성자함수명(속성값,속성값,...)` 형태로 작성

```
var students=[];
students.push(new Student('우고은',80,90,78));
students.push(new Student('우고은',70,90,78));
students.push(new Student('우고은',60,90,78));
students.push(new Student('우고은',50,90,78));
```

##### 1.3 출력부

> 기존과 동일

```
var output= '이름\t총합\t평균\n';
for(var k=0; k<students.length; k++){
  output+= students[k].toString();
}
console.log(output);
```
