---
description: >-
  모델승인이 완료되면 EventBridge 는 모델승인을 감지하여 모델배포용 CodePipeline을 실행하고 Staging 환경에 대한 추론
  endpoint가 배포됩니다.
---

# 4. Model 승인

1. 외쪽 창에서 "Components and registeries" 버튼을 클릭합니다.
2. 방금 만든 프로젝트를 선택합니다.

![](.gitbook/assets/screen-shot-2021-04-01-at-6.41.26-pm.png)

   3. "Model groups"탭을 선택하여 Model Group을 클릭합니다.

![](.gitbook/assets/screen-shot-2021-04-01-at-6.42.20-pm.png)

   4. Version 2를 클릭합니다.

![](.gitbook/assets/screen-shot-2021-04-01-at-6.43.25-pm%20%281%29.png)

{% hint style="warning" %}
Version 2 생성은 어느시점에 생기나요? CodePipeline의 Modelbuild pipeline이 완료되어야 생성됩니다. 모델승인 담당자의 approve 대기상태라 보시면 됩니다.   
{% endhint %}

   5. 오른쪽 상단의 "Update status"를 클릭하여, 'Status'에서 'Approved'을 선택하고 'Update status'를 클릭합니다.

![&#xC0C8;&#xB85C;&#xC6B4; &#xBAA8;&#xB378;&#xBC84;&#xC804; &#xD654;&#xBA74;](.gitbook/assets/screen-shot-2021-04-01-at-6.43.42-pm.png)

![](.gitbook/assets/screen-shot-2021-04-02-at-10.07.52-am.png)

{% hint style="warning" %}
* SageMaker Pipelines의 Mode Registory의 Model Group에 등록된 모델을 승인했습니다. 
* EventBridge 는 모델승인을 감지하여 모델배포 용 CodePipeline이 실행되고 Staging 환경에 대한 추론 endpoint가 Deploy 되었습니다. 
{% endhint %}



