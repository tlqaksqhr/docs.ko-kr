---
title: "HTTP 호출 재시도 지 수 백오프와 관 된 구현"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | HTTP 호출 재시도 지 수 백오프와 관 된 구현"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 1ed48142546403ea710f4c132e038521232c20ed
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-http-call-retries-with-exponential-backoff-with-polly"></a>HTTP 호출 재시도 지 수 백오프와 관 된 구현

오픈 소스와 같은 고급.NET 라이브러리를 활용 하는 지 수 백오프와 재시도 대 한 방법이 권장된 [관](https://github.com/App-vNext/Polly) 라이브러리입니다.

관 복원 력 및 일시적인 오류 처리 기능을 제공 하는.NET 라이브러리입니다. 다시 시도, 회로 차단기, Bulkhead 격리, 제한 시간 및 대체 (fallback) 같은 관 정책을 적용 하 여 이러한 기능을 쉽게 구현할 수 있습니다. .NET을 대상으로 관 4.x과.NET Standard 버전 1.0 (을.NET Core 지원).

관에 다시 시도 정책은 HTTP 재시도 구현할 때 eShopOnContainers에 사용 되는 것이입니다. 표준 HttpClient 기능 또는 관를 사용 하 여 사용 하려면 어떤 재시도 정책 구성에 따라 HttpClient의 복원 력이 버전 중 하나를 삽입할 수 있도록 인터페이스를 구현할 수 있습니다.

다음 예제에서는 eShopOnContainers에 구현 된 인터페이스를 보여 줍니다.

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

표준 구현을 개발 하거나 간단한 방법을 테스트 하는 경우 탄력적 메커니즘으로 사용 하지 않을 경우 사용할 수 있습니다. 다음 코드는 선택적인 경우로 사용 하 여 표준 HttpClient 구현 가능 요청 인증 토큰을 보여줍니다.

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

비슷한 클래스 하지만 관을 사용 하는 데 사용할 복원 력 있는 메커니즘을 구현 하 코딩 하는 흥미로운 구현을-지 수 백오프 하 여 다음 예제에서는 다시 시도 합니다.

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

와 관, 다시 시도 정책은 다시 시도 횟수, 지 수 백오프 구성 및 오류를 기록 하는 등 HTTP 예외가 있을 때 수행할 동작을의 수를 정의 합니다. 이 경우 정책은 IoC 컨테이너에 형식을 등록할 때 지정 된 횟수를 시도 하도록 구성 됩니다. 지 수 백오프 구성으로 인해 코드에서 HttpRequest 예외가 검색 될 때마다 다시 시도 하기는 Http 요청 정책 구성 방법에 따라 기하급수적으로 증가 하는 시간 만큼 대기한 후 합니다.

중요 한 메서드가 개입니다 HttpInvoker,이 유틸리티 클래스 전체에서 HTTP 요청 이유. 메서드를 HTTP 요청을 내부적으로 실행 \_policyWrapper.ExecuteAsync는 재시도 정책을 고려 합니다.

EShopOnContainers에서 정책을 지정할 있습니다 관 IoC 컨테이너에서 다음 코드 에서처럼에 형식을 등록할 때는 [MVC 웹 응용 프로그램의 startup.cs에서](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Web/WebMVC/Startup.cs) 클래스입니다.

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

서비스에서 TCP 연결을 효율적으로 사용 되도록 IHttpClient 개체 임시로 대신 단일 항목으로 인스턴스화됩니다 참고 및 [소켓 문제가](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) 발생 하지 것입니다.

하지만 복원 력에 대 한 중요 한 점은 CreateResilientHttpClient 메서드에서 ResilientHttpClientFactory 내 관 WaitAndRetryAsync 정책 적용 되는 다음 코드에 나와 있는 것 처럼이.

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
[이전] [다음] (구현-회로-분리기-pattern.md) (implement-custom-http-call-retries-exponential-backoff.md)
