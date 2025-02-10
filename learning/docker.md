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
docker build -t myapp:1.0 .
```

* image 확인

```shell
# 생성된 이미지 확인
docker images
# ex)
REPOSITORY          TAG       IMAGE ID       CREATED         SIZE
myapp               1.0       a1b2c3d4e5f6   5 minutes ago   123MB
python              3.10-slim d1e2f3g4h5i6   2 days ago      23MB
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









<div align="left"><figure><img src="../.gitbook/assets/image.png" alt="" width="563"><figcaption><p>오류발생</p></figcaption></figure></div>

<div align="left"><figure><img src="../.gitbook/assets/image (1).png" alt="" width="563"><figcaption><p>image 생성</p></figcaption></figure></div>

















