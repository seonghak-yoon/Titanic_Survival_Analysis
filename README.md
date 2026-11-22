# Titanic Survival Analysis & Prediction

### Python 기반 타이타닉 승객 생존 요인 분석 및 머신러닝 예측

## 1. Project Overview

본 프로젝트는 타이타닉 승객 1,309명의 데이터를 활용하여 생존 여부와 관련된 주요 요인을 탐색하고, 머신러닝 모델을 구축하여 생존 여부를 예측한 개인 데이터 분석 프로젝트입니다.

Python을 활용하여 데이터 탐색, 전처리, 시각화, 머신러닝 모델 구축, 교차검증 및 성능 평가까지 데이터 분석의 전체 과정을 수행했습니다.

## 2. Tech Stack

- **Language:** Python
- **Data Analysis:** Pandas, NumPy
- **Visualization:** Matplotlib, Seaborn
- **Machine Learning:** Scikit-learn
- **Environment:** Anaconda, Jupyter Notebook
- **Version Control:** Git, GitHub

## 3. Analysis Process

### 3.1 Exploratory Data Analysis (EDA)

- 전체 승객 생존율 분석
- 성별 및 객실 등급별 생존율 비교
- 성별과 객실 등급의 교차 분석
- 연령대별 생존 패턴 분석
- 가족 규모에 따른 생존율 분석

### 3.2 Data Preprocessing

- 결측치 탐색 및 처리
- 범주형 변수 인코딩
- 가족 규모 파생변수 생성
- 훈련 및 테스트 데이터 분할
- Scikit-learn Pipeline을 활용한 전처리 및 모델 학습

### 3.3 Machine Learning

- Dummy Classifier를 기준 모델로 설정
- Decision Tree Classifier 구축
- 5-Fold Stratified Cross Validation 수행
- max_depth 조정을 통한 하이퍼파라미터 튜닝
- Feature Importance를 활용한 주요 예측 변수 분석

## 4. Model Performance

| Metric | Dummy Classifier | Decision Tree |
|---|---:|---:|
| Accuracy | 61.83% | **83.59%** |
| Precision | 0.00% | **81.32%** |
| Recall | 0.00% | **74.00%** |
| F1-score | 0.00% | **77.49%** |

- **Accuracy Improvement:** +21.76 percentage points
- **5-Fold CV Mean Accuracy:** 80.51%
- **Selected max_depth:** 3
