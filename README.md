# kaggle_otto

0. 캐글 데이터 코랩에서 받기
참조 : https://han-py.tistory.com/279


1. jsonl 파일 어떻게 데이터 프레임으로 만들지 ?

json을 line 으로 구분한 형태의 파일이다.
 pd.read_json('train.jsonl', **lines=True**)로 가져올 수 있다.
 
 
2. train의 용량이 너무 크다.

train 데이터는 colab에서 ram 이 모자람
train 데이터를 가져오다가 vs에서 에러

**chunk** 를 사용해 데이터를 쪼개서 가져옴.
(e는 인덱스, e<2로 했을 때 e=0,1 두 번 데려와서 chunk 사이즈의 두 배를 가져옴)


3. 결정트리로 머신러닝 결과

type 을 예측하는 모델을 만들었는데, order가 너무 적은 탓인지 예측 값에는 click 과 cart 뿐.
훈련 정확도 0.9480435038844554
검증 정확도 0.8817603421989731
65분 13초 돌린 모델이지만 제출 폼에서 5,015,409개 중 null 값이 4,803,126개
target을 바꿔보려고 도전했으나 session aid 합치기 실패.
Unable to allocate 22.6 TiB for an array with shape (3102202662209,) and data type int64
22TB가 필요하다니...


4. 앙상블 공부

* 배깅 : 샘플을 여러번 뽑아(bootstrap) 각 모델을 학습시켜 결과물을 집계하는 방법

1)categorical data - 투표방식 (voting)
-> 전체 모델에서 예측한 값 중 가장 많은 값을 최종 예측값으로 선정
2)continuous data - 평균
-> 결정값의 평균으로 최종 예측값 선정
 배깅은 간단, 파워풀 ex)랜덤 포레스트

* 부스팅 : 가중치를 활용하여 약 분류기를 강 분류기로 만드는 방법

부스팅은 배깅에 비해 error 적음
속도 느리고 오버 피팅 가능성 있음

개별 결정 트리의 낮은 성능 문제 - 부스팅으로 (xgboost lightGBM)
오버피팅 문제 - 배깅으로 (random forest)


5. polars

앙상블 공부 중에 polars 발견
pandas와는 조금 다른 사용법이라 공부가 필요함.
메모리가 굉장히 효율적이며, 시간면에서도 빠른 처리가 가능하다.

언젠가 panda를 대체하게 될 것 같아 캐글이 끝난 이후에도 공부가 필요할 것 같다.



= 2575명 중 706위로 마무리.

늦게 시작하여 아쉬움이 많이 남는다.
다시 한다면 baseline을 좀 더 빨리 잡고, eda를 좀 더 다양하게 처리해볼 것 같다.

좋았던 점은
jsonl 파일을 처음 다뤄봤고, chunk를 처음 사용해봤다.
그리고 교육에서는 배우지 않았던 polars를 알게 되어 좋았다.


<img src="https://img.shields.io/badge/R-276DC3?
style=flat&logo=R Boot&logoColor=white"/>
