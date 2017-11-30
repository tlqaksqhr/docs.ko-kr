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
# <a name="health-monitoring"></a><span data-ttu-id="cffbf-104">상태 모니터링</span><span class="sxs-lookup"><span data-stu-id="cffbf-104">Health monitoring</span></span>

<span data-ttu-id="cffbf-105">상태 모니터링의 컨테이너 및 microservices 상태에 대 한 정보를 거의 실시간으로 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-105">Health monitoring can allow near-real-time information about the state of your containers and microservices.</span></span> <span data-ttu-id="cffbf-106">상태 모니터링 microservices 운영의 여러 측면에 중요 하며는 나중에 설명 된 대로 orchestrators 단계로, 부분 응용 프로그램 업그레이드를 수행할 때 특히 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-106">Health monitoring is critical to multiple aspects of operating microservices and is especially important when orchestrators perform partial application upgrades in phases, as explained later.</span></span>

<span data-ttu-id="cffbf-107">자주 사용 하 여 하트 비트 Microservices 기반 응용 프로그램 또는 해당 성능 모니터, 스케줄러, 및 orchestrators 다양 한 서비스를 추적 하기 위해 사용할 수 있도록 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-107">Microservices-based applications often use heartbeats or health checks to enable their performance monitors, schedulers, and orchestrators to keep track of the multitude of services.</span></span> <span data-ttu-id="cffbf-108">서비스는 요청 시 또는 일정에 어떤 종류의 "I am 연결 유지" 신호를 보낼 수 없습니다, 응용 프로그램 업데이트를 배포 하거나 단순히 너무 늦게 오류를 검색 하 고 심각한 중단 사태에 될 수 있는 연계 실패를 중지 하지 못할 수 있습니다 위험을 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-108">If services cannot send some sort of “I’m alive” signal, either on demand or on a schedule, your application might face risks when you deploy updates, or it might simply detect failures too late and not be able to stop cascading failures that can end up in major outages.</span></span>

<span data-ttu-id="cffbf-109">일반적인 모델에서 서비스의 상태에 대 한 보고서를 보낼 하 고 해당 정보는 응용 프로그램의 상태를 전체적으로 볼 수 있도록 집계 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-109">In the typical model, services send reports about their status, and that information is aggregated to provide an overall view of the state of health of your application.</span></span> <span data-ttu-id="cffbf-110">orchestrator를 사용 하는 경우에 클러스터 적절 하 게 작동할 수 있도록 orchestrator의 클러스터에 대 한 상태 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-110">If you are using an orchestrator, you can provide health information to your orchestrator’s cluster, so that the cluster can act accordingly.</span></span> <span data-ttu-id="cffbf-111">응용 프로그램에 대 한 사용자 지정 된 수준 높은 상태 보고에 투자 하는 경우에 검색 수 있으며 실행 중인 응용 프로그램에 대 한 훨씬 더 쉽게 문제를 해결 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-111">If you invest in high-quality health reporting that is customized for your application, you can detect and fix issues for your running application much more easily.</span></span>

## <a name="implementing-health-checks-in-aspnet-core-services"></a><span data-ttu-id="cffbf-112">ASP.NET Core 서비스의 검사 상태를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-112">Implementing health checks in ASP.NET Core services</span></span>

<span data-ttu-id="cffbf-113">ASP.NET Core 마이크로 서비스 또는 웹 응용 프로그램을 개발할 때는 ASP.NET 팀에서 HealthChecks 이라는 라이브러리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-113">When developing an ASP.NET Core microservice or web application, you can use a library named HealthChecks from the ASP.NET team.</span></span> <span data-ttu-id="cffbf-114">(2017 년 1 월을 기준으로 초기 릴리스는 GitHub에서 사용할 수 있는).</span><span class="sxs-lookup"><span data-stu-id="cffbf-114">(As of May 2017, an early release is available on GitHub).</span></span>

<span data-ttu-id="cffbf-115">이 라이브러리 사용 하기 쉬운 하며 (예: SQL Server 데이터베이스 또는 원격 API) 응용 프로그램에 필요한 특정 외부 리소스 제대로 작동 하는지 유효성을 검사할 수 있는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-115">This library is easy to use and provides features that let you validate that any specific external resource needed for your application (like a SQL Server database or remote API) is working properly.</span></span> <span data-ttu-id="cffbf-116">이 라이브러리를 사용 하는 경우 그 의미 나중에 설명할와 리소스를 정상으로 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-116">When you use this library, you can also decide what it means that the resource is healthy, as we explain later.</span></span>

<span data-ttu-id="cffbf-117">이 라이브러리를 사용 하려면 먼저 프로그램 microservices에서 라이브러리를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-117">In order to use this library, you need to first use the library in your microservices.</span></span> <span data-ttu-id="cffbf-118">상태 보고서에 대 한 쿼리 하는 프런트 엔드 응용 프로그램을 두 번째로, 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-118">Second, you need a front-end application that queries for the health reports.</span></span> <span data-ttu-id="cffbf-119">프런트 엔드 응용 프로그램에는 사용자 지정 보고 응용 프로그램 수 없거나 적절 하 게 대응할 수 있는 자체 orchestrator 수 있는 성능 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-119">That front end application could be a custom reporting application, or it could be an orchestrator itself that can react accordingly to the health states.</span></span>

### <a name="using-the-healthchecks-library-in-your-back-end-aspnet-microservices"></a><span data-ttu-id="cffbf-120">백 엔드 ASP.NET microservices에서에서 HealthChecks 라이브러리 사용</span><span class="sxs-lookup"><span data-stu-id="cffbf-120">Using the HealthChecks library in your back end ASP.NET microservices</span></span>

<span data-ttu-id="cffbf-121">HealthChecks 라이브러리 eShopOnContainers 샘플 응용 프로그램에서 어떻게 사용 되는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-121">You can see how the HealthChecks library is used in the eShopOnContainers sample application.</span></span> <span data-ttu-id="cffbf-122">를 시작 하려면 각 마이크로 서비스에 대 한 정상 상태를 구성 하는 항목을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-122">To begin, you need to define what constitutes a healthy status for each microservice.</span></span> <span data-ttu-id="cffbf-123">샘플 응용 프로그램의 microservices 마이크로 서비스 API는 HTTP 및 관련된 SQL Server 데이터베이스는 경우도 수를 통해 액세스할 수 있는 경우에 비정상 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-123">In the sample application, the microservices are healthy if the microservice API is accessible via HTTP and if its related SQL Server database is also available.</span></span>

<span data-ttu-id="cffbf-124">나중에 HealthChecks 라이브러리 NuGet 패키지 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-124">In the future, you will be able to install the HealthChecks library as a NuGet package.</span></span> <span data-ttu-id="cffbf-125">하지만이 문서의 작성일를 다운로드 하 여 솔루션의 일부분으로 코드를 컴파일할 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-125">But as of this writing, you need to download and compile the code as part of your solution.</span></span> <span data-ttu-id="cffbf-126">Https://github.com/aspnet/HealthChecks에서 사용할 수 있는 코드를 복제 하 고 솔루션에는 다음 폴더에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-126">Clone the code available at https://github.com/aspnet/HealthChecks and copy the following folders to your solution.</span></span>

  - <span data-ttu-id="cffbf-127">src/공통</span><span class="sxs-lookup"><span data-stu-id="cffbf-127">src/common</span></span>
  - <span data-ttu-id="cffbf-128">src/Microsoft.AspNetCore.HealthChecks</span><span class="sxs-lookup"><span data-stu-id="cffbf-128">src/Microsoft.AspNetCore.HealthChecks</span></span>
  - <span data-ttu-id="cffbf-129">src/Microsoft.Extensions.HealthChecks</span><span class="sxs-lookup"><span data-stu-id="cffbf-129">src/Microsoft.Extensions.HealthChecks</span></span>
  - <span data-ttu-id="cffbf-130">src/Microsoft.Extensions.HealthChecks.SqlServer</span><span class="sxs-lookup"><span data-stu-id="cffbf-130">src/Microsoft.Extensions.HealthChecks.SqlServer</span></span>

<span data-ttu-id="cffbf-131">이 버전의 eShopOnContainers Azure에서 모든 종속성 없으므로 하지만 (Microsoft.Extensions.HealthChecks.AzureStorage) Azure에 대 한 것과 같은 추가 검사를 사용 해도, 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-131">You could also use additional checks like the ones for Azure (Microsoft.Extensions.HealthChecks.AzureStorage), but since this version of eShopOnContainers does not have any dependency on Azure, you do not need it.</span></span> <span data-ttu-id="cffbf-132">ASP.NET Core eShopOnContainers 기반으로 하므로 ASP.NET 상태 검사 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-132">You do not need the ASP.NET health checks, because eShopOnContainers is based on ASP.NET Core.</span></span>

<span data-ttu-id="cffbf-133">그림 10-6 모든 microservices에서 문서 블록으로 사용할 준비가 되었습니다. Visual Studio에서 HealthChecks 라이브러리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-133">Figure 10-6 shows the HealthChecks library in Visual Studio, ready to be used as a building block by any microservices.</span></span>

![](./media/image6.png)

<span data-ttu-id="cffbf-134">**그림 10-6**합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-134">**Figure 10-6**.</span></span> <span data-ttu-id="cffbf-135">ASP.NET Core HealthChecks 라이브러리 소스 코드는 Visual Studio 솔루션</span><span class="sxs-lookup"><span data-stu-id="cffbf-135">ASP.NET Core HealthChecks library source code in a Visual Studio solution</span></span>

<span data-ttu-id="cffbf-136">앞서 도입 된 대로 각 마이크로 서비스 프로젝트에서 작업을 수행 하려면 먼저 세 가지 HealthChecks 라이브러리에 대 한 참조를 추가 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-136">As introduced earlier, the first thing to do in each microservice project is to add a reference to the three HealthChecks libraries.</span></span> <span data-ttu-id="cffbf-137">그런 다음 해당 마이크로 서비스에서 수행 하려는 상태 확인 작업 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-137">After that, you add the health check actions that you want to perform in that microservice.</span></span> <span data-ttu-id="cffbf-138">이러한 작업은 기본적으로 다른 microservices (HttpUrlCheck) 또는 데이터베이스에 대 한 종속성 (현재 SqlCheck\* SQL Server 데이터베이스에 대 한).</span><span class="sxs-lookup"><span data-stu-id="cffbf-138">These actions are basically dependencies on other microservices (HttpUrlCheck) or databases (currently SqlCheck\* for SQL Server databases).</span></span> <span data-ttu-id="cffbf-139">각 ASP.NET 마이크로 서비스 또는 ASP.NET 웹 응용 프로그램의 시작 클래스 내에서 동작을 추가 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="cffbf-139">You add the action within the Startup class of each ASP.NET microservice or ASP.NET web application.</span></span>

<span data-ttu-id="cffbf-140">하나의 AddHealthCheck 방법으로 해당 HTTP 또는 데이터베이스 종속성을 추가 하 여 각 서비스 또는 웹 응용 프로그램을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-140">Each service or web application should be configured by adding all its HTTP or database dependencies as one AddHealthCheck method.</span></span> <span data-ttu-id="cffbf-141">예를 들어 eShopOnContainers에서 MVC 웹 응용 프로그램 많은 서비스에 따라 달라 집니다, 그리고 따라서에 AddCheck 메서드가 상태 검사에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-141">For example, the MVC web application from eShopOnContainers depends on many services, therefore has several AddCheck methods added to the health checks.</span></span>

<span data-ttu-id="cffbf-142">예를 들어, 다음 코드에서 카탈로그 마이크로 서비스의 SQL Server 데이터베이스에 대 한 종속성을 추가 하는 방법을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-142">For instance, in the following code you can see how the catalog microservice adds a dependency on its SQL Server database.</span></span>

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

<span data-ttu-id="cffbf-143">그러나 eShopOnContainers의 MVC 웹 응용 프로그램은 microservices의 나머지 부분에 여러 의존 합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-143">However, the MVC web application of eShopOnContainers has multiple dependencies on the rest of the microservices.</span></span> <span data-ttu-id="cffbf-144">따라서 다음 예제와 같이 각 마이크로 서비스에 대 한 하나의 AddUrlCheck 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-144">Therefore, it calls one AddUrlCheck method for each microservice, as shown in the following example:</span></span>

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

<span data-ttu-id="cffbf-145">따라서 마이크로 서비스는 모든 검사도 정상 될 때까지 "정상" 상태를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-145">Thus, a microservice will not provide a “healthy” status until all its checks are healthy as well.</span></span>

<span data-ttu-id="cffbf-146">마이크로 서비스에 종속 서비스 또는 SQL Server 하는 경우에 Healthy("Ok") 검사를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-146">If the microservice does not have a dependency on a service or on SQL Server, you should just add a Healthy("Ok") check.</span></span> <span data-ttu-id="cffbf-147">다음 코드에서 eShopOnContainers basket.api 마이크로 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-147">The following code is from the eShopOnContainers basket.api microservice.</span></span> <span data-ttu-id="cffbf-148">(바구니 마이크로 서비스 Redis cache를 사용 하 여 되지만 라이브러리는 Redis 상태 검사 공급자를 아직 포함 되지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="cffbf-148">(The basket microservice uses the Redis cache, but the library does not yet include a Redis health check provider.)</span></span>

```csharp
services.AddHealthChecks(checks =>
{
    checks.AddValueTaskCheck("HTTP Endpoint", () => new
        ValueTask<IHealthCheckResult>(HealthCheckResult.Healthy("Ok")));
});
```

<span data-ttu-id="cffbf-149">서비스 또는 웹 응용 프로그램 상태 확인 끝점을 노출 하는 UseHealthChecks 사용할 수 있도록 했습니다 (\[*url\_에 대 한\_상태\_확인*\]) 확장 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-149">For a service or web application to expose the health check endpoint, it has to enable the UseHealthChecks(\[*url\_for\_health\_checks*\]) extension method.</span></span> <span data-ttu-id="cffbf-150">이 메서드는는 WebHostBuilder에서 ASP.NET Core 서비스 또는 웹 응용 프로그램, 아래 코드에 나와 있는 것 처럼 UseKestrel 바로 뒤의 프로그램 클래스의 main 메서드에 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-150">This method goes at the WebHostBuilder level in the main method of the Program class of your ASP.NET Core service or web application, right after UseKestrel as shown in the code below.</span></span>

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

<span data-ttu-id="cffbf-151">프로세스는 다음과 같습니다: 각 마이크로 서비스 끝점 /hc를 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-151">The process works like this: each microservice exposes the endpoint /hc.</span></span> <span data-ttu-id="cffbf-152">해당 끝점이 HealthChecks 라이브러리 ASP.NET Core 미들웨어에 의해 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-152">That endpoint is created by the HealthChecks library ASP.NET Core middleware.</span></span> <span data-ttu-id="cffbf-153">해당 끝점 호출 되 면 시작 클래스의 AddHealthChecks 메서드에 구성 된 모든 상태 검사 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-153">When that endpoint is invoked, it runs all the health checks that are configured in the AddHealthChecks method in the Startup class.</span></span>

<span data-ttu-id="cffbf-154">UseHealthChecks 메서드는 포트 또는 경로가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-154">The UseHealthChecks method expects a port or a path.</span></span> <span data-ttu-id="cffbf-155">해당 포트 또는 경로 서비스의 상태를 확인 하는 데 끝점입니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-155">That port or path is the endpoint to use to check the health state of the service.</span></span> <span data-ttu-id="cffbf-156">예를 들어, 카탈로그 마이크로 서비스 경로 /hc를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-156">For instance, the catalog microservice uses the path /hc.</span></span>

### <a name="caching-health-check-responses"></a><span data-ttu-id="cffbf-157">상태 검사 응답을 캐시</span><span class="sxs-lookup"><span data-stu-id="cffbf-157">Caching health check responses</span></span>

<span data-ttu-id="cffbf-158">이후 한 서비스 거부 (DoS) 서비스에서 발생 하지 않을 또는 단순히 하지 않으려는 경우 리소스를 확인 하 여 서비스 성능에 영향을 너무 자주 반환 캐시 구성 하는 각 상태 검사에 대 한 캐시 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-158">Since you do not want to cause a Denial of Service (DoS) in your services, or you simply do not want to impact service performance by checking resources too frequently, you can cache the returns and configure a cache duration for each health check.</span></span>

<span data-ttu-id="cffbf-159">기본적으로 캐시 기간을 5 분으로 내부적으로 설정 되어 있지만 다음 코드와 같이 각 상태 검사에 해당 캐시 기간을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-159">By default, the cache duration is internally set to 5 minutes, but you can change that cache duration on each health check, as in the following code:</span></span>

```csharp
checks.AddUrlCheck(Configuration["CatalogUrl"],1); // 1 min as cache duration
```

### <a name="querying-your-microservices-to-report-about-their-health-status"></a><span data-ttu-id="cffbf-160">프로그램 microservices 상태에 대 한 보고서를 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-160">Querying your microservices to report about their health status</span></span>

<span data-ttu-id="cffbf-161">Docker에서는 마이크로 서비스를 실행 하 고 여기에서 설명 된 대로 상태 확인을 구성 했으면 때 직접 경우를 확인할 수 브라우저에서 정상 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-161">When you have configured health checks as described here, once the microservice is running in Docker, you can directly check from a browser if it is healthy.</span></span> <span data-ttu-id="cffbf-162">(이 없어도 localhost 또는 외부 Docker 호스트 IP를 통해 컨테이너에 액세스할 수 있도록 Docker 호스트가 컨테이너 포트를 게시 됩니다.) 그림 10-7은 브라우저와 해당 응답에는 요청입니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-162">(This does require that you are publishing the container port out of the Docker host, so you can access the container through localhost or through the external Docker host IP.) Figure 10-7 shows a request in a browser and the corresponding response.</span></span>

![](./media/image7.png)

<span data-ttu-id="cffbf-163">**그림 10-7**합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-163">**Figure 10-7**.</span></span> <span data-ttu-id="cffbf-164">브라우저에서 단일 서비스의 상태를 확인 하는 중</span><span class="sxs-lookup"><span data-stu-id="cffbf-164">Checking health status of a single service from a browser</span></span>

<span data-ttu-id="cffbf-165">해당 테스트에서 볼 수 있습니다 (포트 5101 실행) catalog.api 마이크로 서비스 상태가 json에서 HTTP 200 상태 및 상태 정보를 반환.</span><span class="sxs-lookup"><span data-stu-id="cffbf-165">In that test, you can see that the catalog.api microservice (running on port 5101) is healthy, returning HTTP status 200 and status information in JSON.</span></span> <span data-ttu-id="cffbf-166">또한 내부적으로 서비스도 선택 되어 있는지 해당 SQL Server 데이터베이스 종속성의 상태 및 상태 검사를 보고 했음을 자체 정상으로 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-166">It also means that internally the service also checked the health of its SQL Server database dependency and that health check was reported itself as healthy.</span></span>

## <a name="using-watchdogs"></a><span data-ttu-id="cffbf-167">Watchdogs를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="cffbf-167">Using watchdogs</span></span>

<span data-ttu-id="cffbf-168">그런 다음 안정성 상태를 관찰할 수 있으며 앞서 소개한 HealthChecks 라이브러리와 함께 쿼리를 통해 서비스 및는 microservices에 대 한 상태 보고에서 로드 하는 별도 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-168">A watchdog is a separate service that can watch health and load across services, and report health about the microservices by querying with the HealthChecks library introduced earlier.</span></span> <span data-ttu-id="cffbf-169">이 보기는 단일 서비스의 기반으로 검색 되지 않는 오류를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-169">This can help prevent errors that would not be detected based on the view of a single service.</span></span> <span data-ttu-id="cffbf-170">Watchdogs은 사용자 개입 없이 알려진된 조건에 대 한 수정 작업을 수행할 수 있는 코드를 호스트 하는 데 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-170">Watchdogs also are a good place to host code that can perform remediation actions for known conditions without user interaction.</span></span>

<span data-ttu-id="cffbf-171">EShopOnContainers 샘플 그림 10-8에 나와 있는 것 처럼 샘플 상태를 확인 하는 보고서를 표시 하는 웹 페이지를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-171">The eShopOnContainers sample contains a web page that displays sample health check reports, as shown in Figure 10-8.</span></span> <span data-ttu-id="cffbf-172">이 있을 수는 가장 간단한 watchdog 뿐 이므로 표시에 eShopOnContainers microservices 및 웹 응용 프로그램의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-172">This is the simplest watchdog you could have, since all it does is shows the state of the microservices and web applications in eShopOnContainers.</span></span> <span data-ttu-id="cffbf-173">일반적으로 watchdog 또한 동작 수행 비정상 상태를 감지 합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-173">Usually a watchdog also takes actions when it detects unhealthy states.</span></span>

![](./media/image8.png)

<span data-ttu-id="cffbf-174">**그림 10-8**합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-174">**Figure 10-8**.</span></span> <span data-ttu-id="cffbf-175">EShopOnContainers에 샘플 상태 검사 보고서</span><span class="sxs-lookup"><span data-stu-id="cffbf-175">Sample health check report in eShopOnContainers</span></span>

<span data-ttu-id="cffbf-176">요약 하자면, ASP.NET Core HealthChecks 라이브러리의 ASP.NET 미들웨어 각 마이크로 서비스에 대 한 단일 상태 확인 끝점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-176">In summary, the ASP.NET middleware of the ASP.NET Core HealthChecks library provides a single health check endpoint for each microservice.</span></span> <span data-ttu-id="cffbf-177">내에 정의 된 모든 상태 검사를 실행 되 고 이러한 모든 검사에 따라 사용 되는 전반적인 성능 상태를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-177">This will execute all the health checks defined within it and return an overall health state depending on all those checks.</span></span>

<span data-ttu-id="cffbf-178">HealthChecks 라이브러리는 향후 외부 리소스의 새 상태 검사를 통해 확장 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-178">The HealthChecks library is extensible through new health checks of future external resources.</span></span> <span data-ttu-id="cffbf-179">예를 들어 나중에 라이브러리 들이 있는 다른 데이터베이스와 Redis cache에 대해 상태 검사 라고 생각 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-179">For example, we expect that in the future the library will have health checks for Redis cache and for other databases.</span></span> <span data-ttu-id="cffbf-180">라이브러리를 사용 하 여 여러 서비스 또는 응용 프로그램 종속성 보고 상태 및 해당 상태 확인에 따라 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-180">The library allows health reporting by multiple service or application dependencies, and you can then take actions based on those health checks.</span></span>

## <a name="health-checks-when-using-orchestrators"></a><span data-ttu-id="cffbf-181">상태 검사 orchestrators를 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="cffbf-181">Health checks when using orchestrators</span></span>

<span data-ttu-id="cffbf-182">프로그램 microservices의 가용성을 모니터링 하려면 docker는 Docker Swarm, Kubernetes, 및 서비스 패브릭 같은 orchestrators 정기적으로 상태 확인을 수행는 microservices 테스트에 대 한 요청을 전송 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-182">To monitor the availability of your microservices, orchestrators like Docker Swarm, Kubernetes, and Service Fabric periodically perform health checks by sending requests to test the microservices.</span></span> <span data-ttu-id="cffbf-183">Orchestrator는 판단 하는 경우 서비스/컨테이너 정상 중지 요청이 해당 인스턴스로 라우팅되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-183">When an orchestrator determines that a service/container is unhealthy, it stops routing requests to that instance.</span></span> <span data-ttu-id="cffbf-184">또한 일반적으로 해당 컨테이너의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-184">It also usually creates a new instance of that container.</span></span>

<span data-ttu-id="cffbf-185">예를 들어, 대부분 orchestrators 0-가동 중지 시간 배포를 관리 하려면 상태 검사를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-185">For instance, most orchestrators can use health checks to manage zero-downtime deployments.</span></span> <span data-ttu-id="cffbf-186">상태가 정상으로 서비스/컨테이너 변경 하는 경우에 orchestrator 트래픽을 라우팅 서비스/컨테이너 인스턴스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-186">Only when the status of a service/container changes to healthy will the orchestrator start routing traffic to service/container instances.</span></span>

<span data-ttu-id="cffbf-187">Orchestrator는 응용 프로그램 업그레이드를 수행 하는 경우 상태 모니터링 하는 것이 특히 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-187">Health monitoring is especially important when an orchestrator performs an application upgrade.</span></span> <span data-ttu-id="cffbf-188">(예: Azure Service Fabric) 일부 orchestrators 업데이트에서 서비스 단계가-예를 들어-5 분의 1 각 응용 프로그램 업그레이드에 대 한 클러스터 화면을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-188">Some orchestrators (like Azure Service Fabric) update services in phases—for example, they might update one-fifth of the cluster surface for each application upgrade.</span></span> <span data-ttu-id="cffbf-189">노드 집합에는 동시에 업그레이드 라고는 *업그레이드 도메인*합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-189">The set of nodes that is upgraded at the same time is referred to as an *upgrade domain*.</span></span> <span data-ttu-id="cffbf-190">각 업그레이드 도메인 업그레이드 된 사용자가 사용할 수는 후 다음 업그레이드 도메인으로 이동 하는 배포 하기 전에 해당 업그레이드 도메인 상태 검사를 통과 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-190">After each upgrade domain has been upgraded and is available to users, that upgrade domain must pass health checks before the deployment moves to the next upgrade domain.</span></span>

<span data-ttu-id="cffbf-191">서비스 상태의 또 다른 측면은 서비스에서 메트릭을 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-191">Another aspect of service health is reporting metrics from the service.</span></span> <span data-ttu-id="cffbf-192">서비스 패브릭와 같은 일부 orchestrators의 상태 관리 모델의는 고급 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-192">This is an advanced capability of the health model of some orchestrators, like Service Fabric.</span></span> <span data-ttu-id="cffbf-193">메트릭은 리소스 사용량을 조정에 사용 되는 orchestrator를 사용 하는 경우 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-193">Metrics are important when using an orchestrator because they are used to balance resource usage.</span></span> <span data-ttu-id="cffbf-194">또한 메트릭 시스템 상태 표시기를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-194">Metrics also can be an indicator of system health.</span></span> <span data-ttu-id="cffbf-195">예를 들어 많은 microservices는 응용 프로그램을 할 수 있습니다 및 각 인스턴스는 요청 / 초 (RP) 메트릭을 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-195">For example, you might have an application that has many microservices, and each instance reports a requests-per-second (RPS) metric.</span></span> <span data-ttu-id="cffbf-196">하나의 서비스는 다른 서비스 보다 더 많은 리소스 (메모리, 프로세서, 등)를 사용 하는 경우 orchestrator는 리소스 사용률에도 유지 관리 하려면 클러스터에서 서비스 인스턴스를 바뀔 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-196">If one service is using more resources (memory, processor, etc.) than another service, the orchestrator could move service instances around in the cluster to try to maintain even resource utilization.</span></span>

<span data-ttu-id="cffbf-197">Azure Service Fabric을 사용 하는 경우 제공 하는 자체 참고 [모델 상태 모니터링](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction), 하는 간단한 상태 검사 보다 향상 합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-197">Note that if you are using Azure Service Fabric, it provides its own [Health Monitoring model](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction), which is more advanced than simple health checks.</span></span>

## <a name="advanced-monitoring-visualization-analysis-and-alerts"></a><span data-ttu-id="cffbf-198">고급 모니터링: 시각화, 분석 및 경고</span><span class="sxs-lookup"><span data-stu-id="cffbf-198">Advanced monitoring: visualization, analysis, and alerts</span></span>

<span data-ttu-id="cffbf-199">이벤트 스트림, 서비스 성능에 대 한 보고 하 고 문제가 감지 될 때 경고 모니터링의 마지막 부분을 시각화 합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-199">The final part of monitoring is visualizing the event stream, reporting on service performance, and alerting when an issue is detected.</span></span> <span data-ttu-id="cffbf-200">모니터링의이 부분에 대 한 다양 한 솔루션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-200">You can use different solutions for this aspect of monitoring.</span></span>

<span data-ttu-id="cffbf-201">서비스의 상태를 표시 하는 간단한 사용자 지정 응용 프로그램을 사용할 수 있는데, 사용자 지정 페이지 처럼에 소개 된 설명에서는 [ASP.NET Core HealthChecks](https://github.com/aspnet/HealthChecks)합니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-201">You can use simple custom applications showing the state of your services, like the custom page we showed when we explained [ASP.NET Core HealthChecks](https://github.com/aspnet/HealthChecks).</span></span> <span data-ttu-id="cffbf-202">또는 이벤트 스트림의에 따라 경고를 생성할지 Azure Application Insights 및 Operations Management Suite 등의 고급 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-202">Or you could use more advanced tools like Azure Application Insights and Operations Management Suite to raise alerts based on the stream of events.</span></span>

<span data-ttu-id="cffbf-203">마지막으로, 모든 이벤트 스트림에 저장 된 경우 데이터를 시각화할 Microsoft Power BI 또는 Kibana 또는 Splunk와 같은 타사 솔루션 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cffbf-203">Finally, if you were storing all the event streams, you can use Microsoft Power BI or a third-party solution like Kibana or Splunk to visualize the data.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cffbf-204">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="cffbf-204">Additional resources</span></span>

-   <span data-ttu-id="cffbf-205">**ASP.NET Core HealthChecks** (초기 릴리스) [ *https://github.com/aspnet/HealthChecks/*](https://github.com/aspnet/HealthChecks/)</span><span class="sxs-lookup"><span data-stu-id="cffbf-205">**ASP.NET Core HealthChecks** (early release) [*https://github.com/aspnet/HealthChecks/*](https://github.com/aspnet/HealthChecks/)</span></span>

-   <span data-ttu-id="cffbf-206">**서비스 패브릭 상태 모니터링 소개**
    [*https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction*](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction)</span><span class="sxs-lookup"><span data-stu-id="cffbf-206">**Introduction to Service Fabric health monitoring**
[*https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction*](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction)</span></span>

-   <span data-ttu-id="cffbf-207">**Azure Application Insights**
    [*https://azure.microsoft.com/services/application-insights/*](https://azure.microsoft.com/services/application-insights/)</span><span class="sxs-lookup"><span data-stu-id="cffbf-207">**Azure Application Insights**
[*https://azure.microsoft.com/services/application-insights/*](https://azure.microsoft.com/services/application-insights/)</span></span>

-   <span data-ttu-id="cffbf-208">**Microsoft Operations Management Suite**
    [*https://www.microsoft.com/en-us/cloud-platform/operations-management-suite*](https://www.microsoft.com/en-us/cloud-platform/operations-management-suite)</span><span class="sxs-lookup"><span data-stu-id="cffbf-208">**Microsoft Operations Management Suite**
[*https://www.microsoft.com/en-us/cloud-platform/operations-management-suite*](https://www.microsoft.com/en-us/cloud-platform/operations-management-suite)</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="cffbf-209">[이전] (구현-회로-분리기-pattern.md) [다음] (... /secure-net-microservices-web-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="cffbf-209">[Previous] (implement-circuit-breaker-pattern.md) [Next] (../secure-net-microservices-web-applications/index.md)</span></span>
