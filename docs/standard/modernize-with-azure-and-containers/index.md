---
title: Azure 클라우드를 기존.NET 응용 프로그램 및 Windows 컨테이너를 현대화 할 (2nd edition)
description: 리프트 이동 하 고 기존 응용 프로그램을 Azure 클라우드 및이 전자책 (영문)를 사용 하 여 컨테이너를 현대화 할 방법을 설명 합니다.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 4/28/2018
ms.openlocfilehash: 3fcfdca68e05494785148cbbe149cdc2f812c577
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2018
ms.locfileid: "33956385"
---
# <a name="modernize-existing-net-applications-with-azure-cloud-and-windows-containers-2nd-edition"></a>기존.NET 응용 프로그램을 Azure 클라우드 및 Windows 컨테이너를 현대화 할 (2nd edition)

![표지 이미지](./media/cover.png)

게시자:  
Microsoft Press 및 Microsoft DevDiv  
Microsoft Corporation의 사업부  
One Microsoft Way  
Redmond, Washington 98052-6399  

Copyright © Microsoft corporation 2018  

All rights reserved. 이 가이드의 내용 중 어떤 부분도 게시자의 서면 허가 없이는 어떠한 형식이나 방법으로도 복제할 수 없습니다.

이 책은와 같은 microsoft 여러 채널을 통해 사용할 수 있는 전자는 책 (전자책)의 형태로 무료로 사용할 수 있는 http://dot.net/architecture합니다.

이 책에 관한 질문이 있는 경우 [dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com?subject=Feedback%20for%20.NET%20Container%20&%20Microservices%20Architecture%20book)으로 이메일을 보내 주세요.

이 가이드는 작성자의 견해와 의견을 "있는 그대로" 제공하고 전달합니다. 뷰, 의견 및 표현 URL 및 기타 인터넷 웹 사이트 참조를 포함 하 여이 가이드의 내용은 예 고 없이 변경 될 수 있습니다.

여기에 설명된 일부 예제는 예시 용도로만 제공되며 실제 데이터가 아닙니다. 실제로 연관시키거나 관련시키려고 의도하거나 추론해서는 안 됩니다.

Microsoft 및에 나열 된 상표 http://www.microsoft.com "상표" 웹 페이지에는 Microsoft 그룹 계열사의 상표입니다. 기타 모든 표시는 해당 소유자의 자산입니다.

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

웹 응용 프로그램 또는 서비스를 현대화 할 클라우드로 이동 하려는 경우 완전 하 게 응용 프로그램 아키텍처 변경 필요가 반드시 없습니다. Microservices 같은 고급 방법을 사용 하 여 응용 프로그램을 rearchitecting 항상 좋은 방법이 아닙니다 비용과 시간 제한으로 인해 합니다. 응용 프로그램의 유형에 따라 앱 rearchitecting도 수 필요가 없습니다. 조직의 클라우드 마이그레이션 전략 비용 효율성을 최적화하려면 비즈니스 요구 사항과 앱 요구 사항을 고려해야 합니다. 다음을 파악해야 합니다.

- 어떤 앱 변형이 필요 rearchitecting 또는 합니다.

- 부분적으로만 현대화해야 하는 앱.

- 클라우드에 바로 "리프트 앤 시프트"할 수 있는 앱.

## <a name="about-this-guide"></a>이 가이드의 내용

이 가이드 기존 Microsoft.NET Framework 웹 또는 서비스 기반 응용 프로그램의 초기 현대화에 주로 초점을 최신 또는 최신 환경에 응용 프로그램의 코드를 크게 변경 하지 않고 작업을 이동 하는 작업을 의미 합니다. 및 기본 아키텍처입니다. 

이 가이드에는 클라우드로 응용 프로그램을 이동 하 고 부분적으로 새로운 기술 및 Windows 컨테이너 및 Windows 컨테이너를 지 원하는 Azure의 계산 플랫폼 관련된 같은 인증 방법의 특정 집합을 사용 하 여 앱을 현대화의 이점을 강조 표시 합니다.

## <a name="path-to-the-cloud-for-existing-net-applications"></a>기존.NET 응용 프로그램을 클라우드로 이동하는 경로

조직에서는 일반적으로 응용 프로그램에 민첩성과 속도를 구현하기 위해 클라우드로 이동하기로 선택합니다. 온-프레미스 서버를 설치하는 데 일반적으로 몇 주가 걸리는 데 비해, 클라우드에는 몇 분 안에 수천 대의 서버(VM)를 설치할 수 있습니다.

클라우드로 응용 프로그램을 마이그레이션하는 방법에 대한 단일 만능 전략은 없습니다. 귀하에게 적합한 마이그레이션 전략은 귀사의 요구 사항과 우선 순위, 마이그레이션하는 응용 프로그램의 종류에 따라 달라집니다. 모든 응용 프로그램이 서비스 제공 플랫폼([PaaS](https://azure.microsoft.com/overview/what-is-paas/)) 모델로의 전환이나 [클라우드 전용](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) 응용 프로그램 모델 개발에 대한 투자를 보증하는 것은 아닙니다. 대다수의 경우 비즈니스 요구 사항에 따라 단계식 또는 증분 접근법을 사용하여 클라우드로의 자산 전환에 투자할 수 있습니다.

가장 장기 민첩성 및 조직에 대 한 값을 가진 최신 응용 프로그램에 대 한 이점을 얻을 수에 투자 *클라우드 네이티브* 응용 프로그램 아키텍처입니다. 그러나 기존 응용 프로그램 또는 레거시 자산에 대 한 상당한 이점을 실현 하려면 클라우드로 이동 하는 동안 최소한의 시간과 비용 rearchitecting 또는 코드 변경 없이 소비 하는 키가 합니다.

그림 1-1에서는 증분 단계로 기존.NET 응용 프로그램을 클라우드로 이동하는 경우에 취할 수 있는 경로를 보여 줍니다.

 ![기존 .NET 응용 프로그램 및 서비스의 현대화 경로](./media/image1-1.png)

> **그림 1-1**. 기존 .NET 응용 프로그램 및 서비스의 현대화 경로

각 마이그레이션 방법마다 이점과 사용해야 할 이유가 다릅니다. 클라우드에 앱을 마이그레이션하는 경우 단일 접근법을 선택하거나 여러 접근법 중에서 특정 구성 요소를 선택할 수 있습니다. 개별 응용 프로그램이 단일 접근법이나 완성 상태로 제한되는 것은 아닙니다. 예를 들어, 일반적인 하이브리드 접근법은 특정 온-프레미스 구성 요소와 다른 클라우드 구성 요소를 사용합니다.

정의 하 고 각 응용 프로그램의 성장 수준에 대 한 간단한 설명에는 다음과 같습니다.

**수준 1: 클라우드 인프라를 갖춘** 응용 프로그램:이 마이그레이션 방식에서 단순히를 마이그레이션 또는 현재 온-프레미스 응용 프로그램을 서비스로 인프라 rehost ([IaaS](https://azure.microsoft.com/overview/what-is-iaas/)) 플랫폼입니다. 앱의 구성은 전과 거의 동일하지만 이제 클라우드의 VM에 앱을 배포합니다.
이 단순 유형의 마이그레이션은 일반적으로 "리프트 & 이동"으로 알려져

**수준 2: 클라우드 최적화** 응용 프로그램:이 수준에서 한 rearchitecting 또는 중요 한 코드를 변경 하지 않고 계속 추가 및 컨테이너와 같은 새로운 기술을 통해 클라우드에서 응용 프로그램을 실행에서 추가 혜택을 얻을 수 있습니다 클라우드 관리 서비스입니다. 기업 개발 운영(DevOps) 프로세스를 세분화하여 응용 프로그램의 민첩성을 개선함으로써 더 빨리 배송할 수 있습니다. Docker 엔진을 기반으로 하는 Windows 컨테이너와 같은 기술을 사용 하 여이 작업을 수행할. 컨테이너는 여러 단계에서 배포할 때는 응용 프로그램 종속성으로 인 한 충돌을 제거 합니다. 이 maturity 모델에서 IaaS에서 컨테이너를 배포할 수 있습니다 또는 CI/CD () 파이프라인으로는 서비스, 모니터링 및 연속 통합/연속 배포 추가 사용 하는 동안 PaaS 클라우드 관리 서비스 데이터베이스에 관련 된 캐시 합니다.

세 번째 완성도는 클라우드의 궁극적 목표이지만 여러 앱에는 선택적이며 이 가이드의 주요 초점은 아닙니다.

**수준 3: 클라우드-네이티브** 응용 프로그램: 일반적으로이 마이그레이션 방법은 비즈니스 요구 사항 및 대상 현대화 업무상 중요 한 응용 프로그램에 따라 좌우 됩니다. 이 수준에서는 PaaS 서비스를 사용하여 PaaS 컴퓨팅 플랫폼으로 앱을 이동합니다. [클라우드 전용](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) 응용 프로그램 및 마이크로 서비스 아키텍처를 구현하여 장기적인 민첩성으로 응용 프로그램을 진화시키고 새로운 한계로 확장합니다. 이 유형의 현대화는 일반적으로 클라우드를 위한 특별한 설계가 필요합니다. 특히 클라우드 전용 응용 프로그램 및 마이크로 서비스 기반 모델로 이동하는 경우 새 코드를 작성해야 하는 경우가 많습니다. 이 방법은 모놀리식 및 온-프레미스 응용 프로그램 환경에서 달성하기 어려운 이점을 얻는 데 도움이 될 수 있습니다.

표 1-1에서는 각 마이그레이션 또는 현대화 방법을 선택하는 이유와 주요 이점을 설명합니다.

| **클라우드 인프라 지원** <br /> *리프트 앤 시프트* | **클라우드 액세스에 최적화 된** <br /> *현대화* | **클라우드-기본** <br /> *현대화, 아키텍처 변경 및 다시 작성* |
|---|---|---|
| **응용 프로그램의 계산 대상** |
| Azure의 VM에 배포된 응용 프로그램 | 컨테이너, Azure Service Fabric 또는 AKS (Azure Kubernetes 서비스)와 Azure 앱 서비스, Azure 컨테이너 인스턴스 (ACI), Vm에 배포 하는 N 계층 응용 프로그램이 나 모놀리식 | Azure Kubernetes 서비스 (AKS), 서비스 패브릭 및/또는 Azure 함수 기반으로 하는 서버가 없는 microservices 색인화 microservices 합니다. |
| **데이터 대상** |
| SQL 또는 VM의 모든 관계형 데이터베이스 | Azure SQL 데이터베이스 관리 되는 인스턴스 또는 클라우드에서 다른 관리 되는 데이터베이스입니다. | 마이크로 서비스를 Azure SQL 데이터베이스, Azure Cosmos DB 또는 클라우드에서 다른 관리 되는 데이터베이스에 따라 각 벌금 세분화 된 데이터베이스 |
| **장점**|
| <li>Rearchitecting, 새 코드 없음 <li> 최소한의 작업으로 빠른 마이그레이션 가능 <li> Azure에서 지원되는 최소 공통 분모 <li> 기본 가용성 보장 <li> 클라우드로 이동한 후 훨씬 더 쉽게 현대화 | <li> Rearchitecting 없음 <li> 최소한의 코드/구성 변경 내용 <li> 컨테이너로 인해 향상된 배포 및 DevOps 릴리스 민첩성 <li> 밀도 증가 및 배포 비용 감소 <li> 앱 이식성 및 종속성 <li> 대상 호스트의 유연성: PaaS 접근 방식 또는 IaaS | <li> 설계자는 클라우드에 대 한 최상의 이점을 클라우드에서 나타나지만 새 코드는 필요 <li> 마이크로 서비스 클라우드 전용 접근법 <li> 최신 중요 업무용 응용 프로그램, 클라우드 복원 력 있는 확장 가능한 하이퍼 <li> 완전히 관리되는 서비스 <li> 규모에 최적화 <li> 하위 시스템의 자율적인 민첩성을 위해 최적화 <li> 배포 및 DevOps 기반 |
| **당면 과제** |
| <li> 운영 경비 변화 또는 데이터 센터 폐쇄가 아닌 클라우드 가격 축소 <li> 관리 되는 거의: OS 또는 미들웨어 패치; 없습니다 Terraform, Spinnaker, 또는 puppet과 같은 인프라 솔루션을 사용할 수 있습니다. | <li> Containerizing는 개발자 및 IT 운영 팀에 대 한 학습 곡선의 선분 추가 단계 <li> DevOps 및 CI/CD 파이프라인 반드시 필요 일반적으로 ''이 방식을 사용 합니다. 조직의 문화권에는 현재 있는 수도 있습니다는 추가적인 문제가 발생 하지 않은 경우| <li> 네이티브 응용 프로그램을 클라우드 및 마이크로 서비스 아키텍처에 대 한 rearchitecture 필요 하며 중요 한 코드 리팩터링 또는 현대화 때 다시 작성 (증가 된 시간과 예산을)는 일반적으로 필요 <li> DevOps 및 CI/CD 파이프라인 반드시 필요 일반적으로 ''이 방식을 사용 합니다. 조직의 문화권에는 현재 있는 수도 있습니다는 추가적인 문제가 발생 하지 않은 경우|
> **표 1-1.** 기존 .NET 응용 프로그램 및 서비스의 현대화 경로 이점 및 당면 과제

### <a name="key-technologies-and-architectures-by-maturity-level"></a>완성도별 핵심 기술 및 아키텍처

.NET Framework 응용 프로그램은 2001년 후반에 출시된 .NET Framework 버전 1.0으로 처음 시작되었습니다. 그런 다음 회사에서 최신 버전을 출시했습니다(예: 2.0, 3.5 및 .NET 4.x). 해당 응용 프로그램의 대부분 Windows Server 및 인터넷 정보 서버 (IIS)에서 실행 되 고 SQL Server, Oracle, MySQL 또는 다른 RDBMS와 같은 관계형 데이터베이스 사용.

요즘 기존 .NET 응용 프로그램은 .NET Framework 4.x 또는 .NET Framework 3.5에 기반을 두고 있으며, ASP.NET MVC, ASP.NET Web Forms, ASP.NET Web API, Windows Communication Foundation(WCF), ASP.NET SignalR 및 ASP.NET Web Pages 같은 웹 프레임워크를 사용합니다. 이러한 기존의 .NET Framework 기술은 Windows에 종속됩니다. 레거시 앱만 마이그레이션하고 응용 프로그램 인프라에 대한 변경 사항을 최소화하고자 하는 경우에는 이러한 종속성을 고려하는 것이 중요합니다.

그림 1-2에서는 각각의 세 가지 클라우드 완성도별로 사용되는 주요 기술과 아키텍처 스타일을 보여 줍니다.

![기존 .NET 웹 응용 프로그램 현대화의 각 완성도에 해당하는 주요 기술](./media/image1-2.png)

> **그림 1-2.** 기존 .NET 웹 응용 프로그램 현대화의 각 완성도에 해당하는 주요 기술

그림 1-2는 가장 일반적인 시나리오를 보여주지만 아키텍처에 관해서는 여러 하이브리드 및 혼합된 변형 형태가 가능합니다. 예를 들어 완성 모델은 기존 웹앱의 모놀리식 아키텍처에만 적용되는 것이 아니라 서비스 방향, N 계층 및 다른 아키텍처 스타일 변형에도 적용됩니다. 포커스 또는 백분율 하나 또는 다른 아키텍처 유형 및 관련된 기술에 더 높은 응용 프로그램의 전체 완성도 수준을 결정합니다.

현대화 프로세스의 각 완성도는 다음 핵심 기술 및 접근법과 연관이 있습니다.

- **클라우드 인프라 준비** (rehost 또는 basic 리프트 & 이동): 대부분의 조직에서는 원하는 첫 번째 단계로, 신속 하 게 클라우드 마이그레이션 전략을 실행 합니다. 이 경우 응용 프로그램은 다시 호스트 된 합니다. 대부분의 재호스팅은 [Azure Site Recovery](https://azure.microsoft.com/services/site-recovery/) 및 [Azure Database Migration Service](https://azure.microsoft.com/campaigns/database-migration/) 같은 클라우드 도구 기반의 Azure로 마이그레이션하는 데 도움이 되는 지침, 정보 및 메커니즘을 제공하는 서비스인 [Azure Migrate](https://aka.ms/azuremigrate)를 사용하여 자동화할 수 있습니다. 레거시 앱을 클라우드로 이동할 때 자산에 대한 인프라 세부 정보를 파악할 수 있도록 수동으로 재호스팅을 설정할 수도 있습니다. 거의 Azure에서 Vm에 응용 프로그램를 이동할 수는 예를 들어 사소한 구성 변경만와 수정한 것입니다. 이 경우 네트워킹은 온-프레미스 환경과 비슷합니다. Azure에서 가상 네트워크를 만드는 경우에 특히 비슷합니다.

- **클라우드 액세스에 최적화 된** (관리 되는 서비스와 Windows 컨테이너):이 모델은 응용 프로그램의 핵심 아키텍처를 변경 하지 않고는 클라우드에서 같은 몇 가지 중요 한 이점을 얻을 수 있도록 몇 가지 중요 한 배포 최적화를 수행 하는 방법에 대 한 합니다. 여기서 기본 단계는 기존의 .NET Framework 응용 프로그램에 [Windows 컨테이너](https://docs.microsoft.com/virtualization/windowscontainers/about/) 지원을 추가하는 것입니다. 이러한 중요 한 단계 (컨테이너 화) 전반적인 리프트 및 shift 작업 light 이므로 코드를 건드리지 필요 하지 않습니다. [Image2Docker](https://github.com/docker/communitytools-image2docker-win) 또는 Visual Studio 같은 도구와 [Docker](https://www.docker.com/)용 도구를 사용할 수 있습니다. Visual Studio는 ASP.NET 응용 프로그램 및 Windows 컨테이너 이미지에 대한 스마트 기본값을 자동으로 선택합니다. 이러한 도구는 신속한 내부 루프와 Azure로 컨테이너를 가져올 수 있는 빠른 경로를 제공합니다. 여러 환경에 배포할 때 민첩성이 향상됩니다. 그런 다음 프로덕션으로 이동 배포할 수 있습니다 하 여 Windows 컨테이너 [컨테이너에 대 한 Azure 웹 앱](https://azure.microsoft.com/en-us/services/app-service/containers/), [Azure 컨테이너 인스턴스 (ACI) 및 Windows Server 2016와 컨테이너는 IaaS 접근 방식을 선호 하는 경우와 Azure Vm입니다. 같은 orchestrators에 약간 더 복잡 한 다중 컨테이너 응용 프로그램에 대 한 [Azure 서비스 패브릭](https://azure.microsoft.com/services/service-fabric/) 또는 [Azure Kubernetes 서비스 (AKS/ACS)](https://azure.microsoft.com/en-us/services/container-service/)합니다. 이 초기 현대화 중에 [Azure Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview) 같은 도구를 사용한 모니터링, [Visual Studio Team Services](https://www.visualstudio.com/team-services/)를 사용하는 앱 수명 주기에 대한 CI/CD 파이프라인, Azure에 제공되는 여러 데이터 리소스 서비스와 같은 클라우드의 자산을 추가할 수도 있습니다. 예를 들어 원래 기존의 [ASP.NET Web Forms](https://www.asp.net/web-forms) 또는 [ASP.NET MVC](https://www.asp.net/mvc)를 사용하여 개발되었지만 이제 Windows 컨테이너를 사용하여 배포할 모놀리식 웹앱을 수정할 수 있습니다. Windows 컨테이너를 사용할 경우 응용 프로그램의 핵심 아키텍처를 변경하지 않고 데이터도 [Azure SQL Database 관리되는 인스턴스](https://docs.microsoft.com/azure/sql-database/)의 데이터베이스로 마이그레이션해야 합니다.

- **클라우드-네이티브**:, 도입 된 설계 생각해 야 [클라우드 네이티브](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) 작업을 수행 하는 여러 독립적인 개발 팀에서 대규모 또는 복잡 한 응용 프로그램을 대상으로 하는 경우 응용 프로그램 개발 하 고 자치 적으로 배포할 수 있는 다른 microservices 합니다. 마이크로 서비스 당 granularized와 독립적인 확장성 인해 또한 이러한 아키텍처 접근 방법 매우 중요 한 데 따르는 어려움과 복잡성 맞서게 하지만 PaaS 클라우드를 사용 하 여 크게 간소화할 수 있습니다 및 orchestrators 좋아요 [Azure Kubernetes 서비스 (AKS/ACS)](https://azure.microsoft.com/en-us/services/container-service/) (Kubernetes 관리 됨), [Azure 서비스 패브릭 및 [Azure 함수](https://azure.microsoft.com/services/functions/) 서버가 없는 접근 방식에 대 한 합니다. 이러한 모든 방법 (예: microservices 및 서버 없이) 일반적으로 클라우드에 대 한 설계 하 고 새 코드를 작성 해야 할-특정 PaaS 플랫폼에 적용 되는 코드 또는 microservices와 같은 특정 아키텍처에 맞게 조정 해야 하는 코드입니다.

그림 1-3에서는 각 완성도에 사용할 수 있는 내부 기술을 보여 줍니다.

![각 현대화 완성도에 해당하는 내부 기술](./media/image1-3.png)

> **그림 1-3.** 각 현대화 완성도에 해당하는 내부 기술

## <a name="lift-and-shift-scenario"></a>이동할 시나리오

리프트 및 시프트 마이그레이션의 경우 응용 프로그램 시나리오에서 리프트 앤 시프트의 다양한 변형 형태를 사용할 수 있습니다. 응용 프로그램을 다시 호스팅하기만 하는 경우 응용 프로그램과 데이터베이스 서버 전용 클라우드에서 VM을 사용하는 그림 1-4에 나와 있는 것과 같은 시나리오에 해당될 수 있습니다.

![클라우드에서 순수 IaaS 시나리오의 예](./media/image1-4.png)

> **그림 1-4**. 클라우드에서 순수 IaaS 시나리오의 예

## <a name="modernization-scenarios"></a>현대화 시나리오

현대화 시나리오에 대 한 순수 클라우드 액세스에 최적화 된 하는 응용 프로그램 요소를 사용 하 여 해당 완성도 수준 에서만에서 할 수 있습니다. 또는 클라우드 인프라 지원 및 기타 요소에서 클라우드 액세스에 최적화 된에서 일부 요소와 중간 상태 응용 프로그램이 있을 수 있습니다 ("선택" a 또는 혼합된 모델), 그림 1-5를 선택 합니다.

![IaaS, DevOps 및 컨테이너화 자산에 데이터베이스가 있는 "고르고 선택" 시나리오 예](./media/image1-5.png)

> **그림 1-5.** IaaS, DevOps 및 컨테이너화 자산에 데이터베이스가 있는 "고르고 선택" 시나리오 예

다음을 마이그레이션하려면 여러 기존.NET Framework 응용 프로그램에 대 한 이상적인 시나리오는 클라우드 액세스에 최적화 된 응용 프로그램에 약간의 작업에서 상당한 이점을 얻을 수 마이그레이션할 수 있습니다. 이 방법을 사용도 설정 하면 클라우드 네이티브에 대해 가능한 향후 발전 합니다. 그림 1-6에 그 예가 나와 있습니다.

![Windows 컨테이너 및 관리 되는 서비스와 함께 예제 클라우드 액세스에 최적화 된 응용 프로그램 시나리오](./media/image1-6.png)

> **그림 1-6.** Windows 컨테이너 및 관리 되는 서비스와 함께 예제 클라우드 액세스에 최적화 된 응용 프로그램 시나리오

더 나아가 특정 시나리오에 대 한 몇 가지 microservices를 추가 하 여 기존 클라우드 액세스에 최적화 된 응용 프로그램을 확장할 수 있습니다. 이 이동 하면 부분적으로 현재 가이드의 주된 되지 않는 네이티브 클라우드 모델의 수준으로 합니다.


## <a name="what-this-guide-does-not-cover"></a>이 가이드에서 다루지 않는 내용

이 가이드에서는 그림 1-7에 나와 있는 시나리오 예를 몇 가지 다룹니다. 이 가이드 리프트 및 shift 시나리오에 대해서만 하 고 궁극적으로, 클라우드 액세스에 최적화 된 모델에 중점을 둡니다. 클라우드 액세스에 최적화 된 모델에서 Windows 컨테이너 및 모니터링 같은 추가 구성 요소를 사용 하 여.NET Framework 응용 프로그램은 현대화 된 및 CI/CD 파이프라인. 각 구성 요소는 클라우드로 응용 프로그램을 더 빨리, 민첩하게 배포하는 데 핵심적입니다.

![클라우드-네이티브가이 가이드에서 다루지 않습니다.](./media/image1-7.png)

> **그림 1-7.** 클라우드-네이티브가이 가이드에서 다루지 않습니다.

이 가이드는 특정 부분에 중점을 둡니다. 코드 변경 없이 rearchitecting, 하지 않고 리프트 및 기존.NET 응용 프로그램의 shift를 실현 하기 위해 취할 수 경로 표시. 궁극적으로 하는 방법을 보여 줍니다 응용 프로그램을 쉽게 클라우드 액세스에 최적화 된 합니다.

이 가이드는 microservices 아키텍처 진화 하는 방법 등의 클라우드 네이티브 응용 프로그램을 만드는 방법을 표시 되지 않습니다. 응용 프로그램 아키텍처를 변경 하거나 microservices을 기반으로 하는 완전히 새로운 응용 프로그램을 만드는 참조 전자책 [.NET Microservices: 화 된.NET 응용 프로그램에 대 한 아키텍처](https://aka.ms/microservicesebook)합니다.

### <a name="additional-resources"></a>추가 자료

- **Microsoft 플랫폼 및 도구와 응용 프로그램 수명 주기 Docker 컨테이너 화 된** (다운로드 가능한 전자책 (영문)): [*https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)

- **.NET Microservices: 컨테이너 화 된.NET 응용 프로그램에 대 한 아키텍처** (다운로드 가능한 전자책 (영문)): [*https://aka.ms/microservicesebook*](https://aka.ms/microservicesebook)

- **ASP.NET Core 및 Azure로 웹 응용 프로그램 설계** (다운로드 가능한 전자책 (영문)): [*https://aka.ms/webappebook*](https://aka.ms/webappebook)

## <a name="who-should-use-this-guide"></a>이 가이드의 대상 사용자

이 가이드는 기존 ASP.NET 웹 응용 프로그램 또는 WCF 서비스에 전달 하 고 응용 프로그램을 해제 하는 향상 된 민첩성을 위해.NET Framework를 기반으로 하는 현대화 하려는 솔루션 설계자 및 개발자에 대 한 작성 되었습니다.

또한 Windows 컨테이너를 사용하고, Microsoft Azure 사용 시 클라우드로 배포하여 얻을 수 있는 이점을 간략히 살펴보고자 하는 기업 설계자 또는 개발 책임자/이사와 같은 기술 의사 결정권자일 경우 이 가이드가 유용할 수 있습니다.

## <a name="how-to-use-this-guide"></a>이 가이드를 사용하는 방법

이 가이드에서는 "이유"를 설명합니다. 기존 응용 프로그램을 현대화하려는 이유, 클라우드로 앱 이동 시 Windows 컨테이너 사용으로 얻을 수 있는 구체적인 이점을 설명합니다. 이 가이드에서 처음 몇 챕터의 내용은 개요를 알고 싶지만 구현과 기술적인 단계별 세부 정보에 대해 중점을 둘 필요가 없는 설계자와 기술 의사 결정권자를 위해 고안되었습니다.

이 가이드의 마지막 챕터에서는 특정 배포 시나리오에 초점을 맞춘 여러 안내를 소개합니다. 이 가이드는 시나리오를 요약 하 여 이점을 모르기 강조 표시는 연습 중 더 짧은 버전을 제공 합니다. 자세한 안내는 설치 및 구현에 대한 세부 정보를 설명하고, 관련 샘플 앱이 있는 동일한 공개 [GitHub 리포지토리](https://github.com/dotnet-architecture/eShopModernizing)에 일련의 [Wiki 게시물](https://github.com/dotnet-architecture/eShopModernizing/wiki)로 게시되어 있습니다(다음 섹션에서 설명). 마지막 챕터와 GitHub의 단계별 Wiki 안내는 구현 세부 정보를 중점적으로 파악하고자 하는 개발자와 설계자에게 더 많은 관심을 받을 것입니다.

## <a name="sample-apps-for-modernizing-legacy-apps-eshopmodernizing"></a>레거시 앱 현대화에 대한 샘플 앱: eShopModernizing

GitHub의 [eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing) 리포지토리는 레거시 모놀리식 웹 응용 프로그램을 시뮬레이션하는 두 가지 샘플 응용 프로그램을 제공합니다. ASP.NET MVC;를 사용 하 여 하나의 웹 앱 개발은 ASP.NET Web Forms를 사용 하 여 두 번째 웹 응용 프로그램 개발은 및 세 번째 응용 프로그램은 WCF 서비스 백 엔드를 사용해 WinForms 클라이언트 데스크톱 앱과 N 계층 응용 프로그램입니다. 이러한 모든 응용이 프로그램은 기존.NET Framework를 기반으로 합니다. 이러한 샘플은 현대화해야 하는 기존/레거시 .NET Framework 응용 프로그램이어야 하기 때문에 .NET Core 또는 ASP.NET Core를 사용하지 않습니다.

이러한 샘플 앱은 현대화 된 코드와의 두 번째 버전 및는 매우 간단 합니다. 앱 버전 간의 가장 중요한 차이점은 두 번째 버전에서 배포 옵션으로 Windows 컨테이너를 사용한다는 것입니다. 또한 두 번째 버전에는 이미지 관리를 위한 Azure Storage Blob, 보안 관리를 위한 Azure Active Directory, 응용 프로그램 모니터링 및 감사를 위한 Azure Application Insights 같은 몇 가지 기능이 추가되었습니다.

## <a name="send-your-feedback"></a>사용자 의견

이 가이드는 옵션을 높이고 현대화 기존.NET 웹 응용 프로그램을 쉽게 이해할 수 있도록 작성 되었습니다. 가이드와 관련 샘플 응용 프로그램은 개선되고 있습니다. 사용자 의견은 시작! 이 가이드의 개선 방향에 대한 의견이 있으시면 [dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com?subject=Feedback%20for%20.NET%20Container%20&%20Microservices%20Architecture%20book)으로 보내 주세요.

>[!div class="step-by-step"]
[다음](lift-and-shift-existing-apps-azure-iaas.md)
