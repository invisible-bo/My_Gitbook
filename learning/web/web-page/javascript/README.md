---
icon: js
description: object(객체) 기반의 script 언어. web문서에서 사용자와 다양한 상호작용
---

# JavaScript

<div align="left"><figure><img src="../../../../.gitbook/assets/image (3).png" alt="" width="375"><figcaption></figcaption></figure></div>

1. web page에 동적인 요소 추가

* JS를 사용하면 클릭, 애니메이션, 실시간 업데이트 같은 interactio&#x6E;**(상호작용)** 이 가능해짐

2. HTML & CSS 조작

* JS를 사용하면 HTML요소를 추가, 삭제, 변경 가능, CSS Style로 바꿀 수 있음

3. 사용자 입력 처리(Form 검증)

* JS는 사용자가 입력한 값이 올바른지 확인하고, 서버로 전송 전에 검증할 수 있음.

4. API 호출, AJAX(비동기 데이터 요청)

* JS를 사용하면 **서버에서 데이터를 가져와서 웹페이지에 즉시 반영할 수 있음**
  * (= **비동기 요청, AJAX, Fetch API, Axios 등 활용**)

5. Animation & effects

* CSS 애니메이션이 부족할 때 JS로 더욱 강력한 애니메이션을 만들 수 있음



**HTML** → 웹의 **뼈대**\
**CSS** → 웹의 **스타일링**\
**JavaScript** → 웹의 **동작 & 인터랙션(상호작용)**

:fire:정적 page를 동적 page로





```html
<script>
</script>
```

```html
/* 한줄 이상 긴 주석 */
// 한줄 주석
```



***

#### 🚀 ES5 vs ES6 비교

| 구분           | ES5                        | ES6                                 |
| ------------ | -------------------------- | ----------------------------------- |
| **변수 선언**    | `var`                      | `let`, `const`                      |
| **함수**       | `function() {}`            | 화살표 함수 `() => {}`                   |
| **문자열**      | `"Hello " + name`          | `Hello ${name}` (템플릿 리터럴)           |
| **클래스**      | 프로토타입 기반                   | `class` 문법 도입                       |
| **모듈 시스템**   | 지원 없음 (`require()` 같은 비표준) | `import/export` 문법 도입               |
| **비동기 처리**   | 콜백 지옥 (`callback`)         | `Promise`, 이후 `async/await` 지원      |
| **배열 메서드**   | `forEach`, `map`, `filter` | `for...of`, 스프레드 문법 (`...arr`)      |
| **구조 분해 할당** | 없음                         | `[a, b] = [1, 2];`, `{name} = obj;` |





