# Text Style

### text style

* color: text color (빛의 3원색 기준, 16진수 코드)
* font-family: 글씨체 (글씨체에 띄어쓰기가 있을 경우 쌍 따옴표 사용)
* font-size: 크기 (pt, px, em등의 단위)
* font-weight: 굵기 (100\~900 사이 값이나 bold로 굵은 굵기 표현)
* line-height: 줄 간격(% 단위나 px등의 단위) &#x20;

&#x20;

### Font

* font는 font명을 직접 작성함으로써 지정. 하나의 font-family 이름이 여러단어로\
  이루어져 있다면 쌍따옴표, 아니면 그냥 기술
* 가장 먼저 서술된 font가 없다면 그 뒤의 font 적용됨
* 내가 지정한 font가 없을 경우 알아서 선택되도록 serif, sans-serif, cursive, monospace\
  중 특성을 가진 font를 알아서 선택하도록 할 수 있다

<div align="left"><figure><img src="../../../../.gitbook/assets/image (75).png" alt="" width="375"><figcaption></figcaption></figure></div>

### Size units

1. **절대 단위 (Absolute Units)**
   * 크기가 **고정됨**, 화면 크기나 해상도에 영향을 받지 않음.
   * 단위 (영어 표기):
     * `px` (**pixels** - 픽셀)
     * `pt` (**points** - 포인트, 1pt = 1/72인치)
     * `cm` (**centimeters** - 센티미터)
     * `mm` (**millimeters** - 밀리미터)
     * `in` (**inches** - 인치, 1in = 2.54cm)
     * `pc` (**picas** - 1pc = 12pt)
2. **상대 단위 (Relative Units)**
   * 크기가 **유동적**이며, 부모 요소나 화면 크기에 따라 변함.
   * 단위 (영어 표기):
     * `%` (**percentage** - 백분율, 부모 요소 대비 크기)
     * `em` (**relative to parent font-size** - 부모 글꼴 크기 기준)
     * `rem` (**relative to root font-size** - 루트 요소(`<html>`) 글꼴 크기 기준)
     * `vw` (**viewport width** - 뷰포트 너비 기준, 1vw = 1% 화면 너비)
     * `vh` (**viewport height** - 뷰포트 높이 기준, 1vh = 1% 화면 높이)
     * `vmin` (**viewport minimum** - `vw`, `vh` 중 작은 값)
     * `vmax` (**viewport maximum** - `vw`, `vh` 중 큰 값)

***





