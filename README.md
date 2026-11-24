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
- **CV Standard Deviation:** 1.44%p
- **Selected max_depth:** 3

## 5. Key Findings

**성별에 따른 생존율 차이**

여성 생존율은 약 72.7%, 남성 생존율은 약 19.1%로 나타났습니다. 의사결정나무 모델에서도 성별이 가장 중요한 예측 변수로 활용되었습니다.

**객실 등급에 따른 생존 패턴**

객실 등급별 생존율에 차이가 나타났으며, 객실 등급은 모델에서 두 번째로 높은 변수 중요도를 기록했습니다.

**가족 규모에 따른 생존 패턴**

혼자 탑승한 승객의 생존율은 30.25%, 가족 동반 승객의 생존율은 50.29%로 나타났습니다.

**모델 복잡도와 예측 성능**

의사결정나무의 최대 깊이를 1~10으로 변경하여 교차검증한 결과, max_depth=3에서 가장 높은 평균 정확도를 기록했습니다.

## 6. Limitations & Future Improvements

- 단일 데이터셋을 활용한 분석으로 외부 데이터에 대한 일반화 성능은 검증하지 못했습니다.
- 결측치 대체 과정에서 일부 정보 손실이 발생할 수 있습니다.
- Feature Importance는 예측에 대한 상대적 기여도를 나타내며 인과관계를 의미하지 않습니다.
- 향후 Logistic Regression, Random Forest 등 다양한 모델과의 비교를 통해 성능 개선을 시도할 수 있습니다.

## 7. Project Files

- `Titanic_Survival_Analysis.ipynb`: 전체 분석 코드, 시각화 및 머신러닝 결과
- `README.md`: 프로젝트 소개 및 주요 성과
- `.gitignore`: Git 추적 제외 파일 설정

## 8. Dataset

본 프로젝트는 Titanic3 데이터셋(1,309명)을 사용했습니다.

분석에 사용한 `titanic.xlsx` 파일은 교수자가 제공한 자료로, 재배포 권한이 확인되지 않아 공개 저장소에 포함하지 않았습니다.

원본 데이터가 필요한 경우 별도로 적법하게 이용 가능한 데이터 출처를 확인해야 합니다.

## 9. Conclusion

본 프로젝트를 통해 데이터 탐색부터 전처리, 머신러닝 모델 구축, 교차검증, 성능 평가 및 결과 해석까지 전 과정을 수행했습니다.

최종 Decision Tree 모델은 테스트 정확도 83.59%를 기록했으며, 기준 모델 대비 21.76%p 높은 성능을 보였습니다.

이를 통해 데이터 분석 결과를 정량적으로 검증하고, 모델의 성능뿐 아니라 한계와 개선 방향을 함께 고려하는 경험을 쌓았습니다.

## Kaggle Titanic 대회 실험

기존 엑셀 기반 타이타닉 생존 분석을 확장해, Kaggle 대회 데이터로 모델을 학습하고 예측 결과를 총 6회 제출했다.

| 제출 | 모델 | 입력 변수 및 전처리 | Kaggle 점수 |
|---|---|---|---:|
| 1 | 로지스틱 회귀 | 객실 등급, 성별 | 0.76555 |
| 2 | 로지스틱 회귀 | 객실 등급, 성별, 나이(전체 중앙값으로 보완) | 0.75598 |
| 3 | 로지스틱 회귀 | 객실 등급, 성별, 나이(호칭별 중앙값으로 보완) | **0.77033** |
| 4 | 로지스틱 회귀 | 3번 입력에 가족 규모 추가 | 0.75358 |
| 5 | Random Forest | 3번과 동일한 입력 | 0.72966 |
| 6 | 로지스틱 회귀 | 3번 입력에 운임, SibSp, Parch 추가 | 0.76315 |

최고 Kaggle 정확도는 **77.03% (0.77033)**였다. 나이 결측값을 호칭별 중앙값으로 채운 모델은 전체 중앙값을 사용한 모델보다 정확도가 약 1.44%p 높았다. 호칭별 값을 사용할 수 없는 경우 학습 데이터 전체의 나이 중앙값을 적용했다.

여섯 변수 모델은 내부 검증에서 81.01%로 세 변수 모델의 77.65%를 앞섰지만, Kaggle에서는 세 변수 모델이 더 높은 점수를 기록했다.

대회 데이터는 [Kaggle Titanic 공식 데이터 페이지](https://www.kaggle.com/competitions/titanic/data)에서 내려받을 수 있다.
