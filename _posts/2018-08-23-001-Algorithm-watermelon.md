---
layout: post
title: Algorithm - 수박수박수박수박수
categories:
  - JS-Algorithm
excerpt_separator: <!--more-->
---

##### 문제 설명

길이가 n 이고, `수박수박수박수....`와 같은 패턴을 유지하는 문자열을 리턴하는 함수, solution 을 완성하세요.  
예를들어 n 이 4 이면 수박수박을 리턴하고 3 이라면 수박수를 리턴하면 됩니다.

##### 제한 조건

- n 은 길이 10,000 이하인 자연수입니다.

##### 입출력 예

|  n  | return     |
| :-: | :--------- |
|  3  | "수박수"   |
|  4  | "수박수박" |

---

##### 나의 풀이

1 부터 n 까지 1 씩 증가하면서,  
i 나누기 2 의 나머지가 1 이면 answer 에 "수"를 붙이고, 나머지가 0 이면 answer 에 "박"을 붙입니다.

```
function solution(n) {
    var answer = '';
    for(var i=1; i<n+1 ; i++){
     ((i%2)==1)? answer+="수":answer+="박";
    }
     return answer;
}
```

##### 다른 사람의 풀이

repeat() 함수를 사용하여 "수박" 이라는 단어를 n/2 회 만큼 반복하면서 나머지가 있는 경우(홀수인 경우)에 대해서만 "수"를 붙입니다.

```
function waterMelon(n){
  return ("수박").repeat(n/2) + ((n%2) ? '수' : '');
}
```
