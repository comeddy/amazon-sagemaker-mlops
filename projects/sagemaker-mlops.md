---
description: SageMaker 프로젝트를 사용하여 CI/CD로 엔드투엔드 ML 솔루션을 생성합니다.
---

# 2. SageMaker 프로젝트로 MLOps 자동화

## SageMaker 프로젝트 란 무엇입니까? <a href="#sagemaker-projects-whatis" id="sagemaker-projects-whatis"></a>

SageMaker 프로젝트를 사용하면 데이터 과학자 및 개발자 팀이 기계 학습 비즈니스 문제를 해결할 수 있습니다. 지속적 통합 및 지속적 전달 (CI/CD)을 사용하여 모델 구축 및 배포 파이프 라인을 자동화하는 SageMaker 제공 MLOP 템플릿으로 SageMaker 프로젝트를 생성 할 수 있습니다. SageMaker에서 제공 한 템플릿은 선택한 템플릿에 따라 모델 구축, 교육 및 배포를 포함하여 완전한 종단 간 MLOps 시스템에 필요한 초기 설정을 프로비저닝합니다.

SageMaker 프로젝트는 엔드 투 엔드 ML 솔루션을 쉽게 생성 할 수있는 AWS Service Catalog 프로비저닝 제품입니다. AWS Service Catalog에 대한 자세한 내용은 [AWS Service Catalog](https://docs.aws.amazon.com/servicecatalog/latest/adminguide/introduction.html) 란 무엇입니까?를 참조하십시오 .

각 SageMaker 프로젝트에는 프로젝트에서 생성 된 모든 SageMaker 및 AWS 리소스에 전달되는 고유한 이름과 ID가 있습니다. 이름과 ID를 사용하여 프로젝트와 관련된 모든 항목을 볼 수 있습니다. 여기에는 다음이 포함됩니다.

* 파이프 라인 실행
* 등록 된 모델
* 배포 된 모델 (엔드 포인트)
* 데이터 세트
* AWS 서비스 카탈로그 제품
* AWS CodePipeline 파이프 라인
* AWS CodeCommit 리포지토리

### MLOps의 이점 <a href="#sagemaker-projects-benefits" id="sagemaker-projects-benefits"></a>

MLOps 방식을 채택하면 다음과 같은 이점을 제공하여 ML 프로젝트의 시장 출시 시간을 단축 할 수 있습니다.

* **생산성** -선별 된 데이터 세트에 액세스 할 수있는 셀프 서비스 환경을 제공하면 데이터 엔지니어와 데이터 과학자가 데이터 누락 또는 유효하지 않은 데이터로 인한 시간 낭비를 줄이고 더 빠르게 이동할 수 있습니다.
* **반복성** -MLDC의 모든 단계를 자동화하면 모델 학습, 평가, 버전 지정 및 배포 방법을 포함하여 반복 가능한 프로세스를 보장 할 수 있습니다.
* **신뢰성** -CI/CD 관행을 통합하면 신속하게 배포 할 수있을뿐만 아니라 품질과 일관성을 높일 수 있습니다.
* **감사 가능성** -데이터 과학 실험에서 소스 데이터, **학습** 된 모델에 이르기까지 모든 입력 및 출력의 버전을 지정하면 모델이 구축 된 방법과 배포 된 위치를 정확하게 보여줄 수 있습니다.
* **데이터 및 모델 품질** -MLOps를 사용하면 모델 편향을 방지하고 시간에 따른 데이터 통계 속성 및 모델 품질의 변경 사항을 추적하는 정책을 시행 할 수 있습니다.

## 프로젝트 사용에 필요한 SageMaker Studio 권한 <a href="#sagemaker-projects-studio-updates" id="sagemaker-projects-studio-updates"></a>

**관리자 및 도메인 실행 역할 사용자에 대한 프로젝트** 권한 을 활성화하려면

1. [SageMaker 콘솔](https://console.aws.amazon.com/sagemaker/) 열기.
2. 페이지 왼쪽 상단에서 **Amazon SageMaker Studio** 를 선택합니다.
3. **빠른 설정 선택 합니다.** Amazon SageMaker가 계정을 구성하고 sageSAmazon SageMaker가 계정을 구성하고 SageMaker 도메인에 대한 권한을 설정하도록 합니다.

![](<../.gitbook/assets/스크린샷 2022-01-20 오전 2.05.50.png>)

4\. Studio를 시작합니다.

![](<../.gitbook/assets/스크린샷 2022-01-20 오전 10.04.59.png>)
