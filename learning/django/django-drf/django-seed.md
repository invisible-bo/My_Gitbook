# Django Seed

### Django Seed

* Django에서 **Seed**는 데이터베이스에 **초기 데이터를 채우는 작업**을 의미.&#x20;
* 개발 중에 **더미 데이터**나 **기본 설정 데이터**를 삽입하는 과정

사용하는 이유

1. **개발 및 테스트 편의성**

* 모델을 만들고 난 뒤, 기본적인 데이터가 있어야 테스트할 수 있음
* 예를 들어, User 모델을 만들었으면 몇 개의 유저가 있어야 로그인 테스트를 할 수 있다

2. **데이터 일관성 유지**

* 초기 설정 데이터를 매번 수동으로 입력할 필요 없이 자동으로 생성할 수 있다
* 예를 들어, `Category` 모델에 "Technology", "Science", "Health" 같은 기본 카테고리를 추가할 때 사용

3. **배포 시 기본 데이터 제공**

* 실제 서비스 배포 전에, 필수적인 데이터(예: 관리자 계정, 기본 설정 값)를 미리 채워둘 수 있음

***

**`django-seed` 라이브러리** 사용:

* 이 라이브러리는 Faker를 활용해서 더미 데이터를 쉽게 생성해줌

```bash
pip install django-seed
# django-seed 설치시 faker도 같이설치됨
```

{% hint style="info" %}
Faker : 프로그래밍 언어에서 **가짜 데이터(fake data)** 를 생성하는 데 사용되는 \
&#x20;            오픈소스 라이브러리. \
&#x20;            이름, 주소, 전화번호, 이메일, 날짜, 텍스트 등 다양한 데이터를 랜덤으로 생성할 수 있다.\
&#x20;            주로 **테스트 데이터 생성**이나 **데모 데이터 준비**를 위해 활용



#### **Faker의 주요 특징**

1. **다양한 데이터 타입 지원**: 이름, 주소, 전화번호, 회사명, 이메일, 날짜 등등 \
   다양한 유형의 데이터를 제공.
2. **다국어 지원**: 여러 국가와 언어의 형식에 맞는 데이터를 생성할 수 있음.
   * 예: 한국어, 영어, 일본어 등
3. **확장성**: 기본 제공 데이터 외에도 커스텀 데이터를 생성하도록 확장 가능.
4. **빠르고 간단함**: 코드 몇 줄로 원하는 데이터를 쉽게 만들 수 있음.
{% endhint %}

```
설치 후 setting.py apps에 django_seed 등록
```

seeding

```bash
python manage.py seed {app name} --number={number}
```

에러가 뜰 때

```bash
pip install psycopg2
```

***

* `JsonResponse`
  * JSON으로 인코딩된 response를 만드는 `HttpResponse`의 서브 클래스
  *   `safe`

      → dict 타입이 아닌 객체를 직렬화(Serialization)하기 위해서는 `False`로 설정해야함

<div align="left"><figure><img src="../../../.gitbook/assets/image (5) (1) (1) (1).png" alt=""><figcaption></figcaption></figure></div>

{% hint style="info" %}
**Serialization란?**

직렬화(Serialization)

*   객체 또는 데이터 구조를 저장, 전송을 위해 다른 포맷으로 변경하는 것

    → **데이터의 구조는 유지하면서 추후 재구성이 가능한 포맷으로 변환**

    * **객체(Object)**&#xB97C; JSON, XML, YAML 같은 데이터 형식으로 **변환**하는 것
    * Django도 내부적으로 다른 데이터 포맷으로 쉽게 직렬화 할 수 있는 기능을 제공



Serialization이 **필요한 이유**

Django 같은 웹 프레임워크에서 API를 만들 때,&#x20;

**Python 객체를 JSON으로 변환해서 클라이언트(프론트엔드, 모바일 앱 등)와 통신해야한다**
{% endhint %}

### Serializers 사용법

1. QuerySet을 JSON으로 변환

ex)

```python
from django.core import serializers
from articles.models import Article

articles = Article.objects.all()  # 모든 Article 데이터 가져오기
json_data = serializers.serialize("json", articles)  # JSON 형식으로 변환

print(json_data)  # JSON 데이터 출력
```

출력예시

```python
[
    {
        "model": "articles.article",
        "pk": 1,
        "fields": {
            "title": "Hello Django",
            "content": "This is a sample article.",
            "created_at": "2024-02-01T12:00:00Z",
            "updated_at": "2024-02-01T12:00:00Z"
        }
    }
]
```

* Django의 `serializers.serialize()`는 기본적으로 **QuerySet만 직렬화할 수 있음**
* Django는 위와같이 내부적으로 serializer를 제공하지만 모델 구조에 한정된 구조
  * 직렬화된 데이터의 구조를 변경하거나 새로운 필드를 구성하는 것에 많은 추가 작업이 필요
  * 유연한 API를 위한 기능이라기보다 모델 구조로 저장되어있는 데이터를 export 하는 용도에 가깝다
* **모델에 종속적이지 않고 유연하지만 사용하기 편한 Serializer의 필요성**





