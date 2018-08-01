---
title: Polly를 통해 지수 백오프를 사용하여 HTTP 호출 다시 시도 구현
description: Polly와 HttpClientFactory를 사용하여 HTTP 오류를 처리하는 방법을 알아봅니다.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/10/2018
ms.openlocfilehash: c16f4c0f2ef09f346c8b46ff8089883cedcf0c7e
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37874899"
---
# <a name="implement-http-call-retries-with-exponential-backoff-with-httpclientfactory-and-polly-policies"></a><span data-ttu-id="06db5-103">HttpClientFactory 및 Polly 정책을 통해 지수 백오프를 사용하여 HTTP 호출 다시 시도 구현</span><span class="sxs-lookup"><span data-stu-id="06db5-103">Implement HTTP call retries with exponential backoff with HttpClientFactory and Polly policies</span></span>

<span data-ttu-id="06db5-104">지수 백오프를 사용하는 다시 시도는 오픈 소스 [Polly 라이브러리](https://github.com/App-vNext/Polly)와 같은 고급 .NET 라이브러리를 활용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="06db5-104">The recommended approach for retries with exponential backoff is to take advantage of more advanced .NET libraries like the open-source [Polly library](https://github.com/App-vNext/Polly).</span></span>

<span data-ttu-id="06db5-105">Polly는 복원력 및 일시적인 오류 처리 기능을 제공하는 .NET 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="06db5-105">Polly is a .NET library that provides resilience and transient-fault handling capabilities.</span></span> <span data-ttu-id="06db5-106">다시 시도, 회로 차단기, 격벽(Bulkhead) 격리, 시간 제한 및 대체와 같은 Polly 정책을 적용하여 이러한 기능을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06db5-106">You can implement those capabilities by applying Polly policies such as Retry, Circuit Breaker, Bulkhead Isolation, Timeout, and Fallback.</span></span> <span data-ttu-id="06db5-107">Polly는 .NET 4.x 및 .NET Standard 라이브러리 1.0(.NET Core 지원)을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="06db5-107">Polly targets .NET 4.x and the .NET Standard Library 1.0 (which supports .NET Core).</span></span>

<span data-ttu-id="06db5-108">그러나 사용자 지정 코드에 HttpClient와 함께 Polly의 라이브러리를 사용하는 것은 상당히 복잡할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06db5-108">However, using Polly’s library with your own custom code with HttpClient can be significantly complex.</span></span> <span data-ttu-id="06db5-109">eShopOnContainers의 원래 버전에는 Polly를 기반으로 하는 [ResilientHttpClient 구성 요소](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/Resilience/Resilience.Http/ResilientHttpClient.cs)가 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="06db5-109">In the original version of eShopOnContainers, there was a [ResilientHttpClient building-block](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/Resilience/Resilience.Http/ResilientHttpClient.cs) based on Polly.</span></span> <span data-ttu-id="06db5-110">그러나 HttpClientFactory가 출시되면서 복원력 있는 Http 통신에서 구현하기가 훨씬 쉬워져 eShopOnContainers에서 이 구성 요소가 사용되지 않게 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="06db5-110">But with the release of HttpClientFactory, resilient Http communication has become much simpler to implement, so that building-block was deprecated from eShopOnContainers.</span></span> 

<span data-ttu-id="06db5-111">다음 단계에서는 이전 섹션에서 설명한 HttpClientFactory에 통합된 Polly를 통해 Http 다시 시도를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="06db5-111">The following steps show how you can use Http retries with Polly integrated into HttpClientFactory, which is explained in the previous section.</span></span>

<span data-ttu-id="06db5-112">**ASP.NET Core 2.1 패키지 참조**</span><span class="sxs-lookup"><span data-stu-id="06db5-112">**Reference the ASP.NET Core 2.1 packages**</span></span>

<span data-ttu-id="06db5-113">프로젝트에서는 NuGet의 ASP.NET Core 2.1 패키지를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06db5-113">Your project has to be using the ASP.NET Core 2.1 packages from NuGet.</span></span> <span data-ttu-id="06db5-114">일반적으로 `AspNetCore` 메타패키지와 `Microsoft.Extensions.Http.Polly` 확장 패키지가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="06db5-114">You typically need the `AspNetCore` metapackage, and the extension package `Microsoft.Extensions.Http.Polly`.</span></span>

<span data-ttu-id="06db5-115">**스타트업에서 Polly의 재시도 정책을 사용하여 클라이언트 구성**</span><span class="sxs-lookup"><span data-stu-id="06db5-115">**Configure a client with Polly’s Retry policy, in Startup**</span></span>

<span data-ttu-id="06db5-116">이전 섹션과 같이 표준 Startup.ConfigureServices(...) 메서드에서 명명되거나 형식화된 클라이언트 HttpClient 구성을 정의해야 하지만, 이제는 아래와 같이 지수 백오프를 사용하는 Http 다시 시도에 대한 정책을 지정하는 증분 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06db5-116">As shown in previous sections, you need to define a named or typed client HttpClient configuration in your standard Startup.ConfigureServices(...) method, but now, you add incremental code specifying the policy for the Http retries with exponential backoff, as below:</span></span>

```csharp
//ConfigureServices()  - Startup.cs
services.AddHttpClient<IBasketService, BasketService>()
        .SetHandlerLifetime(TimeSpan.FromMinutes(5))  //Set lifetime to five minutes
        .AddPolicyHandler(GetRetryPolicy());
```

<span data-ttu-id="06db5-117">**AddPolicyHandler()** 는 사용할 `HttpClient` 개체에 정책을 추가하는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="06db5-117">The **AddPolicyHandler()** method is what adds policies to the `HttpClient` objects you will use.</span></span> <span data-ttu-id="06db5-118">이 경우 지수 백오프를 사용하는 Http 다시 시도에 대한 Polly 정책을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="06db5-118">In this case, it is adding a Polly’s policy for Http Retries with exponential backoff.</span></span>

<span data-ttu-id="06db5-119">좀 더 모듈화된 방법을 사용하기 위해 Http 재시도 정책은 다음 코드와 같이 ConfigureServices() 메서드 내에서 별도의 메서드로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06db5-119">In order to have a more modular approach, the Http Retry Policy can be defined in a separate method within the ConfigureServices() method, as the following code.</span></span>

```csharp
static IAsyncPolicy<HttpResponseMessage> GetRetryPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .OrResult(msg => msg.StatusCode == System.Net.HttpStatusCode.NotFound)
        .WaitAndRetryAsync(6, retryAttempt => TimeSpan.FromSeconds(Math.Pow(2,
                                                                    retryAttempt)));
}
```

<span data-ttu-id="06db5-120">Polly를 사용하면 HTTP 예외(예: 오류 로깅)가 발생하는 경우 수행할 다시 시도 횟수, 지수 백오프 구성 및 작업이 포함된 다시 시도 정책을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06db5-120">With Polly, you can define a Retry policy with the number of retries, the exponential backoff configuration, and the actions to take when there is an HTTP exception, such as logging the error.</span></span> <span data-ttu-id="06db5-121">이 경우 정책은 2초에서 시작하여 지수 다시 시도를 6회 시도하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="06db5-121">In this case, the policy is configured to try six times with an exponential retry, starting at two seconds.</span></span> 

<span data-ttu-id="06db5-122">그러면 메서드에서 다시 시도를 6회 시도하고, 각 다시 시도 사이의 시간(초)은 2초에서 시작하는 지수가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06db5-122">so it will try six times and the seconds between each retry will be exponential, starting on two seconds.</span></span>

### <a name="adding-a-jitter-strategy-to-the-retry-policy"></a><span data-ttu-id="06db5-123">지터 전략을 재시도 정책에 추가</span><span class="sxs-lookup"><span data-stu-id="06db5-123">Adding a jitter strategy to the retry policy</span></span>

<span data-ttu-id="06db5-124">일반 재시도 정책은 동시성, 확장성 및 경합이 높은 경우 시스템에 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06db5-124">A regular Retry policy can impact your system in cases of high concurrency and scalability and under high contention.</span></span> <span data-ttu-id="06db5-125">부분 작동 중단 상황에서 여러 클라이언트로부터 유사한 재시도가 대규모로 발생하는 문제를 해결하기 위해 재시도 알고리즘/정책에 지터 전략을 추가하면 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="06db5-125">To overcome peaks of similar retries coming from many clients in case of partial outages, a good workaround is to add a jitter strategy to the retry algorithm/policy.</span></span> <span data-ttu-id="06db5-126">이렇게 하면 지수 백오프에 임의성을 추가하여 종단 간 시스템의 전체 성능을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06db5-126">This can improve the overall performance of the end-to-end system by adding randomness to the exponential backoff.</span></span> <span data-ttu-id="06db5-127">이렇게 문제가 발생했을 때 급증 문제를 분산시킵니다.</span><span class="sxs-lookup"><span data-stu-id="06db5-127">This spreads out the spikes when issues arise.</span></span> <span data-ttu-id="06db5-128">일반 Polly 정책을 사용하는 경우 지터를 구현하는 코드는 다음 예제와 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06db5-128">When you use a plain Polly policy, code to implement jitter could look like the following example:</span></span>

```csharp
Random jitterer = new Random(); 
Policy
  .Handle<HttpResponseException>() // etc
  .WaitAndRetry(5,    // exponential back-off plus some jitter
      retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))  
                    + TimeSpan.FromMilliseconds(jitterer.Next(0, 100)) 
  );
```

## <a name="additional-resources"></a><span data-ttu-id="06db5-129">추가 자료</span><span class="sxs-lookup"><span data-stu-id="06db5-129">Additional resources</span></span>

-   <span data-ttu-id="06db5-130">**패턴 다시 시도**
    [*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)</span><span class="sxs-lookup"><span data-stu-id="06db5-130">**Retry pattern**
[*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)</span></span>

-   <span data-ttu-id="06db5-131">**Polly 및 HttpClientFactory**
    [*https://github.com/App-vNext/Polly/wiki/Polly-and-HttpClientFactory*](https://github.com/App-vNext/Polly/wiki/Polly-and-HttpClientFactory)</span><span class="sxs-lookup"><span data-stu-id="06db5-131">**Polly and HttpClientFactory**
[*https://github.com/App-vNext/Polly/wiki/Polly-and-HttpClientFactory*](https://github.com/App-vNext/Polly/wiki/Polly-and-HttpClientFactory)</span></span>

-   <span data-ttu-id="06db5-132">**Polly(.NET 복원력 및 transient-fault-handling 라이브러리)**</span><span class="sxs-lookup"><span data-stu-id="06db5-132">**Polly (.NET resilience and transient-fault-handling library)**</span></span>

    [*https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)

-   <span data-ttu-id="06db5-133">**Marc Brooker. 지터: 임의성으로 더 효율적인 지터 만들기**</span><span class="sxs-lookup"><span data-stu-id="06db5-133">**Marc Brooker. Jitter: Making Things Better With Randomness**</span></span>

    [*https://brooker.co.za/blog/2015/03/21/backoff.html*](https://brooker.co.za/blog/2015/03/21/backoff.html)



>[!div class="step-by-step"]
<span data-ttu-id="06db5-134">[이전](explore-custom-http-call-retries-exponential-backoff.md)
[다음](implement-circuit-breaker-pattern.md)</span><span class="sxs-lookup"><span data-stu-id="06db5-134">[Previous](explore-custom-http-call-retries-exponential-backoff.md)
[Next](implement-circuit-breaker-pattern.md)</span></span>
