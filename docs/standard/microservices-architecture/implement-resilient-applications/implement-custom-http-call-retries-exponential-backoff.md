---
title: 지수 백오프를 사용하여 사용자 지정 HTTP 호출 다시 시도 구현
description: 컨테이너화된 .NET 응용 프로그램용 .NET 마이크로 서비스 아키텍처 | 지수 백오프를 사용하여 사용자 지정 HTTP 호출 다시 시도 구현
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 10751bb74ed648839fabec67ff7a71e458fb2a44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33574948"
---
# <a name="implementing-custom-http-call-retries-with-exponential-backoff"></a>지수 백오프를 사용하여 사용자 지정 HTTP 호출 다시 시도 구현

복원력 있는 마이크로 서비스를 만들기 위해 가능한 HTTP 오류 시나리오를 처리해야 합니다. 이를 위해 지수 백오프를 사용하여 재시도의 고유한 구현을 만들 수 있습니다.

지수 백오프는 임시 리소스 비가용성 처리 외에도 클라우드 공급자가 사용 오버로드를 방지하기 위해 리소스의 가용성을 제한할 수 있다는 점을 고려해야 합니다. 예를 들어 신속하게 과도한 연결을 요청하면 클라우드 공급자에 의한 [DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)(서비스 거부) 공격으로 보일 수 있습니다. 결과적으로 용량 임계값에 도달한 경우 다시 연결 요청의 크기를 조정하는 메커니즘을 제공해야 합니다.

초기 탐색을 사용하여 [RetryWithExponentialBackoff.cs](https://gist.github.com/CESARDELATORRE/6d7f647b29e55fdc219ee1fd2babb260)와 같이 지수 백오프에 대한 유틸리티 클래스를 포함하는 고유한 코드 외에도 다음과 같은 코드([GitHub 리포지토리](https://gist.github.com/CESARDELATORRE/d80c6423a1aebaffaf387469f5194f5b)에서 제공됨)를 구현할 수 있습니다.

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

클라이언트 C\# 응용 프로그램(다른 웹 API 클라이언트 마이크로 서비스, ASP.NET MVC 응용 프로그램 또는 C\# Xamarin 응용 프로그램)에서 쉽게 이 코드를 사용할 수 있습니다. 다음 예제에서는 HttpClient 클래스를 사용하는 방법을 보여줍니다.

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

그러나 이 코드는 개념 증명으로만 적합합니다. 다음 항목에서는 더 정교하고 검증된 라이브러리를 사용하는 방법을 설명합니다.


>[!div class="step-by-step"]
[이전] (implement-resilient-entity-framework-core-sql-connections.md) [다음] (implement-http-call-retries-exponential-backoff-polly.md)
