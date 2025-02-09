---
description: Deploy(배포)
---

# Django Deploy with AWS

### Cloud computing

* 물리적 server를 가상화 시켜서 internet service 로 제공하는 것

**1) 서비스 모델 기준 (무슨 서비스를 제공하느냐)**

* **IaaS (Infrastructure as a Service)**
  * 서버, 네트워크, 스토리지 같은 **하드웨어 인프라** 제공.
  * 직접 OS 깔고, 필요한 설정까지 해야 함.
  * 모두 설정을 해줘야하므로 마음대로 커스텀 할 수 있음 (장점이자 단점)
  * **예)** **Amazon Web Service**, Microsoft Azure, Google Compute Engine
* **PaaS (Platform as a Service)**
  * 애플리케이션을 개발할 수 있는 **환경(플랫폼)** 제공.
  * OS, 미들웨어, 데이터베이스, 런타임 환경까지 세팅돼 있음.
  * 인프라에 대한 관리 없이 개발에 집중하여 빠른 속도로 개발할 수 있음
  * **예)** AWS Elastic Beanstalk, Google App Engine, Heroku
* **SaaS (Software as a Service)**
  * 그냥 완성된 **소프트웨어**를 웹에서 바로 사용
  * 유저는 걍 가입하고 사용하면 끝
  * 모든 서비스를 맡기고 비지니스에 집중할 수 있음
  * **예)** Gmail, Google Drive, Dropbox, Zoom

***

### AWS



sign up

* [AWS](https://aws.amazon.com/ko/)

1. AWS EC2 인스턴스 생성

* Ubuntu 선택
* 인스턴스 유형 t2.micro
* 키 페어(로그인)
  * 새 키 페어 생성(생성 후 보관)
* 인스턴스 시작



2. 인스턴스 접속

* macOS
  * 터미널을 이용해서 접속 가능
  * 다운로드 받아둔 `.pem` 파일을 사용해서 접속
  * `ssh -i [키 페어 파일] [유저 이름]@[퍼블릭 DNS 주소]`

<div align="left"><figure><img src="../../.gitbook/assets/image (6).png" alt="" width="369"><figcaption></figcaption></figure></div>

* windows
  * 윈도우는 CMD로 바로 SSH에 접근할 수 없고 외부 프로그램을 이용해야함
    * 이전에는 PuTTY라는 툴을 많이 이용했으나 더 기능이 많고 사용성이 좋은 모바엑스텀(MobaXTerm)으로 진행
* [MobaXTerm](https://mobaxterm.mobatek.net/)

<div align="left"><figure><img src="../../.gitbook/assets/image (1) (1) (1) (1).png" alt="" width="375"><figcaption></figcaption></figure></div>

* Remote host : AWS의 퍼블릭 DNS 입력

<div align="left"><figure><img src="../../.gitbook/assets/image (2) (1).png" alt="" width="373"><figcaption></figcaption></figure></div>

* Specify username 체크 후 `ubuntu` 입력
* Advanced SSH settings 선택후 이전에 생성했던 `.pem` 파일 선택

<div align="left"><figure><img src="../../.gitbook/assets/image (3) (1).png" alt="" width="563"><figcaption></figcaption></figure></div>

<div align="left"><figure><img src="../../.gitbook/assets/image (4) (1).png" alt="" width="563"><figcaption><p>AWS에서 임대한 EC2 인스턴스에 접속했다</p></figcaption></figure></div>







