# \*\*practicing

*   #### **Vite란?**

    Vite는 **초고속 프론트엔드 빌드 도구**

```bash
npx create-vite frontend --template react
```

* `npx`: npm 최신 패키지 실행
* `create-vite`: Vite 프로젝트 초기화 도구
* `frontend`: 폴더명
* `--template react`: React + Vite 템플릿 사용

```bash
cd frontend
npm install
npm run dev
```

<div align="left"><figure><img src="../../.gitbook/assets/image (1) (1).png" alt="" width="375"><figcaption></figcaption></figure></div>

***

**`src/` 내부 정리:**

* `src/components/` 폴더 생성 (컴포넌트 모음)
* `src/pages/` 폴더 생성 (페이지별 구성)
* `src/api/` 폴더 생성 (Axios 요청 파일)

**React Router 설치 (페이지 전환)**:

* **역할:** SPA(Single Page Application)에서 \*\*페이지 간 전환(라우팅)\*\*을 책임져.
* **특징:** 새로고침 없이 URL만 바꿔서 페이지 전환. (`useNavigate`, `<Route>` 등)

```bash
npm install react-router-dom
```

**React Query 설치 (API 데이터 관리)**:

* **역할:** 서버 데이터 **캐싱, 페칭, 동기화, 리트라이, 무효화** 등 API 관리를 책임져.
* **특징:** `useQuery`, `useMutation` 같은 **강력한 훅(Hooks)** 제공.

```bash
npm install @tanstack/react-query
```

Axios 설치 (API 통신):

* **역할:** HTTP 요청(GET, POST, PUT, DELETE) 쉽게 보낸다.
* **특징:** `fetch`보다 **간단한 문법, 에러 처리, 요청 인터셉터** 지원.

```bash
npm install axios
```

.env.local 설정 (API 주소 관리):

* **역할:** **API URL, 비밀 키 등 보안 정보**를 코드 밖에서 관리.
* **파일:** `frontend/.env.local`
* **사용법 (`import.meta.env`):**

```
VITE_API_URL=http://localhost:8000/api
```

***

`main.jsx`에 `BrowserRouter` 적용



**`index.html`**: 시작점 (빈 화면 + #root)\
&#xNAN;**`main.jsx`**: React 엔진 시동 (App.jsx를 #root에 넣음)\
&#xNAN;**`App.jsx`**: 화면 전체의 “뼈대”와 페이지 라우팅\
&#xNAN;**`components/`** **`pages/`**: 각각의 화면 구성 요소







