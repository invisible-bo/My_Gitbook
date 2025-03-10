# RESTful API & JSON

### RESTful API

API(Aplication Programming Interface)

* **API : 어플리케이션과 프로그래밍적으로 소통하는 방법**
  * CLI(Command Line Interface) : 명령줄로 소통하는 방법
  * GUI(Graphic User Interface) : 그래픽으로 유저와 소통하는 방법
* 요청, 응답까지 전체적인 것을 포함한 구조
* 소프트웨어 <-> 소프트웨어간 API를 이용해서 서로 소통
* 이러한 소통에는 서로 약속된 형식이 필요 == API
  * ex)google로 로그인 kakao로 로그인 etc

***

RESTful API(REST 같이쓰는(ful) API)

1. REST(Representational State Transfer)

* 웹에 대한 소프트웨어 설계 방법론
* **API를 만들기 위한 개념이 아님**. 그래서 RESTful API라고 우리가 사용하는 것

{% hint style="info" %}
REST의미

하나의 웹 페이지를 **하나의 상태(State)**&#xB85C; 본다면 유저가 링크를 입력하는 것은 \
**상태 전이(State Transfer)**&#xAC00; 일어나는 것이며

이때 유저가 받는 하나의 상태는 **특정한 표현(Representational)**&#xC5D0; 의해 조작된다는 개념
{% endhint %}

2. RESTful API

* 어플리케이션간 소통하는 방법에 REST적인 표현을 더한 것
  * REST원리를 따라 설계한 API
  * RESTful API로 작성하면 결과를 보지 않고 요청 형식만 보더라도 추론이 가능&#x20;
* 핵심 규칙
  * 자원 : **URI로 표현**
  * 행위 : **HTTP Method로 표현**
  * 표현
    * 자원과 행위를 통해 표현되는 결과물로 일반적으로 **JSON 형식**을 사용
    *   URI는 동사가 아닌 명사의 나열로 사용

        → `POST` `/articles/create/` (X)

        → `POST` `/articles/` (O)
* 따르지 않더라도 로직과 동작에는 아무런 이상이 없으나, 이 규칙을 따를 때 얻는 이득이 크다
* 일반적으로 `GET` `POST` `PUT` `DELETE` + `PATCH`를 사용
  * GET : 조회
  * POST : 생성
  * PUT : 전체 수정
  * DELETE : 삭제
  * PATCH : 일부 수정

***

### JSON(JavaScript Object Notation)

* 데이터를 저장하고 전송할 때 사용하는 **가볍고, 읽기 쉬운 데이터 형식**. 원래 JavaScript에서 유래했지만, 지금은 거의 모든 프로그래밍 언어에서 사용
* JS 표기법을 따른 일종의 데이터를 담는 형식
* **JavaScript 객체와 비슷한 구조**지만, 프로그래밍 언어에 독립적
* 사람이 읽기 쉽고 프로그래밍으로 파싱(분석)하기 쉬움
* **키-값(key-value) 쌍**으로 데이터를 저장
* **데이터 교환에 최적화됨** → API 통신, 데이터 저장 등에 자주쓰임

***

### JSON 기본문법

* `.json` 형식으로 사용
* 문자는 `"`으로 묶여야하며 `true` `false` (소문자 주의), 숫자 등을 사용가능

```json
["리스트", 1, true, "다양한 자료를 담을 수 있어요"] // list
{ key: value } // object
```

ex)

```json
{
	"user1": {
			"name": "aiden",
			"age": 22,
			"tags": ["python", "javascript", "django"]
	},
	"user2": {
			...
	},
	...
}
```

***



