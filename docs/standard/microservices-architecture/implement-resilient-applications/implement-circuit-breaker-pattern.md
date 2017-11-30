---
title: "회로 차단기 패턴 구현"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 회로 차단기 패턴 구현"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 2a629e25a7565aaba156f68cf06d9a24b6c2b8b0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-the-circuit-breaker-pattern"></a><span data-ttu-id="e5161-104">회로 차단기 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="e5161-104">Implementing the Circuit Breaker pattern</span></span>

<span data-ttu-id="e5161-105">앞에서 설명한 것 처럼 다양 한 크기의 원격 서비스 또는 리소스에 연결 하려고 할 때 발생할 수 있습니다를 복구 하는 데 시간이 소요 될 수 있는 오류를 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-105">As noted earlier, you should handle faults that might take a variable amount of time to recover from, as might happen when you try to connect to a remote service or resource.</span></span> <span data-ttu-id="e5161-106">이러한 종류의 오류 처리 안정성과 응용 프로그램의 복원 력을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-106">Handling this type of fault can improve the stability and resiliency of an application.</span></span>

<span data-ttu-id="e5161-107">분산된 환경에서 원격 리소스 및 서비스에 대 한 호출 수 느린 네트워크 연결, 시간 초과 등의 일시적인 오류 실패할 또는 느리다고 일시적으로 사용할 수 없는 리소스 되는 경우.</span><span class="sxs-lookup"><span data-stu-id="e5161-107">In a distributed environment, calls to remote resources and services can fail due to transient faults, such as slow network connections and timeouts, or if resources are being slow or are temporarily unavailable.</span></span> <span data-ttu-id="e5161-108">이러한 오류 일반적으로 자체는 얼마 올바르며 재시도 패턴과 같은 전략을 사용 하 여이 처리 하는 강력한 클라우드 응용 프로그램을 준비 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-108">These faults typically correct themselves after a short time, and a robust cloud application should be prepared to handle them by using a strategy like the Retry pattern.</span></span>

<span data-ttu-id="e5161-109">그러나 수 있을 오류 문제를 해결 하려면 훨씬 더 오래 걸릴 수 있는 예기치 않은 이벤트로 인해 모두 경우.</span><span class="sxs-lookup"><span data-stu-id="e5161-109">However, there can also be situations where faults are due to unanticipated events that might take much longer to fix.</span></span> <span data-ttu-id="e5161-110">이러한 오류는 서비스의 전체 오류에 연결 부분 손실이에서 심각도에 이르기까지 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-110">These faults can range in severity from a partial loss of connectivity to the complete failure of a service.</span></span> <span data-ttu-id="e5161-111">이러한 상황에서 응용 프로그램을 지속적으로 성공할 수 있는 작업을 다시 시도 무의미 한 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-111">In these situations, it might be pointless for an application to continually retry an operation that is unlikely to succeed.</span></span> <span data-ttu-id="e5161-112">대신, 응용 프로그램 작업이 실패 했습니다을 받아들이고 오류를 적절 하 게 처리할 코딩 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-112">Instead, the application should be coded to accept that the operation has failed and handle the failure accordingly.</span></span>

<span data-ttu-id="e5161-113">회로 차단기 패턴에는 다른 목적 재시도 패턴.</span><span class="sxs-lookup"><span data-stu-id="e5161-113">The Circuit Breaker pattern has a different purpose than the Retry pattern.</span></span> <span data-ttu-id="e5161-114">재시도 패턴에는 작업은 결국 성공 하는 expectation에 작업을 다시 시도 응용을 프로그램 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-114">The Retry pattern enables an application to retry an operation in the expectation that the operation will eventually succeed.</span></span> <span data-ttu-id="e5161-115">회로 차단기 패턴 실패할 가능성이 있는 작업을 수행 하 여 응용 프로그램을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-115">The Circuit Breaker pattern prevents an application from performing an operation that is likely to fail.</span></span> <span data-ttu-id="e5161-116">응용 프로그램 재시도 패턴을 사용 하 여 회로 차단기를 통해 작업을 호출 하 여 이러한 두 가지 패턴을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-116">An application can combine these two patterns by using the Retry pattern to invoke an operation through a circuit breaker.</span></span> <span data-ttu-id="e5161-117">그러나 재시도 논리 회로 차단기에서 반환 되는 모든 예외에 민감한 며 회로 차단기 오류가 일시적이 지를 나타내는 경우 재시도 중단 해야.</span><span class="sxs-lookup"><span data-stu-id="e5161-117">However, the retry logic should be sensitive to any exceptions returned by the circuit breaker, and it should abandon retry attempts if the circuit breaker indicates that a fault is not transient.</span></span>

## <a name="implementing-a-circuit-breaker-pattern-with-polly"></a><span data-ttu-id="e5161-118">관 된 회로 차단기 패턴을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-118">Implementing a Circuit Breaker pattern with Polly</span></span>

<span data-ttu-id="e5161-119">As 재시도 구현할 때 회로 차단기에 대 한 권장된 접근 방식을 관와 같은 입증 된.NET 라이브러리를 활용 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-119">As when implementing retries, the recommended approach for circuit breakers is to take advantage of proven .NET libraries like Polly.</span></span>

<span data-ttu-id="e5161-120">HTTP 재시도 구현할 때 회로 차단기 관 정책을 사용 하는 eShopOnContainers 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-120">The eShopOnContainers application uses the Polly Circuit Breaker policy when implementing HTTP retries.</span></span> <span data-ttu-id="e5161-121">실제로 응용 프로그램 두 정책을 모두 ResilientHttpClient 유틸리티 클래스에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-121">In fact, the application applies both policies to the ResilientHttpClient utility class.</span></span> <span data-ttu-id="e5161-122">(EShopOnContainers)에서 HTTP 요청에 대 한 ResilientHttpClient 형식의 개체를 사용할 경우 이러한 두 정책의 적용 하지만 너무 추가 정책을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-122">Whenever you use an object of type ResilientHttpClient for HTTP requests (from eShopOnContainers), you will be applying both those policies, but you could add additional policies, too.</span></span>

<span data-ttu-id="e5161-123">유일한 추가 여기 HTTP 호출 재시도에 사용 되는 코드를 있는 정책을 추가 하면 회로 차단기를 사용 하려면 정책 목록에 다음 코드의 끝에 표시 된 것 처럼 코드는.</span><span class="sxs-lookup"><span data-stu-id="e5161-123">The only addition here to the code used for HTTP call retries is the code where you add the Circuit Breaker policy to the list of policies to use, as shown at the end of the following code:</span></span>

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

<span data-ttu-id="e5161-124">HTTP 래퍼에 정책을 추가 하는 코드.</span><span class="sxs-lookup"><span data-stu-id="e5161-124">The code adds a policy to the HTTP wrapper.</span></span> <span data-ttu-id="e5161-125">ExceptionsAllowedBeforeBreaking 매개 변수 (이 경우 5)에서 전달 정책으로를 코드에서 지정된 된 수의 연속 된 예외 (행에서 예외)를 검색 하면 열리는 회로 차단기를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-125">That policy defines a circuit breaker that opens when the code detects the specified number of consecutive exceptions (exceptions in a row), as passed in the exceptionsAllowedBeforeBreaking parameter (5 in this case).</span></span> <span data-ttu-id="e5161-126">회로 연 HTTP 요청 작동 하지 않습니다 되지만 예외가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-126">When the circuit is open, HTTP requests do not work, but an exception is raised.</span></span>

<span data-ttu-id="e5161-127">또한 HTTP 호출을 수행 하는 서비스나 클라이언트 응용 프로그램 보다 다른 환경에 배포 된 특정 리소스에 문제가 나타날 수 있습니다 하는 경우 대체 (fallback) 인프라에 요청을 리디렉션하려면 회로 차단기를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-127">Circuit breakers should also be used to redirect requests to a fallback infrastructure if you might have issues in a particular resource that is deployed in a different environment than the client application or service that is performing the HTTP call.</span></span> <span data-ttu-id="e5161-128">이런 방식으로 여 백 엔드 microservices 있지만 하지 클라이언트 응용 프로그램에 영향을 주는 데이터 센터에서 중단 되는 클라이언트 응용 프로그램 대체 (fallback) 서비스에 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-128">That way, if there is an outage in the datacenter that impacts only your backend microservices but not your client applications, the client applications can redirect to the fallback services.</span></span> <span data-ttu-id="e5161-129">이 과정을 자동화 하는 새 정책을 계획 관 [장애 조치 정책](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-129">Polly is planning a new policy to automate this [failover policy](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) scenario.</span></span>

<span data-ttu-id="e5161-130">물론, 관리 하 고 있는 관리 되는 자동으로 사용자에 대 한 Azure에서 위치 투명성 것 대신,.NET 코드 내에서 장애 조치의 경우에 대 한 이러한 모든 기능을 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-130">Of course, all those features are for cases where you are managing the failover from within the .NET code, as opposed to having it managed automatically for you by Azure, with location transparency.</span></span>

## <a name="using-the-resilienthttpclient-utility-class-from-eshoponcontainers"></a><span data-ttu-id="e5161-131">EShopOnContainers에서 ResilientHttpClient 유틸리티 클래스를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="e5161-131">Using the ResilientHttpClient utility class from eShopOnContainers</span></span>

<span data-ttu-id="e5161-132">.NET HttpClient 클래스를 사용 하는 방법에 비슷한 방식으로 ResilientHttpClient 유틸리티 클래스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-132">You use the ResilientHttpClient utility class in a way similar to how you use the .NET HttpClient class.</span></span> <span data-ttu-id="e5161-133">EShopOnContainers MVC 웹 응용 프로그램 (OrderController에 사용 되는 OrderingService 에이전트 클래스)에서 다음 예에서 ResilientHttpClient 개체 생성자의 httpClient 매개 변수를 통해 삽입 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-133">In the following example from the eShopOnContainers MVC web application (the OrderingService agent class used by OrderController), the ResilientHttpClient object is injected through the httpClient parameter of the constructor.</span></span> <span data-ttu-id="e5161-134">다음 HTTP 요청을 수행 하는 개체 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-134">Then the object is used to perform HTTP requests.</span></span>

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

<span data-ttu-id="e5161-135">때마다는 \_apiClient 멤버 개체는 사용, 내부적으로 관 policiesؙ 된 래퍼 클래스를 사용-다시 시도 정책, 회로 차단기 정책 및 관 정책 컬렉션에서 적용 해야 할 수는 다른 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-135">Whenever the \_apiClient member object is used, it internally uses the wrapper class with Polly policiesؙ—the Retry policy, the Circuit Breaker policy, and any other policy that you might want to apply from the Polly policies collection.</span></span>

## <a name="testing-retries-in-eshoponcontainers"></a><span data-ttu-id="e5161-136">재시도 eShopOnContainers에서 테스트</span><span class="sxs-lookup"><span data-stu-id="e5161-136">Testing retries in eShopOnContainers</span></span>

<span data-ttu-id="e5161-137">Docker 호스트에 eShopOnContainers 솔루션을 시작할 때마다를 여러 컨테이너를 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-137">Whenever you start the eShopOnContainers solution in a Docker host, it needs to start multiple containers.</span></span> <span data-ttu-id="e5161-138">컨테이너의 일부는 시작 하는 SQL Server 컨테이너와 같은 초기화 더 느려집니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-138">Some of the containers are slower to start and initialize, like the SQL Server container.</span></span> <span data-ttu-id="e5161-139">특히 처음 Docker eShopOnContainers 응용 프로그램 배포 때문에 사실이 이미지와 데이터베이스를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-139">This is especially true the first time you deploy the eShopOnContainers application into Docker, because it needs to set up the images and the database.</span></span> <span data-ttu-id="e5161-140">일부 컨테이너에 컨테이너 간의 종속성을 설정 하는 경우에 처음 HTTP 예외를 throw 하는 서비스의 나머지 부분 하면 다른 사용자 보다 느리게 시작은 docker-구성 수준에서 이전 섹션에서 설명한 대로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-140">The fact that some containers start slower than others can cause the rest of the services to initially throw HTTP exceptions, even if you set dependencies between containers at the docker-compose level, as explained in previous sections.</span></span> <span data-ttu-id="e5161-141">이러한 docker-작성 컨테이너 간의 종속성 프로세스 수준에 국한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-141">Those docker-compose dependencies between containers are just at the process level.</span></span> <span data-ttu-id="e5161-142">컨테이너의 진입점 프로세스를 시작할 수 있습니다 하지만 SQL Server 쿼리를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-142">The container’s entry point process might be started, but SQL Server might not be ready for queries.</span></span> <span data-ttu-id="e5161-143">오류를 모두 표시 될 수 있습니다 및 응용 프로그램이 해당 특정 컨테이너를 사용 하려고 할 때 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-143">The result can be a cascade of errors, and the application can get an exception when trying to consume that particular container.</span></span>

<span data-ttu-id="e5161-144">또한 응용 프로그램을 클라우드로 배포할 때 시작에서 이런이 유형의 오류를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-144">You might also see this type of error on startup when the application is deploying to the cloud.</span></span> <span data-ttu-id="e5161-145">이 경우 orchestrators 있습니다 수 컨테이너 노드 또는 VM 간에 이동 (즉, 새 인스턴스 시작) 클러스터의 노드 전체 컨테이너의 수를 균형 있게 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-145">In that case, orchestrators might be moving containers from one node or VM to another (that is, starting new instances) when balancing the number of containers across the cluster’s nodes.</span></span>

<span data-ttu-id="e5161-146">앞서 설명 된 재시도 패턴을 사용 하 여 방식은 eShopOnContainers이이 문제가 해결 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-146">The way eShopOnContainers solves this issue is by using the Retry pattern we illustrated earlier.</span></span> <span data-ttu-id="e5161-147">이기도 이유, 솔루션을 시작할 때 표시 될 수 있습니다 로그 추적 또는 다음과 같은 경고가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-147">It is also why, when starting the solution, you might get log traces or warnings like the following:</span></span>

> <span data-ttu-id="e5161-148">"**관 RetryPolicy를 사용 하 여 구현 하는 다시 시도 하세요 1**를로 인해: System.Net.Http.HttpRequestException: 요청을 보내는 동안 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-148">"**Retry 1 implemented with Polly's RetryPolicy**, due to: System.Net.Http.HttpRequestException: An error occurred while sending the request.</span></span><span data-ttu-id="e5161-149"> ---&gt;System.Net.Http.CurlException: 서버에 연결할 수 없습니다.\\System.Net.Http.CurlHandler.ThrowIfCURLEError (CURLcode 오류)에 n\\에 n \[... \].</span><span class="sxs-lookup"><span data-stu-id="e5161-149"> ---&gt; System.Net.Http.CurlException: Couldn't connect to server\\n at System.Net.Http.CurlHandler.ThrowIfCURLEError(CURLcode error)\\n at \[...\].</span></span>

## <a name="testing-the-circuit-breaker-in-eshoponcontainers"></a><span data-ttu-id="e5161-150">회로 차단기 eShopOnContainers에서 테스트</span><span class="sxs-lookup"><span data-stu-id="e5161-150">Testing the circuit breaker in eShopOnContainers</span></span>

<span data-ttu-id="e5161-151">회로 열고 사용 하 여 eShopOnContainers 테스트 수는 몇 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-151">There are a few ways you can open the circuit and test it with eShopOnContainers.</span></span>

<span data-ttu-id="e5161-152">한 가지 회로 차단기 정책에서 1로 다시 시도가 허용 되는 수를 줄이고 Docker에 전체 솔루션을 다시 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-152">One option is to lower the allowed number of retries to 1 in the circuit breaker policy and redeploy the whole solution into Docker.</span></span> <span data-ttu-id="e5161-153">단일 다시 배포 하는 동안 HTTP 요청 실패 하는 좋은 가능성이, 회로 차단기 열리고 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-153">With a single retry, there is a good chance that an HTTP request will fail during deployment, the circuit breaker will open, and you get an error.</span></span>

<span data-ttu-id="e5161-154">다른 옵션은 정렬 마이크로 서비스에서 구현 되는 사용자 지정 미들웨어를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-154">Another option is to use custom middleware that is implemented in the ordering microservice.</span></span> <span data-ttu-id="e5161-155">이 미들웨어를 사용 하는 모든 HTTP 요청을 catch 하 고 상태 코드 500을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-155">When this middleware is enabled, it catches all HTTP requests and returns status code 500.</span></span> <span data-ttu-id="e5161-156">실패 한에 GET 요청을 하 여 미들웨어를 사용할 수 있습니다 다음과 같은 URI:</span><span class="sxs-lookup"><span data-stu-id="e5161-156">You can enable the middleware by making a GET request to the failing URI, like the following:</span></span>

-   <span data-ttu-id="e5161-157">가져오기/결함</span><span class="sxs-lookup"><span data-stu-id="e5161-157">GET /failing</span></span>

<span data-ttu-id="e5161-158">이 요청 미들웨어의 현재 상태를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-158">This request returns the current state of the middleware.</span></span> <span data-ttu-id="e5161-159">미들웨어를 사용 하는 요청 상태 코드 500을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-159">If the middleware is enabled, the request return status code 500.</span></span> <span data-ttu-id="e5161-160">미들웨어 비활성화 된 경우에 다음과 같은 응답이.</span><span class="sxs-lookup"><span data-stu-id="e5161-160">If the middleware is disabled, there is no response.</span></span>

-   <span data-ttu-id="e5161-161">실패 한 /?를 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="e5161-161">GET /failing?enable</span></span>

<span data-ttu-id="e5161-162">이 요청 미들웨어 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-162">This request enables the middleware.</span></span>

-   <span data-ttu-id="e5161-163">실패 한 /? 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="e5161-163">GET /failing?disable</span></span>

<span data-ttu-id="e5161-164">이 요청 미들웨어를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-164">This request disables the middleware.</span></span>

<span data-ttu-id="e5161-165">예를 들어, 응용 프로그램이 실행 되 면, 다음 URI를 사용 하 여 모든 브라우저에서 요청 하 여 미들웨어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-165">For instance, once the application is running, you can enable the middleware by making a request using the following URI in any browser.</span></span> <span data-ttu-id="e5161-166">정렬 마이크로 서비스 5102 포트를 사용 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-166">Note that the ordering microservice uses port 5102.</span></span>

<span data-ttu-id="e5161-167">http://localhost:5102 실패 /?를 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="e5161-167">http://localhost:5102/failing?enable</span></span>

<span data-ttu-id="e5161-168">다음 URI를 사용 하 여 상태를 확인할 수 있습니다 [http://localhost:5102 / 결함](http://localhost:5100/failing)그림 10-4에 표시 된 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-168">You can then check the status using the URI [http://localhost:5102/failing](http://localhost:5100/failing), as shown in Figure 10-4.</span></span>

![](./media/image4.png)

<span data-ttu-id="e5161-169">**그림 10-4**합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-169">**Figure 10-4**.</span></span> <span data-ttu-id="e5161-170">ASP.NET 미들웨어를 사용 하 여 오류를 시뮬레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-170">Simulating a failure with ASP.NET middleware</span></span>

<span data-ttu-id="e5161-171">이 시점에서 상태 코드 500 호출할 때마다 정렬 마이크로 서비스 응답 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-171">At this point, the ordering microservice responds with status code 500 whenever you call invoke it.</span></span>

<span data-ttu-id="e5161-172">미들웨어 실행 되 면 MVC 웹 응용 프로그램에서 주문을 만드는 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-172">Once the middleware is running, you can try making an order from the MVC web application.</span></span> <span data-ttu-id="e5161-173">요청에 실패 하면 회로가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-173">Because the requests fails, the circuit will open.</span></span>

<span data-ttu-id="e5161-174">다음 예에서 확인할 수 있습니다 MVC 웹 응용 프로그램에는 catch 주문 하기 위한 논리의 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-174">In the following example, you can see that the MVC web application has a catch block in the logic for placing an order.</span></span> <span data-ttu-id="e5161-175">된 오픈 회로 예외를 catch 하는 코드를 하는 경우 사용자가 친숙 한 메시지 내용의 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-175">If the code catches an open-circuit exception, it shows the user a friendly message telling them to wait.</span></span>

```csharp
[HttpPost]
public async Task<IActionResult> Create(Order model, string action)
{
    try
    {
        if (ModelState.IsValid)
        {
            var user = _appUserParser.Parse(HttpContext.User);
            await _orderSvc.CreateOrder(model);
            //Redirect to historic list.
            return RedirectToAction("Index");
        }
    }
    catch(BrokenCircuitException ex)
    {
        ModelState.AddModelError("Error",
            "It was not possible to create a new order, please try later on");
    }
    return View(model);
}
```

<span data-ttu-id="e5161-176">다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-176">Here’s a summary.</span></span> <span data-ttu-id="e5161-177">재시도 정책에는 HTTP 요청 및 HTTP 오류 가져옵니다를 여러 번 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-177">The Retry policy tries several times to make the HTTP request and gets HTTP errors.</span></span> <span data-ttu-id="e5161-178">시도 수 (이 경우 5)에서 회로 차단기 정책에 대 한 최대 설정 수에 도달 하면 응용 프로그램에는 BrokenCircuitException throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-178">When the number of tries reaches the maximum number set for the Circuit Breaker policy (in this case, 5), the application throws a BrokenCircuitException.</span></span> <span data-ttu-id="e5161-179">결과 그림 10-5와 같이 친숙 한 메시지는.</span><span class="sxs-lookup"><span data-stu-id="e5161-179">The result is a friendly message, as shown in Figure 10-5.</span></span>

![](./media/image5.png)

<span data-ttu-id="e5161-180">**그림 10-5**합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-180">**Figure 10-5**.</span></span> <span data-ttu-id="e5161-181">회로 차단기는 UI를 오류를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-181">Circuit breaker returning an error to the UI</span></span>

<span data-ttu-id="e5161-182">회로 열려는 시기에 대 한 다른 논리를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-182">You can implement different logic for when to open the circuit.</span></span> <span data-ttu-id="e5161-183">또는 대체 데이터 센터 또는 중복 백 엔드 시스템 있는 경우 다른 백 엔드 마이크로 서비스에 대 한 HTTP 요청을 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-183">Or you can try an HTTP request against a different back-end microservice if there is a fallback datacenter or redundant back-end system.</span></span>

<span data-ttu-id="e5161-184">마지막으로 CircuitBreakerPolicy는 또 다른 방법은 Isolate (있는 회로 열려 보유을 강제로 열기) 및 (있음 다시 닫힙니다) 리셋을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-184">Finally, another possibility for the CircuitBreakerPolicy is to use Isolate (which forces open and holds open the circuit) and Reset (which closes it again).</span></span> <span data-ttu-id="e5161-185">정책에서 격리 및 재설정 직접 호출 하는 유틸리티 HTTP 끝점을 만드는 데 사용할 수 있습니다 이러한.</span><span class="sxs-lookup"><span data-stu-id="e5161-185">These could be used to build a utility HTTP endpoint that invokes Isolate and Reset directly on the policy.</span></span> <span data-ttu-id="e5161-186">이러한 HTTP 끝점이 사용할 수도, 일시적으로 업그레이드 하는 경우와 같이 다운스트림 시스템을 격리 하기 위해 프로덕션 환경에서 적절 하 게 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-186">Such an HTTP endpoint could also be used, suitably secured, in production for temporarily isolating a downstream system, such as when you want to upgrade it.</span></span> <span data-ttu-id="e5161-187">또는 오류가 있는 수에 대해 의심 스러운 하면 다운스트림 시스템을 보호 하려면 수동으로 회로 여행 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-187">Or it could trip the circuit manually to protect a downstream system you suspect to be faulting.</span></span>

## <a name="adding-a-jitter-strategy-to-the-retry-policy"></a><span data-ttu-id="e5161-188">지터 전략을 다시 시도 정책에 추가</span><span class="sxs-lookup"><span data-stu-id="e5161-188">Adding a jitter strategy to the retry policy</span></span>

<span data-ttu-id="e5161-189">일반 다시 시도 정책은 시스템의 높은 동시성 및 확장성을 경합이 많이 발생 하는 경우에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-189">A regular Retry policy can impact your system in cases of high concurrency and scalability and under high contention.</span></span> <span data-ttu-id="e5161-190">부분 작동 중단 발생 시 많은 클라이언트에서 오는 유사한 재시도의 최대 사용량을 해결 하려면 적합 한 해결을 다시 시도 알고리즘/정책 지터 전략을 추가 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-190">To overcome peaks of similar retries coming from many clients in case of partial outages, a good workaround is to add a jitter strategy to the retry algorithm/policy.</span></span> <span data-ttu-id="e5161-191">임의성 지 수 백오프를 추가 하 여 종단 간 시스템의 전반적인 성능을 향상 시킬 수 있습니다이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-191">This can improve the overall performance of the end-to-end system by adding randomness to the exponential backoff.</span></span> <span data-ttu-id="e5161-192">이 문제가 발생할 때 해결할 퍼져나가는 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-192">This spreads out the spikes when issues arise.</span></span> <span data-ttu-id="e5161-193">관을 사용 하면 지터를 구현 하는 코드는 다음 예제에서는 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5161-193">When you use Polly, code to implement jitter could look like the following example:</span></span>

```csharp
Random jitterer = new Random();
Policy.Handle<HttpResponseException>() // etc
    .WaitAndRetry(5, // exponential back-off plus some jitter
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))
            + TimeSpan.FromMilliseconds(jitterer.Next(0, 100))
    );
```

## <a name="additional-resources"></a><span data-ttu-id="e5161-194">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="e5161-194">Additional resources</span></span>

-   <span data-ttu-id="e5161-195">**패턴을 다시 시도**
    [*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)</span><span class="sxs-lookup"><span data-stu-id="e5161-195">**Retry pattern**
[*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)</span></span>

-   <span data-ttu-id="e5161-196">**연결 복원 력** (Entity Framework Core) [ *https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)</span><span class="sxs-lookup"><span data-stu-id="e5161-196">**Connection Resiliency** (Entity Framework Core) [*https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)</span></span>

-   <span data-ttu-id="e5161-197">**관** (.NET 복원 력 및 일시적인 오류 처리 라이브러리) [ *https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)</span><span class="sxs-lookup"><span data-stu-id="e5161-197">**Polly** (.NET resilience and transient-fault-handling library) [*https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)</span></span>

-   <span data-ttu-id="e5161-198">**회로 차단기 패턴**
    [*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)</span><span class="sxs-lookup"><span data-stu-id="e5161-198">**Circuit Breaker pattern**
[*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)</span></span>

-   <span data-ttu-id="e5161-199">**Marc Brooker 합니다. 지터: 작업을 위해 더 잘 임의성으로** https://brooker.co.za/blog/2015/03/21/backoff.html</span><span class="sxs-lookup"><span data-stu-id="e5161-199">**Marc Brooker. Jitter: Making Things Better With Randomness** https://brooker.co.za/blog/2015/03/21/backoff.html</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="e5161-200">[이전] [다음] (모니터 앱 health.md) (implement-http-call-retries-exponential-backoff-polly.md)</span><span class="sxs-lookup"><span data-stu-id="e5161-200">[Previous] (implement-http-call-retries-exponential-backoff-polly.md) [Next] (monitor-app-health.md)</span></span>
