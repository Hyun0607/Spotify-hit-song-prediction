# 🎵 Spotify 오디오 특성 기반 인기곡 예측 프로젝트

> Spotify가 Kaggle을 통해 제공한 곡별 오디오 특성과 인기점수 데이터를 활용하여, 다양한 음악적 척도만으로 인기 여부를 예측하는 머신러닝 분석 프로젝트

---

## 📌 프로젝트 개요

본 프로젝트는 **다양한 음악적 척도(오디오 특성)** 만으로 곡의 인기도를 예측할 수 있는지 분석하는 것을 목표로 진행되었습니다.  
이는 신곡을 제작하는 음악 산업 종사자들이 인기곡의 특징을 사전에 파악하는 데 도움을 줄 수 있습니다.  
여러 인기 척도 변수가 존재하나, 본 프로젝트에서는 **Kaggle에서 제공한 Spotify 오디오 특성 데이터셋**만을 활용했습니다.

데이터는 곡별 **popularity(0~100)** 점수와 10여 개의 오디오 특성(danceability, energy, loudness, tempo, valence 등)을 포함하며,  
popularity 60점 이상을 ‘인기곡(1)’, 미만을 ‘비인기곡(0)’으로 구분하여 이진 분류 문제로 설정했습니다.

---

### 👥 팀원별 역할 분담

| 이름 (구분) | 주요 역할 |
|-------------|-----------|
| 🧑‍💻 정현우<br>(팀장) | 프로젝트 총괄, 모델링(Random Forest, XGBoost, SVM) 및 성능 비교 |
| 👩‍💻 조하영 | 데이터 수집, 결측치 처리 및 로그 변환, 스케일링 등 전처리 |
| 👩‍💻 김혜원 | 데이터 탐색적 분석(EDA), 시각화(변수 분포, 상관관계 히트맵 등) |
| 👨‍💻 심민기 | 관련 논문·기사 조사, 발표 자료 제작 |

---

## 🧠 분석 구조

1. **데이터 로드**  
   - Kaggle에서 제공한 Spotify 오디오 특성 데이터 불러오기  
   - 불필요한 컬럼 제거 (`track_id`, `artists`, `album_name`, 등)  

2. **탐색적 데이터 분석(EDA)**  
   - 인기/비인기곡 비율 확인  
   - 변수 분포 시각화(KDEPlot)  
   - 오디오 특성 간 상관관계 히트맵  

3. **데이터 전처리**  
   - 로그 변환(`duration_ms`, `speechiness`, `acousticness`, `liveness`)  
   - 스케일링(StandardScaler)  
   - 다중공선성 검증(VIF)  

4. **모델 학습 및 평가**
   - Logistic Regression
   - Random Forest
   - XGBoost
   - SVM
   - AUC 및 F1-score 비교

5. **변수 중요도 분석**
   - Random Forest Feature Importance
   - XGBoost Feature Importance
   - SHAP Summary Plot을 통한 영향 방향 분석

---

## ⚙️ 분석 흐름 요약

데이터 로드  
↓  
EDA (분포 확인, 상관관계 분석)  
↓  
전처리 (컬럼 제거, 로그 변환, 스케일링, VIF)  
↓  
모델 학습 (Logistic, RF, XGB, SVM)  
↓  
성능 비교 (AUC, F1-score, Confusion Matrix)  
↓  
변수 중요도 분석 (Feature Importance, SHAP)


## 🧩 프로젝트 전체 기술 스택

| 영역 | 도구 |
|------|------|
| 데이터 처리 | pandas, numpy |
| 시각화 | matplotlib, seaborn |
| 모델링 | scikit-learn(Logistic, RF, SVM), XGBoost |
| 모델 해석 | SHAP |
| 개발 환경 | Google Colab |


---

## 🧩 프로젝트 전체 기술 스택

| 영역 | 도구 |
|------|------|
| 데이터 처리 | pandas, numpy |
| 시각화 | matplotlib, seaborn |
| 모델링 | scikit-learn(Logistic, RF, SVM), XGBoost |
| 모델 해석 | SHAP |
| 개발 환경 | Google Colab |

---

## 🔍 평가 지표

- **Confusion Matrix**
- **AUC (Area Under the Curve)**
- **F1-score**

| 모델 | AUC | F1-score |
|------|-----|----------|
| Logistic Regression | 예: 0.xx | 예: 0.xx |
| Random Forest | 예: 0.xx | 예: 0.xx |
| XGBoost | 예: 0.xx | 예: 0.xx |
| SVM | 예: 0.xx | 예: 0.xx |

---

## 🧪 분석 결과

- **중요 변수**: Loudness, Energy, Danceability 등이 인기곡 예측에 높은 기여
- **시각화**:
  - Confusion Matrix (모델별)
  - ROC Curve
  - Feature Importance Barplot
  - SHAP Summary Plot

✅ *다양한 음악적 특성만으로도 인기곡 예측이 가능함을 확인*  
✅ *특히 음량(Loudness)과 에너지(Energy) 특성이 예측에 크게 기여함*

