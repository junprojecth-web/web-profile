---
title: "MDLprj - 기후 적응형 작물 추천"
category: ["머신러닝", "추천 시스템", "개인 프로젝트"]
role: ""
period: "기간 미기재"
videoUrl: ""
demoUrl: "https://aiplant-w3fwxydelqxs3gzegjwdms.streamlit.app/"
githubUrl: "https://github.com/junprojecth-web/LMProject"
summary: "국내 지역별 기후와 작물 생육조건을 분석해 재배 적합성과 수익성을 고려한 작물을 추천하는 머신러닝 프로젝트"
highlights:
  - "98개 국내 관측 지점의 기후와 100종 작물의 생육조건을 결합해 9,800건의 분석 데이터 구성"
  - "Random Forest, Gradient Boosting 등 분류 모델을 비교하고 GridSearchCV로 모델 최적화"
  - "재배 적합 작물을 선별한 뒤 수익성 기준 상위 작물과 기후·생육조건 비교 정보를 제공"
techStack:
  - "Python"
  - "Pandas"
  - "NumPy"
  - "scikit-learn"
  - "Random Forest"
  - "XGBoost"
  - "LightGBM"
  - "Streamlit"
  - "Matplotlib"
  - "Seaborn"
tags: ["machine-learning", "crop-recommendation", "climate", "Streamlit"]
---

## 프로젝트 개요

지역 기후와 작물별 생육조건을 머신러닝으로 분석해 국내 재배 적합성을 예측하고, 재배가 가능한 작물 중 수익성이 높은 작물을 추천하는 서비스입니다.

수익성만으로 작물을 고르는 대신 **지역에서 재배할 수 있는지 먼저 판단한 뒤 경제성을 비교**하는 단계적 추천을 목표로 합니다.

## 데이터 및 모델

- 국내 98개 관측 지점의 최근 10년 기후 데이터와 열대·과수 100종의 생육조건 데이터를 결합해 총 9,800건을 구성했습니다.
- 재배 적합 사례가 6.7%인 클래스 불균형을 고려해 `class_weight='balanced'`를 적용하고, Accuracy 외에 Precision, Recall, F1-score, ROC-AUC를 함께 평가했습니다.
- Logistic Regression, Decision Tree, Random Forest, Gradient Boosting을 비교했습니다. 초기 비교에서 Random Forest가 F1-score 0.9887을 기록했습니다.
- GridSearchCV를 이용해 Random Forest를 튜닝하고, XGBoost와 LightGBM을 포함한 Hybrid Stacking 및 Stratified 5-Fold 검증도 진행했습니다.

## 주요 기능

- 지역, 재배 면적, 예상 투자금을 바탕으로 재배 가능 작물을 탐색합니다.
- 재배 적합성이 확인된 작물을 수익성 점수로 정렬해 추천합니다.
- 지역 기후와 작물 생육조건을 비교하는 시각화와 모델 평가 정보를 제공합니다.
- 최저기온과 작물의 한계생육온도 등 주요 특성의 중요도를 확인할 수 있습니다.

## 사용 기술

Python 기반 데이터 분석과 scikit-learn, XGBoost, LightGBM 모델링을 적용했으며, Streamlit으로 추천 결과와 시각화를 제공하도록 구성했습니다.

## 한계 및 고려사항

현재 분석은 과거 10년 기후 데이터를 사용하므로 미래 기후변화에 따른 재배 가능성을 직접 예측하지 않습니다. 수익성과 시장성 점수도 전문가 평가 기반이므로 실제 비용과 순수익을 그대로 나타내지는 않습니다.
