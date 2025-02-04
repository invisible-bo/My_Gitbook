---
description: HyperText Transfer Protocol
---

# HTTP & URL

HTTP(HyperText Transfer Protocol)

* web에서 이루어지는 데이터 교환의 기초(약속)
* 요청(request)
  * client -> server로 전송되는 메세지
* 응답(response)
  * server -> client로 전송되는 메세지

### HTTP의 주요 특징

* **클라이언트-서버 구조**
  * 클라이언트(브라우저)가 서버에 요청(request)을 보내면, 서버는 응답(response)을 보낸다.
  * 예를 들면, 사용자가 `https://example.com`을 입력하면 브라우저가 그 주소를 가진 서버에 요청을 보내고, 서버는 HTML, CSS, JavaScript 파일 같은 걸 보내준다.
* **비연결성(Connectionless)**
  * 요청을 보내고 응답을 받으면 연결이 끝난다. 새로운 요청을 보내면 새로운 연결이 만들어진다.
  * 즉, 한 번 요청-응답이 끝나면 서버는 클라이언트를 기억하지 않는다.
* **무상태성(Stateless)**
  * 서버가 클라이언트의 이전 요청 상태를 기억하지 않는다.
  * 예를 들어, 로그인 정보를 계속 유지하려면 `쿠키(Cookie)`나 `세션(Session)`을 사용해야 한다.

***

#### **HTTP 메서드**

* `GET` : 데이터를 요청할 때 사용. (예: 웹페이지를 로딩할 때)
* `POST` : 데이터를 서버로 보낼 때 사용. (예: 로그인 정보 전송)
* `PUT` : 데이터를 업데이트할 때 사용.
* `DELETE` : 데이터를 삭제할 때 사용.
* `PATCH` : 데이터를 부분적으로 업데이트할 때 사용.

***

#### **HTTP Status Code(상태 코드)**

서버가 응답할 때, 상태 코드로 요청 결과를 알려준다.

* `200 OK` : 정상 처리됨.
* `301 Moved Permanently` : 해당 URL이 다른 곳으로 영구 이동함.
* `404 Not Found` : 요청한 페이지를 찾을 수 없음.
* `500 Internal Server Error` : 서버 내부 오류.

***

### URL

* Web에서의 자원의 식별
  * 우리가 어떤 요청을 하는 대상을 Resource(자원)라함
    * 문서, 사진, 영상 ...
  * 이러한 리소스를 식별하기 위해 URI(Uniform Resource Identifier)를 사용
* URI
  * 통합자원 식별자
  * 인터넷의 리소스를 식별할 수 있는 유일한 문자열
  * 하위개념 - URN, **URL**
    * 일반적으로 URL을 사용하는 비중이 낮아서 **URI와 URL을 같은 의미로 사용하기도 함**

| 구분    | URL                        | URI                   |
| ----- | -------------------------- | --------------------- |
| 의미    | 리소스의 "위치"를 지정하는 주소         | 리소스를 "식별"하는 모든 방법     |
| 포함 여부 | URL ⊆ URI                  | URI ⊇ URL             |
| 예시    | `https://example.com/page` | `urn:isbn:0451450523` |

**결론:** URL은 URI의 하위 개념이고, URI는 더 넓은 의미에서 리소스를 식별하는 개념

***

### URI의 구조

```
https://www.aidenlim.dev:80/path/to/resource/?key=value#docs
```

* https://
  * **Scheme(Protocol)**
    * 브라우저가 사용하는 프로토콜
    * http, https, ftp, file, …
* `www.aidenlim.dev`
  * **Host(Domain name)**
    * 요청을 처리하는 웹 서버
    * IP 주소를 바로 사용할 수 있지만 도메인 이름을 받아서 사용하는 것이 일반적
* `:80`
  * **Port**
    * 리소스에 접근할 때 사용되는 일종의 문(게이트)
    * HTTP: 80 / HTTPS: 443이 표준 포트
* `/path/to/resource/`
  * **Path**
    * 웹 서버에서의 리소스 경로
    * 웹 초기에는 실제 물리적인 위치를 나타냈으나 현재는 추상화된 형태를 표현
* `?key=value`
  * **Query(Identifier)**
    * 웹 서버에 제공하는 추가적인 변수
    * `&`로 구분되는 Key=Value 형태의 데이터
* `#docs`
  * **Fragment(Anchor)**
    * 해당 자원 안에서의 특정 위치 (북마크)를 나타냄
    * HTML 문서의 특정 부분을 보여주기 위한 방법

***

