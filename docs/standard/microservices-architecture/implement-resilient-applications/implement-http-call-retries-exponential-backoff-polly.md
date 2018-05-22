---
title: Polly와 함께 지수 백오프를 사용하여 HTTP 호출 다시 시도 구현
description: 컨테이너화된 .NET 응용 프로그램용 .NET 마이크로 서비스 아키텍처 | Polly와 함께 지수 백오프를 사용하여 HTTP 호출 다시 시도 구현
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 66ac57fc824e01f96d6584ab86bb95ba1b0174a3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="implementing-http-call-retries-with-exponential-backoff-with-polly"></a>Polly와 함께 지수 백오프를 사용하여 HTTP 호출 다시 시도 구현

지수 백오프를 사용하는 재시도는 오픈 소스 [Polly](https://github.com/App-vNext/Polly) 라이브러리와 같은 고급 .NET 라이브러리를 활용하는 것이 좋습니다.

Polly는 복원력 및 일시적인 오류 처리 기능을 제공하는 .NET 라이브러리입니다. 재시도, 회로 차단기, Bulkhead 격리, 시간 제한 및 대체와 같은 Polly 정책을 적용하여 해당 기능을 쉽게 구현할 수 있습니다. Polly는 .NET 4.x 및 .NET Standard 버전 1.0을 대상으로 지정합니다(.NET Core를 지원함).

Polly의 재시도 정책은 HTTP 재시도를 구현할 때 eShopOnContainers에서 사용되는 방법입니다. 사용하려는 재시도 정책 구성에 따라 Polly를 사용하여 표준 HttpClient 기능 또는 탄력성 있는 버전의 HttpClient 중 하나를 삽입할 수 있도록 인터페이스를 구현할 수 있습니다.

다음 예제에서는 eShopOnContainers에서 구현된 인터페이스를 보여줍니다.

```csharp
public interface IHttpClient
{
    Task<string> GetStringAsync(string uri, string authorizationToken = null,
        string authorizationMethod = "Bearer");
        Task<HttpResponseMessage> PostAsync<T>(string uri, T item,
        string authorizationToken = null, string requestId = null,
        string authorizationMethod = "Bearer");

    Task<HttpResponseMessage> DeleteAsync(string uri,
        string authorizationToken = null, string requestId = null,
        string authorizationMethod = "Bearer");

    // Other methods ...
}
```

간단한 방법을 개발하거나 테스트하는 경우 탄력적 메커니즘을 사용하지 않는 경우 표준 구현을 사용할 수 있습니다. 다음 코드에서는 표준 HttpClient 구현이 선택적으로 요청 인증 토큰을 사용하여 요청할 수 있음을 보여줍니다.

```csharp
public class StandardHttpClient : IHttpClient
{
    private HttpClient _client;
    private ILogger<StandardHttpClient> _logger;

    public StandardHttpClient(ILogger<StandardHttpClient> logger)
    {
        _client = new HttpClient();
        _logger = logger;
    }

    public async Task<string> GetStringAsync(string uri,
        string authorizationToken = null,
        string authorizationMethod = "Bearer")
    {
        var requestMessage = new HttpRequestMessage(HttpMethod.Get, uri);
        if (authorizationToken != null)
        {
            requestMessage.Headers.Authorization =
                new AuthenticationHeaderValue(authorizationMethod, authorizationToken);
        }
        var response = await _client.SendAsync(requestMessage);
        return await response.Content.ReadAsStringAsync();
    }

    public async Task<HttpResponseMessage> PostAsync<T>(string uri, T item,
        string authorizationToken = null, string requestId = null,
        string authorizationMethod = "Bearer")
    {
        // Rest of the code and other Http methods ...
```

흥미로운 구현은 다른 비슷한 클래스를 코딩하는 것이지만 다음 예제에서는 복원력 있는 메커니즘을 구현하려면 Polly를 사용하면 지수 백오프를 사용하여 재시도합니다.

```csharp
public class ResilientHttpClient : IHttpClient
{
    private HttpClient _client;
    private PolicyWrap _policyWrapper;
    private ILogger<ResilientHttpClient> _logger;

    public ResilientHttpClient(Policy[] policies,
        ILogger<ResilientHttpClient> logger)
    {
        _client = new HttpClient();
        _logger = logger;
        // Add Policies to be applied
        _policyWrapper = Policy.WrapAsync(policies);
    }

    private Task<T> HttpInvoker<T>(Func<Task<T>> action)
    {
        // Executes the action applying all
        // the policies defined in the wrapper
        return _policyWrapper.ExecuteAsync(() => action());
    }

    public Task<string> GetStringAsync(string uri,
        string authorizationToken = null,
        string authorizationMethod = "Bearer")
    {
        return HttpInvoker(async () =>
        {
            var requestMessage = new HttpRequestMessage(HttpMethod.Get, uri);
            // The Token's related code eliminated for clarity in code snippet
            var response = await _client.SendAsync(requestMessage);
            return await response.Content.ReadAsStringAsync();
        });
    }
    // Other Http methods executed through HttpInvoker so it applies Polly policies
    // ...
}
```

Polly를 사용하여 HTTP 예외(예: 오류 기록)가 있을 때 수행할 재시도 횟수, 지수 백오프 구성 및 동작으로 재시도 정책을 정의합니다. 이 경우에 IoC 컨테이너에 형식을 등록할 때 지정된 횟수만큼 시도하도록 정책을 구성합니다. 지수 백오프 구성 때문에 코드가 HttpRequest 예외를 감지할 때마다 정책 구성 방법에 따라 기하급수적으로 증가하는 시간만큼 대기한 후에 Http 요청을 재시도합니다.

중요한 메서드는 HttpInvoker이며 이 유틸리티 클래스 전체에서 HTTP를 요청하는 항목입니다. 메서드는 \_policyWrapper.ExecuteAsync를 사용하여 HTTP 요청을 내부적으로 실행합니다. 여기서는 재시도 정책을 고려합니다.

[startup.cs 클래스의 MVC 웹 응용 프로그램](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Web/WebMVC/Startup.cs)에 있는 다음 코드처럼 IoC 컨테이너에서 형식을 등록할 때 eShopOnContainers에서 Polly 정책을 지정합니다.

```csharp
// Startup.cs class
if (Configuration.GetValue<string>("UseResilientHttp") == bool.TrueString)
{
    services.AddTransient<IResilientHttpClientFactory,
        ResilientHttpClientFactory>();
    services.AddSingleton<IHttpClient,
        ResilientHttpClient>(sp =>
            sp.GetService<IResilientHttpClientFactory>().
            CreateResilientHttpClient());
}
else
{
    services.AddSingleton<IHttpClient, StandardHttpClient>();
}
```

서비스에서 TCP 연결을 효율적으로 사용하고 [소켓 관련 문제](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/)가 발생하지 않도록 임시가 아닌 singleton으로 IHttpClient 개체를 인스턴스화합니다.

하지만 복원력에 대한 중요한 점은 다음 코드에 표시된 대로 CreateResilientHttpClient 메서드의 ResilientHttpClientFactory 내에서 Polly WaitAndRetryAsync 정책을 적용하는 것입니다.

```csharp
public ResilientHttpClient CreateResilientHttpClient()
    => new ResilientHttpClient(CreatePolicies(), _logger);

// Other code
private Policy[] CreatePolicies()
    => new Policy[]
    {
        Policy.Handle<HttpRequestException>()
            .WaitAndRetryAsync(
        // number of retries
        6,
        // exponential backoff
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt)),
        // on retry
        (exception, timeSpan, retryCount, context) =>
        {
            var msg = $"Retry {retryCount} implemented with Pollys RetryPolicy " +
            $"of {context.PolicyKey} " +
            $"at {context.ExecutionKey}, " +
            $"due to: {exception}.";
            _logger.LogWarning(msg);
            _logger.LogDebug(msg);
        }),
    }
```


>[!div class="step-by-step"]
[이전] (implement-custom-http-call-retries-exponential-backoff.md) [다음] (implement-circuit-breaker-pattern.md)
