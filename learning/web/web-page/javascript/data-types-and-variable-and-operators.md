---
description: JS data types, variable
---

# Data types & Variable & Operators

### JS Data type

* 원시 형태(primitive):&#x20;
  * number, string, boolean, undefined, null
* 객체 형태(object):
  * date, array, object

### Literal 선언

* 코드 상에서 값을 직접 명시해서 선언하거나 할당하는 것으로 자료형에 따라\
  literal 선언 문법이 다름

***

### JS Variable

* 변수의 선언: `var` 키워드와 변수의 이름을 선언
  * ex) `var x;`&#x20;
*   변수에 값을 할당: 선언된 변수명에 대입 연산자 `=` 를 사용, 값을 대입

    * `x = 40;` or x = "`철수";`&#x20;
      * 선언과 동시에 대입 가능
        * `var x = 40;` &#x20;


* :fire: **문자는 항상 홑 or 겹 따옴표로 감싼다**
* :fire:변수 선언시 변하지 않는 값은 `const` 변할 수 있는 값은 `let` 으로 선언
* (\`\`) 백틱 안에서 ${변수명}을 쓰면 변수 값을 문자열 안에 넣을 수 있다
* 변수 이름 규칙
  * 하이픈 `-` 사용 불가
  * 첫 글자 숫자 사용 불가
  * 띄어쓰기 사용 불가
  * JS 예약어 사용 불가
    * [JS 예약어 목록 (W3Schools)](https://w3schools.com/js/js_reserved.asp)

### 변수 이름 convention

**1) `camelCase` (카멜 케이스)**

* 단어를 이어 붙이고 첫 단어는 소문자, 이후 단어는 대문자로 시작
* 대부분의 변수, 함수에서 사용됨

```javascript
let userName = "Johnny";
let totalScore = 100;
```

**2) `PascalCase` (파스칼 케이스, 클래스/생성자에서 사용)**

* 모든 단어를 대문자로 시작
* 주로 클래스나 생성자 함수에서 사용

```javascript
class UserProfile {}
function CreateUser() {}  // 생성자 함수
```

**3) `UPPER_SNAKE_CASE` (대문자 + 언더스코어, 상수에서 사용)**

* 변하지 않는 값(상수)에는 `UPPER_SNAKE_CASE`를 사용

```javascript
const MAX_USERS = 500;
const API_KEY = "abc123";
```

4\) **`is`, `has`, `can`, `should` 접두어 활용 (불리언 값)**

* `true` / `false` 값을 담는 변수는 `is`, `has`, `can`, `should` 같은 접두어를 붙이면 좋음

```javascript
let isAdmin = false;
let hasPermission = true;
let canDeletePost = false;
```

5\) **`get`, `set`, `fetch`, `load` 같은 동작 기반 네이밍**

* 변수는 명사, 함수는 동사를 쓰는 게 좋음

```javascript
let userData = {};         // ✅ 변수는 명사
function getUserData() {}  // ✅ 함수는 동사 + 명사 조합
```



***

### Arithmetic Operators(산술 연산자)

| 연산자  | 설명     | 예제               | 결과    |
| ---- | ------ | ---------------- | ----- |
| `+`  | 덧셈     | `5 + 3`          | `8`   |
| `-`  | 뺄셈     | `5 - 3`          | `2`   |
| `*`  | 곱셈     | `5 * 3`          | `15`  |
| `/`  | 나눗셈    | `5 / 2`          | `2.5` |
| `%`  | 나머지    | `5 % 2`          | `1`   |
| `**` | 거듭제곱   | `2 ** 3`         | `8`   |
| `++` | 증가 연산자 | `let a = 5; a++` | `6`   |
| `--` | 감소 연산자 | `let a = 5; a--` | `4`   |

```javascript
let a = 5;
console.log(a++); // 5 (후위: 먼저 출력 후 증가)
console.log(a);   // 6

let b = 5;
console.log(++b); // 6 (전위: 먼저 증가 후 출력)
```

***

### Assignment Operators(할당 연산자)

| 연산자   | 설명        | 예제           | 결과           |
| ----- | --------- | ------------ | ------------ |
| `=`   | 값 할당      | `let x = 10` | `x = 10`     |
| `+=`  | 덧셈 후 할당   | `x += 5`     | `x = x + 5`  |
| `-=`  | 뺄셈 후 할당   | `x -= 3`     | `x = x - 3`  |
| `*=`  | 곱셈 후 할당   | `x *= 2`     | `x = x * 2`  |
| `/=`  | 나눗셈 후 할당  | `x /= 2`     | `x = x / 2`  |
| `%=`  | 나머지 후 할당  | `x %= 3`     | `x = x % 3`  |
| `**=` | 거듭제곱 후 할당 | `x **= 2`    | `x = x ** 2` |

```javascript
let x = 10;
x += 5;  // x = 15
x *= 2;  // x = 30
```

***

### Comparison Operators(비교 연산자)

| 연산자   | 설명                         | 예제          | 결과      |
| ----- | -------------------------- | ----------- | ------- |
| `==`  | 동등 비교 (타입 변환 O),값만 같음      | `5 == "5"`  | `true`  |
| `===` | 엄격 동등 비교 (타입 변환 X), 타입도 같음 | `5 === "5"` | `false` |
| `!=`  | 부등 비교                      | `5 != "5"`  | `false` |
| `!==` | 엄격 부등 비교                   | `5 !== "5"` | `true`  |
| `>`   | 초과                         | `5 > 3`     | `true`  |
| `<`   | 미만                         | `5 < 3`     | `false` |
| `>=`  | 이상                         | `5 >= 5`    | `true`  |
| `<=`  | 이하                         | `5 <= 3`    | `false` |

```javascript
console.log(5 == "5");  // true (자동 형 변환)
console.log(5 === "5"); // false (타입이 다름)
```



***

### Logical Operators(논리 연산자)

| 연산자  | 설명     | 예제              | 결과      |
| ---- | ------ | --------------- | ------- |
| `&&` | 논리 AND | `true && false` | `false` |
| \|\| | 논리 OR  | \|\|            |         |
| `!`  | 논리 NOT | `!true`         | `false` |

```javascript
console.log(true && false); // false
console.log(true || false); // true
console.log(!true);         // false
```

***

### Bitwise Operators(비트 연산자)

| 연산자   | 설명            | 예제         | 결과           |
| ----- | ------------- | ---------- | ------------ |
| `&`   | AND           | `5 & 1`    | `1`          |
| \`    | \`            | OR         | \`5          |
| `^`   | XOR           | `5 ^ 1`    | `4`          |
| `~`   | NOT           | `~5`       | `-6`         |
| `<<`  | 왼쪽 시프트        | `5 << 1`   | `10`         |
| `>>`  | 오른쪽 시프트       | `5 >> 1`   | `2`          |
| `>>>` | 부호 없는 오른쪽 시프트 | `-5 >>> 1` | `2147483645` |

```javascript
console.log(5 & 1);  // 1
console.log(5 | 1);  // 5
console.log(5 ^ 1);  // 4
console.log(~5);     // -6
console.log(5 << 1); // 10
console.log(5 >> 1); // 2
```

***

### Ternary Operators(삼항 연산자)&#x20;

* 조건에 따라 값을 선택할 때 사용. `if-else`를 한 줄로 축약 가능

```javascript
let age = 20;
let result = age >= 18 ? "성인" : "미성년자";
console.log(result); // "성인"
```



***

### Type Operators(타입 연산자)

| 연산자          | 설명               | 예제                    | 결과         |
| ------------ | ---------------- | --------------------- | ---------- |
| `typeof`     | 데이터 타입 확인        | `typeof 123`          | `"number"` |
| `instanceof` | 특정 클래스 인스턴스인지 확인 | `[] instanceof Array` | `true`     |

```javascript
console.log(typeof "Hello");  // "string"
console.log(typeof 42);       // "number"
console.log(typeof true);     // "boolean"
console.log(typeof {});       // "object"
console.log(typeof null);     // "object" (버그, 원래는 null이어야 함)
console.log(typeof undefined); // "undefined"
console.log([] instanceof Array); // true
```



{% hint style="info" %}
var은 쓰지 말 것  {}안에서 써도 전역으로 나감, 재 선언 되어도 오류 발생이 안됨

\==
{% endhint %}
