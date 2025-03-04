---
icon: atom
---

# Electron

### Electron:

* Electron은 Chromium과 Node.js를 사용하여 JavaScript, HTML, CSS를 이용하여 Windows 또는 Mac, 리눅스에서 직접 설치하여 사용할 수 있는 애플리케이션을 개발 할 수 있다. 크로스 플랫폼 지원으로 이 세 개의 운영체제에서 build 되고 동작한다

### Install Electron

[Electron github](https://github.com/electron/electron-quick-start)

```bash
$ git clone https://github.com/electron/electron-quick-start 
$ cd electron-quick-start
$ npm i && npm start
```

* `npm i` (`npm install`의 줄임말) → `package.json`에 정의된 **의존성 패키지들을 설치**함
* `npm start` → `package.json`에 정의된 `"start"` 스크립트를 실행
  * 보통 `electron .` 명령어가 실행되어 **Electron 앱이 실행됨**

<div align="left"><figure><img src="../../.gitbook/assets/image (85).png" alt="" width="375"><figcaption><p>초기 실행 화면</p></figcaption></figure></div>

***

### Electron Debug

* Electron은 Chromium을 사용하였기 때문에 Chrome에서 개발 시 사용하던 \
  `devTools`를 Electron에서도 사용

```
Menu > View > Toggle Developer Tools
또는 Ctrl + Shift + I
```

{% hint style="info" %}
### **Electron과 Chromium의 관계**

Electron은 **Chromium을 내장한 브라우저 기반 프레임워크**\
즉, Electron 앱을 실행하면 내부적으로 Chromium이 돌아가면서 HTML, CSS, JavaScript를 렌더링

:fire:**정리하면, Chromium은 오픈소스 웹 브라우저 엔진이고,** \
**여러 브라우저와 애플리케이션(Electron, Edge 등)에서 사용되고 있다**
{% endhint %}

***

### Electron Build

* Electron 애플리케이션을 개발한 후, **실제 실행 가능한 프로그램(exe, dmg, AppImage 등)으로 변환하는 과정**을 **빌드(Build)** 라고 한다
* Electron 앱은 기본적으로 **HTML, CSS, JavaScript로 작성된 웹 애플리케이션**이지만, 이를 **Windows, macOS, Linux에서 실행할 수 있는 데스크톱 애플리케이션**으로 패키징해야 함
* **Electron 빌드를 쉽게 도와주는 패키지들이 존재하며, 대표적인 빌드 도구로 electron-builder 사용**

```bash
# electron-builder 설치
npm install --save-dev electron-builder
npm i -D electron-builder
```



* 기본 package.json 상태

```json
{
  "name": "electron-quick-start", // 패키지(앱) 이름. 프로젝트의 고유 식별자로 사용됨.
  "version": "1.0.0", // 앱의 버전. 업데이트 및 배포 시 중요하게 사용됨.
  "description": "A minimal Electron application", // 앱 설명. npm 패키지나 문서에서 참고용으로 사용됨.
  "main": "main.js", // Electron 앱의 진입점 (메인 프로세스 파일).

  "scripts": {
    "start": "electron ." // `npm start` 실행 시 `electron .`을 실행하여 앱을 개발 모드에서 실행.
  },

  "repository": "https://github.com/electron/electron-quick-start", // 프로젝트의 Git 저장소 URL.

  "keywords": [
    "Electron", // Electron 프레임워크 관련 프로젝트임을 나타냄.
    "quick", // 빠르게 시작할 수 있는 템플릿이라는 의미.
    "start", // 스타트업 또는 시작 템플릿과 관련됨.
    "tutorial", // 튜토리얼용 프로젝트라는 의미.
    "demo" // 데모(샘플) 프로젝트라는 의미.
  ],

  "author": "GitHub", // 프로젝트의 작성자 또는 소유자.
  "license": "CC0-1.0", // 프로젝트의 라이선스. (CC0-1.0은 퍼블릭 도메인과 유사하여 자유롭게 사용 가능.)

  "devDependencies": {
    "electron": "^34.3.0", // Electron의 개발 버전 의존성. (^34.3.0은 34.x.x 버전 사용 가능.)
    "electron-builder": "^25.1.8" // Electron 앱을 설치 파일(.exe, .dmg, .AppImage 등)로 빌드하는 도구.
  }
}

```

* 본인 app등록을 위해 수정한 version

```json
{
  "name": "kitty-player", // 앱의 이름 (프로젝트 ID로도 사용됨)
  "version": "1.0.0", // 앱의 현재 버전 (업데이트 및 배포 시 사용)
  "description": "A simple Electron-based music player application", // 앱 설명
  "main": "main.js", // Electron 앱의 진입점 (메인 프로세스 파일)

  "scripts": {
    "start": "electron .", // 개발 모드에서 앱 실행
    "dist": "electron-builder", // 앱을 패키징하여 실행 파일 생성
    "pack": "electron-builder --dir", // 설치 파일 없이 디렉토리 형태로 빌드
    "build:win": "electron-builder --win", // Windows용 설치 파일 빌드
    "build:mac": "electron-builder --mac", // macOS용 설치 파일 빌드
    "build:linux": "electron-builder --linux" // Linux용 설치 파일 빌드
  },

  "repository": {
    "type": "git",
    "url": "https://github.com/invisible-bo/kitty_player" 
  },

  "keywords": [
    "Electron", // Electron 기반 앱
    "Music Player", // 음악 플레이어 앱임을 명시
    "Audio", // 오디오 관련 앱
    "Desktop App", // 데스크탑 애플리케이션
    "Media Player" // 미디어 플레이어 관련 기능
  ],

  "author": "invisible-bo", // 네 이름으로 변경
  "license": "MIT", // 라이선스를 MIT로 변경 (오픈소스 배포 가능)

  "devDependencies": {
    "electron": "^34.3.0", // Electron 프레임워크 (앱 실행에 필수)
    "electron-builder": "^25.1.8", // 앱을 배포 가능한 실행 파일로 빌드하는 패키지
    "electron-store": "^8.1.0", // 로컬 설정 저장을 위한 패키지
    "electron-updater": "^5.5.0", // 자동 업데이트 기능 추가
    "fs-extra": "^11.1.1" // 파일 시스템 관리 기능 강화
  },

  "build": {
    "appId": "com.bo.kittyplayer", // 앱의 고유 식별자 (배포 시 필요)
    "productName": "Kitty Player", // 빌드된 앱의 표시 이름
    "directories": {
      "output": "dist" // 빌드된 결과물이 저장될 폴더
    },
    "files": [     //앱을 빌드할 때 포함할 파일 및 폴더 목록을 정의
      "main.js",   //electron-builder가 실행될 때, 여기에 명시된 파일들만 패키징
      "index.html",
      "renderer.js",
      "assets/**/*"  //assets 폴더 안의 모든 파일과 하위 폴더 포함
    ],
    "mac": {
      "target": "dmg",
      "icon": "build/icon.icns"
    },
    "win": {
      "target": "nsis",
      "icon": "build/icon.ico"
    },
    "linux": {
      "target": "AppImage",
      "icon": "build/icon.png"
    }
  }
}

```

* ```
  "pack": "electron-builder --dir",
  개발단계에서 설치파일 없이 만들고 최종 version이 나온 후에 npm run dist로 설치파일 생성
  ```

***

```bash
npm start
```

* Electron이 정상적으로 실행되는지 확인



* 그 다음 본격적인 기능 구현
  *   ex)

      * **오디오 재생 (Howler.js, Web Audio API 등 사용)**
      * **로컬 파일 불러오기 (`fs` 모듈 사용)**
      * **UI 디자인 (HTML, CSS, JavaScript)**
      * **설정 저장 (`electron-store` 활용)**
      * **자동 업데이트 (`electron-updater` 활용, 선택 사항)**

      **→ 기능을 하나씩 추가하면서 `npm start`로 실행하며 테스트!**

***

설치 파일 없이 빌드 테스트 (`pack` 실행)

```bash
npm run pack
```

실행 후 확인할 사항

* `dist/` 폴더가 생성되었는지 확인
* `dist/플랫폼-unpacked/` 폴더 내에서 실행 가능한 파일이 있는지 확인
* 앱이 정상적으로 실행되는지 확인

**`"npm run pack"`은 설치 파일을 만들지 않고 실행 가능한 빌드만 생성함.**\
:fire: 이 단계에서 **파일이 정상적으로 빌드되는지 먼저 확인하는 게 중요**

***

최종 설치 파일 빌드 (`dist` 실행)

* 앱 개발이 완료되고, 실행 테스트도 문제없다면 **설치 파일을 생성**

```bash
npm run dist
```

실행 후 확인할 사항

* `dist/` 폴더에 OS별 설치 파일이 생성되었는지 확인
* Windows → `.exe`
* macOS → `.dmg`
* Linux → `.AppImage` or `.deb`

:fire: **설치 파일을 생성한 후, 직접 실행해 보고 정상적으로 동작하는지 확인**

***

배포 준비

#### **배포 방법 1: GitHub Release 자동 배포**

1. GitHub 저장소를 만든다.
2. `electron-updater`를 설정하여 GitHub Release를 통한 자동 업데이트 지원
3. `npm run dist` 실행 후 `dist/` 폴더에 생성된 설치 파일을 GitHub Release에 업로드

#### **배포 방법 2: 수동 배포**

* **파일 공유 방식**\
  `dist/` 폴더에 있는 `.exe`, `.dmg`, `.AppImage` 파일을 직접 공유
* **자체 웹사이트에서 다운로드 링크 제공**

<div align="left"><figure><img src="../../.gitbook/assets/image (86).png" alt=""><figcaption></figcaption></figure></div>

***

### Electron process 구조

1. main process `main.js`&#x20;

* Electron의 핵심 로직
* 앱의 창(Window)을 생성하고 관리
* 파일 시스템 접근, 네이티브 기능 호출, IPC 통신 처리
* `BrowserWindow`를 통해 렌더러 프로세스를 실행

2. renderer process `renderer.js`&#x20;

* UI를 담당하는 프로세스 (HTML, CSS, JS 실행)
* 사용자의 입력을 감지하고 화면을 업데이트
* Electron의 `ipcRenderer`를 사용해 메인 프로세스와 통신
* **기본적으로 브라우저 환경과 동일하게 동작 (단, 보안 설정에 따라 Node.js 기능 제한 가능)**

3. `preload.js`&#x20;

* `preload.js`는 "메인 프로세스(Main)와 렌더러 프로세스(Renderer) 사이의 보안 브릿지 역할
* preload.js를 사용하면 보안을 유지하면서도 렌더러에서 메인 프로세스의 기능(Node.js API, Electron API 등)을 사용할 수 있게해줌
  *   ### **`preload.js`가 필요한 이유**

      **Electron에서는 보안을 강화하기 위해 `nodeIntegration: false`를 권장**\
      하지만, `nodeIntegration: false`를 설정하면 렌더러에서 `require('electron')`을 직접 사용할 수 없음\
      그래서 **렌더러에서 메인 프로세스 기능을 안전하게 사용할 수 있도록 `preload.js`가 필요**



