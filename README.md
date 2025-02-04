# 🚇 서울 지하철 혼잡도 예측 분석

## 📌 프로젝트 개요
이 프로젝트는 **서울교통공사의 공공데이터**를 활용하여 지하철 혼잡도를 예측하는 머신러닝 모델을 개발하는 것을 목표로 합니다.

## 🎯 프로젝트 목표
- 서울 지하철의 **혼잡도 패턴 분석**
- **공공데이터**를 활용하여 **시간대별 지하철 혼잡도 예측**
- **K-Means** 클러스터링을 활용한 역별 혼잡도 그룹화
- **RandomForest, XGBoost** 등 머신러닝 모델 적용
- **편의시설이 혼잡도에 미치는 영향 분석**

## 📊 데이터 설명
사용한 데이터는 **서울교통공사에서 제공한 공공데이터**로, 다음과 같은 **CSV 파일**로 구성되어 있습니다.

| 파일명 | 설명 |
|--------|------|
| `서울교통공사_지하철_혼잡도_및_편의시설_병합.csv` | 지하철 혼잡도 및 역별 편의시설 데이터 (전처리 완료) |
| `지하철혼잡도.ipynb` | 데이터 분석 및 모델 실행을 수행한 Jupyter Notebook |

### 🔍 주요 변수 설명
- `시간 (time)`: 5시30분~00시30분 사이의 지하철 운영 시간
- `요일 (weekday)`: 평일, 토요일, 일요일
- `혼잡도 (congestion)`: 0~1 사이로 정규화된 승객 혼잡도 지표
- `편의시설 유무`: 엘리베이터, 환승주차장, 수유실 등의 편의시설 정보

## 🏆 사용한 머신러닝 모델
### 🔹 적용된 모델
1. **RandomForestRegressor**: 랜덤 포레스트 기반 예측
2. **XGBRegressor (XGBoost)**: 부스팅 기반의 예측 모델
3. **KMeans Clustering**: 역별 혼잡도 클러스터링

## 📈 분석 결과 요약
✅ 출퇴근 시간 (7-9AM, 6-8PM)이 가장 혼잡함
✅ K-Means를 활용하여 3개의 혼잡도 클러스터(낮음, 중간, 높음)로 분류
✅ **XGBoost 모델이 가장 높은 예측 성능 (R² ≈ 0.99, RMSE ≈ 0.98)**    

## ⚙️ 실행 방법
### 1) 필요 패키지 설치
```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost
```

### 2) 데이터 다운로드
```bash
git clone https://github.com/kimhee02/Seoul_subway_congestion.git
cd Seoul_subway_congestion
```

### 3) Jupyter Notebook 실행
```bash
jupyter notebook 지하철혼잡도.ipynb
```
