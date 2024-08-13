**프로젝트 소개 및 회고 :** <OTTO 장바구니 추천 시스템> 이라는 주제로 고객이 장바구니에 담긴 물건을 살 것인가 예측하는 프로젝트를 진행했습니다. 큰 데이터였기 때문에 chunk를 사용해 데이터를 잘라서 가져왔고, 이를 수월하게 사용하기 위해 데이터를 그룹화 하는 데에 가장 오랜 시간이 걸렸습니다. 모델은 lightGBM, XGBoost 등을 사용해 처음 성능을 내고, 결과를 바탕으로 voting ensemble을 해 성능을 높였습니다.

처음 도전한 kaggle 대회였던만큼 jsonl 파일을 처음으로 다뤄보고, ensemble이나 polars도 처음 접해봤습니다. 데이터 용량이 커서 모델링 한번 돌리는 데에도 오래 걸려 어려움을 겪었습니다. 하지만 Discussion을 통해 진행 순서나 새로운 라이브러리에 대해 배우는 부분이 정말 많았습니다.

**대회 링크 :** https://www.kaggle.com/competitions/otto-recommender-system

**프로젝트 기간 :** 2023.1.1 - 2023.2.1

**사용 언어 :**  **Python** ver.3.8

**역할 :** 개인 프로젝트 - 데이터 분석

**깃허브 링크 :** https://github.com/i2mmmmm/kaggle_otto
