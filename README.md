# PJT_Search_Engine_Advancement
# 검색엔진 고도화 프로젝트

# 기간
| 2022년 9월 12일(월) ~ 2022년 10월 24일(월) 

# 멤버

|이름|담당 작업|
|:---:|:---:|
|[이태훈](https://github.com/git-ThLee)|meilisearch build, mecab 사용자 사전 구축|
|정새롬| meilisearch setting, 데이터 eda|
|성재훈| meilisearch build,리눅스 환경 세팅|

# 클라우드 플랫폼

- [GCP (Google Cloud Platform)](https://cloud.google.com/free?utm_source=google&utm_medium=cpc&utm_campaign=japac-KR-all-en-dr-bkws-all-all-trial-e-dr-1009882&utm_content=text-ad-none-none-DEV_c-CRE_602771418613-ADGP_Hybrid%20%7C%20BKWS%20-%20EXA%20%7C%20Txt%20~%20GCP_General_core%20brand_main-KWID_43700071610114344-aud-970366092687%3Akwd-87853815-userloc_1009877&utm_term=KW_gcp-ST_gcp&gclid=CjwKCAjwtp2bBhAGEiwAOZZTuDCcWPzbNVCZjhwCsuGS6LeCTC5SA005yRJXY_PRkuMgHqnmOEH5rRoCHbgQAvD_BwE&gclsrc=aw.ds)

# 검색엔진 

![image](https://user-images.githubusercontent.com/55564114/200228953-c6e7122a-32b9-423b-98f1-8cd56c17c5be.png)  

- [Meilisearch](https://www.meilisearch.com/)
- Meilisearch 장점
  - 속도가 빠르다
  - 쉽게 배포가 가능하다
  - 유연하다
  - 오타 허용이 된다
 
# 프로젝트 목적

- 형태소 분석 및 사용자 사전을 생성하여 검색 기능 향상(도메인 딕셔너리 개발, mecab 활용)

# 프로젝트 과정

1. 띄어쓰기 기반 토크나이징을 형태소 기반 토크나이징으로 변경하기
2. mecab 사용자 사전을 구축하여 성능 개선하기
  - mecab을 사용하는 이유는 meilisearch 패키지 중에 [lindera](https://github.com/lindera-morphology/lindera)가 있는데, lindera에서 mecab을 사용하기 때문이다
3. 사용자 사전을 구축하기 위한 데이터 수집(OCR, 크롤링) 및 전처리하기

# 성능평가

![image](https://user-images.githubusercontent.com/55564114/200230779-8a9965ae-861f-454a-9774-06e14d0bd10d.png)  

- Precision
- Recall
- F1 score
- Precision at K (P@K )

# 결과

![image](https://user-images.githubusercontent.com/55564114/200230919-913ffa13-ccac-4ae9-b9db-fa065b4adcbb.png)  

- F1 score 기준으로 0.7721 에서 0.8864 까지 성능이 향상하였다 
- P@K 기준으로 0.8472 에서 0.8502 성능이 향상하였다

# 전체 작업 과정

![image](https://user-images.githubusercontent.com/55564114/200231129-66d3ec0a-4253-4dbf-962f-4aafe0605346.png)
