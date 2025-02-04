---
description: >-
  DRF(Django REST Framework)는 Django 기반의 RESTful API를 쉽게 개발할 수 있도록 지원하는 강력하고 유연한
  라이브러리
icon: user-bounty-hunter
---

# Django DRF

## Django DRF

기존의 Django

* Django는 Web App을 빠르게 개발하기 위한 고수준의 web framework
* 기존에는 Web의 전체 기능이 모두 들어있는 Web Application을 제작
* MTV를 활용한 Web
* 데이터 모델링, URL 라우팅, 템플릿 시스템, 관리자 기능, 세션, 보안

여기서의 Django

* 보여지는 부분은 처리하지 않고 오직 **로직에 집중**하는 형태
  * 요청에 대해 처리한 결과 데이터를 응답하는 형태
* **Django REST Framework (DRF)**&#xB97C; 이용하는 방법
* DRF == 흔히 말하는 RESTful API를 Django로 구축하기 위한 확장 Framework
* **Django**는 주로 HTML, CSS, JavaScript로 구성된 웹 페이지를 반환하는 반면, \
  **DRF**는 **JSON** 형식으로 데이터를 주고받는 **RESTful API**를 생성하는 데 사용

***

### DRF의 핵심요소

1. Serializer (직렬화)

* 데이터를 JSON으로 변환하고, JSON 데이터를 모델로 변환하는 역할

```python
from rest_framework import serializers
from .models import Post

class PostSerializer(serializers.ModelSerializer):
    class Meta:
        model = Post
        fields = '__all__'  # 모든 필드를 JSON으로 변환
```

2. Views (API 로직)

* Django의 `views.py`처럼 **데이터를 어떻게 처리할지 결정하는 곳**

```python
from rest_framework import generics
from .models import Post
from .serializers import PostSerializer

# 게시글 목록 & 생성 API
class PostListCreateView(generics.ListCreateAPIView):
    queryset = Post.objects.all()
    serializer_class = PostSerializer
```

이제 `/api/posts/`로 **GET 요청**을 보내면 모든 게시글을 가져오고,&#x20;

**POST 요청**을 보내면 새 게시글이 생성됨

3. ViewSet & Router (더 쉬운 API 관리)

* DRF의 **ViewSet**을 사용하면 **CRUD 기능을 한 번에 만들 수 있다**
* **(**&#xC5EC;러 개의 API를 하나로 묶어주는 기&#xB2A5;**)**

```python
from rest_framework import viewsets
from .models import Post
from .serializers import PostSerializer

class PostViewSet(viewsets.ModelViewSet):
    queryset = Post.objects.all()
    serializer_class = PostSerializer
```

그리고 **router**를 설정하면 URL 패턴을 자동으로 생성

```python
from rest_framework.routers import DefaultRouter
from django.urls import path, include
from .views import PostViewSet

router = DefaultRouter()
router.register(r'posts', PostViewSet)

urlpatterns = [
    path('api/', include(router.urls)),  # /api/posts/ 엔드포인트 자동 생성
]
```

* 이제 **RESTful API가 완성**\
  `/api/posts/`에서 CRUD가 한 번에 동작

***

### DRF가 제공하는 기능

1. **자동으로 API 문서 생성** (`Browsable API`)
2. 권한 관리 (Permission Classes)
3. 인증 시스템 (JWT, OAuth 지원)
4. 필터링 & 검색 (DjangoFilterBackend)
5. 페이징 처리 (Pagination)

* Django DRF는 **API 개발을 빠르고 쉽게 해주는 라이브러리.**
* **Serializer**로 데이터를 JSON으로 변환.
* **ViewSet**과 **Router**를 활용하면 CRUD API가 자동으로 생성.
* **권한, 인증, 필터링까지 지원.**
