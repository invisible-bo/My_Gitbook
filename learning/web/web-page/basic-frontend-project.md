# Basic Frontend Project

### HTML, CSS, JavaScript

1. 기본 폴더구성 예제

```
frontend/
│── components/      # 헤더, 푸터 등 공통 UI
│   ├── header.html
│   ├── footer.html
│
│── scripts/         # JavaScript 파일
│   ├── include.js   # 공통 요소 로드
│   ├── auth.js      # 로그인, 회원가입 처리
│   ├── api.js       # 백엔드 API 요청
│
│── styles/          # CSS 파일
│   ├── styles.css   # 전체 스타일 설정
│
│── pages/           # 개별 페이지 HTML
│   ├── homelogin.html  # 홈 & 로그인 페이지
│   ├── signup.html     # 회원가입 페이지
│   ├── chatbot.html    # 챗봇 페이지
│   ├── profile.html    # 프로필확인 페이지
```

***

### 주석 방식

HTML

```html
<!-- HTML 주석 -->
```

CSS

```css
/* CSS 주석 */
```

JavaScript

```javascript
// 한 줄 주석

/*
여러 줄 주석
여러 줄 주석
*/
```

***

### Frontend project

* homelogin.html&#x20;

```html
<body>
    <div class="container">
        <h2>로그인</h2>
        <form id="login-form">
            <input type="text" id="username" placeholder="아이디" required>
            <input type="password" id="password" placeholder="비밀번호" required>
            <p id="login-error" style="color:red;"></p>
            <button type="submit">로그인</button>
        </form>
        <a href="signup.html">회원가입</a>
    </div>

    <script src="../scripts/include.js"></script>
    <script src="../scripts/auth.js"></script>
</body>
```

* 로그인 폼을 만들고 `auth.js`를 연결하여 로그인 처리
* 헤더와 푸터&#xB294;**`include.js`**&#xC5D0;서 자동으로 불러올 것



* styles.css
  * 전체적인 공통 스타일 관리
  * 클래스 적용 재 사용 가능

<pre class="language-css"><code class="lang-css">body {
    font-family: Arial, sans-serif;
    background-color: #f5f5f5;
    margin: 0;
    padding: 0;
    text-align: center;
}

/* 컨테이너 박스 스타일 */
.container {
    width: 300px;
    margin: 100px auto;
    padding: 20px;
    background: white;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
    border-radius: 5px;
}

/* 입력 필드 스타일 */
input {
    width: 100%;
    padding: 8px;
    margin: 5px 0;
    border: 1px solid #ccc;
    border-radius: 3px;
}

/* 버튼 스타일 */
button {
    width: 100%;
    padding: 10px;
    background-color: #007bff;
    color: white;
    border: none;
    border-radius: 3px;
    cursor: pointer;
    font-size: 16px;
}

button:hover {
    background-color: #0056b3;
}
<strong>/* 클래스 예시 */
</strong>.text-white {
    color: white;
}
</code></pre>

***























