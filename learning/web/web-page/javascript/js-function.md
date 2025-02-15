# JS function

### JS 함수

1. 함수 선언 (Function Declaration)\
   -`function` 키워드 사용.\
   \- **호이스팅(끌어올리기)** 되어서 선언 전에 호출 가능

```javascript
function greet(name) {
  return `Hello, ${name}!`;
}

console.log(greet("Mike")); // Hello, Mike!
```

#### 🚀 자바스크립트 함수 요약 정리

| 구분           | 설명                                   |
| ------------ | ------------------------------------ |
| **함수 선언**    | `function name() {}` 호이스팅 O          |
| **함수 표현식**   | `const name = function() {};`        |
| **화살표 함수**   | `(a, b) => a + b`                    |
| **기본 매개변수**  | `function(a = 1) {}`                 |
| **나머지 매개변수** | `(...args) => {}`                    |
| **즉시 실행 함수** | `(function() {})()`                  |
| **콜백 함수**    | `function(callback) { callback(); }` |
| **클로저**      | 함수 안의 함수가 외부 스코프 참조                  |



