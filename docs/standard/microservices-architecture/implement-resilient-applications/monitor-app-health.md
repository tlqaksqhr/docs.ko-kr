---
title: "상태 모니터링"
description: "컨테이너화된 .NET 응용 프로그램용 .NET 마이크로 서비스 아키텍처 | 상태 모니터링"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 76821e27613335609527b867a6b94dac551f6235
ms.sourcegitcommit: 15316053918995cc1380163a7d7e7edd5c44e6d7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2018
---
# <a name="health-monitoring"></a><span data-ttu-id="b643d-104">상태 모니터링</span><span class="sxs-lookup"><span data-stu-id="b643d-104">Health monitoring</span></span>

<span data-ttu-id="b643d-105">상태 모니터링은 컨테이너 및 마이크로 서비스의 상태에 대해 거의 실시간으로 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-105">Health monitoring can allow near-real-time information about the state of your containers and microservices.</span></span> <span data-ttu-id="b643d-106">상태 모니터링은 마이크로 서비스를 작동하는 데 있어 여러 가지 측면에서 매우 중요하며, 나중에 설명하는 대로 오케스트레이터에서 응용 프로그램을 부분적으로 업그레이드할 때 특히 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-106">Health monitoring is critical to multiple aspects of operating microservices and is especially important when orchestrators perform partial application upgrades in phases, as explained later.</span></span>

<span data-ttu-id="b643d-107">마이크로 서비스 기반 응용 프로그램은 종종 하트비트 또는 상태 검사를 사용하여 성능 모니터, 스케줄러 및 오케스트레이터에서 다양한 서비스를 추적할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-107">Microservices-based applications often use heartbeats or health checks to enable their performance monitors, schedulers, and orchestrators to keep track of the multitude of services.</span></span> <span data-ttu-id="b643d-108">서비스에서 요구 시 또는 일정에 따라 "활성(I’m alive)" 신호를 보낼 수 없는 경우, 업데이트를 배포할 때 응용 프로그램이 위험에 직면할 수 있고, 단순히 오류를 너무 늦게 감지하여 연속 오류를 방지할 수 없음으로써 심각한 중단 상태에 놓일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-108">If services cannot send some sort of “I’m alive” signal, either on demand or on a schedule, your application might face risks when you deploy updates, or it might simply detect failures too late and not be able to stop cascading failures that can end up in major outages.</span></span>

<span data-ttu-id="b643d-109">일반적인 모델에서 서비스는 상태에 대한 보고서를 보내고, 해당 정보를 집계하여 응용 프로그램 상태 전체에 대한 보기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-109">In the typical model, services send reports about their status, and that information is aggregated to provide an overall view of the state of health of your application.</span></span> <span data-ttu-id="b643d-110">오케스트레이터를 사용하는 경우 클러스터가 적절하게 작동할 수 있도록 오케스트레이터의 클러스터에 상태 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-110">If you are using an orchestrator, you can provide health information to your orchestrator’s cluster, so that the cluster can act accordingly.</span></span> <span data-ttu-id="b643d-111">응용 프로그램에 맞게 사용자 지정된 고품질 상태 보고에 투자하는 경우 실행 중인 응용 프로그램에 대한 문제를 훨씬 쉽게 검색하고 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-111">If you invest in high-quality health reporting that is customized for your application, you can detect and fix issues for your running application much more easily.</span></span>

## <a name="implementing-health-checks-in-aspnet-core-services"></a><span data-ttu-id="b643d-112">ASP.NET Core 서비스에서 상태 검사 구현</span><span class="sxs-lookup"><span data-stu-id="b643d-112">Implementing health checks in ASP.NET Core services</span></span>

<span data-ttu-id="b643d-113">ASP.NET Core 마이크로 서비스 또는 웹 응용 프로그램을 개발할 때 ASP.NET 팀에서 `HealthChecks`라는 라이브러리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-113">When developing an ASP.NET Core microservice or web application, you can use a library named `HealthChecks` from the ASP.NET team.</span></span> <span data-ttu-id="b643d-114">초기 릴리스는 이 [GitHub 리포지토리](https://github.com/dotnet-architecture/HealthChecks)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-114">Early release is available at this [GitHub repo](https://github.com/dotnet-architecture/HealthChecks).</span></span>

<span data-ttu-id="b643d-115">이 라이브러리는 사용하기 쉽고 응용 프로그램에 필요한 특정 외부 리소스(예: SQL Server 데이터베이스 또는 원격 API)가 사용할 수 있습니다. 작동하는지 확인할 수 있는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-115">This library is easy to use and provides features that let you validate that any specific external resource needed for your application (like a SQL Server database or remote API) is working properly.</span></span> <span data-ttu-id="b643d-116">이 라이브러리를 사용하면 나중에 설명하는 대로 정상 리소스에 대한 의미를 결정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-116">When you use this library, you can also decide what it means that the resource is healthy, as we explain later.</span></span>

<span data-ttu-id="b643d-117">이 라이브러리를 사용하려면 먼저 마이크로 서비스에서 라이브러리를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-117">In order to use this library, you need to first use the library in your microservices.</span></span> <span data-ttu-id="b643d-118">다음으로, 상태 보고서를 쿼리하는 프런트 엔드 응용 프로그램이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-118">Second, you need a front-end application that queries for the health reports.</span></span> <span data-ttu-id="b643d-119">프런트 엔드 응용 프로그램은 사용자 지정 보고 응용 프로그램이거나 성능 상태에 따라 대응할 수 있는 오케스트레이터 자체일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-119">That front end application could be a custom reporting application, or it could be an orchestrator itself that can react accordingly to the health states.</span></span>

### <a name="using-the-healthchecks-library-in-your-back-end-aspnet-microservices"></a><span data-ttu-id="b643d-120">백 엔드 ASP.NET 마이크로 서비스에서 HealthChecks 라이브러리 사용</span><span class="sxs-lookup"><span data-stu-id="b643d-120">Using the HealthChecks library in your back end ASP.NET microservices</span></span>

<span data-ttu-id="b643d-121">eShopOnContainers 샘플 응용 프로그램에서 HealthChecks 라이브러리가 사용되는 방식을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-121">You can see how the HealthChecks library is used in the eShopOnContainers sample application.</span></span> <span data-ttu-id="b643d-122">시작하려면 각 마이크로 서비스에 대한 성능 상태를 구성하는 항목을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-122">To begin, you need to define what constitutes a healthy status for each microservice.</span></span> <span data-ttu-id="b643d-123">샘플 응용 프로그램에서 마이크로 서비스 API가 HTTP를 통해 액세스할 수 있고 관련 SQL Server 데이터베이스도 사용할 수 있으면 마이크로 서비스가 정상입니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-123">In the sample application, the microservices are healthy if the microservice API is accessible via HTTP and if its related SQL Server database is also available.</span></span>

<span data-ttu-id="b643d-124">나중에 HealthChecks 라이브러리를 NuGet 패키지로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-124">In the future, you will be able to install the HealthChecks library as a NuGet package.</span></span> <span data-ttu-id="b643d-125">그러나 이 문서를 작성한 시점 이후로는 코드를 솔루션의 일부로 다운로드하고 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-125">But as of this writing, you need to download and compile the code as part of your solution.</span></span> <span data-ttu-id="b643d-126">복제에 사용할 수 있는 코드가 https://github.com/dotnet-architecture/HealthChecks 솔루션을 다음 폴더에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-126">Clone the code available at https://github.com/dotnet-architecture/HealthChecks and copy the following folders to your solution:</span></span>

  - <span data-ttu-id="b643d-127">src/common</span><span class="sxs-lookup"><span data-stu-id="b643d-127">src/common</span></span>
  - <span data-ttu-id="b643d-128">src/Microsoft.AspNetCore.HealthChecks</span><span class="sxs-lookup"><span data-stu-id="b643d-128">src/Microsoft.AspNetCore.HealthChecks</span></span>
  - <span data-ttu-id="b643d-129">src/Microsoft.Extensions.HealthChecks</span><span class="sxs-lookup"><span data-stu-id="b643d-129">src/Microsoft.Extensions.HealthChecks</span></span>
  - <span data-ttu-id="b643d-130">src/Microsoft.Extensions.HealthChecks.SqlServer</span><span class="sxs-lookup"><span data-stu-id="b643d-130">src/Microsoft.Extensions.HealthChecks.SqlServer</span></span>

<span data-ttu-id="b643d-131">Azure(Microsoft.Extensions.HealthChecks.AzureStorage)에 대한 것과 같은 추가 검사를 사용할 수도 있지만, 이 버전의 eShopOnContainers에는 Azure에 대한 종속성이 없으므로 이러한 검사는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-131">You could also use additional checks like the ones for Azure (Microsoft.Extensions.HealthChecks.AzureStorage), but since this version of eShopOnContainers does not have any dependency on Azure, you do not need it.</span></span> <span data-ttu-id="b643d-132">eShopOnContainers는 ASP.NET Core를 기반으로 하므로 ASP.NET 상태 검사가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-132">You do not need the ASP.NET health checks, because eShopOnContainers is based on ASP.NET Core.</span></span>

<span data-ttu-id="b643d-133">그림 10-6에서는 모든 마이크로 서비스에서 구성 요소로 사용할 준비가 된 Visual Studio의 HealthChecks 라이브러리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-133">Figure 10-6 shows the HealthChecks library in Visual Studio, ready to be used as a building block by any microservices.</span></span>

![](./media/image6.png)

<span data-ttu-id="b643d-134">**그림 10-6**</span><span class="sxs-lookup"><span data-stu-id="b643d-134">**Figure 10-6**.</span></span> <span data-ttu-id="b643d-135">Visual Studio 솔루션의 ASP.NET Core HealthChecks 라이브러리 소스 코드</span><span class="sxs-lookup"><span data-stu-id="b643d-135">ASP.NET Core HealthChecks library source code in a Visual Studio solution</span></span>

<span data-ttu-id="b643d-136">앞에서 소개한 대로 각 마이크로 서비스 프로젝트에서 가장 먼저 수행할 작업은 세 가지 HealthChecks 라이브러리에 대한 참조를 추가하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-136">As introduced earlier, the first thing to do in each microservice project is to add a reference to the three HealthChecks libraries.</span></span> <span data-ttu-id="b643d-137">그런 다음, 해당 마이크로 서비스에서 수행하려는 상태 검사 작업을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-137">After that, you add the health check actions that you want to perform in that microservice.</span></span> <span data-ttu-id="b643d-138">이러한 작업은 기본적으로 다른 마이크로 서비스(HttpUrlCheck) 또는 데이터베이스(현재의 SQL Server 데이터베이스에 대한 SqlCheck\*)에 종속됩니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-138">These actions are basically dependencies on other microservices (HttpUrlCheck) or databases (currently SqlCheck\* for SQL Server databases).</span></span> <span data-ttu-id="b643d-139">작업은 각 ASP.NET 마이크로 서비스 또는 ASP.NET 웹 응용 프로그램의 Startup 클래스 내에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-139">You add the action within the Startup class of each ASP.NET microservice or ASP.NET web application.</span></span>

<span data-ttu-id="b643d-140">각 서비스 또는 웹 응용 프로그램은 HTTP 또는 데이터베이스 종속성을 모두 하나의 AddHealthCheck 메서드로 추가하여 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-140">Each service or web application should be configured by adding all its HTTP or database dependencies as one AddHealthCheck method.</span></span> <span data-ttu-id="b643d-141">예를 들어 eShopOnContainers의 MVC 웹 응용 프로그램은 여러 서비스에 종속되므로 상태 검사에 몇 가지 AddCheck 메서드가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-141">For example, the MVC web application from eShopOnContainers depends on many services, therefore has several AddCheck methods added to the health checks.</span></span>

<span data-ttu-id="b643d-142">예를 들어 다음 코드에서 카탈로그 마이크로 서비스가 SQL Server 데이터베이스에 대한 종속성을 추가하는 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-142">For instance, in the following code you can see how the catalog microservice adds a dependency on its SQL Server database.</span></span>

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

<span data-ttu-id="b643d-143">그러나 eShopOnContainers의 MVC 웹 응용 프로그램에는 나머지 마이크로 서비스에 대한 여러 종속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-143">However, the MVC web application of eShopOnContainers has multiple dependencies on the rest of the microservices.</span></span> <span data-ttu-id="b643d-144">따라서 다음 예제와 같이 각 마이크로 서비스에 대해 하나의 AddUrlCheck 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-144">Therefore, it calls one AddUrlCheck method for each microservice, as shown in the following example:</span></span>

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

<span data-ttu-id="b643d-145">따라서 마이크로 서비스는 모든 검사가 정상일 때까지 "정상" 상태를 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-145">Thus, a microservice will not provide a “healthy” status until all its checks are healthy as well.</span></span>

<span data-ttu-id="b643d-146">마이크로 서비스가 서비스 또는 SQL Server에 종속되지 않으면 정상("OK") 검사를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-146">If the microservice does not have a dependency on a service or on SQL Server, you should just add a Healthy("Ok") check.</span></span> <span data-ttu-id="b643d-147">다음 코드는 eShopOnContainers basket.api 마이크로 서비스에서 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-147">The following code is from the eShopOnContainers basket.api microservice.</span></span> <span data-ttu-id="b643d-148">(장바구니 마이크로 서비스에서 Redis 캐시를 사용하지만, 라이브러리에는 아직 Redis 상태 검사 공급자가 포함되어 있지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="b643d-148">(The basket microservice uses the Redis cache, but the library does not yet include a Redis health check provider.)</span></span>

```csharp
services.AddHealthChecks(checks =>
{
    checks.AddValueTaskCheck("HTTP Endpoint", () => new
        ValueTask<IHealthCheckResult>(HealthCheckResult.Healthy("Ok")));
});
```

<span data-ttu-id="b643d-149">서비스 또는 웹 응용 프로그램에서 상태 검사 엔드포인트를 공개하려면 UseHealthChecks(\[*url\_for\_health\_checks*\]) 확장 메서드를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-149">For a service or web application to expose the health check endpoint, it has to enable the UseHealthChecks(\[*url\_for\_health\_checks*\]) extension method.</span></span> <span data-ttu-id="b643d-150">이 메서드는 아래 코드와 같이 UseKestrel 바로 뒤에 ASP.NET Core 서비스 또는 웹 응용 프로그램의 Program 클래스의 main 메서드에서 WebHostBuilder 수준으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-150">This method goes at the WebHostBuilder level in the main method of the Program class of your ASP.NET Core service or web application, right after UseKestrel as shown in the code below.</span></span>

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

<span data-ttu-id="b643d-151">프로세스는 다음과 같이 작동합니다. 각 마이크로 서비스에서 /hc 엔드포인트를 공개합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-151">The process works like this: each microservice exposes the endpoint /hc.</span></span> <span data-ttu-id="b643d-152">이 엔드포인트는 HealthChecks 라이브러리 ASP.NET Core 미들웨어에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-152">That endpoint is created by the HealthChecks library ASP.NET Core middleware.</span></span> <span data-ttu-id="b643d-153">해당 엔드포인트가 호출되면 Startup 클래스의 AddHealthChecks 메서드에 구성된 상태 검사를 모두 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-153">When that endpoint is invoked, it runs all the health checks that are configured in the AddHealthChecks method in the Startup class.</span></span>

<span data-ttu-id="b643d-154">UseHealthChecks 메서드에는 포트 또는 경로가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-154">The UseHealthChecks method expects a port or a path.</span></span> <span data-ttu-id="b643d-155">해당 포트 또는 경로는 서비스의 성능 상태를 확인하는 데 사용할 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-155">That port or path is the endpoint to use to check the health state of the service.</span></span> <span data-ttu-id="b643d-156">예를 들어 카탈로그 마이크로 서비스는/hc 경로를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-156">For instance, the catalog microservice uses the path /hc.</span></span>

### <a name="caching-health-check-responses"></a><span data-ttu-id="b643d-157">상태 검사 응답 캐싱</span><span class="sxs-lookup"><span data-stu-id="b643d-157">Caching health check responses</span></span>

<span data-ttu-id="b643d-158">서비스에서 DoS(서비스 거부) 공격이 발생하지 않도록 하려거나 단순히 리소스를 너무 자주 검사하여 서비스 성능에 영향을 미치지 않으려고 하는 경우에는 각 상태 검사에 대해 반환을 캐시하고 캐시 기간을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-158">Since you do not want to cause a Denial of Service (DoS) in your services, or you simply do not want to impact service performance by checking resources too frequently, you can cache the returns and configure a cache duration for each health check.</span></span>

<span data-ttu-id="b643d-159">기본적으로 캐시 기간은 내부적으로 5분으로 설정되지만, 다음 코드와 같이 각 상태 검사에 대한 해당 캐시 기간을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-159">By default, the cache duration is internally set to 5 minutes, but you can change that cache duration on each health check, as in the following code:</span></span>

```csharp
checks.AddUrlCheck(Configuration["CatalogUrl"],1); // 1 min as cache duration
```

### <a name="querying-your-microservices-to-report-about-their-health-status"></a><span data-ttu-id="b643d-160">마이크로 서비스를 쿼리하여 성능 상태에 대해 보고</span><span class="sxs-lookup"><span data-stu-id="b643d-160">Querying your microservices to report about their health status</span></span>

<span data-ttu-id="b643d-161">여기서 설명한 대로 상태 검사를 구성한 경우 Docker에서 마이크로 서비스가 실행되면 브라우저에서 정상인지 여부를 직접 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-161">When you have configured health checks as described here, once the microservice is running in Docker, you can directly check from a browser if it is healthy.</span></span> <span data-ttu-id="b643d-162">(이 경우 컨테이너 포트를 Docker 호스트 외부에 게시해야 localhost 또는 외부 Docker 호스트 IP를 통해 컨테이너에 액세스할 수 있습니다.) 그림 10-7에서는 브라우저의 요청과 해당 응답을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-162">(This does require that you are publishing the container port out of the Docker host, so you can access the container through localhost or through the external Docker host IP.) Figure 10-7 shows a request in a browser and the corresponding response.</span></span>

![](./media/image7.png)

<span data-ttu-id="b643d-163">**그림 10-7**</span><span class="sxs-lookup"><span data-stu-id="b643d-163">**Figure 10-7**.</span></span> <span data-ttu-id="b643d-164">브라우저에서 단일 서비스의 성능 상태 검사</span><span class="sxs-lookup"><span data-stu-id="b643d-164">Checking health status of a single service from a browser</span></span>

<span data-ttu-id="b643d-165">이 테스트에서는 catalog.api 마이크로 서비스(5101 포트에서 실행 중)가 정상이며, JSON에서 200 HTTP 상태 및 상태 정보를 반환한다는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-165">In that test, you can see that the catalog.api microservice (running on port 5101) is healthy, returning HTTP status 200 and status information in JSON.</span></span> <span data-ttu-id="b643d-166">또한 이 서비스는 내부적으로 SQL Server 데이터베이스 종속성의 상태를 검사했고 상태 검사에서 직접 정상으로 보고되었음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-166">It also means that internally the service also checked the health of its SQL Server database dependency and that health check was reported itself as healthy.</span></span>

## <a name="using-watchdogs"></a><span data-ttu-id="b643d-167">Watchdog 사용</span><span class="sxs-lookup"><span data-stu-id="b643d-167">Using watchdogs</span></span>

<span data-ttu-id="b643d-168">Watchdog은 앞에서 소개한 HealthChecks 라이브러리로 쿼리하여 서비스 전반의 상태와 로드를 감시하고 마이크로 서비스에 대한 상태를 보고할 수 있는 별도의 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-168">A watchdog is a separate service that can watch health and load across services, and report health about the microservices by querying with the HealthChecks library introduced earlier.</span></span> <span data-ttu-id="b643d-169">이렇게 하면 단일 서비스의 보기를 기반으로 하여 검색되지 않는 오류를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-169">This can help prevent errors that would not be detected based on the view of a single service.</span></span> <span data-ttu-id="b643d-170">또한 Watchdog은 사용자 개입 없이 알려진 조건에 대한 수정 작업을 수행할 수 있는 코드를 호스팅하는 데 적합한 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-170">Watchdogs also are a good place to host code that can perform remediation actions for known conditions without user interaction.</span></span>

<span data-ttu-id="b643d-171">eShopOnContainers 샘플에는 그림 10-8과 같이 샘플 상태 검사 보고서를 표시하는 웹 페이지가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-171">The eShopOnContainers sample contains a web page that displays sample health check reports, as shown in Figure 10-8.</span></span> <span data-ttu-id="b643d-172">이는 단지 eShopOnContainers에서 마이크로 서비스 및 웹 응용 프로그램의 상태를 보여 줄 뿐이므로 가장 간단한 Watchdog입니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-172">This is the simplest watchdog you could have, since all it does is shows the state of the microservices and web applications in eShopOnContainers.</span></span> <span data-ttu-id="b643d-173">일반적으로 비정상 상태가 검색되면 Watchdog에서 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-173">Usually a watchdog also takes actions when it detects unhealthy states.</span></span>

![](./media/image8.png)

<span data-ttu-id="b643d-174">**그림 10-8**</span><span class="sxs-lookup"><span data-stu-id="b643d-174">**Figure 10-8**.</span></span> <span data-ttu-id="b643d-175">eShopOnContainers의 샘플 상태 검사 보고서</span><span class="sxs-lookup"><span data-stu-id="b643d-175">Sample health check report in eShopOnContainers</span></span>

<span data-ttu-id="b643d-176">요약하면, ASP.NET Core HealthChecks 라이브러리의 ASP.NET 미들웨어는 각 마이크로 서비스에 대해 단일 상태 검사 엔드포인트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-176">In summary, the ASP.NET middleware of the ASP.NET Core HealthChecks library provides a single health check endpoint for each microservice.</span></span> <span data-ttu-id="b643d-177">이렇게 하면 내부에 정의된 모든 상태 검사가 실행되고, 모든 검사에 따라 전체 성능 상태가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-177">This will execute all the health checks defined within it and return an overall health state depending on all those checks.</span></span>

<span data-ttu-id="b643d-178">HealthChecks 라이브러리는 향후 외부 리소스에 대한 새로운 상태 검사를 통해 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-178">The HealthChecks library is extensible through new health checks of future external resources.</span></span> <span data-ttu-id="b643d-179">예를 들어 나중에 Redis 캐시 및 다른 데이터베이스에 대한 상태 검사가 라이브러리에 제공될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-179">For example, we expect that in the future the library will have health checks for Redis cache and for other databases.</span></span> <span data-ttu-id="b643d-180">라이브러리를 사용하면 여러 서비스 또는 응용 프로그램 종속성을 통해 상태를 보고할 수 있고, 이러한 상태 검사에 따라 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-180">The library allows health reporting by multiple service or application dependencies, and you can then take actions based on those health checks.</span></span>

## <a name="health-checks-when-using-orchestrators"></a><span data-ttu-id="b643d-181">오케스트레이터 사용 시의 상태 검사</span><span class="sxs-lookup"><span data-stu-id="b643d-181">Health checks when using orchestrators</span></span>

<span data-ttu-id="b643d-182">Docker Swarm, Kubernetes 및 Service Fabric과 같은 오케스트레이션은 마이크로 서비스의 가용성을 모니터링하기 위해 정기적으로 마이크로 서비스 테스트 요청을 보내 상태 검사를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-182">To monitor the availability of your microservices, orchestrators like Docker Swarm, Kubernetes, and Service Fabric periodically perform health checks by sending requests to test the microservices.</span></span> <span data-ttu-id="b643d-183">오케스트레이터에서 비정상 서비스/컨테이너로 인식하면 해당 인스턴스에 대한 요청 라우팅을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-183">When an orchestrator determines that a service/container is unhealthy, it stops routing requests to that instance.</span></span> <span data-ttu-id="b643d-184">또한 일반적으로 해당 컨테이너의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-184">It also usually creates a new instance of that container.</span></span>

<span data-ttu-id="b643d-185">예를 들어 대부분의 오케스트레이터에서 상태 검사를 사용하여 가동 중지 시간이 없는 배포를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-185">For instance, most orchestrators can use health checks to manage zero-downtime deployments.</span></span> <span data-ttu-id="b643d-186">서비스/컨테이너의 상태가 정상으로 변경될 때만 오케스트레이터에서 트래픽을 서비스/컨테이너 인스턴스로 라우팅하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-186">Only when the status of a service/container changes to healthy will the orchestrator start routing traffic to service/container instances.</span></span>

<span data-ttu-id="b643d-187">상태 모니터링은 오케스트레이터에서 응용 프로그램 업그레이드를 수행할 때 특히 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-187">Health monitoring is especially important when an orchestrator performs an application upgrade.</span></span> <span data-ttu-id="b643d-188">Azure Service Fabric과 같은 일부 오케스트레이터는 서비스를 단계별로 업데이트합니다. 예를 들어 응용 프로그램 업그레이드마다 클러스터 표면의 1/5을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-188">Some orchestrators (like Azure Service Fabric) update services in phases—for example, they might update one-fifth of the cluster surface for each application upgrade.</span></span> <span data-ttu-id="b643d-189">동시에 업그레이드되는 노드 집합을 *업그레이드 도메인*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-189">The set of nodes that is upgraded at the same time is referred to as an *upgrade domain*.</span></span> <span data-ttu-id="b643d-190">각 업그레이드 도메인을 업그레이드하고 사용자가 사용할 수 있게 되면, 먼저 해당 업그레이드 도메인이 상태 검사를 통과한 후에 배포가 다음 업그레이드 도메인으로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-190">After each upgrade domain has been upgraded and is available to users, that upgrade domain must pass health checks before the deployment moves to the next upgrade domain.</span></span>

<span data-ttu-id="b643d-191">서비스 상태의 또 다른 측면은 서비스의 메트릭을 보고하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-191">Another aspect of service health is reporting metrics from the service.</span></span> <span data-ttu-id="b643d-192">이는 Service Fabric과 같은 일부 오케스트레이터의 상태 모델에 대한 고급 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-192">This is an advanced capability of the health model of some orchestrators, like Service Fabric.</span></span> <span data-ttu-id="b643d-193">메트릭은 리소스 사용량의 균형을 조정하는 데 사용되므로 오케스트레이터를 사용할 때 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-193">Metrics are important when using an orchestrator because they are used to balance resource usage.</span></span> <span data-ttu-id="b643d-194">또한 메트릭은 시스템 상태를 나타내는 지표가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-194">Metrics also can be an indicator of system health.</span></span> <span data-ttu-id="b643d-195">예를 들어 많은 마이크로 서비스가 있는 응용 프로그램이 있을 수 있으며, 각 인스턴스에서 RPS(초당 요청 수)를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-195">For example, you might have an application that has many microservices, and each instance reports a requests-per-second (RPS) metric.</span></span> <span data-ttu-id="b643d-196">한 서비스에서 다른 서비스보다 더 많은 리소스(메모리, 프로세서 등)를 사용하는 경우, 오케스트레이터는 클러스터에서 서비스 인스턴스를 이동하여 리소스 사용률을 유지하려고 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-196">If one service is using more resources (memory, processor, etc.) than another service, the orchestrator could move service instances around in the cluster to try to maintain even resource utilization.</span></span>

<span data-ttu-id="b643d-197">Azure Service Fabric을 사용하는 경우 단순한 상태 검사보다 더 향상된 고급 기능을 갖춘 자체의 [상태 모니터링 모델](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction)을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-197">Note that if you are using Azure Service Fabric, it provides its own [Health Monitoring model](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction), which is more advanced than simple health checks.</span></span>

## <a name="advanced-monitoring-visualization-analysis-and-alerts"></a><span data-ttu-id="b643d-198">고급 모니터링: 시각화, 분석 및 경고</span><span class="sxs-lookup"><span data-stu-id="b643d-198">Advanced monitoring: visualization, analysis, and alerts</span></span>

<span data-ttu-id="b643d-199">모니터링의 마지막 부분은 이벤트 스트림을 시각화하고, 서비스 성능에 대해 보고하고, 문제가 검색되면 경고하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-199">The final part of monitoring is visualizing the event stream, reporting on service performance, and alerting when an issue is detected.</span></span> <span data-ttu-id="b643d-200">이 모니터링 측면에 대해 서로 다른 솔루션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-200">You can use different solutions for this aspect of monitoring.</span></span>

<span data-ttu-id="b643d-201">[ASP.NET Core HealthChecks](https://github.com/aspnet/HealthChecks)에 대해 설명할 때 보여 준 사용자 지정 페이지와 같이 서비스 상태를 표시하는 간단한 사용자 지정 응용 프로그램을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-201">You can use simple custom applications showing the state of your services, like the custom page we showed when we explained [ASP.NET Core HealthChecks](https://github.com/aspnet/HealthChecks).</span></span> <span data-ttu-id="b643d-202">또는 Azure Application Insights 및 Operations Management Suite와 같은 고급 도구를 사용하여 이벤트 스트림에 따라 경고를 발생시킬 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-202">Or you could use more advanced tools like Azure Application Insights and Operations Management Suite to raise alerts based on the stream of events.</span></span>

<span data-ttu-id="b643d-203">마지막으로 모든 이벤트 스트림을 저장하는 경우 Microsoft Power BI 또는 타사 솔루션(예: Kibana 또는 Splunk)을 사용하여 데이터를 시각화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b643d-203">Finally, if you were storing all the event streams, you can use Microsoft Power BI or a third-party solution like Kibana or Splunk to visualize the data.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b643d-204">추가 자료</span><span class="sxs-lookup"><span data-stu-id="b643d-204">Additional resources</span></span>

-   <span data-ttu-id="b643d-205">**ASP.NET Core HealthChecks** (초기 릴리스) [*https://github.com/aspnet/HealthChecks/*](https://github.com/aspnet/HealthChecks/)</span><span class="sxs-lookup"><span data-stu-id="b643d-205">**ASP.NET Core HealthChecks** (early release) [*https://github.com/aspnet/HealthChecks/*](https://github.com/aspnet/HealthChecks/)</span></span>

-   <span data-ttu-id="b643d-206">**서비스 패브릭 상태 모니터링 소개**
    [*https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction*](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction)</span><span class="sxs-lookup"><span data-stu-id="b643d-206">**Introduction to Service Fabric health monitoring**
[*https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction*](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction)</span></span>

-   <span data-ttu-id="b643d-207">**Azure 응용 프로그램 통찰력**
    [*https://azure.microsoft.com/services/application-insights/*](https://azure.microsoft.com/services/application-insights/)</span><span class="sxs-lookup"><span data-stu-id="b643d-207">**Azure Application Insights**
[*https://azure.microsoft.com/services/application-insights/*](https://azure.microsoft.com/services/application-insights/)</span></span>

-   <span data-ttu-id="b643d-208">**Microsoft Operations Management Suite**
    [*https://www.microsoft.com/en-us/cloud-platform/operations-management-suite*](https://www.microsoft.com/en-us/cloud-platform/operations-management-suite)</span><span class="sxs-lookup"><span data-stu-id="b643d-208">**Microsoft Operations Management Suite**
[*https://www.microsoft.com/en-us/cloud-platform/operations-management-suite*](https://www.microsoft.com/en-us/cloud-platform/operations-management-suite)</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="b643d-209">[이전] (implement-circuit-breaker-pattern.md) [다음] (../secure-net-microservices-web-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="b643d-209">[Previous] (implement-circuit-breaker-pattern.md) [Next] (../secure-net-microservices-web-applications/index.md)</span></span>
