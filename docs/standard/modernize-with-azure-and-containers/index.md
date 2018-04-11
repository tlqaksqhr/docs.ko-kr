---
title: Azure 클라우드 및 Windows 컨테이너를 사용하여 기존 .NET 응용 프로그램 현대화
description: 기존 응용 프로그램을 Azure 클라우드 및이 전자책 (영문)를 사용 하 여 컨테이너를 이동 하에 대해 알아봅니다.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ba48579735379bfc857993cd1546f5f7125101f4
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2018
---
# <a name="modernize-existing-net-applications-with-azure-cloud-and-windows-containers-v10"></a>Azure 클라우드 및 Windows 컨테이너를 사용하여 기존 .NET 응용 프로그램 현대화(v1.0)

![표지 이미지](./media/cover.png)

게시자:  
Microsoft Press 및 Microsoft DevDiv  
Microsoft Corporation의 사업부  
One Microsoft Way  
Redmond, Washington 98052-6399  

Copyright © 2017 by Microsoft Corporation  

All rights reserved. 이 가이드의 내용 중 어떤 부분도 게시자의 서면 허가 없이는 어떠한 형식이나 방법으로도 복제할 수 없습니다.

이 가이드는 전자책 (전자책) http://dot.net/architecture 등 microsoft 여러 채널을 통해 사용할 수 있는 형태의 무료로 제공 됩니다.

이 책에 관한 질문이 있는 경우 [dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com?subject=Feedback%20for%20.NET%20Container%20&%20Microservices%20Architecture%20book)으로 이메일을 보내 주세요.

이 가이드는 작성자의 견해와 의견을 "있는 그대로" 제공하고 전달합니다. 뷰, 의견 및 표현 URL 및 기타 인터넷 웹 사이트 참조를 포함 하 여이 가이드의 내용은 예 고 없이 변경 될 수 있습니다.

여기에 설명된 일부 예제는 예시 용도로만 제공되며 실제 데이터가 아닙니다. 실제로 연관시키거나 관련시키려고 의도하거나 추론해서는 안 됩니다.

"상표" 웹 페이지의 http://www.microsoft.com에 나열된 Microsoft 및 상표는 Microsoft 그룹 계열사의 상표입니다. 기타 모든 표시는 해당 소유자의 자산입니다.

만든 이:
> **Cesar de la Torre**, 선임 PM, Microsoft Corp. .NET 제품 팀

참가자 및 검토자:
> **Scott Hunter**, 파트너 PM 책임자, Microsoft .NET 팀  
> **Paul Yuknewicz**, 수석 PM 관리자, Microsoft Visual Studio Tools 팀  
> **Lisa Guthrie**, 선임 PM, Microsoft Visual Studio Tools 팀  
> **Ankit Asthana**, 수석 PM 관리자, Microsoft .NET 팀  
> **Unai Zorrilla**, 수석 개발자, Plain Concepts  
> **Javier Valero**, 최고 운영 책임자, Grupo Solutio  

## <a name="introduction"></a>소개

웹 응용 프로그램을 현대화하고 클라우드로 이동하려는 경우 앱을 꼭 완전히 다시 설계할 필요는 없습니다. 비용과 시간 제한으로 인해 마이크로 서비스 같은 고급 방법을 사용하여 응용 프로그램을 재설계하는 것이 항상 좋은 방법은 아닙니다. 응용 프로그램의 유형에 따라 응용 프로그램을 다시 설계할 필요가 없을 수도 있습니다. 조직의 클라우드 마이그레이션 전략 비용 효율성을 최적화하려면 비즈니스 요구 사항과 앱 요구 사항을 고려해야 합니다. 다음을 파악해야 합니다.

- 변환 또는 재설계가 필요한 앱.

- 부분적으로만 현대화해야 하는 앱.

- 클라우드에 바로 "리프트 앤 시프트"할 수 있는 앱.

## <a name="about-this-guide"></a>이 가이드의 내용

이 가이드에서는 주로 "리프트 앤 시프트" 시나리오와 기존 Microsoft.NET Framework 웹 또는 서비스 기반 응용 프로그램의 초기 현대화에 중점을 둡니다. 리프트 앤 시프트란 응용 프로그램의 코드 및 기본 아키텍처를 변경하지 않고최신 또는 더 현대적인 환경으로 워크로드를 이동하는 작업입니다.

이 가이드에서는 응용 프로그램 전체를 다시 설계하거나 다시 코딩하지 않고 특정 영역을 현대화하여 기존 .NET Framework 서버-응용 프로그램을 클라우드에 바로 이동하는 방법을 설명합니다.

이 가이드에서는 또한 Windows 컨테이너 및 Azure 오케스트레이터 같은 새로운 기술 및 아키텍처의 특정 집합을 사용하여 클라우드로 앱을 이동하고 앱을 부분적으로 현대화할 경우의 이점을 중점적으로 설명합니다.

## <a name="path-to-the-cloud-for-existing-net-applications"></a>기존.NET 응용 프로그램을 클라우드로 이동하는 경로

조직에서는 일반적으로 응용 프로그램에 민첩성과 속도를 구현하기 위해 클라우드로 이동하기로 선택합니다. 온-프레미스 서버를 설치하는 데 일반적으로 몇 주가 걸리는 데 비해, 클라우드에는 몇 분 안에 수천 대의 서버(VM)를 설치할 수 있습니다.

클라우드로 응용 프로그램을 마이그레이션하는 방법에 대한 단일 만능 전략은 없습니다. 귀하에게 적합한 마이그레이션 전략은 귀사의 요구 사항과 우선 순위, 마이그레이션하는 응용 프로그램의 종류에 따라 달라집니다. 모든 응용 프로그램이 서비스 제공 플랫폼([PaaS](https://azure.microsoft.com/overview/what-is-paas/)) 모델로의 전환이나 [클라우드 전용](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) 응용 프로그램 모델 개발에 대한 투자를 보증하는 것은 아닙니다. 대다수의 경우 비즈니스 요구 사항에 따라 단계식 또는 증분 접근법을 사용하여 클라우드로의 자산 전환에 투자할 수 있습니다.

조직에 장기적인 최고의 민첩성과 가치를 제공하는 현대식 응용 프로그램의 경우 *클라우드 최적화* 및 *클라우드 전용* 응용 프로그램 아키텍처에 투자하면 이점을 얻을 수 있습니다. 하지만 기존 자산에 속하는 응용 프로그램의 경우 상당한 이점을 얻기 위한 핵심은 (재설계나 코드 변경 없이) 최소한의 시간과 비용을 들여 클라우드로 이동하는 것입니다.

그림 1-1에서는 증분 단계로 기존.NET 응용 프로그램을 클라우드로 이동하는 경우에 취할 수 있는 경로를 보여 줍니다.

 ![기존 .NET 응용 프로그램 및 서비스의 현대화 경로](./media/image1-1.png)

> **그림 1-1**. 기존 .NET 응용 프로그램 및 서비스의 현대화 경로

각 마이그레이션 방법마다 이점과 사용해야 할 이유가 다릅니다. 클라우드에 앱을 마이그레이션하는 경우 단일 접근법을 선택하거나 여러 접근법 중에서 특정 구성 요소를 선택할 수 있습니다. 개별 응용 프로그램이 단일 접근법이나 완성 상태로 제한되는 것은 아닙니다. 예를 들어, 일반적인 하이브리드 접근법은 특정 온-프레미스 구성 요소와 다른 클라우드 구성 요소를 사용합니다.

처음 두 마이그레이션 수준에서 응용 프로그램을 리프트 앤 시프트할 수 있습니다.

**수준 1: 클라우드 인프라 지원**: 이 마이그레이션 접근법에서는 현재 온-프레미스 응용 프로그램을 서비스 제공 인프라([IaaS](https://azure.microsoft.com/overview/what-is-iaas/)) 플랫폼으로 다시 호스팅하거나 이동합니다. 앱의 구성은 전과 거의 동일하지만 이제 클라우드의 VM에 앱을 배포합니다.

**수준 2: 클라우드 DevOps 지원**: 초기 리프트 앤 시프트가 끝난 이 수준에서는 여전히 재설계나 코드 변경 없이 클라우드에서 앱을 실행하여 훨씬 더 많은 이점을 얻을 수 있습니다. 기업 개발 운영(DevOps) 프로세스를 세분화하여 응용 프로그램의 민첩성을 개선함으로써 더 빨리 배송할 수 있습니다. 이는 Docker Engine에 기반을 둔 Windows 컨테이너 같은 기술을 사용하여 구현할 수 있습니다. 여러 단계로 배포하는 경우 응용 프로그램 종속성으로 인한 마찰을 컨테이너가 제거합니다. 또한 컨테이너 추가 클라우드 관리 서비스와 관련 된 데이터, 모니터링 및 연속 통합/연속 배포 (CI/CD) 파이프라인을 사용 합니다.

세 번째 완성도는 클라우드의 궁극적 목표이지만 여러 앱에는 선택적이며 이 가이드의 주요 초점은 아닙니다.

**수준 3: 클라우드 최적화**: 이 마이그레이션 방법은 일반적으로 비즈니스 요구 사항에 따라 좌우되며 중요 업무용 응용 프로그램 현대화를 대상으로 합니다. 이 수준에서는 PaaS 서비스를 사용하여 PaaS 컴퓨팅 플랫폼으로 앱을 이동합니다. [클라우드 전용](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) 응용 프로그램 및 마이크로 서비스 아키텍처를 구현하여 장기적인 민첩성으로 응용 프로그램을 진화시키고 새로운 한계로 확장합니다. 이 유형의 현대화는 일반적으로 클라우드를 위한 특별한 설계가 필요합니다. 특히 클라우드 전용 응용 프로그램 및 마이크로 서비스 기반 모델로 이동하는 경우 새 코드를 작성해야 하는 경우가 많습니다. 이 방법은 모놀리식 및 온-프레미스 응용 프로그램 환경에서 달성하기 어려운 이점을 얻는 데 도움이 될 수 있습니다.

표 1-1에서는 각 마이그레이션 또는 현대화 방법을 선택하는 이유와 주요 이점을 설명합니다.

| **클라우드 인프라 지원** <br /> *리프트 앤 시프트* | **클라우드 DevOps 지원** <br /> *리프트 앤 시프트* | **클라우드 최적화** *현대화/리팩터링/다시 생성* |
|---|---|---|
| **응용 프로그램의 계산 대상** |
| Azure의 VM에 배포된 응용 프로그램 | VM, Azure Service Fabric 또는 Azure Container Service(즉, Kubernetes)에 배포된 컨테이너화된 모놀리식 또는 N 계층 앱 | Azure App Service, Azure Service Fabric, Azure Container Service(즉, Kubernetes)의 PaaS에 기반을 둔 컨테이너화된 마이크로 서비스 또는 일반 응용 프로그램 |
| **데이터 대상** |
| SQL 또는 VM의 모든 관계형 데이터베이스 | Azure SQL Database 관리되는 인스턴스 | Azure SQL Database, Azure Cosmos DB 또는 기타 NoSQL |
| **장점**|
| <li>재설계, 새 코드 필요 없음 <li> 최소한의 작업으로 빠른 마이그레이션 가능 <li> Azure에서 지원되는 최소 공통 분모 <li> 기본 가용성 보장 <li> 클라우드로 이동한 후 훨씬 더 쉽게 현대화 | <li>재설계, 새 코드 필요 없음 <li> 컨테이너가 VM에 대한 소규모 증분 활동 제공 <li> 컨테이너로 인해 향상된 배포 및 DevOps 릴리스 민첩성 <li> 밀도 증가 및 배포 비용 감소 <li> 앱 이식성 및 종속성 <li> Azure Container Service(또는 Kubernetes)와 Azure Service Fabric으로 고가용성 및 오케스트레이션 제공 <li> Service Fabric에서 노드/VM 패치 <li> 대상 호스트의 유연성: Azure 컨테이너 서비스 (또는 Kubernetes) 가상 컴퓨터 또는 Azure Vm 크기 조정 설정 서비스 패브릭 및 향후 컨테이너 기반 선택 | <li>클라우드 설계자, 리팩터링, 새 코드 필요 <li> 마이크로 서비스 클라우드 전용 접근법 <li> 새 웹앱, 모놀리식, N 계층, 클라우드 복원 및 클라우드 최적화 <li> 완전히 관리되는 서비스 <li> 자동 패치 <li> 규모에 최적화 <li> 하위 시스템의 자율적인 민첩성을 위해 최적화 <li> 배포 및 DevOps 기반 <li> 슬롯 및 배포 전략 같은 향상된 DevOps <li> PaaS 및 오케스트레이터 대상: Azure App Service, Azure Container Service(또는 Kubernetes), Azure Service Fabric 및 향후 컨테이너 기반 PaaS |
| **당면 과제** |
| <li> 운영 경비 변화 또는 데이터 센터 폐쇄가 아닌 클라우드 가격 축소 <li> 관리 부담이 극히 적음: Terraform, Spinnaker 또는 Puppet 같은 인프라 솔루션 덕분에 OS 또는 미들웨어가 필요 없음 | <li> 컨테이너화는 학습 곡선의 추가 단계이고 변경이 불가능 | <li> 중대한 코드 리팩터링 또는 재작성이 필요할 수 있음(시간 및 예산 증가) |
> **표 1-1.** 기존 .NET 응용 프로그램 및 서비스의 현대화 경로 이점 및 당면 과제

### <a name="key-technologies-and-architectures-by-maturity-level"></a>완성도별 핵심 기술 및 아키텍처

.NET Framework 응용 프로그램은 2001년 후반에 출시된 .NET Framework 버전 1.0으로 처음 시작되었습니다. 그런 다음 회사에서 최신 버전을 출시했습니다(예: 2.0, 3.5 및 .NET 4.x). 해당 응용 프로그램의 대부분 Windows Server 및 인터넷 정보 서버 (IIS)에서 실행 되 고 SQL Server, Oracle, MySQL 또는 다른 RDBMS와 같은 관계형 데이터베이스 사용.

요즘 기존 .NET 응용 프로그램은 .NET Framework 4.x 또는 .NET Framework 3.5에 기반을 두고 있으며, ASP.NET MVC, ASP.NET Web Forms, ASP.NET Web API, Windows Communication Foundation(WCF), ASP.NET SignalR 및 ASP.NET Web Pages 같은 웹 프레임워크를 사용합니다. 이러한 기존의 .NET Framework 기술은 Windows에 종속됩니다. 레거시 앱만 마이그레이션하고 응용 프로그램 인프라에 대한 변경 사항을 최소화하고자 하는 경우에는 이러한 종속성을 고려하는 것이 중요합니다.

그림 1-2에서는 각각의 세 가지 클라우드 완성도별로 사용되는 주요 기술과 아키텍처 스타일을 보여 줍니다.

![기존 .NET 웹 응용 프로그램 현대화의 각 완성도에 해당하는 주요 기술](./media/image1-2.png)

> **그림 1-2.** 기존 .NET 웹 응용 프로그램 현대화의 각 완성도에 해당하는 주요 기술

그림 1-2는 가장 일반적인 시나리오를 보여주지만 아키텍처에 관해서는 여러 하이브리드 및 혼합된 변형 형태가 가능합니다. 예를 들어 완성 모델은 기존 웹앱의 모놀리식 아키텍처에만 적용되는 것이 아니라 서비스 방향, N 계층 및 다른 아키텍처 스타일 변형에도 적용됩니다.

현대화 프로세스의 각 완성도는 다음 핵심 기술 및 접근법과 연관이 있습니다.

- **클라우드 인프라 지원**(재호스팅 또는 기본 리프트 앤 시프트): 대다수의 조직에서는 첫 단계로 클라우드 마이그레이션 전략만 신속하게 실행하려고 합니다. 이 경우 응용 프로그램이 다시 호스팅됩니다. 대부분의 재호스팅은 [Azure Site Recovery](https://azure.microsoft.com/services/site-recovery/) 및 [Azure Database Migration Service](https://azure.microsoft.com/campaigns/database-migration/) 같은 클라우드 도구 기반의 Azure로 마이그레이션하는 데 도움이 되는 지침, 정보 및 메커니즘을 제공하는 서비스인 [Azure Migrate](https://aka.ms/azuremigrate)를 사용하여 자동화할 수 있습니다. 레거시 앱을 클라우드로 이동할 때 자산에 대한 인프라 세부 정보를 파악할 수 있도록 수동으로 재호스팅을 설정할 수도 있습니다. 예를 들어 매우 적은 수정(사소한 구성 변경)만으로 응용 프로그램을 VM으로 이동할 수 있습니다. 이 경우 네트워킹은 온-프레미스 환경과 비슷합니다. Azure에서 가상 네트워크를 만드는 경우에 특히 비슷합니다.

- **클라우드 DevOps 지원**(향상된 리프트 앤 시프트): 이 모델은 응용 프로그램의 핵심 아키텍처를 변경하지 않고 클라우드에서 상당한 이점을 얻을 수 있도록 몇 가지 중요한 배포 최적화를 수행하는 방법에 대한 것입니다. 여기서 기본 단계는 기존의 .NET Framework 응용 프로그램에 [Windows 컨테이너](https://docs.microsoft.com/virtualization/windowscontainers/about/) 지원을 추가하는 것입니다. 이러한 중요 단계(컨테이너화)에서는 코드를 건드리지 않아도 되므로 전반적인 리프트 앤 시프트 작업이 매우 가볍습니다. [Image2Docker](https://github.com/docker/communitytools-image2docker-win) 또는 Visual Studio 같은 도구와 [Docker](https://www.docker.com/)용 도구를 사용할 수 있습니다. Visual Studio는 ASP.NET 응용 프로그램 및 Windows 컨테이너 이미지에 대한 스마트 기본값을 자동으로 선택합니다. 이러한 도구는 신속한 내부 루프와 Azure로 컨테이너를 가져올 수 있는 빠른 경로를 제공합니다. 여러 환경에 배포할 때 민첩성이 향상됩니다. 그런 다음 프로덕션으로 이동하여 [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/) 또는 [Azure Container Service](https://azure.microsoft.com/services/container-service/)(Kubernetes, DC/OS 또는 Swarm) 같은 오케스트레이터에 Windows 컨테이너를 배포할 수 있습니다. 이 초기 현대화 중에 [Azure Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview) 같은 도구를 사용한 모니터링, [Visual Studio Team Services](https://www.visualstudio.com/team-services/)를 사용하는 앱 수명 주기에 대한 CI/CD 파이프라인, Azure에 제공되는 여러 데이터 리소스 서비스와 같은 클라우드의 자산을 추가할 수도 있습니다. 예를 들어 원래 기존의 [ASP.NET Web Forms](https://www.asp.net/web-forms) 또는 [ASP.NET MVC](https://www.asp.net/mvc)를 사용하여 개발되었지만 이제 Windows 컨테이너를 사용하여 배포할 모놀리식 웹앱을 수정할 수 있습니다. Windows 컨테이너를 사용할 경우 응용 프로그램의 핵심 아키텍처를 변경하지 않고 데이터도 [Azure SQL Database 관리되는 인스턴스](https://docs.microsoft.com/azure/sql-database/)의 데이터베이스로 마이그레이션해야 합니다.

- **클라우드 최적화**: 앞서 말한 것처럼 클라우드에서 응용 프로그램을 현대화할 때 궁극적인 목표는 [Azure App Service](https://azure.microsoft.com/services/app-service/) 같은 PaaS 플랫폼에 서비스 기반을 두는 것입니다. PaaS 플랫폼은 현대식 웹 응용 프로그램에 집중하고, [서버가 없는 컴퓨팅](https://azure.microsoft.com/overview/serverless-computing/)과 [Azure Functions](https://azure.microsoft.com/services/functions/) 같은 플랫폼에 기반을 둔 새로운 서비스로 앱을 확장합니다. 이 완성 모델에서 한 단계 더 발전한 두 번째 시나리오는 일반적으로 [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/) 또는 [Azure Container Service](https://azure.microsoft.com/services/container-service/)(Kubernetes, DC/OS 또는 Swarm) 같은 오케스트레이터를 사용하는 [클라우드 전용](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) 응용 프로그램과 마이크로 서비스 아키텍처에 대한 것입니다. 이러한 오케스트레이터는 마이크로 서비스 및 다중 컨테이너 응용 프로그램을 위해 특별히 제작되었습니다. 일반적으로 (마이크로 서비스 및 PaaS 같은) 이러한 모든 접근법을 사용하려면 특정 PaaS 플랫폼에 맞게 조정된 새로운 코드 또는 마이크로 서비스 같은 특정 아키텍처에 부합하는 코드를 작성해야 합니다.

그림 1-3에서는 각 완성도에 사용할 수 있는 내부 기술을 보여 줍니다.

![각 현대화 완성도에 해당하는 내부 기술](./media/image1-3.png)

> **그림 1-3.** 각 현대화 완성도에 해당하는 내부 기술

## <a name="lift-and-shift-scenarios"></a>리프트 앤 시프트 시나리오

리프트 및 시프트 마이그레이션의 경우 응용 프로그램 시나리오에서 리프트 앤 시프트의 다양한 변형 형태를 사용할 수 있습니다. 응용 프로그램을 다시 호스팅하기만 하는 경우 응용 프로그램과 데이터베이스 서버 전용 클라우드에서 VM을 사용하는 그림 1-4에 나와 있는 것과 같은 시나리오에 해당될 수 있습니다.

![클라우드에서 순수 IaaS 시나리오의 예](./media/image1-4.png)

> **그림 1-4**. 클라우드에서 순수 IaaS 시나리오의 예

앞으로 가면 해당 성숙도의 요소만 사용하는 순수 클라우드 DevOps 지원 응용 프로그램이 있을 것입니다. 또는 클라우드 인프라 지원의 일부 요소와 클라우드 DevOps 지원("고르고 선택" 또는 혼합 모델)의 다른 요소를 사용하는 중간 상태의 응용 프로그램이 있을 것입니다(그림 1-5 참조).

![IaaS, DevOps 및 컨테이너화 자산에 데이터베이스가 있는 "고르고 선택" 시나리오 예](./media/image1-5.png)

> **그림 1-5.** IaaS, DevOps 및 컨테이너화 자산에 데이터베이스가 있는 "고르고 선택" 시나리오 예

그런 다음 이상적인 시나리오를 마이그레이션하려면 여러 기존.NET Framework 응용 프로그램에 대 한 약간의 작업에서 상당한 이점을 얻을 수 클라우드 DevOps 지원 응용 프로그램에 마이그레이션할 수 있습니다. 이 접근법은 이후 단계인 클라우드 최적화에 준비할 수 있게 해줍니다. 그림 1-6에 그 예가 나와 있습니다.

![Windows 컨테이너 및 관리되는 서비스를 사용하는 클라우드 DevOps 지원 앱 시나리오 예](./media/image1-6.png)

> **그림 1-6.** Windows 컨테이너 및 관리되는 서비스를 사용하는 클라우드 DevOps 지원 앱 시나리오 예

더 나아가서 특정 시나리오의 경우 몇 가지 마이크로 서비스를 추가하여 기존의 클라우드 DevOps 지원 응용 프로그램을 확장할 수 있습니다. 그러면 부분적으로 클라우드 최적화 모델의 클라우드 전용 수준으로 넘어갈 수 있습니다. 현재 지침에서는 이 내용을 다루지 않습니다.


## <a name="what-this-guide-does-not-cover"></a>이 가이드에서 다루지 않는 내용

이 가이드에서는 그림 1-7에 나와 있는 시나리오 예를 몇 가지 다룹니다. 이 가이드에서는 리프트 앤 시프트 시나리오, 궁극적으로는 클라우드 DevOps 지원 모델에만 중점을 둡니다. 클라우드 DevOps 지원 모델에서는 Windows 컨테이너와 모니터링 및 CI/CD 파이프라인 같은 추가 구성 요소를 사용하여 .NET Framework 응용 프로그램이 현대화됩니다. 각 구성 요소는 클라우드로 응용 프로그램을 더 빨리, 민첩하게 배포하는 데 핵심적입니다.

![클라우드 DevOps 지원 응용 프로그램에 대한 리프트 앤 시프트 및 초기 현대화](./media/image1-7.png)

> **그림 1-7.** 클라우드 DevOps 지원 응용 프로그램에 대한 리프트 앤 시프트 및 초기 현대화

이 가이드는 특정 부분에 중점을 둡니다. 코드 변경 없이 다시 설계 하지 않고 리프트 및 기존.NET 응용 프로그램의 shift를 달성 하기 위해 취할 수 경로 표시. 궁극적으로 표시 클라우드 DevOps 지원 응용 프로그램을 확인 하는 방법.

이 가이드는 microservices 아키텍처 진화 하는 방법 등의 클라우드 네이티브 응용 프로그램과 함께 작동 하는 방법을 표시 되지 않습니다. 응용 프로그램을 다시 설계하거나 마이크로 서비스에 기반을 둔 새로운 응용 프로그램을 만들려면 [컨테이너화된 .NET 응용 프로그램을 위한 아키텍처](https://aka.ms/microservicesebook) 전자책을 참조하세요.

### <a name="additional-resources"></a>추가 자료

- **Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 응용 프로그램 수명 주기**(다운로드 가능한 전자책) [*https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)

- **컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처**(다운로드 가능한 전자책): [*https://aka.ms/microservicesebook*](https://aka.ms/microservicesebook)

- **ASP.NET Core 및 Azure로 현대식 웹 응용 프로그램 설계**(다운로드 가능한 전자책): [*https://aka.ms/webappebook*](https://aka.ms/webappebook)

## <a name="who-should-use-this-guide"></a>이 가이드의 대상 사용자

이 가이드는 개발자와 솔루션 설계자에 게 전달 하 고 응용 프로그램 해제에서 향상 된 민첩성을 위해.NET Framework를 기반으로 하는 기존 ASP.NET 응용 프로그램을 최신식를 작성 되었습니다.

또한 Windows 컨테이너를 사용하고, Microsoft Azure 사용 시 클라우드로 배포하여 얻을 수 있는 이점을 간략히 살펴보고자 하는 기업 설계자 또는 개발 책임자/이사와 같은 기술 의사 결정권자일 경우 이 가이드가 유용할 수 있습니다.

## <a name="how-to-use-this-guide"></a>이 가이드를 사용하는 방법

이 가이드에서는 "이유"를 설명합니다. 기존 응용 프로그램을 현대화하려는 이유, 클라우드로 앱 이동 시 Windows 컨테이너 사용으로 얻을 수 있는 구체적인 이점을 설명합니다. 이 가이드에서 처음 몇 챕터의 내용은 개요를 알고 싶지만 구현과 기술적인 단계별 세부 정보에 대해 중점을 둘 필요가 없는 설계자와 기술 의사 결정권자를 위해 고안되었습니다.

이 가이드의 마지막 챕터에서는 특정 배포 시나리오에 초점을 맞춘 여러 안내를 소개합니다. 이 가이드는 시나리오를 요약 하 여 이점을 모르기 강조 표시는 연습 중 더 짧은 버전을 제공 합니다. 자세한 안내는 설치 및 구현에 대한 세부 정보를 설명하고, 관련 샘플 앱이 있는 동일한 공개 [GitHub 리포지토리](https://github.com/dotnet-architecture/eShopModernizing)에 일련의 [Wiki 게시물](https://github.com/dotnet-architecture/eShopModernizing/wiki)로 게시되어 있습니다(다음 섹션에서 설명). 마지막 챕터와 GitHub의 단계별 Wiki 안내는 구현 세부 정보를 중점적으로 파악하고자 하는 개발자와 설계자에게 더 많은 관심을 받을 것입니다.

## <a name="sample-apps-for-modernizing-legacy-apps-eshopmodernizing"></a>레거시 앱 현대화에 대한 샘플 앱: eShopModernizing

GitHub의 [eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing) 리포지토리는 레거시 모놀리식 웹 응용 프로그램을 시뮬레이션하는 두 가지 샘플 응용 프로그램을 제공합니다. 첫 번째 웹앱은 ASP.NET MVC를 사용하여 개발되었고, 두 번째 웹앱은 ASP.NET Web Forms를 사용하여 개발되었습니다. 두 웹앱은 기존의.NET Framework를 기반으로 합니다. 이러한 샘플은 현대화해야 하는 기존/레거시 .NET Framework 응용 프로그램이어야 하기 때문에 .NET Core 또는 ASP.NET Core를 사용하지 않습니다.

두 샘플은 모두 현대화된 코드를 사용하는 두 번째 버전이 있으며, 매우 간단합니다. 앱 버전 간의 가장 중요한 차이점은 두 번째 버전에서 배포 옵션으로 Windows 컨테이너를 사용한다는 것입니다. 또한 두 번째 버전에는 이미지 관리를 위한 Azure Storage Blob, 보안 관리를 위한 Azure Active Directory, 응용 프로그램 모니터링 및 감사를 위한 Azure Application Insights 같은 몇 가지 기능이 추가되었습니다.

## <a name="send-your-feedback"></a>사용자 의견

이 가이드는 옵션을 높이고 현대화 기존.NET 웹 응용 프로그램을 쉽게 이해할 수 있도록 작성 되었습니다. 가이드와 관련 샘플 응용 프로그램은 개선되고 있습니다. 사용자 의견은 시작! 이 가이드의 개선 방향에 대한 의견이 있으시면 [dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com?subject=Feedback%20for%20.NET%20Container%20&%20Microservices%20Architecture%20book)으로 보내 주세요.

>[!div class="step-by-step"]
[다음](lift-and-shift-existing-apps-azure-iaas.md)
