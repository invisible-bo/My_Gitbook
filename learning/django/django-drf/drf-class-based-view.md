# DRF Class Based View

* Django의 View 형태
  * 함수형 뷰 (Function Based View,FBV)
  * 클래스형 뷰 (Class Based View, CBV)



* CBV 특징
  * **클래스 상속을 활용한 코드 재사용성 증가**
    * Django의 CBV는 **`View` 클래스를 상속받아** 필요한 기능을 구현한다.
      * 공통된 로직을 부모 클래스로 만들고, 여러 뷰에서 재사용할 수 있다.
  * **내장된 Generic View 제공**
    * Django는 `ListView`, `DetailView`, `CreateView`, `UpdateView`, `DeleteView` 같은 **기본적인 CRUD를 처리하는 클래스형 뷰를 제공**한다.
    * 개발자는 최소한의 코드만 작성해도 CRUD 기능을 쉽게 구현할 수 있다
  * **뷰 로직을 메서드 단위로 나눠서 처리**
    * FBV는 `request.method`로 분기 처리를 하지만, CBV는 `get()`, `post()` 같은 메서드 오버라이딩을 통해 HTTP 요청을 세분화할 수 있다
* :fire:기본 `APIView` 외에도 여러 편의를 제공하는 다양한 내장 CBV 존재

{% hint style="info" %}
#### Class Based View 종류

* `APIView` - **DRF CBV의 베이스 클래스**
* `GenericAPIView`
  * 일반적인 **API 작성을 위한 기능이 포함된 클래스**
  * 보통 CRUD 기능이 대부분인 상황을 위해 여러가지 기능이 미리 내장되어 있습니다.
* `Mixin`
  * 재사용 가능한 여러가지 기능을 담고있는 클래스
  * 말그대로 여러 클래스를 섞어서 사용하기 위한 클래스
    * `ListModelMixin` - 리스트 반환 API를 만들기 위해 상속 받는 클래스
    * `CreateModelMixin` - 새로운 객체를 생성하는 API를 만들기위해 상속 받는 클래스
* `ViewSets`
  * 여러 엔드포인트(endpoint)를 한 번에 관리할 수 있는 클래스
  * RESTful API에서 반복되는 구조를 더 편리하게 작성할 수 있는 방법을 제공합니다.
{% endhint %}

***

* APIView 사용

<div align="left"><figure><img src="../../../.gitbook/assets/image (51).png" alt="" width="308"><figcaption></figcaption></figure></div>

{% hint style="info" %}
block 후 전체 주석처리 = ctrl + /
{% endhint %}

<div align="left"><figure><img src="../../../.gitbook/assets/image (52).png" alt="" width="563"><figcaption></figcaption></figure></div>

<div align="left"><figure><img src="../../../.gitbook/assets/image (54).png" alt="" width="555"><figcaption></figcaption></figure></div>

* FBV를 CBV로 변경

<div align="left"><figure><img src="../../../.gitbook/assets/image (55).png" alt="" width="559"><figcaption><p>urls.py</p></figcaption></figure></div>

* CBV를 사용할 때는 참조하는 형식이 변경
*   `as_view()`메서드를 사용해서 URL 패턴에 연결

    → 클래스 자체를 넘기는 것이 아니라 `as_view()`메서드를 사용해서 호출 가능한 함수로 변환!















