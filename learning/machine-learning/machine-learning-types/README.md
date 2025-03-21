# Machine learning types

### 1.  지도 학습(Supervised learning)

* 입력 데이터(feature)와 출력 데이터(label)이 함께 제공
* 모델이 주어진 입력과 출력 간의  관계를  학습하여 새로운 데이터를 예측

1. 회귀(Regression):\
   \- 연속적인 값을 예측\
   \- ex) 주택 가격 예측, 주식 시장 예측\
   \- 알고리즘 ex) 선형 회귀, 다항 회귀, Lasso, Ridge
2. 분류(Classification)\
   \- 데이터가 미리 정의된 여러 카테고리 중 하나로 분류됨\
   \- ex) 스팸 메일 분류, 암 진단\
   \- 알고리즘 ex) 로지스틱 회귀, 의사결정 트리(Decision tree), 랜덤 포레스트, SVM, Naive Bayes

***

### 2. 비지도 학습(Unsupervised learning)

* 출력 데이터(label)이 없는 상태에서 입력 데이터의 패턴이나 구조를 학습
* 데이터 간의 군집화, 차원 축소 등의 작업에 사용

1. 군집화(Clustering)\
   \-  비슷한 특성을 가진 데이터를 그룹으로 나눈다\
   \- ex) 고객 세분화, 문서 분류\
   \- 알고리즘 ex) K-평균(K-means), 계층적 군집화, DBSCAN
2. 차원 축소(Dimensionality Reduction)\
   \- 고차원의 데이터를 저차원으로 변환하여 중요한 정보만 남김\
   \- ex) 데이터 시각화, 노이즈 제거\
   \- 알고리즘 ex) PCA(주 성분 분석), t-SNE, UMAP.

***

### 3. 강화 학습(Reinforcement Learning)

* **에이전트**\[환경(Environment)과 상호작용 하며 최적의 행동을 **학습하는 주체**]가\
  환경과 상호작용 하며 최적의 행동을 학습한다
* 특정 행동에 대한 **보상(Reward)**&#xC744; 극대화하는 방향으로 학습한다

&#x20;주요 개념:

* **상태(State):** 에이전트가 현재 처한 상황
* **행동(Action):** 에이전트가 선택할 수 있는 행동
* **보상(Reward):** 특정 행동을 취했을 때 받는 피드백

#### 알고리즘 ex)&#x20;

* Q-Learning
* SARSA
* 딥 Q-네트워크(DQN)
* 정책 기반 학습(Policy Gradient)

응용 사례

* 게임 AI(Alphago)
* 자율 주행 자동차
* 로봇 제어

***

### 4. 앙상블 학습(Ensemble Learning)

* 여러 모델을 조합하여 단일 모델 보다 더 강력한 성능을 내는 학습 기법
* 각 모델의 강점을 결합하고 약점을 상호 보완하여 과적합(overfitting)을 줄이고 \
  일반화 성능을 향상 시킴

#### 유형&#x20;

* 배깅(Bagging)\
  여러 모델을 독립적으로 학습 시키고, 예측을 평균 내거나 다수결 투표로 최종 예측

***

### 5. 딥 러닝(Deep Learning)

* 인공신경망(Artificial Neural Networks)을 사용하여 데이터를 분석하고 학습하는 기술\

* 1\.  다층 구조(Deep Neural Networks)\
  \- 여러 층(layer)의 신경망으로 이루어져 있음. 입력층(Input Layer), 숨겨진 층(Hidden Layers), \
  출력층 (Output Layer)으로 구성되며, 숨겨진 층이 많을수록 "딥(deep)"하다고 표현\

* 2\. 특징 추출 자동화\
  \- 머신러닝은 보통 사람이 데이터를 전처리하고 중요한 특징(Feature)을 추출해야 하지만, \
  딥러닝은 데이터를 입력하면 중요한 특징을 자동으로 추출해 학습\

* 3\. 대량의 데이터 활용\
  \- 딥러닝은 많은 양의 데이터를 사용하여 높은 성능을 발휘. \
  특히, 이미지, 음성, 텍스트 같은 비정형 데이터를 처리하는 데 탁월합니다.\

* 4\. GPU 활용\
  \- 딥러닝은 대규모 행렬 연산을 수행하기 때문에 GPU(그래픽 처리 장치)를 활용해 계산 속도를 \
  크게 높임

ex) 인공신경망 (ANN), 합성곱신경망 (CNN), 순환신경망 (RNN)



