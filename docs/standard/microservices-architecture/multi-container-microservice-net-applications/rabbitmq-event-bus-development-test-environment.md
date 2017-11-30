---
title: "개발 또는 테스트 환경에 대 한 RabbitMQ와 이벤트 버스 구현"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 개발 또는 테스트 환경에 대 한 RabbitMQ와 이벤트 버스 구현"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f58d355b6f5fd31a21791d3b072c77f70f90c387
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-an-event-bus-with-rabbitmq-for-the-development-or-test-environment"></a><span data-ttu-id="9c536-104">개발 또는 테스트 환경에 대 한 RabbitMQ와 이벤트 버스 구현</span><span class="sxs-lookup"><span data-stu-id="9c536-104">Implementing an event bus with RabbitMQ for the development or test environment</span></span>

<span data-ttu-id="9c536-105">eShopOnContainers 응용 프로그램과 컨테이너에서 실행 되는 RabbitMQ 기반 하 여 사용자 지정 이벤트 버스를 만들면 그 사용할지 개발 및 테스트 환경에 대해서만 한다는 것으로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c536-105">We should start by saying that if you create your custom event bus based on RabbitMQ running in a container, as the eShopOnContainers application does, it should be used only for your development and test environments.</span></span> <span data-ttu-id="9c536-106">해야 사용 하지 있습니다 프로덕션 환경에 대 한 프로덕션에 사용 가능한 서비스 버스의 일부로 작성 하는 경우가 아니면 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c536-106">You should not use it for your production environment, unless you are building it as a part of a production-ready service bus.</span></span> <span data-ttu-id="9c536-107">간단한 사용자 지정 이벤트 버스에는 많은 프로덕션에 사용 가능한 중요 한 기능을 상용 서비스 버스는 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c536-107">A simple custom event bus might be missing many production-ready critical features that a commercial service bus has.</span></span>

<span data-ttu-id="9c536-108">이벤트 버스의 eShopOnContainers 사용자 지정 구현을 RabbitMQ API를 사용 하 여 라이브러리는 기본적으로.</span><span class="sxs-lookup"><span data-stu-id="9c536-108">The eShopOnContainers custom implementation of an event bus is basically a library using the RabbitMQ API.</span></span> <span data-ttu-id="9c536-109">구현 그림 8-21 나와 있는 것 처럼 이벤트를 구독, 이벤트를 게시 하 고 이벤트를 수신 microservices가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c536-109">The implementation lets microservices subscribe to events, publish events, and receive events, as shown in Figure 8-21.</span></span>

![](./media/image22.png)

<span data-ttu-id="9c536-110">**그림 8-21입니다.**</span><span class="sxs-lookup"><span data-stu-id="9c536-110">**Figure 8-21.**</span></span> <span data-ttu-id="9c536-111">이벤트 버스의 RabbitMQ 구현</span><span class="sxs-lookup"><span data-stu-id="9c536-111">RabbitMQ implementation of an event bus</span></span>

<span data-ttu-id="9c536-112">코드를 EventBusRabbitMQ 클래스는 제네릭 IEventBus 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="9c536-112">In the code, the EventBusRabbitMQ class implements the generic IEventBus interface.</span></span> <span data-ttu-id="9c536-113">이 기반 종속성 주입 프로덕션 버전에이 개발/테스트 버전에서 교체할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c536-113">This is based on Dependency Injection so that you can swap from this dev/test version to a production version.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Implementation using RabbitMQ API
    //...
```

<span data-ttu-id="9c536-114">샘플 개발/테스트 이벤트 버스의 RabbitMQ 구현은 상용구 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="9c536-114">The RabbitMQ implementation of a sample dev/test event bus is boilerplate code.</span></span> <span data-ttu-id="9c536-115">후에 RabbitMQ 서버 연결을 처리 하 고 큐에 메시지 이벤트를 게시 하기 위한 코드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c536-115">It has to handle the connection to the RabbitMQ server and provide code for publishing a message event to the queues.</span></span> <span data-ttu-id="9c536-116">도 컬렉션의 각 이벤트 유형에 통합 이벤트 처리기의 사전을 구현 하는 경우 이러한 이벤트 유형의 그림 8-21 나와 있는 것 처럼 다른 인스턴스화 및 각 수신기 마이크로 서비스에 대 한 서로 다른 구독을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c536-116">It also has to implement a dictionary of collections of integration event handlers for each event type; these event types can have a different instantiation and different subscriptions for each receiver microservice, as shown in Figure 8-21.</span></span>

## <a name="implementing-a-simple-publish-method-with-rabbitmq"></a><span data-ttu-id="9c536-117">RabbitMQ 사용 하 여 메서드를 게시 하는 간단한 구현</span><span class="sxs-lookup"><span data-stu-id="9c536-117">Implementing a simple publish method with RabbitMQ</span></span>

<span data-ttu-id="9c536-118">다음 코드 RabbitMQ에 대 한 eShopOnContainers 이벤트 버스 구현의 일부 이므로 일반적으로 불필요 개선 하는 경우가 아니면 코딩 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c536-118">The following code is part of the eShopOnContainers event bus implementation for RabbitMQ, so you usually do not need to code it unless you are making improvements.</span></span> <span data-ttu-id="9c536-119">코드는 연결 및 채널 RabbitMQ 갖게 메시지를 만들고 큐에 메시지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c536-119">The code gets a connection and channel to RabbitMQ, creates a message, and then publishes the message into the queue.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Member objects and other methods ...
    // ...

    public void Publish(IntegrationEvent @event)
    {
        var eventName = @event.GetType().Name;
        var factory = new ConnectionFactory() { HostName = _connectionString };
        using (var connection = factory.CreateConnection())
        using (var channel = connection.CreateModel())
        {
            channel.ExchangeDeclare(exchange: _brokerName,
                type: "direct");
            string message = JsonConvert.SerializeObject(@event);
            var body = Encoding.UTF8.GetBytes(message);
            channel.BasicPublish(exchange: _brokerName,
                routingKey: eventName,
                basicProperties: null,
                body: body);
       }
    }
}
```

<span data-ttu-id="9c536-120">[실제 코드](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) 게시의 eShopOnContainers 응용 프로그램에서 메서드를 사용 하 여 향상 됩니다는 [관](https://github.com/App-vNext/Polly) RabbitMQ 컨테이너는 경우 특정 횟수의 작업을 다시 시도 하는 정책을 다시 시도 하십시오. 준비 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="9c536-120">The [actual code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) of the Publish method in the eShopOnContainers application is improved by using a [Polly](https://github.com/App-vNext/Polly) retry policy, which retries the task a certain number of times in case the RabbitMQ container is not ready.</span></span> <span data-ttu-id="9c536-121">이 발생할 수 있습니다 때 docker 작성; 컨테이너 시작 예를 들어 RabbitMQ 컨테이너가 다른 컨테이너 보다 느리게 시작 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c536-121">This can occur when docker-compose is starting the containers; for example, the RabbitMQ container might start more slowly than the other containers.</span></span>

<span data-ttu-id="9c536-122">앞서 언급 했 듯이 여러 가지 가능한 구성이 RabbitMQ에서 하므로이 코드 개발/테스트 환경에만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c536-122">As mentioned earlier, there are many possible configurations in RabbitMQ, so this code should be used only for dev/test environments.</span></span>

## <a name="implementing-the-subscription-code-with-the-rabbitmq-api"></a><span data-ttu-id="9c536-123">RabbitMQ API를 사용 하 여 구독 코드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="9c536-123">Implementing the subscription code with the RabbitMQ API</span></span>

<span data-ttu-id="9c536-124">로 다음 코드는 게시 코드로 RabbitMQ에 대 한 이벤트 버스 구현의 단순화 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c536-124">As with the publish code, the following code is a simplification of part of the event bus implementation for RabbitMQ.</span></span> <span data-ttu-id="9c536-125">다시, 일반적으로 않아도 개선 것만를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c536-125">Again, you usually do not need to change it unless you are improving it.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Member objects and other methods ...
    // ...
    public void Subscribe<T>(IIntegrationEventHandler<T> handler)
        where T : IntegrationEvent
    {
        var eventName = typeof(T).Name;
        if (_handlers.ContainsKey(eventName))
        {
            _handlers[eventName].Add(handler);
        }
        else
        {
            var channel = GetChannel();
            channel.QueueBind(queue: _queueName,
                exchange: _brokerName,
                routingKey: eventName);
            _handlers.Add(eventName, new List<IIntegrationEventHandler>());
            _handlers[eventName].Add(handler);
            _eventTypes.Add(typeof(T));
        }
    }
}
```

<span data-ttu-id="9c536-126">각 이벤트 형식에 대 한 관련된 채널을 RabbitMQ에서 이벤트를 발생 시.</span><span class="sxs-lookup"><span data-stu-id="9c536-126">Each event type has a related channel to get events from RabbitMQ.</span></span> <span data-ttu-id="9c536-127">그런 다음 필요에 따라 채널 및 이벤트 유형 마다 만큼 이벤트 처리기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c536-127">You can then have as many event handlers per channel and event type as needed.</span></span>

<span data-ttu-id="9c536-128">Subscribe 메서드 IIntegrationEventHandler 개체 처럼 현재 마이크로 서비스의 콜백 메서드를 및 해당 관련된 IntegrationEvent 개체를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c536-128">The Subscribe method accepts an IIntegrationEventHandler object, which is like a callback method in the current microservice, plus its related IntegrationEvent object.</span></span> <span data-ttu-id="9c536-129">다음 코드는 클라이언트 마이크로 서비스 당 각 통합 이벤트 형식을 가질 수 있는 이벤트 처리기의 목록에 해당 이벤트 처리기를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c536-129">The code then adds that event handler to the list of event handlers that each integration event type can have per client microservice.</span></span> <span data-ttu-id="9c536-130">클라이언트 코드는 이벤트를 이미 구독 하지 않은 경우 다른 서비스에서 해당 이벤트를 게시할 때 밀어넣기 스타일 RabbitMQ로 이벤트를 받을 수 있도록 코드 이벤트 형식에 대 한 채널을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9c536-130">If the client code has not already been subscribed to the event, the code creates a channel for the event type so it can receive events in a push style from RabbitMQ when that event is published from any other service.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="9c536-131">[이전] (통합-이벤트-기반-마이크로 서비스-communications.md) [다음] (구독 events.md)</span><span class="sxs-lookup"><span data-stu-id="9c536-131">[Previous] (integration-event-based-microservice-communications.md) [Next] (subscribe-events.md)</span></span>
