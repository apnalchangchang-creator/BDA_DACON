# DACON BDA Learner Completion Prediction

데이콘 BDA 학습자 수료 예측 AI 경진대회 참가 코드 저장소입니다.  
본 프로젝트에서는 수강생들의 학습 데이터를 기반으로 최종 수료 여부를 예측하는 모델을 개발했습니다.  

---

##  대회 소개
- **대회명**: 데이콘 BDA 학습자 수료 예측 AI 경진대회  
- **주최**: DACON, 빅데이터분석학회 BDA  
- **목표**: 온라인 학습자의 행동 데이터를 분석하여 수료 가능성을 예측  

---

##  데이터 개요
- **train.csv**: 학습 데이터 (수료 여부 라벨 포함)  
- **test.csv**: 테스트 데이터 (라벨 미포함)  
- **submission.csv**: 제출 형식 (ID, prediction)  

 데이터 파일은 데이콘에서 직접 다운로드해야 하며, 본 저장소에는 포함되어 있지 않습니다.  

---

##  모델 및 접근 방법
- **전처리**  
  - 결측치 처리 및 이상치 제거  
  - 범주형 변수 Label Encoding  
  - 파생 변수 생성 (활동 빈도, 그룹 참여도 등)  

- **모델링**  
  - LightGBM 기반 이진 분류 모델  
  - Stratified K-Fold 교차 검증 (5-Fold)  
  - 과적합 방지 및 일반화 성능 확보  

- **평가지표**  
  - Binary F1 Score  

---

## 성과
- **Public Score**: 0.64837  
- **Private Score**: 0.70+ (최종 제출 기준)  

---

##  실행 방법
1. 저장소 클론:
   ```bash
   git clone https://github.com/username/DACON-BDA-Learner-Completion.git
   cd DACON-BDA-Learner-Completion
