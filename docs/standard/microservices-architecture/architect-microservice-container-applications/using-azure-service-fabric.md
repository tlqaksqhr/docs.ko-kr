---
title: Azure Service Fabric 사용
description: 컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | Azure Service Fabric 사용
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.openlocfilehash: d65968e3d37f53cceee55120110ad4bb3c13d304
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33577680"
---
# <a name="using-azure-service-fabric"></a>Azure Service Fabric 사용

Azure Service Fabric은 Microsoft가 전형적으로 획일화된 스타일의 패키지형 제품을 제공하는 것에서 서비스를 제공하는 방식으로 전환하는 것으로부터 비롯되었습니다. Azure SQL Database, Azure Cosmos DB, Azure Service Bus 또는 Cortana의 백 엔드와 같은 규모가 큰 대규모 서비스를 구축하고 운영한 경험을 토대로 Service Fabric이 형성되었습니다. 점점 더 많은 서비스가 도입됨에 따라 플랫폼은 시간이 지날수록 향상되었습니다. 중요한 점은 Service Fabric은 Azure뿐만 아니라 독립 실행형 Windows Server 배포에서도 실행되어야 한다는 것입니다.

Service Fabric의 목적은 서비스를 구축 및 실행하고 인프라 리소스를 효율적으로 활용하는 어려운 문제를 해결하여, 팀이 마이크로 서비스 접근 방식을 사용하여 비즈니스 문제를 해결할 수 있도록 하는 것입니다.

Service Fabric은 마이크로 서비스 접근 방식을 사용하는 응용 프로그램을 빌드하는 데 도움이 되는 두 가지 폭넓은 영역을 제공합니다.

-   실패한 서비스를 배포, 확장, 업그레이드, 검색 및 다시 시작하고 서비스 위치를 검색하며 상태를 관리하고 상태를 모니터링하는 시스템 서비스를 제공하는 플랫폼. 실제 이러한 시스템 서비스를 통해 이전에 설명한 마이크로 서비스의 많은 특성을 실현할 수 있습니다.

-   마이크로 서비스로 응용 프로그램을 빌드하는 데 도움이 되는 프로그래밍 API 또는 프레임워크: [Reliable Actor 및 Reliable Service](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework). 물론 마이크로 서비스를 구축하는 코드를 선택할 수는 있지만 이러한 API를 사용하면 작업이 더 간단해지며 플랫폼과 보다 자세히 통합할 수 있습니다. 이러한 방식으로 상태 및 진단 정보를 얻을 수 있거나 신뢰할 수 있는 상태 관리를 이용할 수 있습니다.

Service Fabric은 서비스 구축하는 방법과 관련하여 제약이 없으며 모든 기술을 사용할 수 있습니다. 단, 마이크로 서비스를 보다 쉽게 구축할 수 있도록 해주는 기본 제공 프로그래밍 API가 제공됩니다.

그림 4-26과 같이 Service Fabric에서 간단한 프로세스 또는 Docker 컨테이너로 마이크로 서비스를 만들고 실행할 수 있습니다. 동일한 Service Fabric 클러스터 내에서 컨테이너 기반 마이크로 서비스와 프로세스 기반 마이크로 서비스를 함께 사용할 수도 있습니다.

![](./media/image30.png)

**그림 4-26**. Azure Service Fabric에서 프로세스 또는 컨테이너로 마이크로 서비스 배포

Linux 및 Windows 호스트 기반 Service Fabric 클러스터는 Linux Docker 컨테이너와 Windows 컨테이너를 각각 실행할 수 있습니다.

Azure Service Fabric에서 컨테이너 지원에 대한 최신 정보는 [Service Fabric 및 컨테이너](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview)를 참조하세요.

Service Fabric은 [논리적 아키텍처 및 물리적 아키텍처](#logical-architecture-versus-physical-architecture) 섹션에서 소개된 물리적 구현과 다른 논리적 아키텍처(비즈니스 마이크로 서비스 또는 바인딩된 컨텍스트)를 정의할 수 있는 플랫폼의 좋은 예입니다. 예를 들어 [상태 비저장 및 상태 저장 마이크로 서비스](#stateless-versus-stateful-microservices) 섹션에 소개된 대로 [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview)에 [상태 저장 Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction)를 구현하면 여러 물리적 서비스에 비즈니스 마이크로 서비스 개념을 적용할 수 있습니다.

그림 4-27에서 볼 수 있듯이, 논리적/비즈니스 마이크로 서비스 관점에서 생각해 보면, Service Fabric 상태 저장 Reliable Service를 구현할 때 일반적으로 두 가지 서비스 계층을 구현해야 합니다. 첫 번째는 여러 개의 파티션(각 파티션은 상태 저장 서비스)을 처리하는 백 엔드 상태 저장 신뢰할 수 있는 서비스입니다. 두 번째는 다중 파티션 또는 상태 저장 서비스 인스턴스에서 라우팅 및 데이터 집계를 담당하는 프런트 엔드 서비스 또는 Gateway 서비스입니다. 또한 이 Gateway 서비스는 백 엔드 서비스에 액세스하는 재시도 루프로 클라이언트 쪽 통신을 처리합니다.
사용자 지정 서비스를 구현하거나, 기본 제공 Service Fabric [역방향 프록시 서비스](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy)를 사용할 수 있는 경우 Gateway 서비스라고 합니다.

![](./media/image31.png)

**그림 4-27**. 여러 상태 저장 서비스 인스턴스 및 사용자 지정 게이트웨이 프런트 엔드가 있는 비즈니스 마이크로 서비스

어떤 경우든, Service Fabric 상태 저장 Reliable Services를 사용하면, 일반적으로 여러 물리적 서비스로 구성된 논리적 또는 비즈니스 마이크로 서비스(바인딩된 컨텍스트)가 있습니다. 각각의 Gateway 서비스 및 Partition 서비스를 그림 4-26과 같이 ASP.NET Web API 서비스로 구현할 수 있습니다.

Service Fabric에서는 오케스트레이터 또는 클러스터의 패키징 및 배포 단위인 [Service Fabric 응용 프로그램](https://docs.microsoft.com/azure/service-fabric/service-fabric-application-model)으로 서비스 그룹을 그룹화 및 배포할 수 있습니다. 따라서 Service Fabric 응용 프로그램을 이 자치 비즈니스 및 논리적 마이크로 서비스 경계 또는 바인딩된 컨텍스트에도 매핑할 수 있으므로 이러한 서비스를 자율적으로 배포할 수 있습니다.

## <a name="service-fabric-and-containers"></a>Service Fabric 및 컨테이너

Service Fabric의 컨테이너와 관련해서는 Service Fabric 클러스터 내의 컨테이너 이미지에 서비스를 배포할 수도 있습니다. 그림 4-28에서 보듯이 대부분의 경우 서비스당 하나의 컨테이너만 존재하게 됩니다.

![](./media/image32.png)

**그림 4-28**. Service Fabric에 여러 서비스(컨테이너)가 있는 비즈니스 마이크로 서비스

그러나 Service Fabric에서는 소위 “사이드카” 컨테이너(논리적 서비스의 일부로 함께 배포해야 하는 두 개의 컨테이너)도 가능합니다. 중요한 것은 비즈니스 마이크로 서비스가 여러 응집 요소 주위의 논리적 경계라는 것입니다. 대부분의 경우, 단일 데이터 모델을 사용하는 단일 서비스일 수 있지만 일부 다른 경우에는 여러 개의 물리적 서비스가 있을 수도 있습니다.

2017년 중반부터, Service Fabric에서는 SF 상태 저장 Reliable Services를 컨테이너에 배포할 수 없으며 상태 비저장 서비스와 행위자 서비스만 컨테이너에 배포할 수 있습니다. 그러나 그림 4-29와 같이 동일한 Service Fabric 응용 프로그램에서 컨테이너의 서비스와 프로세스의 서비스를 혼합할 수 있습니다.

![](./media/image33.png)

**그림 4-29**. 컨테이너 및 상태 저장 서비스와 함께 Service Fabric 응용 프로그램에 매핑된 비즈니스 마이크로 서비스

Azure Service Fabric에서 컨테이너 지원에 대한 자세한 내용은 [Service Fabric 및 컨테이너](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview)를 참조하세요.

## <a name="stateless-versus-stateful-microservices"></a>상태 비저장 및 상태 저장 마이크로 서비스

앞에서 설명한 대로, 각 마이크로 서비스(논리적 바인딩된 컨텍스트)는 고유한 도메인 모델(데이터 및 논리)을 소유해야 합니다. 상태 비저장 마이크로 서비스의 경우, 데이터베이스는 SQL Server와 같은 관계형 옵션, MongoDB 또는 Azure Cosmos DB와 같은 NoSQL 옵션을 사용하여 외부 데이터베이스가 됩니다.

그러나 서비스 자체는 Service Fabric에서도 상태가 유지될 수 있습니다. 즉, 데이터가 마이크로 서비스 내에 있습니다. 이 데이터는 동일한 서버에 있을 뿐만 아니라 마이크로 서비스 프로세스, 메모리 내에 있으며 하드 드라이브에 보관되어 다른 노드에 복제될 수 있습니다. 그림 4-30은 다양한 방식을 보여 줍니다.

![](./media/image34.png)

**그림 4-30**. 상태 비저장 및 상태 저장 마이크로 서비스

상태 비저장 방식은 완벽하게 유효하며 기존의 잘 알려진 패턴과 유사하기 때문에 상태 저장 마이크로 서비스보다 쉽게 구현할 수 있습니다. 그러나 상태 비저장 마이크로 서비스는 프로세스와 데이터 원본 간에 대기 시간을 둡니다. 또한 캐시 및 대기열을 추가하여 성능을 향상시키려는 경우 더욱 복잡해집니다. 결과적으로 너무 많은 계층을 가진 복잡한 아키텍처로 끝날 수 있습니다.

반대로 [상태 기반 마이크로 서비스](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis)는 도메인 논리와 데이터 간에 대기 시간이 없기 때문에 고급 시나리오에서 뛰어납니다. 대량의 데이터 처리, 게임 백 엔드, 서비스 형태의 데이터베이스 및 기타 대기 시간이 적은 시나리오는 모두 상태 저장 서비스를 활용하여 로컬 상태에서 더 빠르게 액세스할 수 있습니다.

상태 비저장 및 상태 저장 서비스는 보완적입니다. 예를 들어, 그림 4-30의 오른쪽 다이어그램을 보면 상태 저장 서비스를 여러 파티션으로 분할할 수 있습니다. 이러한 파티션에 액세스하려면 파티션 키를 기반으로 각 파티션의 주소를 지정하는 방법을 알고 있는 게이트웨이 서비스로 작동하는 상태 비저장 서비스가 필요할 수 있습니다.

상태 저장 서비스에는 단점이 있습니다. 규모 확장을 허용하는 복잡성 수준을 내포합니다. 일반적으로 외부 데이터베이스 시스템에 의해 구현되는 기능은 상태 저장 마이크로 서비스 간 데이터 복제 및 데이터 분할과 같은 작업을 위해 처리되어야 합니다. 그러나 이것은 [상태 저장 신뢰할 수 있는 서비스](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis)가 있는 [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-platform-architecture)과 같은 오케스트레이터가 [Reliable Services API](https://docs.microsoft.com/azure/service-fabric/service-fabric-work-with-reliable-collections) 및 [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction)를 사용하여 상태 저장 마이크로 서비스의 개발 및 수명 주기를 단순화함으로써 지원할 수 있는 분야 중 하나입니다.

상태 저장 서비스를 허용하고 Actor 패턴을 지원하며 비즈니스 논리와 데이터 간의 내결함성과 대기 시간을 향상시키는 기타 마이크로 서비스 프레임워크로는 Microsoft Research의 Microsoft [Orleans](https://github.com/dotnet/orleans) 및 [Akka.NET](https://getakka.net/)이 있습니다. 두 프레임워크는 현재 Docker에 대한 지원을 개선 중입니다.

Docker 컨테이너 자체는 상태 비저장입니다. 상태 저장 서비스를 구현하려면 앞에서 언급한 추가 규범 및 상위 수준 프레임워크 중 하나가 필요합니다. 

>[!div class="step-by-step"]
[이전] (scalable-available-multi-container-microservice-applications.md) [다음] (../docker-application-development-process/index.md)
