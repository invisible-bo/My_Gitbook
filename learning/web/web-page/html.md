---
icon: html5
description: HyperText Markup Language
---

# HTML

## HTML(Hyper Text Markup Language)

* 웹 페이지의 구조를 정의하고 콘텐츠를 표시하는 데 사용되는 **Markup Language(마크업언어)**
* 여는 **tag**와 닫는 **tag**의 **한 쌍**
* tag는 **중첩**될 수 있다

<div align="left"><figure><img src="../../../.gitbook/assets/image (64).png" alt="" width="300"><figcaption></figcaption></figure></div>

### 1. HTML 기본구조

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>문서 제목</title>
</head>
<body>
    <h1>안녕하세요!</h1>
    <p>HTML 문법을 배우는 중입니다.</p>
</body>
</html>
```

* `<!DOCTYPE html>`: HTML5 문서를 선언.
* `<html>`: HTML 문서의 루트 요소.
* `<head>`: 문서 정보를 포함(메타 데이터, 제목 등).
* `<body>`: 화면에 표시될 콘텐츠를 포함. 실제 사용자에게 보여질 화면을 구현

코드 편집 프로그램(HTML기반 editor)

[Sublime Text 3](https://www.sublimetext.com/3)     &#x20;



:fire::fire::fire:크롬 개발자 도구

* Ctrl + Shift + I

***

### 2. HTML 태그

### Text 내용 정의 tag

* heading 제목 tag: 제목을 표시할 때 사용. 숫자가 작을수록 글자가 커짐
  * h1, h2, h3, h4, h5, h6
* paragraph 문단 tag : 본문 텍스트를 작성할 때 사용. 하나의 문단으로 지정되어 화면에 보여짐
  * p
* break  줄 바꿈  tag : 혼자서 사용하는 **홀 태그.** **내용이 포함된것이 아님**
  * \<br> 혹은 \<br/> 홀로 쓰임
* italic 기울임tag
  * i
* strong 강조 tag
  * strong
* bold 굵게 tag
  * b
* :fire:Horizontal rule tag : 문서 내에 **가로 선**. **홀태그**
  * \<hr>

| 태그         | 기본 스타일 | 의미(semantic) | 검색엔진(SEO)      | 스크린 리더    |
| ---------- | ------ | ------------ | -------------- | --------- |
| `<b>`      | 볼드체    | 없음 (단순 스타일)  | 영향 없음          | 그냥 굵게 읽음  |
| `<strong>` | 볼드체    | 중요한 내용을 강조   | 중요한 키워드로 인식 가능 | 강한 강조로 읽음 |



### List tag

* 항목들을 구분해서 나열할때 사용하는 tags
* Ordered list tag&#x20;
  * ol
    * 1, 2, 3
* Unordered list tag
  * ul
* List item tag
  * li

