# CSS selector

### Css selector

* **어떤 HTML 요소에 스타일을 적용할지 선택하는 방법**\
  쉽게 말해, **CSS에서 특정 태그, 클래스, ID 등을 선택해서 스타일을 먹이는 도구**
* 내/외부 style sheet에서 문서의 html 요소를 선택할 수 있게 하는 문법
* tag selector: html 문서의 모든 특정 tag 선택

```css
h1 {
    color: red; /* 모든 h1 태그를 빨간색으로 */
}
p {
    font-size: 16px; /* 모든 p 태그의 글자 크기 */
}
```

* id selector: html 문서의 하나의 요소를 특정해서 선택
  * **하나의 id**는 **문서 내 하나만 존재**해야 함
  * (#)기호로 표현

```css
#main-title {
    font-size: 24px;
    color: blue;
}
```

```html
<h1 id="main-title">main title</h1>
```

* class selector: html문서의 여러 요소를 그룹으로 선택
  * 하나의 class는 문서 내 여러 개에 지정할 수 있음
  * `.` 기호로 표현

```css
.red-text {
    color: red;
}

```

```html
<p class="red-text">this sentence is red</p>
```

***

### Advanced selector

* 직계 자식 선택자 (Child Selector, `>` )



* 자손 선택자 (Descendant Selector, 띄어쓰기 사용)



* 상태 선택자 (Pseudo-classes)
  * 반응 선택자: hover(마우스 커서가 위에), active(활성화된), visitied(방문한 link)
  * 상태 선택자: focus(입력, 버튼에포커스), enabled(사용가능한), disable(사용불가능한)



* 특성 선택자
  * a\[href]: href속성이 지정된 요소
  * a\[href=https://www.google.com]: href 속성이 google 사이트 주소인 경우의 요소











