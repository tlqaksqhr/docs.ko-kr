---
title: "부분 실패 처리 전략"
description: "컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | 부분 실패 처리 전략"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 0b5fdb03e4b0d0c2d4e8aa8a897fd46d56707f11
ms.sourcegitcommit: c3957fdb990060559d73cca44ab3e2c7b4d049c0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2018
---
# <a name="strategies-for-handling-partial-failure"></a><span data-ttu-id="93bce-104">부분 실패 처리 전략</span><span class="sxs-lookup"><span data-stu-id="93bce-104">Strategies for handling partial failure</span></span>

<span data-ttu-id="93bce-105">부분 실패 처리 전략은 다음을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="93bce-105">Strategies for dealing with partial failures include the following.</span></span>

<span data-ttu-id="93bce-106">**내부 마이크로 서비스 전체에 걸친 비동기 통신(예를 들어, 메시지 기반 통신) 사용**.</span><span class="sxs-lookup"><span data-stu-id="93bce-106">**Use asynchronous communication (for example, message-based communication) across internal microservices**.</span></span> <span data-ttu-id="93bce-107">잘못된 디자인은 결국 잘못된 중단의 결정적 원인이 되기 때문에 내부 마이크로 서비스 전역에 걸쳐 동기 HTTP 호출의 긴 체인을 만들지 않는 것이 바람직합니다.</span><span class="sxs-lookup"><span data-stu-id="93bce-107">It is highly advisable not to create long chains of synchronous HTTP calls across the internal microservices because that incorrect design will eventually become the main cause of bad outages.</span></span> <span data-ttu-id="93bce-108">반대로, 클라이언트 응용 프로그램과 첫 번째 수준의 마이크로 서비스 또는 세분화된 API 게이트웨이 간의 프런트 엔드 통신을 제외하고 내부 마이크로 서비스 전역에 걸쳐 초기 요청/응답 주기를 넘어서 비동기(메시지 기반) 통신만 한 번 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="93bce-108">On the contrary, except for the front-end communications between the client applications and the first level of microservices or fine-grained API Gateways, it is recommended to use only asynchronous (message-based) communication once past the initial request/response cycle, across the internal microservices.</span></span> <span data-ttu-id="93bce-109">결과적 일관성 및 이벤트 기반 아키텍처는 파급 효과를 최소화하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93bce-109">Eventual consistency and event-driven architectures will help to minimize ripple effects.</span></span> <span data-ttu-id="93bce-110">이런 접근법은 높은 수준의 마이크로 서비스 자율성을 시행하고 따라서 여기서 지적된 문제를 예방할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93bce-110">These approaches enforce a higher level of microservice autonomy and therefore prevent against the problem noted here.</span></span>

<span data-ttu-id="93bce-111">**지수 백오프를 사용하여 다시 시도 사용**.</span><span class="sxs-lookup"><span data-stu-id="93bce-111">**Use retries with exponential backoff**.</span></span> <span data-ttu-id="93bce-112">이 기법은 해당 서비스가 단기간만 사용할 수 없을 경우 호출 다시 시도를 여러 번 수행함으로써 단기간의 일시적인 오류를 막는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93bce-112">This technique helps to avoid short and intermittent failures by performing call retries a certain number of times, in case the service was not available only for a short time.</span></span> <span data-ttu-id="93bce-113">이런 현상은 마이크로 서비스/컨테이너를 클러스터의 다른 노드로 이동할 경우 또는 일시적인 네트워크 문제로 인해 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93bce-113">This might occur due to intermittent network issues or when a microservice/container is moved to a different node in a cluster.</span></span> <span data-ttu-id="93bce-114">그러나 이러한 재시도가 회로 차단기를 사용해 적절히 계획되지 않은 경우 그 파급 효과는 악화되고 결국 [서비스 거부(DoS)](https://en.wikipedia.org/wiki/Denial-of-service_attack)를 초래할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93bce-114">However, if these retries are not designed properly with circuit breakers, it can aggravate the ripple effects, ultimately even causing a [Denial of Service (DoS)](https://en.wikipedia.org/wiki/Denial-of-service_attack).</span></span>

<span data-ttu-id="93bce-115">**네트워크 시간 제한의 해결 방법**.</span><span class="sxs-lookup"><span data-stu-id="93bce-115">**Work around network timeouts**.</span></span> <span data-ttu-id="93bce-116">일반적으로 클라이언트는 응답을 기다릴 때 항상 시간 제한을 사용하되 무기한 차단하지 않도록 설계되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93bce-116">In general, clients should be designed not to block indefinitely and to always use timeouts when waiting for a response.</span></span> <span data-ttu-id="93bce-117">시간 제한의 사용은 리소스가 절대 무기한으로 묶여 있지 않게 합니다.</span><span class="sxs-lookup"><span data-stu-id="93bce-117">Using timeouts ensures that resources are never tied up indefinitely.</span></span>

<span data-ttu-id="93bce-118">**회로 차단기 패턴 사용**.</span><span class="sxs-lookup"><span data-stu-id="93bce-118">**Use the Circuit Breaker pattern**.</span></span> <span data-ttu-id="93bce-119">이 방법에서 클라이언트 프로세스는 실패한 요청 횟수를 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="93bce-119">In this approach, the client process tracks the number of failed requests.</span></span> <span data-ttu-id="93bce-120">오류율이 설정된 제한을 초과하는 경우 “회로 차단기”가 작동해 더 이상의 시도는 즉시 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="93bce-120">If the error rate exceeds a configured limit, a “circuit breaker” trips so that further attempts fail immediately.</span></span> <span data-ttu-id="93bce-121">(많은 요청이 실패 하는 경우 서비스가 사용할 수 없게 되고 요청 전송이 무의미하다는 것을 의미합니다.) 제한 시간 경과 후 해당 클라이언트는 다시 시도해야 하며 새 요청이 성공하는 경우 회로 차단기를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="93bce-121">(If a large number of requests are failing, that suggests the service is unavailable and that sending requests is pointless.) After a timeout period, the client should try again and, if the new requests are successful, close the circuit breaker.</span></span>

<span data-ttu-id="93bce-122">**대체 제공**.</span><span class="sxs-lookup"><span data-stu-id="93bce-122">**Provide fallbacks**.</span></span> <span data-ttu-id="93bce-123">이 방법에서 클라이언트 프로세스는 캐시된 데이터 또는 기본값 반환처럼 요청이 실패한 경우 대체 논리를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="93bce-123">In this approach, the client process performs fallback logic when a request fails, such as returning cached data or a default value.</span></span> <span data-ttu-id="93bce-124">이 방법은 쿼리에 적합하며 업데이트나 명령에 관해서는 더욱 복잡합니다.</span><span class="sxs-lookup"><span data-stu-id="93bce-124">This is an approach suitable for queries, and is more complex for updates or commands.</span></span>

<span data-ttu-id="93bce-125">**큐에 대기 중인 요청 수 제한**.</span><span class="sxs-lookup"><span data-stu-id="93bce-125">**Limit the number of queued requests**.</span></span> <span data-ttu-id="93bce-126">클라이언트는 클라이언트 마이크로 서비스가 특정 서비스에 보낼 수 있는 대기 중인 요청 수에 대한 상한값을 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93bce-126">Clients should also impose an upper bound on the number of outstanding requests that a client microservice can send to a particular service.</span></span> <span data-ttu-id="93bce-127">제한치에 도달한 경우 추가 요청을 하는 것은 무의미하며 이런 시도는 즉각 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="93bce-127">If the limit has been reached, it is probably pointless to make additional requests, and those attempts should fail immediately.</span></span> <span data-ttu-id="93bce-128">구현 관점에서 Polly [Bulkhead 격리](https://github.com/App-vNext/Polly/wiki/Bulkhead) 정책은 요구 사항을 충족하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93bce-128">In terms of implementation, the Polly [Bulkhead Isolation](https://github.com/App-vNext/Polly/wiki/Bulkhead) policy can be used to fulfil this requirement.</span></span> <span data-ttu-id="93bce-129">이 방법은 기본적으로 <xref:System.Threading.SemaphoreSlim>을 구현으로 사용하는 병렬화 제한입니다.</span><span class="sxs-lookup"><span data-stu-id="93bce-129">This approach is essentially a parallelization throttle with <xref:System.Threading.SemaphoreSlim> as the implementation.</span></span> <span data-ttu-id="93bce-130">또한 Bulkhead 외부에 "큐"를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="93bce-130">It also permits a "queue" outside the bulkhead.</span></span> <span data-ttu-id="93bce-131">실행 전에도 과부하를 미리 줄일 수 있습니다(예를 들어, 용량이 가득찼다고 여겨지기 때문에).</span><span class="sxs-lookup"><span data-stu-id="93bce-131">You can proactively shed excess load even before execution (for example, because capacity is deemed full).</span></span> <span data-ttu-id="93bce-132">이렇게 하면 특정 오류 시나리오에 대한 응답이 회로 차단기보다 더 빠르게 됩니다. 회로 차단기는 오류를 대기하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="93bce-132">This makes its response to certain failure scenarios faster than a circuit breaker would be, since the circuit breaker waits for the failures.</span></span> <span data-ttu-id="93bce-133">Polly에서 BulkheadPolicy 개체는 Bulkhead와 큐가 얼마나 차있는지 드러내며 오버플로에 대한 이벤트를 제공하므로 자동화된 수평 확장에 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93bce-133">The BulkheadPolicy object in Polly exposes how full the bulkhead and queue are, and offers events on overflow so can also be used to drive automated horizontal scaling.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="93bce-134">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="93bce-134">Additional resources</span></span>

-   <span data-ttu-id="93bce-135">**복원력 패턴**
    [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)</span><span class="sxs-lookup"><span data-stu-id="93bce-135">**Resiliency patterns**
[*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)</span></span>

-   <span data-ttu-id="93bce-136">**복원력 추가 및 성능 최적화**
    [*https://msdn.microsoft.com/library/jj591574.aspx*](https://msdn.microsoft.com/library/jj591574.aspx)</span><span class="sxs-lookup"><span data-stu-id="93bce-136">**Adding Resilience and Optimizing Performance**
[*https://msdn.microsoft.com/library/jj591574.aspx*](https://msdn.microsoft.com/library/jj591574.aspx)</span></span>

-   <span data-ttu-id="93bce-137">**Bulkhead.**</span><span class="sxs-lookup"><span data-stu-id="93bce-137">**Bulkhead.**</span></span> <span data-ttu-id="93bce-138">GitHub 리포지토리.</span><span class="sxs-lookup"><span data-stu-id="93bce-138">GitHub repo.</span></span> <span data-ttu-id="93bce-139">Polly 정책 구현.\\</span><span class="sxs-lookup"><span data-stu-id="93bce-139">Implementation with Polly policy.\\</span></span>
    [<span data-ttu-id="93bce-140">*https://github.com/App-vNext/Polly/wiki/Bulkhead*</span><span class="sxs-lookup"><span data-stu-id="93bce-140">*https://github.com/App-vNext/Polly/wiki/Bulkhead*</span></span>](https://github.com/App-vNext/Polly/wiki/Bulkhead)

-   <span data-ttu-id="93bce-141">**Azure용 복원력 있는 응용 프로그램 설계**
    [*https://docs.microsoft.com/azure/architecture/resiliency/*](https://docs.microsoft.com/azure/architecture/resiliency/)</span><span class="sxs-lookup"><span data-stu-id="93bce-141">**Designing resilient applications for Azure**
[*https://docs.microsoft.com/azure/architecture/resiliency/*](https://docs.microsoft.com/azure/architecture/resiliency/)</span></span>

-   <span data-ttu-id="93bce-142">**일시적인 오류 처리**
    <https://docs.microsoft.com/azure/architecture/best-practices/transient-faults></span><span class="sxs-lookup"><span data-stu-id="93bce-142">**Transient fault handling**
<https://docs.microsoft.com/azure/architecture/best-practices/transient-faults></span></span>


>[!div class="step-by-step"]
<span data-ttu-id="93bce-143">[이전] (handle-partial-failure.md) [다음] (implement-retries-exponential-backoff.md)</span><span class="sxs-lookup"><span data-stu-id="93bce-143">[Previous] (handle-partial-failure.md) [Next] (implement-retries-exponential-backoff.md)</span></span>
