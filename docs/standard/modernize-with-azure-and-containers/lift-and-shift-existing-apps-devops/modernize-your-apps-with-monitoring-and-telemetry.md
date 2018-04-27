---
title: 모니터링 및 원격 분석을 사용 하 여 앱을 최신식
description: 컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 모니터링 및 원격 분석을 사용 하 여 앱을 최신식
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 539e7d48b6115dbd77a78ba3e06914196826c344
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a>모니터링 및 원격 분석을 사용 하 여 앱을 최신식

프로덕션 환경에서 응용 프로그램을 실행 하는 경우에 응용 프로그램은 수행 하는 방법에 대 한 통찰력을 해야 중요 합니다. 상위 수준에서 수행 하는 것? 사용자가 오류를 가져오는지 안정적이 고 신뢰할 수 있는 사용자가 응용 프로그램 또는? 풍부한 성능 모니터링, 강력한 경고 및 대시보드 응용 프로그램을 사용 가능 하 고 예상 대로 수행 되지 않도록 해야 합니다. 문제가 있는지 신속 하 게 확인, 영향을 받는 하 고 찾고 문제를 해결 하는 근본 원인 분석을 수행 하는 얼마나 많은 고객을 결정 하는 작업을 할 수 있어야 합니다.

## <a name="monitor-your-application-with-application-insights"></a>Application Insights로 응용 프로그램을 모니터링합니다

Application Insights에는 여러 플랫폼에서 작업 하는 웹 개발자를 위한 확장 가능한 응용 프로그램 성능 관리 (APM) 서비스입니다. 실시간 웹 응용 프로그램 모니터링을 사용 합니다. Application Insights 성능 예외를 자동으로 검색 합니다. 사용자가 실제로 수행할 작업을 앱과 쉽게 이해할 수 있도록 하 고 문제를 진단할 수 있도록 강력한 분석 도구를 포함 합니다. Application Insights는 성능과 유용성을 지속적으로 향상 시킬 수 있도록 설계 되었습니다. 다양 한 플랫폼에서.NET, Node.js, 및 J2EE, 여부 등의 앱에 대 한 작동 온-프레미스 호스트 또는 클라우드입니다. Application Insights DevOps 프로세스와 통합 되어 있으며 다양 한 개발 도구에 대 한 연결 지점입니다.

그림 4-10에는 Application Insights에서 응용 프로그램을 모니터링 하는 방법 및 대시보드에 해당 insights 것 표시 방법의 예가 나와 있습니다.

![Application Insights 대시보드 모니터링](./media/image10.png)

> **그림 4-10입니다.** Application Insights 대시보드 모니터링

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a>로그 분석 워크 로드와 해당 컨테이너 모니터링 솔루션으로 Docker 인프라 모니터링

[Azure 로그 분석](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) 의 일부는 [Microsoft Azure 모니터링 솔루션 전체](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview)합니다. ´ Â 서비스 [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)합니다. 로그 분석 모니터링 하는 클라우드 및 온-프레미스 환경 (온-프레미스에 대 한 OMS) 가용성과 성능을 유지 관리할 수 있도록 합니다. 여러 원본에서 분석 기능을 제공 하려면 다른 모니터링 도구와 클라우드 및 온-프레미스 환경에서 리소스에 의해 생성 된 데이터를 수집 합니다.

Azure 인프라 로그를 기준으로 로그 분석 Azure 서비스로 수집 다른 Azure 서비스의 로그 및 메트릭 데이터 (통해 [Azure 모니터](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), Azure Vm, Docker 컨테이너 및 온-프레미스 또는 다른 클라우드 인프라입니다. 로그 분석은 유연한 로그 검색 및이 데이터를 기반으로 아웃-기본 분석을 제공합니다. 지정 된 조건에 따라 원본 간에 데이터를 분석 하는 데 사용할 수는 모든 로그에서 복잡 한 쿼리를 허용 및 사전 경고할 수 있습니다 풍부한 도구를 제공 합니다. 중앙 로그 분석 저장소를 쿼리 하 고 시각화할 수의 사용자 지정 데이터도 수집할 수 있습니다. 인프라의 기능 및 보안에 대 한 정보를 즉시 로그 분석 기본 제공 솔루션을 활용할도 수행할 수 있습니다.

OMS 포털 또는 모든 브라우저에서 실행 하면 Azure 포털을 통해 로그 분석에 액세스할 수 있으며 구성 설정에 액세스할 수 있습니다 및 여러 도구 제공 분석 하 고 수집 된 데이터 작업을 수행할 수 있습니다.

[컨테이너 모니터링 솔루션](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) 로그 분석을 통해에서 보기 있습니다 및이 단일 위치에 Docker 및 Windows 컨테이너 호스트를 관리 합니다. 솔루션을 보여 줍니다 컨테이너를 실행 하 고 컨테이너를 실행 하는 어떤 컨테이너 이미지를 실행 합니다. 컨테이너와 사용 중인 명령을 포함 한 자세한 감사 정보를 볼 수 있습니다. 보기 및 원격으로 Windows 또는 Docker 호스트를 보는 데 필요 없이 중앙 집중화 된 로그를 검색 하 여 컨테이너를 해결할 수도 있습니다. 호스트에서 초과 리소스 노이즈가 많고 소비 될 수 있는 컨테이너를 찾을 수 있습니다. 중앙 집중식된 CPU, 메모리, 저장소 및 네트워크 사용량 및 컨테이너에 대 한 성능 정보를 볼 수 있습니다. Windows를 실행 하는 컴퓨터에 중앙 집중화 하 고 있고 Windows Server에서 로그를 비교 하이퍼-V 및 Docker 컨테이너입니다. 솔루션에는 다음과 같은 컨테이너 orchestrators 지원합니다.

-   Docker Swarm

-   DC/OS

-   Kubernetes

-   Service Fabric

-   Red Hat OpenShift

그림 4-11 다양 한 컨테이너 호스트와 에이전트와 OMS 간의 관계를 나타냅니다.

![로그 분석 컨테이너 모니터링 솔루션](./media/image11.png)

> **그림 4-11입니다.** 로그 분석 컨테이너 모니터링 솔루션

로그 분석 컨테이너 모니터링 솔루션을 사용할 수 있습니다.

-   단일 위치에 있는 모든 컨테이너 호스트에 대 한 정보를 참조 하십시오.

-   컨테이너를를 실행 하 고 실행 중인 어떤 이미지를 실행 합니다.

-   컨테이너에 작업에 대 한 감사 내역을 참조 하십시오.

-   보기 및 Docker 호스트에 대 한 원격 로그인 없이 중앙 집중화 된 로그를 검색 하 여이 문제를 해결 합니다.

-   호스트에 과도 한 리소스 사용 되 고 "시끄러운 이웃" 될 수 있는 컨테이너를 찾습니다.

-   중앙 집중식된 CPU, 메모리, 저장소 및 네트워크 사용량 및 컨테이너에 대 한 성능 정보를 봅니다.

### <a name="additional-resources"></a>추가 자료

-   **Microsoft Azure에서 모니터링 개요**

[https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview)

-   **Application Insights 란?**

[https://docs.microsoft.com/azure/application-insights/app-insights-overview](https://docs.microsoft.com/azure/application-insights/app-insights-overview)

-   **로그 분석 이란?**

[https://docs.microsoft.com/azure/log-analytics/log-analytics-overview](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview)

-   **로그 분석에서 컨테이너 모니터링 솔루션**

[https://docs.microsoft.com/azure/log-analytics/log-analytics-containers](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers)

-   **Azure 모니터 개요**

[https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)

-   **Operations Management Suite (OMS) 이란?**

[https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)

-   **OMS와 함께 서비스 패브릭에서 Windows Server 컨테이너를 모니터링합니다.**

[https://docs.microsoft.com/azure/service-fabric/service-fabric-diagnostics-containers-windowsserver](https://docs.microsoft.com/azure/service-fabric/service-fabric-diagnostics-containers-windowsserver)

>[!div class="step-by-step"]
[이전](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
[다음](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
