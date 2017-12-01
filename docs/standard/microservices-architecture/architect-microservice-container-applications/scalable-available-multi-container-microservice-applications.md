---
title: "Microservices 및 높은 확장성 및 가용성을 위한 다중 컨테이너 응용 프로그램 오케스트레이션"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | Microservices 및 높은 확장성 및 가용성을 위한 다중 컨테이너 응용 프로그램 오케스트레이션"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: ec33901a0ddc9e5b58263440b0e4399e687c6904
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="orchestrating-microservices-and-multi-container-applications-for-high-scalability-and-availability"></a>Microservices 및 높은 확장성 및 가용성을 위한 다중 컨테이너 응용 프로그램 오케스트레이션

프로덕션에 사용 가능한 응용 프로그램에 대 한 orchestrators를 사용 하 여이 응용 프로그램에 microservices 기반 또는 단순히 여러 컨테이너에서 분할 하는 경우 중요 합니다. 마이크로 서비스 기반 접근 방식에서 이전에 도입 된 각 마이크로 서비스 소유 하 고 해당 모델 및 데이터 하는 개발 및 배포 측면 자치 됩니다. 그러나는 보다 일반적인 응용 프로그램으로 구성 된 여러 서비스 (예: SOA)의 경우에는 또한 여러 컨테이너 또는 분산된 시스템으로 배포 되어야 하는 단일 비즈니스 응용 프로그램을 구성 하는 서비스. 이러한 종류의 시스템은 확장성 및 관리; 복잡 따라서 있습니다 반드시 사용할 필요는 orchestrator 프로덕션 지원 하 고 확장 가능한 다중 컨테이너 응용 프로그램을 포함 하려는 경우.

그림 4-23 여러 microservices (컨테이너)의 구성 된 응용 프로그램의 클러스터로 배포를 보여 줍니다.

![](./media/image23.PNG)

**그림 4-23**합니다. 컨테이너의 클러스터

논리적인 접근법 모양입니다. 하지만 응용 프로그램 구성 어떻게 처리 부하 분산, 라우팅 및 이러한 조정 입니까?

하나의 호스트에서 단일 이미지 인스턴스를 관리 요구를 충족 하는 단일 Docker 호스트의 일반 Docker 엔진 하 하지만 더 복잡 한 분산된 응용 프로그램에 대 한 여러 호스트에 배포 된 여러 컨테이너를 관리 하는 데 있어 짧은 대체 됩니다. 대부분의 경우에서 자동으로 시작 컨테이너 이미지에 여러 개의 인스턴스를 사용 하 여 확장 컨테이너, 일시 중단 하거나 필요한 경우를 종료 되며 이상적으로 네트워크 및 데이터와 같은 리소스에 액세스 하는 방식 또한 제어 하는 관리 플랫폼 필요 저장소입니다.

개별 컨테이너 또는 매우 간단한 구성 된 앱 및 microservices 있는 대규모 엔터프라이즈 응용 프로그램의 이동 관리 외에 오케스트레이션 및 플랫폼 클러스터링을 설정 해야 합니다.

아키텍처 및 개발 관점에서 대기업 microservices 기반 응용 프로그램을 구성을 작성 하는 경우 이기 플랫폼 आ स ा 고급 시나리오를 지 원하는 제품을 이해 하는 것이 중요 합니다.

**클러스터 및 orchestrators**합니다. 중지 해야 많은 Docker 호스트에 응용 프로그램 확장은를 기본 플랫폼의 복잡성을 추상화 하 여 모든 호스트를 단일 클러스터로 관리할 수 있도록에 중요 한 경우 큰 마이크로 서비스 기반 응용 프로그램입니다. 컨테이너 클러스터와 orchestrators 제공 기능입니다. Orchestrators에는 Azure 서비스 패브릭, Kubernetes, docker는 Docker Swarm 및 Mesosphere DC/OS이 있습니다. 마지막 세 오픈 소스 orchestrators Azure 컨테이너 서비스를 통해 Azure에서 사용할 수 있는 합니다.

**스케줄러**합니다. *예약* 게도 UI를 제공 하는 클러스터의 컨테이너를 시작 하려면 관리자에 대 한 기능을 의미 합니다. 클러스터 스케줄러는 여러 가지 역할: 클러스터의 리소스를 효율적으로 사용 하려면, 노드 또는 호스트 간에 부하를 분산 컨테이너와 효율적으로 사용자가 제공한 제약 조건을 설정 및 높음 제공 하는 동안 오류에 대해 강력한 수 가용성입니다.

클러스터 및 스케줄러의 개념 없으므로 두 가지 기능을 제공 하는 종종 다른 공급 업체에서 제공 하는 제품 관련 밀접 하 게 됩니다. 다음 목록에는 가장 중요 한 플랫폼 및 클러스터 및 스케줄러에 대 한 소프트웨어 선택 표시 됩니다. 이러한 orchestrators Azure와 같은 공용 클라우드에 일반적으로 제공 됩니다.

## <a name="software-platforms-for-container-clustering-orchestration-and-scheduling"></a>클러스터링 컨테이너, 오케스트레이션 및 예약에 대 한 소프트웨어 플랫폼

Kubernetes

![https://pbs.twimg.com/media/Bt\_pEfqCAAAiVyz.png](./media/image24.png)

> Kubernetes는 클러스터 인프라 및 컨테이너 조정 기능을 예약 하는 기능을 제공 하는 오픈 소스 제품입니다. 호스트 클러스터 간에 배포, 배율 및 응용 프로그램 컨테이너의 작업을 자동화할 수 있습니다.
>
> Kubernetes는 컨테이너 응용 프로그램을 쉽게 관리 및 검색에 대 한 논리 단위로 그룹화 하는 컨테이너 중심 인프라를 제공 합니다.
>
> Kubernetes linux, Windows에서 덜 완성도 높은 완성도 높은입니다.

Docker 웜

![http://rancher.com/wp-content/themes/rancher-2016/assets/images/swarm.png?v=2016-07-10-am](./media/image25.png)

> Docker 웜을 사용 하 여 클러스터 및 Docker 컨테이너를 예약할 수 있습니다. 웜을 사용 하 여 단일, 가상 Docker 호스트에 Docker 호스트의 풀을 설정할 수 있습니다. 클라이언트는 호스트는 웜 쉽게 여러 호스트 조정을 응용 프로그램에 대 한 의미를 위한 것 같은 방식으로 Swarm을 API 요청을 만들 수 있습니다.
>
> Docker 웜은 동시에 회사에서 제품입니다.
>
> Docker v1.12 하거나 네이티브 및 기본 제공 Swarm 모드 나중에 실행할 수 있습니다.

Mesosphere DC/OS

![https://mesosphere.com/wp-content/uploads/2016/04/logo-horizontal-styled.png](./media/image26.png)

> Mesosphere 엔터프라이즈 DC/OS (Apache Mesos에 기반)는 컨테이너 및 분산된 응용 프로그램을 실행 하기 위한 프로덕션에 사용 가능한 플랫폼입니다.
>
> DC/OS 클러스터에서 사용할 수 있는 리소스의 컬렉션을 추상화 하 고 해당 리소스를 기반으로 하는 구성 요소를 사용할 수 있도록 하 여 작동 합니다. 풀 마라톤 DC/운영 체제와 통합 하는 스케줄러로 일반적으로 사용 됩니다.
>
> DC/OS는 linux, Windows에서 덜 완성도 높은 완성도 높은입니다.

Azure 서비스 패브릭

![https://azure.microsoft.com/svghandler/service-fabric?width=600&height=315](./media/image27.png)

> [서비스 패브릭](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) 는 응용 프로그램을 빌드하기 위한 Microsoft microservices 플랫폼입니다. 한 [orchestrator](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction) 의 서비스를 컴퓨터의 클러스터를 만듭니다. 서비스 패브릭 컨테이너로 또는 일반 프로세스로 서비스를 배포할 수 있습니다. 도 혼합 프로세스의 서비스를 컨테이너 내에서 동일한 응용 프로그램 및 클러스터의에서 서비스와 수 있습니다.
>
> 서비스 패브릭 추가 및 선택적 제공 규범적인 [프로그래밍 모델 서비스 패브릭 ](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework) 같은 [상태 저장 서비스](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) 및 [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction)합니다.
>
> Windows (Windows에서 진화 years)에서 완성 된 덜 Linux에서 서비스 패브릭은 성숙한입니다. 
> Linux 및 Windows 컨테이너는 2017 이후 서비스 패브릭에서 지원 됩니다.

## <a name="using-container-based-orchestrators-in-microsoft-azure"></a>Microsoft Azure에서 컨테이너 기반 orchestrators를 사용 하 여

여러 클라우드 공급 업체는 Docker 컨테이너 지원 함께 Docker 클러스터 및 Microsoft Azure, Amazon EC2 컨테이너 서비스 및 Google 컨테이너 엔진 등의 오케스트레이션 지원을 제공 합니다. Microsoft Azure는 다음 섹션에 설명 된 대로 클러스터 및 orchestrator 지원을 통해 Azure 컨테이너 서비스 (ACS), Docker를 제공 합니다.

다른 선택 Microsoft Azure 서비스 패브릭 (microservices 플랫폼)도 Docker를 기반으로 Linux 및 Windows 컨테이너를 지원 하를 사용 하는 것입니다. 서비스 패브릭 다른 클라우드 또는 Azure에서 실행 되 고도 실행 [온-프레미스](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere)합니다.

## <a name="using-azure-container-service"></a>Azure 컨테이너 서비스를 사용 하 여

Docker 클러스터 여러 Docker 호스트를 풀링 하 고는 단일 가상 Docker 호스트에 노출 하는 클러스터에 여러 컨테이너를 배포할 수 있습니다. 클러스터는 확장성, 상태, 등과 같은 모든 복잡 한 관리 작업으로 처리 합니다. 그림 4-24 구성 된 응용 프로그램에 대 한 Docker 클러스터에 Azure 컨테이너 서비스 (ACS)를 매핑하는 방식을 나타냅니다.

ACS를 생성, 구성 및 클러스터 화 된 응용 프로그램을 실행 하는 미리 구성 된 가상 컴퓨터의 관리를 단순화 하는 방법을 제공 합니다. 인기 있는 오픈 소스 일정 예약 및 오케스트레이션 도구는 최적화 된 구성을 사용 하 여, ACS 하면 사용자의 기존 기술을 사용 하거나 커뮤니티 전문성을 배포 하 고 Microsoft Azure에서 컨테이너 기반 응용 프로그램 관리의 크기가 크고 점점 본문에 그리기 .

Azure 컨테이너 서비스를 Azure에 맞게 인기 있는 오픈 소스 도구를 클러스터링 하는 Docker 및 기술 구성을 최적화합니다. 사용자 컨테이너와 응용 프로그램 구성에 대 한 이식성을 제공 하는 열린 솔루션 가져오기 Orchestrator 도구, 호스트, 수 및 크기를 선택 하 고 다른 모든 항목을 처리 하는 컨테이너 서비스 키를 누릅니다.

![](./media/image28.png)

**그림 4-24**합니다. Azure 컨테이너 서비스에서 선택할 수 있는 클러스터링

ACS 응용 프로그램 컨테이너가 완전히 이식 가능 인지 확인 하는 Docker 이미지를 활용 합니다. 선택 하는 DC/OS (Apache Mesos 기반의), (처음 만든 Google에서) Kubernetes 및 docker는 Docker Swarm와 같은 오픈 소스 오케스트레이션 플랫폼 이러한 응용 프로그램 아니면 수천 또는 심지어 수만 컨테이너의 배율을 조정할 수 있도록 지원 합니다.

Azure 컨테이너 서비스를 사용 하면 오케스트레이션 계층에 포함 하 여 응용 프로그램 이식성을 유지 하면서 Azure의 엔터프라이즈급 기능을 활용할 수 있습니다.

![](./media/image29.png)

**그림 4-25**합니다. ACS에서 orchestrators

그림 4-25와 같이 Azure 컨테이너 서비스는 Azure에서 DC/OS, Kubernetes 또는 docker는 Docker Swarm을 배포 하기 위해 제공 하는 인프라 단순히 하지만 ACS 모든 추가 orchestrator를 구현 하지 않습니다. 따라서 ACS는 orchestrator 마찬가지로 컨테이너에 대 한 기존 오픈 소스 orchestrators를 활용 하는 인프라 하지 않습니다.

사용 관점에서 Azure 컨테이너 서비스의 목표는 인기 있는 오픈 소스 도구와 기술을 사용 하 여 컨테이너 호스팅 환경을 제공 하는입니다. 이 위해 선택한 여 orchestrator에 대 한 표준 API 끝점을 노출합니다. 이러한 끝점을 사용 하 여 해당 끝점에 서로 연결할 수 있는 모든 소프트웨어를 활용할 수 있습니다. 예를 들어 docker는 Docker Swarm 끝점의 경우 Docker 명령줄 인터페이스 (CLI)를 사용 하도록 선택할 수 있습니다. DC/OS 용 DC/OS CLI를 사용 하도록 선택할 수 있습니다.

### <a name="getting-started-with-azure-container-service"></a>Azure 컨테이너 서비스를 시작 하기 

Azure 컨테이너 서비스를 사용 하 여을 시작 하려면 클러스터를 배포할 있습니다 Azure 컨테이너 서비스는 Azure 포털에서 Azure 리소스 관리자 템플릿을 사용 하 여 또는 [CLI](https://docs.microsoft.com/cli/azure/install-azure-cli)합니다. 사용 가능한 템플릿에 포함 [docker는 Docker Swarm](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-swarm), [Kubernetes](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-kubernetes), 및 [DC/OS](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-dcos)합니다. 퀵 스타트 서식 파일을 추가 또는 고급 Azure 구성을 포함 하도록 수정할 수 있습니다. Azure 컨테이너 서비스 클러스터를 배포 하는 방법에 대 한 자세한 내용은 참조 하십시오. [Azure 컨테이너 서비스 클러스터를 배포할](https://docs.microsoft.com/azure/container-service/container-service-deployment) Azure 웹 사이트입니다.

ACS의 일부로 기본적으로 설치 된 소프트웨어의 모든 가격 있습니다. 모든 기본 옵션은 오픈 소스 소프트웨어로 구현 됩니다.

ACS는 표준 A "," D "," DS "," G "및" GS 시리즈 Azure에서 Linux 가상 컴퓨터를 찾을 수 없습니다. 다른 기본 인프라 리소스 저장소 및 네트워킹 등 사용 뿐만 아니라 계산 인스턴스를 선택 하면에 대해서만 청구 됩니다. 자체 ACS에 대 한 증분 요금이 없습니다 있습니다.

## <a name="additional-resources"></a>추가 리소스

-   **Azure 컨테이너 서비스를 사용 하 여 솔루션을 호스팅하는 Docker 컨테이너 소개**
    [*https://docs.microsoft.com/azure/container-service/container-service-intro*](https://docs.microsoft.com/azure/container-service/container-service-intro)

-   **Docker 웜 개요**
    [*https://docs.docker.com/swarm/overview/*](https://docs.docker.com/swarm/overview/)

-   **모드 개요 swarm**
    [*https://docs.docker.com/engine/swarm/*](https://docs.docker.com/engine/swarm/)

-   **DC/OS 개요 mesosphere**
    [*https://docs.mesosphere.com/1.7/overview/*](https://docs.mesosphere.com/1.7/overview/)

-   **Kubernetes 합니다.** 공식 사이트입니다. \ \
    [*http://kubernetes.io/*](http://kubernetes.io/)


>[!div class="step-by-step"]
[이전] (탄력적인-높은-가용성-microservices.md) [다음] (사용 하 여-azure-서비스-fabric.md)
