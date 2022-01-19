---
description: >-
  모델 소스코드변경 후 소스커밋과 푸시를 진행합니다. CodeCommit 에 소스가 커밋되면  ModelBuild 용
  CodePipleline에 의해서 Build 프로세스가 완료됩니다.
---

# 4. Code 수정 및 커밋

1. SageMaker Studio 왼쪽 창에서 파일 브라우저 아이콘을 선택합니다.
2. "sagemaker-mlopsproject-xxxxxxxxx-**modelbuild**/pipelines/abalone"으로 이동하여 "pipeline.py"을 클릭합니다.

![pipeline.py 소스 수정화면](<../.gitbook/assets/Screen Shot 2021-04-01 at 5.26.01 PM.png>)

3\. "pipeline.py"소스에 training instance type을 ml.m5.large 로 수정하고 저장합니다.

![pipeline.py 소수 수정화면](<../.gitbook/assets/Screen Shot 2021-04-01 at 5.35.44 PM.png>)

4\. Git 버튼을 선택하여 방금 변경된 "pipeline.py"파일을 (+)클릭합니다. 변경내용은 Staged에 저장됩니다.

![Git 메뉴](<../.gitbook/assets/Screen Shot 2021-04-01 at 5.42.16 PM.png>)

5\. Summary에 "**Change intance type**"을 입력하고, Description에 수정내용을 입력하고 커밋합니다.

![](<../.gitbook/assets/Screen Shot 2021-04-01 at 5.46.41 PM.png>)

![커밋화면](<../.gitbook/assets/Screen Shot 2021-04-01 at 5.47.47 PM.png>)

6\. History 탭에서 변경내용을 확인하고 "Push Commited changed"버튼을 클릭합니다.

![Push 화면](<../.gitbook/assets/Screen Shot 2021-04-01 at 5.48.32 PM (1).png>)

7\. Dismiss 버튼 클릭합니다.

![](<../.gitbook/assets/Screen Shot 2021-04-01 at 5.48.45 PM.png>)

8\. CodeCommit에 커밋된 후 ModelBuild용 CodePipeline의 Build 프로세스가 진행됩니다.

![](<../.gitbook/assets/Screen Shot 2021-04-01 at 6.00.20 PM.png>)

{% hint style="warning" %}
pipeline.py는 abalone 데이터세트를 XGBoost를 사용하여 선형회귀모델을 Training 하고 있습니다. Abalone 데이터세트는 전복의 나이를 예측하는데 자주 이용되는 데이터 세트입니다. 수정된 코드를 push한 것을 EventBridge가 감지하여 CodePipeline이 실행되었습니다.
{% endhint %}

Amazon EventBridge는 애플리케이션을 다양한 소스의 데이터와 쉽게 연결할 수 있게 해주는 서버리스 이벤트 버스 서비스입니다. EventBridge는 고유한 애플리케이션, SaaS(Software-as-a-Service) 애플리케이션 및 AWS 서비스의 실시간 데이터 스트림을 전달하고, AWS Lambda와 같은 대상에 해당 데이터를 라우팅합니다.

![](<../.gitbook/assets/Screen Shot 2021-04-01 at 9.33.43 PM.png>)

규칙은 특정 유형의 이벤트를 감시합니다. 일치하는 이벤트가 발생하면 규칙에 연결된 대상으로 해당 이벤트가 라우팅됩니다. 규칙은 하나 이상의 대상에 연결할 수 있습니다. 본 구성에서는 3가지 규칙 생성합니다.

* _ModelBuild CodeCommit 리포지토리가 업데이트 될 때 배포를 트리거하는 규칙 -> 대상(modelbuild)_
* _CodeCommit이 커밋으로 업데이트 될 때 배포를 트리거하는 규칙 -> 대상(modeldeploy)_
* _SageMaker 모델 레지스트리가 새 모델 패키지로 업데이트 될 때 배포를 트리거하는 규칙입니다. 예를 들어 새 모델 패키지가 레지스트리에 등록됩니다.-> 대상(modedeploy)_

![](<../.gitbook/assets/Screen Shot 2021-04-01 at 9.29.35 PM.png>)
