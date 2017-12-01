---
title: "상태 모니터링"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 상태 모니터링"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: cbbad72f06bcaa882bc50083d9103b0872f51754
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="health-monitoring"></a>상태 모니터링

상태 모니터링의 컨테이너 및 microservices 상태에 대 한 정보를 거의 실시간으로 허용할 수 있습니다. 상태 모니터링 microservices 운영의 여러 측면에 중요 하며는 나중에 설명 된 대로 orchestrators 단계로, 부분 응용 프로그램 업그레이드를 수행할 때 특히 중요 합니다.

자주 사용 하 여 하트 비트 Microservices 기반 응용 프로그램 또는 해당 성능 모니터, 스케줄러, 및 orchestrators 다양 한 서비스를 추적 하기 위해 사용할 수 있도록 상태를 확인 합니다. 서비스는 요청 시 또는 일정에 어떤 종류의 "I am 연결 유지" 신호를 보낼 수 없습니다, 응용 프로그램 업데이트를 배포 하거나 단순히 너무 늦게 오류를 검색 하 고 심각한 중단 사태에 될 수 있는 연계 실패를 중지 하지 못할 수 있습니다 위험을 발생할 수 있습니다.

일반적인 모델에서 서비스의 상태에 대 한 보고서를 보낼 하 고 해당 정보는 응용 프로그램의 상태를 전체적으로 볼 수 있도록 집계 됩니다. orchestrator를 사용 하는 경우에 클러스터 적절 하 게 작동할 수 있도록 orchestrator의 클러스터에 대 한 상태 정보를 제공할 수 있습니다. 응용 프로그램에 대 한 사용자 지정 된 수준 높은 상태 보고에 투자 하는 경우에 검색 수 있으며 실행 중인 응용 프로그램에 대 한 훨씬 더 쉽게 문제를 해결 수 있습니다.

## <a name="implementing-health-checks-in-aspnet-core-services"></a>ASP.NET Core 서비스의 검사 상태를 구현 합니다.

ASP.NET Core 마이크로 서비스 또는 웹 응용 프로그램을 개발할 때는 ASP.NET 팀에서 HealthChecks 이라는 라이브러리를 사용할 수 있습니다. (2017 년 1 월을 기준으로 초기 릴리스는 GitHub에서 사용할 수 있는).

이 라이브러리 사용 하기 쉬운 하며 (예: SQL Server 데이터베이스 또는 원격 API) 응용 프로그램에 필요한 특정 외부 리소스 제대로 작동 하는지 유효성을 검사할 수 있는 기능을 제공 합니다. 이 라이브러리를 사용 하는 경우 그 의미 나중에 설명할와 리소스를 정상으로 결정할 수 있습니다.

이 라이브러리를 사용 하려면 먼저 프로그램 microservices에서 라이브러리를 사용 해야 합니다. 상태 보고서에 대 한 쿼리 하는 프런트 엔드 응용 프로그램을 두 번째로, 해야 합니다. 프런트 엔드 응용 프로그램에는 사용자 지정 보고 응용 프로그램 수 없거나 적절 하 게 대응할 수 있는 자체 orchestrator 수 있는 성능 상태에 있습니다.

### <a name="using-the-healthchecks-library-in-your-back-end-aspnet-microservices"></a>백 엔드 ASP.NET microservices에서에서 HealthChecks 라이브러리 사용

HealthChecks 라이브러리 eShopOnContainers 샘플 응용 프로그램에서 어떻게 사용 되는지 확인할 수 있습니다. 를 시작 하려면 각 마이크로 서비스에 대 한 정상 상태를 구성 하는 항목을 정의 해야 합니다. 샘플 응용 프로그램의 microservices 마이크로 서비스 API는 HTTP 및 관련된 SQL Server 데이터베이스는 경우도 수를 통해 액세스할 수 있는 경우에 비정상 상태가 됩니다.

나중에 HealthChecks 라이브러리 NuGet 패키지 설치 됩니다. 하지만이 문서의 작성일를 다운로드 하 여 솔루션의 일부분으로 코드를 컴파일할 필요 합니다. Https://github.com/aspnet/HealthChecks에서 사용할 수 있는 코드를 복제 하 고 솔루션에는 다음 폴더에 복사 합니다.

  - src/공통
  - src/Microsoft.AspNetCore.HealthChecks
  - src/Microsoft.Extensions.HealthChecks
  - src/Microsoft.Extensions.HealthChecks.SqlServer

이 버전의 eShopOnContainers Azure에서 모든 종속성 없으므로 하지만 (Microsoft.Extensions.HealthChecks.AzureStorage) Azure에 대 한 것과 같은 추가 검사를 사용 해도, 필요 하지 않습니다. ASP.NET Core eShopOnContainers 기반으로 하므로 ASP.NET 상태 검사 않아도 됩니다.

그림 10-6 모든 microservices에서 문서 블록으로 사용할 준비가 되었습니다. Visual Studio에서 HealthChecks 라이브러리를 나타냅니다.

![](./media/image6.png)

**그림 10-6**합니다. ASP.NET Core HealthChecks 라이브러리 소스 코드는 Visual Studio 솔루션

앞서 도입 된 대로 각 마이크로 서비스 프로젝트에서 작업을 수행 하려면 먼저 세 가지 HealthChecks 라이브러리에 대 한 참조를 추가 하는 것입니다. 그런 다음 해당 마이크로 서비스에서 수행 하려는 상태 확인 작업 추가 합니다. 이러한 작업은 기본적으로 다른 microservices (HttpUrlCheck) 또는 데이터베이스에 대 한 종속성 (현재 SqlCheck\* SQL Server 데이터베이스에 대 한). 각 ASP.NET 마이크로 서비스 또는 ASP.NET 웹 응용 프로그램의 시작 클래스 내에서 동작을 추가 하는 경우.

하나의 AddHealthCheck 방법으로 해당 HTTP 또는 데이터베이스 종속성을 추가 하 여 각 서비스 또는 웹 응용 프로그램을 구성 해야 합니다. 예를 들어 eShopOnContainers에서 MVC 웹 응용 프로그램 많은 서비스에 따라 달라 집니다, 그리고 따라서에 AddCheck 메서드가 상태 검사에 추가 합니다.

예를 들어, 다음 코드에서 카탈로그 마이크로 서비스의 SQL Server 데이터베이스에 대 한 종속성을 추가 하는 방법을 볼 수 있습니다.

```csharp
// Startup.cs from Catalog.api microservice
//
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        // Add framework services
        services.AddHealthChecks(checks =>
        {
            checks.AddSqlCheck("CatalogDb", Configuration["ConnectionString"]);
        });
        // Other services
    }
}
```

그러나 eShopOnContainers의 MVC 웹 응용 프로그램은 microservices의 나머지 부분에 여러 의존 합니다. 따라서 다음 예제와 같이 각 마이크로 서비스에 대 한 하나의 AddUrlCheck 메서드를 호출 합니다.

```csharp
// Startup.cs from the MVC web app
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc();
        services.Configure<AppSettings>(Configuration);
        services.AddHealthChecks(checks =>
        {
            checks.AddUrlCheck(Configuration["CatalogUrl"]);
            checks.AddUrlCheck(Configuration["OrderingUrl"]);
            checks.AddUrlCheck(Configuration["BasketUrl"]);
            checks.AddUrlCheck(Configuration["IdentityUrl"]);
        });
    }
}
```

따라서 마이크로 서비스는 모든 검사도 정상 될 때까지 "정상" 상태를 제공 하지 않습니다.

마이크로 서비스에 종속 서비스 또는 SQL Server 하는 경우에 Healthy("Ok") 검사를 추가 해야 합니다. 다음 코드에서 eShopOnContainers basket.api 마이크로 서비스입니다. (바구니 마이크로 서비스 Redis cache를 사용 하 여 되지만 라이브러리는 Redis 상태 검사 공급자를 아직 포함 되지 않습니다.)

```csharp
services.AddHealthChecks(checks =>
{
    checks.AddValueTaskCheck("HTTP Endpoint", () => new
        ValueTask<IHealthCheckResult>(HealthCheckResult.Healthy("Ok")));
});
```

서비스 또는 웹 응용 프로그램 상태 확인 끝점을 노출 하는 UseHealthChecks 사용할 수 있도록 했습니다 (\[*url\_에 대 한\_상태\_확인*\]) 확장 메서드입니다. 이 메서드는는 WebHostBuilder에서 ASP.NET Core 서비스 또는 웹 응용 프로그램, 아래 코드에 나와 있는 것 처럼 UseKestrel 바로 뒤의 프로그램 클래스의 main 메서드에 수준입니다.

```csharp
namespace Microsoft.eShopOnContainers.WebMVC
{
    public class Program
    {
        public static void Main(string[] args)
        {
            var host = new WebHostBuilder()
                .UseKestrel()
                .UseHealthChecks("/hc")
                .UseContentRoot(Directory.GetCurrentDirectory())
                .UseIISIntegration()
                .UseStartup<Startup>()
                .Build();
            host.Run();
        }
    }
}
```

프로세스는 다음과 같습니다: 각 마이크로 서비스 끝점 /hc를 노출 합니다. 해당 끝점이 HealthChecks 라이브러리 ASP.NET Core 미들웨어에 의해 생성 됩니다. 해당 끝점 호출 되 면 시작 클래스의 AddHealthChecks 메서드에 구성 된 모든 상태 검사 실행 됩니다.

UseHealthChecks 메서드는 포트 또는 경로가 필요합니다. 해당 포트 또는 경로 서비스의 상태를 확인 하는 데 끝점입니다. 예를 들어, 카탈로그 마이크로 서비스 경로 /hc를 사용합니다.

### <a name="caching-health-check-responses"></a>상태 검사 응답을 캐시

이후 한 서비스 거부 (DoS) 서비스에서 발생 하지 않을 또는 단순히 하지 않으려는 경우 리소스를 확인 하 여 서비스 성능에 영향을 너무 자주 반환 캐시 구성 하는 각 상태 검사에 대 한 캐시 기간입니다.

기본적으로 캐시 기간을 5 분으로 내부적으로 설정 되어 있지만 다음 코드와 같이 각 상태 검사에 해당 캐시 기간을 변경할 수 있습니다.

```csharp
checks.AddUrlCheck(Configuration["CatalogUrl"],1); // 1 min as cache duration
```

### <a name="querying-your-microservices-to-report-about-their-health-status"></a>프로그램 microservices 상태에 대 한 보고서를 쿼리합니다.

Docker에서는 마이크로 서비스를 실행 하 고 여기에서 설명 된 대로 상태 확인을 구성 했으면 때 직접 경우를 확인할 수 브라우저에서 정상 상태입니다. (이 없어도 localhost 또는 외부 Docker 호스트 IP를 통해 컨테이너에 액세스할 수 있도록 Docker 호스트가 컨테이너 포트를 게시 됩니다.) 그림 10-7은 브라우저와 해당 응답에는 요청입니다.

![](./media/image7.png)

**그림 10-7**합니다. 브라우저에서 단일 서비스의 상태를 확인 하는 중

해당 테스트에서 볼 수 있습니다 (포트 5101 실행) catalog.api 마이크로 서비스 상태가 json에서 HTTP 200 상태 및 상태 정보를 반환. 또한 내부적으로 서비스도 선택 되어 있는지 해당 SQL Server 데이터베이스 종속성의 상태 및 상태 검사를 보고 했음을 자체 정상으로 의미 합니다.

## <a name="using-watchdogs"></a>Watchdogs를 사용 하 여

그런 다음 안정성 상태를 관찰할 수 있으며 앞서 소개한 HealthChecks 라이브러리와 함께 쿼리를 통해 서비스 및는 microservices에 대 한 상태 보고에서 로드 하는 별도 서비스입니다. 이 보기는 단일 서비스의 기반으로 검색 되지 않는 오류를 방지할 수 있습니다. Watchdogs은 사용자 개입 없이 알려진된 조건에 대 한 수정 작업을 수행할 수 있는 코드를 호스트 하는 데 있습니다.

EShopOnContainers 샘플 그림 10-8에 나와 있는 것 처럼 샘플 상태를 확인 하는 보고서를 표시 하는 웹 페이지를 포함 합니다. 이 있을 수는 가장 간단한 watchdog 뿐 이므로 표시에 eShopOnContainers microservices 및 웹 응용 프로그램의 상태입니다. 일반적으로 watchdog 또한 동작 수행 비정상 상태를 감지 합니다.

![](./media/image8.png)

**그림 10-8**합니다. EShopOnContainers에 샘플 상태 검사 보고서

요약 하자면, ASP.NET Core HealthChecks 라이브러리의 ASP.NET 미들웨어 각 마이크로 서비스에 대 한 단일 상태 확인 끝점을 제공합니다. 내에 정의 된 모든 상태 검사를 실행 되 고 이러한 모든 검사에 따라 사용 되는 전반적인 성능 상태를 반환 합니다.

HealthChecks 라이브러리는 향후 외부 리소스의 새 상태 검사를 통해 확장 가능 합니다. 예를 들어 나중에 라이브러리 들이 있는 다른 데이터베이스와 Redis cache에 대해 상태 검사 라고 생각 됩니다. 라이브러리를 사용 하 여 여러 서비스 또는 응용 프로그램 종속성 보고 상태 및 해당 상태 확인에 따라 작업을 할 수 있습니다.

## <a name="health-checks-when-using-orchestrators"></a>상태 검사 orchestrators를 사용 하는 경우

프로그램 microservices의 가용성을 모니터링 하려면 docker는 Docker Swarm, Kubernetes, 및 서비스 패브릭 같은 orchestrators 정기적으로 상태 확인을 수행는 microservices 테스트에 대 한 요청을 전송 하 여 합니다. Orchestrator는 판단 하는 경우 서비스/컨테이너 정상 중지 요청이 해당 인스턴스로 라우팅되지 않습니다. 또한 일반적으로 해당 컨테이너의 새 인스턴스를 만듭니다.

예를 들어, 대부분 orchestrators 0-가동 중지 시간 배포를 관리 하려면 상태 검사를 사용할 수 있습니다. 상태가 정상으로 서비스/컨테이너 변경 하는 경우에 orchestrator 트래픽을 라우팅 서비스/컨테이너 인스턴스를 시작 합니다.

Orchestrator는 응용 프로그램 업그레이드를 수행 하는 경우 상태 모니터링 하는 것이 특히 중요 합니다. (예: Azure Service Fabric) 일부 orchestrators 업데이트에서 서비스 단계가-예를 들어-5 분의 1 각 응용 프로그램 업그레이드에 대 한 클러스터 화면을 업데이트할 수 있습니다. 노드 집합에는 동시에 업그레이드 라고는 *업그레이드 도메인*합니다. 각 업그레이드 도메인 업그레이드 된 사용자가 사용할 수는 후 다음 업그레이드 도메인으로 이동 하는 배포 하기 전에 해당 업그레이드 도메인 상태 검사를 통과 해야 합니다.

서비스 상태의 또 다른 측면은 서비스에서 메트릭을 보고 합니다. 서비스 패브릭와 같은 일부 orchestrators의 상태 관리 모델의는 고급 기능입니다. 메트릭은 리소스 사용량을 조정에 사용 되는 orchestrator를 사용 하는 경우 중요 합니다. 또한 메트릭 시스템 상태 표시기를 수 있습니다. 예를 들어 많은 microservices는 응용 프로그램을 할 수 있습니다 및 각 인스턴스는 요청 / 초 (RP) 메트릭을 보고 합니다. 하나의 서비스는 다른 서비스 보다 더 많은 리소스 (메모리, 프로세서, 등)를 사용 하는 경우 orchestrator는 리소스 사용률에도 유지 관리 하려면 클러스터에서 서비스 인스턴스를 바뀔 수 있습니다.

Azure Service Fabric을 사용 하는 경우 제공 하는 자체 참고 [모델 상태 모니터링](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction), 하는 간단한 상태 검사 보다 향상 합니다.

## <a name="advanced-monitoring-visualization-analysis-and-alerts"></a>고급 모니터링: 시각화, 분석 및 경고

이벤트 스트림, 서비스 성능에 대 한 보고 하 고 문제가 감지 될 때 경고 모니터링의 마지막 부분을 시각화 합니다. 모니터링의이 부분에 대 한 다양 한 솔루션을 사용할 수 있습니다.

서비스의 상태를 표시 하는 간단한 사용자 지정 응용 프로그램을 사용할 수 있는데, 사용자 지정 페이지 처럼에 소개 된 설명에서는 [ASP.NET Core HealthChecks](https://github.com/aspnet/HealthChecks)합니다. 또는 이벤트 스트림의에 따라 경고를 생성할지 Azure Application Insights 및 Operations Management Suite 등의 고급 도구를 사용할 수 있습니다.

마지막으로, 모든 이벤트 스트림에 저장 된 경우 데이터를 시각화할 Microsoft Power BI 또는 Kibana 또는 Splunk와 같은 타사 솔루션 사용할 수 있습니다.

## <a name="additional-resources"></a>추가 리소스

-   **ASP.NET Core HealthChecks** (초기 릴리스) [ *https://github.com/aspnet/HealthChecks/*](https://github.com/aspnet/HealthChecks/)

-   **서비스 패브릭 상태 모니터링 소개**
    [*https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction*](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction)

-   **Azure Application Insights**
    [*https://azure.microsoft.com/services/application-insights/*](https://azure.microsoft.com/services/application-insights/)

-   **Microsoft Operations Management Suite**
    [*https://www.microsoft.com/en-us/cloud-platform/operations-management-suite*](https://www.microsoft.com/en-us/cloud-platform/operations-management-suite)

>[!div class="step-by-step"]
[이전] (구현-회로-분리기-pattern.md) [다음] (... /secure-net-microservices-web-applications/index.md)
