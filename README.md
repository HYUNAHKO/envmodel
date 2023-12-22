# envmodel
# 낙동강 Cyano 분석 머신러닝 모델

## 프로젝트 개요
이 프로젝트는 낙동강의 8개 보에서 발견되는 cyanobacteria 4종(Microcystis, Anabaena, Oscillatoria, Aphanizaomenon)과 총 질소(TN), 총 인(TP) 수치, 독성 물질(MC-LR) 간의 상관관계를 분석하는 머신러닝 모델을 구현합니다. 이 모델은 환경 데이터(https://water.nier.go.kr/web)를 통해 수질 관리 현황을 2020-2023.7월까지 분석하여 제시했습니다. 프로젝트의 목적은 날짜 및 계절에 따른 cyanobacteria 수 및 다른 요인들과 이에 영향을 받는 독성 물질 수치의 변화를 분석하는 것을 목표로 합니다.

## 모델 설명
본 모델은 다음의 주요 내용을 분석했습니다. :
1. **상관관계 분석**: 낙동강 8개 보에서 채취한 데이터를 기반으로, cyanobacteria의 4종 개체 수와 TN, TP 수치 간의 상관관계를 분석합니다.
2. **층별 독소 물질 분석**: 수질 데이터 중 독성을 일으키는 MC-LR 냄새 물질은 표층과 혼합층에서 각각 수집됩니다. 모델은 이 두 층의 각 층에 cyanobacteria 개체수와 냄새 물질 수치 간의 상관관계가 어떻게 다른지 8개 보마다 회귀 분석(Linear Regression)을 통해 분석합니다.
3. **Microcystis cells 분석**: 2  이후 cyanobacteria 중 상관관계가 높은 종의 수와 이 종의 수에 영향을 미치는 요인들에 대한 분석 머신러닝 모델(Linear Regression, Decision Tree, SVM, 을 활용하여 진행합니다.

## 데이터 세트
데이터는 낙동강의 8개 보(상주보, 낙단보, 구미보, 칠곡보, 강정고령보, 달성보, 합천창녕보, 창녕함안보)에서 수집되었으며, 다음과 같은 정보를 포함합니다:
- Cyanobacteria 개체수 (4종)
- 총 질소(TN) 및 총 인(TP) 수치
- 8개 보의 표층 및 혼합층에서 수집된 MC-LR
- WT(Water Temperature), pH, DO, Chl-a, DTN, DTP, EC(Electric Conductivity), NH3-N, NO3-N, PO4-P, 8개 보 근처 7일간 강수량 평균, BOD, COD, TOC, SS

## 기술 스택
이 프로젝트에서 사용된 주요 기술 및 라이브러리는 다음과 같습니다:
- Python
- Scikit-learn
- Pandas
- NumPy
- Matplotlib
- statsmodels
- seaborn
- Scipy

## 결과 및 결론
이 모델은 낙동강에서의 cyanobacteria 개체수 중 Microcystis가 영양염 수치 간의 상관관계가 다른 종보다 높다는 것을 밝혀냈습니다. 결과는 (https://colab.research.google.com/drive/1A0qJ7vzFH2BczOxfAyMLiwTWSaSz3AlT) 과 결과-(https://colab.research.google.com/drive/16HYS8W9_h_8L4jOIzC_I7dvl2mpGPuvZ#scrollTo=AWY6gtOafHHG) 에서 확인할 수 있습니다. 이러한 분석은 계절별로 어떤 요인이 개체 수 증가에 영향을 주는지 또한 알아내어 향후 수질 관리 및 예방 조치에 사용될 것입니다.


