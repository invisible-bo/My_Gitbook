---
icon: react
---

# React

### React

#### **1. React: 프론트엔드 UI 라이브러리 (요리사)**

* **React**는 \*\*UI(화면)\*\*를 구성하는 도구
* **컴포넌트 기반**으로 화면을 쪼개서 재사용한다
* 단순한 HTML/CSS가 아닌 **JavaScript의 힘**으로 **동적인 웹앱**을 만든다
* 요리사처럼, 필요한 재료(컴포넌트)들을 조합해 요리(웹페이지)를 만든다

```javascript
// 예제: React 컴포넌트 (Header.jsx)
import React from 'react';

function Header() {
  return (
    <header>
      <h1>Welcome to BookGroo</h1>
    </header>
  );
}

export default Header;
```

***

* 개발환경 setting
* Node.js(LTS)다운로드
  * 작업폴더 생성 후&#x20;
    * npm create vite@latest로 `프로젝트 시작`

<figure><img src="../../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
npm (Node Package Manager)

* Node.js의 패키지 매니저
* `npm install`같은 걸 쓰면, 특정 기능을 가진 패키지를 설치해서 가져오는 것
  * `package.json` 파일에 어떤 패키지를 쓰는지 기록

Vite (프랑스어로 '빠르다'는 뜻)

* 프로젝트 템플릿을 생성
* 개발 서버(dev server)를 제공
* 프로덕션 빌드시 번들링도 함
{% endhint %}

* `npm run dev` : 개발 서버 실시간 확인
* body { margin : 0 }  \
  div { box-sizing : border-box }
  * css 깔끔하게 시작할때. 전역 css파일에 설정(`index.css`)





* 메인 개발 page : `app.jsx`

`App.jsx → main.jsx → index.html(#root)` &#x20;

* 단방향 데이터 흐름

***

* className&#x20;

<div align="left"><figure><img src="../../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure></div>



* inline style css

<div align="left"><figure><img src="../../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure></div>

***

### useState

* **state에 데이터 바인딩**
* state는 변동 사항이 생기면 state쓰는 html도 자동으로 재 렌더링 됨
* UI 기능 개발이 매우 편리해지짐

```jsx
function App(){
  let [글제목, b] = useState('남자 코트 추천');

  return (
    <h4>{ 글제목 }</h4>
  )
}
```

* **자주변경될 것 같은 데이터**들은 state에 저장했다가 html에 {데이터바인딩}&#x20;

1\. 변경할 일이 없는 데이터들

2\. 굳이 html에 표기가 필요없는 데이터들은 그냥 변수에 저장



























