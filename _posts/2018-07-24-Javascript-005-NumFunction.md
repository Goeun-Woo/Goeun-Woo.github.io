---
layout: post
title: Javascript - 내장함수 (숫자 함수)
categories:
  - Javascript
excerpt_separator:  <!--more-->

---

### 내장함수 - 숫자함수

#### 1. 숫자 확인 함수

###### 1.1 isFinite()

> 셀 수 있는 수면 true 출력
> 셀 수 없는 수(숫자가 아니거나 무한대의 수)면 false 출력

```
- 셀 수 없는 수(무한한 수) 예시
1) 10 / 0
2) -10 / 0
3) Number.MAX_VALUE 보다 큰 값
4) Number.MIN_VALUE 보다 작은 값
```

###### 1.2 isNaN()

> NaN(Not a Number)이면 true 출력
> NaN(Not a Number)이 아니면 false 출력

```
var output = Number('afdsfasdfassfds');
alert(isNaN(output));	//true
alert(isNaN(3));		//false
```

---

#### 2.숫자 변환 함수

###### 2.1 parseInt()

> 정수(Integer)로 추출할 수 있는 부분을 앞쪽부터 읽으면서 변환

```
parseInt('200.23424'); // 200
parseInt('200가나다라'); //200
parseInt('rsdfdfsf200'); //NaN
```

###### 2.1 parseFloat()

> 부동소수점(Float)으로 추출할 수 있는 부분을 앞쪽부터 읽으면서 변환

```
parseFloat('200.234가나다라'); // 200.234
parseFloat('가나다라200.234'); //NaN
```
