# \*Useful CSS effects

### transform

* **`translate(x, y)`** → X, Y축으로 이동
* **`scale(x, y)`** → 크기 조절
* **`rotate(deg)`** → 회전
* **`skew(x, y)`** → 기울기

### transition

* **`transition: all 0.3s ease-in-out;`** → 모든 속성을 0.3초 동안 부드럽게 변형
* **`transition-property`** → 변형할 속성 지정 (`transform`, `background`, `opacity` 등)
* **`transition-duration`** → 변형 지속 시간
* **`transition-timing-function`** → 속도 변화 스타일 (`ease`, `linear`, `ease-in-out` 등)
* **`transition-delay`** → 변형이 시작되기까지의 지연 시간



### display: flex;

* 가로로 편하게 배치 하기
* 내가 가로로 배치하고 싶은 box들의 부모 box에 display: flex;
* align-items: center;&#x20;
* justify-content: center; 중앙 정렬
* flex-direction: column; 세로 정렬

<div align="left"><figure><img src="../../../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure></div>

* box 사이를 띄울때 가상의 box를 넣고 flex-grow

display: flex;\
flex-direction: column; /\* 세로 정렬 _/_\
_justify-content: center; /_ 세로 중앙 정렬 _/_\
_align-items: center; /_ 가로 중앙 정렬 _/_\
_height: 100vh; /_ 화면 높이 기준 중앙 정렬 _/_\
_text-align: center; /_ 텍스트 중앙 정렬 \*/

<figure><img src="../../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>







