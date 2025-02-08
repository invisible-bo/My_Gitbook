---
icon: github
---

# Gitmoji

gitmoji-cli

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

{% hint style="info" %}
`gitmoji`가 CMD에서는 되는데 Git Bash에서 `command not found` 오류가 나는 경우



1. CMD에서 다음 명령어 실행

`where gitmoji`&#x20;

ex) C:\Users\사용자이름\AppData\Roaming\npm\gitmoji



2. Git Bash에서 환경 변수(PATH) 추가

`echo 'export PATH=$PATH:/c/Users/사용자이름/AppData/Roaming/npm' >> ~/.bashrc` &#x20;

`source ~/.bashrc`&#x20;

Git Bash를 껐다가 다시 실행



3. Git Bash에서 실행

`gitmoji -v`&#x20;

Gitmoji CLI version이 나오면 성공


{% endhint %}



3. `gitmoji-cli` 사용법

```bash
gitmoji -c
# commit 단계에서 입력
```

* 실행하면 **이모지 선택 화면**이 나오고, commit 메시지를 입력하면 자동으로 적용



자주 쓰는 Gitmoji

<table data-full-width="true"><thead><tr><th>Gitmoji</th><th>커밋 타입</th><th>설명</th></tr></thead><tbody><tr><td>✨ <code>:sparkles:</code></td><td><code>feat</code></td><td>새로운 기능 추가</td></tr><tr><td>🐛 <code>:bug:</code></td><td><code>fix</code></td><td>버그 수정</td></tr><tr><td>♻️ <code>:recycle:</code></td><td><code>refactor</code></td><td>코드 리팩토링 (기능 변화 없음)<br><strong>기능은 그대로 유지하면서 코드의 구조를 개선하는 작업</strong><br>코드의 <strong>가독성, 유지보수성, 성능 최적화</strong> 등을 위해 내부 로직을 정리</td></tr><tr><td>📝 <code>:memo:</code></td><td><code>docs</code></td><td>문서 수정 (README, 주석 등)</td></tr><tr><td>🎨 <code>:art:</code></td><td><code>style</code></td><td>코드 스타일 변경 (공백, 포맷팅, 세미콜론 추가 등)</td></tr><tr><td>✅ <code>:white_check_mark:</code></td><td><code>test</code></td><td>테스트 코드 추가 및 수정</td></tr><tr><td>🔧 <code>:wrench:</code></td><td><code>chore</code></td><td>빌드, 패키지 매니저 설정 변경 (CI/CD, 라이브러리 업데이트 등)</td></tr><tr><td>⚡ <code>:zap:</code></td><td><code>perf</code></td><td>성능 개선</td></tr><tr><td>👷 <code>:construction_worker:</code></td><td><code>ci</code></td><td>CI/CD 관련 변경</td></tr><tr><td>🏗️ <code>:building_construction:</code></td><td><code>build</code></td><td>빌드 시스템 변경 (예: Webpack, Docker 설정 변경)</td></tr><tr><td>⏪ <code>:rewind:</code></td><td><code>revert</code></td><td>이전 커밋 되돌리기</td></tr><tr><td>🎉 <code>:tada:</code></td><td><code>init</code></td><td>초기 커밋</td></tr></tbody></table>

<div align="left"><figure><img src="../../../.gitbook/assets/image (5) (1).png" alt="" width="401"><figcaption></figcaption></figure></div>

***

4. Gitmoji를 `git commit` 명령어에 자동 연결(선택 사항)

```bash
gitmoji --init # 자동실행
#git commit을 실행하면 자동으로 Gitmoji 선택 창이 뜸

gitmoji --remove # 자동실행 해제
```





