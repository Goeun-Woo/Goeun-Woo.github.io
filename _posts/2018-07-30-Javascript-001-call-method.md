---
layout: post
title: Javascript - Call ()
categories:
  - Javascript
excerpt_separator:  <!--more-->

---

- call() : `모든 함수`가 내장하고 있는 메서드
- call 을 사용하여 다른 객체에 속한 함수를 사용할 수 있음.
- 첫번쨰 매개변수 : `this` (메서드를 사용할 객체 지정)
- 두번째 이하 매개변수 : `호출하는 함수로 전달`

```
var person1 = {
    성 : "우",
    이름 : "고은",
    평균 : function(국어, 영어, 수학) {
        var avg = ((국어 + 영어 + 수학) / 3).toFixed(2);

        return this.성 + " " + this.이름 + "의 평균점수는 " + avg + "입니다.";
        }
};

var person2 = {
    성 : "김",
    이름 : "이박"
};
```

> person2 에서 person1 의 메서드를 가져와 사용  
>  `this`는 `person2`로 지정

```
document.write(person1.평균(80,80,90));
document.write(person1.평균.call(person2,80,90,85));  
```

<p data-height="265" data-theme-id="0" data-slug-hash="BPmrWw" data-default-tab="js,result" data-user="cathy-go-eun-woo" data-pen-title="Javascript : Call ()" class="codepen">See the Pen <a href="https://codepen.io/cathy-go-eun-woo/pen/BPmrWw/">Javascript : Call ()</a> by Cathy Go Eun Woo (<a href="https://codepen.io/cathy-go-eun-woo">@cathy-go-eun-woo</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script src="https://static.codepen.io/assets/embed/ei.js"> </script>
