---
description: DRF를 사용해서 JSON을 응답하는 API를 설계하고 구현
---

# Django REST Framework

```bash
pip install djangorestframework
```

<div align="left"><figure><img src="../../.gitbook/assets/image (37).png" alt="" width="175"><figcaption><p>setting.py apps 등록</p></figcaption></figure></div>

<div align="left"><figure><img src="../../.gitbook/assets/image (38).png" alt="" width="350"><figcaption><p>app의 urls.py path등록</p></figcaption></figure></div>

<div align="left"><figure><img src="../../.gitbook/assets/image (39).png" alt="" width="96"><figcaption><p>app마다 serializers.py 생성</p></figcaption></figure></div>

<div align="left"><figure><img src="../../.gitbook/assets/image (40).png" alt="" width="303"><figcaption></figcaption></figure></div>

<div align="left"><figure><img src="../../.gitbook/assets/image (43).png" alt="" width="281"><figcaption></figcaption></figure></div>

<div align="left"><figure><img src="../../.gitbook/assets/image (44).png" alt="" width="563"><figcaption></figcaption></figure></div>

***

{% hint style="info" %}
**Django REST Framework (DRF)**

* Django를 이용해서 API를 구축하는 기능을 제공하는 라이브러리
* Django의 Form, ModelForm과 굉장히 비슷하게 구성 및 작동
{% endhint %}

### Postman

* API를 제공하는 서버를 개발하고 나면 해당 API를 Call 할 수 있는 무언가가 필요
  * API를 호출하고 결과도 보고
  * Postman webpage 가입 및 설치([https://www.postman.com/](https://www.postman.com/))
* Postman:
  * 개발자가 API를 디자인, 테스트, 문서화, 공유를 할 수 있도록 도와주는 software
  * API 테스트, 환경관리, 협업 등을 위한 강력한 기능 제공, \
    보다 효율적으로 API를 개발하고 test할 수 있게 도와줌



