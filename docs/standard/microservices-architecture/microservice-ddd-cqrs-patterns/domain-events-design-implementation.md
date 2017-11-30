---
title: "도메인 이벤트입니다. 디자인 및 구현"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 도메인 이벤트, 디자인 및 구현"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 2d98b302be4ee72d8225526944fc3e41cbadcb5f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="domain-events-design-and-implementation"></a><span data-ttu-id="53638-105">도메인 이벤트: 설계 및 구현</span><span class="sxs-lookup"><span data-stu-id="53638-105">Domain events: design and implementation</span></span>

<span data-ttu-id="53638-106">도메인 이벤트를 사용 하 여 명시적으로 도메인 내에서 변경의 부작용을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-106">Use domain events to explicitly implement side effects of changes within your domain.</span></span> <span data-ttu-id="53638-107">다른 단어 및 DDD 용어를 사용 하 여 명시적으로 여러 집계에서 파생 작업을 구현 하 도메인 이벤트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-107">In other words, and using DDD terminology, use domain events to explicitly implement side effects across multiple aggregates.</span></span> <span data-ttu-id="53638-108">필요에 따라 확장성이 향상 하 고 데이터베이스 잠금에 영향을 덜 같은 도메인 내의 집계 간의 결과적 일관성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-108">Optionally, for better scalability and less impact in database locks, use eventual consistency between aggregates within the same domain.</span></span>

## <a name="what-is-a-domain-event"></a><span data-ttu-id="53638-109">도메인 이벤트는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="53638-109">What is a domain event?</span></span>

<span data-ttu-id="53638-110">이벤트는 과거에 발생 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="53638-110">An event is something that has happened in the past.</span></span> <span data-ttu-id="53638-111">도메인 이벤트 논리적으로 특정 도메인에서 발생 하는 것 이며, 하 알고 있어야 하 고 잠재적으로 반응 하는 동일한 도메인 (in process)의 다른 부분에서 원하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="53638-111">A domain event is, logically, something that happened in a particular domain, and something you want other parts of the same domain (in-process) to be aware of and potentially react to.</span></span>

<span data-ttu-id="53638-112">이벤트 도메인 중요 한 이점은 의도 하지 않은 도메인에서 발생 한 후 암시적으로 대신 명시적으로 나타낼 수는입니다.</span><span class="sxs-lookup"><span data-stu-id="53638-112">An important benefit of domain events is that side effects after something happened in a domain can be expressed explicitly instead of implicitly.</span></span> <span data-ttu-id="53638-113">어느 모든 작업 관련 비즈니스 태스크에이 오류가 발생할 수 있으므로 효과 일관성이 있어야 해당 하나 이상의 그 중입니다.</span><span class="sxs-lookup"><span data-stu-id="53638-113">Those side effects must be consistent so either all the operations related to the business task happen, or none of them.</span></span> <span data-ttu-id="53638-114">또한 도메인 이벤트는 동일한 도메인 안에 있는 클래스는 더 나은 분리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-114">In addition, domain events enable a better separation of concerns among classes within the same domain.</span></span>

<span data-ttu-id="53638-115">예를 들어 사용 중인 경우만 Entity Framework 및 엔터티 또는 짝수의 집계 사용 사례를 초래한 부작용 있어야 하는 경우, 하는 것은으로 구현 됩니다 결합 된 코드에는 암시적 개념 후 문제가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-115">For example, if you are just using just Entity Framework and entities or even aggregates, if there have to be side effects provoked by a use case, those will be implemented as an implicit concept in the coupled code after something happened.</span></span> <span data-ttu-id="53638-116">하지만 해당 코드를 표시 하는 경우 알지 못할 수도 있습니다 (부작용) 해당 코드는 기본 작업의 일부인 아니면 부작용 정말 그렇습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-116">But, if you just see that code, you might not know if that code (the side effect) is part of the main operation or if it really is a side effect.</span></span> <span data-ttu-id="53638-117">반면에 도메인 이벤트를 사용 하 여 명시적 이며 유비쿼터스 언어의 일부가 개념을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="53638-117">On the other hand, using domain events makes the concept explicit and part of the ubiquitous language.</span></span> <span data-ttu-id="53638-118">예를 들어, eShopOnContainers 응용 프로그램에서 주문을 만드는; 순서에 대 한 업데이트 또는 주문을 준비에서 될 때까지 사용자가 아닌 구매자 때문에 원래 사용자에 따라 구매자 집계를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="53638-118">For example, in the eShopOnContainers application, creating an order is not just about the order; it updates or creates a buyer aggregate based on the original user, because the user is not a buyer until there is an order in place.</span></span> <span data-ttu-id="53638-119">도메인 이벤트를 사용 하는 경우에 도메인 전문가 의해 제공 유비쿼터스 언어에 따라 해당 도메인 규칙을 명시적으로 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-119">If you use domain events, you can explicitly express that domain rule based in the ubiquitous language provided by the domain experts.</span></span>

<span data-ttu-id="53638-120">도메인 이벤트는 한 가지 중요 한 차이점 메시징 스타일 이벤트 일부 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-120">Domain events are somewhat similar to messaging-style events, with one important difference.</span></span> <span data-ttu-id="53638-121">실제 메시징, 메시지 큐, 메시지 브로커 또는 AMPQ를 사용 하 여 서비스 버스를 메시지가 항상 비동기적으로 보내고 프로세스 및 컴퓨터에서 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-121">With real messaging, message queuing, message brokers, or a service bus using AMPQ, a message is always sent asynchronously and communicated across processes and machines.</span></span> <span data-ttu-id="53638-122">여러 경계가 지정 된 컨텍스트, microservices, 또는 다른 응용 프로그램을 통합 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-122">This is useful for integrating multiple Bounded Contexts, microservices, or even different applications.</span></span> <span data-ttu-id="53638-123">그러나 도메인 이벤트에서 현재 실행 중인 도메인 작업 이벤트를 발생 하려면 되지만 같은 도메인 내에서 실행 되도록 모든 부작용을 원하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-123">However, with domain events, you want to raise an event from the domain operation you are currently running, but you want any side effects to occur within the same domain.</span></span>

<span data-ttu-id="53638-124">도메인 이벤트 및 해당 부작용 (트리거되는 작업 나중에 이벤트 처리기가 관리 되는) 거의 즉시 수행 해야 일반적으로-프로세스, 하 고 같은 도메인 내에서.</span><span class="sxs-lookup"><span data-stu-id="53638-124">The domain events and their side effects (the actions triggered afterwards that are managed by event handlers) should occur almost immediately, usually in-process, and within the same domain.</span></span> <span data-ttu-id="53638-125">따라서 동기 또는 비동기 도메인 이벤트 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-125">Thus, domain events could be synchronous or asynchronous.</span></span> <span data-ttu-id="53638-126">하지만 통합 이벤트 항상 되어야 비동기 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-126">Integration events, however, should always be asynchronous.</span></span>

## <a name="domain-events-versus-integration-events"></a><span data-ttu-id="53638-127">통합 이벤트와 도메인 이벤트</span><span class="sxs-lookup"><span data-stu-id="53638-127">Domain events versus integration events</span></span>

<span data-ttu-id="53638-128">도메인 및 통합 이벤트 동일한 작업에는 의미상으로: 일이 일어났는지 하는 것에 대 한 알림을 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-128">Semantically, domain and integration events are the same thing: notifications about something that just happened.</span></span> <span data-ttu-id="53638-129">그러나 해당 구현에는 달라 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-129">However, their implementation must be different.</span></span> <span data-ttu-id="53638-130">도메인 이벤트는 프로그램 메모리에 중재자 IoC 컨테이너 또는 다른 방법을 기반으로 구현할 수 있는 한 도메인 이벤트 발송자에 푸시된 정당한 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="53638-130">Domain events are just messages pushed to a domain event dispatcher, which could be implemented as an in-memory mediator based on an IoC container or any other method.</span></span>

<span data-ttu-id="53638-131">반면에 통합 이벤트의 목적은 커밋된 트랜잭션 및 추가 하위 시스템에 대 한 업데이트를 전파 하는 데이 든 상관 없이 다른 microservices, 경계가 지정 된 컨텍스트 또는 외부 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="53638-131">On the other hand, the purpose of integration events is to propagate committed transactions and updates to additional subsystems, whether they are other microservices, Bounded Contexts or even external applications.</span></span> <span data-ttu-id="53638-132">따라서 발생 해야 엔터티가 성공적으로 지속 되 면 이후 대부분의 시나리오에서 실패 하면 전체 작업이 되지 않도록 발생 한 시간에 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-132">Hence, they should occur only if the entity is successfully persisted, since in many scenarios if this fails, the entire operation effectively never happened.</span></span>

<span data-ttu-id="53638-133">또한 및로 언급 한 통합 이벤트를 기반으로 여러 microservices (다른 경계가 지정 된 컨텍스트의 경우) 또는 외부 시스템/응용 프로그램 간의 비동기 통신 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-133">In addition, and as mentioned, integration events must be based on asynchronous communication between multiple microservices (other Bounded Contexts) or even external systems/applications.</span></span> <span data-ttu-id="53638-134">따라서 이벤트 버스 인터페이스 간 프로세스를 허용 하 고 잠재적으로 원격 서비스 간의 통신에 분산 하는 일부 인프라가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-134">Thus, the event bus interface needs some infrastructure that allows inter-process and distributed communication between potentially remote services.</span></span> <span data-ttu-id="53638-135">상용 서비스 버스, 큐는 사서함으로 사용 되는 공유 데이터베이스 또는 다른 배포에 따라 수 하 고 이상적 기반된 메시징 시스템을 강제 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-135">It can be based on a commercial service bus, queues, a shared database used as a mailbox, or any other distributed and ideally push based messaging system.</span></span>

## <a name="domain-events-as-a-preferred-way-to-trigger-side-effects-across-multiple-aggregates-within-the-same-domain"></a><span data-ttu-id="53638-136">같은 도메인 내 여러 집계에서 부작용을 트리거할 수는 기본 방법으로 도메인 이벤트</span><span class="sxs-lookup"><span data-stu-id="53638-136">Domain events as a preferred way to trigger side effects across multiple aggregates within the same domain</span></span>

<span data-ttu-id="53638-137">집계 인스턴스 필요 하나 이상의 추가 집계에서 실행 되도록 추가 도메인 규칙 하나 관련 명령을 실행할 경우 디자인 하 고 도메인 이벤트에 의해 트리거될 이러한 부작용을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-137">If executing a command related to one aggregate instance requires additional domain rules to be run on one or more additional aggregates, you should design and implement those side effects to be triggered by domain events.</span></span> <span data-ttu-id="53638-138">그림 9-14에서 사용 하 여 표시 된 것 처럼 및 가장 중요 한 중 하나로 사용 사례, 같은 도메인 모델에 여러 집계 상태 변경 내용을 전파할 도메인 이벤트를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-138">As shown in Figure 9-14, and as one of the most important use cases, a domain event should be used to propagate state changes across multiple aggregates within the same domain model.</span></span>

![](./media/image15.png)

<span data-ttu-id="53638-139">**그림 9-14**합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-139">**Figure 9-14**.</span></span> <span data-ttu-id="53638-140">같은 도메인 내 여러 집계 간의 일관성을 유지 하려면 도메인 이벤트</span><span class="sxs-lookup"><span data-stu-id="53638-140">Domain events to enforce consistency between multiple aggregates within the same domain</span></span>

<span data-ttu-id="53638-141">그림에서 사용자가을 주문으로 시작할 때 OrderStarted 도메인 이벤트 CreateOrder 명령에서 제공 된 정보) (된 identity 마이크로 서비스에서 원래 사용자 정보에 따라 정렬 마이크로 서비스에서 구매자 개체 생성을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-141">In the figure, when the user initiates an order, the OrderStarted domain event triggers creation of a Buyer object in the ordering microservice, based on the original user info from the identity microservice (with information provided in the CreateOrder command).</span></span> <span data-ttu-id="53638-142">처음에 만들어질 때 도메인 이벤트 순서 집계에 의해 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53638-142">The domain event is generated by the order aggregate when it is created in the first place.</span></span>

<span data-ttu-id="53638-143">또는 집계 루트의 집계 (자식 엔터티)의 멤버에 의해 발생 한 이벤트에 대 한 구독을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-143">Alternately, you can have the aggregate root subscribed for events raised by members of its aggregates (child entities).</span></span> <span data-ttu-id="53638-144">예를 들어, 각 OrderItem 자식 엔터티에 항목 값이 특정 금액 보다 높은 경우 또는 제품 항목 크기 너무 높은 경우 이벤트를 발생 시키는 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-144">For instance, each OrderItem child entity can raise an event when the item price is higher than a specific amount, or when the product item amount is too high.</span></span> <span data-ttu-id="53638-145">집계 루트 해당 이벤트를 받을 전역 계산 또는 집계를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-145">The aggregate root can then receive those events and perform a global calculation or aggregation.</span></span>

<span data-ttu-id="53638-146">이 이벤트 기반 통신 집계; 내에서 직접 구현 되지 않았다는 것을 이해 하는 도메인 이벤트 처리기를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-146">It is important to understand that this event-based communication is not implemented directly within the aggregates; you need to implement domain event handlers.</span></span> <span data-ttu-id="53638-147">도메인 이벤트를 처리 하는 것은 응용 프로그램 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="53638-147">Handling the domain events is an application concern.</span></span> <span data-ttu-id="53638-148">도메인 모델 계층 해야 하는 도메인 논리에만 초점을 — 도메인 전문가 이해 하는 것, 처리기 및 부수적 지 속성 동작 저장소를 사용 하 여 같은 응용 프로그램 인프라 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-148">The domain model layer should only focus on the domain logic—things that a domain expert would understand, not application infrastructure like handlers and side-effect persistence actions using repositories.</span></span> <span data-ttu-id="53638-149">따라서 응용 프로그램 계층 수준에는 도메인 이벤트가 발생할 때 작업을 트리거하는 도메인 이벤트 처리기 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-149">Therefore, the application layer level is where you should have domain event handlers triggering actions when a domain event is raised.</span></span>

<span data-ttu-id="53638-150">수의 응용 프로그램 작업을 트리거할 도메인 이벤트도 사용할 수 있으며 더 중요 한 수를 늘리려면 해당 나중에 분리 된 방식으로 열려 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-150">Domain events can also be used to trigger any number of application actions, and what is more important, must be open to increase that number in the future in a decoupled way.</span></span> <span data-ttu-id="53638-151">예를 들어, 순서가 시작 되 면 알림 같은 응용 프로그램 동작을 발생 시 키도 또는 다른 집계에 해당 정보를 전파 하는 데 도메인 이벤트를 게시 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-151">For instance, when the order is started, you might want to publish a domain event to propagate that info to other aggregates or even to raise application actions like notifications.</span></span>

<span data-ttu-id="53638-152">중요 한 점은 열기 도메인 이벤트가 발생할 때 실행할 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="53638-152">The key point is the open number of actions to be executed when a domain event occurs.</span></span> <span data-ttu-id="53638-153">결국 동작 및 도메인 및 표준 응용 프로그램에 규칙은 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-153">Eventually, the actions and rules in the domain and application will grow.</span></span> <span data-ttu-id="53638-154">하지만 코드 "글 루"와 결합 된 경우 복잡성 또는 변경 내용이 있을 때 파생 작업이 작업 수 증가 합니다 (즉, 방금 C의 새로운 키워드를 사용 하 여 개체를 인스턴스화\#), 게 해야 할 때마다 새 동작을 추가 하는 데 필요한 다음 원본 코드를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-154">The complexity or number of side-effect actions when something happens will grow, but if your code were coupled with “glue” (that is, just instantiating objects with the new keyword in C\#), then every time you needed to add a new action you would need to change the original code.</span></span> <span data-ttu-id="53638-155">각 새 요구 사항으로 원래 코드 흐름을 변경 해야 하기 때문에 새로운 버그가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-155">This could result in new bugs, because with each new requirement you would need to change the original code flow.</span></span> <span data-ttu-id="53638-156">이 어긋납니다는 [열기/종결 됨 원칙](https://en.wikipedia.org/wiki/Open/closed_principle) 에서 [단색](https://en.wikipedia.org/wiki/SOLID_(object-oriented_design))합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-156">This goes against the [Open/Closed principle](https://en.wikipedia.org/wiki/Open/closed_principle) from [SOLID](https://en.wikipedia.org/wiki/SOLID_(object-oriented_design)).</span></span> <span data-ttu-id="53638-157">뿐만 아니라 작업을 조정 된 원본 클래스는 확장 및 증가 함에 따라에 대해 이동 하 여 [단일 책임 원칙 (SRP)](https://en.wikipedia.org/wiki/Single_responsibility_principle)합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-157">Not only that, the original class that was orchestrating the operations would grow and grow, which goes against the [Single Responsibility Principle (SRP)](https://en.wikipedia.org/wiki/Single_responsibility_principle).</span></span>

<span data-ttu-id="53638-158">반면에 도메인 이벤트를 사용 하는 경우이 방법을 사용 하는 책임 분리 하면 세부적이 고 분리 된 구현을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-158">On the other hand, if you use domain events, you can create a fine-grained and decoupled implementation by segregating responsibilities using this approach:</span></span>

1.  <span data-ttu-id="53638-159">명령 (예를 들어 CreateOrder)를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="53638-159">Send a command (for example, CreateOrder).</span></span>
2.  <span data-ttu-id="53638-160">이 명령은 명령 처리기에서 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-160">Receive the command in a command handler.</span></span>
    -   <span data-ttu-id="53638-161">단일 집계를 트랜잭션을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-161">Execute a single aggregate’s transaction.</span></span>
    -   <span data-ttu-id="53638-162">(선택 사항) 부작용 (예를 들어 OrderStartedDomainDvent)에 대 한 도메인 이벤트를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="53638-162">(Optional) Raise domain events for side effects (for example, OrderStartedDomainDvent).</span></span>
1.  <span data-ttu-id="53638-163">핸들 도메인 (현재 프로세스) 내에서 이벤트 thast 여러 집계 또는 응용 프로그램 작업에 열려 있는 부작용 수가 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53638-163">Handle domain events (within the current process) thast will execute an open number of side effects in multiple aggregates or application actions.</span></span> <span data-ttu-id="53638-164">예:</span><span class="sxs-lookup"><span data-stu-id="53638-164">For example:</span></span>
    -   <span data-ttu-id="53638-165">구매자 및 지불 방법을 만들거나 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-165">Verify or create buyer and payment method.</span></span>
    -   <span data-ttu-id="53638-166">만들고 관련된 통합 이벤트 상태를 구매자에 게 전자 메일을 보내는 등의 외부 작업 트리거에 microservices 전파할 이벤트 버스에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="53638-166">Create and send a related integration event to the event bus to propagate states across microservices or trigger external actions like sending an email to the buyer.</span></span>
    -   <span data-ttu-id="53638-167">다른 부작용을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-167">Handle other side effects.</span></span>

<span data-ttu-id="53638-168">그림 9-15에 표시 된 대로 동일한 도메인 이벤트에서 시작 처리할 수 있습니다 다른 집계 도메인 또는 microservices 통합 이벤트와 이벤트 버스에 연결을 수행 해야 할 추가 응용 프로그램 작업에 관련 된 여러 작업.</span><span class="sxs-lookup"><span data-stu-id="53638-168">As shown in Figure 9-15, starting from the same domain event, you can handle multiple actions related to other aggregates in the domain or additional application actions you need to perform across microservices connecting with integration events and the event bus.</span></span>

![](./media/image16.png)

<span data-ttu-id="53638-169">**그림 9-15**합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-169">**Figure 9-15**.</span></span> <span data-ttu-id="53638-170">도메인당 여러 작업을 처리</span><span class="sxs-lookup"><span data-stu-id="53638-170">Handling multiple actions per domain</span></span>

<span data-ttu-id="53638-171">이벤트 처리기 되므로 일반적으로 응용 프로그램 계층에서 마이크로 서비스의 동작에 대 한 저장소 또는 응용 프로그램 API와 같은 인프라 개체를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-171">The event handlers are typically in the application layer, because you will use infrastructure objects like repositories or an application API for the microservice’s behavior.</span></span> <span data-ttu-id="53638-172">이런 의미에서 이벤트 처리기는 응용 프로그램 계층의 일부가 되므로 명령 처리기와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-172">In that sense, event handlers are similar to command handlers, so both are part of the application layer.</span></span> <span data-ttu-id="53638-173">중요 한 차이점은 명령을 한 번만 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-173">The important difference is that a command should be processed just once.</span></span> <span data-ttu-id="53638-174">도메인 이벤트 수 0 처리 또는  *n*  있었기 때문에 경우 여러 수신기 또는 각 처리기에 대 한 다른 목적으로 이벤트 처리기에서 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-174">A domain event could be processed zero or *n* times, because if can be received by multiple receivers or event handlers with a different purpose for each handler.</span></span>

<span data-ttu-id="53638-175">열려 있는 도메인 이벤트당 처리기 수가 가능성 현재 코드에 영향을 주지 않고 더 많은 도메인 규칙을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-175">The possibility of an open number of handlers per domain event allows you to add many more domain rules without impacting your current code.</span></span> <span data-ttu-id="53638-176">예를 들어, 오른쪽 이벤트 후에 발생할 수 있는 다음 비즈니스 규칙을 구현 몇 가지 이벤트 처리기 (또는 심지어 하나)를 추가 하는 것 만큼 쉽게 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-176">For instance, implementing the following business rule that has to happen right after an event might be as easy as adding a few event handlers (or even just one):</span></span>

<span data-ttu-id="53638-177">주문 수 전체 저장소에 고객이 구매한 총 금액 $ 6, 000을 초과 하면 모든 새 주문을에 10% 할인 가격 할인을 적용 한 이후 주문에 대 한 해당 할인에 대 한 전자 메일 인 고객에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="53638-177">When the total amount purchased by a customer in the store, across any number of orders, exceeds $6,000, apply a 10% off discount to every new order and notify the customer with an email about that discount for future orders.</span></span>

## <a name="implementing-domain-events"></a><span data-ttu-id="53638-178">도메인 이벤트 구현</span><span class="sxs-lookup"><span data-stu-id="53638-178">Implementing domain events</span></span>

<span data-ttu-id="53638-179">C#, 도메인 이벤트는 단순히 데이터를 보유 중인 구조체 또는 다음 예제와 같이 방금 도메인의 내용에 관련 된 모든 정보로는 DTO와 같은 클래스:</span><span class="sxs-lookup"><span data-stu-id="53638-179">In C#, a domain event is simply a data-holding structure or class, like a DTO, with all the information related to what just happened in the domain, as shown in the following example:</span></span>

```csharp
public class OrderStartedDomainEvent : IAsyncNotification
{
    public int CardTypeId { get; private set; }
    public string CardNumber { get; private set; }
    public string CardSecurityNumber { get; private set; }
    public string CardHolderName { get; private set; }
    public DateTime CardExpiration { get; private set; }
    public Order Order { get; private set; }

    public OrderStartedDomainEvent(Order order,
        int cardTypeId, string cardNumber,
        string cardSecurityNumber, string cardHolderName,
        DateTime cardExpiration)
    {
        Order = order;
        CardTypeId = cardTypeId;
        CardNumber = cardNumber;
        CardSecurityNumber = cardSecurityNumber;
        CardHolderName = cardHolderName;
        CardExpiration = cardExpiration;
    }
}
```

<span data-ttu-id="53638-180">기본적으로 OrderStarted 이벤트와 관련 된 모든 데이터를 보유 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="53638-180">This is essentially a class that holds all the data related to the OrderStarted event.</span></span>

<span data-ttu-id="53638-181">도메인의 유비쿼터스 언어를 기준으로 이벤트 이전에 발생 한 것 이므로 이벤트의 클래스 이름으로 표시 되어야 OrderStartedDomainEvent 또는 OrderShippedDomainEvent 같은 과거 시제 동사입니다.</span><span class="sxs-lookup"><span data-stu-id="53638-181">In terms of the ubiquitous language of the domain, since an event is something that happened in the past, the class name of the event should be represented as a past-tense verb, like OrderStartedDomainEvent or OrderShippedDomainEvent.</span></span> <span data-ttu-id="53638-182">EShopOnContainers에 정렬 마이크로 서비스에서 도메인 이벤트의 구현 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="53638-182">That is how the domain event is implemented in the ordering microservice in eShopOnContainers.</span></span>

<span data-ttu-id="53638-183">듯이 있는 이벤트의 중요 한 특성 이므로 하는 이벤트는 변경 하지 않아야, 과거에 발생 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="53638-183">As we have noted, an important characteristic of events is that since an event is something that happened in the past, it should not change.</span></span> <span data-ttu-id="53638-184">따라서 변경 불가능 클래스 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-184">Therefore it must be an immutable class.</span></span> <span data-ttu-id="53638-185">속성은 읽기 전용에서 개체 외부에서 위의 코드에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-185">You can see in the preceding code that the properties are read-only from outside of the object.</span></span> <span data-ttu-id="53638-186">이벤트 개체를 만들 때 생성자를 통해 개체를 업데이트 하는 유일한 방법은 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53638-186">The only way to update the object is through the constructor when you create the event object.</span></span>

### <a name="raising-domain-events"></a><span data-ttu-id="53638-187">도메인 이벤트를 발생 시키기</span><span class="sxs-lookup"><span data-stu-id="53638-187">Raising domain events</span></span>

<span data-ttu-id="53638-188">다음 질문은 해당 관련 된 이벤트 처리기에 도달 하기 하므로 도메인 이벤트를 발생 하는 방법.</span><span class="sxs-lookup"><span data-stu-id="53638-188">The next question is how to raise a domain event so it reaches its related event handlers.</span></span> <span data-ttu-id="53638-189">여러 접근 방식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-189">You can use multiple approaches.</span></span>

<span data-ttu-id="53638-190">Udi Dahan 원래 제안 (예를 들어 몇 개에 등의 관련 된 게시물 [도메인 이벤트 – 2 수행](http://udidahan.com/2008/08/25/domain-events-take-2/)) 정적 클래스를 사용 하 여 관리 하 고 이벤트를 발생 시키기 위한 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-190">Udi Dahan originally proposed (for example, in several related posts, such as [Domain Events – Take 2](http://udidahan.com/2008/08/25/domain-events-take-2/)) using a static class for managing and raising the events.</span></span> <span data-ttu-id="53638-191">여기 DomainEvents.Raise (이벤트 myEvent)와 같은 구문을 사용 하 여 호출 될 때 즉시 도메인 이벤트를 발생 시킵니다 DomainEvents 라는 정적 클래스에 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-191">This might include a static class named DomainEvents that would raise domain events immediately when it is called, using syntax like DomainEvents.Raise(Event myEvent).</span></span> <span data-ttu-id="53638-192">Jimmy Bogard 블로그 게시물을 작성 했습니다. ([도메인 강화: 도메인 이벤트](https://lostechies.com/jimmybogard/2010/04/08/strengthening-your-domain-domain-events/)) 유사한 방법을 권장 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-192">Jimmy Bogard wrote a blog post ([Strengthening your domain: Domain Events](https://lostechies.com/jimmybogard/2010/04/08/strengthening-your-domain-domain-events/)) that recommends a similar approach.</span></span>

<span data-ttu-id="53638-193">그러나 도메인 이벤트 클래스는 정적 때도 디스패치합니다 처리기에 즉시 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-193">However, when the domain events class is static, it also dispatches to handlers immediately.</span></span> <span data-ttu-id="53638-194">이렇게 하면 테스트 및 디버깅 더 어렵게 부작용 논리를 사용 하 여 이벤트 처리기는 이벤트가 발생 한 후에 즉시 실행 되므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-194">This makes testing and debugging more difficult, because the event handlers with side-effects logic are executed immediately after the event is raised.</span></span> <span data-ttu-id="53638-195">에 집중 하 고 현재 집계 클래스;에서 일어나는 방금 하려는 테스트 하 고 디버깅 하는 경우 의도 하지 않은 다른 집계 또는 응용 프로그램 논리와 관련 된 다른 이벤트 처리기에 갑자기 리디렉션될 하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-195">When you are testing and debugging, you want to focus on and just what is happening in the current aggregate classes; you do not want to suddenly be redirected to other event handlers for side effects related to other aggregates or application logic.</span></span> <span data-ttu-id="53638-196">이것이 다른 접근 방법이 진화 하는 이유는 다음 섹션에 설명 된 대로입니다.</span><span class="sxs-lookup"><span data-stu-id="53638-196">This is why other approaches have evolved, as explained in the next section.</span></span>

#### <a name="the-deferred-approach-for-raising-and-dispatching-events"></a><span data-ttu-id="53638-197">발생 시키고 이벤트 전달에 대 한 지연 된 접근 방식</span><span class="sxs-lookup"><span data-stu-id="53638-197">The deferred approach for raising and dispatching events</span></span>

<span data-ttu-id="53638-198">즉시 도메인 이벤트 처리기에 디스패치 하는 대신 더 나은 방법은 도메인 이벤트 컬렉션에 추가 하려면 다음 해당 도메인 이벤트를 디스패치 하 *직전* 또는 *오른쪽*  *후* 트랜잭션을 커밋하는 중 (과 마찬가지로 EF에서 SaveChanges).</span><span class="sxs-lookup"><span data-stu-id="53638-198">Instead of dispatching to a domain event handler immediately, a better approach is to add the domain events to a collection and then to dispatch those domain events *right before* or *right* *after* committing the transaction (as with SaveChanges in EF).</span></span> <span data-ttu-id="53638-199">(이 방법은 Jimmy Bogard이이 게시물에서 설명한 [더 나은 도메인 이벤트 패턴](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/).)</span><span class="sxs-lookup"><span data-stu-id="53638-199">(This approach was described by Jimmy Bogard in this post [A better domain events pattern](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/).)</span></span>

<span data-ttu-id="53638-200">도메인 이벤트를 보낼 경우 결정 트랜잭션을 커밋한 후 이전 또는 오른쪽 오른쪽 이므로 중요 일부로 동일한 트랜잭션 또는 서로 다른 트랜잭션을 부작용은 포함 됩니다 있는지 여부를 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="53638-200">Deciding if you send the domain events right before or right after committing the transaction is important, since it determines whether you will include the side effects as part of the same transaction or in different transactions.</span></span> <span data-ttu-id="53638-201">후자의 경우 결과적 일관성 여러 집계에서 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-201">In the latter case, you need to deal with eventual consistency across multiple aggregates.</span></span> <span data-ttu-id="53638-202">이 항목의 다음 섹션에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-202">This topic is discussed in the next section.</span></span>

<span data-ttu-id="53638-203">지연 된 방법은 다음을 사용 하 여 어떤 eShopOnContainers입니다.</span><span class="sxs-lookup"><span data-stu-id="53638-203">The deferred approach is what eShopOnContainers uses.</span></span> <span data-ttu-id="53638-204">먼저, 컬렉션 또는 엔터티 당 이벤트의 목록에 엔터티의 발생 하는 이벤트를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-204">First, you add the events happening in your entities into a collection or list of events per entity.</span></span> <span data-ttu-id="53638-205">다음 예제와 같이 나열 하는 엔터티 개체의 일부 또는 더 좋은 기준 엔터티 클래스의 일부 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-205">That list should be part of the entity object, or even better, part of your base entity class, as shown in the following example:</span></span>

```csharp
public abstract class Entity
{
    private List<IAsyncNotification> _domainEvents;

    public List<IAsyncNotification> DomainEvents => _domainEvents;

    public void AddDomainEvent(IAsyncNotification eventItem)
    {
        _domainEvents = _domainEvents ?? new List<IAsyncNotification>();
        _domainEvents.Add(eventItem);
    }

    public void RemoveDomainEvent(IAsyncNotification eventItem)
    {
        if (_domainEvents is null) return;
        _domainEvents.Remove(eventItem);
    }
    // ...
}
```

<span data-ttu-id="53638-206">이벤트를 발생 시키는 하려면 방금에 추가한 다음 코드와 같이 집계 entity 메서드를 배치 하려면 이벤트 컬렉션:</span><span class="sxs-lookup"><span data-stu-id="53638-206">When you want to raise an event, you just add it to the event collection to be placed within an aggregate entity method, as the following code shows:</span></span>

```csharp
var orderStartedDomainEvent = new OrderStartedDomainEvent(this, //Order object
    cardTypeId,
    cardNumber,
    cardSecurityNumber,
    cardHolderName,
    cardExpiration);
this.AddDomainEvent(orderStartedDomainEvent);
```

<span data-ttu-id="53638-207">공지 AddDomainEvent 메서드를 수행 하 고 있는 유일한 항목 목록에 한 이벤트를 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53638-207">Notice that the only thing that the AddDomainEvent method is doing is adding an event to the list.</span></span> <span data-ttu-id="53638-208">이벤트가 아직 발생 하 고 이벤트 처리기가 아직 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-208">No event is raised yet, and no event handler is invoked yet.</span></span>

<span data-ttu-id="53638-209">실제로 해당 데이터베이스에 트랜잭션을 커밋하는 경우 나중에 이벤트를 전달 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-209">You actually want to dispatch the events later on, when you commit the transaction to the database.</span></span> <span data-ttu-id="53638-210">Entity Framework Core를 사용 하는 경우 즉, 다음 코드 에서처럼 프로그램 EF DbContext의 SaveChanges 메서드:</span><span class="sxs-lookup"><span data-stu-id="53638-210">If you are using Entity Framework Core, that means in the SaveChanges method of your EF DbContext, as in the following code:</span></span>

```csharp
// EF Core DbContext
public class OrderingContext : DbContext, IUnitOfWork
{
    // ...
    public async Task<int> SaveEntitiesAsync()
    {
        // Dispatch Domain Events collection.
        // Choices:
        // A) Right BEFORE committing data (EF SaveChanges) into the DB. This makes
        // a single transaction including side effects from the domain event
        // handlers that are using the same DbContext with Scope lifetime
        // B) Right AFTER committing data (EF SaveChanges) into the DB. This makes
        // multiple transactions. You will need to handle eventual consistency and
        // compensatory actions in case of failures.
        await _mediator.DispatchDomainEventsAsync(this);
        // After this line runs, all the changes (from the Command Handler and Domain
        // event handlers) performed through the DbContext will be commited
        var result = await base.SaveChangesAsync();
    }
}
```

<span data-ttu-id="53638-211">이 코드를 통해 해당 해당 이벤트 처리기에 엔터티 이벤트를 발송합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-211">With this code, you dispatch the entity events to their respective event handlers.</span></span>

<span data-ttu-id="53638-212">전체 결과 있는지 있습니다가에서 분리 됨 (간단한 메모리에 있는 목록에 추가) 도메인 이벤트의 발생 한 이벤트 처리기에 디스패치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53638-212">The overall result is that you have decoupled the raising of a domain event (a simple add into a list in memory) from dispatching it to an event handler.</span></span> <span data-ttu-id="53638-213">또한 사용 중인 발송자의 종류에 따라 동기적 또는 비동기적으로 이벤트를 발송 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-213">In addition, depending on what kind of dispatcher you are using, you could dispatch the events synchronously or asynchronously.</span></span>

<span data-ttu-id="53638-214">중요 한 것으로 배치 하는 트랜잭션 경계 여기 재생 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-214">Be aware that transactional boundaries come into significant play here.</span></span> <span data-ttu-id="53638-215">둘 이상의 집계는 작업 및 트랜잭션 단위에 걸쳐 있을 수 있는 경우 (as EF 코어와 관계형 데이터베이스를 사용 하는 경우)이도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-215">If your unit of work and transaction can span more than one aggregate (as when using EF Core and a relational database), this can work well.</span></span> <span data-ttu-id="53638-216">하지만 일관성을 확보 하기 위한 추가 단계를 구현 해야 하는 경우 트랜잭션이 Azure DocumentDB와 같은 NoSQL 데이터베이스를 사용 하는 경우 등의 집계를 확장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-216">But if the transaction cannot span aggregates, such as when you are using a NoSQL database like Azure DocumentDB, you have to implement additional steps to achieve consistency.</span></span> <span data-ttu-id="53638-217">이 지 속성 무시 유니버설; 하지 않은 이유는 또 다른 이유입니다. 사용 하는 저장소 시스템에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="53638-217">This is another reason why persistence ignorance is not universal; it depends on the storage system you use.</span></span>

### <a name="single-transaction-across-aggregates-versus-eventual-consistency-across-aggregates"></a><span data-ttu-id="53638-218">집계에서 결과적 일관성와 집계에서 단일 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="53638-218">Single transaction across aggregates versus eventual consistency across aggregates</span></span>

<span data-ttu-id="53638-219">이러한 집계에서 결과적 일관성에 의존와 집계에서 단일 트랜잭션을 수행할 것인지 여부에 대 한 질문은 논쟁입니다.</span><span class="sxs-lookup"><span data-stu-id="53638-219">The question of whether to perform a single transaction across aggregates versus relying on eventual consistency across those aggregates is a controversial one.</span></span> <span data-ttu-id="53638-220">Eric Evans 및 Vaughn Vernon 주 창 규칙 해당 하나의 트랜잭션 처럼 DDD 저자를 많이 = 하나의 집계 하 고 따라서 집계에서 결과적 일관성 주장 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-220">Many DDD authors like Eric Evans and Vaughn Vernon advocate the rule that one transaction = one aggregate and therefore argue for eventual consistency across aggregates.</span></span> <span data-ttu-id="53638-221">예를 들어 저서인에서에서 *Domain-Driven 디자인*, Eric Evans이 표시:</span><span class="sxs-lookup"><span data-stu-id="53638-221">For example, in his book *Domain-Driven Design*, Eric Evans says this:</span></span>

<span data-ttu-id="53638-222">집계에 걸쳐 있는 모든 규칙에 항상 최신 상태로 유지할 수 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-222">Any rule that spans Aggregates will not be expected to be up-to-date at all times.</span></span> <span data-ttu-id="53638-223">이벤트 처리, 일괄 처리 또는 다른 업데이트 메커니즘을 통해 특정 시간 내 다른 종속성 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-223">Through event processing, batch processing, or other update mechanisms, other dependencies can be resolved within some specific time.</span></span> <span data-ttu-id="53638-224">(페이지</span><span class="sxs-lookup"><span data-stu-id="53638-224">(pg.</span></span> <span data-ttu-id="53638-225">128)</span><span class="sxs-lookup"><span data-stu-id="53638-225">128)</span></span>

<span data-ttu-id="53638-226">다음에 따르면 Vaughn Vernon [효율적인 집계 디자인 합니다. 2 부: 만들기 집계 작업 함께](http://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf):</span><span class="sxs-lookup"><span data-stu-id="53638-226">Vaughn Vernon says the following in [Effective Aggregate Design. Part II: Making Aggregates Work Together](http://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf):</span></span>

<span data-ttu-id="53638-227">따라서 집계 인스턴스에 하나 이상의 집계에 비즈니스 규칙을 추가로 실행 하는 필요 하나에서 명령을 실행할 경우 사용할 결과적 일관성 \[...\] DDD 모델에서 결과적 일관성을 지 원하는 데 실용적인 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-227">Thus, if executing a command on one aggregate instance requires that additional business rules execute on one or more aggregates, use eventual consistency \[...\] There is a practical way to support eventual consistency in a DDD model.</span></span> <span data-ttu-id="53638-228">집계 메서드는 하나 이상의 비동기 구독자에 배달 하는 시간 도메인 이벤트를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-228">An aggregate method publishes a domain event that is in time delivered to one or more asynchronous subscribers.</span></span>

<span data-ttu-id="53638-229">집계 수가 많거나 엔터티에 걸쳐 있는 트랜잭션 대신 세분화 된 트랜잭션을 수용 하기에 근거는입니다.</span><span class="sxs-lookup"><span data-stu-id="53638-229">This rationale is based on embracing fine-grained transactions instead of transactions spanning many aggregates or entities.</span></span> <span data-ttu-id="53638-230">개념은 초는 두 번째 경우에 데이터베이스 잠금 수가 높은 확장성 요구 사항이 있는 대규모 응용 프로그램에서 상당한입니다.</span><span class="sxs-lookup"><span data-stu-id="53638-230">The idea is that in the second case, the number of database locks will be substantial in large-scale applications with high scalability needs.</span></span> <span data-ttu-id="53638-231">확장성이 높은 응용 프로그램 필요 없는 여러 집계 간에 트랜잭션 일관성 인스턴트 사실을 수용는 결과적 일관성의 개념을 적용에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53638-231">Embracing the fact that high-scalable applications need not have instant transactional consistency between multiple aggregates helps with accepting the concept of eventual consistency.</span></span> <span data-ttu-id="53638-232">원자성 변경 하지 않는 비즈니스에 필요한 및 특정 작업 또는 not 원자성 트랜잭션이 필요한 지를 말 하 도메인 전문가 작업은 어떤 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-232">Atomic changes are often not needed by the business, and it is in any case the responsibility of the domain experts to say whether particular operations need atomic transactions or not.</span></span> <span data-ttu-id="53638-233">작업은 항상 원자성 트랜잭션 간에 여러 집계를 필요로 한다면 인지 궁금할 프로그램 집계 커야 여부는 제대로 설계 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-233">If an operation always needs an atomic transaction between multiple aggregates, you might ask whether your aggregate should be larger or was not correctly designed.</span></span>

<span data-ttu-id="53638-234">그러나 다른 개발자와 같은 Jimmy Bogard 설계자는 단일 트랜잭션을 여러 집계에 확장을 덮어쓰려면-하지만 때 이러한 추가 집계 관련 된 동일한 원래 명령에 대 한 부작용입니다.</span><span class="sxs-lookup"><span data-stu-id="53638-234">However, other developers and architects like Jimmy Bogard are okay with spanning a single transaction across several aggregates—but only when those additional aggregates are related to side effects for the same original command.</span></span> <span data-ttu-id="53638-235">예를 들어, [더 나은 도메인 이벤트 패턴](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/),이 Bogard 표시:</span><span class="sxs-lookup"><span data-stu-id="53638-235">For instance, in [A better domain events pattern](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/), Bogard says this:</span></span>

<span data-ttu-id="53638-236">일반적으로 동일한 논리 트랜잭션 내에서 하지만 반드시 도메인 이벤트를 발생 시키는 동일한 범위에 적용 되려면 도메인 이벤트의 부작용은 원하는 \[...\] 우리의 트랜잭션 약속할 하기 바로 전에 각 해당 처리기에 우리의 이벤트를 전달 했습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-236">Typically, I want the side effects of a domain event to occur within the same logical transaction, but not necessarily in the same scope of raising the domain event \[...\] Just before we commit our transaction, we dispatch our events to their respective handlers.</span></span>

<span data-ttu-id="53638-237">도메인 이벤트 오른쪽을 디스패치 하는 경우 *전에* 원래 트랜잭션을 커밋한 되었기 때문에 동일한 트랜잭션에 포함 시킬 이벤트의 부작용을 원하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-237">If you dispatch the domain events right *before* committing the original transaction, it is because you want the side effects of those events to be included in the same transaction.</span></span> <span data-ttu-id="53638-238">예를 들어, EF DbContext SaveChanges 메서드를 호출에 실패 하면 트랜잭션이 롤백합니다 도메인 관련된 이벤트 처리기에 의해 구현 되는 부작용 작업의 결과 포함 하는 모든 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-238">For example, if the EF DbContext SaveChanges method fails, the transaction will roll back all changes, including the result of any side effect operations implemented by the related domain event handlers.</span></span> <span data-ttu-id="53638-239">이 DbContext 수명 범위는 기본적으로 정의으로 하기 때문에 "범위가 지정 됩니다."</span><span class="sxs-lookup"><span data-stu-id="53638-239">This is because the DbContext life scope is by default defined as "scoped."</span></span> <span data-ttu-id="53638-240">따라서 DbContext 개체는 동일한 범위 또는 개체 그래프에서 인스턴스화되는 여러 저장소 개체 간에 공유 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53638-240">Therefore, the DbContext object is shared across multiple repository objects being instantiated within the same scope or object graph.</span></span> <span data-ttu-id="53638-241">이 위치 MVC 또는 Web API 앱을 개발할 때 HttpRequest 범위와 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-241">This coincides with the HttpRequest scope when developing Web API or MVC apps.</span></span>

<span data-ttu-id="53638-242">실제로 두 방법 모두 (단일 원자성 트랜잭션 및 결과적 일관성) 오른쪽 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-242">In reality, both approaches (single atomic transaction and eventual consistency) can be right.</span></span> <span data-ttu-id="53638-243">실제로 어떤 도메인 전문가 알려 및 도메인 또는 비즈니스 요구 사항에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="53638-243">It really depends on your domain or business requirements and what the domain experts tell you.</span></span> <span data-ttu-id="53638-244">또한 되도록 서비스가 필요한 경우 확장 가능한 방식에 따라 다릅니다 (더 세분화 된 트랜잭션을 영향이 줄어듭니다 데이터베이스 잠금 관련 하 여).</span><span class="sxs-lookup"><span data-stu-id="53638-244">It also depends on how scalable you need the service to be (more granular transactions have less impact with regard to database locks).</span></span> <span data-ttu-id="53638-245">한 결과적 일관성 집계 및 compensatory 동작을 구현 해야 할 필요성 간의 유형 검사 결과 검색 하기 위해 더 복잡 한 코드가 필요 하므로 사용자 코드에서 있도록 감수할지 얼마나 많은 투자에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="53638-245">And it depends on how much investment you are willing to make in your code, since eventual consistency requires more complex code in order to detect possible inconsistencies across aggregates and the need to implement compensatory actions.</span></span> <span data-ttu-id="53638-246">원래 집계와 그 후에 이벤트를 발송 되는 변경 내용을 커밋할 경우는 문제가 있는지 고려 하는 이벤트 처리기의 부작용을 커밋할 수 없습니다, 그리고 집계 간의 불일치를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-246">Take into account that if you commit changes to the original aggregate and afterwards, when the events are being dispatched, there is an issue and the event handlers cannot commit their side effects, you will have inconsistencies between aggregates.</span></span>

<span data-ttu-id="53638-247">Compensatory 작업을 허용 하는 방법을 원래 트랜잭션의 일부가 될 수 있도록 추가 데이터베이스 테이블에 도메인 이벤트를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-247">A way to allow compensatory actions would be to store the domain events in additional database tables so they can be part of the original transaction.</span></span> <span data-ttu-id="53638-248">이후에 불일치를 감지 하 고 집계의 현재 상태와 이벤트 목록을 비교 하 여 compensatory 동작을 실행 하는 일괄 처리를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-248">Afterwards, you could have a batch process that detects inconsistencies and runs compensatory actions by comparing the list of events with the current state of the aggregates.</span></span> <span data-ttu-id="53638-249">Compensatory 작업을 사용 하면 비즈니스 사용자 및 도메인 전문가와 토론을 포함 한 쪽에서 심층 분석 해야 하는 복잡 한 주제에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-249">The compensatory actions are part of a complex topic that will require deep analysis from your side, which includes discussing it with the business user and domain experts.</span></span>

<span data-ttu-id="53638-250">어떤 경우 든, 필요한 방법을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-250">In any case, you can choose the approach you need.</span></span> <span data-ttu-id="53638-251">하지만 초기 지연 접근 방식을-단일 트랜잭션을 사용 하므로, 커밋하기 전에 이벤트를 발생 시키는-EF 코어와 관계형 데이터베이스를 사용 하는 경우는 가장 간단한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="53638-251">But the initial deferred approach—raising the events before committing, so you use a single transaction—is the simplest approach when using EF Core and a relational database.</span></span> <span data-ttu-id="53638-252">것 잘 구현 하 고 대부분의 비즈니스 사례에서 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-252">It is easier to implement and valid in many business cases.</span></span> <span data-ttu-id="53638-253">EShopOnContainers에 정렬 마이크로 서비스에서 사용 하는 방법 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-253">It is also the approach used in the ordering microservice in eShopOnContainers.</span></span>

<span data-ttu-id="53638-254">그러나 어떻게 수행 하면 실제로 이러한 이벤트 전달 하며, 해당 이벤트 처리기를?</span><span class="sxs-lookup"><span data-stu-id="53638-254">But how do you actually dispatch those events to their respective event handlers?</span></span> <span data-ttu-id="53638-255">란는 \_앞의 예제에서 볼 수 있는 중재자 개체?</span><span class="sxs-lookup"><span data-stu-id="53638-255">What is the \_mediator object that you see in the previous example?</span></span> <span data-ttu-id="53638-256">기술 및 아티팩트 이벤트 및 해당 이벤트 처리기 간에 매핑하는 데 사용할 수와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-256">That has to do with the techniques and artifacts you can use to map between events and their event handlers.</span></span>

### <a name="the-domain-event-dispatcher-mapping-from-events-to-event-handlers"></a><span data-ttu-id="53638-257">도메인 이벤트 발송자: 이벤트에서 이벤트 처리기에 매핑</span><span class="sxs-lookup"><span data-stu-id="53638-257">The domain event dispatcher: mapping from events to event handlers</span></span>

<span data-ttu-id="53638-258">를 디스패치 하거나 이벤트를 게시할 수 있는 후 일종의 아티팩트를 해당 이벤트에 따라 의도 하지 않은 프로세스 및 모든 관련된 처리기에서 얻을 수 있도록 이벤트를 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-258">Once you are able to dispatch or publish the events, you need some kind of artifact that will publish the event so that every related handler can get it and process side effects based on that event.</span></span>

<span data-ttu-id="53638-259">한 가지 방법은 실제 메시징 시스템 또는 심지어는 이벤트 버스를 메모리에 이벤트 대신 서비스 버스에 기반 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-259">One approach is a real messaging system or even an event bus, possibly based on a service bus as opposed to in-memory events.</span></span> <span data-ttu-id="53638-260">그러나 첫 번째 경우에 대 한 실제 메시징 수 도메인 이벤트를 처리 하 여 동일한 프로세스 내에서 이러한 이벤트를 처리할 필요가 없기 때문에 대 한 개념을 세우 (즉, 같은 도메인 및 응용 프로그램 계층 내에서).</span><span class="sxs-lookup"><span data-stu-id="53638-260">However, for the first case, real messaging would be overkill for processing domain events, since you just need to process those events within the same process (that is, within the same domain and application layer).</span></span>

<span data-ttu-id="53638-261">여러 이벤트 처리기에 이벤트를 매핑할 또 다른 방법은 이벤트를 디스패치할 위치를 동적으로 유추할 수 있도록 IoC 컨테이너에서 형식 등록을 사용 하 여는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="53638-261">Another way to map events to multiple event handlers is by using types registration in an IoC container so that you can dynamically infer where to dispatch the events.</span></span> <span data-ttu-id="53638-262">즉, 특정 이벤트를 가져와야 할 이벤트 처리기를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-262">In other words, you need to know what event handlers need to get a specific event.</span></span> <span data-ttu-id="53638-263">그림 9-16을 있는 간단한 접근 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="53638-263">Figure 9-16 shows a simplified approach for that.</span></span>

![](./media/image17.png)

<span data-ttu-id="53638-264">**그림 9-16**합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-264">**Figure 9-16**.</span></span> <span data-ttu-id="53638-265">IoC를 사용 하 여 도메인 이벤트 발송자</span><span class="sxs-lookup"><span data-stu-id="53638-265">Domain event dispatcher using IoC</span></span>

<span data-ttu-id="53638-266">모든 배관 및 혼자서는 방법을 구현 하는 아티팩트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-266">You can build all the plumbing and artifacts to implement that approach by yourself.</span></span> <span data-ttu-id="53638-267">그러나과 같은 사용 가능한 라이브러리도 사용할 수 [MediatR](https://github.com/jbogard/MediatR), IoT 컨테이너를 사용 하 여 내부적입니다.</span><span class="sxs-lookup"><span data-stu-id="53638-267">However, you can also use available libraries like [MediatR](https://github.com/jbogard/MediatR), which underneath the covers uses your IoT container.</span></span> <span data-ttu-id="53638-268">따라서 직접 사용할 수는 미리 정의 된 인터페이스와 중재자 개체의 게시/디스패치 메서드.</span><span class="sxs-lookup"><span data-stu-id="53638-268">You can therefore directly use the predefined interfaces and the mediator object’s publish/dispatch methods.</span></span>

<span data-ttu-id="53638-269">코드에서 먼저 등록 해야 이벤트 처리기 형식 IoC 컨테이너의 다음 예제와 같이:</span><span class="sxs-lookup"><span data-stu-id="53638-269">In code, you first need to register the event handler types in your IoC container, as shown in the following example:</span></span>

```csharp
public class MediatorModule : Autofac.Module
{
    protected override void Load(ContainerBuilder builder)
    {
        // Other registrations ...
        // Register the DomainEventHandler classes (they implement
        // IAsyncNotificationHandler<>) in assembly holding the Domain Events
        builder.RegisterAssemblyTypes(
            typeof(ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler)
            .GetTypeInfo().Assembly)
            .Where(t => t.IsClosedTypeOf(typeof(IAsyncNotificationHandler<>)))
            .AsImplementedInterfaces();
        // Other registrations ...
    }
}
```

<span data-ttu-id="53638-270">코드 처리기 중 하나를 보유 하는 어셈블리를 찾아 도메인 이벤트 처리기를 포함 하는 어셈블리를 먼저 식별 (사용 하 여 typeof(ValidateOrAddBuyerAggregateWhenXxxx)를 선택할 수는 어셈블리를 찾는 다른 이벤트 처리기).</span><span class="sxs-lookup"><span data-stu-id="53638-270">The code first identifies the assembly that contains the domain event handlers by locating the assembly that holds any of the handlers (using typeof(ValidateOrAddBuyerAggregateWhenXxxx), but you could have chosen any other event handler to locate the assembly).</span></span> <span data-ttu-id="53638-271">모든 이벤트 처리기 IAsyncNotificationHandler 인터페이스를 구현 하므로 정당한 검색 하는 것에 대 한 다음 코드 형식 및 모든 이벤트 처리기를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-271">Since all the event handlers implement the IAsyncNotificationHandler interface, the code then just searches for those types and registers all the event handlers.</span></span>

### <a name="how-to-subscribe-to-domain-events"></a><span data-ttu-id="53638-272">도메인 이벤트를 구독 하는 방법</span><span class="sxs-lookup"><span data-stu-id="53638-272">How to subscribe to domain events</span></span>

<span data-ttu-id="53638-273">MediatR를 사용 하면 각 이벤트 처리기 다음 코드에서 볼 수 있듯이 IAsyncNotificationHandler 인터페이스의 제네릭 매개 변수에서 제공 되는 이벤트 유형을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-273">When you use MediatR, each event handler must use an event type that is provided on the generic parameter of the IAsyncNotificationHandler interface, as you can see in the following code:</span></span>

```csharp
public class ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler
  : IAsyncNotificationHandler<OrderStartedDomainEvent>
```

<span data-ttu-id="53638-274">MediatR 아티팩트 수 이벤트와 이벤트 처리기를으로 간주 될 수는 구독 간의 관계에 따라 각 이벤트에 대 한 모든 이벤트 처리기를 검색 및 이러한 이벤트 처리기의 각 트리거 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-274">Based on the relationship between event and event handler, which can be considered the subscription, the MediatR artifact can discover all the event handlers for each event and trigger each of those event handlers.</span></span>

### <a name="how-to-handle-domain-events"></a><span data-ttu-id="53638-275">도메인 이벤트를 처리 하는 방법</span><span class="sxs-lookup"><span data-stu-id="53638-275">How to handle domain events</span></span>

<span data-ttu-id="53638-276">마지막으로, 이벤트 처리기는 일반적으로 필요한 추가 집계를 가져올 수 및 부수적 도메인 논리를 실행 하 저장소 인프라를 사용 하는 응용 프로그램 계층 코드를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-276">Finally, the event handler usually implements application layer code that uses infrastructure repositories to obtain the required additional aggregates and to execute side-effect domain logic.</span></span> <span data-ttu-id="53638-277">다음 코드는 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="53638-277">The following code shows an example.</span></span>

```csharp
public class ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler
    : IAsyncNotificationHandler<OrderStartedDomainEvent>
{
    private readonly ILoggerFactory _logger;
    private readonly IBuyerRepository<Buyer> _buyerRepository;
    private readonly IIdentityService _identityService;
    public ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler(
        ILoggerFactory logger,
        IBuyerRepository<Buyer> buyerRepository,
        IIdentityService identityService)
    {
        // Parameter validations
        //...
    }

    public async Task Handle(OrderStartedDomainEvent orderStartedEvent)
    {
        var cardTypeId = (orderStartedEvent.CardTypeId != 0) ?
            orderStartedEvent.CardTypeId : 1;
        var userGuid = _identityService.GetUserIdentity();
        var buyer = await _buyerRepository.FindAsync(userGuid);
        bool buyerOriginallyExisted = (buyer == null) ? false : true;
        if (!buyerOriginallyExisted)
        {
            buyer = new Buyer(userGuid);
        }
        buyer.VerifyOrAddPaymentMethod(cardTypeId,
            $"Payment Method on {DateTime.UtcNow}",
            orderStartedEvent.CardNumber,
            orderStartedEvent.CardSecurityNumber,
            orderStartedEvent.CardHolderName,
            orderStartedEvent.CardExpiration,
            orderStartedEvent.Order.Id);
        var buyerUpdated = buyerOriginallyExisted ? _buyerRepository.Update(buyer) :
        _buyerRepository.Add(buyer);
        await _buyerRepository.UnitOfWork.SaveEntitiesAsync();
        // Logging code using buyerUpdated info, etc.
    }
}
```

<span data-ttu-id="53638-278">이 이벤트 처리기 코드로 간주 됩니다 응용 프로그램 계층 코드 인프라 저장소를 사용 하기 때문에 인프라를 지 속성 계층의 다음 섹션에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-278">This event handler code is considered application layer code because it uses infrastructure repositories, as explained in the next section on the infrastructure-persistence layer.</span></span> <span data-ttu-id="53638-279">또한 이벤트 처리기 수 다른 인프라 구성 요소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-279">Event handlers could also use other infrastructure components.</span></span>

#### <a name="domain-events-can-generate-integration-events-to-be-published-outside-of-the-microservice-boundaries"></a><span data-ttu-id="53638-280">도메인 이벤트 마이크로 서비스 경계 외부에서 게시할 통합 이벤트를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53638-280">Domain events can generate integration events to be published outside of the microservice boundaries</span></span>

<span data-ttu-id="53638-281">마지막으로,이 이벤트에 여러 microservices 전파 하려는 경우에 따라 언급 하기 위해 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-281">Finally, is important to mention that you might sometimes want to propagate events across multiple microservices.</span></span> <span data-ttu-id="53638-282">통합 이벤트 /에서 특정 도메인 이벤트 처리기는 이벤트 버스를 통해 게시할 수 있었습니다 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-282">That is considered an integration event, and it could be published through an event bus from any specific domain event handler.</span></span>

## <a name="conclusions-on-domain-events"></a><span data-ttu-id="53638-283">결론 도메인 이벤트</span><span class="sxs-lookup"><span data-stu-id="53638-283">Conclusions on domain events</span></span> 

<span data-ttu-id="53638-284">언급 한 것 처럼 명시적으로 도메인 내에서 변경의 부작용을 구현 하 도메인 이벤트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-284">As stated, use domain events to explicitly implement side effects of changes within your domain.</span></span> <span data-ttu-id="53638-285">DDD 용어를 사용 하려면 도메인 이벤트를 사용 하 여 하나 또는 여러 집계에서 의도 하지 않은 명시적으로 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-285">To use DDD terminology, use domain events to explicitly implement side effects across one or multiple aggregates.</span></span> <span data-ttu-id="53638-286">또한 및 확장성 향상을 위해와 데이터베이스 잠금에 미치는 영향을 덜 같은 도메인 내의 집계 간의 결과적 일관성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="53638-286">Additionally, and for better scalability and less impact on database locks, use eventual consistency between aggregates within the same domain.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="53638-287">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="53638-287">Additional resources</span></span>

-   <span data-ttu-id="53638-288">**Greg Young 합니다. 도메인 이벤트는 무엇입니까? ** 
     [ *http://codebetter.com/gregyoung/2010/04/11/what-is-a-domain-event/*](http://codebetter.com/gregyoung/2010/04/11/what-is-a-domain-event/)</span><span class="sxs-lookup"><span data-stu-id="53638-288">**Greg Young. What is a Domain Event?**
[*http://codebetter.com/gregyoung/2010/04/11/what-is-a-domain-event/*](http://codebetter.com/gregyoung/2010/04/11/what-is-a-domain-event/)</span></span>

-   <span data-ttu-id="53638-289">**1 월 Stenberg 합니다. 도메인 이벤트와 결과적 일관성**
    [*https://www.infoq.com/news/2015/09/domain-events-consistency*](https://www.infoq.com/news/2015/09/domain-events-consistency)</span><span class="sxs-lookup"><span data-stu-id="53638-289">**Jan Stenberg. Domain Events and Eventual Consistency**
[*https://www.infoq.com/news/2015/09/domain-events-consistency*](https://www.infoq.com/news/2015/09/domain-events-consistency)</span></span>

-   <span data-ttu-id="53638-290">**Jimmy Bogard. 더 나은 도메인 이벤트 패턴**
    [*https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/*](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/)</span><span class="sxs-lookup"><span data-stu-id="53638-290">**Jimmy Bogard. A better domain events pattern**
[*https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/*](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/)</span></span>

-   <span data-ttu-id="53638-291">**Vaughn Vernon. 효과적인 집계 디자인 2 부: 만들기 작업 함께 집계**
    [*http://dddcommunity.org/wp-content/uploads/files/pdf\_문서/Vernon\_2011\_ 2. pdf*](http://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf)</span><span class="sxs-lookup"><span data-stu-id="53638-291">**Vaughn Vernon. Effective Aggregate Design Part II: Making Aggregates Work Together**
[*http://dddcommunity.org/wp-content/uploads/files/pdf\_articles/Vernon\_2011\_2.pdf*](http://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf)</span></span>

-   <span data-ttu-id="53638-292">**Jimmy Bogard. 도메인 강화: 도메인 이벤트**
    *<https://lostechies.com/jimmybogard/2010/04/08/strengthening-your-domain-domain-events/>*</span><span class="sxs-lookup"><span data-stu-id="53638-292">**Jimmy Bogard. Strengthening your domain: Domain Events**
*<https://lostechies.com/jimmybogard/2010/04/08/strengthening-your-domain-domain-events/> *</span></span>

-   <span data-ttu-id="53638-293">**Tony Truong 합니다. 도메인 이벤트 패턴을 예제**
    [*http://www.tonytruong.net/domain-events-pattern-example/*](http://www.tonytruong.net/domain-events-pattern-example/)</span><span class="sxs-lookup"><span data-stu-id="53638-293">**Tony Truong. Domain Events Pattern Example**
[*http://www.tonytruong.net/domain-events-pattern-example/*](http://www.tonytruong.net/domain-events-pattern-example/)</span></span>

-   <span data-ttu-id="53638-294">**Udi Dahan 합니다. 완벽 하 게 만드는 방법에는 도메인 모델 캡슐화**
    [*http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/*](http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/)</span><span class="sxs-lookup"><span data-stu-id="53638-294">**Udi Dahan. How to create fully encapsulated Domain Models**
[*http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/*](http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/)</span></span>

-   <span data-ttu-id="53638-295">**Udi Dahan 합니다. 도메인 이벤트 – 2 수행**
    [*http://udidahan.com/2008/08/25/domain-events-take-2/*](http://udidahan.com/2008/08/25/domain-events-take-2/%20)</span><span class="sxs-lookup"><span data-stu-id="53638-295">**Udi Dahan. Domain Events – Take 2**
[*http://udidahan.com/2008/08/25/domain-events-take-2/*](http://udidahan.com/2008/08/25/domain-events-take-2/%20)</span></span>

-   <span data-ttu-id="53638-296">**Udi Dahan 합니다. 도메인 이벤트 – 구원을 받 았**
    [*http://udidahan.com/2009/06/14/domain-events-salvation/*](http://udidahan.com/2009/06/14/domain-events-salvation/)</span><span class="sxs-lookup"><span data-stu-id="53638-296">**Udi Dahan. Domain Events – Salvation**
[*http://udidahan.com/2009/06/14/domain-events-salvation/*](http://udidahan.com/2009/06/14/domain-events-salvation/)</span></span>

-   <span data-ttu-id="53638-297">**1 월 Kronquist 합니다. 반환를 도메인 이벤트를 게시 하지 마십시오! ** 
     [ *https://blog.jayway.com/2013/06/20/dont-publish-domain-events-return-them/*](https://blog.jayway.com/2013/06/20/dont-publish-domain-events-return-them/)</span><span class="sxs-lookup"><span data-stu-id="53638-297">**Jan Kronquist. Don't publish Domain Events, return them!**
[*https://blog.jayway.com/2013/06/20/dont-publish-domain-events-return-them/*](https://blog.jayway.com/2013/06/20/dont-publish-domain-events-return-them/)</span></span>

-   <span data-ttu-id="53638-298">**Cesar de la Torre. 도메인 이벤트 vs입니다. DDD 및 microservices 아키텍처에 대 한 통합 이벤트**
    [*https://blogs.msdn.microsoft.com/cesardelatorre/2017/02/07/domain-events-vs-integration-events-in-domain-driven-design-and-microservices-architectures/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/02/07/domain-events-vs-integration-events-in-domain-driven-design-and-microservices-architectures/)</span><span class="sxs-lookup"><span data-stu-id="53638-298">**Cesar de la Torre. Domain Events vs. Integration Events in DDD and microservices architectures**
[*https://blogs.msdn.microsoft.com/cesardelatorre/2017/02/07/domain-events-vs-integration-events-in-domain-driven-design-and-microservices-architectures/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/02/07/domain-events-vs-integration-events-in-domain-driven-design-and-microservices-architectures/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="53638-299">[이전] (클라이언트 액세스 측면-validation.md) [다음] (인프라-지 속성-계층-design.md)</span><span class="sxs-lookup"><span data-stu-id="53638-299">[Previous] (client-side-validation.md) [Next] (infrastructure-persistence-layer-design.md)</span></span>
