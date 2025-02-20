---
icon: link-horizontal
---

# Langchain

### Langchain

* LLM(대형 언어 모델)을 쉽게 활용할 수 있도록 도와주는 **Python 및 JavaScript 프레임워크**다.\
  간단히 말해, **GPT 같은 AI 모델을 더 똑똑하게 연결하고 확장하는 도구**

#### **주요 기능**

1. **프롬프트 관리**
   * LLM에 전달할 프롬프트를 템플릿화해서 쉽게 재사용 가능
2. **체인(Chains)**
   * LLM 응답을 다른 함수나 API에 연결해서 **복잡한 워크플로우**를 만들 수 있음
3. **에이전트(Agents)**
   * AI가 API, DB, 검색 엔진 등을 이용해 **자율적으로 작업 수행** 가능
4. **메모리(Memory)**
   * 이전 대화를 기억해서 **연속적인 대화 흐름** 유지 가능
5. **데이터 소스 연결**
   * 벡터 데이터베이스, 웹 검색, SQL DB 등 다양한 데이터 소스를 AI와 연결 가능



#### **LangChain으로 할 수 있는 것**

* **AI 챗봇** 만들기 (예: OpenAI + 데이터베이스 연결)
* **자동 문서 요약** (예: PDF 파일 요약)
* **질문-응답 시스템** (예: 기업 내부 문서에서 정보 검색)
* **코드 생성 및 실행** (예: AI 기반 코드 자동화)
* **LLM 기반 검색** (예: RAG, 벡터DB 활용)

ex)

```python
from langchain.chat_models import ChatOpenAI

llm = ChatOpenAI(model="gpt-4", temperature=0.7)
```







