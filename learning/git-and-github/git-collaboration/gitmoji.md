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

| 이모지 | 태그         | 설명                  |
| --- | ---------- | ------------------- |
| ✨   | `feat`     | 새로운 기능 추가           |
| 🐛  | `fix`      | 버그 수정               |
| 🎨  | `style`    | 코드 스타일 변경 (기능 변경 X) |
| 🔨  | `refactor` | 코드 리팩토링 (기능 변화 없음)  |
| 🚀  | `chore`    | 빌드, CI/CD 설정 변경     |
| 📝  | `docs`     | 문서 수정 (README 등)    |

<div align="left"><figure><img src="../../../.gitbook/assets/image.png" alt="" width="401"><figcaption></figcaption></figure></div>

4. Gitmoji를 `git commit` 명령어에 자동 연결(선택 사항)

```bash
gitmoji --init # 자동실행
#git commit을 실행하면 자동으로 Gitmoji 선택 창이 뜸

gitmoji --remove # 자동실행 해제
```





