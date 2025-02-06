# Gitmoji

### gitmoji-cli

1. Node.js & npm 설치 (필수)

Mac:

```bash
brew install node 
```

* `Homebrew`가 없으면&#x20;

[homebrew](https://brew.sh/)





Windows:

[LTS 버전 다운로드](https://nodejs.org/ko)

설치 후 `cmd` 또는 `PowerShell`에서 확인

```bash
node -v
npm -v
```



2. `gitmoji-cli` 설치

```bash
npm install -g gitmoji-cli
```



3. `gitmoji-cli` 사용법

```bash
gitmoji -c
# 커밋 단계에서 입력
```

* 실행하면 **이모지 선택 화면**이 나오고, 커밋 메시지를 입력하면 자동으로 적용

<div align="left"><figure><img src="../../../.gitbook/assets/image.png" alt="" width="401"><figcaption></figcaption></figure></div>





4. Gitmoji를 `git commit` 명령어에 자동 연결(선택사항)

```bash
gitmoji --init # 자동실행
gitmoji --remove # 자동실행 해제
```

* 이제 `git commit`을 실행하면 자동으로 Gitmoji 선택창이 뜸



