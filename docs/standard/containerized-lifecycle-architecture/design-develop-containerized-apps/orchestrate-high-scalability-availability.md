---
title: "Microservices 및 높은 확장성 및 가용성 multicontainer 응용 프로그램 오케스트레이션"
description: "Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 응용 프로그램 수명 주기"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/19/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 4345fe8f36ecc32a7dd8e72fce5338bff308ffdf
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="orchestrating-microservices-and-multicontainer-applications-for-high-scalability-and-availability"></a>Microservices 및 높은 확장성 및 가용성 multicontainer 응용 프로그램 오케스트레이션

프로덕션에 사용 가능한 응용 프로그램에 대 한 orchestrators를 사용 하 여이 응용 프로그램에 microservices 기반 또는 단순히 여러 컨테이너에서 분할 하는 경우 중요 합니다. 마이크로 서비스 기반 접근 방식에서 이전에 도입 된 각 마이크로 서비스 소유 하 고 해당 모델 및 데이터 하는 개발 및 배포 측면 자치 됩니다. 하지만 보다 일반적인 응용 프로그램으로 구성 된 여러 서비스 (예: SOA)의 경우에 됩니다 있는 여러 컨테이너 또는 분산된 시스템으로 배포 되어야 하는 단일 비즈니스 응용 프로그램을 구성 하는 서비스입니다. 이러한 종류의 시스템은 확장성 및 관리; 복잡 따라서 있습니다 반드시 사용할 필요는 orchestrator 프로덕션 지원 하 고 확장 가능한 multicontainer 응용 프로그램이 들어 있습니다.

그림 4-6 여러 microservices (컨테이너)의 구성 된 응용 프로그램의 클러스터로 배포를 보여 줍니다.

![](./media/image6.png)

그림 4-6: 컨테이너 클러스터

논리적인 접근법 모양입니다. 그러나 어떻게 하면 처리 부하 분산, 라우팅 및 이러한 구성 된 응용 프로그램을 줄이면서?

Docker 명령줄 인터페이스 (CLI)는 한 호스트에서 한 컨테이너를 관리 요구를 충족 하 하지만 더 복잡 한 분산된 응용 프로그램에 대 한 여러 호스트에 배포 된 여러 컨테이너를 관리 하는 데 있어 짧은 대체 됩니다. 대부분의 경우에는 관리 플랫폼을 하는 자동으로 컨테이너를 시작, 일시 중단 또는 필요할 때 종료할 이상적으로 네트워크 및 데이터 저장소 같은 리소스에 액세스 하는 방식 또한 제어 해야 합니다.

개별 컨테이너 또는 매우 간단한 구성 된 앱 및 microservices 있는 대규모 엔터프라이즈 응용 프로그램의 이동 관리 외에 오케스트레이션 및 플랫폼 클러스터링을 설정 해야 합니다.

아키텍처 및 개발 관점에서 microservices 기반 건물 큰, 엔터프라이즈는 응용 프로그램을 된 경우 다음 플랫폼 및 고급 시나리오를 지 원하는 제품을 이해 하는 것이 중요.

-   **클러스터 및 orchestrators** 조정 해야 할 때-out 많은 Docker 호스트에 걸쳐 응용 프로그램을와 같은 큰 microservices 기반 응용 프로그램으로를 것이 중요 하 여 단일 클러스터의 모든 해당 호스트를 관리할 수 기본 플랫폼의 복잡성을 추상화 합니다. 컨테이너 클러스터와 orchestrators 제공 기능입니다. Docker는 Docker Swarm, Mesosphere DC/OS, Kubernetes (첫 번째 세 Azure 컨테이너 서비스를 통해 사용할 수 있는) 및 Azure 서비스 패브릭은이 orchestrators 있습니다.

-   **스케줄러** *일정 예약* 또한 사용자 인터페이스를 제공 하는 클러스터의 컨테이너를 시작 하려면 관리자에 대 한 기능을 의미 합니다. 클러스터 스케줄러는 여러 가지 역할: 클러스터의 리소스를 효율적으로 사용 하려면, 노드 또는 호스트 간에 부하를 분산 컨테이너와 효율적으로 사용자가 제공한 제약 조건을 설정 및 높음 제공 하는 동안 오류에 대해 강력한 수 가용성입니다.

클러스터 및 스케줄러의 개념 없으므로 두 가지 기능을 제공 하는 종종 다른 공급 업체에서 제공 하는 제품 관련 밀접 하 게 됩니다. 표 4-1에는 가장 중요 한 플랫폼 및 클러스터 및 스케줄러에 대 한 소프트웨어 선택 나열 합니다. 일반적으로 이러한 클러스터는 Azure와 같은 공용 클라우드에서 제공 됩니다.

클러스터링 컨테이너, 오케스트레이션 및 예약에 대 한 표 4-1: 소프트웨어 플랫폼

| 플랫폼 | 설명 |
|---|---|
| Docker 웜<br/> ![http://rancher.com/wp-content/themes/rancher-2016/assets/images/swarm.png?v=2016-07-10-am](./media/image7.png) | Docker 웜 클러스터 및 Docker 컨테이너를 예약 하는 기능을 제공 합니다. 웜을 사용 하 여 단일, 가상 Docker 호스트에 Docker 호스트의 풀을 설정할 수 있습니다. 클라이언트의 의미는 웜 쉽게 크기를 조정 하는 응용 프로그램에 대 한 여러 호스트를 호스트에는 동일한 방식으로 웜을 API 요청을 수행할 수 있습니다. <br /><br /> Docker 웜은 동시에 회사에서 제품입니다. <br /><br /> Docker v1.12 하거나 네이티브 및 기본 제공 Swarm 모드 나중에 실행할 수 있습니다. |
| Mesosphere DC/OS<br/>![https://mesosphere.com/wp-content/uploads/2016/04/logo-horizontal-styled.png](./media/image8.png) |  Mesosphere 엔터프라이즈 DC/OS (Apache Mesos에 기반)는 컨테이너 및 분산된 응용 프로그램을 실행 하기 위한 프로덕션에 사용 가능한 플랫폼입니다. <br /><br /> DC/OS 클러스터에서 사용할 수 있는 리소스의 컬렉션을 추상화 하 고 해당 리소스를 기반으로 하는 구성 요소를 사용할 수 있도록 하 여 작동 합니다. 풀 마라톤 DC/운영 체제와 통합 하는 스케줄러로 일반적으로 사용 됩니다. |
| Google Kubernetes<br />![https://pbs.twimg.com/media/Bt\_pEfqCAAAiVyz.png](./media/image9.png) | Kubernetes는 클러스터 인프라 및 컨테이너 조정 기능을 예약 하는 기능을 제공 하는 오픈 소스 제품입니다. 호스트 클러스터 간에 배포, 배율 및 응용 프로그램 컨테이너의 작업을 자동화할 수 있습니다. <br /><br /> Kubernetes는 컨테이너 응용 프로그램을 쉽게 관리 및 검색에 대 한 논리 단위로 그룹화 하는 컨테이너 중심 인프라를 제공 합니다. |
| Azure Service Fabric<br />![https://azure.microsoft.com/svghandler/service-fabric?width=600&height=315](./media/image10.png) | [서비스 패브릭](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) 는 응용 프로그램을 빌드하기 위한 Microsoft microservices 플랫폼입니다. 한 [orchestrator](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction) 의 서비스를 컴퓨터의 클러스터를 만듭니다. 기본적으로 서비스 패브릭에서 배포 하 고 프로세스에 따라 서비스를 활성화 되지만 서비스 패브릭 서비스를 Docker 컨테이너 이미지에서를 배포할 수 있습니다. 더 중요 한 혼합할 수 있습니다 프로세스의 서비스 서비스에 동일한 응용 프로그램의 컨테이너입니다. <br /><br /> 2017 년 1 월을 기준으로 Docker 컨테이너 배포 서비스를 지 원하는 서비스 패브릭의 기능은 미리 보기 상태입니다. <br /><br /> 사용 하 여 다양 한 방식에서 서비스 패브릭 서비스를 개발할 수 있습니다는 [프로그래밍 모델 서비스 패브릭](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework) 배포 [게스트 실행 파일](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-existing-app) 컨테이너 뿐만 아니라 합니다. 서비스 패브릭 같은 규범적인 응용 프로그램 모델을 지원 [상태 저장 서비스](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) 및 [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction)합니다.

## <a name="using-container-based-orchestrators-in-azure"></a>Azure에서 컨테이너 기반 orchestrators를 사용 하 여

여러 클라우드 공급 업체는 Docker 컨테이너 지원 함께 Docker 클러스터 및 Azure, Amazon EC2 컨테이너 서비스 및 Google 컨테이너 엔진 등의 오케스트레이션 지원을 제공 합니다. Azure는 다음 섹션에 설명 된 대로 Azure 컨테이너 서비스를 통해 클러스터 및 orchestrator 지원을 Docker를 제공 합니다.

다른 선택도 Linux 및 Windows 컨테이너에 따라 Docker 지원 Azure Service Fabric을 사용 하는 것입니다. Azure 또는 다른 클라우드 서비스 패브릭 실행으로 [온-프레미스](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere)합니다.

## <a name="using-azure-container-service"></a>Azure 컨테이너 서비스를 사용 하 여

Docker 클러스터 여러 Docker 호스트를 풀링 하 고는 단일 가상 Docker 호스트에 노출 하는 클러스터에 여러 컨테이너를 배포할 수 있습니다. 클러스터는 확장성 및 상태와 같은 모든 복잡 한 관리 기능을 처리 합니다. 그림 4-7 Docker 클러스터 구성 된 응용 프로그램에 대 한 컨테이너 서비스에 매핑되는 방식을 나타냅니다.

컨테이너 서비스 만들기, 구성 및 클러스터 화 된 응용 프로그램을 실행 하는 미리 구성 된 vm의 관리를 단순화 하는 방법을 제공 합니다. 최적화 된 구성의 인기 있는 오픈 소스 일정 예약 및 오케스트레이션 도구를 사용 하 여 컨테이너 서비스 기능을 제공 하면 기존 기술을 사용 하거나 커뮤니티 전문성을 배포 하 고 컨테이너 기반 관리의 크기가 크고 점점 본문에 그리기 Azure에서 응용 프로그램입니다.

컨테이너 서비스를 Azure에 맞게 인기 있는 오픈 소스 도구를 클러스터링 하는 Docker 및 기술 구성을 최적화합니다. 사용자 컨테이너와 응용 프로그램 구성에 대 한 이식성을 제공 하는 열린 솔루션 가져오기 Orchestrator 도구, 호스트, 수 및 크기를 선택 하 고 다른 모든 항목을 처리 하는 컨테이너 서비스 키를 누릅니다.

컨테이너 서비스 Docker 이미지를 사용 하 여 응용 프로그램 컨테이너가 완전히 이식 가능 하도록 합니다. 선택 하는 DC/OS, Kubernetes, 및 docker는 Docker Swarm와 같은 오픈 소스 오케스트레이션 플랫폼 이러한 응용 프로그램 수천 또는 심지어 수만 컨테이너를 확장할 수 있도록 지원 합니다.

Azure 컨테이너 서비스를 사용 하면 오케스트레이션 계층에 포함 하 여 응용 프로그램 이식성을 유지 하면서 Azure의 엔터프라이즈급 기능을 걸릴 수 있습니다.

![](./media/image11.png)

그림 4-7: Azure 컨테이너 서비스에서 선택할 수 있는 클러스터링

그림 4-8에서와 같이 컨테이너 서비스는 Azure에서 DC/OS, Kubernetes, 또는 docker는 Docker Swarm을 배포 하기 위해 제공 하는 인프라 단순히 하지만 모든 추가 orchestrator를 구현 하지 않습니다. 따라서 컨테이너 서비스는 하지는 orchestrator, 따라서; 이 환경은 컨테이너에 대 한 기존 오픈 소스 orchestrators을 활용 하는 인프라입니다.

![](./media/image12.png)

그림 4-8: Orchestrators 컨테이너 서비스에

사용 관점에서 컨테이너 서비스의 목표는 인기 있는 오픈 소스 도구와 기술을 사용 하 여 컨테이너 호스팅 환경을 제공 하는입니다. 이 위해 선택한 여 orchestrator에 대 한 표준 API 끝점을 노출합니다. 이러한 끝점을 사용 하 여 이러한 끝점과 통신할 수 있는 모든 소프트웨어를 사용할 수 있습니다. 예를 들어 docker는 Docker Swarm 끝점의 경우 Docker CLI를 사용 하도록 선택할 수 있습니다. DC/OS 용 DC/OS CLI를 사용 하도록 선택할 수 있습니다.

### <a name="getting-started-with-container-service"></a>컨테이너 서비스를 시작 하기

컨테이너 서비스를 사용 하 여을 시작 하려면 Azure 리소스 관리자 템플릿을 사용 하 여 Azure 포털에서 컨테이너 서비스 클러스터 배포할 또는 [CLI](https://docs.microsoft.com/cli/azure/install-azure-cli)합니다. 사용 가능한 템플릿에 포함 [docker는 Docker Swarm](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-swarm), [Kubernetes](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-kubernetes), 및 [DC/OS](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-dcos)합니다. 추가 또는 고급 Azure 구성을 포함 하도록 퀵 스타트 템플릿을 수정할 수 있습니다.

**자세한 내용은** Azure 웹 사이트에서의 컨테이너 서비스 클러스터를 배포 하는 방법에 대 한 자세한 내용을 보려면 읽고 [Azure 컨테이너 서비스 클러스터를 배포할](https://docs.microsoft.com/azure/container-service/dcos-swarm/container-service-deployment)합니다.

ACS의 일부로 기본적으로 설치 된 소프트웨어의 모든 가격 있습니다. 모든 기본 옵션은 오픈 소스 소프트웨어로 구현 됩니다.

컨테이너 서비스는 현재 표준 A "," D "," DS "," G "및" Azure의 GS 시리즈 Linux Vm에 사용할 수 있습니다. 다른 기본 인프라 리소스 저장소 및 네트워킹 등 사용 뿐만 아니라 선택 하는 컴퓨팅 인스턴스에 대해서만 청구 됩니다. 컨테이너 서비스에 대 한 증분 요금이 없습니다 자체 있습니다.

### <a name="additional-resources"></a>추가 리소스

다음은 추가 정보를 찾을 수 있는 위치:

-   컨테이너 서비스를 사용 하 여 솔루션을 호스팅하는 Docker 컨테이너 소개:  
    https://docs.microsoft.com/azure/container-service/kubernetes/container-service-intro-kubernetes>

-   Docker 웜 개요:  
    <https://docs.docker.com/swarm/overview/>

-   웜 모드 개요:  
    <https://docs.docker.com/engine/swarm/>

-   Mesosphere DC/OS 개요:    
    <https://docs.mesosphere.com/1.7/overview/>

-   Kubernetes (공식 사이트):  
    <http://kubernetes.io/>

## <a name="using-service-fabric"></a>서비스 패브릭을 사용 하 여

서비스 패브릭 서비스 제공를 일반적으로 스타일에서 모놀리식 였던 "상자" 제품 배달에서 Microsoft의 전환에서 발생 합니다. Azure SQL 데이터베이스, Azure 문서 DB, Azure 서비스 버스 Cortana의 백 엔드 등 규모에 대규모 서비스 구축 및 운영 하는 환경을 서비스 패브릭 모양이 지정 합니다. 플랫폼 발전 함에 따라 시간이 지남에 따라 점점 더 많은 서비스 채택으로 합니다. 중요 서비스 패브릭 Azure에서 뿐만 아니라 독립 실행형 Windows Server 배포에서 실행 해야 했습니다.

서비스 패브릭의 목적은 구축 하 고 서비스를 실행 하 고 팀 microservices 방식을 사용 하 여 비즈니스 문제를 해결할 수 있도록 인프라 리소스를 효율적으로 활용의 어려운 문제를 해결 하는 것입니다.

서비스 패브릭 microservices 접근 방식을 사용 하는 응용 프로그램을 빌드할 수 있도록 두 가지 광범위 한 영역을 제공 합니다.

-   시스템 서비스를 배포, 확장, 업그레이드, 검색 및 실패 한 서비스를 다시 시작, 서비스 위치 검색, 상태를 관리 및 상태 모니터링을 제공 하는 플랫폼입니다. 이러한 시스템 서비스를 제공 앞에서 설명한 microservices 특징을 많이 적용 합니다.

-   Microservices로, 응용 프로그램을 빌드할 수 있도록 프로그래밍 Api 또는 프레임 워크: [신뢰할 수 있는 작업자와 신뢰할 수 있는 서비스](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework)합니다. 물론, 프로그램 마이크로 서비스를 작성 하기 위해 코드를 선택할 수 있지만 이러한 Api 작업 더 간단한 만들고 더 하위 수준 플랫폼에 통합 합니다. 상태 및 진단 정보 또는 있습니다를 얻을 수 있습니다 이러한 방식으로 활용할 수 신뢰할 수 있는 상태 관리 합니다.

서비스 패브릭 서비스를 구축 하는 방법에 대해 알 수 없는 이며 모든 기술을 사용할 수 있습니다. 그러나 보다 쉽게 microservices 빌드할 수 있도록 기본 제공 프로그래밍 Api를 제공 합니다.

그림 4-9 만들 간단한 프로세스 또는 Docker 컨테이너 microservices 서비스 패브릭에서 실행 하는 방법을 보여 줍니다. 와 동일한 서비스 패브릭 클러스터 내에서 프로세스 기반 microservices microservices 컨테이너 기반을 함께 사용할 수 이기도 합니다.

![](./media/image13.png)

그림 4-9: 배포 microservices 프로세스 또는 Azure 서비스 패브릭의 컨테이너

Linux 및 Windows 호스트에 따라 서비스 패브릭 클러스터 Linux Docker 컨테이너와 Windows 컨테이너를 실행할 수 있습니다.

**자세한 내용은** 서비스 패브릭에서 컨테이너 지원에 대 한 최신 정보는 Azure 웹 사이트에 대 한 읽기 [서비스 패브릭 및 컨테이너](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview)합니다.

서비스 패브릭은 다른 논리적 아키텍처 (비즈니스 microservices 또는 경계가 지정 된 컨텍스트) 물리적 구현 보다를 정의할 수 있는 플랫폼의 좋은 예입니다. 예를 들어, 구현 하는 경우 [상태 저장 Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) 에 [Azure 서비스 패브릭](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview)는 다음 섹션에 도입 된 "[와 상태 저장 microservicesStateless](#stateless-versus-stateful-microservices), "비즈니스 마이크로 서비스 개념을 여러 물리적 서비스를 사용 해야 합니다.

그림 4-10이 고 서비스 패브릭 상태 저장 신뢰할 수 있는 서비스를 구현 하는 경우 논리적/비즈니스 마이크로 서비스 관점에서의 생각에서와 같이, 일반적으로 해야 합니다 두 계층의 서비스를 구현 합니다. 첫 번째 백 엔드 상태 저장 신뢰할 수 있는 서비스를 여러 파티션을 처리 하는 합니다. 두 번째 프런트 엔드 서비스 또는 라우팅 및 데이터 집계 여러 파티션 또는 상태 저장 서비스 인스턴스는 일을 담당 게이트웨이 서비스입니다. 해당 게이트웨이 서비스가 서비스 패브릭과 함께에서 사용 되는 백 엔드 서비스에 액세스 하는 다시 시도 루프도 클라이언트 통신을 처리 [역방향 프록시](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy)합니다.

![](./media/image14.png)

서비스 패브릭에서 여러 개의 상태 저장 및 상태 비저장 서비스를 그림 4-10: 비즈니스 마이크로 서비스

어떤 경우 든, 서비스 패브릭 상태 저장 Reliable Services를 사용 하는 경우는 논리 또는 비즈니스 마이크로 서비스 (경계가 지정 된 컨텍스트) 일반적으로 여러 개의 물리적 서비스의 요소로 구성 된도 합니다. 각에, 게이트웨이 서비스 및 서비스 파티션 그림 4-10에서와 같이 ASP.NET Web API 서비스로 구현할 수 있습니다.

서비스 패브릭에서 그룹화를 그룹으로 서비스를 배포할 수 있습니다는 [서비스 패브릭 응용 프로그램](https://docs.microsoft.com/azure/service-fabric/service-fabric-application-model)는 패키징 및 orchestrator 또는 클러스터에 대 한 배포의 단위입니다. 따라서 서비스 패브릭 응용 프로그램에 매핑할 수이 자율 영업 및 논리 마이크로 서비스 경계 또는 컨텍스트 제한도 있습니다.

### <a name="service-fabric-and-containers"></a>서비스 패브릭 및 컨테이너

서비스 패브릭에서 컨테이너와 관련 하 여도 서비스 패브릭 클러스터 내에서 컨테이너 이미지에 서비스를 배포 수 있습니다. 그림 4-11 해당 대부분을의 경우 서비스 당 하나만 컨테이너 있을 것을 보여 줍니다.

![](./media/image15.png)

서비스 패브릭에서 여러 개의 서비스 (컨테이너)를 그림 4-11: 비즈니스 마이크로 서비스

하지만 이른바 "사이드카" 컨테이너 (함께 논리 서비스의 일부분으로 배포 해야 하는 두 개의 컨테이너)는 서비스 패브릭에서 가능 합니다. 것이 중요 비즈니스 마이크로 서비스 여러 화합 요소 주위에 논리적 경계 된다는 점입니다. 대부분의 경우에서 단일 데이터 모델에서는 단일 서비스 않을 수 있지만 다른 경우에 실제 몇 가지 서비스도 할 수 있습니다.

이 작성 (2017 년 4 월) 기준으로 서비스 패브릭에서 배포할 수 없습니다 SF 신뢰할 수 있는 상태 저장 서비스 컨테이너에 — 게스트 컨테이너, 상태 비저장 서비스 또는 컨테이너에 행위자 서비스를 배포할 수 있습니다. 그러나 프로세스의 서비스 및 서비스에 동일한 서비스 패브릭 응용 프로그램의 컨테이너를 혼합할 수 그림 4-12에 나와 있는 것 처럼 합니다.

![](./media/image16.png)

그림 4-12: 비즈니스 마이크로 서비스 컨테이너 및 상태 저장 서비스와 함께 서비스 패브릭 응용 프로그램에 매핑

지원은 Docker 컨테이너를 사용 하는 Linux 또는 Windows 컨테이너는 여부에 따라 다른 이기도 합니다. 서비스 패브릭에서 컨테이너에 대 한 지원이 예정 된 릴리스에서 저장 됩니다. Azure 웹 사이트에서 서비스 패브릭에서 컨테이너 지원에 대 한 최신 뉴스 읽기 [서비스 패브릭 및 컨테이너](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview)합니다.

## <a name="stateless-versus-stateful-microservices"></a>상태 저장 microservices와 상태 비저장

에서 설명한 대로 각 마이크로 서비스 (논리적 경계가 지정 된 컨텍스트) 해당 도메인 모델 (데이터와 논리)를 소유 해야 합니다. 상태 비저장 microservices의 경우 데이터베이스 외부 SQL Server와 같은 관계형 옵션 또는 MongoDB 또는 Azure DocumentDB와 같은 NoSQL 옵션 사용 됩니다.

하지만 서비스 자체도 수, 상태 저장은 마이크로 서비스 내에서 멤버의 데이터를 의미입니다. 이 데이터는 동일한 서버의 뿐 아니라 하지만 메모리에, 마이크로 서비스 프로세스 내에 있을 수 있습니다 및 드라이브에 유지 다른 노드에 복제 합니다. 그림 4-13에서는 다양 한 방식을 보여 줍니다.

![](./media/image17.png)

그림 4-13: microservices 상태 저장 또는 상태 비저장

상태 비저장 방법을 완벽 하 게 올바른지와 방법은 전통적인 및 잘 알려진 패턴 유사 하기 때문에 상태 저장 microservices 보다 구현 하기가 더 쉽습니다. 하지만 상태 비저장 microservices 프로세스 및 데이터 원본 간의 대기 시간을 적용 합니다. 추가 캐시 및 큐를 사용 하 여 성능 개선 하려고 시도할 때 더 이동 조각도 포함 합니다. 결과 너무 많은 계층에 있는 복잡 한 아키텍처를 가진 종료할 수 있습니다.

반면, [상태 저장 microservices](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) 도메인 논리 및 데이터가 간의 대기 시간이 없음이 있기 때문에 고급 시나리오에서 excel 수 있습니다. 고급 데이터 처리 게임 백 엔드가, 서비스 및 로컬 상태에 대 한 액세스 속도 제공 하는 상태 저장 서비스에서 활용 하는 모든 기타 대기 시간이 짧은 시나리오도 데이터베이스.

상태 비저장 및 상태 저장 서비스를 보완 합니다. 예를 들어, 여러 파티션으로 상태 저장 서비스를 구분할 수 있습니다. 이러한 파티션을 액세스 하려면 역할을 각 파티션의 파티션 키를 기반으로 주소를 지정 하는 방법을 알고 있는 게이트웨이 서비스 상태 비저장 서비스를 할 수 있습니다.

상태 저장 서비스 단점이지 않습니다. 간단한 수준을 제시 쉽게 확장할 수 있도록 해 주는 비교해 합니다. 상태 저장 microservices 및 분할 하는 데이터 간의 데이터 복제와 같은 작업에 대 한 일반적으로 외부 데이터베이스 시스템으로 구현할 수 있는 기능을 보내야 합니다. 그러나이 orchestrator와 같은 영역 중 하나는 [서비스 패브릭](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-platform-architecture) 와 해당 [신뢰할 수 있는 상태 저장 서비스](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) 가장 수-개발 및 상태 저장의 수명 주기를 단순화 하 여 microservices를 사용 하 여 [신뢰할 수 있는 서비스 API](https://docs.microsoft.com/azure/service-fabric/service-fabric-work-with-reliable-collections) 및 [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction)합니다.

상태 저장 서비스 Actor 패턴을 지 원하는 및 내결함성 및 비즈니스 논리와 데이터 사이의 대기 시간을 개선 시켜 주는 허용 하는 다른 마이크로 서비스 프레임 워크는 Microsoft [식품](https://github.com/dotnet/orleans): Microsoft Research 를[ Akka.NET](http://getakka.net/)합니다. 현재 두 프레임 워크 Docker에 대 한 지원을 개선 합니다.

Docker 컨테이너는 자체 상태 비저장 있는지 확인 합니다. 상태 저장 서비스를 구현 하려는 경우 앞에서 기록한 추가 규정 및 상위 수준 프레임 워크 중 하나가 필요 합니다. 그러나이 문서의 작성일 서비스 패브릭의 상태 저장 서비스 일반 microservices 으로만 컨테이너로 지원 되지 않습니다. 컨테이너에서 신뢰할 수 있는 서비스 지원 서비스 구성의 후속 버전에서 사용할 수 있습니다.


>[!div class="step-by-step"]
[이전] (soa-applications.md) [다음] (docker-앱-개발-environment.md)
