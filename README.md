# 📊 모바일 게임 시장 분석 프로젝트

이 프로젝트는 모바일 게임의 매출 및 사용자 데이터를 기반으로 **장르별 시장 동향 분석**과 **A/B 테스트 기반 사용자 행동 분석**을 수행합니다. Jupyter Notebook 2종, 가공 및 원시 데이터, 분석 결과 보고서로 구성되어 있습니다.

---

## 📂 파일 구성

| 파일명 | 설명 |
|--------|------|
| `Game_Revenue_Analysis.ipynb` | 장르 및 게임별 매출 데이터를 분석하고, 시각화를 통해 주요 장르와 상위 게임을 파악합니다. |
| `Game_User_Behavior_ABTest.ipynb` | A/B 테스트 데이터를 기반으로 그룹별 사용자 수, 로그인 횟수, 수익 비교 분석을 수행합니다. |
| `mobile_game_revenue.csv` | 모바일 게임의 장르, 매출, 출시일, 퍼블리셔 정보가 포함된 원시 매출 데이터 (`mobile-games.csv`의 정식 이름) |
| `mobile_game_usercount.csv` | 게임별 사용자 수 및 관련 정보가 포함된 데이터 (`Mobile_games.csv`의 정식 이름) |
| `genre_top5_games.csv` | 장르별 상위 5개 게임과 매출 정보를 정리한 전처리 데이터 |
| `top10_overall_games.csv` | 전체 매출 기준 상위 10개 게임 정보를 정리한 전처리 데이터 |
| `merged_abtest_data.csv` | 로그인, 가입, 수익 데이터 등을 통합한 A/B 테스트용 통합 데이터 |
| `Project_Report_BTeam.docx` | 프로젝트 배경, 분석 내용, 주요 결과 등을 담은 보고서 (한글 작성) |

---

## 🧪 실험코드 설명

### 1. `Game_Revenue_Analysis.ipynb`
- 장르 및 게임명 표준화
- 과학적 표기 매출값 정규화
- 다중 장르 분해 및 시각화
- 주요 시각화:
  - 장르별 매출 상위 5개 게임 막대그래프
  - 전체 매출 상위 10개 게임 막대그래프
  - 장르별 매출 점유율 파이차트

### 2. `Game_User_Behavior_ABTest.ipynb`
- `ab_test.csv`, `auth_data.csv`, `reg_data.csv` 병합
- 유닉스 타임스탬프 변환
- 그룹별:
  - 로그인 횟수
  - 평균 수익
  - 가입 시기 분포
- 로그인 횟수별 평균 수익 비교

---

## 📈 데이터 설명

| 데이터 파일명              | 주요 컬럼 설명 |
|----------------------------|----------------|
| `mobile_game_revenue.csv`  | `Game`, `Revenue`, `Genre`, `Publisher`, `Release Date` 등 모바일 게임 매출 관련 원시 데이터 |
| `mobile_game_usercount.csv`| `Game Title`, `Player Count`, `Publisher`, `Release Date` 등 유저 수 기반 인기 게임 정보 |
| `merged_abtest_data.csv`   | `user_id`, `testgroup`, `revenue`, `reg_date`, `login_count`, `first_login`, `last_login` 등 통합 A/B 테스트 분석용 데이터 |
| `ab_test.csv`              | `user_id`, `testgroup` — A/B 테스트 그룹 할당 정보 |
| `reg_data.csv`             | `user_id`, `reg_date` — 사용자 가입 일자 정보 |
| `auth_data.csv`            | `user_id`, `login_time` — 유저 로그인 활동 (중복 포함, 로그 단위) |

---

## 🔍 주요 인사이트

- Puzzle, RPG, Strategy, MOBA 장르가 전체 수익의 **65% 이상** 차지
- A/B 테스트 결과, **B 그룹의 평균 수익이 다소 높음**
- **로그인 4~5회** 유저의 평균 수익이 가장 높음
- Tencent 등의 대형 퍼블리셔가 수익 상위권 대부분 차지
- **장기 수익형 게임**: Clash of Clans, Puzzle & Dragons 등

---

## 🔮 향후 확장 방향

- DAU/MAU 지표 반영한 사용자 잔존 모델 구축
- Prophet, ARIMA 기반 매출 예측 모델 적용
- K-평균 또는 GMM 기반 사용자 군집 분석

