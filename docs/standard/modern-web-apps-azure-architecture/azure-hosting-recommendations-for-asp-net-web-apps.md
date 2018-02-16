---
title: "Azure 호스팅 ASP.NET Core 웹 앱에 대 한 권장 사항"
description: "ASP.NET Core와 Azure의 최신 웹 응용 프로그램을 설계 | Azure 호스팅 ASP.NET 웹 앱에 대 한 권장 사항"
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 868f1b7ce452be9e29b921888f90d128e074ba13
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="azure-hosting-recommendations-for-aspnet-core-web-apps"></a>Azure 호스팅 ASP.NET Core 웹 앱에 대 한 권장 사항

> "업무의 everywhere는 IT 부서에서 클라우드 (즉, SaaS)에서 응용 프로그램 가져오기 무시 및 잡지 구독과 처럼을 지불 합니다. 및 서비스가 더 이상 필요한 경우 왼쪽 모서리에 사용 하지 않는 없는 장비와 구독을 취소할 수 없습니다. "  
> _\- Daryl Plummer, Gartner의 분석가_

## <a name="summary"></a>요약

모든 응용 프로그램의 요구 사항 및 아키텍처에 Windows Azure에서 지 원하는 합니다. 호스팅 요구 사항 수십 가지 서비스가 이루어진 매우 복잡 한 응용 프로그램에 정적 웹 사이트 처럼 간단할 수 있습니다. ASP.NET Core 모놀리식 웹 응용 프로그램 및 지원 서비스에 대 한 권장 되는 여러 개의 잘 알려진 구성이 있습니다. 다음과 같은 권장 사항은 호스팅될, 여부 대 한 모든 응용 프로그램, 개별 프로세스 또는 데이터 리소스의 종류에 따라 그룹화 됩니다.

## <a name="web-applications"></a>웹 응용 프로그램

웹 응용 프로그램으로 호스팅할 수 있습니다.

-   앱 서비스 웹 앱

-   컨테이너

-   Azure Service Fabric

-   가상 컴퓨터 (Vm)

이 중에서 응용 프로그램 서비스 웹 앱은 대부분의 시나리오에 대 한 권장된 접근 방법입니다. 마이크로 서비스 아키텍처에 대 한 컨테이너 기반 접근 방식을 또는 서비스 패브릭 것이 좋습니다. 응용 프로그램을 실행 하는 컴퓨터에 더 많은 제어 해야 할 경우 Azure 가상 컴퓨터를 고려 합니다.

### <a name="app-service-web-apps"></a>앱 서비스 웹 앱

앱 서비스 웹 앱은 웹 응용 프로그램 호스팅에 대 한 액세스에 최적화 된 완전히 관리 되는 플랫폼을 제공 합니다. 실행 하 고 앱의 크기를 조정 하는 데 필요한 Azure 인프라를 담당 하는 동안 비즈니스 논리에 집중할 수 있도록은 제공 platform-as-a-service(PaaS) 이며 앱 서비스 웹 앱의 몇 가지 주요 기능:

-   DevOps 최적화 (연속 통합 및 배달, 다양 한 환경, A / B 테스트, 스크립팅 지원)

-   세계적인 규모 및 고가용성

-   SaaS 플랫폼 및 온-프레미스 데이터에 대 한 연결

-   보안 및 규정 준수

-   Visual Studio 통합

Azure 앱 서비스는 대부분의 웹 응용 프로그램에 적합 합니다. 배포 및 관리 플랫폼에 통합 되어, 사이트 트래픽 부하를 처리할 신속 하 게 확장할 수 있습니다 및 기본 제공 부하 분산 및 트래픽 관리자는 고가용성을 제공 합니다. 온라인 마이그레이션 도구를 사용 하 여 손쉽게 기존 사이트 Azure 앱 서비스를 웹 응용 프로그램 갤러리에서 오픈 소스 응용 프로그램을 사용 하거나 프레임 워크 및 사용자가 원하는 도구를 사용 하 여 새 사이트를 만들 이동할 수 있습니다. Webjob 기능을 사용 하면 쉽게 응용 프로그램 서비스 웹 앱을 처리 하는 백그라운드 작업을 추가할 수 있습니다.

### <a name="containers-and-azure-container-service"></a>컨테이너와 컨테이너를 Azure 서비스

Azure 컨테이너 서비스를 사용 하면 보다 간단 하 게 생성, 구성 및 클러스터 화 된 응용 프로그램을 실행 하는 미리 구성 된 가상 컴퓨터를 관리할 수 있습니다. 인기 있는 오픈 소스 일정 예약 및 오케스트레이션 도구는 최적화 된 구성을 사용합니다. 이렇게 하면 기존 기술을 사용 하거나 크기가 크고 점점 본문의 커뮤니티 전문 배포 하 고 Microsoft Azure에서 컨테이너 기반 응용 프로그램 관리를 활용할 수 있습니다.

Azure 컨테이너 서비스를 사용 하면 보다 간단 하 게 생성, 구성 및 클러스터 화 된 응용 프로그램을 실행 하는 미리 구성 된 가상 컴퓨터를 관리할 수 있습니다. 인기 있는 오픈 소스 일정 예약 및 오케스트레이션 도구는 최적화 된 구성을 사용합니다. 이렇게 하면 기존 기술을 사용 하거나 크기가 크고 점점 본문의 커뮤니티 전문 배포 하 고 Microsoft Azure에서 컨테이너 기반 응용 프로그램 관리를 활용할 수 있습니다.

Azure 컨테이너 서비스의 단일 목표는 현재 Microsoft의 고객 간에 널리 사용 되는 기술과 오픈 소스 도구를 사용 하는 컨테이너 호스팅 환경을 제공 하는 것입니다. 이 위해 Azure 컨테이너 서비스 (예: DC/OS, docker는 Docker Swarm 또는 Kubernetes) 하 여 선택한 orchestrator에 대 한 표준 API 끝점을 노출합니다. 이러한 끝점을 사용 하 여 해당 끝점 통신할 수 있는 모든 소프트웨어를 활용할 수 있습니다. 예를 들어 docker는 Docker Swarm 끝점의 경우 Docker 명령줄 인터페이스 (CLI)를 사용 하도록 선택할 수 있습니다. DC/OS 용 DCOS CLI를 선택할 수 있습니다. Kubernetes, kubectl를 선택할 수 있습니다. 그림 11-1에서는 이러한 끝점을 사용 하는 컨테이너 클러스터를 관리 하는 방법을 보여 줍니다.

![](./media/image11-1.png)

**그림 11-1입니다.** Docker, Kubernetes, 또는 DC/OS 끝점과 함께 azure 컨테이너 서비스 관리.

### <a name="azure-service-fabric"></a>Azure Service Fabric

서비스 패브릭은 새 응용 프로그램을 만들거나 마이크로 서비스 아키텍처를 사용 하는 기존 응용 프로그램을 다시 작성 하는 경우에 적합 한 선택입니다. 에 컴퓨터의 공유 풀에서 실행 되는 앱 작은 항목부터 시작 하 고 대규모 수백 또는 수천 대 컴퓨터 필요에 따라 증가할 수 있습니다. 상태 저장 서비스 쉽게 일관 되 고 안정적으로 응용 프로그램 상태를 저장 하 고 서비스 패브릭에서 자동으로 관리 서비스를 분할 배율 및 가용성 드립니다. 서비스 패브릭.NET (OWIN) 및 ASP.NET Core WebAPI 열린 웹 인터페이스를 지원합니다. 앱 서비스에 비해, 서비스 패브릭도 제공 더 많은 제어를 기본 인프라에 대 한 직접 액세스 합니다. 서버 시작 작업을 구성 하거나 원격 서버에 수 있습니다.

### <a name="azure-virtual-machines"></a>Azure Virtual Machines

앱 서비스 또는 서비스 패브릭에서 실행 하려면 상당한 수정 해야 하는 기존 응용 프로그램의 경우에 클라우드로 마이그레이션의 간소화 하기 위해 가상 컴퓨터를 선택할 수 있습니다. 그러나 제대로 구성, 보안, 및 유지 관리 Vm 필요 훨씬 더 많은 시간 및 Azure 앱 서비스 및 서비스 패브릭 비교 하는 IT 전문 합니다. Azure 가상 컴퓨터를 고려 하는 경우에 패치, 업데이트 및 VM 환경을 관리 하는 데 필요한 지속적인 유지 관리 작업을 고려 하 고 있는지 확인 합니다. 앱 서비스 및 서비스 패브릭 플랫폼으로-서비스 (Paas)는 azure 가상 컴퓨터 인프라-as a Service (IaaS)를입니다.

#### <a name="feature-comparison"></a>기능 비교

| 앱 서비스 기능 | 서비스 패브릭 | 가상 컴퓨터 |
|---------|----------|----------|
| 거의 즉각적인 배포 | X | X | |
| 재배포 하지 않고 대형 컴퓨터까지 확장 | X | X | |
| 인스턴스가 공유 콘텐츠 및 구성 합니다. 다시 배포 또는 확장 시 재구성 필요가 없습니다 | X | X | |
| 여러 배포 환경 (프로덕션, 준비) | X | X | |
| 자동 OS 업데이트 관리 | X | | |
| 원활한 32/64 비트 플랫폼 간 전환 | X | | |
| Git, FTP 통해 코드 배포 | X | | X |
| 웹 배포를 통해 코드 배포 | X | | X |
| TFS 통해 코드 배포 | X | X | X |
| 호스트 웹 또는 다중 계층 아키텍처의 웹 서비스 계층 | X | X | X |
| 서비스 버스, 저장소, SQL 데이터베이스와 같은 Azure 서비스에 액세스 | X | X | X |
| 모든 사용자 지정 MSI 설치 | | X | X |

## <a name="logical-processes"></a>논리적 프로세스

응용 프로그램의 나머지 부분에서 분리 될 수 있는 개별 논리 프로세스 수 별도로 배포할 수 Azure 함수에 "서버가 없는" 방식입니다. Azure 함수를 사용 하면 응용 프로그램 또는 인프라를 실행 하는 방법에 대 한 걱정 없이 필요한 특정된 문제에 대 한 코드 작성 하므로 수 있습니다. 다양 한 C를 포함 하는 프로그래밍 언어 중에서 선택할 수 있습니다\#, F\#, Node.js, Python 및 PHP를 현재 작업에 대 한 가장 생산적인 언어를 선택할 수 있습니다. 대부분의 클라우드 기반 솔루션와 마찬가지로 시간에 대해서만 지불 하 고 사용 하 고 필요에 따라 수직 Azure 함수를 신뢰할 수 있습니다.

## <a name="data"></a>데이터

Azure 응용 프로그램에 데이터에 대 한 적절 한 데이터 공급자를 사용할 수 있도록 다양 한 데이터 저장소 옵션을 제공 합니다.

트랜잭션, 관계형 데이터에 대 한 Azure SQL 데이터베이스는 가장 적합 한 옵션입니다. 고성능 대부분 읽기 전용인 데이터에 대 한 Azure SQL 데이터베이스에서 지 원하는 Redis cache는 것이 좋습니다.

여러 가지 방법으로, Blob 또는 Azure 저장소의 테이블에 SQL 데이터베이스 열에서 DocumentDB에 구조화 되지 않은 JSON 데이터를 저장할 수 있습니다. 이 중에서 DocumentDB 기능을 쿼리 하는 최상의 있으며 다 수의 쿼리를 지원 해야 하는 JSON 기반 문서에 대 한 권장된 옵션입니다.

응용 프로그램 동작을 오케스트레이션 하는 데 사용 하는 일시적인 명령 또는 이벤트 기반 데이터는 Azure 서비스 버스 또는 Azure 저장소 큐 사용 수 있습니다. Azure 저장소 버스 더 많은 유연성을 제공 하 고는 응용 프로그램 간 및 내에서 특수 메시징에 대 한 권장된 서비스입니다.

## <a name="architecture-recommendations"></a>아키텍처 권장 사항

응용 프로그램의 요구 사항을 아키텍처를 결정 해야 합니다. 사용 가능한 선택 적합 한 중요 한 결정은 여러 다른 Azure 서비스 있습니다. Microsoft는 일반적인 시나리오에 맞게 최적화 하는 일반적인 아키텍처를 식별 하려면 참조 아키텍처의 갤러리를 제공 합니다. 응용 프로그램의 요구 사항에 밀접 하 게 또는 지도 이상 시작점을 제공 하는 참조 아키텍처에 바인딩할 수 있습니다.

그림 11-2는 예제 참조 아키텍처를 보여 줍니다. 이 다이어그램에서는 마케팅 부서에 대 한 액세스에 최적화 된 Sitecore 콘텐츠 관리 시스템 웹 사이트에 대 한 권장된 아키텍처 접근 방식을 설명 합니다.

![](./media/image11-2.png)

**그림 11-2입니다.** 웹 사이트 참조 아키텍처 마케팅 Sitecore입니다.

**참조-Azure 호스팅 권장 사항**

-   Azure 솔루션 Architectures\
    <https://azure.microsoft.com/solutions/architecture/>

-   Azure 개발자 Guide\
    <https://azure.microsoft.com/campaigns/developer-guide/>

-   Azure 앱 서비스란? \ \
    <https://docs.microsoft.com/azure/app-service/app-service-value-prop-what-is>

-   Azure 앱 서비스, 가상 컴퓨터, 서비스 패브릭 및 클라우드 서비스 Comparison\
    <https://docs.microsoft.com/azure/app-service-web/choose-web-site-cloud-service-vm>

>[!div class="step-by-step"]
[이전] (개발-프로세스-에-azure.md)
