# Block & Inline

### HTML 요소의 두 형태

1. Block

* tag의 내용과 관계 없이 상위 요소의 너비에 맞게 너비를 차지함
  * 레이아웃의 영역을 지정할 때 주로 사용

2. Inline

* tag의 내용에 맞춰서 너비가 결정됨
  * 레이아웃에 영향을 주지 않고 일부 내용에만 스타일이나 내용의 구분을 주고 싶을때 사용

***

### Block요소

* 화면의 layout, 얼개를 짜거나 구성을 나눌때 자주 사용(Grouping)\
  이 요소에 CSS style을 적용해서(크기, 위치등) 화면의 layout 완성.
  * `div` : block 요소의 대표적인 tag. 아무 의미를 담지 않는 블록요소로 \
    하위 블록 요소들의 상위 개념
    * section : 서로 다른 내용 구성이 들어갈 영역을 구분하는 블록요소
    * article : 동일한 내용 구성이 반복될 때 구분하기 위한 블록요소
    * header : 본문 내용의 머리말 영역 블록요소
    * footer : 본문 내용의 바닥글 영역 블록요소

<div align="left"><figure><img src="../../../../.gitbook/assets/image (65).png" alt="" width="375"><figcaption></figcaption></figure></div>

* Section
  * 3개가 같은 종류의 데이터를 다루고 있지는 않은데 본문에서의 중요도나 레벨이 같음
* Article
  * 다루는 데이터의 형태가 동일함

***

### Inline요소

* **화면의 layout에 영향을 미치지 않고** 특정 내용을 강조하거나 구분하고 싶을 때 사용
* strong, i 등의 요소가 이에 속하고 대표적인 tag로 span이 있음
  * span : 아무 의미도 내포하지 않은 inline요소. CSS style과 함께 특정 내용 강조, 구분

