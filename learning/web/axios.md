# Axios

### Axios

* **Axios:** Promise 기반 JavaScript **HTTP 클라이언트**
  * **`Promise`는 비동기 작업의 완료 또는 실패를 나타내는 객체** \
    &#xNAN;**"나중에 결과를 줄 테니 기다려" 라는 약속**
  *   | **`pending` (대기)** | 작업이 아직 끝나지 않음 (초기 상태) |
      | ------------------ | --------------------- |

      | **`fulfilled` (성공)** | 작업이 성공적으로 완료됨 → `.then()` 실행 |
      | -------------------- | ---------------------------- |

      | **`rejected` (실패)** | 작업이 실패함 → `.catch()` 실행 |
      | ------------------- | ----------------------- |
* 주로 **API 요청, 데이터 전송, 크롤링** 등에 사용
* **요청(Request):** API, 서버에 데이터 요구
* **응답(Response):** 데이터 받아와서 처리
* **간단한 문법:** `fetch`보다 사용법이 직관적.
* **Promise 기반:** `async/await`을 지원.
* **자동 JSON 파싱:** 응답 데이터를 자동으로 `JSON`으로 처리.
* **인터셉터:** 요청(Request)과 응답(Response)을 가로채서 공통 로직 처리 가능.
* **에러 처리:** `HTTP Status Code`에 따른 에러 구분이 편리.
* **요청 취소(Cancellation):** 불필요한 요청을 중단할 수 있음.
* **타임아웃 및 재시도 설정:** API 호출 실패 시 재시도 및 타임아웃 처리 가능
* :fire:JavaScript/Node.js 전용 라이브러리



* Axios 설치

```bash
npm install axios
```

**프론트엔드에서 (React, Vue, Angular)**

* \*\*서버(API)\*\*와 \*\*프론트(UI)\*\*를 연결하는 브릿지
* `GET`, `POST`, `PUT`, `DELETE`로 **API 통신**
* **CORS 설정**, **JWT 토큰** 쉽게 추가

















***

**프론트 Axios 특징:**

* 브라우저에서 **API 호출**
* **JWT 토큰, 쿠키 자동 처리**
* **UI 반영** 빠름

#### **백엔드(Django, Node.js)에서도 사용 가능**

**"Axios는 백엔드에서도 똑같이 쓴다."**

* **API 간 데이터 연계:** 백엔드가 **외부 API**에서 데이터 끌어올 때
* **OpenAI, 카카오 API 통신**
* **크론 잡(Cron job) 자동화 작업**

**백엔드 Axios 특징:**

* **외부 API와 통신 (OpenAI, 카카오, 네이버)**
* **서버 간 데이터 파이프라인 연결**
* **비동기 처리 + 빠른 병렬 요청**

## 프론트엔드(React/Vue) vs 백엔드(Node.js/Django)에서&#x20;

## Axios 사용 비교

| 구분          | 프론트엔드 (React/Vue) | 백엔드 (Node.js/Django)  |
| ----------- | ----------------- | --------------------- |
| **주요 목적**   | API 호출 → 화면에 표시   | API 호출 → 데이터 처리 및 저장  |
| **요청 출발지**  | 브라우저 (클라이언트)      | 서버 (서버 간 통신)          |
| **CORS 문제** | CORS 설정 필수        | 서버 간 통신이므로 CORS 문제 없음 |
| **속도**      | 클라이언트에서 즉시 반응     | 서버에서 비동기 병렬 처리 가능     |
| **보안**      | API 키 노출 위험 있음    | API 키 안전 (백엔드에만 저장됨)  |

***

## **Axios의 강력한 기능 (프론트 & 백 공통)**

#### **1. 인터셉터 (Interceptor)**

요청/응답 전에 **가로채기**

* **프론트:** `Authorization` 헤더 자동 추가
* **백엔드:** API 응답 포맷 통일

```
axios.interceptors.request.use((config) => {
  config.headers.Authorization = `Bearer ${localStorage.getItem('token')}`;
  return config;
});
```

#### **2. 병렬 요청 (Promise.all)**

**API 여러 개 동시에 호출 (비동기 병렬)**

* **책 추천 API + 리뷰 API + 작가 정보 API** 동시 호출
* **백엔드 서버 간 데이터 수집 최적화**

```javascript
javascript복사편집const [books, reviews] = await Promise.all([
  axios.get('/api/books'),
  axios.get('/api/reviews'),
]);
```

#### **3. 에러 핸들링**

**요청 실패 시 빠른 복구 및 공통 처리**

```javascript
javascript복사편집axios.interceptors.response.use(
  response => response,
  error => {
    console.error('API Error:', error.response?.data || error.message);
    if (error.response?.status === 401) {
      alert('인증이 필요합니다. 로그인하세요.');
    }
    return Promise.reject(error);
  }
);
```



## 프론트엔드 vs 백엔드 vs 공통점

| 구분        | 역할                   |
| --------- | -------------------- |
| **프론트엔드** | API 호출 → 화면에 즉각 표시   |
| **백엔드**   | API 호출 → 데이터 가공 및 저장 |
| **공통점**   | 비동기 통신, 인터셉터, 병렬 처리  |

***

* 비동기성은 "도구"가 아니라 "코드 작성법"에 달렸다
* **Axios 자체는 언제나 비동기(`Promise` 기반)**
* &#x20;**`await`은 비동기 요청을 동기적으로 보이게 만든다.**
* **`Promise.all()`을 써서 병렬 처리해야 진짜 비동기의 힘을 쓴다**

| 구분                        | Axios 사용 | 비동기 코드 | 병렬 처리 | 실제 실행 속도 |
| ------------------------- | -------- | ------ | ----- | -------- |
| **`await` 직렬 코드**         | ✅        | ✅      | ❌     | 느림 (7초)  |
| **`Promise.all()` 병렬 코드** | ✅        | ✅      | ✅     | 빠름 (3초)  |

* **"Axios는 비동기 병기다."**\
  &#xNAN;**"하지만 `await`으로 순서대로 쏘면 권총이고,"**\
  &#xNAN;**"`Promise.all()`로 동시에 쏘면 기관총이다."**





