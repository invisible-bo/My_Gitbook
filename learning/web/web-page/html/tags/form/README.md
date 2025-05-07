---
description: form tag
---

# Form

### Form tag&#x20;

* user에게 data를 입력 받기 위한 화면 구성
* \<form>\</form> 사이에 관련 태그들을 넣어 하나의 폼 구성
  * form : form의 시작 끝 정의
  * input, select : user입력을 받는 입력 상자나 버튼 만드는 tag
  * label : 입력 상자 마다 제목을 붙이는 tag
  * button : button tag

<div align="left"><figure><img src="../../../../../../.gitbook/assets/image (3) (1) (1) (1).png" alt="" width="563"><figcaption><p>있음 없음 부분 radio</p></figcaption></figure></div>

주요 속성

* :fire:action : data를 전송할 url 주소
* method : data를 전송할 방법(주로get 과 post)
* enctype : data를 전송할 때 전송 인코딩 형식을 지정

***

### input tag

* void element: 홀태그&#x20;
* type: 입력 형태. text, password, button, submit, radio, checkbox etc
* name: 입력값의 name
* value: 입력상자의 값

| 태그                      | 기본 동작                           | 스타일(Customization)       | 내용 삽입 가능 여부          | 주요 사용처                                    |
| ----------------------- | ------------------------------- | ------------------------ | -------------------- | ----------------------------------------- |
| `<button>`              | 기본적으로 아무 기능 없음 (type 속성에 따라 다름) | CSS 적용 쉽고 자유롭게 스타일링 가능   | 가능 (텍스트, 아이콘, 이미지 등) | 다양한 기능 버튼 (일반 버튼, 폼 제출, JavaScript 이벤트 등) |
| `<input type="submit">` | 폼 제출 기능 기본 내장                   | CSS 커스텀 제한적 (텍스트만 변경 가능) | 불가능 (텍스트만 설정 가능)     | 폼 전송 버튼                                   |

1. `<button>` 태그 (더 유연한 버튼)

```html
<button type="submit">전송</button>
<button type="button" onclick="alert('버튼 클릭!')">클릭</button>
<button type="reset">초기화</button>
```

* **기본적으로 아무 기능 없음** → `type` 속성을 지정해야 함 (`button`, `submit`, `reset` 등)
* **텍스트, 아이콘, 이미지 넣기 가능** → `<button><img src="icon.png"/> 클릭</button>`
* **JavaScript 이벤트 처리 가능** → `onclick` 이벤트 등 활용 가능
* **스타일링이 쉬움** → CSS로 자유롭게 디자인 가능

2. `<input type="submit">` 태그 (폼 제출 버튼)

```html
<form action="submit_page.html">
    <input type="submit" value="전송">
</form>
```

* **기본적으로 폼을 제출하는 버튼** (따로 기능 안 줘도 `submit` 기능 가짐)
* **스타일링이 제한적** → `value` 속성으로 텍스트만 변경 가능
* **내부에 이미지나 아이콘 넣기 불가능** → 오로지 텍스트 버튼

✅ **폼 제출 버튼만 필요하면?** → `<input type="submit">`\
✅ **아이콘, 이미지, 다양한 스타일링이 필요하면?** → `<button>`\
✅ **JavaScript 이벤트 (클릭 등)를 추가할 거면?** → `<button type="button">`

***

radio - 여러 개 중에서 하나만 선택

checkbox - 중첩 선택 가능&#x20;

***

* text, password

<div align="left"><figure><img src="../../../../../../.gitbook/assets/image (66).png" alt="" width="375"><figcaption></figcaption></figure></div>

* button, submit

<div align="left"><figure><img src="../../../../../../.gitbook/assets/image (67).png" alt="" width="375"><figcaption></figcaption></figure></div>

* radio, check box

<div align="left"><figure><img src="../../../../../../.gitbook/assets/image (68).png" alt="" width="563"><figcaption></figcaption></figure></div>

* select

<div align="left"><figure><img src="../../../../../../.gitbook/assets/image (69).png" alt="" width="563"><figcaption></figcaption></figure></div>

* textarea
* 두 줄 이상의 긴 글을 입력받도록 해주는 입력 칸
* **textarea 내부의 컨텐츠는 줄바꿈을 인식함**

<div align="left"><figure><img src="../../../../../../.gitbook/assets/image (70).png" alt="" width="563"><figcaption></figcaption></figure></div>

* label
* user에게 각 입력 칸을 설명해주는 label을 표시
* input 태그에 id 속성으로 지정된 값을 for 속성으로 넣어주면 그 input 태그를 수식

<div align="left"><figure><img src="../../../../../../.gitbook/assets/image (71).png" alt="" width="563"><figcaption></figcaption></figure></div>

* fieldset, legend
* 여러 입력 태그를 하나의 그룹으로 묶고 원하는 제목으로 grouping&#x20;

<div align="left"><figure><img src="../../../../../../.gitbook/assets/image (72).png" alt="" width="563"><figcaption></figcaption></figure></div>





