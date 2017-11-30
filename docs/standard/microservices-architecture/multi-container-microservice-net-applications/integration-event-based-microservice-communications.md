---
title: "Microservices (통합 이벤트) 간의 이벤트 기반 통신 구현"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | Microservices (통합 이벤트) 간의 이벤트 기반 통신 구현"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: e438607ab3549d63b89bef6af64c6723a4cac950
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-event-based-communication-between-microservices-integration-events"></a><span data-ttu-id="f11b1-104">Microservices (통합 이벤트) 간의 이벤트 기반 통신 구현</span><span class="sxs-lookup"><span data-stu-id="f11b1-104">Implementing event-based communication between microservices (integration events)</span></span>

<span data-ttu-id="f11b1-105">이벤트 기반 통신을 사용할 경우 앞에서 설명 된 대로 비즈니스 엔터티를 업데이트할 때와 같은 활동이 주목할 만한가 발생 했을 때 이벤트는 마이크로 서비스에 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-105">As described earlier, when you use event-based communication, a microservice publishes an event when something notable happens, such as when it updates a business entity.</span></span> <span data-ttu-id="f11b1-106">다른 microservices 해당 이벤트를 구독 합니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-106">Other microservices subscribe to those events.</span></span> <span data-ttu-id="f11b1-107">마이크로 서비스는 이벤트를 받으면 자체 비즈니스 엔터티 발생할 수 있습니다. 게시 되 고 더 많은 이벤트를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-107">When a microservice receives an event, it can update its own business entities, which might lead to more events being published.</span></span> <span data-ttu-id="f11b1-108">이 게시/구독 시스템은 일반적으로 이벤트 버스의 구현을 사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-108">This publish/subscribe system is usually performed by using an implementation of an event bus.</span></span> <span data-ttu-id="f11b1-109">이벤트 버스 구독 하 고 이벤트에 구독을 취소 하 고 이벤트를 게시 하는 데 필요한 api 인터페이스로 디자인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-109">The event bus can be designed as an interface with the API needed to subscribe and unsubscribe to events and to publish events.</span></span> <span data-ttu-id="f11b1-110">메시징 큐 또는 비동기 통신 및 게시/구독 모델을 지 원하는 서비스 버스 등 모든 메시징 또는 프로세스 간 통신을 사용 하 여 하나 이상의 구현을 가질 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-110">It can also have one or more implementations based on any inter-process or messaging communication, such as a messaging queue or a service bus that supports asynchronous communication and a publish/subscribe model.</span></span>

<span data-ttu-id="f11b1-111">수 이벤트를 사용 하면 여러 서비스에 걸쳐 있는 비즈니스 트랜잭션을 구현을 해당 서비스 간의 결과적 일관성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-111">You can use events to implement business transactions that span multiple services, which gives you eventual consistency between those services.</span></span> <span data-ttu-id="f11b1-112">결국 일관 된 트랜잭션 일련의 분산된 작업으로 이루어져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-112">An eventually consistent transaction consists of a series of distributed actions.</span></span> <span data-ttu-id="f11b1-113">각 작업에는 마이크로 서비스는 비즈니스 엔터티를 업데이트 하 고 작업을 트리거하는 이벤트를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-113">At each action, the microservice updates a business entity and publishes an event that triggers the next action.</span></span>

![](./media/image19.PNG)

<span data-ttu-id="f11b1-114">**그림 8-18**합니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-114">**Figure 8-18**.</span></span> <span data-ttu-id="f11b1-115">이벤트 버스에 따른 이벤트 기반 통신</span><span class="sxs-lookup"><span data-stu-id="f11b1-115">Event-driven communication based on an event bus</span></span>

<span data-ttu-id="f11b1-116">이 섹션에서는 그림 8-18에서와 같이 일반 이벤트 버스 인터페이스를 사용 하 여 이러한 유형의.NET와의 통신을 구현 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-116">This section describes how you can implement this type of communication with .NET by using a generic event bus interface, as shown in Figure 8-18.</span></span> <span data-ttu-id="f11b1-117">각각 서로 다른 기술 또는 RabbitMQ, Azure 서비스 버스 또는 다른 타사 오픈 소스 또는 상용 서비스 버스와 같은 인프라를 사용 하 여 여러 개의 잠재적인 구현이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-117">There are multiple potential implementations, each using a different technology or infrastructure such as RabbitMQ, Azure Service Bus, or any other third-party open source or commercial service bus.</span></span>

## <a name="using-message-brokers-and-services-buses-for-production-systems"></a><span data-ttu-id="f11b1-118">메시지 브로커 및 서비스 버스를 사용 하 여 프로덕션 시스템에 대 한</span><span class="sxs-lookup"><span data-stu-id="f11b1-118">Using message brokers and services buses for production systems</span></span>

<span data-ttu-id="f11b1-119">아키텍처 섹션에서 설명한 대로, 추상 이벤트 버스 구현 하기 위한 여러 메시징 기술을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-119">As noted in the architecture section, you can choose from multiple messaging technologies for implementing your abstract event bus.</span></span> <span data-ttu-id="f11b1-120">그러나 이러한 기술은 다양 한 수준.</span><span class="sxs-lookup"><span data-stu-id="f11b1-120">But these technologies are at different levels.</span></span> <span data-ttu-id="f11b1-121">예를 들어, RabbitMQ, 메시징 브로커 전송, Azure 서비스 버스, NServiceBus, MassTransit, 또는 Brighter과 같은 상업용 제품 보다 낮은 수준에서 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-121">For instance, RabbitMQ, a messaging broker transport, is at a lower level than commercial products like Azure Service Bus, NServiceBus, MassTransit, or Brighter.</span></span> <span data-ttu-id="f11b1-122">대부분의 이러한 제품 RabbitMQ 또는 Azure 서비스 버스를 기반으로 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-122">Most of these products can work on top of either RabbitMQ or Azure Service Bus.</span></span> <span data-ttu-id="f11b1-123">선택한 제품의 응용 프로그램에 필요한 기능 및 얼마나-의-즉시 확장성 수에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-123">Your choice of product depends on how many features and how much out-of-the-box scalability you need for your application.</span></span>

<span data-ttu-id="f11b1-124">방금는 이벤트 버스의 개념 증명 eShopOnContainers 샘플과 같이 개발 환경에 대 한 구현에 대 한 컨테이너를 실행 하는 RabbitMQ 위에 간단한 구현을 충분 한 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-124">For implementing just an event bus proof-of-concept for your development environment, as in the eShopOnContainers sample, a simple implementation on top of RabbitMQ running as a container might be enough.</span></span> <span data-ttu-id="f11b1-125">하지만 대 한 중요 한 높은 확장성을 필요로 하는 프로덕션 시스템을 평가 하 고 Azure 서비스 패브릭을 사용 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-125">But for mission-critical and production systems that need high scalability, you might want to evaluate and use Azure Service Fabric.</span></span> <span data-ttu-id="f11b1-126">상위 수준 추상화 필요 하 고과 같은 다양 한 기능 [sagas](https://docs.particular.net/nservicebus/sagas/) 분산된 개발 NServiceBus, MassTransit, 처럼 쉽게, 기타 상업용 및 오픈 소스 서비스 버스를 구성 하는 장기 실행 프로세스에 대 한 및 영역이 더 평가 해봐야 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-126">If you require high-level abstractions and richer features like [sagas](https://docs.particular.net/nservicebus/sagas/) for long-running processes that make distributed development easier, other commercial and open-source service buses like NServiceBus, MassTransit, and Brighter are worth evaluating.</span></span> <span data-ttu-id="f11b1-127">물론, 항상 RabbitMQ 및 Docker와 같은 하위 수준의 기술 기반으로 사용자 고유의 서비스 버스 기능을 작성할 수 있습니다 하지만 휠을 같은 작업을 반복 하는 데 필요한 작업을 사용자 지정 엔터프라이즈 응용 프로그램에 대 한 비용이 너무 높은 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-127">Of course, you could always build your own service bus features on top of lower-level technologies like RabbitMQ and Docker, but the work needed to reinvent the wheel might be too costly for a custom enterprise application.</span></span>

<span data-ttu-id="f11b1-128">다시 말해: 샘플 이벤트 버스 추상화 및 eShopOnContainers 샘플에서 보여 줍니다. 구현 개념 증명으로 사용 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-128">To reiterate: the sample event bus abstractions and implementation showcased in the eShopOnContainers sample are intended to be used only as a proof of concept.</span></span> <span data-ttu-id="f11b1-129">현재 섹션에서 설명한 대로 비동기 및 이벤트 기반 통신에 사용할 결정 했으면, 요구 사항에 가장 잘 맞는 서비스 버스 제품을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-129">Once you have decided that you want to have asynchronous and event-driven communication, as explained in the current section, you should choose the service bus product that best fits your needs.</span></span>

## <a name="integration-events"></a><span data-ttu-id="f11b1-130">통합 이벤트</span><span class="sxs-lookup"><span data-stu-id="f11b1-130">Integration events</span></span>

<span data-ttu-id="f11b1-131">통합 이벤트 여러 microservices 또는 외부 시스템과 동기화 도메인 상태 전환에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-131">Integration events are used for bringing domain state in sync across multiple microservices or external systems.</span></span> <span data-ttu-id="f11b1-132">이 마이크로 서비스 외부 통합 이벤트를 게시 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-132">This is done by publishing integration events outside the microservice.</span></span> <span data-ttu-id="f11b1-133">이벤트에 여러 개의 수신기 microservices 만큼 microservices 통합 이벤트를 구독 하는 대로) (에 게시 되 면 각 수신기 마이크로 서비스에서 적절 한 이벤트 처리기는 이벤트를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-133">When an event is published to multiple receiver microservices (to as many microservices as are subscribed to the integration event), the appropriate event handler in each receiver microservice handles the event.</span></span>

<span data-ttu-id="f11b1-134">통합 이벤트는 기본적으로 다음 예제와 같이 데이터를 보유 중인 클래스:</span><span class="sxs-lookup"><span data-stu-id="f11b1-134">An integration event is basically a data-holding class, as in the following example:</span></span>

```csharp
public class ProductPriceChangedIntegrationEvent : IntegrationEvent
{
    public int ProductId { get; private set; }
    public decimal NewPrice { get; private set; }
    public decimal OldPrice { get; private set; }

    public ProductPriceChangedIntegrationEvent(int productId, decimal newPrice,
        decimal oldPrice)
    {
        ProductId = productId;
        NewPrice = newPrice;
        OldPrice = oldPrice;
    }
}
```

<span data-ttu-id="f11b1-135">통합 이벤트 클래스는 간단할 수 있습니다. 예를 들어 것 ID에 대 한 GUID를 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-135">The integration event class can be simple; for example, it might contain a GUID for its ID.</span></span>

<span data-ttu-id="f11b1-136">Viewmodel 서버와 클라이언트에서 정의 하는 방법에 비교 가능한 방식으로 다른 microservices에서 분리 되어 있으므로 각 마이크로 서비스의 응용 프로그램 수준에서 통합 이벤트를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-136">The integration events can be defined at the application level of each microservice, so they are decoupled from other microservices, in a way comparable to how ViewModels are defined in the server and client.</span></span> <span data-ttu-id="f11b1-137">여러 microservices;에서 일반적인 통합 이벤트 라이브러리 공유는 어떤 권장 되지 않습니다. 이렇게 하면 각 것 될 연결 이러한 microservices 단일 이벤트 정의 데이터 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-137">What is not recommended is sharing a common integration events library across multiple microservices; doing that would be coupling those microservices with a single event definition data library.</span></span> <span data-ttu-id="f11b1-138">동일한 이유로 여러 microservices에서 공용 도메인 모델을 공유 하지 않도록 하는 작업을 수행 하 고 원하지 않는: microservices 완전히 자치 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-138">You do not want to do that for the same reasons that you do not want to share a common domain model across multiple microservices: microservices must be completely autonomous.</span></span>

<span data-ttu-id="f11b1-139">몇 가지 유형의 microservices 간에 공유 해야 하는 라이브러리 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-139">There are only a few kinds of libraries you should share across microservices.</span></span> <span data-ttu-id="f11b1-140">하나는 마찬가지로 최종 응용 프로그램 블록 되는 라이브러리는 [이벤트 버스 클라이언트 API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/BuildingBlocks/EventBus)와 같이, eShopOnContainers 합니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-140">One is libraries that are final application blocks, like the [Event Bus client API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/BuildingBlocks/EventBus), as in eShopOnContainers.</span></span> <span data-ttu-id="f11b1-141">다른 JSON 직렬 변환기와 같은 NuGet 구성 요소와 공유 될 수도 있는 도구를 구성 하는 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-141">Another is libraries that constitute tools that could also be shared as NuGet components, like JSON serializers.</span></span>

## <a name="the-event-bus"></a><span data-ttu-id="f11b1-142">이벤트 버스</span><span class="sxs-lookup"><span data-stu-id="f11b1-142">The event bus</span></span>

<span data-ttu-id="f11b1-143">이벤트 버스 명시적으로 주의 해야 할, 그림 8-19에 나와 있는 것 처럼 구성 요소를 요구 하지 않고 microservices 간의 게시/구독-스타일 통신을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-143">An event bus allows publish/subscribe-style communication between microservices without requiring the components to explicitly be aware of each other, as shown in Figure 8-19.</span></span>

![](./media/image20.png)

<span data-ttu-id="f11b1-144">**그림 8-19**합니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-144">**Figure 8-19**.</span></span> <span data-ttu-id="f11b1-145">게시/구독 이벤트 버스를 사용한 기본 사항</span><span class="sxs-lookup"><span data-stu-id="f11b1-145">Publish/subscribe basics with an event bus</span></span>

<span data-ttu-id="f11b1-146">이벤트 버스 관련이 Observer 패턴 및 게시-구독 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-146">The event bus is related to the Observer pattern and the publish-subscribe pattern.</span></span>

### <a name="observer-pattern"></a><span data-ttu-id="f11b1-147">Observer 패턴</span><span class="sxs-lookup"><span data-stu-id="f11b1-147">Observer pattern</span></span>

<span data-ttu-id="f11b1-148">에 [관찰자 패턴](https://en.wikipedia.org/wiki/Observer_pattern), 기본 개체 (Observable 라고도 함)에 적절 한 정보 (이벤트)를 (관찰자 라고도 함) 관심 있는 다른 개체를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-148">In the [Observer pattern](https://en.wikipedia.org/wiki/Observer_pattern), your primary object (known as the Observable) notifies other interested objects (known as Observers) with relevant information (events).</span></span>

### <a name="publish-subscribe-pubsub-pattern"></a><span data-ttu-id="f11b1-149">게시-구독 패턴 (Pub/Sub)</span><span class="sxs-lookup"><span data-stu-id="f11b1-149">Publish-subscribe (Pub/Sub) pattern</span></span> 

<span data-ttu-id="f11b1-150">용도 [Pub/Sub 패턴](https://msdn.microsoft.com/en-us/library/ff649664.aspx) 관찰자 패턴와 같습니다:를 특정 이벤트가 발생할 때 다른 서비스에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-150">The purpose of the [Pub/Sub pattern](https://msdn.microsoft.com/en-us/library/ff649664.aspx) is the same as the Observer pattern: you want to notify other services when certain events take place.</span></span> <span data-ttu-id="f11b1-151">하지만 관찰자 및 Pub/Sub 패턴 간에 중요 한 의미 체계 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-151">But there is an important semantic difference between the Observer and Pub/Sub patterns.</span></span> <span data-ttu-id="f11b1-152">Pub/Sub 패턴에서 메시지 브로드캐스트 위주로 설명 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-152">In the Pub/Sub pattern, the focus is on broadcasting messages.</span></span> <span data-ttu-id="f11b1-153">반면, 관찰자 패턴의 Observable 알 수 없습니다 게 이벤트, 해당 아웃 인스턴스용으로. 즉, Observable (게시자) 알 수 없습니다 (구독자) Observer 인.</span><span class="sxs-lookup"><span data-stu-id="f11b1-153">In contrast, in the Observer pattern, the Observable does not know who the events are going to, just that they have gone out. In other words, the Observable (the publisher) does not know who the Observers (the subscribers) are.</span></span>

### <a name="the-middleman-or-event-bus"></a><span data-ttu-id="f11b1-154">Middleman 또는 이벤트 버스</span><span class="sxs-lookup"><span data-stu-id="f11b1-154">The middleman or event bus</span></span> 

<span data-ttu-id="f11b1-155">게시자와 구독자 간에 익명 목적을 어떻게 달성 하려면?</span><span class="sxs-lookup"><span data-stu-id="f11b1-155">How do you achieve anonymity between publisher and subscriber?</span></span> <span data-ttu-id="f11b1-156">쉬운 방법은 모든 통신을 처리 하는 middleman 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-156">An easy way is let a middleman take care of all the communication.</span></span> <span data-ttu-id="f11b1-157">이벤트 버스 이러한 하나 middleman 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-157">An event bus is one such middleman.</span></span>

<span data-ttu-id="f11b1-158">이벤트 버스는 일반적으로 두 부분으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-158">An event bus is typically composed of two parts:</span></span>

-   <span data-ttu-id="f11b1-159">추상 또는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-159">The abstraction or interface.</span></span>

-   <span data-ttu-id="f11b1-160">하나 이상의 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-160">One or more implementations.</span></span>

<span data-ttu-id="f11b1-161">그림 8-19 어떻게는 응용 프로그램의 관점에서 이벤트 버스 불과합니다 Pub/Sub 채널을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-161">In Figure 8-19 you can see how, from an application point of view, the event bus is nothing more than a Pub/Sub channel.</span></span> <span data-ttu-id="f11b1-162">이 비동기 통신을 구현 하는 방법은 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-162">The way you implement this asynchronous communication can vary.</span></span> <span data-ttu-id="f11b1-163">환경 요구 사항 (예를 들어 개발 환경 및 프로덕션)에 따라 둘 간의 교체할 수 있도록 여러 구현을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-163">It can have multiple implementations so that you can swap between them, depending on the environment requirements (for example, production versus development environments).</span></span>

<span data-ttu-id="f11b1-164">그림 8-20 RabbitMQ, Azure 서비스 버스 또는 NServiceBus, MassTransit 등과 같은 다른 서비스 버스와 같은 기술을 메시징 인프라를 기반으로 여러 번 구현 된 이벤트 버스에 대 한 추상화를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-164">In Figure 8-20 you can see an abstraction of an event bus with multiple implementations based on infrastructure messaging technologies like RabbitMQ, Azure Service Bus, or other service buses like NServiceBus, MassTransit, etc.</span></span>

![](./media/image21.png)

<span data-ttu-id="f11b1-165">**그림 8-20입니다.**</span><span class="sxs-lookup"><span data-stu-id="f11b1-165">**Figure 8- 20.**</span></span> <span data-ttu-id="f11b1-166">이벤트 버스를 여러 번 구현</span><span class="sxs-lookup"><span data-stu-id="f11b1-166">Multiple implementations of an event bus</span></span>

<span data-ttu-id="f11b1-167">그러나 강조 표시 된 대로 이전에 추상화 (이벤트 버스 인터페이스)를 사용 하는 추상화 프로그램에서 지 원하는 기본 이벤트 버스 기능이 필요한 경우에 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-167">However, as highlighted previously, using abstractions (the event bus interface) is possible only if you need basic event bus features supported by your abstractions.</span></span> <span data-ttu-id="f11b1-168">다양 한 서비스 버스 기능이 필요 하면 자신의 추상화 하는 대신 기본 service bus에서 제공 하는 API 사용 해야 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-168">If you need richer service bus features, you should probably use the API provided by your preferred service bus instead of your own abstractions.</span></span>

### <a name="defining-an-event-bus-interface"></a><span data-ttu-id="f11b1-169">이벤트 버스 인터페이스 정의</span><span class="sxs-lookup"><span data-stu-id="f11b1-169">Defining an event bus interface</span></span>

<span data-ttu-id="f11b1-170">이벤트 버스 인터페이스에 대 한 몇 가지 구현 코드 및 탐색을 위해 가능한 구현 시작 하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-170">Let’s start with some implementation code for the event bus interface and possible implementations for exploration purposes.</span></span> <span data-ttu-id="f11b1-171">인터페이스는 제네릭이 고 다음 인터페이스에서와 같이 간단 하 게 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-171">The interface should be generic and straightforward, as in the following interface.</span></span>

```csharp
public interface IEventBus
{
    void Publish(IntegrationEvent @event);
    void Subscribe<T>(IIntegrationEventHandler<T> handler)
        where T: IntegrationEvent;

    void Unsubscribe<T>(IIntegrationEventHandler<T> handler)
        where T : IntegrationEvent;
}
```

<span data-ttu-id="f11b1-172">게시 방법은 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-172">The Publish method is straightforward.</span></span> <span data-ttu-id="f11b1-173">이벤트 버스에는 해당 이벤트를 구독 하는 마이크로 서비스에 전달 된 통합 이벤트를 브로드캐스트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-173">The event bus will broadcast the integration event passed to it to any microservice subscribed to that event.</span></span> <span data-ttu-id="f11b1-174">이 메서드는 이벤트를 게시 하는 마이크로 서비스에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-174">This method is used by the microservice that is publishing the event.</span></span>

<span data-ttu-id="f11b1-175">Subscribe 메서드는 이벤트를 수신 하려는 microservices에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-175">The Subscribe method is used by the microservices that want to receive events.</span></span> <span data-ttu-id="f11b1-176">이 메서드는 두 부분으로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-176">This method has two parts.</span></span> <span data-ttu-id="f11b1-177">첫 번째는 통합 이벤트 (IntegrationEvent) 구독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-177">The first is the integration event to subscribe to (IntegrationEvent).</span></span> <span data-ttu-id="f11b1-178">두 번째 부분은 통합 이벤트 처리기 (또는 콜백 메서드)를 호출 하려면 (IIntegrationEventHandler&lt;T&gt;) 마이크로 서비스는 해당 통합 이벤트 메시지를 받을 때입니다.</span><span class="sxs-lookup"><span data-stu-id="f11b1-178">The second part is the integration event handler (or callback method) to be called (IIntegrationEventHandler&lt;T&gt;) when the microservice receives that integration event message.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="f11b1-179">[이전] (데이터베이스-서버-container.md) [다음] (rabbitmq-event-bus-development-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="f11b1-179">[Previous] (database-server-container.md) [Next] (rabbitmq-event-bus-development-test-environment.md)</span></span>
