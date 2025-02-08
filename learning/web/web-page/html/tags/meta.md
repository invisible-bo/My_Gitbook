# Meta

### Meta tag

* meta tag는 **웹 문서의 정보 (meta data)**&#xB97C; 알려주기 위해 작성하는 tag
* 작성된 meta data는 사용자에겐 보이지 않지만\
  web browser, 검색엔진, meta data를 활용하는 web service들이 사용하게 됨
* :fire:**\<head> tag 내에 위치**하고 **empty tag형식**으로 사용

meta = "초월한", "상위 개념의", "자기 자신을 가리키는"

```html
<meta charset="UTF-8">  <!-- 문자 인코딩 -->
<meta name="description" content="이 페이지는 웹 개발 튜토리얼입니다.">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

* `<meta>` tag는 페이지 정보를 포함하지만 **브라우저에 직접 표시되지는 않음**



viewport

* web 문서가 그려지는 영역(viewport)에 대해 크기나 확대 비율 조정
* content 속성에 viewport 설정 값을 넣을 수 있다.

```html
<meta name="viewport" content ="width"=device-width, initial-scale=1.0">
```

* width: 웹문서 표현되는 영역의 너비. device-width = mobile기기 너비
* initial-scale: 처음 화면에 보여질 때의 배율. 1.0 = 기본 2.0 = 2배
* 그 외 user-scalable, maximum-scale, minimum-scale 등 <-mobile



author, description, keyword

* 검색엔진이나 외부 web service에 알려질 정보들을 표현

<div align="left"><figure><img src="../../../../../.gitbook/assets/image (73).png" alt="" width="563"><figcaption></figcaption></figure></div>





