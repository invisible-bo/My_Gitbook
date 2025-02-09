---
description: <form> tag action 속성
---

# action

### action

* HTML `<form>` 태그에서 사용되는 속성으로, "입력한 데이터를 어디로 보낼지" 결정하는 역할
* 폼을 제출(submit)했을 때 데이터를 전송할 URL을 지정

```html
<form action="submit.php" method="post">
    <label for="name">이름:</label>
    <input type="text" id="name" name="name">
    <button type="submit">제출</button>
</form>
```

| action 값                              | 설명                             |
| ------------------------------------- | ------------------------------ |
| `action="submit.php"`                 | 데이터를 `submit.php`로 전송          |
| `action="/process-form"`              | 현재 도메인의 `/process-form` 경로로 전송 |
| `action="https://example.com/submit"` | 외부 서버(도메인)로 데이터 전송             |
| `action=""`                           | 현재 페이지로 데이터 전송                 |
| `action="#"`                          | 데이터를 전송하지 않고, 페이지를 새로고침        |



### action + method



:fire:`action`은 **"데이터를 어디로 보낼지"**, `method`는 **"어떻게 보낼지"\`를 결정**

```html
<form action="/submit-form" method="post">
    <input type="text" name="username">
    <button type="submit">Submit</button>
</form>
```

* `method="get"` → **URL 뒤에 데이터가 붙어서 전송됨** (`/submit-form?username=Bo`)
* `method="post"` → **URL에 보이지 않고, 요청 본문(body)으로 데이터가 전송됨**

