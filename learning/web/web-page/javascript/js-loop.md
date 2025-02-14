# JS Loop

### JS반복문



1. for

* 특정 횟수만큼 반복

<pre class="language-javascript"><code class="lang-javascript">for (초기값; 조건; 증감) {
    // 실행할 코드
}
---
//예제 (0부터 4까지 출력)
for (let i = 0; i &#x3C; 5; i++) {
    console.log(i);
}
//i = 0 → 초기값
//i &#x3C; 5 → 조건 충족하면 실행. false가 되면 멈춤
<strong>//i++ → 반복마다 i 증가
</strong></code></pre>

***

2. while

* 조건이 `true`인 동안 계속 반복

```javascript
while (조건) {
    // 실행할 코드
}
---
let i = 0;
while (i < 5) {
    console.log(i);
    i++;
}
//while 내부 코드 실행 → i++ → 조건 다시 체크 → 반복
```















