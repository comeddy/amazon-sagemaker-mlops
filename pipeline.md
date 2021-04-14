---
description: >-
  이 절차는 파이프 라인을 직접 찾고 세부 정보 페이지를 보는 방법을 보여줍니다. 프로젝트의 일부인 파이프 라인은 프로젝트의 세부 정보
  페이지에서도 찾을 수 있습니다. 프로젝트의 일부인 파이프 라인을 찾는 방법에 대한 자세한 내용은 SageMaker 프로젝트를 사용하여
  MLOps 자동화를 참조하십시오 .
---

# 6. Pipeline 살표보기\(옵션\)

1. Pipelines 메뉴을 선택한후 Pipeline 이름을 클릭합니다.

![](.gitbook/assets/screen-shot-2021-04-01-at-8.44.49-pm.png)

   2. Executions 메뉴에서 성공적으로 실행된 Executions 을 클릭합니다. 

![](.gitbook/assets/screen-shot-2021-04-01-at-8.47.40-pm%20%281%29.png)

   3. pipeline Graph의 단계중 'PreprocessAbaloneData' 클릭하여 Output, logs, Information 을 체크합니다.

![](.gitbook/assets/screen-shot-2021-04-01-at-8.50.08-pm.png)

    4. 'Start an execution'을 클릭하여 '**Execution-Test**'를 입력하여, 커스텀 Execution 실행을 시도해봅니다. \(ProcessingInstanceCount 를 2대로 설정\)

![](.gitbook/assets/screen-shot-2021-04-01-at-9.02.33-pm.png)



  5. Execution Grape를 통해 단계별 과정을 확인합니다. 더이상 진행을 원하지 않을 경우 Stop을 클릭합니다.

![](.gitbook/assets/screen-shot-2021-04-01-at-9.10.35-pm.png)

  6. Pending 상태의 'Version 3'을 클릭합니다.

![](.gitbook/assets/screen-shot-2021-04-01-at-10.00.34-pm.png)

  7. Pending 상태의 Version 3의 모델을 승인합니다.

![](.gitbook/assets/screen-shot-2021-04-01-at-10.01.16-pm.png)

  8. 'Execution-Test'의 Status가 Succeeded 상태가 되면, Parameters 메뉴에서 변경된 ProcessInstanceCount 값을 확인합니다.

![](.gitbook/assets/screen-shot-2021-04-01-at-9.50.37-pm.png)

 9. Pipeline의 DeployStaging 진행을 거처 Prod Deploy 승인 대기상태에서 승인시 Prod Deploy가 완료됩니다.

![](.gitbook/assets/screen-shot-2021-04-01-at-8.07.03-pm.png)



