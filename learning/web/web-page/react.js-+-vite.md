---
icon: react
---

# React.js + Vite

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



### Vite

#### **2. Vite: 초고속 개발 서버 + 번들러 (오븐)**

* **Vite**는 **React 코드를 빠르게 실행**해주는 **개발 서버**이자 **번들러**다
* 보통 **React는 `create-react-app(CRA)`로 만들었지만, 느렸다**
* **Vite는 CRA보다 10배 이상 빠르다.**
* 오븐처럼, 요리사(React)가 만든 재료(코드)를 빠르게 구워서 **즉시 브라우저에 보여준다**

***

React + Vite 협력

```scss
[React] 컴포넌트 작성 → [Vite] 즉시 반영 (Hot Module Reloading) → 브라우저 출력  
```

***

### **Vite 주요 명령어 및 사용법:**

#### 1. **프로젝트 생성:**

```bash
npm create vite@latest
```

`npm create vite@latest`는 Vite 기반의 새 프로젝트를 생성하는 명령어

`npm` = Node.js의 패키지 관리 시스템(Node Package Manager)&#x20;

2. **의존성 설치:**

```bash
npm install
```

#### **`package.json`에 적힌 모든 패키지 설치**

* **`dependencies`**: 실제 프로젝트에서 필요한 패키지들
* **`devDependencies`**: 개발 중에만 필요한 패키지들 (예: `vite`, `eslint`)
* **`peerDependencies`**: 플러그인 같은 의존성 관리
  * 결과: **`node_modules/`** 폴더에 전부 설치됨.
    * **`package-lock.json`** 파일에 설치된 패키지 버전이 잠금(lock)됨

3. 개발 서버 실행:

```bash
npm run dev
```

* http://localhost:5173에서 바로 확인

4\. **프로덕션 빌드 (배포용):**

```bash
npm run build
```

* **`dist/` 폴더에 최적화된 파일 생성**
* 빠르고 가볍게 압축됨.

***

Vite 프로젝트 구조 예제 (`frontend/`)

```csharp
frontend/
├── public/                # 정적 파일 (favicon, 로고 등)
├── src/                   # 소스 코드
│   ├── components/         # 컴포넌트 폴더
│   │   └── Header.jsx      # 헤더 컴포넌트
│   ├── pages/              # 페이지 폴더
│   │   └── HomePage.jsx    # 홈페이지 컴포넌트
│   ├── App.jsx             # 루트 컴포넌트
│   └── main.jsx            # React DOM 렌더링
├── package.json           # 패키지 정보 및 명령어
└── vite.config.js         # Vite 설정 파일
```













