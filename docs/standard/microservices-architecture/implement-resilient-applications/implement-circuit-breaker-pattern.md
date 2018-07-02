---
title: 회로 차단기 패턴 구현
description: 컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | 회로 차단기 패턴 구현
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/12/2017
ms.openlocfilehash: 2c89992c4c60ca7f1085050e6fed4922ecd4d8cc
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106132"
---
# <a name="implementing-the-circuit-breaker-pattern"></a>회로 차단기 패턴 구현

앞에서 설명한 것처럼 원격 서비스나 리소스에 연결할 때 발생할 수 있는 복구에 소요되는 시간이 유동적인 오류를 처리해야 합니다.  이러한 종류의 오류를 처리하면 응용 프로그램의 안정성과 탄력성을 높일 수 있습니다.

분산된 환경에서는 느린 네트워크 연결 및 시간 초과 등과 같은 일시적 오류 때문에, 또는 리소스가 느리거나 일시적으로 사용할 수 없어 원격 리소스 및 서비스에 대한 호출이 실패할 수 있습니다. 이러한 오류는 일반적으로 곧 자체 해결되며 재시도 패턴 등과 같은 전략을 사용하여 이를 처리하는 강력한 클라우드 응용 프로그램을 준비해야 합니다.

그러나 해결에 더 오랜 시간이 필요한 예기치 않은 이벤트로 인한 오류 상황도 있을 수 있습니다. 이러한 오류의 심각도는 부분적 연결 손실에서부터 전체 서비스 오류에까지 이를 수 있습니다. 이러한 상황에서 응용 프로그램이 성공할 가능성이 없는 작업을 계속 다시 시도하는 것은 무의미할 수 있습니다. 이보다는 작업에 실패했음을 받아들이고 그에 따라 오류를 처리하도록 응용 프로그램을 코딩해야 합니다.

회로 차단기 패턴은 재시도 패턴과 목적이 다릅니다. 재시도 패턴을 사용하면 응용 프로그램이 결과적으로 작업이 성공한다고 예상하고 작업을 다시 시도합니다. 회로 차단기 패턴은 응용 프로그램이 실패할 가능성 있는 작업을 수행하지 않게 합니다. 응용 프로그램은 회로 차단기를 통해 작업 호출에 재시도 패턴을 사용하여 이 두 패턴을 결합할 수 있습니다. 그러나 재시도 논리는 회로 차단기가 반환하는 모든 예외에 민감해야 하며, 회로 차단기가 일시적 오류가 아니라고 표시한다면 재시도를 중단해야 합니다.

## <a name="implementing-a-circuit-breaker-pattern-with-polly"></a>Polly를 통한 회로 차단기 패턴 구현

재시도를 구현할 때 회로 차단기에 권장되는 방식은 Polly처럼 입증된 .NET 라이브러리를 사용하는 것입니다.

eShopOnContainers 응용 프로그램은 HTTP 재시도를 구현할 때 Polly 회로 차단기 정책을 사용합니다. 실제로 이 응용 프로그램은 두 정책을 모두 ResilientHttpClient 유틸리티 클래스에 적용합니다. (eShopOnContainers로부터의) HTTP 요청에 대해 ResilientHttpClient 형식의 개체를 사용할 때마다 두 정책을 모두 적용하게 되며 다른 정책을 더 추가할 수도 있습니다.

여기서 HTTP 호출 재시도에 사용되는 코드에 추가되는 유일한 항목은 다음 코드의 마지막에 보이는 것처럼 사용할 정책 목록에 회로 차단기 정책을 추가하는 코드입니다.

```csharp
public ResilientHttpClient CreateResilientHttpClient()
    => new ResilientHttpClient(CreatePolicies(), _logger);

private Policy[] CreatePolicies()
    => new Policy[]
    {
        Policy.Handle<HttpRequestException>()
            .WaitAndRetryAsync(
            // number of retries
            6,
            // exponential backofff
            retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt)),
            // on retry
            (exception, timeSpan, retryCount, context) =>
            {
                var msg = $"Retry {retryCount} implemented with Polly RetryPolicy " +
                    $"of {context.PolicyKey} " +
                    $"at {context.ExecutionKey}, " +
                    $"due to: {exception}.";
                _logger.LogWarning(msg);
                _logger.LogDebug(msg);
            }),
            Policy.Handle<HttpRequestException>()
                .CircuitBreakerAsync(
                    // number of exceptions before breaking circuit
                    5,
                    // time circuit opened before retry
                    TimeSpan.FromMinutes(1),
                    (exception, duration) =>
                    {
                        // on circuit opened
                        _logger.LogTrace("Circuit breaker opened");
                    },
                    () =>
                    {
                        // on circuit closed
                        _logger.LogTrace("Circuit breaker reset");
                    })
    };
}
```

이 코드는 HTTP 래퍼에 정책을 추가합니다. 이 정책은 코드가 exceptionsAllowedBeforeBreaking 매개 변수에서 전달되는 지정된 개수(이 경우 5)의 연속 예외(연이은 예외)를 탐지할 때 열리는 회로 차단기를 정의합니다. 이 회로가 열리면 HTTP 요청이 작동하지 않고 예외가 발생합니다.

또 HTTP 호출을 수행하는 클라이언트 응용 프로그램이나 서비스와는 다른 환경에 배포된 특정 리소스에 문제가 있을 가능성이 있으면 회로 차단기를 사용하여 요청을 대체(fallback) 인프라로 리디렉션해야 합니다. 이런 식으로 클라이언트 응용 프로그램이 아닌 백엔드 마이크로 서비스에만 영향을 미치는 데이터 센터에서 중단이 발생한 경우, 클라이언트 응용 프로그램이 대체(fallback) 서비스로 리디렉션할 수 있습니다. Polly는 이 [장애 조치(failover) 정책](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) 시나리오를 자동화하기 위해 새 정책을 계획하고 있습니다.

물론 이 기능은 모두 위치 투명성을 통해 Azure가 사용자를 위해 자동으로 관리하는 것과는 반대로 .NET 코드 안에서 장애 조치(failover)를 관리하는 경우를 위한 것입니다.

## <a name="using-the-resilienthttpclient-utility-class-from-eshoponcontainers"></a>eShopOnContainers에서 ResilientHttpClient 유틸리티 클래스 사용

.NET HttpClient 클래스 사용 방법과 비슷한 방식으로 ResilientHttpClient 유틸리티 클래스를 사용합니다. 다음 eShopOnContainers MVC 웹 응용 프로그램(OrderController에서 사용하는 OrderingService 에이전트 클래스) 예제에서는 ResilientHttpClient 개체가 생성자의 httpClient 매개 변수를 통해 삽입됩니다. 그런 다음, 이 개체를 사용하여 HTTP 요청을 수행합니다.

```csharp
public class OrderingService : IOrderingService
{
    private IHttpClient _apiClient;
    private readonly string _remoteServiceBaseUrl;
    private readonly IOptionsSnapshot<AppSettings> _settings;
    private readonly IHttpContextAccessor _httpContextAccesor;

    public OrderingService(IOptionsSnapshot<AppSettings> settings,
        IHttpContextAccessor httpContextAccesor,
        IHttpClient httpClient)
    {
        _remoteServiceBaseUrl = $"{settings.Value.OrderingUrl}/api/v1/orders";
        _settings = settings;
        _httpContextAccesor = httpContextAccesor;
        _apiClient = httpClient;
    }

    async public Task<List<Order>> GetMyOrders(ApplicationUser user)
    {
        var context = _httpContextAccesor.HttpContext;
        var token = await context.Authentication.GetTokenAsync("access_token");
        _apiClient.Inst.DefaultRequestHeaders.Authorization = new
            System.Net.Http.Headers.AuthenticationHeaderValue("Bearer", token);
        var ordersUrl = _remoteServiceBaseUrl;
        var dataString = await _apiClient.GetStringAsync(ordersUrl);
        var response = JsonConvert.DeserializeObject<List<Order>>(dataString);
        return response;
    }

    // Other methods ...
    async public Task CreateOrder(Order order)
    {
        var context = _httpContextAccesor.HttpContext;
        var token = await context.Authentication.GetTokenAsync("access_token");
        _apiClient.Inst.DefaultRequestHeaders.Authorization = new
            System.Net.Http.Headers.AuthenticationHeaderValue("Bearer", token);
        _apiClient.Inst.DefaultRequestHeaders.Add("x-requestid",
            order.RequestId.ToString());
        var ordersUrl = $"{_remoteServiceBaseUrl}/new";
        order.CardTypeId = 1;
        order.CardExpirationApiFormat();
        SetFakeIdToProducts(order);
        var response = await _apiClient.PostAsync(ordersUrl, order);
        response.EnsureSuccessStatusCode();
    }
}
```

\_apiClient 멤버 개체가 사용될 때마다 내부적으로 Polly 정책, 즉 재시도 정책, 회로 차단기 정책 및 기타 Polly 정책 컬렉션에서 적용하고자 하는 정책과 함께 래퍼 클래스를 사용합니다.

## <a name="testing-retries-in-eshoponcontainers"></a>eShopOnContainers에서 재시도 테스트

Docker 호스트에서 eShopOnContainers 솔루션을 시작할 때마다 여러 컨테이너를 시작해야 합니다. SQL Server 컨테이너처럼 일부 컨테이너는 시작과 초기화가 더 느립니다. 특히 처음 Docker에 eShopOnContainers 응용 프로그램을 배포할 때 그렇습니다. 이미지와 데이터베이스를 설정해야 하기 때문입니다. 일부 컨테이너가 다른 컨테이너보다 늦게 시작되기 때문에 이전 섹션에서 설명한 대로 도커-작성 수준에서 컨테이너 간의 종속성을 설정했다 하더라도 나머지 서비스에서 최초에 HTTP 예외가 발생할 수 있습니다. 이러한 컨테이너 간 도커-작성 종속성은 프로세스 수준에 국한됩니다. 컨테이너의 진입점 프로세스는 시작될 수 있지만 SQL Server는 쿼리 준비가 되지 않았을 수 있습니다. 그 결과 오류가 연쇄 발생하고 특정 컨테이너를 사용하려 할 때 응용 프로그램에 예외가 발생할 수 있습니다.

또한 응용 프로그램을 클라우드에 배포할 때도 시작 중에 이런 종류의 오류가 발생할 수 있습니다. 이 경우 클러스터의 노드 전체에서 컨테이너 수의 균형을 유지할 때 오케스트레이터가 한 노드나 VM의 컨테이너를 다른 곳으로 옮길 수 있습니다(즉 새 인스턴스 시작).

eShopOnContainers가 이 문제를 해결하는 방법은 앞서 설명한 재시도 패턴을 사용하는 것입니다. 솔루션을 시작할 때 다음과 같은 로그 추적이나 경고가 발생할 수 있는 이유도 바로 여기에 있습니다.

> "**Retry 1 implemented with Polly's RetryPolicy**, due to: System.Net.Http.HttpRequestException: An error occurred while sending the request. ---&gt; System.Net.Http.CurlException: Couldn't connect to server\\n at System.Net.Http.CurlHandler.ThrowIfCURLEError(CURLcode error)\\n at \[...\].

## <a name="testing-the-circuit-breaker-in-eshoponcontainers"></a>eShopOnContainers에서 회로 차단기 테스트

몇 가지 방법으로 회로를 열고 eShopOnContainers에서 테스트할 수 있습니다.

한 옵션은 회로 차단기 정책에서 재시도 허용 횟수를 1로 낮추고 전체 솔루션을 Docker에 다시 배포하는 것입니다. 단일 재시도 상황에서 배포 중에 HTTP 요청이 실패하면 회로 차단기가 열리고 오류가 발생하게 됩니다.

또 다른 옵션은 `Basket` 마이크로 서비스에서 구현된 사용자 지정 미들웨어를 사용하는 것입니다. 이 미들웨어를 사용할 때는 모든 HTTP 요청이 캐시되고 상태 코드 500을 반환합니다. 다음과 같이 실패 URI에 대한 GET 요청을 수행하여 마들웨어를 사용할 수 있습니다. 

-   GET /failing

이 요청은 미들웨어의 현재 상태를 반환합니다. 미들웨어를 사용할 경우 이 요청은 상태 코드 500을 반환합니다. 미들웨어를 사용하지 않으면 응답이 없습니다.

-   GET /failing?enable

이 요청은 미들웨어를 사용합니다.

-   GET /failing?disable

이 요청은 미들웨어를 사용하지 않습니다.

예를 들어, 응용 프로그램이 실행되면 아무 브라우저에서나 다음 URI를 통해 요청을 수행하여 미들웨어를 사용합니다. 순서 지정 마이크로 서비스는 포트 5103을 사용합니다.

http://localhost:5103/failing?enable

그런 다음, 그림 10-4처럼 URI [http://localhost:5103/failing](http://localhost:5103/failing)을 사용하여 상태를 확인할 수 있습니다.

![](./media/image4.png)

**그림 10-4**. "실패" ASP.NET 미들웨어의 상태 확인. 이 경우 사용하지 않습니다. 

이 시점에서 Basket 마이크로 서비스는 호출될 때마다 상태 코드 500으로 응답합니다.

미들웨어가 실행되면 MVC 웹 응용 프로그램으로부터 주문을 시도해 볼 수 있습니다. 요청이 실패하므로 회로가 열립니다.

다음 예제에서는 MVC 웹 응용 프로그램의 논리에 주문 수행을 위한 수집 블록이 있습니다. 이 코드가 열림-회로 예외를 수집하면 사용자에게 기다리라고 알리는 친숙한 메시지를 표시합니다.

```csharp
public class CartController : Controller
{
    //…
    public async Task<IActionResult> Index()
    {
        try
        {
            //… Other code
        }
        catch (BrokenCircuitException)
        {
            // Catches error when Basket.api is in circuit-opened mode                 
            HandleBrokenCircuitException();
        }
        return View();
    }       

    private void HandleBrokenCircuitException()
    {
        TempData["BasketInoperativeMsg"] = "Basket Service is inoperative, please try later on. (Business message due to Circuit-Breaker)";
    }
}
```

요약하면 다음과 같습니다. 재시도 정책이 HTTP 요청을 수행하기 위해 몇 차례 시도했고 HTTP 오류를 받았습니다. 회로 차단기 정책에 대해 설정된 최대 시도 횟수(이 경우 5)에 도달하면 응용 프로그램에서 BrokenCircuitException이 발생합니다. 그 결과 그림 10-5처럼 사용자에게 친숙한 메시지가 표시됩니다.

![](./media/image5.png)

**그림 10-5**. UI에 오류를 반환한 회로 차단기

회로를 열 때 다른 논리를 구현할 수 있습니다. 또흔 대체 데이터 센터나 중복 백엔드 시스템이 있는 경우 다른 백엔드 마이크로 서비스에 대해 HTTP 요청을 시도할 수 있습니다.

마지막으로 CircuitBreakerPolicy가 분리(강제로 열고 회로를 연 상태로 유지) 및 재설정(다시 닫음)을 사용하는 방법이 있습니다. 이를 사용하여 정책에서 직접 분리 및 재설정을 호출하는 유틸리티 HTTP 엔드포인트를 구성할 수 있습니다. 이러한 HTTP 엔드포인드는 업그레이드 등의 상황에서 다운스트림을 임시 분리하기 위해 프로덕션에서 적절히 안전하게 사용할 수도 있습니다. 또는 오류가 있다고 의심되는 다운스트림 시스템을 보호하기 위해 회로를 수동으로 이동할 수 있습니다.

## <a name="adding-a-jitter-strategy-to-the-retry-policy"></a>지터 전략을 재시도 정책에 추가

일반 재시도 정책은 동시성, 확장성 및 경합이 높은 경우 시스템에 영향을 미칠 수 있습니다. 부분 작동 중단 상황에서 여러 클라이언트로부터 유사한 재시도가 대규모로 발생하는 문제를 해결하기 위해 재시도 알고리즘/정책에 지터 전략을 추가하면 좋습니다. 이렇게 하면 지수 백오프에 임의성을 추가하여 종단 간 시스템의 전체 성능을 높일 수 있습니다. 이렇게 문제가 발생했을 때 급증 문제를 분산시킵니다. Polly를 사용할 경우 지터 구현 코드는 다음 예제와 비슷합니다. 

```csharp
Random jitterer = new Random();
Policy.Handle<HttpResponseException>() // etc
    .WaitAndRetry(5, // exponential back-off plus some jitter
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))
            + TimeSpan.FromMilliseconds(jitterer.Next(0, 100))
    );
```

## <a name="additional-resources"></a>추가 자료

-   **패턴 다시 시도**
    [*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)

-   **연결 복원력**(Entity Framework Core)[*https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)

-   **Polly**(.NET 탄력성 및 transient-fault-handling 라이브러리) [*https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)

-   **회로 차단기 패턴**
    [*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)

-   **Marc Brooker. 지터: 임의성으로 작업을 더 좋게 만들기** https://brooker.co.za/blog/2015/03/21/backoff.html


>[!div class="step-by-step"]
[이전](implement-http-call-retries-exponential-backoff-polly.md)
[다음](monitor-app-health.md)
