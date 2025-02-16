---
icon: file-lines
---

# Documents

### System/Software Architecture(SA) 문서

*   시스템의 전체 구조, 구성 요소, 데이터 흐름, 모듈 간 관계를 한눈에 보여주는 문서

    * 프로젝트의 **"기술적 설계도"** 같은 것

    &#x20;

**SA 문서에 꼭 들어가야 하는 핵심 요소:**

1. **프로젝트 개요(Project Overview)**
   * 프로젝트 목적, 목표, 주요 기능.
   * 기술 스택(백엔드, 프론트엔드, DB, 클라우드, API 등).
2. **아키텍처 다이어그램(Architecture Diagram)**
   * **전체 시스템 구성도** (Client, Server, DB, 3rd-party API 등)
   * **데이터 흐름(Flow)** (요청 → 처리 → 응답 과정)
   * **마이크로서비스 구조도(필요 시)**
3. **모듈 및 컴포넌트 설계(Module/Component Design)**
   * 주요 모듈, 각 모듈의 역할 및 인터페이스.
   * 예: **User 서비스**, **Post 서비스**, **Auth 서비스(JWT)** 등.
4. **데이터베이스 설계(Database Design)**
   * ERD(Entity Relationship Diagram)
   * 주요 테이블, 관계 및 주요 컬럼 설명.
5. **API 설계(API Design)**
   * API 엔드포인트 명세 (RESTful or GraphQL)
   * 요청/응답 형식(JSON 스키마)
6. **보안(Security) 및 인증(Authentication)**
   * JWT, OAuth2, CORS 정책
   * HTTPS 및 데이터 암호화 방식
7. **비기능 요구사항(Non-functional Requirements)**
   * 성능(Performance)
   * 확장성(Scalability)
   * 가용성(Availability)
   * 장애 복구(Backup & Recovery)
8. **시스템 통합 및 외부 연동(Integration)**
   * 외부 API 호출 구조
   * 메시지 큐(RabbitMQ, Kafka 등) 사용 여부

#### **작업 순서(추천 프로세스):**

1. **요구사항 분석** →
2. **SA 문서 작성 (아키텍처, ERD, API 스펙 포함)** →
3. **팀원들과 리뷰 및 피드백** →
4. **POC(Proof of Concept) 또는 MVP 테스트** →
5. **개발 착수**

***

### Architecture

