---
layout: post
title: Javascript : ECMASCript 5,6 비교하기 (함수)
categories:
  - Javascript
excerpt_separator:  <!--more-->

---

#### 1. 함수 선언 방식
###### 1.1 ECMAScript 5

```
function power(n) {
  return n*n ;
}
```

###### 1.2 ECMAScript 6 : 화살표 함수(람다 식), IE에서 지원 불가능

```
var power = (n) => { n*n }; 	//코드가 한 줄일 경우 중괄호 {} 생략 가능
```

----

#### 2. 가변매개변수
###### 2.1 ECMAScript 5 : arguments 객체 사용
###### 2.2 ECMAScript 6 : 전개연산자(...) 사용

- 전개 연산자는 매개변수 마지막에 사용할 수 있음.

```
(...numbers,a,b) --> X
(a,b,...numbers) --> O
```

- 전개 연산자는 함수 당 하나씩만 사용할 수 있음.

```
var sumAll= (...numbers) => {
  var output = 0 ;
  for (var i=0;i<numbers.length ; i++){
    output += numbers[i];			// 매개변수로 들어온 모든 인자를 더하는 함수
  }
  document.write(output);
}
var array = [1,2,3,4,5,6,7,8];
sumAll.apply(null, array);  		//ECMAScript 5 : 다른 array 자체를 매개변수로 전달.

sumAll(...array); 				  //ECMAScript 6 : 다른 array 자체를 매개변수로 전달.
```

<p data-height="541" data-theme-id="0" data-slug-hash="KBqqdj" data-default-tab="js" data-user="cathy-go-eun-woo" data-pen-title="Javascript : Arrow function" class="codepen">See the Pen <a href="https://codepen.io/cathy-go-eun-woo/pen/KBqqdj/">Javascript : Arrow function</a> by Cathy Go Eun Woo (<a href="https://codepen.io/cathy-go-eun-woo">@cathy-go-eun-woo</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script src="https://static.codepen.io/assets/embed/ei.js"> </script>