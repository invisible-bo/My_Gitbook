---
icon: vr-cardboard
---

# Package & Virtual Environment

### Virtual Environment



in Python

```bash
# Creating Virtual Environment
python -m venv {name}

# Activate Virtual Environment # Windows
source {name}/Scripts/activate

# Activate Virtual Environment # MacOS
source {name}/bin/activate


deactivate
```

in Conda

```bash
# Creating Virtual Environment
conda create --name {name}

# Activate Virtual Environment
conda activate {name}

# deactivate Virtual Environment
conda deactivate
```

***

### Package

* 여러 module들을 묶어 놓은 하나의 directory
* ex) pandas, numpy, Django, pytorch etc...



`PIP` : Python package 관리

```bash
pip install {package name}
pip install {package name}=={version number}

# pip 목록과 version 확인
pip list
```

{% hint style="info" %}
패키지 설치 목록을 저장하고 나중에 동일한 환경을 복원

가상환경에서 사용 중인 패키지들을 `requirements.txt` 파일로 추출

* pip freeze > requirements.txt

이 파일을 다른 개발자나 서버에 배포하고, 같은 환경을 만들려면

* pip install -r requirements.txt
{% endhint %}

