---
layout: post
title: Javascript - 객체지향 기본 3 (Class)
categories:
  - Javascript
excerpt_separator:  <!--more-->

---

### 1. Class

- 프로토타입의 자바스크립트 > 클래스 기반 객체지향(대세)으로 변화하는 중

##### 1.1 클래스 선언

> **1.1.1 클래스 선언하기**
> 클래스는 선언할 때 클래스명을 **대문자**로 선언해야 함.
> 클래스 내부에 생성자(constructor) 선언

```
class Student {
  constructor(이름,국어,영어,수학){
  this.이름=이름;
  this.국어=국어;
  this.영어=영어;
  this.수학=수학;
  }
```

> **1.1.2 모든 객체가 공유하는 기능**
 > `생성자 함수 밖에서 공유할 기능을 선언하는 prototype`과 달리, 클래스 내에서 선언함.
> 클래스 내에서 함수를 선언할때는 function 키워드를 사용하지 않아도 됨.

```
class Student {

    ...

    getSum() {
     return this.국어 + this.영어 + this.수학;
    }
    getAvg() {
      return this.getSum() / 3;  
    }
    toString() {
      return output = this.이름 + "\t" + this.getSum() + "\t" + this.getAvg() + "\n";
    }
}
```

##### 1.2 인스턴스 생성하기

> 프로토타입과 동일
> `new 생성자함수명(속성값,속성값,...)` 형태로 작성

```
var students=[];
students.push(new Student('우고은',80,90,78));
students.push(new Student('우고은',70,90,78));
students.push(new Student('우고은',60,90,78));
students.push(new Student('우고은',50,90,78));
```

##### 1.3 출력부

> 프로토타입과 동일

```
var output= '이름\t총합\t평균\n';
for(var k=0; k<students.length; k++){
  output+= students[k].toString();
}
console.log(output);
```
