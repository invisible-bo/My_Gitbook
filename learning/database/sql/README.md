---
icon: s
description: Structured Query Language
---

# SQL

### SQL(Structured Query Language)

* Database와 대화하기 위해 디자인된 언어

SQL의 열(Column)과 행(Row)

1. #### **열(Column)**:
   * **설명**:
     * 테이블의 **세로 방향** 데이터를 의미
     * 각 열은 테이블의 속성을 나타내며, **필드(field)** 라고도 불림
     * 열에는 특정 데이터 유형(예: 문자열, 정수, 날짜 등)이 지정
     * 예를 들어, `이름`, `나이`, `직업` 같은 속성이 열에 해당
   * **특징**:
     * 열 이름은 테이블 생성 시 지정하며, 데이터베이스에서 각 열은 고유한 이름을 가
     * 데이터 유형(예: `VARCHAR`, `INT`)을 기반으로 열에 저장할 데이터 형식이 제한

ex)

```
이름    나이    직업
----    ----    ----


이름, 나이, 직업은 각각 열을 나타냄
```

2. **행(Row)**:

* **설명**:
  * 테이블의 **가로 방향** 데이터를 의미
  * 각 행은 **레코드(record)** 라고도 불리며, 특정 개체 또는 항목의 데이터를 저장
  * 예를 들어, 한 사람의 이름, 나이, 직업 정보를 하나의 행으로 표현
* **특징**:
  * 행은 테이블의 열에 해당하는 속성 값을 포함하여 하나의 완전한 데이터를 구성
  * 테이블에는 여러 행이 존재하며, 각 행은 고유 식별자(예: 기본 키)를 가질 수 있음

ex)

```
이름      나이    직업
----      ----    ----
김철수     25      학생
박영희     30      개발자


김철수 | 25 | 학생과 박영희 | 30 | 개발자는 각각 하나의 행
```

***

#### **행과 열의 관계**:

* **테이블**은 열과 행의 조합으로 구성
* 열은 데이터의 **속성**을 정의하고, 행은 데이터의 **인스턴스**를 나타냄
* 모든 행은 동일한 열 구조를 공유하지만, 열 값은 각 행마다 다를 수 있음



SQL에서 \*\*행(row)\*\*과 \*\*열(column)\*\*은 데이터베이스 테이블의 구성 요소로, 데이터를 구조화하고 관리하기 위해 사용됩니다.

#### 1. **열(Column)**:

* **설명**:
  * 테이블의 **세로 방향** 데이터를 의미합니다.
  * 각 열은 테이블의 속성을 나타내며, \*\*필드(field)\*\*라고도 불립니다.
  * 열에는 특정 데이터 유형(예: 문자열, 정수, 날짜 등)이 지정됩니다.
  * 예를 들어, `이름`, `나이`, `직업` 같은 속성이 열에 해당합니다.
* **특징**:
  * 열 이름은 테이블 생성 시 지정하며, 데이터베이스에서 각 열은 고유한 이름을 가집니다.
  * 데이터 유형(예: `VARCHAR`, `INT`)을 기반으로 열에 저장할 데이터 형식이 제한됩니다.
*   **예시**:

    ```plaintext
    이름    나이    직업
    ----    ----    ----
    ```

    위 예시에서 `이름`, `나이`, `직업`은 각각 열을 나타냅니다.

***

#### 2. **행(Row)**:

* **설명**:
  * 테이블의 **가로 방향** 데이터를 의미합니다.
  * 각 행은 \*\*레코드(record)\*\*라고도 불리며, 특정 개체 또는 항목의 데이터를 저장합니다.
  * 예를 들어, 한 사람의 이름, 나이, 직업 정보를 하나의 행으로 표현합니다.
* **특징**:
  * 행은 테이블의 열에 해당하는 속성 값을 포함하여 하나의 완전한 데이터를 구성합니다.
  * 테이블에는 여러 행이 존재하며, 각 행은 고유 식별자(예: 기본 키)를 가질 수 있습니다.
*   **예시**:

    ```plaintext
    이름      나이    직업
    ----      ----    ----
    김철수     25      학생
    박영희     30      개발자
    ```

    위에서 `김철수 | 25 | 학생`과 `박영희 | 30 | 개발자`는 각각 하나의 행입니다.

***

#### **행과 열의 관계**:

* **테이블**은 열과 행의 조합으로 구성됩니다.
* 열은 데이터의 **속성**을 정의하고, 행은 데이터의 **인스턴스**를 나타냅니다.
* 모든 행은 동일한 열 구조를 공유하지만, 열 값은 각 행마다 다를 수 있습니다.

***

#### **SQL에서 행과 열의 작업**:

* **열 작업**:
  * 새로운 열 추가: `ALTER TABLE ADD COLUMN`
  * 특정 열 선택: `SELECT column_name`
  * 열 삭제: `ALTER TABLE DROP COLUMN`
* **행 작업**:
  * 새로운 행 추가: `INSERT INTO`
  * 특정 행 조회: `SELECT * FROM table WHERE 조건`
  * 행 삭제: `DELETE FROM table WHERE 조건`

