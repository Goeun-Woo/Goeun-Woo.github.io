---
layout: post
title: Javascript - Event (이벤트 기본, 이벤트 등록하기)
categories:
  - Javascript
excerpt_separator:  <!--more-->

---

##### 1. 이벤트 기본

> ** 1.1 이벤트 타입 **  
> 이벤트의 종류를 의미한다.
>
> ```
> 사용자가 마우스를 클릭했을 때 (onClick)  
> 사용자가 마우스 휠을 돌렸을 때(onMouseWheel)  
> 텍스트 박스의 입력 값이 바뀌었을 때 (onChange)  
> ```
>
> ** 1.2 이벤트 핸들러 **  
> 특정 이벤트가 발생했을 때 실행될 코드 (onClick, onChange 이하 ...)

---

##### 2. 이벤트 등록 방법

- 이벤트 프로그래밍을 하기 위해서는 이벤트의 대상에 이벤트 핸들러를 등록해야 한다.

> ** 2.1 inline **  
> 이벤트를 이벤트 대상의 태그 속성으로 지정  
> HTML input 태그 안에 이벤트가 직접 포함  
> `정보(HTML)와 제어(Javascript)가 혼재된 형태`이기 때문에 바람직한 방법이라고 할수는 없다.  
> HTML 태그 안에 이벤트 코드를 작성하므로 복잡한 코드는 작성하기 어렵다.

```
<!-- Inline -->
<input type ="button" id="target" onClick ="alert('Hello world')" />
```

> getElementById : 하나의 결과만을 리턴하기 때문에 id 값이 2 개일 경우에는 정상 작동하지 않음  
> ** this ** 활용하기 : 코드 관리가 용이함

```
자기 자신을 참조하는 불편한 방법 : document.getElementById('target').value

<input type="button" id="target" onclick="alert('Hello world, '+document.getElementById('target').value);" value="button" />

this를 통해서 간편하게 참조할 수 있다 : this.value

<input type="button" onclick="alert('Hello world, '+this.value);" value="button" />
```

> ** 2.2 Property Listener **  
> 이벤트 대상이 되는 객체의 프로퍼티로 이벤트 등록  
> `<script> </script> 태그` 안에 메서드 정의  
> 이벤트 핸들러의 첫번째 인자 `'event' 객체` : 현재 발생한 이벤트에 대한 정보를 얻을 수 있음.  
> event 객체의 target 프로퍼티 : event 라는 기능자체의 객체  
> value : event.target 이 가지고 있는 `value="button"` 출력  
> Cross Browsing Issue : IE 8 이하에서는 `전역객체의 event 프로퍼티로 제공`하기 때문에 다음 방식으로 문제 해결.  
> 같은 이벤트 이름으로 단 하나의 이벤트 핸들러만을 사용할 수 있음  
> : 재사용 불가
>
> ```
> var event = event || window.event;
> var target = event.target || event.srcElement;
> ```

```

```

<body>
    <input type="button" id="target" value="button" />

<script>
<!-- Property Listener -->

    var t = document.getElementById('target');
    t.onclick = function(event){
        alert('Hello world, '+event.target.value)
    }
</script>

```
> ** 2.3 addEventListener( ) **  
> 이벤트를 등록하는 가장 권장되는 방식  
> 복수의 엘리먼트에 하나의 리스너를 등록해서 재사용할 수 있다.  
> Cross Browsing Issue : IE 8 이하에서는 attachEvent 메소드를 사용  
```

var t = document.getElementById('target');

<!-- addEventListener -->

if(t.addEventListener){
t.addEventListener('click', function(event){
alert('Hello world, '+event.target.value);
});
} else if(t.attachEvent){ //IE 8 이하
t.attachEvent('onclick', function(event){
alert('Hello world, '+event.target.value);
})
}

```
> 같은 이벤트 이름으로 여러 개의 이벤트를 추가할 수 있다.
```

    var t = document.getElementById('target');
    t.addEventListener('click', function(event){
        alert(1);
    });
    t.addEventListener('click', function(event){
        alert(2);
    });

```
> 반대로 여러 엘리먼트를 하나의 이벤트 리스너로 등록하여 사용할 수 있다.
```

var t1 = document.getElementById('target1');
var t2 = document.getElementById('target2');

function btn_listener(event){
switch(event.target.id){ //id 체크

case 'target1': // target1 에 대한 이벤트 추가
alert(1);
break;

case 'target2': // target2 에 대한 이벤트 추가
alert(2);
break;
}
}

t1.addEventListener('click', btn_listener); //alert(1)
t2.addEventListener('click', btn_listener); //alert(2)

```

```
