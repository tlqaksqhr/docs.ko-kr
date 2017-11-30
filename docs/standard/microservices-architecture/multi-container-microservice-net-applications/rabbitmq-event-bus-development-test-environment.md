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
# <a name="implementing-an-event-bus-with-rabbitmq-for-the-development-or-test-environment"></a>개발 또는 테스트 환경에 대 한 RabbitMQ와 이벤트 버스 구현

eShopOnContainers 응용 프로그램과 컨테이너에서 실행 되는 RabbitMQ 기반 하 여 사용자 지정 이벤트 버스를 만들면 그 사용할지 개발 및 테스트 환경에 대해서만 한다는 것으로 시작 해야 합니다. 해야 사용 하지 있습니다 프로덕션 환경에 대 한 프로덕션에 사용 가능한 서비스 버스의 일부로 작성 하는 경우가 아니면 합니다. 간단한 사용자 지정 이벤트 버스에는 많은 프로덕션에 사용 가능한 중요 한 기능을 상용 서비스 버스는 없을 수 있습니다.

이벤트 버스의 eShopOnContainers 사용자 지정 구현을 RabbitMQ API를 사용 하 여 라이브러리는 기본적으로. 구현 그림 8-21 나와 있는 것 처럼 이벤트를 구독, 이벤트를 게시 하 고 이벤트를 수신 microservices가 있습니다.

![](./media/image22.png)

**그림 8-21입니다.** 이벤트 버스의 RabbitMQ 구현

코드를 EventBusRabbitMQ 클래스는 제네릭 IEventBus 인터페이스를 구현합니다. 이 기반 종속성 주입 프로덕션 버전에이 개발/테스트 버전에서 교체할 수 있도록 합니다.

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Implementation using RabbitMQ API
    //...
```

샘플 개발/테스트 이벤트 버스의 RabbitMQ 구현은 상용구 코드입니다. 후에 RabbitMQ 서버 연결을 처리 하 고 큐에 메시지 이벤트를 게시 하기 위한 코드를 제공 합니다. 도 컬렉션의 각 이벤트 유형에 통합 이벤트 처리기의 사전을 구현 하는 경우 이러한 이벤트 유형의 그림 8-21 나와 있는 것 처럼 다른 인스턴스화 및 각 수신기 마이크로 서비스에 대 한 서로 다른 구독을 가질 수 있습니다.

## <a name="implementing-a-simple-publish-method-with-rabbitmq"></a>RabbitMQ 사용 하 여 메서드를 게시 하는 간단한 구현

다음 코드 RabbitMQ에 대 한 eShopOnContainers 이벤트 버스 구현의 일부 이므로 일반적으로 불필요 개선 하는 경우가 아니면 코딩 하 합니다. 코드는 연결 및 채널 RabbitMQ 갖게 메시지를 만들고 큐에 메시지를 게시 합니다.

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

[실제 코드](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) 게시의 eShopOnContainers 응용 프로그램에서 메서드를 사용 하 여 향상 됩니다는 [관](https://github.com/App-vNext/Polly) RabbitMQ 컨테이너는 경우 특정 횟수의 작업을 다시 시도 하는 정책을 다시 시도 하십시오. 준비 되지 않았습니다. 이 발생할 수 있습니다 때 docker 작성; 컨테이너 시작 예를 들어 RabbitMQ 컨테이너가 다른 컨테이너 보다 느리게 시작 수도 있습니다.

앞서 언급 했 듯이 여러 가지 가능한 구성이 RabbitMQ에서 하므로이 코드 개발/테스트 환경에만 사용 해야 합니다.

## <a name="implementing-the-subscription-code-with-the-rabbitmq-api"></a>RabbitMQ API를 사용 하 여 구독 코드를 구현합니다.

로 다음 코드는 게시 코드로 RabbitMQ에 대 한 이벤트 버스 구현의 단순화 합니다. 다시, 일반적으로 않아도 개선 것만를 변경 합니다.

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

각 이벤트 형식에 대 한 관련된 채널을 RabbitMQ에서 이벤트를 발생 시. 그런 다음 필요에 따라 채널 및 이벤트 유형 마다 만큼 이벤트 처리기를 사용할 수 있습니다.

Subscribe 메서드 IIntegrationEventHandler 개체 처럼 현재 마이크로 서비스의 콜백 메서드를 및 해당 관련된 IntegrationEvent 개체를 허용 합니다. 다음 코드는 클라이언트 마이크로 서비스 당 각 통합 이벤트 형식을 가질 수 있는 이벤트 처리기의 목록에 해당 이벤트 처리기를 추가 합니다. 클라이언트 코드는 이벤트를 이미 구독 하지 않은 경우 다른 서비스에서 해당 이벤트를 게시할 때 밀어넣기 스타일 RabbitMQ로 이벤트를 받을 수 있도록 코드 이벤트 형식에 대 한 채널을 만듭니다.


>[!div class="step-by-step"]
[이전] (통합-이벤트-기반-마이크로 서비스-communications.md) [다음] (구독 events.md)
