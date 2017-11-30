---
title: "Docker 응용 프로그램에 대 한 외부 루프 DevOps 워크플로의 단계"
description: "Microsoft 플랫폼 및 도구와 Docker 컨테이너 화 된 응용 프로그램 수명 주기"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 070d174cde9e80f542865f5617b1c702a07a8018
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="steps-in-the-outer-loop-devops-workflow-for-a-docker-application"></a>Docker 응용 프로그램에 대 한 외부 루프 DevOps 워크플로의 단계

그림 5-1 DevOps 외부 반복 워크플로 구성 하는 단계는 종단 간 솔루션 내의 표시 합니다.

![](./media/image1.png)

Microsoft 도구와 함께 Docker 응용 프로그램에 대 한 그림 5-1: DevOps 외부 루프 워크플로

이제 이러한 각 단계를 더 자세히 살펴보겠습니다.

## <a name="step-1-inner-loop-development-workflow"></a>1 단계: 내부 루프 개발 워크플로

이 단계 4 장에에서 자세히 설명 되어 있지만 재생을 위해 다음은 여기서 외부 루프 시작 되는 순간을 개발자 푸시 CI 파이프라인 동작 시작 코드를 소스 제어 관리 시스템 (예: Git).

## <a name="step-2-source-code-control-integration-and-management-with-visual-studio-team-services-and-git"></a>2 단계: 소스 코드 제어 통합 및 Visual Studio Team Services 및 Git를 사용 하 여 관리

이 단계에서 통합 된 버전의 팀에서 다른 개발자 로부터 들어오는 모든 코드를 수집 하기 위해 버전 제어 시스템을 지정 해야 합니다.

소스 코드 제어 (SCC) 및 소스 코드 관리에 대부분의 개발자는 DevOps 수명에서 Docker 응용 프로그램을 만들 때 주기 많습니다 것 처럼 보일 수, 하는 경우에이 응용 프로그램을 사용 하 여 Docker 이미지를 제출 하지 해야 강조 하기 위해 중요 레지스트리를 직접 전역 Docker (예: Azure 컨테이너 레지스트리 또는 Docker 허브)에서 개발자의 컴퓨터. 반대로 Docker 이미지를 해제 하 고 프로덕션 환경에 배포 글로벌 빌드 또는 소스 코드 리포지토리에 (예: Git)에 따라 CI 파이프라인에 통합 되는 소스 코드에만 전적으로 만들 수 해야 합니다.

자체는 개발자가 생성 되는 로컬 이미지 자신의 컴퓨터 내에서 테스트할 때 개발자가 여는 것 같습니다. 이 때문에를 SCC 코드에서 활성화 DevOps 파이프라인에 있는 것이 중요 합니다.

Visual Studio Team Services 및 Team Foundation Server Git 및 Team Foundation 버전 제어를 지원합니다. 서로 선택할 수 있으며 Microsoft 종단 간 환경을 사용 합니다. 그러나도 관리할 수 있습니다 (예: GitHub, 온-프레미스 Git 리포지토리 또는 Subversion) 외부 저장소에서 코드 고에 연결 하 고 DevOps CI 파이프라인에 대 한 시작 점으로 코드를 가져올 수 있습니다.

## <a name="step-3-build-ci-integrate-and-test-with-visual-studio-team-services-and-docker"></a>3 단계: 빌드, CI를 통합 하 고 Visual Studio Team Services 및 Docker와 테스트

CI 최신 소프트웨어 테스트 및 배달에 대 한 표준으로 나타났습니다. Docker 솔루션 개발 및 운영 팀 간의 문제를 명확 하 게 분리 유지 관리합니다. Docker 이미지의 불변성 개발, CI를 통해 테스트 및 프로덕션 환경에서 실행에 어떤 간의 반복 가능한 배포가 보장 합니다. Docker 엔진 개발자 랩톱에서 배포 하 고 테스트 인프라 컨테이너 이식 가능한 환경에 걸쳐.

이 시점에서 제출 올바른 코드 버전 제어 시스템을 설정한 후 필요한는 *빌드 서비스* 에 코드를 선택 하 고 글로벌 빌드 및 테스트를 실행 합니다.

이 단계 (CI 빌드, 테스트)에 대 한 내부 워크플로 빌드 (Visual Studio Team Services) 서버에, Docker 엔진 및 Docker 레지스트리 코드 리포지토리에 (Git, 등)로 구성 된 CI 파이프라인의 구성에 관한는입니다.

사용할 수 있습니다 Visual Studio Team Services의 기반으로 하 고 작성 된 "아티팩트"를 게시 하기 위한 응용 프로그램을 빌드하고 CI 파이프라인을 설정 하기 위한 "아티팩트 저장소에," 다음 단계에 설명 된.

"최종 아티팩트" 배포에 대 한 Docker를 사용 하는 경우 배포할 응용 프로그램 또는 서비스를 사용 하 여 Docker 이미지에 포함 된 해당 합니다. 이러한 이미지는 푸시하거나에 게시 한 *Docker 레지스트리* (공식 기본 이미지에 일반적으로 사용 되는 Docker 허브 레지스트리 같은 공용 하나 또는 Azure 컨테이너 레지스트리에 있는 수와 같은 개인 리포지토리에).

여기에 기본적으로 개념: CI 파이프라인 시작-으로 해제 Git 같은 SCC 저장소에 커밋 됩니다. 그림 5-2를 보여 주는 것 처럼 커밋 Docker 컨테이너 내에서 빌드 작업을 실행 하 고 해당 작업을 성공적으로 완료 되 면 Docker 이미지를 Docker 레지스트리를 강제 하려면 Visual Studio Team Services를 발생 합니다.

![](./media/image2.png)

그림 5-2: 관련 된 단계 CI

Docker 및 Visual Studio Team Services를 사용 하 여 기본 CI 워크플로 단계는 다음과 같습니다.

1.  개발자는 커밋 SCC 저장소 (Git/Visual Studio Team Services, GitHub, 등)에 푸시합니다.

2.  Visual Studio Team Services 또는 Git을 사용 하는 경우 CI 내장 되어 하기만 하면 Visual Studio Team Services에서 확인란을 선택 하는 합니다. 외부 SCC (예: GitHub에서)를 사용 하 여 한 *webhook* 업데이트의 Visual Studio Team Services 또는 Git/GitHub를 강제 합니다.

3.  Visual Studio Team Services에는 이미지 뿐만 아니라 응용 프로그램 및 테스트 코드를 설명 하는 DockerFile을 포함 하 여 SCC 저장소를 끌어옵니다.

4.  Visual Studio Team Services에는 Docker 이미지를 빌드하고 빌드 번호 레이블 합니다.

5.  Visual Studio Team Services를 프로 비전 된 Docker 호스트 내에서 Docker 컨테이너 인스턴스화하고 적절 한 테스트를 실행 합니다.

6.  테스트가 성공 하면 이미지는 먼저 레이블 재지정 된 의미 있는 이름에는 "축복 받은 빌드" 알 수 있도록 (같은 "/ 1.0.0" 또는 다른 레이블), 다음 푸시됩니다. Docker 레지스트리 (Docker 허브, Azure 컨테이너 레지스트리, DTR 등) 하 고

### <a name="implementing-the-ci-pipeline-with-visual-studio-team-services-and-the-docker-extension-for-visual-studio-team-services"></a>Visual Studio Team Services에 대 한 Visual Studio Team Services와 Docker 확장이 포함 된 CI 파이프라인 구현

[Visual Studio Team Services Docker 확장](https://aka.ms/vstsdockerextension) CI 파이프라인은 Docker 이미지를 작성, 인증 된 Docker 레지스트리에 Docker 이미지를 푸시, Docker 이미지를 실행 하거나 실행할 수 있습니다 제공 하는 다른 작업에 작업을 추가 Docker CLI 합니다. 또한 Docker Compose를 빌드, 푸시 및 multicontainer Docker 응용 프로그램을 실행 또는 그림 5-3에 나와 있는 것 처럼 Docker 작성 CLI 제공 하는 다른 작업을 실행 하는 데 사용할 수 있는 작업을 추가 합니다.

![](./media/image3.png)

그림 5-3: Visual Studio Team Services에서 Docker CI 파이프라인

Docker 확장 서비스 끝점을 사용 하 여 Docker 호스트에 대 한 컨테이너 또는 이미지 레지스트리 수 있습니다. 작업 기본적으로 (이 현재는 사용자 지정 Visual Studio Team Services 에이전트 필요); 사용 가능한 경우 로컬 Docker 호스트를 사용 합니다. 그렇지 Docker 호스트 연결을 제공 해야 합니다. 같은 이미지를 푸시하는 Docker 레지스트리로 인증 하 고에 종속 된 작업을 제공 하는 Docker 레지스트리 연결 해야 합니다.

Visual Studio Team Services 계정에 다음 구성 요소를 설치 하는 Visual Studio Team Services Docker 확장 합니다.

-   Docker 레지스트리에 연결에 대 한 서비스 끝점

-   Docker 컨테이너 호스트에 연결 하기 위한 서비스 끝점

-   다음을 수행 하는 Docker 작업:

-   이미지 만들기

-   레지스트리에 이미지 또는 리포지토리 푸시

-   이미지는 컨테이너에서 실행

-   Docker 명령 실행

-   Docker Compose 명령을 실행 하는 Docker Compose 작업

이러한 Visual Studio Team Services 작업 빌드 Linux Docker 호스트/v M Azure에서 프로 비전 및 기본 Docker 레지스트리 (Azure 컨테이너 레지스트리, Docker 허브, 개인 Docker DTR 또는 다른 Docker 레지스트리) Docker CI 파이프라인을 어셈블할 수 있습니다는 매우 일관 된 방법입니다.

***요구 사항:***

-   Visual Studio Team Services 또는 Team Foundation Server 2015 업데이트 3 이상을 온-프레미스 설치 합니다.

-   Docker 이진 파일에 있는 Visual Studio Team Services 에이전트입니다.

다음 중 하나를 만드는 쉽게 Visual Studio Team Services 에이전트 Docker 이미지를 기반으로 컨테이너를 실행 하려면 Docker를 사용 하는 것입니다.

**자세한 내용은** 파이프라인와 연습을 보려면 다음 사이트를 방문 하십시오. Visual Studio Team Services Docker CI 어셈블하는 방법에 대 한 자세한를 읽으려면:

Docker 컨테이너와 Visual Studio Team Services 에이전트를 실행: [https://hub.docker.com/r/ \ 에이전트에서 microsoft/vsts /](https://hub.docker.com/r/microsoft/vsts-agent/)

VSTS Docker 확장: <https://aka.ms/vstsdockerextension>

Visual Studio Team Services를 사용 하 여.NET Core Linux Docker 이미지를 구축: <https://blogs.msdn.microsoft.com/stevelasker/2016/06/13/building-net-core-linux-docker-images-with-visual-studio-team-services/>

Docker 지 원하는 컴퓨터를 빌드 Visual Studio 팀 Linux 기반 서비스 빌드: <http://donovanbrown.com/post/2016/06/03/Building-a-Linux-Based-Visual-Studio-Team-Service-Build-Machine-with-Docker-Support>

### <a name="integrate-test-and-validate-multicontainer-docker-applications"></a>통합, 테스트 및 multicontainer Docker 응용 프로그램의 유효성을 검사합니다

일반적으로 대부분의 Docker 응용 프로그램은 단일 컨테이너 대신 여러 컨테이너도 구성 됩니다. 좋은 예 해야 마이크로 서비스 당 하나의 컨테이너 microservices 지향 응용 프로그램입니다. 그러나 microservices 접근 방식을 패턴을 엄격 하 게 수행 하지 않고도 매우 예상 Docker 응용 프로그램이 여러 컨테이너 또는 서비스의 구성 된 것입니다.

따라서 CI 파이프라인에서 응용 프로그램 컨테이너를 빌드한 후도 해야 배포, 통합 및 모든 해당 컨테이너 통합 Docker 호스트 내에서 나 사용자 컨테이너에는 테스트 클러스터에도 전체 응용 프로그램 테스트 배포 됩니다.

단일 호스트를 사용 하 여 docker 같은 Docker 명령을 사용할 수 있습니다-을 빌드 및 배포는 단일 VM에서 Docker 환경 ֲ 관련된 컨테이너를 구성 합니다. 하지만 orchestrator 클러스터 DC/OS, Kubernetes, docker는 Docker Swarm 등을 사용 하는 경우 orchestrator 선택한 클러스터/스케줄러에 따라 또는 다른 메커니즘을 통해 프로그램 컨테이너를 배포 해야 합니다.

다음은 몇 가지 종류의 Docker 컨테이너에 대해 실행할 수 있는 테스트.

-   Docker 컨테이너에 대 한 단위 테스트

-   서로 관련 된 응용 프로그램 또는 microservices 테스트 그룹

-   프로덕션 서버와 "카나리아" 릴리스에서 테스트

중요 한 점은 통합 및 기능 테스트를 실행할 때 컨테이너의 외부에서 이러한 테스트 실행 해야 합니다. 테스트를 정의 고 컨테이너는 프로덕션 환경에 배포 하는 동일 해야 하는 정적 이미지를 기반으로 하므로, 배포 하는 컨테이너 안에서 실행 될 해야 합니다.

여러 클러스터 (클러스터, 클러스터 준비 및 프로덕션 클러스터 테스트)를 테스트와 같은 더 고급 시나리오를 테스트할 때 매우 사용할 수 없는 옵션인 다양 한 클러스터에서 테스트 하는 레지스트리를 이미지를 게시 하는 것입니다.

### <a name="push-the-custom-application-docker-image-into-your-global-docker-registry"></a>사용자 지정 응용 프로그램 Docker 이미지 글로벌 Docker 레지스트리 푸시

Docker 이미지를 테스트 하 고 유효성을 검사 한 후에 태그 및 Docker 레지스트리에 게시을 하려고 합니다. Docker 레지스트리 QA 및 프로덕션 환경에 배포 하 여 사용자 지정 테스트 (즉, "축복 받은 이미지")을 저장 하는 중심적인 곳 이므로 Docker 응용 프로그램 수명 주기에서 중요 한 부분을는.

Docker 레지스트리는 프로그램 "source of truth" QA 또는 프로덕션 환경에 배포할 응용 프로그램 이진 또는 비트에 대 한 방법을 SCC 리포지토리에 (Git, 등)에 저장 된 응용 프로그램 코드는 "소스 of truth" 비슷합니다.

일반적으로 있습니다 (예: 제한 된 액세스로 공용 클라우드 레지스트리 또는 Azure 컨테이너 레지스트리 또는 Docker Trusted Registry와 같은 온-프레미스 레지스트리는 사용자 지정 이미지에 대 한 개인 저장소에 개인 저장소에서 해야 할 수 있습니다. Docker 허브) 오픈 소스 코드가 경우 마지막 액세스 위반은 하지만에 공급 업체의 보안을 신뢰 해야 합니다. 어떤 방법을 사용 하는 기준인이 작업을 수행 방법은 매우 유사 하 고 궁극적으로 docker push 명령에 따라 그림 5-4에 표시 된 것 처럼 합니다.

![](./media/image4.png)

그림 5-4: 사용자 지정 이미지를 Docker 레지스트리에 게시

Azure 컨테이너 레지스트리, Amazon 웹 서비스 컨테이너 레지스트리, Google 컨테이너 레지스트리, Quay 레지스트리 등 클라우드 공급 업체에서 Docker 레지스트리의의 여러 제공 있습니다.

Visual Studio Team Services Docker 확장을 사용 하 여 그림 5-5와 같이 이미지는 인증 된 Docker 레지스트리 (예: Azure 컨테이너 레지스트리)에 여러 태그와 docker compose.yml 파일에 정의 된 서비스의 집합을 푸시할 수 있습니다.

![](./media/image5.png)

그림 5-5: Visual Studio Team Services Docker 레지스트리에 게시 사용자 지정 이미지를 사용 하 여

**자세한 내용은** 자세한 내용을 알아보려면 Visual Studio Team Services에 대 한 Docker 확장 프로그램에 대 한 <https://aka.ms/vstsdockerextension>합니다. Azure 컨테이너 레지스트리에 대 한 자세한 내용은 이동 <https://aka.ms/azurecontainerregistry>합니다.

## <a name="step-4-cd-deploy"></a>4 단계: CD, 배포

Docker 이미지의 불변성 개발, CI를 통해 테스트 및 프로덕션 환경에서 실행에 어떤 반복 가능한 배포가 보장 합니다. 응용 프로그램 Docker 이미지를 Docker 레지스트리 (개인 또는 공용)에서 게시를 설정한 후 발생할 수 있는 여러 환경에 배포할 수 있습니다 (프로덕션, QA, 스테이징 등)에서 Visual Studio Team Services를 사용 하 여 CD 파이프라인 파이프라인 작업이 나 Visual Studio Team Services 릴리스 관리 합니다.

그러나이 시점에서 종속 배포 Docker 응용 프로그램의 종류에 있습니다. 간단한 응용 프로그램에 배포 (구성 및 배포의 관점에서)는 모놀리식 같은 몇 가지 컨테이너 또는 서비스를 구성 하는 응용 프로그램 및 배포 된 몇 가지 서버 또는 Vm 간에 차이가 있는 매우와 같은 보다 복잡 한 응용 프로그램 배포는 microservices 지향 응용 프로그램 대규모 기능을 사용 합니다. 이러한 두 가지 시나리오는 다음 섹션에 설명 되어 있습니다.

### <a name="deploying-composed-docker-applications-to-multiple-docker-environments"></a>구성 된 여러 Docker 환경에 Docker 응용 프로그램 배포

덜 복잡 한 시나리오에서 첫 번째 하는지 살펴보겠습니다: 단일 환경 또는 여러 환경에서 간단한 Docker 호스트 (Vm 또는 서버)를 배포 (QA, 스테이징 및 프로덕션). 이 시나리오에서는 내부적으로 CD 파이프라인 צ ְ ײ docker-그림 5-6에 설명 된 대로 컨테이너 또는 서비스의 관련된 집합으로 Docker 응용 프로그램을 배포 (Visual Studio Team Services 배포 작업)에서 작성 합니다.

![](./media/image6.png)

그림 5-6: 간단 하 게 Docker 호스트 환경 레지스트리를 응용 프로그램 컨테이너 배포

그림 5-7 작업 추가 대화 상자에서 Docker Compose를 클릭 하 여 Visual Studio Team Services를 통해 QA/테스트 환경에 빌드 CI를 연결할 수는 어떻게 강조 표시 합니다. 그러나,을 스테이징 또는 프로덕션 환경에 배포할 때는 일반적으로 사용 환경이 여러 개를 처리 하는 릴리스 관리 기능 (같은 QA, 스테이징 및 프로덕션). Visual Studio Team Services를 사용 하는 단일 Docker 호스트에 배포할 경우 작업 "Docker Compose" (docker를 호출 하는 것입니다-내부에서 명령을 작성). Azure 컨테이너 서비스를 배포 하는 경우 다음 섹션에 설명 된 대로 Docker 배포 태스크를 사용 합니다.

![](./media/image7.png)

그림 5-7: Visual Studio Team Services 파이프라인에서 Docker Compose 태스크 추가

Visual Studio Team Services에서 릴리스를 만들 때에 입력된 아티팩트는 집합을 사용 합니다. 이러한 작업은 여러 환경에 걸쳐 릴리스의 수명 주기 동안 변경할 수 없어야 하는 데 사용 됩니다. 컨테이너를 사용할 때 입력된 아티팩트를 배포 하는 레지스트리에서 이미지를 식별 합니다. 를 확인 방법에 따라 docker-compose 파일에서 "myimage:latest"를 참조 하는 경우 되 고 가장 뚜렷한 사례는 릴리스 기간 동안 동일 하 게 보장 되지 않습니다.

Visual Studio Team Services에 대 한 Docker 확장을 제공 특정 레지스트리 이미지를 포함 하는 빌드 아티팩트를 생성 하는 기능 다이제스트 고유 하 게 식별 하는 이미지를 이진 보장 합니다. 실제로 필요한 것 릴리스에 대 한 입력으로 사용 하는 것이 이들은입니다.

### <a name="managing-releases-to-docker-environments-by-using-visual-studio-team-services-release-management"></a>Visual Studio Team Services Release Management를 사용 하 여 Docker 환경에는 릴리스 관리

Visual Studio Team Services 확장 프로그램을 통해 있습니다 수 새 이미지를 작성, Docker 레지스트리에 게시, Linux 또는 Windows 호스트에서 실행 및 docker와 같은 명령을 사용 하 여-시각적 개체를 통해 전체 응용 프로그램으로 여러 컨테이너를 배포 하도록 구성 Studio Team Services 릴리스 관리 기능을 그림 5-8에 나와 있는 것 처럼 여러 환경을 위한 것입니다.

![](./media/image8.png)

그림 5-8: Visual Studio Team Services Release Management에서 Visual Studio Team Services Docker Compose 작업 구성

하지만 그림 5-6을 표시 하 고 그림 5-8을 구현 하는 시나리오 (단순 Docker 호스트 및 Vm을 배포 하는 및 단일 컨테이너 또는 이미지 당 인스턴스 됩니다) 상당히 기본적 이며 아마도 sc 개발 또는 테스트에 대해서만 사용할 수 해야 염두에서에 둬야 enarios 합니다. 대부분의 엔터프라이즈 프로덕션 시나리오에서는 HA (고가용성)를 포함 하려고는 및에 걸쳐 부하 분산 여러 노드, 서버 및 Vm의 경우와 "지능형 장애 조치" 하므로 하는 경우 서버 또는 노드도 관리 하기 쉬운 확장성에 실패 하면 해당 서비스 및 컨테이너를 다른 호스트 서버 또는 VM으로 이동 됩니다. 이 경우 컨테이너 클러스터, orchestrators, 및 스케줄러와 같은 고급 기술이 필요 합니다. 따라서 해당 클러스터에 배포 하는 방법은 다음 섹션에서 설명 하는 고급 시나리오를 통해 정확 하 게는 합니다.

### <a name="deploying-complex-docker-applications-to-docker-clusters-dcos-kubernetes-and-docker-swarm"></a>Docker 클러스터 (DC/OS, Kubernetes, 및 docker는 Docker Swarm)에 복잡 한 Docker 응용 프로그램 배포

분산된 응용 프로그램의 특성에는 또한 배포 되는 계산 리소스가 필요 합니다. 풀링된 리소스를 기준으로 한 HA 및 프로덕션 규모 기능이 하려면 클러스터링 높은 확장성을 제공 하는 기능을 합니다.

Docker는 Docker Swarm 같은 CLI 도구에서 위에 해당 클러스터에 컨테이너를 수동으로 배포할 수 있습니다 (사용과 같은 [docker 서비스를 만들](https://docs.docker.com/engine/swarm/swarm-tutorial/deploy-service/)) 또는 웹 UI와 같은 [Mesosphere 마라톤](https://mesosphere.github.io/marathon/docs/marathon-ui.html) DC/OS 용 클러스터에 있지만 해야 확장 또는 모니터링을 위해 관리 목적으로 또는 punctual 배포 테스트에 있는 예약 합니다.

CD의 관점 및 Visual Studio Team Services에서 특히에서 실행할 수 있습니다 특수 처리 된 배포 작업 분산 클러스터에 컨테이너 화 된 응용 프로그램 배포는 Visual Studio Team Services 릴리스 관리 환경 그림 5-9와 같이 컨테이너 서비스입니다.

![](./media/image9.png)

그림 5-9: 컨테이너 서비스에 분산된 된 응용 프로그램 배포

처음에 특정 클러스터 또는 orchestrators을 배포할 때는 일반적으로 사용 합니다 (즉, Mesosphere DC/OS 또는 Docker 및 Docker 보다 다양 한 배포 메커니즘이 Kubernetes 각 orchestrator 당 메커니즘과 특정 배포 스크립트 대신 swarm)는 간단 하 고 사용 하기 쉬운 docker-작성 도구 docker compose.yml 정의 파일에 기반 합니다. 그러나 Microsoft Visual Studio Team Services Docker를 배포 하는 작업을 그림 5-10에서 표시 된 덕분에 하면 이제도를 배포할 수 DC/OS Microsoft 드립니다 "변환"을 수행 하기 때문에 친숙 한 docker compose.yml 파일 사용 하 여 (에서 프로그램 docker compose.yml 파일 DC/OS에 필요한 다른 형식으로).

![](./media/image10.png)

그림 5-10: 환경 RM에 Docker 배포 태스크 추가

그림 5-11 편집 Docker 배포 작업 대상 유형 (Azure 컨테이너 서비스 DC/OS,이 경우), Docker 구성 파일 및 Docker 레지스트리 연결 (예: Azure 컨테이너 레지스트리 또는 Docker 허브)를 지정 하는 방법을 보여 줍니다. 이 작업 DC/OS 클러스터의 컨테이너 형태로 배포할 수를 즉시 사용할 사용자 지정 Docker 이미지를 검색 합니다.

![](./media/image11.png)

그림 5-11: Docker 배포 작업 정의 배포 하려면 Azure 컨테이너 서비스 DC/OS

**자세한 내용은** 자세한 내용은 Visual Studio Team Services 및 Docker와 CD 파이프라인에 대 한 다음 사이트를 방문 하십시오.:

Docker 및 Azure 컨테이너 서비스에 대 한 visual Studio Team Services 확장: [https://aka.ms/ \ vstsdockerextension](https://aka.ms/vstsdockerextension)

Azure 컨테이너 서비스: <https://aka.ms/azurecontainerservice>

Mesosphere DC/OS: <https://mesosphere.com/product/>

## <a name="step-5-run-and-manage"></a>5 단계: 실행 및 관리

실행 및 응용 프로그램을 관리 하기 때문에 엔터프라이즈 프로덕션에서 수준이 고 언어에서는 자체의 형식 작업으로 인해 주요 대상은 고이 영역의 큰 범위 뿐만 아니라 해당 수준 (IT 작업)에서 작업 하는 사람들 우리는 할당 되어 전체 다음 장 것에 대해 설명 합니다.

## <a name="step-6-monitor-and-diagnose"></a>6 단계: 모니터링 및 진단

이 항목 또한에 대해서는 다음 장에서 IT 운영; 프로덕션 시스템에서 수행 하는 작업의 일부로 그러나는이 단계에서 얻은 insights 응용 프로그램은 지속적으로 개선 하는 개발 팀에 다시 피드 해야 강조 표시 해야 합니다. 그의 관점에서 일부 이기도 하므로 DevOps의 작업 및 작업에서 일반적으로 수행 되지만 IT 합니다.

모니터링 및 진단이 100 %DevOps 영역 내에서 경우에 모니터링 하는 프로세스와 테스트 또는 베타 환경에 대 한 개발 팀에서 수행 하는 분석 됩니다. 이 부하 테스트를 수행 하 여 또는 베타 또는 QA 환경에 베타 테스터에서 새 버전을 시도 하는 위치를 모니터링 하 여 수행 됩니다.

>[!div class="step-by-step"]
[이전] [다음]을 (index.md) (... /run-manage-monitor-docker-environments/index.md)
