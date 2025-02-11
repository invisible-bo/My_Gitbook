# Template

### Templates System

* 데이터를 보여주는 로직 작성
* Template 기본 경로
  * `app_name / templates / app_name`&#x20;

### 앱 내부 구조의 권장 규칙

```
app_name/
├── templates/
│   └── app_name/
│       └── index.html
```

* **앱 간의 템플릿 이름 충돌**을 방지하기 위해서
  * `views.py`에서 `app_name/index.html`로 위치를 명시해주어야 함

```python
from django.shortcuts import render

def index(request):
    return render(request, 'articles/index.html')
```

***

### Django Template Language(DTL)

* Django template에서 사용하는 문법
  * (주의) **PYTHON이 동작하는 것이 아님!!**
* 데이터를 표현하기 위한 방법
* DTL문법



1. **변수, Variable**

```python
{{ variable }}
```

* **view의 context**로 넘긴 데이터를 변수로로 접근할 수 있음
* 변수에 어떠한 작업을 추가적으로 더해 수정하고 싶을 때 사용
* `.` 을 사용하여 변수의 속성 값에 접근 가능
*   `**render()` 의 세 번째 인자인 **context**에 \*\*`dictionary` 형태로 넘겨진 데이터 중

    `**key` 값이 template에서 사용 가능한 변수가 됨

    * **render(request, template, context)**

    \


<div align="left"><figure><img src="../../../.gitbook/assets/image (61).png" alt="" width="341"><figcaption><p>context</p></figcaption></figure></div>

<div align="left"><figure><img src="../../../.gitbook/assets/image (62).png" alt="" width="221"><figcaption><p>.으로 속성값에 접근</p></figcaption></figure></div>

2. **필터 (Filters)**

```python
{{ variable|filter }}
```

* 변수에 작업을 추가적으로 더해 수정하고 싶을 때 사용
* 약 60개의 built-in template filter가 제공되며 일부 필터는 인자를 받기도 함
* 필터 사용 예시
  * view에서 넘겨준 데이터를  소문자로 보이게 하고 싶다면

```python
{{ first_name|lower }}
```



3. **태그 (Tags)**

```python
{% raw %}
{% tag %}
{% endraw %}
```

* 반복 또는 논리를 수행하여 제어 흐름을 만들거나 특수한 기능을 수행
* 일부는 시작 태그와 종료 태그가 있음

```python
{% raw %}
{% if ~ %}
{% endif %}
{% endraw %}
```

* 주석 (Comments)

```python
{# 한 줄 주석 #}

{% raw %}
{% comment %}
 여러줄
 주석
{% endcomment %}
{% endraw %}
```



<figure><img src="../../../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

***

### Template Inheritance(템플릿  상속)

* Django는 템플릿 상속을 지원
* 코드의 재사용성, 상위 템플릿에 공통이 될 부분을 정의하고\
  하위 템플릿에서 달라질 부분을 Block으로 만드는 Skeleton형태

`{% block block_name %}`&#x20;

`{% endblock block_name %}`&#x20;

* 상위 템플릿에서 하위 템플릿 마다 달라질 부분을 정의



`{% extends 'template_name' %}`&#x20;

* 하위 템플릿에서 상위 템플릿을 상속해서 확장한다는 것&#x20;
* 템플릿의 가장 최상단에 위치해야함
* 다중 상속을 지원하지 않음

<figure><img src="../../../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>

* 상위템플릿에 base.html을 옮겼을때

<figure><img src="../../../.gitbook/assets/image (36).png" alt="" width="563"><figcaption></figcaption></figure>











