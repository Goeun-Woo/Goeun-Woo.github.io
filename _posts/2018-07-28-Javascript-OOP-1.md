---
layout: post
title: Javascript - 객체지향 기본 1
categories:
  - Javascript
excerpt_separator:  <!--more-->

---

#### 1. 학생들의 성적 총점과 평균을 출력하는 코드 작성하기

##### 1.1 배열에 인스턴스 추가하기

```
var students=[];
students.push({ 이름: '우고은', 국어:80, 영어:90, 수학:78 });
students.push({ 이름: '김이박', 국어:90, 영어:92, 수학:72 });
students.push({ 이름: '박이김', 국어:70, 영어:94, 수학:98 });
students.push({ 이름: '이박김', 국어:78, 영어:95, 수학:86 });
```

##### 1.2 점수의 <u>총합</u>과 <u>평균</u> 출력하기

> 1.2.1. For 문 내부에 변수(total, avg) 선언하기

```
var output= '이름\t총합\t평균\n';
for(var i=0;i<students.length;i++){
  var total = students[i].국어 + students[i].영어 + students[i].수학;
  var avg = total/3;
  output += students[i].이름 + "\t" + total + "\t" + avg + "\n";
}
console.log(output);
```

> 1.2.2. 객체 내부에 메서드 삽입하기

```
for(var j=0;j<students.length; j++){
  students[j].total = function() {
   return this.국어 + this.영어 + this.수학;
  }
  students[j].avg = function() {
    return this.total() / 3;
  }
  students[j].toString = function(){
    return output = this.이름 + "\t" + this.total() + "\t" + this.avg() + "\n";
  }
}
```

##### 1.3 출력하기

```
var output= '이름\t총합\t평균\n';
for(var k=0; k< students.length; k++){
  output+= students[k].toString();
}
  console.log(output);
```

##### 1.4 한계

- 서로 다른 기능을 하는 코드들이 혼재되어 있어 코드의 가독성이 떨어짐
- 이를 위해 기능 별로 코드를 분리하여 코드의 가독성을 높이고자 함.

<p data-height="265" data-theme-id="0" data-slug-hash="yqPejO" data-default-tab="js,result" data-user="cathy-go-eun-woo" data-pen-title="Javascript 객체지향 기본[1] : 객체를 만드는 함수" class="codepen">See the Pen <a href="https://codepen.io/cathy-go-eun-woo/pen/yqPejO/">Javascript 객체지향 기본[1] : 객체를 만드는 함수</a> by Cathy Go Eun Woo (<a href="https://codepen.io/cathy-go-eun-woo">@cathy-go-eun-woo</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script src="https://static.codepen.io/assets/embed/ei.js"> </script>
----

#### 2. 기능 별로 코드 분리해보기

- 동일한 기능을 하는 부분들을 분리하여 따로 작성함으로써, 협업 및 코드 관리가 용이

##### 2.1 객체 선언

> 2.1.1 객체의 속성 정의

```
function createStudent(이름,국어,영어,수학){
  var object = {
    // 2.1.1 속성 정의
    //키로 선언되는 값 : 매개변수의 값
    이름 : 이름,
    국어 : 국어,
    영어 : 영어,
    수학 : 수학
  };
```

> 2.1.2 객체의 메서드 정의  
> createStudent() 함수 내부에 메서드 정의

```
 function createStudent(이름,국어,영어,수학){

    ...
    // 2.1.2 메서드 정의
    object.total = function() {
   		return this.국어 + this.영어 + this.수학;
  	}
  	object.avg = function() {
    	return this.total() / 3;
  	}

  	object.toString = function(){
    	return output = this.이름 + "\t" + this.total() + "\t" + this.avg() + "\n";
  	}
  	return object;
	}
}
```

##### 2.2 student 객체 생성하기

> createStudent()로 배열에 객체 추가

```
var students=[];
students.push(createStudent('우고은',80,90,78));
students.push(createStudent('우고은',70,90,78));
students.push(createStudent('우고은',60,90,78));
students.push(createStudent('우고은',50,90,78));
```

##### 2.3 출력하기

> toString() 함수 이용

```
var output= '이름\t총합\t평균\n';
for(var k=0; k<students.length; k++){
  output+= students[k].toString();	//toString()함수 이용
}
console.log(output);
```

##### 2.4 한계

- 객체를 생성할 때 마다 `같은 기능을 하는 메서드`를 객체를 생성할 때 마다`중복하여 정의`하게 됨
- 메모리 낭비 발생
- 이를 해결하기 위해 **객체지향 프로그래밍 방식의 prototype** 개념이 도입됨.

<p data-height="343" data-theme-id="0" data-slug-hash="rrYeNG" data-default-tab="js" data-user="cathy-go-eun-woo" data-pen-title="Javascript 객체지향 기본[1] : 기능 별 코드 분리하기" class="codepen">See the Pen <a href="https://codepen.io/cathy-go-eun-woo/pen/rrYeNG/">Javascript 객체지향 기본[1] : 기능 별 코드 분리하기</a> by Cathy Go Eun Woo (<a href="https://codepen.io/cathy-go-eun-woo">@cathy-go-eun-woo</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script src="https://static.codepen.io/assets/embed/ei.js"> </script>
