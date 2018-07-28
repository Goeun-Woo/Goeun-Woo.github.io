---
layout: post
title: Javascript - 캡슐화 (Encapsulation)
categories:
  - Javascript
excerpt_separator:  <!--more-->

---

- 캡슐화 : 정보 은닉하기
- **객체의 자료와 행위를 하나로 묶고, 실제 구현내용을 외부에 감춘다.**
- 캡슐화 규칙 : 속성명을 밑줄로 시작하는 것

---

##### 캡슐화 방법 1. 밑줄(\_)로 시작하는 변수는 '절대 건드리지 말자'라는 약속!

- 한계점 : 개발자들의 언어 규칙일 뿐, 실제 자바스크립트 내에서 제한 할 수는 없음.

> **1.1 Rectangle 생성자 함수 선언**

```
function Rectangle(width, height){
  this._width = width; // width 변수는 건드리지 말자.
  this._height = height; // height 변수도 건드리지 말자.
}
```

> **1.2 메서드(프로토타입) 선언**

```
Rectangle.prototype.getArea = function (){
  return this._width * this._height;
}
```

> **1.3 인스턴스 생성 및 출력**

```
var rectangle = new Rectangle(5,7);
document.write('Area : ' + rectangle.getArea() );	// Area : 35
```

<p data-height="265" data-theme-id="0" data-slug-hash="wxPGyz" data-default-tab="js" data-user="cathy-go-eun-woo" data-pen-title="Javascript 캡슐화 1 : 밑줄로 시작하는 속성명" class="codepen">See the Pen <a href="https://codepen.io/cathy-go-eun-woo/pen/wxPGyz/">Javascript 캡슐화 1 : 밑줄로 시작하는 속성명</a> by Cathy Go Eun Woo (<a href="https://codepen.io/cathy-go-eun-woo">@cathy-go-eun-woo</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script src="https://static.codepen.io/assets/embed/ei.js"> </script>

---

##### 캡슐화 방법 2. 클로저를 활용하여 외부에서 변수에 접근할 수 없도록 하자.

- **Getter / Setter 이용하여 캡슐화하기**
- 내부에 코드를 작성하여 원래 변수를 보호하는 목적
- 자기 자신도 직접 접근이 불가능하기 때문에 getter 를 이용하여 접근
- 한계점 : 생성자 함수 안에 Getter/Setter 함수를 선언하므로 약간의 메모리 낭비가 발생
- 하지만, 완벽한 캡슐화가 가능하다.

> **2.1 Rectangle 생성자 함수 선언**  
> 생성자 함수 안에 Getter/Setter 선언

```
function Rectangle (width, height) {
  var _width = width;
  var _height = height;

  // 2.1.1 Getter
  	this.getWidth = function () { return _width; }
  	this.getHeight = function () { return _height; }

  // 2.1.2 Setter : 0보다 작은 수를 입력하면 값 세팅 불가 !
  	this.setWidth = function (value) {
    	if(value<=0){ return alert("0보다 작은 값은 넣을 수 없습니다."); }
    	_width=value;
  	}

  	this.setHeight = function (value) {
 		 if(value<=0){ return alert("0보다 작은 값은 넣을 수 없습니다."); }
    	_height=value;
   }

}
```

> **2.2 메서드(프로토타입) 선언**  
> 자기 자신도 직접 접근이 불가능 --> `getter` 를 이용하여 접근

```
Rectangle.prototype.getArea = function (){
  return this.getWidth() * this.getHeight();
}
```

> **2.3 인스턴스 생성 및 출력**

```
var rectangle = new Rectangle(5,7);
rectangle.setHeight(10); // 값 변경하기
document.write('Area : ' + rectangle.getArea() );	// Area : 50
```

<p data-height="265" data-theme-id="0" data-slug-hash="qyVazK" data-default-tab="js" data-user="cathy-go-eun-woo" data-pen-title="Javascript 캡슐화 2  : 클로저 사용" class="codepen">See the Pen <a href="https://codepen.io/cathy-go-eun-woo/pen/qyVazK/">Javascript 캡슐화 2  : 클로저 사용</a> by Cathy Go Eun Woo (<a href="https://codepen.io/cathy-go-eun-woo">@cathy-go-eun-woo</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script src="https://static.codepen.io/assets/embed/ei.js"> </script>
----
##### 캡슐화 방법 3. 혼합하기.
- (방법1) + (방법2) 혼합하여 사용
- 기존의 클로저 방식의 메모리 낭비 문제를 해결하기 위한 타협점
- **프로토 타입으로 캡슐화하기**

> **3.1 Rectangle 생성자 함수 선언**

```
function Rectangle (width, height) {
  this._width = width;
  this._height = height;
}
```

> **3.2 Getter/Setter 를 프로토타입으로서 선언**  
> 리턴 타입을 `this.속성명` 형태로 변환

```
  Rectangle.prototype.getArea = function (){
    return this._width * this._height;
  }

  Rectangle.prototype.getWidth = function () {
    return this._width;
  }

  Rectangle.prototype.getHeight = function () {
    return this._height;
  }

  Rectangle.prototype.setWidth = function (value) {
    if(value<=0) { return alert("0보다 작은 값은 넣을 수 없습니다."); }
    this._width = value;
  }

  Rectangle.prototype.setHeight = function (value) {
  if(value<=0) { return alert("0보다 작은 값은 넣을 수 없습니다."); }
    this._height = value;
   }
```

> **2.3 인스턴스 생성 및 출력**

```
var rectangle = new Rectangle(5,7);
rectangle.setHeight(20);	// 값 변경하기
document.write('Area : ' + rectangle.getArea() ); // Area : 100
```

<p data-height="265" data-theme-id="0" data-slug-hash="LBORKB" data-default-tab="js" data-user="cathy-go-eun-woo" data-pen-title="Javascript 캡슐화 3 : 혼합" class="codepen">See the Pen <a href="https://codepen.io/cathy-go-eun-woo/pen/LBORKB/">Javascript 캡슐화 3 : 혼합</a> by Cathy Go Eun Woo (<a href="https://codepen.io/cathy-go-eun-woo">@cathy-go-eun-woo</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script src="https://static.codepen.io/assets/embed/ei.js"> </script>
