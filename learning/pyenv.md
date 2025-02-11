---
icon: python
---

# Pyenv

### pyenv로 Python version 관리



1. Python install

<pre class="language-bash"><code class="lang-bash"><strong>pyenv install 3.10.6  # 원하는 버전
</strong>pyenv install --list # 설치 가능 버전 목록
</code></pre>

2. install version 확인

```python
pyenv versions
```

3. 특정 version 사용(global)

```bash
pyenv global 3.10.6
```

4. 정상 동작 확인

```bash
python --version 
```

5. 특정 프로젝트에서만 python version 사용(local)

```python
cd /c/project/my_project  # 프로젝트 폴더로 이동
pyenv local 3.8.12        # 다른 폴더로 가면 global 설정된 Python이 적용
```

6. 일시적으로 Python 버전 변경 (shell)

```bash
pyenv shell 3.12.1 # 이 터미널 세션에서만 3.12.1을 사용한다
                   # 터미널을 닫거나 새로 열면 원래 설정으로 돌아감
```









