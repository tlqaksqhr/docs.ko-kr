---
title: "지 수 백오프 하는 사용자 지정 HTTP 호출 재시도 구현합니다."
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 지 수 백오프 하는 사용자 지정 HTTP 호출 재시도 구현합니다."
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 4449e5d7e0ca3c81aead26fac653de3ba2187a92
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-custom-http-call-retries-with-exponential-backoff"></a><span data-ttu-id="c5ba6-104">지 수 백오프 하는 사용자 지정 HTTP 호출 재시도 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba6-104">Implementing custom HTTP call retries with exponential backoff</span></span>

<span data-ttu-id="c5ba6-105">복원 력 있는 microservices를 만들기 위해 가능한 HTTP 오류 시나리오를 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba6-105">In order to create resilient microservices, you need to handle possible HTTP failure scenarios.</span></span> <span data-ttu-id="c5ba6-106">이 위해 다시 시도 횟수의 사용자 지정 구현을 지 수 백오프를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba6-106">For that purpose, you could create your own implementation of retries with exponential backoff.</span></span>

<span data-ttu-id="c5ba6-107">사용할 수 없는 임시 리소스를 처리 하는 것 외에도 지 수 백오프도 클라우드 공급자 사용 오버 로드를 방지 하기 위해 리소스의 가용성을 제한할 수 정도 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba6-107">In addition to handling temporal resource unavailability, the exponential backoff also needs to take into account that the cloud provider might throttle availability of resources to prevent usage overload.</span></span> <span data-ttu-id="c5ba6-108">예를 들어 너무 많은 연결 요청을 신속 하 게 만드는 노출 될 수로 서비스 거부 ([DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)) 클라우드 공급자가 공격입니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba6-108">For example, creating too many connection requests very quickly might be viewed as a Denial of Service ([DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)) attack by the cloud provider.</span></span> <span data-ttu-id="c5ba6-109">결과적으로, 용량 임계값에 발생 한 경우 다시 연결 요청을 확장 하는 메커니즘을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba6-109">As a result, you need to provide a mechanism to scale back connection requests when a capacity threshold has been encountered.</span></span>

<span data-ttu-id="c5ba6-110">와 같이 지 수 백오프에 대 한 유틸리티 클래스를 사용 하 여 사용자 고유의 코드를 구현할 수는 초기 탐색으로 [RetryWithExponentialBackoff.cs](https://gist.github.com/CESARDELATORRE/6d7f647b29e55fdc219ee1fd2babb260), 다음과 같은 코드 더하기 (도에서 제공 되는 [GitHub 리포지토리 ](https://gist.github.com/CESARDELATORRE/d80c6423a1aebaffaf387469f5194f5b)).</span><span class="sxs-lookup"><span data-stu-id="c5ba6-110">As an initial exploration, you could implement your own code with a utility class for exponential backoff as in [RetryWithExponentialBackoff.cs](https://gist.github.com/CESARDELATORRE/6d7f647b29e55fdc219ee1fd2babb260), plus code like the following (which is also available on a [GitHub repo](https://gist.github.com/CESARDELATORRE/d80c6423a1aebaffaf387469f5194f5b)).</span></span>

```csharp
public sealed class RetryWithExponentialBackoff
{
    private readonly int maxRetries, delayMilliseconds, maxDelayMilliseconds;

    public RetryWithExponentialBackoff(int maxRetries = 50,
        int delayMilliseconds = 200,
        int maxDelayMilliseconds = 2000)
    {
        this.maxRetries = maxRetries;
        this.delayMilliseconds = delayMilliseconds;
        this.maxDelayMilliseconds = maxDelayMilliseconds;
    }

    public async Task RunAsync(Func<Task> func)
    {
        ExponentialBackoff backoff = new ExponentialBackoff(this.maxRetries,
            this.delayMilliseconds,
            this.maxDelayMilliseconds);
        retry:
        try
        {
            await func();
        }
        catch (Exception ex) when (ex is TimeoutException ||
            ex is System.Net.Http.HttpRequestException)
        {
            Debug.WriteLine("Exception raised is: " +
                ex.GetType().ToString() +
                " –Message: " + ex.Message +
                " -- Inner Message: " +
                ex.InnerException.Message);
            await backoff.Delay();
            goto retry;
        }
    }
}

public struct ExponentialBackoff
{
    private readonly int m_maxRetries, m_delayMilliseconds, m_maxDelayMilliseconds;
    private int m_retries, m_pow;

    public ExponentialBackoff(int maxRetries, int delayMilliseconds,
        int maxDelayMilliseconds)
    {
        m_maxRetries = maxRetries;
        m_delayMilliseconds = delayMilliseconds;
        m_maxDelayMilliseconds = maxDelayMilliseconds;
        m_retries = 0;
        m_pow = 1;
    }

    public Task Delay()
    {
        if (m_retries == m_maxRetries)
        {
            throw new TimeoutException("Max retry attempts exceeded.");
        }
        ++m_retries;
        if (m_retries < 31)
        {
            m_pow = m_pow << 1; // m_pow = Pow(2, m_retries - 1)
        }
        int delay = Math.Min(m_delayMilliseconds * (m_pow - 1) / 2,
            m_maxDelayMilliseconds);
        return Task.Delay(delay);
    }
}
```

<span data-ttu-id="c5ba6-111">이 코드를 사용 하 여 C 클라이언트에서\# 응용 프로그램 (다른 웹 API에 대 한 클라이언트 마이크로 서비스, ASP.NET MVC 응용 프로그램 또는 C에도\# Xamarin 응용 프로그램)는 단순 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba6-111">Using this code in a client C\# application (another Web API client microservice, an ASP.NET MVC application, or even a C\# Xamarin application) is straightforward.</span></span> <span data-ttu-id="c5ba6-112">다음 예제에서는 어떻게 HttpClient 클래스를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba6-112">The following example shows how, using the HttpClient class.</span></span>

```csharp
public async Task<Catalog> GetCatalogItems(int page,int take, int? brand, int? type)
{
    _apiClient = new HttpClient();
    var itemsQs = $"items?pageIndex={page}&pageSize={take}";
    var filterQs = "";
    var catalogUrl = $"{_remoteServiceBaseUrl}items{filterQs}?pageIndex={page}&pageSize={take}";
    var dataString = "";
    //
    // Using HttpClient with Retry and Exponential Backoff
    //
    var retry = new RetryWithExponentialBackoff();
    await retry.RunAsync(async () =>
    {
        // work with HttpClient call
        dataString = await _apiClient.GetStringAsync(catalogUrl);
    });
    return JsonConvert.DeserializeObject<Catalog>(dataString);
}
```

<span data-ttu-id="c5ba6-113">그러나이 코드는 개념 증명으로만 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba6-113">However, this code is suitable only as a proof of concept.</span></span> <span data-ttu-id="c5ba6-114">다음 항목에는 더 정교 하 고 검증 된 라이브러리를 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5ba6-114">The next topic explains how to use more sophisticated and proven libraries.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="c5ba6-115">[이전] [다음] (implement-http-call-retries-exponential-backoff-polly.md) (implement-resilient-entity-framework-core-sql-connections.md)</span><span class="sxs-lookup"><span data-stu-id="c5ba6-115">[Previous] (implement-resilient-entity-framework-core-sql-connections.md) [Next] (implement-http-call-retries-exponential-backoff-polly.md)</span></span>
