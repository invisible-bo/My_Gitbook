---
icon: presentation-screen
---

# Web Page

## Core Web Technologies

<div align="left"><figure><img src="../../../.gitbook/assets/image (63).png" alt="" width="322"><figcaption></figcaption></figure></div>

| 기술         | 역할                 | 비유              |
| ---------- | ------------------ | --------------- |
| HTML       | 웹 페이지의 구조          | "건물의 골조"        |
| CSS        | 웹 페이지의 디자인, 스타일링   | "페인트, 인테리어"     |
| JavaScript | 웹 페이지의 동적 기능, 인터랙션 | "전기, 수도, 엘리베이터" |

* **HTML, CSS, JavaScript** → **"프론트엔드 3대 요소"**
* **HTML + CSS + JavaScript** → **"웹 삼대장"**
* **HTML, CSS, JavaScript** → **"웹 개발의 3대 기둥"**
* **"Frontend 삼신기"**
* **"웹의 핵심 3요소" (Core Web Technologies)**
* **"웹 개발 기초 스택 (Web Development Stack)"**
* **"웹 개발의 기본 (Frontend Essentials)"**

***

### 1. HTML(HyperText Markup Language) - "구조"

* HTML은 웹 페이지의 **기본 뼈대(구조)** 를 만든다
* **태그(tag)**&#xB97C; 이용해서 요소들을 정의하는 방식

```html
<!DOCTYPE html>
<html>
<head>
    <title>내 웹페이지</title>
</head>
<body>
    <h1>안녕하세요!</h1>
    <p>이것이 HTML입니다.</p>
</body>
</html>
```

:fire:**핵심:**

* `<h1>`, `<p>` 같은 \*\*태그(tag)\*\*로 요소를 정의함.
* HTML만 있으면 그냥 **하얀 바탕에 글자만 있는 웹페이지**가 됨. (디자인 없음)

***

### 2. CSS(Cascading Style Sheets) - "디자인"

* CSS는 웹페이지를 **스타일링(꾸미기)** 하는 역할을 한다
* 색깔, 폰트, 크기, 레이아웃 등을 변경할 수 있음

```css
body {
    background-color: black;
    color: white;
    font-family: Arial, sans-serif;
}
h1 {
    color: red;
}
```

:fire:**핵심:**

* `background-color: black;` → 배경을 검정색으로 설정.
* `color: white;` → 글자색을 흰색으로 변경.
* `h1` 태그의 글자 색을 빨간색으로 변경.

***

### 3. JavaScript – "동작"

* JavaScript는 **웹사이트에 동적인 기능을 추가**하는 역할
* 클릭, 입력, 애니메이션, API 호출 등 **사용자 인터랙션을 처리**

```html
<button onclick="sayHello()">클릭하세요</button>

<script>
    function sayHello() {
        alert("안녕하세요! JavaScript입니다.");
    }
</script>
```

:fire:**핵심:**

* JavaScript를 사용하면 HTML 요소를 클릭했을 때 **동작을 추가**할 수 있음
* `onclick="sayHello()"` → 버튼을 누르면 `sayHello()` 함수 실행.
* `alert("안녕하세요!")` → 경고창 띄우기.

***

**결과:** HTML과 CSS는 **화면만 만들고**, JavaScript가 **사용자의 입력을 받아 반응함**

### **HTML, CSS, JS 없이 프론트엔드는 없다**

#### **✅ HTML만 있다면?**

* 글자와 이미지만 보이는 **하얀 바탕**의 웹페이지.
* 스타일이 없고 디자인도 없음

#### **✅ HTML + CSS만 있다면?**

* 예쁜 UI는 만들 수 있지만, **버튼 클릭 같은 인터랙션은 없음.**
* 정적인 웹페이지

#### **✅ HTML + CSS + JavaScript라면?**

* **진짜 웹사이트!**
* 버튼 클릭, 메뉴 애니메이션, 입력 폼 검증 등 **동적인 기능이 가능**
* 백엔드(Django, Node.js 등)와 연결하면 **데이터베이스와 통신**도 가능

***

### **최종 개발 흐름 요약**

1️⃣ **HTML 작성** → 뼈대를 만든다.\
2️⃣ **CSS 추가** → 예쁘게 꾸민다.\
3️⃣ **JavaScript 추가** → 기능을 넣는다.\
4️⃣ **반응형 디자인 (선택)** → 화면 크기에 맞게 조정 (CSS `@media` 활용).\
5️⃣ **최적화 & 배포** → 코드 정리, 속도 개선 후 실제 웹에 올리기

***

예시)

```html
<!DOCTYPE html>
<html>
<head>
    <title>내 첫 웹사이트</title>
    <style>
        /* CSS 스타일 */
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            color: #333;
            margin: 0;
            padding: 0;
        }

        header {
            background-color: #6200ea;
            color: white;
            padding: 20px;
            text-align: center;
        }

        nav ul {
            list-style-type: none;
            padding: 0;
            text-align: center;
        }

        nav ul li {
            display: inline;
            margin: 10px;
        }

        nav a {
            text-decoration: none;
            color: white;
            background: #333;
            padding: 10px 15px;
            border-radius: 5px;
        }

        button {
            background-color: #6200ea;
            color: white;
            padding: 10px 15px;
            border: none;
            cursor: pointer;
            font-size: 16px;
            border-radius: 5px;
        }

        button:hover {
            background-color: #3700b3;
        }
    </style>
</head>
<body>
    <header>
        <h1>안녕하세요, 여기는 내 웹사이트!</h1>
    </header>

    <nav>
        <ul>
            <li><a href="#">홈</a></li>
            <li><a href="#">소개</a></li>
            <li><a href="#">문의</a></li>
        </ul>
    </nav>

    <section>
        <p>여기는 본문 내용입니다.</p>
        <button>클릭하세요</button>
    </section>

    <footer>
        <p>© 2025 All rights reserved.</p>
    </footer>

    <script>
        // JavaScript 기능 추가
        document.querySelector("button").addEventListener("click", function() {
            alert("버튼이 클릭되었습니다!");
        });

        document.querySelector("nav a").addEventListener("mouseover", function() {
            this.style.backgroundColor = "red";
        });

        document.querySelector("nav a").addEventListener("mouseout", function() {
            this.style.backgroundColor = "#333";
        });
    </script>
</body>
</html>
```

* JavaScript를 HTML 최하단에 두는 이유
  * HTML과 CSS가 먼저 로딩되도록 하기 위해
    * 브라우저는 **HTML을 위에서 아래로 읽음**
    * 만약 `<head>` 부분에 JavaScript를 넣으면, **JS가 실행되느라 HTML이 늦게 로딩될 수도 있음**
    * JavaScript가 **DOM을 조작하려면 HTML이 먼저 로드돼야 하기 때문**에,\
      HTML이 다 불러와진 뒤 **최하단에 JS를 두는 게 일반적**
  * 페이지 **속도 최적화**
    * JS가 `<head>`에 있으면 **HTML이 완전히 로드되기 전에 JS가 실행됨** → 페이지가 느려짐
    * 하지만 JS를 `<body>` 끝에 두면 **HTML과 CSS가 먼저 로드된 뒤 실행됨** → 속도 최적화
* 최적의 방식 (JS를 `<body>` 끝에 둠)

