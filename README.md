# DACON BDA Learner Completion Prediction

데이콘 BDA 학습자 수료 예측 AI 경진대회 참가 코드 저장소입니다.  
본 프로젝트는 온라인 학습자의 행동 데이터를 기반으로 최종 수료 여부(`withdrawal`)를 예측하는 이진 분류 모델을 구현했습니다.

---

##  대회 소개
- **대회명**: 데이콘 BDA 학습자 수료 예측 AI 경진대회  
- **주최**: DACON, 빅데이터분석학회 BDA  
- **목표**: 학습자의 로그 데이터를 분석하여 수료 가능성을 예측  

---

##  데이터 개요
- **train.csv**: 학습 데이터 (수료 여부 라벨 포함)  
- **test.csv**: 테스트 데이터 (라벨 미포함)  
- **sample_submission.csv**: 제출 형식 (ID, prediction)  

 데이터는 데이콘에서 다운로드해야 하며, 본 저장소에는 포함되어 있지 않습니다.  

---

##  모델 및 접근 방법
- **전처리**
  - ID 컬럼 제거  
  - 범주형 컬럼(Label, bool)을 `LabelEncoder`로 변환  

- **모델링**
  - LightGBM (`binary` objective)  
  - Stratified K-Fold 교차검증 (5-Fold)  
  - 학습 metric: `binary_error`  
  - 예측은 0.5 임계값으로 이진화  

- **예측/출력**
  - Fold별 예측값을 평균하여 최종 제출값 산출  
  - `submit.csv` 파일로 저장  

---

##  실행 방법
1. 저장소 클론:
   ```bash
   git clone https://github.com/username/DACON-BDA-Learner-Completion.git
   cd DACON-BDA-Learner-Completion
