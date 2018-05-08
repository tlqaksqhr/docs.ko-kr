---
title: 컨테이너 화 된 응용 프로그램 서비스를 모니터링 합니다.
description: Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 응용 프로그램 수명 주기
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 3877767117d8292644782fc07df6667931688be2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="monitor-containerized-application-services"></a>컨테이너 화 된 응용 프로그램 서비스를 모니터링 합니다.

것은 응용 프로그램으로 여러 컨테이너 및 microservices 분할을 모니터링 하 고 응용 프로그램의 동작을 분석 하는 방법이 중요 합니다.

## <a name="microsoft-application-insights"></a>Microsoft Application Insights

[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview) 는 라이브 응용 프로그램을 모니터링 하는 확장 가능한 분석 서비스입니다. 검색 및 성능 문제를 진단 하 고 사용자가 실제로 수행할 작업을 앱과 이해 수 수 있습니다. 개발자는 지속적으로 성능을 향상 시킬 수의 의도 및 서비스 또는 응용 프로그램의 유용성을 위해 설계 되었습니다. Application Insights.NET, Java, Node.js 및 기타 다양 한 플랫폼 온-프레미스 호스트와 같은 플랫폼 또는 클라우드에서 다양 한 응용 프로그램 웹/서비스와 독립 실행형으로 작동 합니다.

### <a name="analyzing-docker-apps-in-qa-environments-using-application-insights"></a>Application Insights를 사용 하 여 QA 환경에서 Docker 응용 프로그램 분석

Docker, 관련 된 수명 주기 이벤트 및 Docker 컨테이너에 Application Insights에서 성능 카운터 차트 수 있습니다. 실행 해야는 [응용 프로그램 통찰력 Docker 이미지](https://hub.docker.com/r/microsoft/applicationinsights/) 하며 호스트와 컨테이너는 Docker 이미지 뿐만 아니라 호스트에 대 한 성능 카운터에 표시 되므로 합니다. 이 응용 프로그램 통찰력 Docker 이미지 (그림 6-1)를 사용 하면 컨테이너 화 된 응용 프로그램 성능 및 Docker 호스트 (즉, Linux Vm), Docker 컨테이너 및 실행 중인 응용 프로그램의 동작에 대 한 원격 분석을 수집 하 여 모니터링 내 합니다.

![예제](./media/image1.png)

그림 6-1: Application Insights Docker 호스트와 컨테이너를 모니터링 합니다.

실행 하는 경우는 [응용 프로그램 통찰력 Docker 이미지](https://hub.docker.com/r/microsoft/applicationinsights/) Docker 호스트에서 다음 중 하나를 활용 합니다.

-   호스트에서 실행 중인 모든 컨테이너에 대 한 원격 분석 수명 주기-시작, 중지 및 등입니다.

-   모든 컨테이너에 대 한 성능 카운터: CPU, 메모리, 네트워크 사용 등입니다.

-   도 설치 되어 있으면 [Application Insights SDK](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net) 컨테이너에서 실행 중인 앱에서이 앱의 모든 원격 분석 컨테이너와 호스트 컴퓨터를 식별 하는 추가 속성이 갖습니다. 따라서 예를 들어 둘 이상의 호스트에서 실행 되는 앱의 인스턴스를 설정한 경우 쉽게 수 있습니다 호스트에 의해 앱 원격 분석을 필터링 할 합니다.

### <a name="setting-up-application-insights-to-monitor-docker-applications-and-docker-hosts"></a>응용 프로그램 Docker 및 Docker 호스트를 모니터링 하려면 Application Insights 설정

Application Insights 리소스를 만들려면 뒤에 오는 목록에 표시 되는 문서에 대 한 지침을 따르십시오. Azure 포털에서 필요한 스크립트를 만듭니다.

-   **Application Insights에서 Docker 응용 프로그램 모니터링:**  [https://docs.microsoft.com/azure/application-insights/app-insights-docker](https://docs.microsoft.com/azure/application-insights/app-insights-docker)

-   **Docker 허브 및 Github에서 응용 프로그램 통찰력 Docker 이미지:**  
[https://hub.docker.com/r/microsoft/applicationinsights/](https://hub.docker.com/r/microsoft/applicationinsights/) 및 <https://github.com/Microsoft/ApplicationInsights-Docker>

-   **ASP.NET 용 Application Insights를 설정 합니다.**  
[https://docs.microsoft.com/azure/application-insights/app-insights-asp-net](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net)

-   **웹 페이지 용 application Insights:**  
<https://docs.microsoft.com/azure/application-insights/app-insights-javascript>

## <a name="microsoft-operations-management-suite"></a>Microsoft 작업 관리 도구 모음

[Operations Management Suite](http://microsoft.com/oms) 은 로그 분석, 자동화, 백업 및 사이트 복구를 제공 하는 간소화 된 IT 관리 솔루션입니다. 에 따라 [쿼리](https://blogs.technet.microsoft.com/msoms/2016/01/21/easy-microsoft-operations-management-suite-search-queries/) 발생 시킬 수 Operations Management Suite에 [경고](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-monitoring-alerts) 재구성을 통해 설정 [Azure 자동화](https://docs.microsoft.com/azure/automation/)합니다. 단일 유리 창 뷰를 제공 하 여 기존 관리 솔루션과 원활 하 게 통합 합니다. Operations Management Suite를 사용 하면 관리 하 고 보호할 온-프레미스 및 클라우드 인프라 수 있습니다.

### <a name="operations-management-suitehttpmicrosoftcomoms-container-solution-for-docker"></a>[Operations Management Suite](http://microsoft.com/oms) Docke에 대 한 컨테이너 솔루션

자체적으로 중요 한 서비스를 제공할 뿐 아니라 Operations Management Suite 컨테이너 솔루션 관리 및 모니터링할 수 Docker 호스트와 컨테이너에 컨테이너와 컨테이너 호스트는에 대 한 정보를 표시 하 여 컨테이너는 실행 되는 실패, 또는 및 Docker 디먼 및 컨테이너 로그로 전송 *stdout* 및 *stderr*합니다. 또한 CPU, 메모리, 네트워크 및 저장소 등 컨테이너 및 호스트에 대한 성능 메트릭을 표시하여 문제를 해결하고, 노이지 네이버(noisy neighbor) 컨테이너를 찾을 수 있게 해줍니다.

![](./media/image2.png)

Operations Management Suite로 표시 된 Docker 컨테이너에 대 한 그림 6-2: 정보

Application Insights 및 Operations Management Suite 작업 모니터링에 집중 그러나 Application Insights에 주안점을 두 응용 프로그램 내에서 실행 되는 SDK 덕분에 앱을 모니터링 합니다. 그러나 Operations Management Suite는 호스트, 주위 인프라 훨씬 더 중점적 플러스 매우 유연한 데이터 기반 검색/쿼리 시스템을 제공 하는 동안 규모에 로그에 심층 분석을 제공 합니다.

Operations Management Suite를 클라우드 기반 서비스로 구현 되므로 빠르게 사용할 수 있습니다이 실행 되 고 인프라 서비스에 최소한만 투자 하면서 합니다. 새로운 기능이 자동적으로 전달 되므로 지속적인 유지 관리에서 절약 및 업그레이드 비용이 절감 됩니다.

Operations Management Suite 컨테이너 솔루션을 사용 하면 다음을 수행할 수 있습니다.

-   중앙 집중화 하 고 및 수백만 규모에 Docker 컨테이너에서 로그의 상관 관계 지정

-   단일 위치에 있는 모든 컨테이너 호스트에 대 한 정보를 참조 하십시오.

-   컨테이너를 실행 중인 어떤 이미지를 실행 및 실행 하는 위치

-   컨테이너 호스트에서 문제가 발생할 수 있는 "시끄러운 이웃" 컨테이너를 신속 하 게 진단

-   컨테이너에서 작업에 대 한 감사 내역을 참조 하십시오.

-   보기 및 Docker 호스트에 원격 없이 중앙 집중화 된 로그를 검색 하 여 문제 해결

-   "시끄러운 이웃" 및 과도 한 리소스는 호스트에서 소비 될 수 있는 컨테이너를 찾기

-   중앙 집중식된 CPU, 메모리, 저장소 및 컨테이너에 대 한 네트워크 사용량 및 성능 정보를 보려면

-   생성 Azure 자동화를 사용 하 여 Docker 컨테이너를 테스트 합니다.

형식이 같은 쿼리를 실행 하 여 성능 정보를 볼 수 = Perf, 그림 6-3에 나와 있는 것 처럼 합니다.

![DockerPerfMetricsView](./media/image3.png){width="5.78625in" height="3.25in"}

Operations Management Suite로 표시 된 Docker 호스트의 그림 6-3: 성능 메트릭

쿼리를 저장할 Operations Management Suite의 표준 기능이 며 도와 유용 발견 한 및 시스템의 추세를 파악 하는 쿼리를 유지 합니다.

**자세한 내용은** 컨테이너 솔루션에 설치 하 고 Docker 구성 정보를 찾으려면 [Operations Management Suite](http://microsoft.com/oms)로 이동 <https://docs.microsoft.com/azure/log-analytics/log-analytics-containers>합니다.

>[!div class="step-by-step"]
[이전] (관리-프로덕션-docker-environments.md) [다음] (... /key-takeaways/index.md)
