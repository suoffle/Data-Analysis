# ML

프로젝트 기간: 2024.09. - 2024.10.

### __요약:__
﻿카드 사기로 인한 손실과 사기 탐지 시스템 운영 비용의 최소화를 위한 머신러닝 모델 개발하였다.

- 모델: XGBoost, RandomForestClassifier, LinearRegression 사용하여 가장 적절한 모델을 테스트했다.
- 주어진 데이터를 UnderSampling, OverSampling, Under+OverSampling, PCA 적용하여 각 모델에 실험하였다.

### __역할:__
- Under+OverSampling을 이용한 데이터 전처리 후, 3가지 모델에 학습 및 평가하였다.
- 데이터의 특징을 찾아 가장 우수한 성능과 비용 최소화를 고려한 모델을 구축하였다.


### __결과:__
- 데이터의 특징 발견: 한 번 사기를 당한 사용자(233명)가 다시 사기를 당하는 사용자(223)가 약 95.7%였다.
- 전처리된 데이터를 3가지 모델에 적용한 결과 가장 적절한 모델이 RandomForestClassifier라고 판단되었다.
- 따라서, 사기를 한 번 이상 경험한 사용자를 추출하여 해당 사용자의 사기 거래와 비사기 거래 데이터를 RandomForestClassifier에 학습하였다.

---
### __결론:__
### <초기 Raw 데이터 RandomForest>  
<img width="250" height="226" alt="Image" src="https://github.com/user-attachments/assets/c9f5f650-b72b-4f89-b653-fd6db11842f5" />

### <사기 거래 집중 학습 데이터 RandomForest>  
<<img width="235" height="226" alt="Image" src="https://github.com/user-attachments/assets/ce5fa241-61d3-4a18-bb7f-12709e847cd7" />

#### 1) 연산 비용와 메모리 사용 비용 감소: 전체 데이터 중 약 15.4% 데이터만을 사용하여 오탐과 미탐을 크게 줄여 모델의 성능을 향상시켰다.
#### 2) 불균형한 데이터 처리로 모델의 성능이 향상하였다.
#### 3) 사기 거래를 집중적으로 탐지하는 모델을 구현하여, 대체로 오탐(False Positive)보다 비용이 큰 미탐(False Negative)을 효과적으로 줄일 수 있었다.

<br>

※ 해당 결과는 사기 당한 사용자 데이터를 집중적으로 학습하기 때문에 특정 사용자에 종속된 패턴이 학습될 위험이 존재한다.

