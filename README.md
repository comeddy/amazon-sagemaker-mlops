---
description: SageMaker 프로젝트를 사용하여 CI/CD로 MLOps 솔루션을 실습 및 구성합니다.
---

# SageMaker Project

**실습구성**

![](.gitbook/assets/.jpg%20%281%29.jpeg)



1. MLOps 템플릿을 사용하여 프로젝트 생성합니다. 이때 Service Catalog의 Cloudformation을 이용합니다.
2. CodeCommit에 변경소스를 커밋하고 Push합니다.
3. CodePipeline의 CodeBuild가 실행됩니다.
   1. 커밋된 소스변경발생시 EventBridge 이벤트발생합니다.
4. CodeBuild에서 SageMaker Pipeline을 실행합니다.
5. Model group에 등록된 학습결과의 모델을 승인합니다.
6. 모델의 승인을 감지하여 CodePipeline\(Modeldeploy\)을 실행합니다.
7. CodeBuild에서 CloudFormation을 이용하여 Staging 에 대한 추론 endpoint를 구성합니다.
8. Pipeline 의 승인을 감지하여 6번과 마찬가지로 CloudFormation에서 Prod환경에 대한 추론 endpoint를 구성합니다.

