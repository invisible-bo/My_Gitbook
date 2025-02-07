---
description: DRF를 사용하여 단일 Model의 CRUD구현
---

# DRF Single Model CRUD

### DRF SingleModel

* **1.단일 model에서 데이터를 조회**해서/2.**직렬화(Serialization)**&#xD558;여/3.**JSON으로 응답**하기
* ModelSerializer
  * Model의 여러가지 필드들을 어떻게 직렬화해서 데이터의 포맷을 잡을지가 핵심
  * Django의 Model -> ModelForm 사용과 굉장히 유사한 형태

***

### API 설계

<div align="left"><figure><img src="../../../.gitbook/assets/image (3).png" alt="" width="420"><figcaption></figcaption></figure></div>

<div align="left"><figure><img src="../../../.gitbook/assets/image (1) (1) (1).png" alt="" width="441"><figcaption><p>urls.py 작성 이후 views 작성</p></figcaption></figure></div>

<div align="left"><figure><img src="../../../.gitbook/assets/image (2) (1).png" alt="" width="410"><figcaption><p>views.py</p></figcaption></figure></div>

\


{% hint style="info" %}
`@api_view()`&#x20;

* 아무것도 적지 않으면 **GET 만 허용**, 이외의 요청일 경우 = `405 Method Not Allowed`
* :fire:**DRF의 함수형 view의 경우 필수적**으로 작성이 필요
* articles/serializers.py
{% endhint %}

***

<div align="left"><figure><img src="../../../.gitbook/assets/image (45).png" alt="" width="486"><figcaption></figcaption></figure></div>

<div align="left"><figure><img src="../../../.gitbook/assets/image (46).png" alt="" width="341"><figcaption><p>API로 작성시에는 app_name, name 생략 가능</p></figcaption></figure></div>

<div align="left"><figure><img src="../../../.gitbook/assets/image (47).png" alt="" width="365"><figcaption><p>views.py</p></figcaption></figure></div>

:fire:**1.단일 model에서 데이터를 조회**해서/2.**직렬화(Serialization)**&#xD558;여/3.**JSON으로 응답**하기

***

### Article 생성 (Create)

* `title` 과 `content` data를 받아야 함
* JSON으로 주고받기(Form도 가능)

<div align="left"><figure><img src="../../../.gitbook/assets/image (48).png" alt="" width="437"><figcaption></figcaption></figure></div>

***

### Article 삭제 (Delete)

<div align="left"><figure><img src="../../../.gitbook/assets/image (49).png" alt="" width="439"><figcaption></figcaption></figure></div>

***

### Article 수정 (Update)

<div align="left"><figure><img src="../../../.gitbook/assets/image (50).png" alt="" width="563"><figcaption><p>partial : 특정부분만도 수정할 수 있게</p></figcaption></figure></div>



