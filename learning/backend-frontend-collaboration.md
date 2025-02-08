---
icon: arrows-to-line
description: 협업(Backend-Frontend Collaboration)혹은 API 연동 작업
---

# Backend-Frontend Collaboration

### Django 내부에서 HTML, CSS, JS 작성 (backend 중심 개발)

* backedn 개발자가 Django template **시스템**을 사용하면, \
  Django 내부에서 직접 HTML, CSS, JS를 작성할 수도 있다.\
  이 방식은 **"서버 렌더링 방식"**

1. Django backend에서 HTML 파일을 template으로 작성
2. Django에서 이 HTML을 렌더링해서 제공
3. CSS, JS도 Django `static/` 폴더에서 관리 가능

특징:

* backend 개발자가 Django 안에서 모든 걸 처리 가능
* SSR(서버 사이드 렌더링) 방식이라 SEO에 강함
* 프론트엔드 개발자가 백엔드 프로젝트 내부에서 작업해야 함

***

### Frontend와 Backend를 분리 (완전 독립된 Front, API 연동)

* frontend는 **React, Vue.js 같은 SPA (Single Page Application)** 로 만들고
* backend는 Django의 **DRF(Django REST Framework)** 로 **API 서버**를 만든 뒤 통신하는 방식

```
📂 frontend/ (React, Vue 등)
   ├── src/
   ├── public/
   ├── package.json (Node.js 프로젝트)
   ├── index.html (SPA 기반)
📂 backend/ (Django)
   ├── myproject/
   ├── users/ (회원가입, 로그인 관련 API)
   ├── db.sqlite3
   ├── manage.py
```

특징:

* frontend 개발자는 Django에 얽매이지 않고 React/Vue 등 최신 기술을 활용 가능
* Django는 API만 제공하고, 프론트엔드는 독립적으로 운영 가능
* 확장성이 뛰어나고, 모바일 앱에서도 같은 API 사용 가능
* 초반 설정이 다소 번거로움

| 방식              | Django 템플릿 방식   | 프론트엔드 & 백엔드 분리 (API) |
| --------------- | --------------- | -------------------- |
| ✅ 빠르게 만들기       | O               | X                    |
| ✅ SEO(검색엔진 최적화) | O               | X                    |
| ✅ 최신 웹 트렌드      | X               | O                    |
| ✅ 유지보수          | X (백엔드와 프론트 혼재) | O (역할 분리)            |
| ✅ 확장성 (모바일 앱 등) | X               | O                    |

* **Django 템플릿 방식** → 빠르고 간단한 웹사이트
* **프론트 & 백엔드 분리 방식** → SPA, 모바일 앱까지 확장 가능





