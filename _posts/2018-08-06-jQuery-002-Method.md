---
layout: post
title: jQuery - 문서 객체 조작하기
categories:
  - jQuery
excerpt_separator:  <!--more-->

---

- jQuery 메서드의 일부는 Setter, Getter 로 구분하여 사용할 수 있다.
- css(), html(), text(), attr()

---

##### 0. Getter / Setter

> 0.1 Setter
>
> - 값을 설정하는 메서드
> - 두 매개변수를 모두 입력하여 값을 설정한다.
> - jQuery 객체를 리턴

> > 0.1.1 (문자열, 문자열) 방식으로 set 하기
> >
> > 0.1.2 객체 방식으로 set 하기
> >
> > 0.1.3 함수로 값 입력하기

> 0.2 Getter
>
> - 해당 CSS 속성에 설정된 값을 가져오는 메서드
> - 매개변수를 하나 생략해서 사용한다
> - 문자열을 리턴
> - <u>같은 속성 값을 가진 문서객체가 복수 개 일경우, 가장 첫번째에 위치한 문서 객체의 속성값만 추출
> - text() 예외 : 해당되는 모든 문서 객체의 속성 값 추출 </u>

---

##### 1. CSS ()

> 1.1 Setter

> > 1.1.1 (문자열, 문자열) 방식으로 set 하기
> >
> > ```
> > $("h1").css("color","red);
> > ```
> >
> > 1.1.2 객체 방식으로 set 하기
> >
> > ```
> > $("h1").css({
> > "color" :"red",
> > "background-color" : "orange",
> > "text-align" : "center"
> > });
> > ```
> >
> > 1.1.3 함수로 값 입력하기
> >
> > ```
> > var array = ["red", "blue", "orange"]
> > $("h1").css("color", function(index){
> > ```
> >
> > return array[index];
> >
> > })
> >
> > ```
> >
> > ```

> 1.2 Getter

> ```
> $("h1").css("color")
> // rgb(255,0,0)
> ```

<p data-height="265" data-theme-id="0" data-slug-hash="JBBwZw" data-default-tab="js,result" data-user="cathy-go-eun-woo" data-pen-title="jQuery : CSS()" class="codepen">See the Pen <a href="https://codepen.io/cathy-go-eun-woo/pen/JBBwZw/">jQuery : CSS()</a> by Cathy Go Eun Woo (<a href="https://codepen.io/cathy-go-eun-woo">@cathy-go-eun-woo</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script src="https://static.codepen.io/assets/embed/ei.js"> </script>
----
##### 2. Attr()  
- 속성을 지정하는 함수, img 태그 등에서 사용  

> 1.1 Setter
>
> > 1.1.1 (문자열, 문자열) 방식으로 set 하기
> >
> > ```
> > $("img").attr("src","http://placehold.it/300x300");
> > ```
> >
> > 1.1.2 객체 방식으로 set 하기
> >
> > ```
> > $("img").attr({ "src" : "http://placehold.it/300x300" });  
> > ```
> >
> > 1.1.3 함수로 값 입력하기
> >
> > ```
> > $("img").attr({
> > 	"src" : function(index){
> >    return "http://placehold.it/100x"+ ((index+1)*100)
> >    }
> > })
> > ```
>
> 1.2 Getter
>
> ```
> $("img").attr("src");
> ```

<p data-height="265" data-theme-id="0" data-slug-hash="NBBEvm" data-default-tab="js,result" data-user="cathy-go-eun-woo" data-pen-title="jQuery - attr()" class="codepen">See the Pen <a href="https://codepen.io/cathy-go-eun-woo/pen/NBBEvm/">jQuery - attr()</a> by Cathy Go Eun Woo (<a href="https://codepen.io/cathy-go-eun-woo">@cathy-go-eun-woo</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script src="https://static.codepen.io/assets/embed/ei.js"> </script>
----
##### 3. html()
- 태그 내에 텍스트 및 html 요소를 입력하는 함수
- 매개변수를 하나만 입력받기 때문에, 객체방식의 setter를 사용할 수 없음.
> 1.1 Setter  
> > 1.1.1 (문자열, 문자열) 방식으로 set 하기  
> >  
> > ```
> > $("h1").html("Hello world");
> > ```
> >
> > 1.1.2 함수로 값 입력하기  
> >
> > ```
> > $("h1").html(function(index) {
> > return "Hello world -" + index
})
> >
> >
> > ```
>
> 1.2 Getter  
>
> ```
> $("h1").html();
> ```

<p data-height="265" data-theme-id="0" data-slug-hash="RBBqmE" data-default-tab="js,result" data-user="cathy-go-eun-woo" data-pen-title="jQuery : html ()" class="codepen">See the Pen <a href="https://codepen.io/cathy-go-eun-woo/pen/RBBqmE/">jQuery : html ()</a> by Cathy Go Eun Woo (<a href="https://codepen.io/cathy-go-eun-woo">@cathy-go-eun-woo</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script src="https://static.codepen.io/assets/embed/ei.js"> </script>
----
##### 4. text()
- 태그 내에 텍스트를 입력하는 함수
- html() 메서드와 다르게 텍스트만 입력함.
- <u>getter로서 사용할 때, 다른 메서드와 다르게 모든 문서객체의 텍스트를 가져온다</u>

<p data-height="265" data-theme-id="0" data-slug-hash="MBBzdj" data-default-tab="result" data-user="cathy-go-eun-woo" data-pen-title="jQuery : text()" class="codepen">See the Pen <a href="https://codepen.io/cathy-go-eun-woo/pen/MBBzdj/">jQuery : text()</a> by Cathy Go Eun Woo (<a href="https://codepen.io/cathy-go-eun-woo">@cathy-go-eun-woo</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script src="https://static.codepen.io/assets/embed/ei.js"> </script>
