---
layout: post
title: Javascript - 자료형 변환하기 (강제 자료형 변환)
categories:
  - Javascript
excerpt_separator:  <!--more-->

---

# 자료형 변환하기 :강제 자료형 변환

: 개발자가 원하는 시점에 특정 코드를 입력하여 자료형 변환
: 자료형을 변환할 때, 자료형의 이름을 가진 함수를 사용한다.
ex/ Number('any type'), String('any type'), Boolean('any type')

### 1. Number()

1.  숫자처럼 생긴 문자열을 숫자로 변환하기
2.  숫자처럼 생기지 않은 문자열을 숫자로 변환하기
3.  불리언을 숫자로 변환하기

### 2. String()

1.  숫자를 문자열로 변환하기
2.  불리언을 문자열로 변환하기

### 3.Boolean()

1.  다음을 제외한 모든 값이 true 로 출력됨.
    - Boolean(0), Boolean(NaN), Boolean(undefined), Boolean(null), Boolean('') : false

---

<p data-height="425" data-theme-id="0" data-slug-hash="ejgaMZ" data-default-tab="result" data-user="gonni" data-embed-version="2" data-pen-title="자료형 변환하기 - 강제변환" class="codepen"> See the Pen <a href="https://codepen.io/gonni/pen/ejgaMZ/"> 자료형 변환하기 - 강제변환 </a> by gonni (<a href="https://codepen.io/gonni"> @gonni </a>) on <a href="https://codepen.io">CodePen</a> . </p>
<script src="https://static.codepen.io/assets/embed/ei.js"> </script>

NaN(Not a Number) : 숫자로 나타낼 수 없는 숫자 의미, 숫자로 나타낼 수는 없지만 강제로 자료형을 변환
