---
description: >-
  모델승인이 완료되면 EventBridge 는 모델승인을 감지하여 모델배포용 CodePipeline을 실행하고 Staging 환경에 대한 추론
  endpoint가 배포됩니다.
---

# 5. Model 승인

1. 외쪽 창에서 "Components and registeries" 버튼을 클릭합니다.
2. 방금 만든 프로젝트를 선택합니다.

![](<../.gitbook/assets/Screen Shot 2021-04-01 at 6.41.26 PM.png>)

&#x20;  3\. "Model groups"탭을 선택하여 Model Group을 클릭합니다.

![](<../.gitbook/assets/Screen Shot 2021-04-01 at 6.42.20 PM.png>)

&#x20;  4\. Version 1를 클릭합니다.

![](<../.gitbook/assets/Screen Shot 2021-06-06 at 8.50.12 PM.png>)

{% hint style="warning" %}
Version 1은 생성된이유? CodePipeline의 Modelbuild pipeline이 완료되어야 생성됩니다. 모델승인 담당자의 approve 대기상태라 보시면 됩니다.  &#x20;
{% endhint %}

&#x20;  5\. 오른쪽 상단의 "Update status"를 클릭하여, 'Status'에서 'Approved'을 선택하고 'Update status'를 클릭합니다.

![update status](<../.gitbook/assets/Screen Shot 2021-06-06 at 8.51.37 PM (2).png>)

&#x20; 6\. 모델 승인 관리자가 'Approved' 승인처리합니다.

![update model version status](<../.gitbook/assets/Screen Shot 2021-06-06 at 8.54.09 PM.png>)

![Successfully updated Version 1 status](<../.gitbook/assets/Screen Shot 2021-06-06 at 8.56.03 PM.png>)

{% hint style="warning" %}
* SageMaker Pipeline의 Model Group에 등록된 모델을 승인했습니다.&#x20;
* EventBridge 는 모델승인을 감지하여 모델배포 용 CodePipeline이 실행되고 Staging 환경에 대한 추론 endpoint가 Deploy 되었습니다.&#x20;
{% endhint %}

&#x20;     7\. CodePipeline 모델 승인 파이프라인의 build가 3\~5분뒤 완료 확인합니다.

![](<../.gitbook/assets/Screen Shot 2021-06-06 at 9.01.22 PM.png>)

