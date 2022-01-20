# 7. Pipeline 살펴보기

***

이 절차는 파이프 라인을 직접 찾고 세부 정보 페이지를 보는 방법을 보여줍니다. 프로젝트의 일부인 파이프 라인은 프로젝트의 세부 정보 페이지에서도 찾을 수 있습니다. 프로젝트의 일부인 파이프 라인을 찾는 방법에 대한 자세한 내용은 SageMaker 프로젝트를 사용하여 MLOps 자동화를 참조하십시오.&#x20;

## 7. Pipeline 살펴보기

1. Pipelines 메뉴을 선택한후 Pipeline 이름을 클릭합니다.

![](<../.gitbook/assets/Screen Shot 2021-04-01 at 8.44.49 PM.png>)

2\. Executions 메뉴에서 성공적으로 실행된 Executions 을 클릭합니다.

![](<../.gitbook/assets/Screen Shot 2021-04-01 at 8.47.40 PM (1).png>)

3\. pipeline Graph의 단계중 'PreprocessAbaloneData' 클릭하여 Input, Output, logs, Information 을 살펴봅니다.

![](<../.gitbook/assets/스크린샷 2022-01-20 오후 3.02.49.png>)

![](<../.gitbook/assets/스크린샷 2022-01-20 오후 3.58.53.png>)

4\. 모델 훈련 단계에서 원하는 메뉴이동에 따라 CloudWatch 로그나 Training Job 으로 이동하실수 있습니다.

![](<../.gitbook/assets/스크린샷 2022-01-20 오후 3.59.08.png>)

![](<../.gitbook/assets/스크린샷 2022-01-20 오후 4.06.36.png>)

5\. Setting 이동하시어 Download pipeline definition file을 다운로드받아 전체 설정값 execution 별로 살펴보실수 있습니다.

![](<../.gitbook/assets/스크린샷 2022-01-20 오후 4.29.55.png>)

![](<../.gitbook/assets/스크린샷 2022-01-20 오후 4.29.39.png>)
