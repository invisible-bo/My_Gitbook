---
icon: database
---

# Database

### DB(Database): Data를 저장하고 관리하는 system

* **데이터베이스(Database, DB)**&#xB780;, 데이터를 **체계적으로 저장하고, 검색하고, 수정할 수 있는** \
  **구조화된 저장소**
* 그냥 엑셀 파일처럼 데이터를 저장하는 게 아니라, **대량의 데이터를 빠르게 검색하고 안전하게 관리할 수 있도록 설계된 시스템**

**DB의 필요성**

* **데이터를 안전하게 저장**\
  → 앱이나 웹서비스가 종료돼도 데이터가 유지됨
* **대량의 데이터를 빠르게 검색**\
  → 원하는 정보를 `SELECT` 한 줄로 찾아낼 수 있음
* **여러 사람이 동시에 사용 가능**\
  → 사용자 수백\~수천 명이 한 번에 접근 가능
* **데이터 무결성(Integrity) 보장**\
  → 중복 데이터 제거, 외래키 설정으로 데이터 오류 방지
* **보안이 강력함**\
  → 인증된 사용자만 데이터에 접근 가능

***

### DBMS(Database Management System)

* **DBMS(Database Management System)**&#xB294; **데이터베이스를 관리하는 소프트웨어**
* DBMS는 데이터를 저장, 검색, 수정하는 소프트웨어고, 종류에 따라 기능이 다름



### RDBMS(관계형 Database)

*   **RDBMS(Relational Database Management System) = 관계형 데이터베이스 관리 시스템**

    데이터를 **"테이블(표)" 구조로 저장하고, SQL을 사용해서 관리하는 DBMS**

특징

* 데이터를 **행(Row)과 열(Column) 형태로 저장**
* SQL(Structured Query Language)을 사용해서 데이터 관리
* 여러 테이블을 **"관계(Relation)"로 연결**해서 사용 가능



