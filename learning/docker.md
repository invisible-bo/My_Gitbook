---
icon: docker
---

# Docker

### Docker

* Docker를 사용하면 애플리케이션을 실행하기 위해 필요한 모든 파일과 환경 설정을 하나의 패키지로 묶어 이식성과 재현성을 높일 수 있음
* 개발 환경을 재현(복제)하는 기술

:fire:장점

* 가벼움: 컨테이너는 기본적으로 애플리케이션과 필수 구성 요소만 포함하므로 \
  &#x20;              가상 머신보다 훨씬 가벼움
* 이식성: 개발 환경과 운영 환경이 동일하게 유지되므로 환경 차이에 의한 문제를 최소화
* 빠른 배포: 애플리케이션과 관련된 모든 것을 패키징하므로 배포 시간이 단축

***

### Docker 구성요소

* Dockerfile: Dockerfile 도커 image의 설정 파일. 컨테이너 실행에 필요한 애플리케이션, \
  &#x20;                    라이브러리, 의존성 등을 정의
* 이미지(Image): 애플리케이션 실행에 필요한 모든 것을 포함한 읽기 전용 템플릿\
  &#x20;                             Dockerfile로 정의되며, 컨테이너의 기반
* 컨테이너(Container): 이미지를 실행 가능한 상태로 만든 것. \
  컨테이너는 애플리케이션이 실제로 실행되는 환경 &#x20;

***

### Dockerfile 기본 구조

```docker
# 베이스 이미지 설정
FROM python:3.8-slim

# 필수 패키지 설치
RUN apt-get update && apt-get install -y --no-install-recommends \
    gcc \
    build-essential \
    libffi-dev \
    libssl-dev \
    zlib1g-dev \
    python3-dev \
    && rm -rf /var/lib/apt/lists/*

# 컨테이너 내부 작업 디렉토리 설정
WORKDIR /myapp

# 의존성 파일 복사
COPY requirements.txt /myapp/
RUN pip install --upgrade pip setuptools wheel
# 의존성 설치
RUN pip install --no-cache-dir -r requirements.txt

# 애플리케이션 코드 복사
COPY myapp /myapp

# 애플리케이션(서버) 실행
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
```

***

### Image build

* image build

```shell
docker build -t [이미지 이름]:[태그] [Dockerfile 경로]
# ex)
docker build -t qhrms111/book_app:v1.0.0 .
```

* image 확인

```shell
# 생성된 이미지 확인
docker images
# ex)
REPOSITORY          TAG       IMAGE ID       CREATED          SIZE
qhrms111/book_app   v1.0.0    1dd181fe2fa3   35 seconds ago   807MB
book_app            latest    8f2b241a7367   10 hours ago     807MB
```

* image 삭제

```shell
docker rmi [이미지 이름 또는 ID]
```





***

### Container

* container 실행

```shell
docker run [옵션] [이미지 이름]:[태그]
# ex)
docker run myapp:1.0
```

* container 실행(port mapping)

```shell
docker run -d -p 8000:8000 myapp:1.0
# -d 옵션 백그라운드실행
```

* 실행중인 container 확인

```shell
docker ps
```

* container 중지, 재실행

```shell
docker stop [컨테이너 이름 또는 ID]
docker start [컨테이너 이름 또는 ID]
```

* container 삭제

```shell
docker rm [컨테이너 이름 또는 ID]
```



***

<div align="left"><figure><img src="../.gitbook/assets/image (1).png" alt="" width="563"><figcaption><p>오류발생</p></figcaption></figure></div>

<div align="left"><figure><img src="../.gitbook/assets/image (1) (1).png" alt="" width="563"><figcaption><p>image 생성</p></figcaption></figure></div>

***

### Push to Docker Hub

* login

```shell
docker login
```

* image tag settings

```shell
docker tag [이미지 이름]:[태그] [도커 허브 사용자 이름]/[이미지 이름]:[태그]
# ex)
docker tag book_app qhrms111/book_app
```

* image push

```shell
docker push [도커 허브 사용자 이름]/[이미지 이름]:[태그]
# ex)
docker push qhrms111/book_app:v1.0.0
```

* code 수정 후 version number를  달리 한 뒤 push

***

* `.dockerignore` &#x20;
  * ex)

```
# Python
venv/
__pycache__/
*.pyc
*.pyo
*.pyd

# Git
.git/
.gitignore

# OS & IDE
.DS_Store
Thumbs.db
.vscode/
.idea/

# Docker
.dockerignore
Dockerfile~

# Logs & Build
logs/
*.log
*.out
*.err

# Django
db.sqlite3
staticfiles/
media/
**/migrations/*
!**/migrations/__init__.py
```

* 빌드 속도 향상
* 보안
* 이크기 감소

| 파일              | 역할                            | 적용 대상               |
| --------------- | ----------------------------- | ------------------- |
| `.gitignore`    | Git 저장소에 추적되지 않을 파일을 지정       | Git (커밋, 푸시할 때 적용)  |
| `.dockerignore` | Docker 빌드 시 컨텍스트에서 제외할 파일을 지정 | `docker build` 컨텍스트 |

### .gitignore & .dockerignore

1. Git에 올리지는 않지만, Docker 빌드에는 필요한 파일이 있을 수 있음
   * 예: `Dockerfile`은 `.gitignore`에서 제외할 이유가 없지만, `.dockerignore`에서는 필요할 수도 있음.
2. **Docker 빌드 시 불필요한 파일을 제외해야 속도가 빨라짐**
   * 예: `.git` 폴더는 Git에는 있어야 하지만, Docker 이미지에는 포함할 필요가 없음.
3. **Git과 Docker가 다루는 파일의 범위가 다름**
   * `.gitignore`: 개발 중 불필요한 파일이나 캐시를 커밋에서 제외 (예: `__pycache__/`)
   * `.dockerignore`: Docker 빌드 시 컨테이너에 포함되지 않아야 하는 파일 제외 (예: `venv/`)

***

### Docker Compose



<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

* 복잡한 어플리케이션 관리
  * 어플리케이션이 **여러 서비스**로 구성된 경우
    * ex) django, PostgreSQL
* 의존성 관리
  * 각 서비스 간 **의존성** 설정해야 하는 경우
    * ex)Django가 PostgreSQL 데이터베이스에 연결



핵심개념

* `docker-compose.yml` 파일
  * YAML 형식으로 작성되며, 여러 컨테이너의 설정(이미지, 네트워크, 볼륨 등)을 정의
* 서비스 (Services)
  * 컨테이너의 논리적 단위
    * ex) `web`서비스는 Django 애플리케이션, `db`서비스는 PostgreSQL 데이터베이스
* 네트워크 (Networks)
  * Docker Compose는 자동으로 각 서비스 간의 통신을 위한 네트워크를 생성
    * ex) `web`서비스에서 `db`서비스를 이름으로 호출 가능
* Docker Volumes
* **Docker Volumes는** **컨테이너 내부 데이터가 영구적으로 유지되도록 저장하는 방식**
  * 컨테이너는 기본적으로 휘발성
  * `docker run`으로 실행한 컨테이너는 삭제되면 내부 데이터도 사라짐
  * 하지만 데이터베이스 같은 서비스는 컨테이너가 사라져도 데이터가 유지되어야 함
* 호스트와 컨테이너 간 데이터 공유
  * 컨테이너 내부 데이터를 **호스트(로컬 시스템)에도 저장**할 수 있음
    * 이를 통해 개발 환경에서 데이터를 유지하면서 컨테이너를 여러 번 재시작 가능
* 여러 컨테이너 간 데이터 공유
  * 같은 볼륨을 여러 개의 컨테이너가 접근할 수 있음
  * 예를 들어, Nginx 컨테이너와 Django 컨테이너가 같은 정적 파일을 공유할 수 있음



* `docker-compose.yml`&#x20;

```yaml
version: '3.8' # Docker Compose 파일의 형식 버전 (최신 버전)

services:       # 여러 컨테이너 서비스를 정의하는 섹션
  web:          # Django 애플리케이션 서비스 정의
    build:  # 이미지 관련된 설정
      context: .  # Dockerfile이 위치한 디렉토리 (현재 디렉토리)
    ports:
      - "8000:8000"  # 호스트와 컨테이너의 포트를 매핑 (로컬 8000 → 컨테이너 8000)
    volumes:
      - ./myapp:/myapp  # 로컬의 myproject 디렉토리를 컨테이너의 /myapp과 동기화
    environment:           # Django 환경 변수 설정
      - DJANGO_SETTINGS_MODULE=myapp.settings
      - DATABASE_URL=postgres://postgres:password@db:5432/postgres
      # 주소 주석 추가       # id:postgress password:password
    depends_on:
      - db  # db 서비스가 시작된 후 실행

  db:           # PostgreSQL 서비스 정의
    image: postgres:13  # PostgreSQL 공식 이미지 사용 (버전 13)
    volumes:
      - db_data:/var/lib/postgresql/data  # PostgreSQL 데이터를 영구적으로 저장
    environment:             # PostgreSQL 초기 사용자, 비밀번호, 데이터베이스 설정
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: password
      POSTGRES_DB: postgres

volumes:
  db_data:       # PostgreSQL 데이터 저장소를 위한 Docker Volume 정의
		 # 컨테이너 간 데이터 공유 또는 컨테이너가 삭제되어도 데이터 유지
```

* database local 설치

1. database 설치
2. database를 사용할 user 생성 (id, password)
3. database 생성
4. table 생성

***

### docker compose 실행

```shell
docker compose up
```







