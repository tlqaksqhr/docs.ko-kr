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
ms.locfileid: "33576983"
---
# <a name="implementing-http-call-retries-with-exponential-backoff-with-polly"></a><span data-ttu-id="2a238-103">Polly와 함께 지수 백오프를 사용하여 HTTP 호출 다시 시도 구현</span><span class="sxs-lookup"><span data-stu-id="2a238-103">Implementing HTTP call retries with exponential backoff with Polly</span></span>

<span data-ttu-id="2a238-104">지수 백오프를 사용하는 재시도는 오픈 소스 [Polly](https://github.com/App-vNext/Polly) 라이브러리와 같은 고급 .NET 라이브러리를 활용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2a238-104">The recommended approach for retries with exponential backoff is to take advantage of more advanced .NET libraries like the open source [Polly](https://github.com/App-vNext/Polly) library.</span></span>

<span data-ttu-id="2a238-105">Polly는 복원력 및 일시적인 오류 처리 기능을 제공하는 .NET 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="2a238-105">Polly is a .NET library that provides resilience and transient-fault handling capabilities.</span></span> <span data-ttu-id="2a238-106">재시도, 회로 차단기, Bulkhead 격리, 시간 제한 및 대체와 같은 Polly 정책을 적용하여 해당 기능을 쉽게 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a238-106">You can implement those capabilities easily by applying Polly policies such as Retry, Circuit Breaker, Bulkhead Isolation, Timeout, and Fallback.</span></span> <span data-ttu-id="2a238-107">Polly는 .NET 4.x 및 .NET Standard 버전 1.0을 대상으로 지정합니다(.NET Core를 지원함).</span><span class="sxs-lookup"><span data-stu-id="2a238-107">Polly targets .NET 4.x and the .NET Standard version 1.0 (which supports .NET Core).</span></span>

<span data-ttu-id="2a238-108">Polly의 재시도 정책은 HTTP 재시도를 구현할 때 eShopOnContainers에서 사용되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="2a238-108">The Retry policy in Polly is the approach used in eShopOnContainers when implementing HTTP retries.</span></span> <span data-ttu-id="2a238-109">사용하려는 재시도 정책 구성에 따라 Polly를 사용하여 표준 HttpClient 기능 또는 탄력성 있는 버전의 HttpClient 중 하나를 삽입할 수 있도록 인터페이스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a238-109">You can implement an interface so you can inject either standard HttpClient functionality or a resilient version of HttpClient using Polly, depending on what retry policy configuration you want to use.</span></span>

<span data-ttu-id="2a238-110">다음 예제에서는 eShopOnContainers에서 구현된 인터페이스를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="2a238-110">The following example shows the interface implemented in eShopOnContainers.</span></span>

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

<span data-ttu-id="2a238-111">간단한 방법을 개발하거나 테스트하는 경우 탄력적 메커니즘을 사용하지 않는 경우 표준 구현을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a238-111">You can use the standard implementation if you do not want to use a resilient mechanism, as when you are developing or testing simpler approaches.</span></span> <span data-ttu-id="2a238-112">다음 코드에서는 표준 HttpClient 구현이 선택적으로 요청 인증 토큰을 사용하여 요청할 수 있음을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="2a238-112">The following code shows the standard HttpClient implementation allowing requests with authentication tokens as an optional case.</span></span>

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

<span data-ttu-id="2a238-113">흥미로운 구현은 다른 비슷한 클래스를 코딩하는 것이지만 다음 예제에서는 복원력 있는 메커니즘을 구현하려면 Polly를 사용하면 지수 백오프를 사용하여 재시도합니다.</span><span class="sxs-lookup"><span data-stu-id="2a238-113">The interesting implementation is to code another, similar class, but using Polly to implement the resilient mechanisms you want to use—in the following example, retries with exponential backoff.</span></span>

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

<span data-ttu-id="2a238-114">Polly를 사용하여 HTTP 예외(예: 오류 기록)가 있을 때 수행할 재시도 횟수, 지수 백오프 구성 및 동작으로 재시도 정책을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2a238-114">With Polly, you define a Retry policy with the number of retries, the exponential backoff configuration, and the actions to take when there is an HTTP exception, such as logging the error.</span></span> <span data-ttu-id="2a238-115">이 경우에 IoC 컨테이너에 형식을 등록할 때 지정된 횟수만큼 시도하도록 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2a238-115">In this case, the policy is configured so it will try the number of times specified when registering the types in the IoC container.</span></span> <span data-ttu-id="2a238-116">지수 백오프 구성 때문에 코드가 HttpRequest 예외를 감지할 때마다 정책 구성 방법에 따라 기하급수적으로 증가하는 시간만큼 대기한 후에 Http 요청을 재시도합니다.</span><span class="sxs-lookup"><span data-stu-id="2a238-116">Because of the exponential backoff configuration, whenever the code detects an HttpRequest exception, it retries the Http request after waiting an amount of time that increases exponentially depending on how the policy was configured.</span></span>

<span data-ttu-id="2a238-117">중요한 메서드는 HttpInvoker이며 이 유틸리티 클래스 전체에서 HTTP를 요청하는 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="2a238-117">The important method is HttpInvoker, which is what makes HTTP requests throughout this utility class.</span></span> <span data-ttu-id="2a238-118">메서드는 \_policyWrapper.ExecuteAsync를 사용하여 HTTP 요청을 내부적으로 실행합니다. 여기서는 재시도 정책을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="2a238-118">That method internally executes the HTTP request with \_policyWrapper.ExecuteAsync, which takes into account the retry policy.</span></span>

<span data-ttu-id="2a238-119">[startup.cs 클래스의 MVC 웹 응용 프로그램](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Web/WebMVC/Startup.cs)에 있는 다음 코드처럼 IoC 컨테이너에서 형식을 등록할 때 eShopOnContainers에서 Polly 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2a238-119">In eShopOnContainers you specify Polly policies when registering the types at the IoC container, as in the following code from the [MVC web app at the startup.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Web/WebMVC/Startup.cs) class.</span></span>

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

<span data-ttu-id="2a238-120">서비스에서 TCP 연결을 효율적으로 사용하고 [소켓 관련 문제](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/)가 발생하지 않도록 임시가 아닌 singleton으로 IHttpClient 개체를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="2a238-120">Note that the IHttpClient objects are instantiated as singleton instead of as transient so that TCP connections are used efficiently by the service and [an issue with sockets](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) will not occur.</span></span>

<span data-ttu-id="2a238-121">하지만 복원력에 대한 중요한 점은 다음 코드에 표시된 대로 CreateResilientHttpClient 메서드의 ResilientHttpClientFactory 내에서 Polly WaitAndRetryAsync 정책을 적용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2a238-121">But the important point about resiliency is that you apply the Polly WaitAndRetryAsync policy within ResilientHttpClientFactory in the CreateResilientHttpClient method, as shown in the following code:</span></span>

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
<span data-ttu-id="2a238-122">[이전] (implement-custom-http-call-retries-exponential-backoff.md) [다음] (implement-circuit-breaker-pattern.md)</span><span class="sxs-lookup"><span data-stu-id="2a238-122">[Previous] (implement-custom-http-call-retries-exponential-backoff.md) [Next] (implement-circuit-breaker-pattern.md)</span></span>
