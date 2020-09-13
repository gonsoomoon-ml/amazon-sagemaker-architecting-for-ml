# 주가 데이터(시계열) 클러스터링하기 

#### 주의 : 본 프로젝트는 마켓플레이스에 접근 가능한 별도 계정이 필요합니다. 본 프로젝트를 선택하시는 경우 먼저 AWS SA에게 접근권한과 관련한 내용을 문의하십시오.

알고리즘기반 주식거래 - 악마는 항상 디테일에 있습니다. 여러분은 All The Margins라는 신규 트레이딩 회사의 데이터 사이언스 팀에 합류하였습니다. 회사는 현재까지 성공적으로 운용중인 포트폴리오를 보여주었습니다. 여러분의 업무는 현재 포트폴리오와 유사한 패턴을 보이는 다른 주식을 찾아내는 것입니다. 본 과제에서는 클러스터링 문제해결을 위해 AWS ML 마켓플레이스의 알고리즘을 적용해 보고, 다음으로 SageMaker의 알고리즘을 활용하게 됩니다.  


**목표**: 고차원 공간에서 근접한 이웃을 추정해 냅니다.

1. 마켓플레이스의 [K-Shape: Time Series Clustering](https://aws.amazon.com/marketplace/pp/Spotad-LTD-K-Shape-Time-Series-Clustering/prodview-bjbovimwn5ajs) 알고리즘을 사용하여 시계열 데이터를 클러스터링 합니다.

1. SageMaker의 빌트인 [K-Means Algorithm](https://docs.aws.amazon.com/sagemaker/latest/dg/k-means.html) 알고리즘을 이용하여 고차원 데이터를 클러스터링합니다.

---

#### Task 1 설명:
첫 번째 과제에서는 시계열 데이터를 클러스터링하고, 주어진 기간 동안 서로 동일한 성과를 내는 주식을 찾아내는 방법을 배웁니다. 진행과정에서 주식시장 데이터를 다운로드 하고, 각 주가를 정규화한 후, 고유한 모양을 가지는 주식 클러스터를 식별할 것입니다. 그 다음 어떤 주식이 동일한 패턴을 보이는지 살펴보고 정리합니다. 여러가지 K (2~20)값을 시도하여 최소 SSD (Sum of the squared distances, 각 데이터포인트와 클러스터 중심사이의 거리 제곱의 합)를 리턴하는  `k`를 찾아냅니다. 

다음 링크의 [starter code](https://github.com/aws-samples/amazon-sagemaker-architecting-for-ml/blob/master/Starter-Code/Apply%20clustering%20techniques.ipynb)를 참고합니다. Task 2를 위해 보다 많은 시간을 투자하실 수 있도로 Task1은 보다 많은 구분을 이미 구현한 상태로 준비하였습니다.


#### *References:*

* [K-means 블로그](https://aws.amazon.com/blogs/machine-learning/k-means-clustering-with-amazon-sagemaker/)
* [AWS 마켓플레이스의 알고리즘과 모델을 이용하여 ML 프로젝트 가속화하기(동영상))](https://youtu.be/OrmHHVI1uPk?t=1682)
* [그래프 등 참고 예제](https://github.com/awslabs/amazon-sagemaker-examples/blob/master/aws_marketplace/using_model_packages/financial_transaction_processing/Extracting_insights_from_your_credit_card_statement.ipynb)

---

#### Task 2 설명:
본 과제에서는 고차원 공간에서 클러스터링 알고리즘을 적용하여 어떻게 근접한 이웃을 근사하는지를 배우게 됩니다. 본 작업의 일부분으로, 처음은 주식 종목 포트폴리오를 포함하는 고차원 데이터셋을 합성할 것이고, 그 다음 이 데이터셋에 K-Means 클러스터링 알고리즘을 적용하여 유사한 포트폴리오를 가지는 투자자의 군집을 구별하게 됩니다. 

**Notes**:

* 프로젝트에 재미를 더하기 위해, 특정 종목을 리스트에 추가해 보십시오. 

* 프로젝트 시간이 남나요?  
    Task1과 Task2 문제를 풀 수 있는 다른 알고리즘을 시도해 보고 적절한 매트릭으로 결과를 비교해 보십시오.

#### *References:*

* [K-means 블로그](https://aws.amazon.com/blogs/machine-learning/k-means-clustering-with-amazon-sagemaker/)
* [K-Means 동작방식(SageMaker 개발자 가이드)](https://docs.aws.amazon.com/sagemaker/latest/dg/algo-kmeans-tech-notes.html)
