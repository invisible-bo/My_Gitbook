---
description: API를 프론트엔드 개발자들이 사용하기 위한 문서화
---

# API Documentation

* Django REST Framework에서의 문서화
  * `drf-spectacular`와 `drf-yasg`를 추천
    * 둘 모두 코드를 기반으로 API Doc을 만들고, 이 문서를 사용자가 보기 편하게 UI로 변환하는 도구(Swagger-UI / Redoc)를 포함하고 있음
    * 둘의 가장 큰차이는 `drf-yasg` 는 OpenAPI 2 기반으로 만들어졌고 `drf-spectacular` 는 OpenAPI 3을 기반으로 한다는 것

```bash
pip install drf-spectacular
```

```python
INSTALLED_APPS = [
    ...
    'drf_spectacular',
]
# setting.py apps 등록
```

```python
REST_FRAMEWORK = {
    ...
    'DEFAULT_SCHEMA_CLASS': 'drf_spectacular.openapi.AutoSchema',
}
# setting.py REST_FRAMEWORK 등록
```

```python
SPECTACULAR_SETTINGS = {
    'TITLE': 'MY Django API',
    'DESCRIPTION': 'Django DRF API Doc',
    'VERSION': '1.0.0',
    ...
}
# setting.py에 등록(없어도 동작은 한다)
```

```python
from drf_spectacular.views import SpectacularAPIView, SpectacularRedocView, SpectacularSwaggerView

urlpatterns = [
    # YOUR PATTERNS
    ...
    path('api/schema/', SpectacularAPIView.as_view(), name='schema'),
    # Optional UI:
    path('api/schema/swagger-ui/', SpectacularSwaggerView.as_view(url_name='schema'), name='swagger-ui'),
    path('api/schema/redoc/', SpectacularRedocView.as_view(url_name='schema'), name='redoc'),
]
# 프로젝트의 urls.py 등록
```

* `~/api/schema/swagger-ui/` 로 접근









