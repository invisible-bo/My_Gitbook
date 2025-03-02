# Node.js & NPM

### Node.js

* 오픈소스 JavaScript 런타임 환경이다. 일반적으로 JavaScript는 브라우저에서 실행되지만, Node.js를 사용하면 브라우저가 아닌 서버 환경에서도 JavaScript를 실행할 수 있다



### NPM(Node Package Manager)

* Node.js 패키지 관리자로, JavaScript 라이브러리 및 패키지를 설치하고 관리할 수 있는 도구
* #### **NPM의 역할**
  * 패키지(라이브러리) **설치, 업데이트, 삭제** 가능
  * 프로젝트에서 사용할 **의존성(Dependencies) 관리**
  * 전역(Global) 또는 로컬(Local)로 패키지 설치 가능
  * npm 스크립트를 이용해 빌드, 실행, 테스트 자동화 가능

```bash
# Node.js 및 NPM 버전 확인
node -v
npm -v

# 새로운 Node 프로젝트 생성 (package.json 생성)
npm init  # 대화형 설정
npm init -y  # 기본값으로 설정

# 패키지 설치
npm install 패키지이름  # 로컬 설치
npm install -g 패키지이름  # 전역 설치

# 모든 패키지 업데이트
npm update

# 특정 패키지 삭제
npm uninstall 패키지이름

# 프로젝트에서 사용 중인 패키지 목록 확인
npm list

# 캐시 정리 (에러 발생 시 유용)
npm cache clean --force
```

`package.json`&#x20;

*   `package.json`은 프로젝트의 패키지 정보를 관리하는 파일로, 아래 정보를 포함한다.

    ```
    {
      "name": "my_project",
      "version": "1.0.0",
      "description": "My Node.js Project",
      "main": "index.js",
      "scripts": {
        "start": "node index.js"
      },
      "dependencies": {
        "express": "^4.18.2"
      },
      "devDependencies": {
        "nodemon": "^2.0.22"
      }
    }
    ```
* **dependencies**: 실제 애플리케이션 실행에 필요한 패키지 목록
* **devDependencies**: 개발 중에만 필요한 패키지 (예: `nodemon`, `eslint` 등)

:fire:`npm install`을 실행하면 `package.json`을 참고하여 모든 의존성을 설치함.





Node.js 자체는 백엔드 기술이지만, **프론트엔드 개발에서도 도구로 활용**될 수 있다. \
프론트엔드 개발 환경을 구성하고, 빌드 도구를 실행하는 등의 작업을 할 때 Node.js가 필요하다

* **프론트엔드 개발 환경 설정**
  * Webpack, Vite, Parcel 같은 **번들러** 실행
  * Babel을 이용해 최신 JavaScript 코드 변환
  * PostCSS, Sass 등의 스타일링 처리
* **패키지 관리**
  * `npm` 또는 `yarn`을 이용해 프론트엔드 라이브러리 설치 (예: React, Vue.js, Tailwind CSS)
* **개발 서버 실행**
  * `vite dev`, `next dev` 등 Node.js 기반 개발 서버를 실행하여 프론트엔드 개발 환경을 구축
* **SSR(Server-Side Rendering) 및 풀스택 개발**
  * Next.js, Nuxt.js 같은 프레임워크는 서버 사이드 렌더링(SSR)을 지원하는데, 이때 Node.js가 필요함.







