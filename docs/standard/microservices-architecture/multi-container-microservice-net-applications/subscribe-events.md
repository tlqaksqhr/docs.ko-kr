---
title: "이벤트 구독"
description: "컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | 이벤트 구독"
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
ms.openlocfilehash: 7538c760d396349fe9b1e93a21839e3e59d7f046
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="subscribing-to-events"></a><span data-ttu-id="a3212-104">이벤트 구독</span><span class="sxs-lookup"><span data-stu-id="a3212-104">Subscribing to events</span></span>

<span data-ttu-id="a3212-105">이벤트 버스를 사용하기 위한 첫 번째 단계는 마이크로 서비스에서 수신하려는 이벤트를 구독하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-105">The first step for using the event bus is to subscribe the microservices to the events they want to receive.</span></span> <span data-ttu-id="a3212-106">구독은 수신자 마이크로 서비스에서 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-106">That should be done in the receiver microservices.</span></span>

<span data-ttu-id="a3212-107">다음의 간단한 코드는 서비스를 시작할 때(즉, `Startup` 클래스에서) 마이크로 서비스가 필요한 이벤트를 구독할 수 있도록 각 수신자 마이크로 서비스가 무엇을 구현해야 하는가를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-107">The following simple code shows what each receiver microservice needs to implement when starting the service (that is, in the `Startup` class) so it subscribes to the events it needs.</span></span> <span data-ttu-id="a3212-108">이 경우 `basket.api` 마이크로 서비스는 `ProductPriceChangedIntegrationEvent` 및 `OrderStartedIntegrationEvent` 메시지를 구독해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-108">In this case, the `basket.api` microservice needs to subscribe to `ProductPriceChangedIntegrationEvent` and the `OrderStartedIntegrationEvent` messages.</span></span> 

<span data-ttu-id="a3212-109">예를 들어 `ProductPriceChangedIntegrationEvent` 이벤트에 등록하면 장바구니 마이크로 서비스는 제품 가격의 변경 사항을 파악하고 해당 제품이 사용자의 장바구니에 있는 경우 사용자에게 변경 사항을 경고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-109">For instance, when subscribing to the `ProductPriceChangedIntegrationEvent` event, that makes the basket microservice aware of any changes to the product price and lets it warn the user about the change if that product is in the user’s basket.</span></span>

```csharp
var eventBus = app.ApplicationServices.GetRequiredService<IEventBus>();

eventBus.Subscribe<ProductPriceChangedIntegrationEvent, 
                   ProductPriceChangedIntegrationEventHandler>();

eventBus.Subscribe<OrderStartedIntegrationEvent, 
                   OrderStartedIntegrationEventHandler>();

```

<span data-ttu-id="a3212-110">이 코드가 실행되면 구독자 마이크로 서비스는 RabbitMQ 채널을 통해 수신 대기하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-110">After this code runs, the subscriber microservice will be listening through RabbitMQ channels.</span></span> <span data-ttu-id="a3212-111">ProductPriceChangedIntegrationEvent 유형의 메시지가 도착하면 코드가 여기에 전달된 이벤트 처리기를 호출하고 이벤트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-111">When any message of type ProductPriceChangedIntegrationEvent arrives, the code invokes the event handler that is passed to it and processes the event.</span></span>

## <a name="publishing-events-through-the-event-bus"></a><span data-ttu-id="a3212-112">이벤트 버스를 통한 이벤트 게시</span><span class="sxs-lookup"><span data-stu-id="a3212-112">Publishing events through the event bus</span></span>

<span data-ttu-id="a3212-113">마지막으로 메시지 발송자(원본 마이크로 서비스)는 다음 예와 유사한 코드를 사용해 통합 이벤트를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-113">Finally, the message sender (origin microservice) publishes the integration events with code similar to the following example.</span></span> <span data-ttu-id="a3212-114">(원자성을 고려하지 않은 간단 예제입니다.) 일반적으로 원본 마이크로 서비스의 데이터 또는 트랜잭션을 커밋한 직후에 여러 마이크로 서비스로 이벤트를 전파할 때마다 유사한 코드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-114">(This is a simplified example that does not take atomicity into account.) You would implement similar code whenever an event must be propagated across multiple microservices, usually right after committing data or transactions from the origin microservice.</span></span>

<span data-ttu-id="a3212-115">가장 먼저 다음 코드와 같이 컨트롤러 생성자에서 이벤트 버스 구현 개체(RabbitMQ 기반 또는 서비스 버스 기반)를 주입합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-115">First, the event bus implementation object (based on RabbitMQ or based on a service bus) would be injected at the controller constructor, as in the following code:</span></span>

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    private readonly CatalogContext _context;
    private readonly IOptionsSnapshot<Settings> _settings;
    private readonly IEventBus _eventBus;

    public CatalogController(CatalogContext context,
        IOptionsSnapshot<Settings> settings,
        IEventBus eventBus)
    {
        _context = context;
        _settings = settings;
        _eventBus = eventBus;
    }
    // ...
}
```

<span data-ttu-id="a3212-116">그런 다음, UpdateProduct 메서드와 같이 컨트롤러 메소드에서 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-116">Then you use it from your controller’s methods, like in the UpdateProduct method:</span></span>

```csharp
[Route("update")]
[HttpPost]
public async Task<IActionResult> UpdateProduct([FromBody]CatalogItem product)
{
    var item = await _context.CatalogItems.SingleOrDefaultAsync(
        i => i.Id == product.Id);
    // ...
    if (item.Price != product.Price)
    {
        var oldPrice = item.Price;
        item.Price = product.Price;
        _context.CatalogItems.Update(item);
        var @event = new ProductPriceChangedIntegrationEvent(item.Id,
            item.Price,
            oldPrice);
        // Commit changes in original transaction
        await _context.SaveChangesAsync();
        // Publish integration event to the event bus
        // (RabbitMQ or a service bus underneath)
        _eventBus.Publish(@event);
        // ...
    }
    // ...
}
```

<span data-ttu-id="a3212-117">이 경우에는 원본 마이크로 서비스가 간단한 CRUD 마이크로 서비스이므로 해당 코드가 웹 API 컨트롤러에 바로 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-117">In this case, since the origin microservice is a simple CRUD microservice, that code is placed right into a Web API controller.</span></span> 
 
<span data-ttu-id="a3212-118">CQRS 방식을 사용하는 경우와 같은 고급 마이크로 서비스의 경우에는 `Handle()` 메서드 내 `CommandHandler` 클래스에 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-118">In more advanced microservices, like when using CQRS approaches, it can be implemented in the `CommandHandler` class, within the `Handle()` method.</span></span> 


### <a name="designing-atomicity-and-resiliency-when-publishing-to-the-event-bus"></a><span data-ttu-id="a3212-119">이벤트 버스로 게시할 경우 원자성 및 복원력 디자인</span><span class="sxs-lookup"><span data-stu-id="a3212-119">Designing atomicity and resiliency when publishing to the event bus</span></span>

<span data-ttu-id="a3212-120">이벤트 버스와 같은 분산 메시징 시스템을 통해 통합 이벤트를 게시할 경우 원본 데이터베이스를 하나의 큰 단위로 업데이트하고 이벤트를 게시하는 데 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-120">When you publish integration events through a distributed messaging system like your event bus, you have the problem of atomically updating the original database and publishing an event.</span></span> <span data-ttu-id="a3212-121">예를 들어 위에 나와 있는 간단 예제의 코드는 제품 가격이 변경될 때 데이터베이스에 데이터를 커밋한 다음, ProductPriceChangedIntegrationEvent 메시지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-121">For instance, in the simplified example shown earlier, the code commits data to the database when the product price is changed and then publishes a ProductPriceChangedIntegrationEvent message.</span></span> <span data-ttu-id="a3212-122">초기에는 이러한 두 작업을 하나의 큰 단위로 수행해야만 하는 것처럼 보입니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-122">Initially, it might look essential that these two operations be performed atomically.</span></span> <span data-ttu-id="a3212-123">하지만 [MSMQ(Microsoft Message Queuing)](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx) 등의 기존 시스템과 같은 방식으로 데이터베이스 및 메시지 브로커가 포함된 분산 트랜잭션을 사용하는 경우에는 [CAP 공식](https://www.quora.com/What-Is-CAP-Theorem-1)에서 설명하는 이유 때문에 적절하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-123">However, if you are using a distributed transaction involving the database and the message broker, as you do in older systems like [Microsoft Message Queuing (MSMQ)](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx), this is not recommended for the reasons described by the [CAP theorem](https://www.quora.com/What-Is-CAP-Theorem-1).</span></span>

<span data-ttu-id="a3212-124">기본적으로 마이크로 서비스는 확장 가능하고 가용성이 높은 시스템을 빌드하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-124">Basically, you use microservices to build scalable and highly available systems.</span></span> <span data-ttu-id="a3212-125">간단히 말해, CAP 공식에 따르면 지속적으로 가용하며 일관성이 높고 *그리고* 모든 파티션에 허용되는 데이터베이스(또는 해당 모델을 소유하는 마이크로 서비스)를 빌드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-125">Simplifying somewhat, the CAP theorem says that you cannot build a database (or a microservice that owns its model) that is continually available, strongly consistent, *and* tolerant to any partition.</span></span> <span data-ttu-id="a3212-126">다음과 같은 특성 중 두 가지를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-126">You must choose two of these three properties.</span></span>

<span data-ttu-id="a3212-127">마이크로 서비스 기반 아키텍처에서는 가용성과 허용을 선택해야 하며 강력한 일관성은 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-127">In microservices-based architectures, you should choose availability and tolerance, and you should deemphasize strong consistency.</span></span> <span data-ttu-id="a3212-128">따라서 [MSMQ](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx)와 함께 Windows DTC(Distributed Transaction Coordinator) 기반 [분산 트랜잭션](https://msdn.microsoft.com/library/ms978430.aspx#bdadotnetasync2_topic3c)을 구현할 때와 마찬가지로 오늘날 대부분의 마이크로 서비스 기반 응용 프로그램에서는 일반적으로 메시징에 분산 트랜잭션을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-128">Therefore, in most modern microservice-based applications, you usually do not want to use distributed transactions in messaging, as you do when you implement [distributed transactions](https://msdn.microsoft.com/library/ms978430.aspx#bdadotnetasync2_topic3c) based on the Windows Distributed Transaction Coordinator (DTC) with [MSMQ](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx).</span></span>

<span data-ttu-id="a3212-129">처음의 문제와 해당 예를 다시 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-129">Let’s go back to the initial issue and its example.</span></span> <span data-ttu-id="a3212-130">데이터베이스를 업데이트한 후부터(이 경우 \_context.SaveChangesAsync()가 포함된 코드 라인 직후) 통합 이벤트를 게시하기 전까지 서비스가 충돌하는 경우 전체 시스템이 비일관 상태가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-130">If the service crashes after the database is updated (in this case, right after the line of code with \_context.SaveChangesAsync()), but before the integration event is published, the overall system could become inconsistent.</span></span> <span data-ttu-id="a3212-131">이 경우 처리하는 특정 비즈니스 작업에 따라 중요 비즈니스 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-131">This might be business critical, depending on the specific business operation you are dealing with.</span></span>

<span data-ttu-id="a3212-132">앞의 아키텍처 섹션에서 언급했듯이 몇 가지 방식으로 이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-132">As mentioned earlier in the architecture section, you can have several approaches for dealing with this issue:</span></span>

-   <span data-ttu-id="a3212-133">[전체 이벤트 소싱](https://msdn.microsoft.com/library/dn589792.aspx) 패턴 사용.</span><span class="sxs-lookup"><span data-stu-id="a3212-133">Using the full [Event Sourcing pattern](https://msdn.microsoft.com/library/dn589792.aspx).</span></span>

-   <span data-ttu-id="a3212-134">[트랜잭션 로그 마이닝](http://www.scoop.it/t/sql-server-transaction-log-mining) 사용.</span><span class="sxs-lookup"><span data-stu-id="a3212-134">Using [transaction log mining](http://www.scoop.it/t/sql-server-transaction-log-mining).</span></span>

-   <span data-ttu-id="a3212-135">[아웃박스 패턴](http://gistlabs.com/2014/05/the-outbox/) 사용.</span><span class="sxs-lookup"><span data-stu-id="a3212-135">Using the [Outbox pattern](http://gistlabs.com/2014/05/the-outbox/).</span></span> <span data-ttu-id="a3212-136">이 트랜잭션 테이블에는 통합 이벤트를 저장합니다(로컬 트랜잭션 확장).</span><span class="sxs-lookup"><span data-stu-id="a3212-136">This is a transactional table to store the integration events (extending the local transaction).</span></span>

<span data-ttu-id="a3212-137">이 시나리오의 경우 ES(이벤트 소싱) 패턴이 *가장* 적절하거나 적절한 방법 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-137">For this scenario, using the full Event Sourcing (ES) pattern is one of the best approaches, if not *the* best.</span></span> <span data-ttu-id="a3212-138">하지만 대부분의 응용 프로그램 시나리오에서는 전체 ES 시스템을 구현하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-138">However, in many application scenarios, you might not be able to implement a full ES system.</span></span> <span data-ttu-id="a3212-139">ES란 현재 상태 데이터를 저장하는 대신 트랜잭션 데이터베이스에 도메인 이벤트만 저장하는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-139">ES means storing only domain events in your transactional database, instead of storing current state data.</span></span> <span data-ttu-id="a3212-140">도메인 이벤트만 저장할 경우 시스템 기록을 사용할 수 있다는 점, 지난 시스템 상태를 확인할 수 있다는 점 등의 뛰어난 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-140">Storing only domain events can have great benefits, such as having the history of your system available and being able to determine the state of your system at any moment in the past.</span></span> <span data-ttu-id="a3212-141">하지만 전체 ES 시스템을 구현하려면 대부분의 시스템을 재설계해야 하며 그 외에도 많은 복잡성과 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-141">However, implementing a full ES system requires you to rearchitect most of your system and introduces many other complexities and requirements.</span></span> <span data-ttu-id="a3212-142">예를 들어 [이벤트 저장소](https://geteventstore.com/) 등의 이벤트 소싱용으로 만든 데이터베이스 또는 Azure Cosmos DB, MongoDB, Cassandra, CouchDB, RavenDB 등의 문서 중심 데이터베이스를 사용하려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-142">For example, you would want to use a database specifically made for event sourcing, such as [Event Store](https://geteventstore.com/), or a document-oriented database such as Azure Cosmos DB, MongoDB, Cassandra, CouchDB, or RavenDB.</span></span> <span data-ttu-id="a3212-143">ES는 이 문제에 적합한 방식이지만 이벤트 소싱에 대해 잘 알고 있는 경우가 아니면 가장 쉬운 솔루션이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-143">ES is a great approach for this problem, but not the easiest solution unless you are already familiar with event sourcing.</span></span>

<span data-ttu-id="a3212-144">트랜잭션 로그 마이닝을 사용하는 옵션은 처음에는 매우 간단해 보입니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-144">The option to use transaction log mining initially looks very transparent.</span></span> <span data-ttu-id="a3212-145">하지만 이 방식을 사용하려면 마이크로 서비스를 SQL Server 트랜잭션 로그와 같은 RDBMS 트랜잭션 로그에 결합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-145">However, to use this approach, the microservice has to be coupled to your RDBMS transaction log, such as the SQL Server transaction log.</span></span> <span data-ttu-id="a3212-146">이는 바람직하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-146">This is probably not desirable.</span></span> <span data-ttu-id="a3212-147">또 다른 단점은 트랜잭션 로그에 기록된 하위 수준 업데이트가 상위 수준 통합 이벤트와 같은 수준이 아닐 수 있다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-147">Another drawback is that the low-level updates recorded in the transaction log might not be at the same level as your high-level integration events.</span></span> <span data-ttu-id="a3212-148">그럴 경우 이러한 트랜잭션 로그 작업을 리버스 엔지니어링하는 프로세스가 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-148">If so, the process of reverse-engineering those transaction log operations can be difficult.</span></span>

<span data-ttu-id="a3212-149">균형 있는 방식은 트랜잭션 데이터베이스 테이블과 간단한 ES 패턴을 혼합하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-149">A balanced approach is a mix of a transactional database table and a simplified ES pattern.</span></span> <span data-ttu-id="a3212-150">통합 이벤트 테이블로 커밋할 때 원본 이벤트에서 설정하는 "이벤트 게시 준비 완료" 등의 상태를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-150">You can use a state such as “ready to publish the event,” which you set in the original event when you commit it to the integration events table.</span></span> <span data-ttu-id="a3212-151">그런 다음, 이벤트를 이벤트 버스에 게시해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-151">You then try to publish the event to the event bus.</span></span> <span data-ttu-id="a3212-152">이벤트-게시 작업이 성공할 경우 원본 서비스에서 다른 트랜잭션을 시작하고 "이벤트 게시 준비 완료"에서 "이벤트 이미 게시됨" 상태로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-152">If the publish-event action succeeds, you start another transaction in the origin service and move the state from “ready to publish the event” to “event already published.”</span></span>

<span data-ttu-id="a3212-153">이벤트 버스에서 이벤트-게시 작업이 실패할 경우 원본 마이크로 서비스 내 데이터는 여전히 비일관 상태로 "이벤트 게시 준비 완료"로 표시되며 나머지 서비스는 결과적으로 일관 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-153">If the publish-event action in the event bus fails, the data still will not be inconsistent within the origin microservice—it is still marked as “ready to publish the event,” and with respect to the rest of the services, it will eventually be consistent.</span></span> <span data-ttu-id="a3212-154">언제든지 백그라운드 작업으로 트랜잭션 또는 통합 이벤트를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-154">You can always have background jobs checking the state of the transactions or integration events.</span></span> <span data-ttu-id="a3212-155">이 작업에서 이벤트가 "이벤트 게시 준비 완료" 상태인 것을 발견하면 해당 이벤트를 이벤트 버스로 다시 게시해볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-155">If the job finds an event in the “ready to publish the event” state, it can try to republish that event to the event bus.</span></span>

<span data-ttu-id="a3212-156">이 방식에서는 각 원본 마이크로 서비스의 통합 이벤트와 다른 마이크로 서비스 또는 외부 시스템으로 전달하려는 이벤트만 지속하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-156">Notice that with this approach, you are persisting only the integration events for each origin microservice, and only the events that you want to communicate to other microservices or external systems.</span></span> <span data-ttu-id="a3212-157">반면 전체 ES 시스템에서는 모든 도메인 이벤트도 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-157">In contrast, in a full ES system, you store all domain events as well.</span></span>

<span data-ttu-id="a3212-158">따라서 이러한 균형적 방식이 간소화된 ES 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-158">Therefore, this balanced approach is a simplified ES system.</span></span> <span data-ttu-id="a3212-159">통합 이벤트와 해당 현재 상태의 목록이 필요합니다("게시 준비 완료" 및 "게시됨").</span><span class="sxs-lookup"><span data-stu-id="a3212-159">You need a list of integration events with their current state (“ready to publish” versus “published”).</span></span> <span data-ttu-id="a3212-160">하지만 통합 서비스에 대해서만 이러한 상태를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-160">But you only need to implement these states for the integration events.</span></span> <span data-ttu-id="a3212-161">이 방식에서는 전체 ES 시스템처럼 트랜잭션 데이터베이스에 모든 도메인 데이터를 이벤트로 저장하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-161">And in this approach, you do not need to store all your domain data as events in the transactional database, as you would in a full ES system.</span></span>

<span data-ttu-id="a3212-162">이미 관계형 데이터베이스를 사용하고 있는 경우 트랜잭션 테이블을 사용하여 통합 이벤트를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-162">If you are already using a relational database, you can use a transactional table to store integration events.</span></span> <span data-ttu-id="a3212-163">응용 프로그램에서 원자성을 달성하려면 로컬 트랜잭션을 기반으로 하는 2단계 프로세스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-163">To achieve atomicity in your application, you use a two-step process based on local transactions.</span></span> <span data-ttu-id="a3212-164">기본적으로 IntegrationEvent 테이블은 도메인 엔터티가 있는 데이터베이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-164">Basically, you have an IntegrationEvent table in the same database where you have your domain entities.</span></span> <span data-ttu-id="a3212-165">이 테이블은 원자성 달성을 위한 보험과 같기 때문에 사용자는 도메인 데이터를 커밋하는 대상 트랜잭션과 동일한 트랜잭션에 지속된 통합 이벤트를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-165">That table works as an insurance for achieving atomicity so that you include persisted integration events into the same transactions that are committing your domain data.</span></span>

<span data-ttu-id="a3212-166">단계별 프로세스는 다음과 같습니다. 응용 프로그램이 로컬 데이터베이스 트랜잭션을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-166">Step by step, the process goes like this: the application begins a local database transaction.</span></span> <span data-ttu-id="a3212-167">그런 다음, 도메인 엔터티의 상태를 업데이트하고 통합 이벤트 테이블로 이벤트를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-167">It then updates the state of your domain entities and inserts an event into the integration event table.</span></span> <span data-ttu-id="a3212-168">마지막으로 트랜잭션을 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-168">Finally, it commits the transaction.</span></span> <span data-ttu-id="a3212-169">그러면 원하는 원자성을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-169">You get the desired atomicity.</span></span>

<span data-ttu-id="a3212-170">이벤트 게시 단계를 구현할 경우 선택권이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-170">When implementing the steps of publishing the events, you have these choices:</span></span>

-   <span data-ttu-id="a3212-171">트랜잭션을 커밋한 직후 통합 이벤트를 게시하고 다른 로컬 트랜잭션을 사용하여 게시 중인 테이블에서 이벤트를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-171">Publish the integration event right after committing the transaction and use another local transaction to mark the events in the table as being published.</span></span> <span data-ttu-id="a3212-172">그런 다음, 원격 마이크로 서비스의 문제가 발생할 경우에 대비해 통합 이벤트를 추적하기 위한 아티팩트로 테이블을 사용하고 저장된 통합 이벤트를 기준으로 보상 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-172">Then, use the table just as an artifact to track the integration events in case of issues in the remote microservices, and perform compensatory actions based on the stored integration events.</span></span>

-   <span data-ttu-id="a3212-173">테이블을 일종의 큐로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-173">Use the table as a kind of queue.</span></span> <span data-ttu-id="a3212-174">별도의 응용 프로그램 스레드 또는 프로세스가 통합 이벤트 테이블을 쿼리하고 이벤트 버스로 이벤트를 게시한 다음, 로컬 트랜잭션을 사용하여 이벤트가 게시된 것으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-174">A separate application thread or process queries the integration event table, publishes the events to the event bus, and then uses a local transaction to mark the events as published.</span></span>

<span data-ttu-id="a3212-175">그림 8-22는 첫 번째 방식의 아키텍처입니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-175">Figure 8-22 shows the architecture for the first of these approaches.</span></span>

![](./media/image23.png)

<span data-ttu-id="a3212-176">**그림 8-22**.</span><span class="sxs-lookup"><span data-stu-id="a3212-176">**Figure 8-22**.</span></span> <span data-ttu-id="a3212-177">이벤트 버스로 이벤트를 게시할 경우 원자성</span><span class="sxs-lookup"><span data-stu-id="a3212-177">Atomicity when publishing events to the event bus</span></span>

<span data-ttu-id="a3212-178">그림 8-22에서 설명하는 방식은 게시된 통합 서비스의 성공 여부를 검사 및 확인하는 추가 작업자 마이크로 서비스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-178">The approach illustrated in Figure 8-22 is missing an additional worker microservice that is in charge of checking and confirming the success of the published integration events.</span></span> <span data-ttu-id="a3212-179">실패 시 해당 추가 검사기 작업자 마이크로 서비스는 테이블에서 이벤트를 읽고 다시 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-179">In case of failure, that additional checker worker microservice can read events from the table and republish them.</span></span>

<span data-ttu-id="a3212-180">두 번째 방식에서는 EventLog 테이블을 큐로 사용하고 언제나 작업자 마이크로 서비스를 사용해 메시지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-180">About the second approach: you use the EventLog table as a queue and always use a worker microservice to publish the messages.</span></span> <span data-ttu-id="a3212-181">이 경우 프로세스는 그림 8-23과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-181">In that case, the process is like that shown in Figure 8-23.</span></span> <span data-ttu-id="a3212-182">이 프로세스에는 추가 마이크로 서비스가 있으며 이벤트를 게시할 때 테이블은 단일 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-182">This shows an additional microservice, and the table is the single source when publishing events.</span></span>

![](./media/image24.png)

<span data-ttu-id="a3212-183">**그림 8-23**.</span><span class="sxs-lookup"><span data-stu-id="a3212-183">**Figure 8-23**.</span></span> <span data-ttu-id="a3212-184">작업자 마이크로 서비스를 사용하여 이벤트 버스로 이벤트를 게시할 경우 원자성</span><span class="sxs-lookup"><span data-stu-id="a3212-184">Atomicity when publishing events to the event bus with a worker microservice</span></span>

<span data-ttu-id="a3212-185">간단한 설명을 위해 eShopOnContainers 샘플은 첫 번째 방식(추가 프로세스 또는 검사기 마이크로 서비스가 없음)과 이벤트 버스를 사용하는 경우를 가정했습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-185">For simplicity, the eShopOnContainers sample uses the first approach (with no additional processes or checker microservices) plus the event bus.</span></span> <span data-ttu-id="a3212-186">하지만 eShopOnContainers는 발생 가능한 모든 실패 케이스를 처리하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-186">However, the eShopOnContainers is not handling all possible failure cases.</span></span> <span data-ttu-id="a3212-187">클라우드로 배포하는 실제 응용 프로그램에서는 언젠가 문제가 발생한다는 사실을 감안하고 이러한 검사 및 재전송 논리를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-187">In a real application deployed to the cloud, you must embrace the fact that issues will arise eventually, and you must implement that check and resend logic.</span></span> <span data-ttu-id="a3212-188">테이블을 큐로 사용하는 방식은 이벤트를 이벤트 버스를 통해 게시할 때 해당 테이블이 이벤트의 단일 소스인 경우 첫 번째 방식보다 훨씬 효과적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-188">Using the table as a queue can be more effective than the first approach if you have that table as a single source of events when publishing them through the event bus.</span></span>

### <a name="implementing-atomicity-when-publishing-integration-events-through-the-event-bus"></a><span data-ttu-id="a3212-189">이벤트 버스를 통해 통합 이벤트를 게시할 경우 원자성 구현</span><span class="sxs-lookup"><span data-stu-id="a3212-189">Implementing atomicity when publishing integration events through the event bus</span></span>

<span data-ttu-id="a3212-190">다음 코드는 복수의 DbContext 개체가 포함된 단일 트랜잭션을 만드는 방법을 보여줍니다. 첫 번째 컨텍스트는 업데이트되는 원본 데이터와 관련되어 있고 두 번째 컨텍스트는 IntegrationEventLog 테이블과 관련되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-190">The following code shows how you can create a single transaction involving multiple DbContext objects—one context related to the original data being updated, and the second context related to the IntegrationEventLog table.</span></span>

<span data-ttu-id="a3212-191">단, 아래 예제 코드의 트랜잭션은 코드를 실행할 때 데이터베이스 접속에 문제가 있을 경우 복원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-191">Note that the transaction in the example code below will not be resilient if connections to the database have any issue at the time when the code is running.</span></span> <span data-ttu-id="a3212-192">이러한 상황은 Azure SQL DB와 같이 서버 간 데이터베이스를 이동할 수 있는 클라우드 기반 시스템에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-192">This can happen in cloud-based systems like Azure SQL DB, which might move databases across servers.</span></span> <span data-ttu-id="a3212-193">복수 컨텍스트에 걸쳐 복원 가능한 트랜잭션을 구현하는 방법은 이 가이드의 뒷부분에 나오는 [복원 엔터티 프레임워크 코어 SQL 접속 구현](#implementing_resilient_EFCore_SQL_conns) 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a3212-193">For implementing resilient transactions across multiple contexts, see the [Implementing resilient Entity Framework Core SQL connections](#implementing_resilient_EFCore_SQL_conns) section later in this guide.</span></span>

<span data-ttu-id="a3212-194">다음 예는 명확한 설명을 위해 단일 코드로 전체 프로세스를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-194">For clarity, the following example shows the whole process in a single piece of code.</span></span> <span data-ttu-id="a3212-195">하지만 eShopOnContainers 구현은 실제로 리팩터링되었으며 이 논리를 복수의 클래스로 나누어 쉽게 관리할 수 있도록 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-195">However, the eShopOnContainers implementation is actually refactored and split this logic into multiple classes so it is easier to maintain.</span></span>

```csharp
// Update Product from the Catalog microservice
//
public async Task<IActionResult> UpdateProduct([FromBody]CatalogItem productToUpdate) 
{
  var catalogItem = 
       await _catalogContext.CatalogItems.SingleOrDefaultAsync(i => i.Id == 
                                                               productToUpdate.Id); 
  if (catalogItem == null) return NotFound();

  bool raiseProductPriceChangedEvent = false; 
  IntegrationEvent priceChangedEvent = null; 

  if (catalogItem.Price != productToUpdate.Price) 
          raiseProductPriceChangedEvent = true; 

  if (raiseProductPriceChangedEvent) // Create event if price has changed
  {
      var oldPrice = catalogItem.Price; 
      priceChangedEvent = new ProductPriceChangedIntegrationEvent(catalogItem.Id,
                                                                  productToUpdate.Price, 
                                                                  oldPrice); 
  }
  // Update current product
  catalogItem = productToUpdate; 

  // Just save the updated product if the Product's Price hasn't changed.
  if !(raiseProductPriceChangedEvent) 
  {
      await _catalogContext.SaveChangesAsync();
  }
  else  // Publish to event bus only if product price changed
  {
        // Achieving atomicity between original DB and the IntegrationEventLog 
        // with a local transaction
        using (var transaction = _catalogContext.Database.BeginTransaction())
        {
           _catalogContext.CatalogItems.Update(catalogItem); 
           await _catalogContext.SaveChangesAsync();

           // Save to EventLog only if product price changed
           if(raiseProductPriceChangedEvent) 
               await _integrationEventLogService.SaveEventAsync(priceChangedEvent); 

           transaction.Commit();
        }   

      // Publish the intergation event through the event bus
      _eventBus.Publish(priceChangedEvent); 

      integrationEventLogService.MarkEventAsPublishedAsync(
                                                priceChangedEvent); 
  }

  return Ok();
}

```

<span data-ttu-id="a3212-196">ProductPriceChangedIntegrationEvent 통합 이벤트가 생성된 후 원본 도메인 작업을 저장하는(카탈로그 항목 업데이트) 트랜잭션은 EventLog 테이블에 이벤트의 지속성을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-196">After the ProductPriceChangedIntegrationEvent integration event is created, the transaction that stores the original domain operation (update the catalog item) also includes the persistence of the event in the EventLog table.</span></span> <span data-ttu-id="a3212-197">이로써 단일 트랜잭션이 되며 언제든지 이벤트 메시지가 전송되었는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-197">This makes it a single transaction, and you will always be able to check whether event messages were sent.</span></span>

<span data-ttu-id="a3212-198">이벤트 로그 테이블은 동일 데이터베이스에 대한 로컬 트랜잭션을 사용하여 원본 데이터베이스 작업에 따라 하나의 큰 단위로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-198">The event log table is updated atomically with the original database operation, using a local transaction against the same database.</span></span> <span data-ttu-id="a3212-199">작업이 하나라도 실패할 경우 예외가 발생하고 트랜잭션은 임의의 완료 작업으로 롤백되면서 도메인 작업과 전송된 이벤트 메시지 간 일관성을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-199">If any of the operations fail, an exception is thrown and the transaction rolls back any completed operation, thus maintaining consistency between the domain operations and the event messages sent.</span></span>

### <a name="receiving-messages-from-subscriptions-event-handlers-in-receiver-microservices"></a><span data-ttu-id="a3212-200">구독에서 메시지 수신: 수신자 마이크로 서비스의 이벤트 처리기</span><span class="sxs-lookup"><span data-stu-id="a3212-200">Receiving messages from subscriptions: event handlers in receiver microservices</span></span>

<span data-ttu-id="a3212-201">이벤트 구독 논리 이외에도, 통합 이벤트 처리기의 내부 코드를 구현해야 합니다(콜백 메서드와 유사).</span><span class="sxs-lookup"><span data-stu-id="a3212-201">In addition to the event subscription logic, you need to implement the internal code for the integration event handlers (like a callback method).</span></span> <span data-ttu-id="a3212-202">이벤트 처리기에서는 특정 유형의 이벤트 메시지를 수신 및 처리할 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-202">The event handler is where you specify where the event messages of a certain type will be received and processed.</span></span>

<span data-ttu-id="a3212-203">이벤트 핸들러는 가장 먼저 이벤트 버스로부터 이벤트 인스턴스를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-203">An event handler first receives an event instance from the event bus.</span></span> <span data-ttu-id="a3212-204">그런 다음, 해당 통합 이벤트와 관련하여 처리할 구성 요소를 찾아 수신자 마이크로 서비스의 상태 변경으로 이벤트를 전파 및 지속합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-204">Then it locates the component to be processed related to that integration event, propagating and persisting the event as a change in state in the receiver microservice.</span></span> <span data-ttu-id="a3212-205">예를 들어 카탈로그 마이크로 서비스에서 ProductPriceChanged 이벤트가 발생할 경우 해당 이벤트는 다음 코드와 같이 장바구니 마이크로 서비스에서 처리된 후 이 수신자 장바구니 마이크로 서비스에서도 상태를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-205">For example, if a ProductPriceChanged event originates in the catalog microservice, it is handled in the basket microservice and changes the state in this receiver basket microservice as well, as shown in the following code.</span></span>

```csharp
namespace Microsoft.eShopOnContainers.Services.Basket.API.IntegrationEvents.EventHandling
{
    public class ProductPriceChangedIntegrationEventHandler :
        IIntegrationEventHandler<ProductPriceChangedIntegrationEvent>
    {
        private readonly IBasketRepository _repository;

        public ProductPriceChangedIntegrationEventHandler(
            IBasketRepository repository)
        {
            _repository = repository;
        }

        public async Task Handle(ProductPriceChangedIntegrationEvent @event)
        {
            var userIds = await _repository.GetUsers();
            foreach (var id in userIds)
            {
                var basket = await _repository.GetBasket(id);
                await UpdatePriceInBasketItems(@event.ProductId, @event.NewPrice, basket);
            }
        }

        private async Task UpdatePriceInBasketItems(int productId, decimal newPrice,
            CustomerBasket basket)
        {
            var itemsToUpdate = basket?.Items?.Where(x => int.Parse(x.ProductId) ==
                productId).ToList();
            if (itemsToUpdate != null)
            {
                foreach (var item in itemsToUpdate)
                {
                    if(item.UnitPrice != newPrice)
                    {
                        var originalPrice = item.UnitPrice;
                        item.UnitPrice = newPrice;
                        item.OldUnitPrice = originalPrice;
                    }
                }
                await _repository.UpdateBasket(basket);
            }
        }
    }
}
```

<span data-ttu-id="a3212-206">이벤트 처리기는 제품이 존재하는 장바구니 인스턴스가 있는지 여부를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-206">The event handler needs to verify whether the product exists in any of the basket instances.</span></span> <span data-ttu-id="a3212-207">이벤트 처리기는 각각의 관련 장바구니 라인 품목의 품목 가격을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-207">It also updates the item price for each related basket line item.</span></span> <span data-ttu-id="a3212-208">마지막으로 그림 8-24와 같이 사용자에게 가격 변동에 대해 표시할 알림을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-208">Finally, it creates an alert to be displayed to the user about the price change, as shown in Figure 8-24.</span></span>

![](./media/image25.png)

<span data-ttu-id="a3212-209">**그림 8-24**.</span><span class="sxs-lookup"><span data-stu-id="a3212-209">**Figure 8-24**.</span></span> <span data-ttu-id="a3212-210">통합 이벤트에서 전달한 장바구니 내 품목 가격 변동 표시</span><span class="sxs-lookup"><span data-stu-id="a3212-210">Displaying an item price change in a basket, as communicated by integration events</span></span>

## <a name="idempotency-in-update-message-events"></a><span data-ttu-id="a3212-211">업데이트 메시지 이벤트의 멱등성</span><span class="sxs-lookup"><span data-stu-id="a3212-211">Idempotency in update message events</span></span>

<span data-ttu-id="a3212-212">업데이트 메시지 이벤트에서 중요한 점은 통신의 임의 지점에서 문제가 발생할 경우 메시지를 재시도하도록 해야 한다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-212">An important aspect of update message events is that a failure at any point in the communication should cause the message to be retried.</span></span> <span data-ttu-id="a3212-213">그렇지 않을 경우 백그라운드 작업이 이미 게시된 이벤트를 게시하려고 하여 경합 상태가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-213">Otherwise a background task might try to publish an event that has already been published, creating a race condition.</span></span> <span data-ttu-id="a3212-214">업데이트가 한 번만 전송되도록 하거나 중복 여부를 감지해 폐기하고 하나의 응답만 회신하는 데 충분한 정보를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-214">You need to make sure that the updates are either idempotent or that they provide enough information to ensure that you can detect a duplicate, discard it, and send back only one response.</span></span>

<span data-ttu-id="a3212-215">앞에서 언급했듯이, 멱등성이란 결과를 바꾸지 않고 작업을 여러 번 수행할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-215">As noted earlier, idempotency means that an operation can be performed multiple times without changing the result.</span></span> <span data-ttu-id="a3212-216">통신 이벤트와 같은 메시징 환경에서는 수신자 마이크로 서비스의 결과를 바꾸지 않고 이벤트를 여러 번 전달할 수 있을 경우 이벤트에 멱등성이 있다고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-216">In a messaging environment, as when communicating events, an event is idempotent if it can be delivered multiple times without changing the result for the receiver microservice.</span></span> <span data-ttu-id="a3212-217">멱등성은 이벤트 자체의 특성 때문에 또는 시스템이 이벤트를 처리하는 방식 때문에 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-217">This may be necessary because of the nature of the event itself, or because of the way the system handles the event.</span></span> <span data-ttu-id="a3212-218">메시지 멱등성은 이벤트 버스 패턴을 구현하는 응용 프로그램뿐만 아니라 메시징을 사용하는 모든 응용 프로그램에서 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-218">Message idempotency is important in any application that uses messaging, not just in applications that implement the event bus pattern.</span></span>

<span data-ttu-id="a3212-219">예를 들어 테이블에 데이터가 없을 경우에만 테이블에 해당 데이터를 삽입하는 SQL 문은 멱등성 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-219">An example of an idempotent operation is a SQL statement that inserts data into a table only if that data is not already in the table.</span></span> <span data-ttu-id="a3212-220">해당 삽입 SQL 문을 몇 번 수행하는가는 중요하지 않으며 테이블에 해당 데이터가 포함된다는 결과는 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-220">It does not matter how many times you run that insert SQL statement; the result will be the same—the table will contain that data.</span></span> <span data-ttu-id="a3212-221">이와 같은 멱등성은 메시지가 전송되어 두 번 이상 처리될 수 있는 경우 메시지를 처리하는 데 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-221">Idempotency like this can also be necessary when dealing with messages if the messages could potentially be sent and therefore processed more than once.</span></span> <span data-ttu-id="a3212-222">예를 들어 발신자가 정확히 동일한 메시지를 두 번 이상 전송하도록 하는 재시도 논리의 경우 멱등성인지 여부를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-222">For instance, if retry logic causes a sender to send exactly the same message more than once, you need to make sure that it is idempotent.</span></span>

<span data-ttu-id="a3212-223">멱등성 메시지를 설계할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-223">It is possible to design idempotent messages.</span></span> <span data-ttu-id="a3212-224">예를 들어 "제품 가격에 \$5 추가" 대신 "제품 가격을 \$25로 설정"이라는 이벤트를 만드는 경우를 가정하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-224">For example, you can create an event that says "set the product price to \$25" instead of "add \$5 to the product price."</span></span> <span data-ttu-id="a3212-225">첫 번째 메시지는 여러 번 처리해도 안전하며 결과는 동일해집니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-225">You could safely process the first message any number of times and the result will be the same.</span></span> <span data-ttu-id="a3212-226">두 번째 메시지는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-226">That is not true for the second message.</span></span> <span data-ttu-id="a3212-227">하지만 첫 번째 이벤트의 경우에도 시스템에서 새로운 가격 변동 이벤트를 전송해 새 가격을 덮어쓸 수 있기 때문에 첫 번째 이벤트를 처리하지 않아야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-227">But even in the first case, you might not want to process the first event, because the system could also have sent a newer price-change event and you would be overwriting the new price.</span></span>

<span data-ttu-id="a3212-228">다른 예를 들면 주문 완료 이벤트를 여러 구독자에게 전파하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-228">Another example might be an order-completed event being propagated to multiple subscribers.</span></span> <span data-ttu-id="a3212-229">동일한 주문 완료 이벤트에 대해 중복된 메시지 이벤트가 있는 경우에도 주문 정보는 다른 시스템에서 한 번만 업데이트하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-229">It is important that order information be updated in other systems just once, even if there are duplicated message events for the same order-completed event.</span></span>

<span data-ttu-id="a3212-230">각 이벤트를 수신자당 한 번만 처리하는 논리를 만들 수 있도록 이벤트당 일종의 ID를 만드는 것이 편리합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-230">It is convenient to have some kind of identity per event so that you can create logic that enforces that each event is processed only once per receiver.</span></span>

<span data-ttu-id="a3212-231">일부 메시지 처리는 본질적으로 멱등성입니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-231">Some message processing is inherently idempotent.</span></span> <span data-ttu-id="a3212-232">예를 들어 시스템에서 이미지 썸네일을 생성할 경우 생성된 썸네일에 대한 메시지가 몇 번 처리되었는가는 중요하지 않을 수 있습니다. 결과는 썸네일이 생성되었고 언제나 동일하다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-232">For example, if a system generates image thumbnails, it might not matter how many times the message about the generated thumbnail is processed; the outcome is that the thumbnails are generated and they are the same every time.</span></span> <span data-ttu-id="a3212-233">반면 신용카드 청구를 위한 결제 게이트를 호출하는 등의 작업은 전혀 멱등성이 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-233">On the other hand, operations such as calling a payment gateway to charge a credit card may not be idempotent at all.</span></span> <span data-ttu-id="a3212-234">이 경우 메시지를 여러 번 처리함으로써 기대하는 효과를 얻을 수 있는지 여부를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-234">In these cases, you need to ensure that processing a message multiple times has the effect that you expect.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="a3212-235">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="a3212-235">Additional resources</span></span>

-   <span data-ttu-id="a3212-236">**메시지 멱등성 준수** (이 페이지의 부제목) [*https://msdn.microsoft.com/library/jj591565.aspx*](https://msdn.microsoft.com/library/jj591565.aspx)</span><span class="sxs-lookup"><span data-stu-id="a3212-236">**Honoring message idempotency** (subhead on this page) [*https://msdn.microsoft.com/library/jj591565.aspx*](https://msdn.microsoft.com/library/jj591565.aspx)</span></span>

## <a name="deduplicating-integration-event-messages"></a><span data-ttu-id="a3212-237">통합 이벤트 메시지 중복 제거</span><span class="sxs-lookup"><span data-stu-id="a3212-237">Deduplicating integration event messages</span></span>

<span data-ttu-id="a3212-238">메시지 이벤트가 다른 수준의 구독자별로 한 번만 전송 및 처리되었는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-238">You can make sure that message events are sent and processed just once per subscriber at different levels.</span></span> <span data-ttu-id="a3212-239">한 가지 방법은 사용하고 있는 메시징 인프라에서 제공하는 중복 제거 기능을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-239">One way is to use a deduplication feature offered by the messaging infrastructure you are using.</span></span> <span data-ttu-id="a3212-240">또한 대상 마이크로 서비스에 사용자 지정 논리를 구현할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-240">Another is to implement custom logic in your destination microservice.</span></span> <span data-ttu-id="a3212-241">전송 수준 및 응용 프로그램 수준에서 검증하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-241">Having validations at both the transport level and the application level is your best bet.</span></span>

### <a name="deduplicating-message-events-at-the-eventhandler-level"></a><span data-ttu-id="a3212-242">EventHandler 수준에서 메시지 이벤트 중복 제거</span><span class="sxs-lookup"><span data-stu-id="a3212-242">Deduplicating message events at the EventHandler level</span></span>

<span data-ttu-id="a3212-243">수신자에서 이벤트가 한 번만 처리되었는지 여부를 확인하는 한 가지 방법은 이벤트 처리기에서 메시지 이벤트를 처리할 때 특정 논리를 구현하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-243">One way to make sure that an event is processed just once by any receiver is by implementing certain logic when processing the message events in event handlers.</span></span> <span data-ttu-id="a3212-244">예를 들어 OrdersController 클래스의 [소스 코드](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Controllers/OrdersController.cs)에 나와 있는 대로 eShopOnContainers 응용 프로그램에서 CreateOrderCommand 명령을 수신할 때 사용된 방식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-244">For example, that is the approach used in the eShopOnContainers application, as you can see in the [source code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Controllers/OrdersController.cs) of the OrdersController class when it receives a CreateOrderCommand command.</span></span> <span data-ttu-id="a3212-245">(이 경우 메시지 기반 명령이 아닌 HTTP 요청 명령을 사용하지만 메시지 기반 명령을 멱등성으로 설정하는 데 필요한 논리는 유사합니다.)</span><span class="sxs-lookup"><span data-stu-id="a3212-245">(In this case we use an HTTP request command, not a message-based command, but the logic you need to make a message-based command idempotent is similar.)</span></span>

### <a name="deduplicating-messages-when-using-rabbitmq"></a><span data-ttu-id="a3212-246">RabbitMQ 사용 시 메시지 중복 제거</span><span class="sxs-lookup"><span data-stu-id="a3212-246">Deduplicating messages when using RabbitMQ</span></span>

<span data-ttu-id="a3212-247">간헐적 네트워크 장애가 발생할 경우에는 메시지가 중복될 수 있으며 메시지 수신자는 이러한 중복 메시지를 처리할 준비가 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-247">When intermittent network failures happen, messages can be duplicated, and the message receiver must be ready to handle these duplicated messages.</span></span> <span data-ttu-id="a3212-248">가능할 경우 수신자는 메시지를 멱등 방식으로 처리해야 하며, 이 방식은 중복 제거를 통해 명시적으로 처리하는 방식보다 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-248">If possible, receivers should handle messages in an idempotent way, which is better than explicitly handling them with deduplication.</span></span>

<span data-ttu-id="a3212-249">[RabbitMQ 문서](https://www.rabbitmq.com/reliability.html#consumer)에 따르면, 메시지가 소비자에게 전달된 다음, 큐에 다시 추가되는 경우(예를 들어 소비자 접속이 끊기기 전 인식되지 않았기 때문에) RabbitMQ는 메시지가 (동일한 소비자 또는 다른 소비자에게) 다시 전달될 때 해당 메시지에 재전달 플래그를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-249">According to the [RabbitMQ documentation](https://www.rabbitmq.com/reliability.html#consumer), “If a message is delivered to a consumer and then requeued (because it was not acknowledged before the consumer connection dropped, for example) then RabbitMQ will set the redelivered flag on it when it is delivered again (whether to the same consumer or a different one).</span></span>

<span data-ttu-id="a3212-250">"재전달" 플래그가 설정된 경우에는 메시지가 이미 처리되었을 수 있으므로 수신자를 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-250">If the “redelivered” flag is set, the receiver must take that into account, because the message might already have been processed.</span></span> <span data-ttu-id="a3212-251">하지만 메시지가 처리된다는 보장은 없으며 메시지가 메시지 브로커에서 나온 이후 네트워크 문제 등의 이유로 수신자에게 도달하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-251">But that is not guaranteed; the message might never have reached the receiver after it left the message broker, perhaps because of network issues.</span></span> <span data-ttu-id="a3212-252">반면, "재전달" 플래그가 설정되지 않은 경우 메시지는 확실히 두 번 이상 전송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-252">On the other hand, if the “redelivered” flag is not set, it is guaranteed that the message has not been sent more than once.</span></span> <span data-ttu-id="a3212-253">따라서 수신자는 메시지에 "재배달" 플래그가 설정된 경우에만 메시지를 중복 제거하거나 멱등 방식으로 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-253">Therefore, the receiver needs to deduplicate messages or process messages in an idempotent way only if the “redelivered” flag is set in the message.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="a3212-254">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="a3212-254">Additional resources</span></span>

-   <span data-ttu-id="a3212-255">**Forked eShopOnContainers using NServiceBus (Particular Software)**
    [*http://go.particular.net/eShopOnContainers*](http://go.particular.net/eShopOnContainers)</span><span class="sxs-lookup"><span data-stu-id="a3212-255">**Forked eShopOnContainers using NServiceBus (Particular Software)**
[*http://go.particular.net/eShopOnContainers*](http://go.particular.net/eShopOnContainers)</span></span>

-   <span data-ttu-id="a3212-256">**Event Driven Messaging**
    [*http://soapatterns.org/design\_patterns/event\_driven\_messaging*](http://soapatterns.org/design_patterns/event_driven_messaging)</span><span class="sxs-lookup"><span data-stu-id="a3212-256">**Event Driven Messaging**
[*http://soapatterns.org/design\_patterns/event\_driven\_messaging*](http://soapatterns.org/design_patterns/event_driven_messaging)</span></span>

-   <span data-ttu-id="a3212-257">**Jimmy Bogard. Refactoring Towards Resilience: Evaluating Coupling**
    [*https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/*](https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/)</span><span class="sxs-lookup"><span data-stu-id="a3212-257">**Jimmy Bogard. Refactoring Towards Resilience: Evaluating Coupling**
[*https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/*](https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/)</span></span>

-   <span data-ttu-id="a3212-258">**Publish-Subscribe channel**
    [*http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html*](http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html)</span><span class="sxs-lookup"><span data-stu-id="a3212-258">**Publish-Subscribe channel**
[*http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html*](http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html)</span></span>

-   <span data-ttu-id="a3212-259">**Communicating Between Bounded Contexts**
    [*https://msdn.microsoft.com/library/jj591572.aspx*](https://msdn.microsoft.com/library/jj591572.aspx)</span><span class="sxs-lookup"><span data-stu-id="a3212-259">**Communicating Between Bounded Contexts**
[*https://msdn.microsoft.com/library/jj591572.aspx*](https://msdn.microsoft.com/library/jj591572.aspx)</span></span>

-   <span data-ttu-id="a3212-260">**Eventual Consistency**
    [*https://en.wikipedia.org/wiki/Eventual\_consistency*](https://en.wikipedia.org/wiki/Eventual_consistency)</span><span class="sxs-lookup"><span data-stu-id="a3212-260">**Eventual Consistency**
[*https://en.wikipedia.org/wiki/Eventual\_consistency*](https://en.wikipedia.org/wiki/Eventual_consistency)</span></span>

-   <span data-ttu-id="a3212-261">**Philip Brown. Strategies for Integrating Bounded Contexts**
    [*http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/*](http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/)</span><span class="sxs-lookup"><span data-stu-id="a3212-261">**Philip Brown. Strategies for Integrating Bounded Contexts**
[*http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/*](http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/)</span></span>

-   <span data-ttu-id="a3212-262">**Chris Richardson. Developing Transactional Microservices Using Aggregates, Event Sourcing and CQRS - Part 2**
    [*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson)</span><span class="sxs-lookup"><span data-stu-id="a3212-262">**Chris Richardson. Developing Transactional Microservices Using Aggregates, Event Sourcing and CQRS - Part 2**
[*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson)</span></span>

-   <span data-ttu-id="a3212-263">**Chris Richardson. Event Sourcing pattern**
    [*http://microservices.io/patterns/data/event-sourcing.html*](http://microservices.io/patterns/data/event-sourcing.html)</span><span class="sxs-lookup"><span data-stu-id="a3212-263">**Chris Richardson. Event Sourcing pattern**
[*http://microservices.io/patterns/data/event-sourcing.html*](http://microservices.io/patterns/data/event-sourcing.html)</span></span>

-   <span data-ttu-id="a3212-264">**Introducing Event Sourcing**
    [*https://msdn.microsoft.com/library/jj591559.aspx*](https://msdn.microsoft.com/library/jj591559.aspx)</span><span class="sxs-lookup"><span data-stu-id="a3212-264">**Introducing Event Sourcing**
[*https://msdn.microsoft.com/library/jj591559.aspx*](https://msdn.microsoft.com/library/jj591559.aspx)</span></span>

-   <span data-ttu-id="a3212-265">**Event Store database**.</span><span class="sxs-lookup"><span data-stu-id="a3212-265">**Event Store database**.</span></span> <span data-ttu-id="a3212-266">공식 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="a3212-266">Official site.</span></span>
    [<span data-ttu-id="a3212-267">*https://geteventstore.com/*</span><span class="sxs-lookup"><span data-stu-id="a3212-267">*https://geteventstore.com/*</span></span>](https://geteventstore.com/)

-   <span data-ttu-id="a3212-268">**Patrick Nommensen. Event-Driven Data Management for Microservices**
    *<https://dzone.com/articles/event-driven-data-management-for-microservices-1> *</span><span class="sxs-lookup"><span data-stu-id="a3212-268">**Patrick Nommensen. Event-Driven Data Management for Microservices**
*<https://dzone.com/articles/event-driven-data-management-for-microservices-1> *</span></span>

-   <span data-ttu-id="a3212-269">**The CAP Theorem**
    [*https://en.wikipedia.org/wiki/CAP\_theorem*](https://en.wikipedia.org/wiki/CAP_theorem)</span><span class="sxs-lookup"><span data-stu-id="a3212-269">**The CAP Theorem**
[*https://en.wikipedia.org/wiki/CAP\_theorem*](https://en.wikipedia.org/wiki/CAP_theorem)</span></span>

-   <span data-ttu-id="a3212-270">**What is CAP Theorem?**
    [*https://www.quora.com/What-Is-CAP-Theorem-1*](https://www.quora.com/What-Is-CAP-Theorem-1)</span><span class="sxs-lookup"><span data-stu-id="a3212-270">**What is CAP Theorem?**
[*https://www.quora.com/What-Is-CAP-Theorem-1*](https://www.quora.com/What-Is-CAP-Theorem-1)</span></span>

-   <span data-ttu-id="a3212-271">**Data Consistency Primer**
    [*https://msdn.microsoft.com/library/dn589800.aspx*](https://msdn.microsoft.com/library/dn589800.aspx)</span><span class="sxs-lookup"><span data-stu-id="a3212-271">**Data Consistency Primer**
[*https://msdn.microsoft.com/library/dn589800.aspx*](https://msdn.microsoft.com/library/dn589800.aspx)</span></span>

-   <span data-ttu-id="a3212-272">**Rick Saling. The CAP Theorem: Why “Everything is Different” with the Cloud and Internet**
    [*https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/*](https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/)</span><span class="sxs-lookup"><span data-stu-id="a3212-272">**Rick Saling. The CAP Theorem: Why “Everything is Different” with the Cloud and Internet**
[*https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/*](https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/)</span></span>

-   <span data-ttu-id="a3212-273">**Eric Brewer. CAP Twelve Years Later: How the "Rules" Have Changed**
    [*https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed*](https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed)</span><span class="sxs-lookup"><span data-stu-id="a3212-273">**Eric Brewer. CAP Twelve Years Later: How the "Rules" Have Changed**
[*https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed*](https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed)</span></span>

-   <span data-ttu-id="a3212-274">**Participating in External (DTC) Transactions** (MSMQ) [*https://msdn.microsoft.com/library/ms978430.aspx\#bdadotnetasync2\_topic3c*](https://msdn.microsoft.com/library/ms978430.aspx%23bdadotnetasync2_topic3c)</span><span class="sxs-lookup"><span data-stu-id="a3212-274">**Participating in External (DTC) Transactions** (MSMQ) [*https://msdn.microsoft.com/library/ms978430.aspx\#bdadotnetasync2\_topic3c*](https://msdn.microsoft.com/library/ms978430.aspx%23bdadotnetasync2_topic3c)</span></span>

-   <span data-ttu-id="a3212-275">**Azure Service Bus. Brokered Messaging: Duplicate Detection**
    [*https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25*](https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25)</span><span class="sxs-lookup"><span data-stu-id="a3212-275">**Azure Service Bus. Brokered Messaging: Duplicate Detection**
[*https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25*](https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25)</span></span>

-   <span data-ttu-id="a3212-276">**Reliability Guide** (RabbitMQ documentation) [*https://www.rabbitmq.com/reliability.html\#consumer*](https://www.rabbitmq.com/reliability.html%23consumer)</span><span class="sxs-lookup"><span data-stu-id="a3212-276">**Reliability Guide** (RabbitMQ documentation) [*https://www.rabbitmq.com/reliability.html\#consumer*](https://www.rabbitmq.com/reliability.html%23consumer)</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="a3212-277">[이전] (rabbitmq-event-bus-development-test-environment.md) [다음] (test-aspnet-core-services-web-apps.md)</span><span class="sxs-lookup"><span data-stu-id="a3212-277">[Previous] (rabbitmq-event-bus-development-test-environment.md) [Next] (test-aspnet-core-services-web-apps.md)</span></span>
