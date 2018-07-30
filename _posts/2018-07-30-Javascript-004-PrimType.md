---
layout: post
title: Javascript - 기본 자료형과 메서드
categories:
  - Javascript
excerpt_separator:  <!--more-->

---

- 기본자료형도 속성을 가지고 있다.
- 기본자료형에 메소드를 입력하면 **일시적으로 객체로 변환**됨.
- **라인이 끝나는 순간** 객체에서 기본자료형으로 복귀

```
var primitiveNum = 273;
var objectNum = new Number(273);

document.write(typeof(primitiveNum));	//number 타입
document.write(typeof(objectNum));	// object 타입
```

> 기본자료형의 메서드 --> 일회용 옷의 개념  
> `한번 사용하고 버린다`

```
primitiveNum.a =10;
// primitiveNum.a에 10 할당
// 라인이 끝나는 순간 다시 기본자료형으로 복귀

document.write(primitiveNum.a);
// 윗 라인에서 선언된 primitiveNum과 관계없이 undefined 출력
```

> 메서드를 추가하여 `기본자료형`의 `일회용 메서드`로서 활용 가능

```
Number.prototype.power = function (){
  return this *this;
}
document.write(primitiveNum.power());	// 273*273 = 74529
```
