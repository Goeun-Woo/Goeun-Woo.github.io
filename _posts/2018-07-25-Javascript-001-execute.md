---
layout: post
title: Javascript - 실행 순서
categories:
  - Javascript
excerpt_separator:  <!--more-->

---

### 1. 자바스크립트의 실행 순서

- 다른 프로그래밍 언어 : 쓰레드[Thread] --> 코드를 읽어 내려가는 녀석
- 자바스크립트 : 쓰레드를 개발자가 따로 생성할 수 없음.
- <u>따라서 코드를 읽어내려가는 녀석은 단 1 개</u>

> 1.1 실행순서 예제 1

```
//자바스크립트 실행순서
//위에서 아래로 읽어내려감

//1. A를 실행해야 겠다!
alert('A');  // A 출력

//2. 뭔지는 모르겠지만 0초 후에 실행을 해야한다 ==> 기록/예약 걸어둔다
setTimeout(function() {
  alert('B');
},0);

//3. C를 출력해야겠다!
alert('C');  // C 출력

//4.예약된 걸 확인 : B를 출력해야 겠다!
//B 출력
```

<p data-height="265" data-theme-id="0" data-slug-hash="jpwMda" data-default-tab="js,result" data-user="cathy-go-eun-woo" data-pen-title="Javascript : 실행순서 1" data-preview="true" class="codepen">See the Pen <a href="https://codepen.io/cathy-go-eun-woo/pen/jpwMda/">Javascript : 실행순서 1</a> by Cathy Go Eun Woo (<a href="https://codepen.io/cathy-go-eun-woo">@cathy-go-eun-woo</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script src="https://static.codepen.io/assets/embed/ei.js"> </script>

---

> 2.  실행순서 예제 2 : 반복문

```
//1. A를 실행해야 겠다!
document.write('A');  // A 출력

//2. 뭔지는 모르겠지만 0초 후에 실행을 해야한다 ==> 기록/예약 걸어둔다
setTimeout(function() {
  document.write('B');
},0);

//3. C를 출력해야겠다!
document.write('C');  // C 출력

//4. 무한 루프
while(true){
}

//5. 무한 루프에 걸려 실행 끊김 ==> B 출력 X
```

<p data-height="265" data-theme-id="0" data-slug-hash="bjRwJR" data-default-tab="js,result" data-user="cathy-go-eun-woo" data-pen-title="Javascript : 실행순서 2" class="codepen">See the Pen <a href="https://codepen.io/cathy-go-eun-woo/pen/bjRwJR/">Javascript : 실행순서 2</a> by Cathy Go Eun Woo (<a href="https://codepen.io/cathy-go-eun-woo">@cathy-go-eun-woo</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script src="https://static.codepen.io/assets/embed/ei.js"> </script>

---

> 3.  실행순서 예제 3 : FOR 문

- var 타입 변수는 블록단위의 스코프를 제공하지 않는다.
- 따라서 var i 는 <u>전역변수</u>로 취급됨 : 블록 밖에서 사용 가능.
- 해결방법 1. (let) 사용 : 블록 단위의 스코프 제공
- 단, ECMA6 문법(let)은 인터넷 익스플로러에서 제공하지 않으므로 사용에 유의해야한다.
- 해결방법 2. 클로저 사용 : 함수 내의 함수에서 변수를 선언하여 해당 범위 내에서만 사용할 수 있도록 한다.

```
//0. var i 는 전역변수로서 선언됨
for(var i=0;i<3;i++){
	//1. i=0일때, setTimeout()에 대한 예약을 건다.
	//2. i=1일때, setTimeout()에 대한 예약을 건다.
	//3. i=2일때, setTimeout()에 대한 예약을 건다.
  setTimeout(function(){alert(i),1})
}
	//4. i=3일때, For문을 탈출한다.
	//5. 예약을 걸어둔 setTimeout(function(),1)를 3번 실행
	// 실행하는 시점에서 i의 값이 3이기 때문에 alert(i)=3, 즉 3을 3번 출력하게된다.
	//5-1. alert(i) = 3
	//5-2. alert(i) = 3
	//5-3. alert(i) = 3

( function (i) {
setTimeout( function() { alert(i); } , 0 )
})(i);		// 클로저를 활용하여 해결

// 단, ECMA6 문법(let)은 인터넷 익스플로러에서 제공하지 않으므로 사용에 유의해야한다.
```

<p data-height="265" data-theme-id="0" data-slug-hash="MBobKP" data-default-tab="js,result" data-user="cathy-go-eun-woo" data-pen-title="Javascript : 실행순서 3" data-preview="true" class="codepen">See the Pen <a href="https://codepen.io/cathy-go-eun-woo/pen/MBobKP/">Javascript : 실행순서 3</a> by Cathy Go Eun Woo (<a href="https://codepen.io/cathy-go-eun-woo">@cathy-go-eun-woo</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script src="https://static.codepen.io/assets/embed/ei.js"> </script>

---
