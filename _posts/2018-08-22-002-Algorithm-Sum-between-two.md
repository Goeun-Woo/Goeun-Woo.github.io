---
layout: post
title: Algorithm - 두 정수 사이의 합
categories:
  - JS-Algorithm
excerpt_separator: <!--more-->
---

##### 문제 설명

두 정수 a, b 가 주어졌을 때 a 와 b 사이에 속한 모든 정수의 합을 리턴하는 함수, solution 을 완성하세요.  
예를 들어 a = 3, b = 5 인 경우, 3 + 4 + 5 = 12 이므로 12 를 리턴합니다.

##### 제한 조건

- a 와 b 가 같은 경우는 둘 중 아무 수나 리턴하세요.
- a 와 b 는 -10,000,000 이상 10,000,000 이하인 정수입니다.
- a 와 b 의 대소관계는 정해져있지 않습니다.

##### 입출력 예

|  a  |  b  | return |
| :-: | :-: | :----: |
|  3  |  5  |   12   |
|  3  |  3  |   3    |
|  5  |  3  |   12   |

---

##### 나의 풀이

작은 수에서 큰 수로 1 씩 증가하면서, 그 사이에 속한 정수의 합을 리턴하도록 구현합니다.  
a 는 작은 수, b 는 큰 수를 담는 변수로서 a 의 입력 값이 크다면 temp 변수를 이용하여 a 와 b 의 값을 swap 합니다.  
변수 i 가 a 부터 b 까지 1 씩 증가하며 for 문을 돌면서, 값의 합계를 answer 에 담고 결과값을 리턴합니다.

```
function solution(a, b) {
    if(a > b){
        var temp = b;
        b = a;
        a = temp;
    }

    var answer = 0;
    for(var i=a; i<b+1; i++){
        answer = answer + i;
    }
    return answer;
}
```
