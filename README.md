# SKYTREND: 서울 주요 상권 날씨 기반 매출 예측 프로젝트

## 프로젝트 개요
SKYTREND는 기상청 공공 API의 날씨 데이터와 서울 주요 상권(용산역전자상가, 노량진역, 가산디지털단지)의 2022년 매출 데이터를 활용하여 2023년 매출을 예측하는 프로젝트입니다. 날씨 요소가 상권 매출에 미치는 영향을 분석하고, 이를 기반으로 머신러닝 모델을 통해 매출을 예측합니다.

## 기술 스택
- **언어**: Python 3.11
- **데이터베이스**: MongoDB
- **주요 라이브러리**: 
  - 데이터 처리: Pandas, NumPy
  - 머신러닝: Scikit-learn, statsmodels
  - 시각화: Matplotlib, Seaborn, Plotly
  - 웹 대시보드: Streamlit

## 프로젝트 구조
```
skytrend/
├── src/
│   ├── dashboard/
│   │   └── app.py
│   ├── models/
│   │   ├── __init__.py
│   │   └── prediction_models.py
│   ├── database.py
│   └── data_collector.py
├── data/
│   └── seoul_sales_data.csv
├── notebooks/
│   ├── data_analysis.ipynb
│   └── data_preprocessing.ipynb
└── requirements.txt
```

## 주요 분석 결과

### 1. 상권별 매출 예측
- **용산전자상가**: 2023년 5.2% 매출 증가 예상 (14.7억원 → 15.5억원)
- **노량진역**: 2023년 17.5% 매출 감소 예측 (15.7억원 → 13.0억원)
- **가산디지털단지**: 2023년 38.9% 매출 감소 예측 (26.3억원 → 16.1억원)

### 2. 계절별 매출 트렌드
#### 용산전자상가
- 가을(+11.3%)과 겨울(+11.1%)에 가장 큰 매출 증가 예상
- 여름은 소폭 증가(+1.8%), 봄은 소폭 감소(-2.7%) 전망

#### 노량진역
- 봄철 매출 증가(+3.4%) 예상
- 가을(-29.6%)과 여름(-25.1%)에 큰 폭의 매출 감소 예측

#### 가산디지털단지
- 전 계절 유사한 수준의 매출 감소 예상(-37.8% ~ -39.7%)
- 계절적 영향이 가장 적은 것으로 분석

### 3. 날씨 영향도 분석 (2022년 실제 데이터 기준)
- **기온 영향**: 가산디지털단지(0.618) > 노량진역(0.560) > 용산전자상가(0.435)
- **강수량 영향**: 노량진역(0.731) > 용산전자상가(-0.359) > 가산디지털단지(0.197)
- **습도 영향**: 노량진역(0.719) > 용산전자상가(-0.345) > 가산디지털단지(0.195)

## 데이터 시각화

### 1. 계절별 평균 매출 비교
#### 용산전자상가
![용산전자상가 계절별 매출]
![alt text](용산계절별평균매출비교.png)

#### 가산디지털단지
![가산디지털단지 계절별 매출]
![alt text](가산평균매출비교.png)

#### 노량진역
![노량진역 계절별 매출]
![alt text](노량진평균매출비교.png)

### 2. 날씨-매출 상관관계 분석
#### 용산전자상가 (2022-2023)
![용산전자상가 상관관계]
![alt text](<22용산 날씨,매출 상관관계-1.png>)
![alt text](<23용산 날씨,매출 상관관계-1.png>)

#### 가산디지털단지 (2022-2023)
![가산디지털단지 상관관계]
![alt text](22가산날씨매출상관관계-1.png)
![alt text](23가산날씨매출상관관계-1.png)

#### 노량진역 (2022-2023)
![노량진역 상관관계]
![alt text](<22노량진날씨,매출 상관관계-1.png>)
![alt text](<23노량잔 날씨,매출 상관관계-1.png>)

### 3. 날씨 요소별 매출 영향
#### 용산전자상가
![용산전자상가 날씨 영향]
![alt text](용산기온강수량습도매출관계-1.png)

#### 가산디지털단지
![가산디지털단지 날씨 영향]
![alt text](가산기온강수량습도매출관계-1.png)

#### 노량진역
![노량진역 날씨 영향]
![alt text](노량진기온강수량습도매출관계-1.png)