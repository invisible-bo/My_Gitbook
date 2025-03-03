---
icon: css3-alt
description: Cascading Style Sheets
---

# CSS

## CSS(Cascading Style Sheets)

* HTML은 웹 페이지의 **구조**(텍스트, 이미지 등)를 정의
* CSS는 이 구조를 **어떻게 보일지**를 지정
* HTML 코드로 작성된 web요소들의 스타일과 레이아웃을 정의하는 style sheet언어

<div align="left"><figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1).png" alt="" width="286"><figcaption></figcaption></figure></div>

* 속성을 여러 개 지정 가능

### CSS의 역할

1. **색상 설정**:
   * 텍스트, 배경, 버튼 등 요소의 색상을 지정
2. **글꼴 설정**:
   * 글꼴 종류, 크기, 굵기, 간격 등을 조정
3. **배치**:
   * 웹 페이지의 요소를 정렬하거나 배치
   * 예: 가로/세로 정렬, 화면 중앙 배치 등
4. **크기와 여백**:
   * 요소의 크기, 내부/외부 여백, 경계선 등을 정의
5. **반응형 디자인**:
   * 화면 크기에 따라 레이아웃을 변경해 모바일, 태블릿, 데스크탑에서 적절히 보이게 설정

***

### CSS의 기본 문법

CSS는 **선택자(selector)**&#xC640; **속성(property)**&#xC73C;로 구성

```css
선택자 {
    속성1: 값1;
    속성2: 값2;
}
```

ex)

```css
body {
    background-color: lightblue;  /* 배경색을 연한 파란색으로 설정 */
    font-family: Arial, sans-serif;  /* 글꼴을 Arial로 설정 */
    margin: 0;  /* 기본 여백 제거 */
}

h1 {
    color: navy;  /* 제목 텍스트 색상을 남색으로 설정 */
    text-align: center;  /* 제목을 가운데 정렬 */
}

```

***

### CSS를 HTML에 적용

1. **내부 스타일**:
   * `<style>` 태그를 사용해 HTML 문서 내에 CSS를 작성

```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <title>CSS 예제</title>
    <style>
        body {
            background-color: lightblue;
        }
        h1 {
            color: navy;
        }
    </style>
</head>
<body>
    <h1>CSS 테스트</h1>
</body>
</html>
```

| 태그                       | 역할                                            |
| ------------------------ | --------------------------------------------- |
| `<html lang="ko">`       | 문서의 기본 언어를 한국어(ko)로 설정 (SEO, 음성 리더, 번역 기능 영향) |
| `<meta charset="UTF-8">` | 문자의 인코딩 방식을 UTF-8로 설정 (한글, 특수문자 깨짐 방지)        |



2. **외부 CSS 파일:**

* CSS 파일을 별도로 만들어 HTML에서 링크

**CSS 파일(`style.css`)**:

```css
body {
    background-color: lightblue;
}
h1 {
    color: navy;
}
```

**HTML 파일**:

```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <title>CSS 예제</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>CSS 테스트</h1>
</body>
</html>
```

3. **inline스타일**:
   * HTML 태그에 직접 CSS를 작성 (**비추천**: **유지 보수가 어려움)**

```html
<h1 style="color: navy;">CSS 테스트</h1>
```

***

### 주석쓰기

```html
/* 주석내용 */
```

###

### CSS가 중요한 이유

1. **디자인과 개발 분리**:
   * HTML은 구조, CSS는 디자인을 담당하므로 작업을 분리할 수 있다
2. **일관성**:
   * 한 번 작성한 스타일을 여러 페이지에 재사용 가능
3. **사용자 경험 개선**:
   * 반응형 디자인과 시각적 효과로 웹사이트가 더 아름답고 사용하기 편리해짐

***

ex)

<div align="left"><figure><img src="../../../.gitbook/assets/image (77).png" alt="" width="563"><figcaption><p>외부 css를 html 내부에 적용</p></figcaption></figure></div>

<div align="left"><figure><img src="../../../.gitbook/assets/image (78).png" alt="" width="341"><figcaption><p>basic css example</p></figcaption></figure></div>
