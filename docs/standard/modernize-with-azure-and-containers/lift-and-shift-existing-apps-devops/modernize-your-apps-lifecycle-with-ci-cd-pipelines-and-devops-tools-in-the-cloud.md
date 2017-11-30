---
title: "현대화 CI/CD 파이프라인 및 DevOps 도구로 클라우드에서 앱의 수명 주기"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 현대화 CI/CD 파이프라인 및 DevOps 도구로 클라우드에서 앱의 수명 주기"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: 2799f203cec2b01d2c9ff1a60ece801dc5939104
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a>현대화 CI/CD 파이프라인 및 DevOps 도구로 클라우드에서 앱의 수명 주기

오늘날의 비즈니스 경쟁 시장에 포함 되도록 빠른 속도로 혁신 하도록 해야 합니다. DevOps 도구와 프로세스 혁신 주기적으로이 구현 하는 데 중요 한 최신 응용 프로그램 필요 높은 품질을 제공 합니다. 오른쪽 DevOps 도구와 함께 개발자 연속 배포를 효율적이 고 사용자의 혁신적인 응용 프로그램에 보다 신속 하 게 가져올 수 있습니다.

연속 통합 및 배포 사례는 잘 구성, 특히 다중 컨테이너 응용 프로그램을 사용 하 여 작업할 때 컨테이너의 도입 새로운 고려 사항을 소개 합니다.

Visual Studio Team Services에는 연속 통합 및 다양 한 공식 Team Services 배포 작업을 수행 하는 환경에 여러 컨테이너 응용 프로그램 배포를 지원합니다.

-   [독립 실행형 Docker 호스트 VM에 배포](https://docs.microsoft.com/vsts/build-release/apps/cd/deploy-docker-windowsvm) (Linux 또는 Windows Server 2016 이상)

-   [서비스 패브릭에 배포](https://docs.microsoft.com/azure/service-fabric/service-fabric-tutorial-deploy-app-with-cicd-vsts)

-   [Azure 컨테이너 서비스 – Kubernetes에 배포](https://docs.microsoft.com/vsts/build-release/apps/cd/azure/deploy-container-kubernetes)

또한에 배포할 수 있지만 [docker는 Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) 또는 DC/Team Services 스크립트 기반 작업을 사용 하 여 운영 체제입니다.

배포 민첩성을 촉진를 계속 하려면 이러한 도구는 다양 한 개발 및 CI/CD 솔루션으로 컨테이너 작업에 대 한 뛰어난 dev 테스트-에-프로덕션에 배포 환경을 제공 합니다.

그림 4-12 Kubernetes 클러스터 컨테이너 서비스를 Azure에 배포 하는 연속 배포 파이프라인을 보여 줍니다.

![Visual Studio Team Services 연속 배포 파이프라인을 Kubernetes 클러스터에 배포](./media/image12.png)

> **그림 4-12입니다.** Visual Studio Team Services 연속 배포 파이프라인을 Kubernetes 클러스터에 배포

>[!div class="step-by-step"]
[이전](modernize-your-apps-with-monitoring-and-telemetry.md)
[다음](migrate-to-hybrid-cloud-scenarios.md)
