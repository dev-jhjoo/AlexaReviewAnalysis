# Amazon Alexa 리뷰 분석

---
> 이 프로젝트는 Amazon Alexa 제품 리뷰를 분석하여 자연어 처리(NLP)와 머신러닝 기법을 사용해 평점을 예측하는 것을 목표로 합니다.

## 프로젝트 개요
 
이 프로젝트의 주요 목표는 다음과 같습니다:
1. Amazon Alexa 리뷰를 분석하여 고객 감정과 주요 주제에 대한 통찰을 도출합니다.
2. 리뷰 텍스트를 기반으로 제품 평점을 예측하는 머신러닝 모델을 구축합니다.
3. 모델 성능을 다양한 지표로 평가하고 시각화 자료를 통해 결과를 확인합니다.

## 주요 기능
- **데이터 전처리**: 리뷰 데이터에서 공백, 불필요한 문자를 제거하고 불용어 제거, 표제어 처리 등의 전처리 과정을 수행했습니다.
- **평점 예측**: Random Forest 모델을 사용해 리뷰 텍스트를 기반으로 제품 평점을 예측했습니다.
- **모델 평가**: 정확도, 혼동 행렬, 분류 보고서를 통해 모델의 성능을 평가했습니다.

## 프로젝트 구조

- `amazon_alexa_review_analysis.ipynb`: 데이터 전처리부터 모델 구축, 평가까지 모든 과정이 담긴 Jupyter Notebook 파일입니다.
- `data/amazon_alexa.tsv`: 분석에 사용된 Amazon Alexa 제품 리뷰 데이터셋입니다.
- `out/misclassification_df.csv`: 실제 평점과 예측된 평점이 2점 이상 차이 나는 리뷰들을 저장한 CSV 파일입니다.

## 설치 방법

레포지토리 클론:
   ```bash
   git clone https://github.com/your-repo/alexa-review-analysis.git
   ```

## 데이터 셋
이 데이터셋은 Amazon Alexa 제품 리뷰로 구성되어 있으며, 다음과 같은 컬럼을 포함하고 있습니다:

* rating: 제품 평점(1-5).
* date: 리뷰 작성 날짜.
* variation: 제품의 변형 정보(예: 색상 또는 버전).
* verified_reviews: 실제 리뷰 텍스트.
* feedback: 긍정적인 피드백을 받았는지 여부.

## 모델 세부사항
* 랜덤 포레스트 분류기: 리뷰 텍스트를 기반으로 제품 평점을 예측하기 위해 랜덤 포레스트 모델을 사용했습니다. 리뷰 텍스트는 TF-IDF 벡터로 변환되어 모델에 입력되었습니다.

* 성능 지표:
  * 정확도: 81.89%
  * 혼동 행렬: 예측이 맞은 경우와 틀린 경우를 시각화하여 분석.

## 결과
* 혼동 행렬: 혼동 행렬 분석 결과, 3점 이하에 리뷰에서 오분류된 경우가 많았습니다.
* 오분류된 리뷰: 실제 평점과 예측 평점의 차이가 2점 이상인 리뷰는 CSV 파일에 저장되었습니다.

## 결론
* 리뷰 데이터 예측 모델링을 통해 3점 이하에서 오분류된 데이터가 상대적으로 많다는것을 확인 했습니다. 그래서 해당 리뷰들을 실제로 확인해보니 실제 리뷰 점수는 낮지만 제품에 대해 관심도는 높은 리뷰들을 확인할 수 있었습니다. 이를통해 실제 점수와 예측된 점수가 2점 이상 차이가 난다면 오분류 데이터로 분류한 후 오분류된 리뷰 데이터들을 전부 확인하여 현재 AI 스피커 시장에서 개선되어야할 사항들을 정리하여 제품 개발시에 충분히 활용할 수 있다고 느꼈습니다.
