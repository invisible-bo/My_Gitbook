# \*kitty player project

### Kitty player

<div align="left"><figure><img src="../../.gitbook/assets/image (1).png" alt="" width="375"><figcaption></figcaption></figure></div>

* Figma로 기본 design 완성

***

#### **HTML과 CSS의 역할**

**HTML (구조)**

* 버튼, 이미지, 텍스트 같은 **기본적인 요소 배치**
* `div`, `section`, `button`, `img` 등의 태그로 **Figma 프레임 구조 재현**
* 계층적인 구조를 만들고, CSS로 스타일링 가능하도록 설정

**CSS (디자인 스타일)**

* 배경색, 테두리, 버튼 크기, 폰트 스타일 적용
* **Figma에서 설정한 색상, 폰트, 크기, 정렬 방식 반영**
* `flexbox` 또는 `grid`를 활용해 정렬

***

builder.io plugin으로 기본 프레임만 html과 css로 따오고 버튼들은 이미지를 import해서 붙혀 보기로 함

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption><p>어긋난 부분들이 발생해서 직접미세조정</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

<div align="left"><figure><img src="../../.gitbook/assets/image (4).png" alt="" width="244"><figcaption><p>playbar의 키티 버튼이 컨테이너 밖으로 자꾸 나가는 현상</p></figcaption></figure></div>

overflow를 hidden 으로 설정하자 버튼이 playbar내부에 가려지고 오른쪽 일정 부분 이상 이동이 안됨

seekbar와 playbar 모두width 100%로 변경

position: relative;, padding: 0;,&#x20;

seekbar position: absolute;로 playbar 내부에서 정확한 위치 설정



<div align="left"><figure><img src="../../.gitbook/assets/image (6).png" alt="" width="179"><figcaption><p>fixed</p></figcaption></figure></div>

```django-html
<input type="range" id="seekbar" min="0" value="0" step="1">
```

* **MP3 플레이어의 진행 상태를 조절하는 슬라이더(시크바)** 역할을 하는 `<input>` 요소

| 속성             | 의미           | 현재 코드에서 적용된 역할                   |
| -------------- | ------------ | -------------------------------- |
| `type="range"` | 슬라이더 형태의 입력값 | 숫자를 조절할 수 있는 슬라이더 UI 생성          |
| `id="seekbar"` | 슬라이더 요소의 ID  | JavaScript에서 이 슬라이더를 조작하기 위해 사용됨 |
| `min="0"`      | 최소 값         | MP3 재생 시간의 시작점 (0초)              |
| `value="0"`    | 초기 값         | 슬라이더가 처음에는 0초(처음 위치)에서 시작함       |
| `step="1"`     | 증가 단위        | 슬라이더를 움직일 때 1초 단위로 조절됨           |



<div align="left"><figure><img src="../../.gitbook/assets/image (7).png" alt="" width="177"><figcaption><p>add playbtn</p></figcaption></figure></div>

CSS와 HTML에서PlayPausebtn으로 합쳐서 설정, JS에서 이미지 두개 각각

<div align="left"><figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure></div>

***

<div align="left"><figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure></div>

* HTML `<audio>` 태그 (`audioPlayer`)

**`<audio>` 태그는 가장 기본적인 웹 오디오 플레이어**\
✔ **HTML5에서 기본 제공하는 오디오 재생 기능**\
✔ **MP3, WAV, OGG 등 여러 오디오 포맷을 지원**\
✔ **JavaScript와 함께 사용하면 더 다양한 기능을 추가할 수 있음**

<div align="left"><figure><img src="../../.gitbook/assets/image (10).png" alt="" width="179"><figcaption><p>audio 재생 및 버튼 변환 확인</p></figcaption></figure></div>



















