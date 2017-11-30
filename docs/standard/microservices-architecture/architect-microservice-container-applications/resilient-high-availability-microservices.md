---
title: "복원 력 및 microservices의 고가용성"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 복원 력 및 microservices의 고가용성"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 149e28ac7bd7383e4e960ed8a226943e2b9bdaa1
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="resiliency-and-high-availability-in-microservices"></a>복원 력 및 microservices의 고가용성

예기치 않은 오류를 처리 하는 분산된 시스템에서 특히 해결 하기 위해 가장 어려운 문제 중 하나입니다. 예외 처리, 개발자가 작성 하는 코드의 대부분을 포함 하며이 또한 테스트에서 가장 많은 시간이 소요 된 위치. 문제는 오류를 처리 하는 코드를 작성 보다 훨씬 복잡 합니다. 마이크로 서비스에서 실행 되 고 있는 컴퓨터에서 오류가 발생 하는 경우 어떻게 되나요? 이 마이크로 서비스 오류 (자체적으로 하드 문제)를 검색 하는 데 필요한 할 뿐만 아니라 사용자 마이크로 서비스를 다시 시작 해야 할 항목 할 수 있습니다.

마이크로 서비스는 오류 시 복원할 수 있으며 가용성을 위해 다른 컴퓨터에서 자주 다시 시작할 수를 해야 합니다. 이 복구는 마이크로 서비스를 성공적으로 다시 시작할 수 있는지 여부를 및에 마이크로 서비스에서이 상태를 복구할 수 있는 마이크로 서비스를 대신 하 여 저장 된 상태에도 제공 됩니다. 즉, 필요한 계산 기능 (프로세스를 다시 시작할 수 있습니다)에서 복원 력을 상태 또는 데이터 (데이터 손실 없음 및 일관 된 데이터는 유지)에 대 한 복원 력을 뿐만 아니라 합니다.

복원 력 문제 응용 프로그램 업그레이드를 사용 하는 동안 오류가 발생 하는 경우 처럼, 다른 시나리오 중 중요 합니다. 배포 시스템을 사용 하는 마이크로 서비스를 최신 버전으로 앞으로 이동 하거나 대신 롤백할 일관성 있는 상태로 유지 하기 위해 이전 버전으로 계속 수 있는지 여부를 결정 해야 합니다. 충분 한 컴퓨터를 앞으로 이동 하 게 유지 하는 사용할 수 있는지 여부 및 이전 버전의는 마이크로 서비스를 복구 하는 방법 등의 질문을 고려해 야 할 합니다. 이렇게 하려면 전체 응용 프로그램 및 orchestrator 이러한 결정을 내릴 수 있도록 상태 정보를 내보내는 데 마이크로 서비스 합니다.

복원 력 관련 또한, 클라우드 기반 시스템에 동작 해야 합니다. 했 듯이, 클라우드 기반 시스템 오류를 받아들여야 하 고 임원의 자동으로 복구 하려고 합니다. 예를 들어, 네트워크 또는 컨테이너 오류 발생 시 클라이언트 응용 프로그램 또는 클라이언트 서비스 메시지 전송을 다시 시도 하거나 오류 클라우드에서 대부분의 경우에서 부분는 이후 요청을 다시 시도 전략이 있어야 합니다. [내부 응용 프로그램 구현](#implementing_resilient_apps) 이 가이드의 섹션에서는 부분 실패를 처리 하는 방법입니다. 과 같은 라이브러리를 사용 하 여 지 수 백오프 또는.NET Core에서 회로 차단기 패턴으로 다시 시도 횟수와 같은 기법 설명 [관](https://github.com/App-vNext/Polly), 다양 한이 주제를 처리 하는 정책 제공 합니다.

## <a name="health-management-and-diagnostics-in-microservices"></a>상태 관리 및 진단 microservices에

것, 하 고 종종 간과 생략 해당 상태 및 진단을 보고 해야 하는 마이크로 서비스입니다. 그렇지 않으면 작업 측면에서 볼 때 거의 통찰력이 있습니다. 독립 서비스의 조합에 대해 진단 이벤트를 상호 연결 하 고 컴퓨터 클록 스큐 이벤트 순서를 이해 하기를 다루는 하기는 쉽지 않습니다. 합의 프로토콜 및 데이터 형식에 대 한 마이크로 서비스와 상호 작용 하는 동일한 방법으로 상태와는 결국 쿼리 및 보기를 위한 이벤트 저장소에 있는 진단 이벤트를 기록 하는 방법에 대 한 표준화에 대 한 요구가 있습니다. 가 키인 microservices 방법에서는 다른 팀이 단일 로깅 형식을에 동의 하는지 합니다. 응용 프로그램에서 진단 이벤트를 확인 하는 일관 된 방법이 될 필요 합니다.

### <a name="health-checks"></a>상태 확인

상태는 진단와에서 다릅니다. 적절 한 조치를 취할 현재 상태를 보고 마이크로 서비스에 대 한 상태가입니다. 좋은 예로 가용성을 유지 하는 업그레이드 및 배포 메커니즘으로 작동 합니다. 서비스 수 현재 프로세스 충돌로 인해 비정상을 하거나 있지만 컴퓨터 다시 부팅 서비스 작동 중일 수 있습니다. 필요한 것은 업그레이드를 수행 하 여 나쁜을 유지할 것입니다. 먼저 조사를 수행 하는 가장 좋은 방법입니다 하거나 복구 하려면 마이크로 서비스에 대 한 시간을 허용 합니다. 상태 이벤트는 마이크로 서비스를 당사는 여러분 합리적인된 결정을 내릴, 실제로 자체 치료 서비스를 만드는 데 도움이 됩니다.

구현 상태 확인이 가이드의 ASP.NET Core services 섹션에서 적절 한 조치를 취할 모니터링 서비스에의 상태를 보고할 수 있도록 프로그램 microservices에서 새 ASP.NET HealthChecks 라이브러리를 사용 하는 방법을 설명 합니다.

### <a name="using-diagnostics-and-logs-event-streams"></a>진단 및 로그 이벤트 스트림 사용

로그는 응용 프로그램 또는 서비스는 실행 방법을, 예외, 경고 및 정보 메시지를 간단한 포함 하는 방법에 대 한 정보를 제공 합니다. 일반적으로 예외도 서 표시 스택 추적 여러 줄에 이벤트당 한 줄 텍스트 형식으로 각 로그는 합니다.

단일 서버 기반 응용 프로그램에서 디스크 (로그 파일)에 있는 파일에 로그를 간단 하 게 작성할 수 있으며 어떤 도구를 사용 하 여 분석 한 다음 키를 누릅니다. 응용 프로그램을 실행 하는 고정된 서버 또는 VM에 제한 되는 경우 일반적으로 되므로 없습니다 너무 복잡해 서 이벤트의 흐름을 분석할 수 있습니다. 그러나 여러 서비스는 orchestrator 클러스터의 여러 노드에서 실행 되는 분산 응용 프로그램에서는 분산된 이벤트 간의 상관 관계 수 있으면 어렵습니다.

마이크로 서비스 기반 응용 프로그램 이벤트 또는 로그 파일의 출력 스트림으로 자체적으로 저장 하려고 하 고 아니더라도 중앙 위치로 이벤트의 라우팅 관리 하려고 해야 합니다. 각 프로세스 아래 수집 되는 실행 환경 인프라에서 실행 되 고 있는 표준 출력에 해당 하는 이벤트 스트림의 작성 해야 방금 의미 투명 해야 합니다. 이러한 이벤트 스트림 라우터의 예로 [Microsoft.Diagnostic.EventFlow](https://github.com/Azure/diagnostics-eventflow), 여러 원본의 이벤트 스트림을 수집 하 고 시스템을 출력에 게시 합니다. 개발 환경에 대 한 간단한 표준 출력을 포함할 수 있습니다 또는 클라우드 시스템 like [Application Insights](https://azure.microsoft.com/services/application-insights/), [OMS](https://github.com/Azure/diagnostics-eventflow#oms-operations-management-suite) (온-프레미스 응용 프로그램)에 대 한 및 [Azure진단](https://docs.microsoft.com/azure/monitoring-and-diagnostics/azure-diagnostics). 또한 좋은 타사 로그 분석 플랫폼 및 도구를 검색할 수, 경고, 보고서를 되며 실시간으로도 모니터 로그와 같은 [Splunk](http://www.splunk.com/goto/Splunk_Log_Management?ac=ga_usa_log_analysis_phrase_Mar17&_kk=logs%20analysis&gclid=CNzkzIrex9MCFYGHfgodW5YOtA)합니다.

### <a name="orchestrators-managing-health-and-diagnostics-information"></a>상태 및 진단 정보를 관리 하는 orchestrators

마이크로 서비스 기반 응용 프로그램을 만들 때 복잡성을 처리 해야 합니다. 물론, 단일 마이크로 서비스를 다루기가 단순 않으며 수십 또는 수백 형식의 수천 microservices의 인스턴스는 복잡 한 문제입니다. 마이크로 서비스 아키텍처에 대 한 빌드되지 않습니다-또한 해야 고가용성, 주소 지정 기능, 복원 력, 상태 및 진단을 안정적이 고 화합 시스템 하려는 경우.

![](./media/image22.png)

**그림 4-22**합니다. 마이크로 서비스 플랫폼은 응용 프로그램의 상태 관리에 대 한 기본

그림 4-22 표시 된 복잡 한 문제는 직접 해결 하기가 매우 어렵습니다. 개발 팀 비즈니스 문제를 해결 하 고 마이크로 서비스 기반 접근 방식 사용한 사용자 지정 응용 프로그램 빌드에 초점을 맞추어야 합니다. 이며 복잡 한 인프라 문제 해결을 위해만 제한 되지 해야 했다는 것 비용 마이크로 서비스 기반 응용 프로그램의 거 대 한 것입니다. 따라서 orchestrators 또는 마이크로 서비스 클러스터의 구축 하 고 서비스를 실행 하 고 효율적으로 인프라 리소스를 사용 하 여 어려운 문제를 해결 하기 위해 시도 하 라고 하는 마이크로 서비스 지향 플랫폼에 있습니다. 이 작성 microservices 접근 방식을 사용 하는 응용 프로그램의 복잡성을 줄여 줍니다.

다른 orchestrators 유사해 있습니다 하지만 다음 섹션에 설명 된 대로 진단 및 상태 검사에서 각각의 제공 기능 및 운영 체제 플랫폼에 따라 때로는 완성 상태 다릅니다.

## <a name="additional-resources"></a>추가 리소스

-   **12 단계 앱입니다. XI 합니다. 로그: 이벤트 스트림을로 로그를 처리할**
    [*https://12factor.net/logs*](https://12factor.net/logs)

-   **Microsoft 진단 EventFlow 라이브러리입니다.** GitHub 리포지토리 합니다.

    [*https://github.com/Azure/diagnostics-eventflow*](https://github.com/Azure/diagnostics-eventflow)

-   **Azure 진단 이란**
    [*https://docs.microsoft.com/azure/azure-diagnostics*](https://docs.microsoft.com/azure/azure-diagnostics)

-   **Azure에서 로그 분석 서비스에 Windows 컴퓨터 연결**
    [*https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents*](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)

-   **하는 평균 로깅: 의미 체계 로깅 응용 프로그램 블록을 사용**
    [*https://msdn.microsoft.com/library/dn440729 (v=pandp.60).aspx*](https://msdn.microsoft.com/library/dn440729(v=pandp.60).aspx)

-   **Splunk 합니다.** 공식 사이트입니다.
    [*http://www.splunk.com*](http://www.splunk.com)

-   **EventSource 클래스**합니다. Windows (ETW)에 대 한 추적 이벤트에 대 한 API [ *https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing.eventsource*](https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing.eventsource)




>[!div class="step-by-step"]
[이전] [다음] (scalable-available-multi-container-microservice-applications.md) (microservice-based-composite-ui-shape-layout.md)
