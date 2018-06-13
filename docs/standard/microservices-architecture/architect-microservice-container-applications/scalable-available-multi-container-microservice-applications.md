---
title: 높은 확장성 및 가용성을 위한 마이크로 서비스 및 다중 컨테이너 응용 프로그램 오케스트레이션
description: 컨테이너화된 .NET 응용 프로그램용 .NET 마이크로 서비스 아키텍처 | 높은 확장성 및 가용성을 위한 마이크로 서비스 및 다중 컨테이너 응용 프로그램 오케스트레이션
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.openlocfilehash: e8552f79a4196c161ec70d7ea46156215e52db26
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33578887"
---
# <a name="orchestrating-microservices-and-multi-container-applications-for-high-scalability-and-availability"></a>높은 확장성 및 가용성을 위한 마이크로 서비스 및 다중 컨테이너 응용 프로그램 오케스트레이션

응용 프로그램이 마이크로 서비스를 기반으로 하거나 단순히 여러 컨테이너로 분할되는 경우 프로덕션 지원 응용 프로그램에 오케스트레이터를 사용해야 합니다. 이전에 소개한 대로 마이크로 서비스 기반 방법에서 각 마이크로 서비스마다 모델 및 데이터를 소유하므로 개발 및 배포 관점에서 독립적입니다. 그러나 SOA와 같은 여러 서비스로 구성된 기존 응용 프로그램이 있는 경우에도 분산 시스템으로 배포해야 하는 단일 비즈니스 응용 프로그램을 구성하는 여러 컨테이너 또는 서비스가 제공됩니다. 이러한 종류의 시스템은 규모 확장 및 관리가 복잡합니다. 따라서 프로덕션을 지원하고 확장성 있는 다중 컨테이너 응용 프로그램을 원하는 경우 오케스트레이터가 반드시 필요합니다.

그림 4-23에서는 여러 마이크로 서비스(컨테이너)로 구성된 응용 프로그램의 클러스터에 배포하는 방법을 보여 줍니다.

![](./media/image23.PNG)

**그림 4-23** 컨테이너의 클러스터

이는 논리적인 방법처럼 보입니다. 그러나 이처럼 구성된 응용 프로그램을 부하 분산, 라우팅 및 오케스트레이션하려면 어떻게 할까요?

단일 Docker 호스트의 일반 Docker 엔진은 하나의 호스트에서 단일 이미지 인스턴스를 관리해야 하는 필요성을 충족하지만, 더 복잡한 분산 응용 프로그램을 위해 여러 호스트에 배포된 여러 컨테이너를 관리하는 경우에는 부족합니다. 대부분의 경우 컨테이너를 자동으로 시작하고 이미지당 여러 인스턴스로 컨테이너를 확장하고 일시 중지하거나 필요한 경우 종료하는 관리 플랫폼이 필요하며, 네트워크 및 데이터 저장소와 같은 리소스에 액세스하는 방법을 제어하는 것도 좋습니다.

개별 컨테이너 또는 매우 간단하게 구성된 앱을 관리하는 것 외에도, 마이크로 서비스가 있는 대규모 엔터프라이즈 응용 프로그램으로 이동하려면 오케스트레이션 및 클러스터링 플랫폼으로 전환해야 합니다.

아키텍처 및 개발 관점에서 마이크로 서비스 기반 응용 프로그램으로 구성된 대규모 엔터프라이즈를 구축하는 경우 고급 시나리오를 지원하는 다음 플랫폼과 제품을 이해해야 합니다.

**클러스터 및 오케스트레이터** 대규모 마이크로 서비스 기반 응용 프로그램과 같이 많은 Docker 호스트에서 응용 프로그램을 확장해야 하는 경우, 기본 플랫폼의 복잡성을 추상화하여 모든 호스트를 단일 클러스터로 관리할 수 있어야 합니다. 이는 컨테이너 클러스터 및 오케스트레이터에서 제공하는 것입니다. 오케스트레이터의 예로, Azure Service Fabric, Kubernetes, Docker Swarm 및 Mesosphere DC/OS가 있습니다. 마지막 세 개의 오픈 소스 오케스트레이터는 Azure에서 Azure Container Service를 통해 사용할 수 있습니다.

**스케줄러** *예약*은 관리자가 클러스터에서 컨테이너를 시작하여 UI도 제공할 수 있는 기능을 의미합니다. 클러스터 스케줄러에는 클러스터 리소스를 효율적으로 사용하고, 사용자가 제공하는 제약 조건을 설정하며, 노드 또는 호스트 간에 컨테이너를 효율적으로 부하 분산하고, 고가용성을 제공하면서 오류에 대해 강력한 기능을 제공하기 위한 여러 가지 역할이 있습니다.

클러스터 및 스케줄러의 개념은 밀접하게 관련되어 있으므로 여러 공급업체에서 제공하는 제품은 종종 두 가지 기능의 집합을 제공합니다. 다음 목록에서는 클러스터 및 스케줄러에 가장 중요한 플랫폼 및 소프트웨어 선택 항목을 보여 줍니다. 이러한 오케스트레이터는 일반적으로 Azure와 같은 공용 클라우드에서 제공됩니다.

## <a name="software-platforms-for-container-clustering-orchestration-and-scheduling"></a>컨테이너 클러스터링, 오케스트레이션 및 예약용 소프트웨어 플랫폼

Kubernetes

![https://pbs.twimg.com/media/Bt\_pEfqCAAAiVyz.png](./media/image24.png)

> Kubernetes는 클러스터 인프라와 컨테이너 예약에서 기능 오케스트레이션에 이르기까지 다양한 기능을 제공하는 오픈 소스 제품입니다. 이를 통해 호스트 클러스터 전체에서 응용 프로그램 컨테이너의 배포, 확장 및 작업을 자동화할 수 있습니다.
>
> Kubernetes는 쉽게 관리하고 검색할 수 있도록 응용 프로그램 컨테이너를 논리 단위로 그룹화하는 컨테이너 중심 인프라를 제공합니다.
>
> Kubernetes의 완성도는 Linux에서 높았지만, Windows에서는 그렇지 못했습니다.

Docker Swarm

![http://rancher.com/wp-content/themes/rancher-2016/assets/images/swarm.png?v=2016-07-10-am](./media/image25.png)

> Docker Swarm을 사용하면 Docker 컨테이너를 클러스터링하고 예약할 수 있습니다. Swarm을 사용하면 Docker 호스트 풀을 단일 가상 Docker 호스트로 전환할 수 있습니다. 클라이언트는 호스트에 수행한 방식과 동일하게 API 요청을 수행할 수 있습니다. 즉, Swarm을 사용하면 응용 프로그램을 여러 호스트로 쉽게 확장할 수 있습니다.
>
> Docker Swarm은 Docker 회사의 제품입니다.
>
> Docker v1.12 이상에서는 네이티브 및 기본 제공 Swarm 모드를 실행할 수 있습니다.

Mesosphere DC/OS

![https://mesosphere.com/wp-content/uploads/2016/04/logo-horizontal-styled.png](./media/image26.png)

> Mesosphere Enterprise DC/OS(Apache Mesos 기반)는 컨테이너 및 분산 응용 프로그램을 실행하기 위한 프로덕션 지원 플랫폼입니다.
>
> DC/OS는 클러스터에서 사용할 수 있는 리소스 컬렉션을 추상화하고 이를 기반으로 하여 빌드된 구성 요소에서 이러한 리소스를 사용할 수 있도록 함으로써 작동합니다. Marathon은 일반적으로 DC/OS와 통합된 스케줄러로 사용됩니다.
>
> DC/OS의 완성도는 Linux에서 높았지만, Windows에서는 그렇지 못했습니다.

Azure Service Fabric

![https://azure.microsoft.com/svghandler/service-fabric?width=600&height=315](./media/image27.png)

> [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview)은 응용 프로그램을 빌드하기 위한 Microsoft 마이크로 서비스 플랫폼입니다. 서비스의 [오케스트레이터](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction)이며, 컴퓨터로 구성된 클러스터를 만듭니다. Service Fabric은 서비스를 컨테이너 또는 일반 프로세스로 배포할 수 있습니다. 또한 동일한 응용 프로그램 및 클러스터 내의 컨테이너에 있는 서비스와 프로세스에 있는 서비스를 혼합할 수도 있습니다.
>
> Service Fabric은 [상태 저장 서비스](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) 및 [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction)와 같이 규범적 [Service Fabric 프로그래밍 모델](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework)(추가 및 선택 사양)을 제공합니다.
>
> Service Fabric의 완성도는 Windows에서 높았지만(Windows에서 진화), Linux에서는 그렇지 못했습니다. 
> 2017년 이후 Service Fabric에서 Linux 및 Windows 컨테이너를 모두 지원합니다.

## <a name="using-container-based-orchestrators-in-microsoft-azure"></a>Microsoft Azure에서 컨테이너 기반 오케스트레이션 사용

여러 클라우드 공급업체에서 Microsoft Azure, Amazon EC2 Container Service 및 Google Container Engine을 포함하여 Docker 컨테이너 지원 및 Docker 클러스터/오케스트레이션 지원을 제공합니다. Microsoft Azure는 다음 섹션에서 설명한 대로 ACS(Azure Container Service)를 통해 Docker 클러스터 및 오케스트레이터 지원을 제공합니다.

또 다른 선택 사항으로, Microsoft Azure Service Fabric(마이크로 서비스 플랫폼)을 사용하는 것이며, Linux 및 Windows 컨테이너 기반 Docker도 지원합니다. Service Fabric은 Azure 또는 다른 클라우드에서 실행되며, [온-프레미스](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere)에서도 실행됩니다.

## <a name="using-azure-container-service"></a>Azure Container Service 사용

Docker 클러스터는 여러 Docker 호스트를 풀링하고 단일 가상 Docker 호스트로 공개하여 여러 컨테이너를 클러스터에 배포할 수 있습니다. 클러스터는 확장성, 상태 등 모든 복잡한 관리 작업을 처리합니다. 그림 4-24에서는 구성된 응용 프로그램용 Docker 클러스터가 ACS(Azure Container Service)에 매핑되는 방법을 보여 줍니다.

ACS는 컨테이너화된 응용 프로그램을 실행하도록 미리 구성된 가상 머신 클러스터를 만들기, 구성 및 관리를 단순화할 수 있는 방법을 제공합니다. 인기 있는 오픈 소스 일정 예약 및 오케스트레이션 도구의 최적화된 구성을 통해 ACS를 사용하면 기존 기술을 사용하거나 광범위한 커뮤니티 전문 분야에 집중하여 Microsoft Azure에서 컨테이너 기반 응용 프로그램을 배포하고 관리할 수 있습니다.

Azure Container Service는 Azure용으로 특별히 인기 있는 Docker 클러스터링 오픈 소스 도구 및 기술의 구성을 최적화합니다. 컨테이너와 응용 프로그램 구성 모두에 이식성을 제공하는 개방형 솔루션을 얻을 수 있습니다. 사용자가 크기, 호스트 수, 오케스트레이터 도구를 선택하고, Container Service에서 다른 모든 작업을 처리합니다.

![](./media/image28.png)

**그림 4-24** Azure Container Service의 클러스터링 선택 항목

ACS는 Docker 이미지를 활용하여 응용 프로그램 컨테이너를 완벽하게 이식할 수 있도록 합니다. 이는 DC/OS(Apache Mesos로 구동), Kubernetes(원래 Google에서 개발), Docker Swarm과 같은 오픈 소스 오케스트레이션 플랫폼을 선택하여 이러한 응용 프로그램을 수천 개 또는 수만 개의 컨테이너로 확장할 수 있도록 지원합니다 .

Azure Container Service를 사용하면 Azure의 엔터프라이즈급 기능을 활용하면서 오케스트레이션 계층을 포함하여 응용 프로그램 이식성을 계속 유지할 수 있습니다.

![](./media/image29.png)

**그림 4-25** ACS의 오케스트레이터

그림 4-25와 같이 Azure Container Service는 DC/OS, Kubernetes 또는 Docker Swarm을 배포하기 위해 Azure에서 제공하는 인프라이지만, ACS는 오케스트레이터를 추가로 구현하지 않습니다. 따라서 ACS는 이처럼 오케스트레이터 자체가 아니며, 기존의 컨테이너용 오픈 소스 오케스트레이터를 활용하는 인프라입니다.

사용 관점에서, Azure Container Service의 목표는 인기 있는 오픈 소스 도구 및 기술을 사용하여 컨테이너 호스팅 환경을 제공하는 것입니다. 이를 위해 선택한 오케스트레이터의 표준 API 엔드포인트를 공개합니다. 이 엔드포인트를 사용하면 해당 엔드포인트와 통신할 수 있는 모든 소프트웨어를 활용할 수 있습니다. 예를 들어 Docker Swarm 엔드포인트의 경우 Docker CLI(명령줄 인터페이스)를 사용하도록 선택할 수 있습니다. DC/OS의 경우 DC/OS CLI를 사용하도록 선택할 수 있습니다.

### <a name="getting-started-with-azure-container-service"></a>Azure Container Service 시작 

Azure Container Service의 사용을 시작하려면 Azure Resource Manager 템플릿 또는 [CLI](https://docs.microsoft.com/cli/azure/install-azure-cli)를 사용하여 Azure Portal에서 Azure Container Service 클러스터를 배포합니다. 사용 가능한 템플릿으로, [Docker Swarm](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-swarm), [Kubernetes](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-kubernetes) 및 [DC/OS](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-dcos)가 있습니다. 빠른 시작 템플릿은 추가 또는 고급 Azure 구성을 포함하도록 수정할 수 있습니다. Azure Container Service 클러스터 배포에 대한 자세한 내용은 Azure 웹 사이트에서 [Azure Container Service 클러스터 배포](https://docs.microsoft.com/azure/container-service/container-service-deployment)를 참조하세요.

기본적으로 ACS의 일부로 설치된 소프트웨어에 대해서는 추가 비용이 없습니다. 모든 기본 옵션은 오픈 소스 소프트웨어로 구현됩니다.

ACS는 현재 Azure의 표준 A, D, DS, G 및 GS 시리즈 Linux 가상 머신에서 사용할 수 있습니다. 선택한 계산 인스턴스 및 사용되는 다른 기본 인프라 리소스(예: 저장소 및 네트워킹)에 대해서만 요금이 청구됩니다. ACS 자체에 대한 추가 비용은 없습니다.

## <a name="additional-resources"></a>추가 자료

-   **Azure Container Service를 사용한 Docker 컨테이너 호스팅 솔루션 소개**
    [*https://docs.microsoft.com/azure/container-service/container-service-intro*](https://docs.microsoft.com/azure/container-service/container-service-intro)

-   **Docker Swarm 개요**
    [*https://docs.docker.com/swarm/overview/*](https://docs.docker.com/swarm/overview/)

-   **Swarm 모드 개요**
    [*https://docs.docker.com/engine/swarm/*](https://docs.docker.com/engine/swarm/)

-   **Mesosphere DC/OS 개요**
    [*https://docs.mesosphere.com/1.7/overview/*](https://docs.mesosphere.com/1.7/overview/)

-   **Kubernetes.** 공식 사이트는 다음과 같습니다.
    [*https://kubernetes.io/*](https://kubernetes.io/)


>[!div class="step-by-step"]
[이전] (resilient-high-availability-microservices.md) [다음] (using-azure-service-fabric.md)
