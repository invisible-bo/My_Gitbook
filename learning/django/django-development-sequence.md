# Django development sequence

## Django 개발 순서

1. project 및 app 생성 &#x20;

```python
# 프로젝트 생성
django-admin startproject project_name
# 앱 생성
python manage.py startapp app_name
```

* 생성한 앱을 `settings.py`의 `INSTALLED_APPS`에 등록

***

2. 모델(Model) 설계

* 데이터베이스에 저장할 구조를 정의
* 예: `models.py`에서 테이블 정의

```python
from django.db import models

# Create your models here.
class MainMarket(models.Model):
    market_ID = models.CharField(max_length=300, primary_key=True)
    area = models.CharField(max_length=50)
    name = models.CharField(max_length=50)
    area_num = models.CharField(max_length=50)
    open_date = models.DateField(auto_now_add=True)
    worker_num = models.IntegerField()
```

* 모델 작성 후 마이그레이션 파일 생성

```python
python manage.py makemigrations
```

* 데이터베이스에 적용

```python
python manage.py migrate
```

* `migrate` 명령어는 **Django에서 데이터 베이스 테이블을 생성하거나 업데이트할 때 사용**된다.
* Django의 **모델을 변경**하거나 새로운 모델을 만들고 나면 **마이그레이션 파일을 생성하고 적용**해야 한다.

***

3. 관리자 사이트(Admin) 설정

* `admin.py`에 모델 등록

```python
from .models import ExampleModel

admin.site.register(ExampleModel)
```

* 관리자 계정 생성

```python
python manage.py createsuperuser
```

* 관리자 사이트를 통해 데이터를 확인하고 관리

***

4. 폼을 View에서 활용

* `views.py` 에서 폼을 처리하는 로직 추가

```python
from django.shortcuts import render, redirect
from .models import ExampleModel
from .forms import ExampleForm

def example_create(request):
    if request.method == "POST":
        form = ExampleForm(request.POST)
        if form.is_valid():
            form.save()
            return redirect('example')  # 데이터 저장 후 리디렉트
    else:
        form = ExampleForm()
    return render(request, 'example_form.html', {'form': form})
```

* 폼을 HTML 템플릿에 렌더링
  * `templates/app_name/example_form.html`에 폼을 렌더링하는 코드 작성

```python
<form method="post">
    {% raw %}
{% csrf_token %}
{% endraw %}
    {{ form.as_p }}
    <button type="submit">저장</button>
</form>
```

***

4. 뷰(View) 작성

* `views.py`에 Form을 처리하는 로직 작성
* 예: 특정 데이터를 가져오는 함수형 뷰

```python
from django.shortcuts import render
from .models import ExampleModel

def example_view(request):
    data = ExampleModel.objects.all()
    return render(request, 'example.html', {'data': data})
```

***

5. 템플릿(Template) 작성

* HTML 템플릿 작성
  * `app_name/templates/app_name/example.html`에 HTML 파일 생성
  * 템플릿에서 데이터를 표시

```python
<ul>
    {% raw %}
{% for item in data %}
    <li>{{ item.name }} - {{ item.description }}</li>
    {% endfor %}
{% endraw %}
</ul>
```

***

6. URL 설정

* 프로젝트 레벨 `urls.py`와 앱 레벨 `urls.py`에서 URL 매핑 설정
* app\_name/urls.py

```python
from django.urls import path
from . import views

urlpatterns = [
    path('example/', views.example_view, name='example'),
    path('example/create/', views.example_create, name='example_create'),  # 폼 추가
]
# / = Trailing Slash. django에서 사용 권장
```

* project\_name/urls.py

```python
from django.urls import include, path

urlpatterns = [
    path('app_name/', include('app_name.urls')),
]
```

***

7. 정적 파일 및 미디어 파일 설정

* 정적 파일 (`static/`)과 미디어 파일 (`media/`) 경로 설정
* 정적 파일 서빙 테스트

```python
python manage.py collectstatic
```

***

8. 테스트 작성

* 각 앱별로 `tests.py`에 유닛 테스트 작성
* 명령어로 테스트 실행

```python
python manage.py test
```

***

9. 배포 준비

* `DEBUG` 설정 변경, `ALLOWED_HOSTS` 지정
* WSGI 서버 사용 (예: Gunicorn, uWSGI).
* 웹 서버와 연결 (예: Nginx, Apache)





