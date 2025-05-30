---
description: Django 설계 철학, design pattern
---

# MTV pattern

### Design pattern

* client-server 역시 디자인 패턴 중 하나
* 자주 사용되는 소프트웨어의 구조를 일반화해둔 것
  * 특정 구조에 대한 설계를 빠르게 할 수 있음
  * 공통적으로 발생하는 문제에 대해 재사용 가능한 해결 방법을 제시할 수 있음



## Django의 Design Pattern

MVC:

* Model-View-Controller&#x20;
  * Model : 데이터 관련 로직관리
  * View :  레이아웃과 관련된 화면을 처리
  * Controller : Model과 View를 연결하는 로직을 처리
  * 분리 이유: 관심사를 분리, 각 부분 독립적 개발 생산성 증가, 유지보수 쉬워

### \*\*MTV(Django)\*\*

* **Model**
  * MVC에서의 Model
  * **데이터와 관련된 로직** 처리
    * 데이터 구조 정의, 데이터베이스 기록 관리
* **Template**
  * MVC에서의 View
  * **레이아웃**과 **화면**상의 로직을 처리
    * UI와 레이아웃
* **View**
  * MVC에서의 Controller
  * **메인 비지니스 로직**을 담당(Model과 Template의  **중간을 연결**하는 역할)

<div align="left"><figure><img src="../../../.gitbook/assets/image (56).png" alt="" width="563"><figcaption></figcaption></figure></div>

Client로부터 요청(request)이 들어오면

1. URL(urls.py) 에서 request를 받아서 어떤 view로 보낼지 처리
2. View(views.py) 에서 요청을 받아 로직에 따라 data와 관련된 읽기나 쓰기가 필요하면\
   &#x20;Model에게 요청. Model이 처리해서 view에게 돌려줌.&#x20;
3. Template(html) 처리\
   view에서 다시 받아서 Template에게 data를 줄 수도 있고, data를 안주고\
   Template에서 받아올 수도 있음. 화면과 관련된(HTML)것은 전부 Template이 처리
4. 응답(Response) 전달\
