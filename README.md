# 검색엔진 고도화 프로젝트

---

# 🛰 성능 결과

| 검색 성능(F1) 0.7721 -> 0.8864 (14.8%) 향상됨

# 핵심 작업

1. (RUST) Meilisearch 한국어 형태소분석 빌드 
2. (Python) EDA 및 Mecab 사용자 사전 구축
3. (리눅스) GCP 환경구축

---

# 🕓 기간 
| 2022년 9월 5일(월) ~ 2022년 10월 24일(월) 

# 📆 스케줄

|일정| 날짜| 기간 |
|:---:|:---:|:---:|
|프로젝트 기획 기간| 9/5(월) ~ 9/19(월) | 2주 |
|기획 발표(수행계획 포함)| 9/19(월) | 1일|
|프로젝트 수행기간 1차|9/20(화) ~ 10/7(금)| 2주|
|중간 발표(중간 진행 상황/피드백)|10/7(금)|1일|
|프로젝트 수행기간 2차|10/7(금) ~ 10/21(금)|2주|
|최종 발표|10/24(월) ~ 10/25(화) | 2일 |
|총 수행기간|9/5(월) ~ 10/25(화) | 50일 | 

# 🧔 멤버

|이름|담당 작업|
|:---:|:---:|
|[이태훈](https://github.com/git-ThLee)|meilisearch build, mecab 사용자 사전 구축|
|정새롬| meilisearch setting, 데이터 eda|
|성재훈| meilisearch build,리눅스 환경 세팅|
|[박제윤](https://github.com/Jeiyoon)| 멘토님|

# ☁ 클라우드 플랫폼

- [GCP (Google Cloud Platform)](https://cloud.google.com/free?utm_source=google&utm_medium=cpc&utm_campaign=japac-KR-all-en-dr-bkws-all-all-trial-e-dr-1009882&utm_content=text-ad-none-none-DEV_c-CRE_602771418613-ADGP_Hybrid%20%7C%20BKWS%20-%20EXA%20%7C%20Txt%20~%20GCP_General_core%20brand_main-KWID_43700071610114344-aud-970366092687%3Akwd-87853815-userloc_1009877&utm_term=KW_gcp-ST_gcp&gclid=CjwKCAjwtp2bBhAGEiwAOZZTuDCcWPzbNVCZjhwCsuGS6LeCTC5SA005yRJXY_PRkuMgHqnmOEH5rRoCHbgQAvD_BwE&gclsrc=aw.ds)

# 🖥 검색엔진(Meilisearch) 소개

![image](https://user-images.githubusercontent.com/55564114/200228953-c6e7122a-32b9-423b-98f1-8cd56c17c5be.png)  

- [Meilisearch](https://www.meilisearch.com/)란 
  - 속도가 빠르다
  - 쉽게 배포가 가능하다
  - 유연하다
  - 오타 허용이 된다
  - Rust 언어로 만들었다 (이것 때문에 많이 고생했다...)

 ---

# 🧨 프로젝트 목적

- `형태소 분석` 및 `사용자 사전`을 생성하여 검색 기능 향상(도메인 딕셔너리 개발, mecab 활용)

# 🔥 프로젝트 과정

1. 띄어쓰기 기반 토크나이징을 형태소 기반 토크나이징으로 변경하기
2. 사용자 사전을 구축하기 위한 데이터 수집(OCR, 크롤링) 및 전처리하기
3. mecab 사용자 사전을 구축하여 성능 개선하기
    - mecab을 사용하는 이유는 meilisearch 패키지 중에 [lindera](https://github.com/lindera-morphology/lindera)가 있는데, lindera에서 mecab을 사용하기 때문이다

# 📋 프로젝트 진행 전 상황 

![image](https://user-images.githubusercontent.com/55564114/200232387-b25ffab3-28b0-4c4a-9e22-0e1939f2f0e4.png)  

- 띄어쓰기 기반 토크나이징에 의해 "필립스적외선전구"를 검색하게 되면 검색 효율이 저하가 된다
- 이를 형태소 분석 기반 토크나이징으로 변경하게 되면 "필립스 적외선 전구"로써 검색이 되며, 검색 효율이 증가하게 된다

# 성능평가

![image](https://user-images.githubusercontent.com/55564114/200230779-8a9965ae-861f-454a-9774-06e14d0bd10d.png)  

성능평가는 F1-score를 기준으로 했습니다. 프로젝트 내에서 검색결과 sort는 제외하라는 언급이 있었기에 Precision at K는 부적합하다고 판단했습니다. (sort(필터)하기 전에 적합 문서들만 검색이 되게하는 것이 목표)

# 결과

![image](https://user-images.githubusercontent.com/55564114/200230919-913ffa13-ccac-4ae9-b9db-fa065b4adcbb.png)  

- F1 score 기준으로 `0.7721 에서 0.8864` 까지 성능이 향상하였다 
- P@K 기준으로 `0.8472 에서 0.8502` 성능이 향상하였다

# 전체 작업 과정

![image](https://user-images.githubusercontent.com/55564114/200239738-dae18242-5e82-4a84-918b-eceafb0d5e89.png)  
