---
layout: post
title: Javascript - 유효범위
categories:
  - Javascript
excerpt_separator:  <!--more-->

---

- Javascript 는 함수에 대한 유효범위만을 제공한다.
- cf ) Java : 블록({})단위에 대한 유효범위 제공

##### 1. 전역변수

> 애플리케이션 전역에서 접근이 가능한 변수  
> 어떤 함수 안에서도 그 변수에 접근 할 수 있다

##### 2. 지역변수

> 함수 내에서 선언된 변수  
> 지역변수의 유효범위는 함수 안  
> 같은 이름의 지역변수와 전역변수가 동시에 정의되어 있다면 지역변수가 우선한다

##### 3. 사용팁

> var 를 사용하지 않은 지역변수는 전역변수가 된다  
> 동일한 이름의 전역변수가 있었다면 함수의 값을 변경하게 되는 것  
> 변수를 선언할 때는 **꼭 var 을 붙이는 것을 습관화**해야 한다.  
> 전역변수는 되도록 사용하지 않는다.

```
MYAPP = {}
MYAPP.calculator = {
    'left' : null,
    'right' : null
}
MYAPP.coordinate = {
    'left' : null,
    'right' : null
}

MYAPP.calculator.left = 10;
MYAPP.calculator.right = 20;
```
