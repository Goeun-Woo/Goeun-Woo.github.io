---
layout: post
title: Javascript - 객체 (속성과 메서드)
categories:
  - Javascript
excerpt_separator:  <!--more-->

---

---

##### 1. 함수에서 this 키워드 사용하기

> 객체 메서드 내부에서는 `this 키워드를 사용`하여 자기 자신이 가지고 있는 다른 속성을 참조할 수 있다.

```
var person = {
  name : '우고은',
  eat_a : function(food) {
    //this == person 객체
  document.write(this.name + '이 ' + food + '을 먹습니다');
  }
```

> 출력 결과

```
person.eat_a('밥');  // 우고은이 밥을 먹습니다.
```

##### 2. Arrow 함수에서 this 키워드 사용하기

> 출력할 때 this.name 이 비워져 있음
> 화살표 함수에서는 this 를 바인딩 하지 않는다.
> ** 객체 내부에서 this 키워드를 활용하고 싶을 때는, 화살표 함수를 사용하지 않는다.**

```
    eat_b : (food) => {
  document.write(this.name + '이 ' + food + '을 먹습니다');
  }
}
```

> 출력 결과

```
person.eat_b('냠냠'); // 이 냠냠을 먹습니다
```

<p data-height="265" data-theme-id="0" data-slug-hash="VBMXJr" data-default-tab="js,result" data-user="cathy-go-eun-woo" data-pen-title="Javascript - 객체 02 속성과 메서드" class="codepen">See the Pen <a href="https://codepen.io/cathy-go-eun-woo/pen/VBMXJr/">Javascript - 객체 02 속성과 메서드</a> by Cathy Go Eun Woo (<a href="https://codepen.io/cathy-go-eun-woo">@cathy-go-eun-woo</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script src="https://static.codepen.io/assets/embed/ei.js"> </script>
