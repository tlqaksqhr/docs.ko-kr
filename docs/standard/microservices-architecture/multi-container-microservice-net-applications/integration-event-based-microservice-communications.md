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
# <a name="implementing-event-based-communication-between-microservices-integration-events"></a>Microservices (통합 이벤트) 간의 이벤트 기반 통신 구현

이벤트 기반 통신을 사용할 경우 앞에서 설명 된 대로 비즈니스 엔터티를 업데이트할 때와 같은 활동이 주목할 만한가 발생 했을 때 이벤트는 마이크로 서비스에 게시 합니다. 다른 microservices 해당 이벤트를 구독 합니다. 마이크로 서비스는 이벤트를 받으면 자체 비즈니스 엔터티 발생할 수 있습니다. 게시 되 고 더 많은 이벤트를 업데이트할 수 있습니다. 이 게시/구독 시스템은 일반적으로 이벤트 버스의 구현을 사용 하 여 수행 됩니다. 이벤트 버스 구독 하 고 이벤트에 구독을 취소 하 고 이벤트를 게시 하는 데 필요한 api 인터페이스로 디자인할 수 있습니다. 메시징 큐 또는 비동기 통신 및 게시/구독 모델을 지 원하는 서비스 버스 등 모든 메시징 또는 프로세스 간 통신을 사용 하 여 하나 이상의 구현을 가질 수도 있습니다.

수 이벤트를 사용 하면 여러 서비스에 걸쳐 있는 비즈니스 트랜잭션을 구현을 해당 서비스 간의 결과적 일관성을 제공 합니다. 결국 일관 된 트랜잭션 일련의 분산된 작업으로 이루어져 있습니다. 각 작업에는 마이크로 서비스는 비즈니스 엔터티를 업데이트 하 고 작업을 트리거하는 이벤트를 게시 합니다.

![](./media/image19.PNG)

**그림 8-18**합니다. 이벤트 버스에 따른 이벤트 기반 통신

이 섹션에서는 그림 8-18에서와 같이 일반 이벤트 버스 인터페이스를 사용 하 여 이러한 유형의.NET와의 통신을 구현 하는 방법을 설명 합니다. 각각 서로 다른 기술 또는 RabbitMQ, Azure 서비스 버스 또는 다른 타사 오픈 소스 또는 상용 서비스 버스와 같은 인프라를 사용 하 여 여러 개의 잠재적인 구현이 있습니다.

## <a name="using-message-brokers-and-services-buses-for-production-systems"></a>메시지 브로커 및 서비스 버스를 사용 하 여 프로덕션 시스템에 대 한

아키텍처 섹션에서 설명한 대로, 추상 이벤트 버스 구현 하기 위한 여러 메시징 기술을 선택할 수 있습니다. 그러나 이러한 기술은 다양 한 수준. 예를 들어, RabbitMQ, 메시징 브로커 전송, Azure 서비스 버스, NServiceBus, MassTransit, 또는 Brighter과 같은 상업용 제품 보다 낮은 수준에서 됩니다. 대부분의 이러한 제품 RabbitMQ 또는 Azure 서비스 버스를 기반으로 작업할 수 있습니다. 선택한 제품의 응용 프로그램에 필요한 기능 및 얼마나-의-즉시 확장성 수에 따라 달라 집니다.

방금는 이벤트 버스의 개념 증명 eShopOnContainers 샘플과 같이 개발 환경에 대 한 구현에 대 한 컨테이너를 실행 하는 RabbitMQ 위에 간단한 구현을 충분 한 수 있습니다. 하지만 대 한 중요 한 높은 확장성을 필요로 하는 프로덕션 시스템을 평가 하 고 Azure 서비스 패브릭을 사용 할 수 있습니다. 상위 수준 추상화 필요 하 고과 같은 다양 한 기능 [sagas](https://docs.particular.net/nservicebus/sagas/) 분산된 개발 NServiceBus, MassTransit, 처럼 쉽게, 기타 상업용 및 오픈 소스 서비스 버스를 구성 하는 장기 실행 프로세스에 대 한 및 영역이 더 평가 해봐야 됩니다. 물론, 항상 RabbitMQ 및 Docker와 같은 하위 수준의 기술 기반으로 사용자 고유의 서비스 버스 기능을 작성할 수 있습니다 하지만 휠을 같은 작업을 반복 하는 데 필요한 작업을 사용자 지정 엔터프라이즈 응용 프로그램에 대 한 비용이 너무 높은 수 있습니다.

다시 말해: 샘플 이벤트 버스 추상화 및 eShopOnContainers 샘플에서 보여 줍니다. 구현 개념 증명으로 사용 하는 데 사용 됩니다. 현재 섹션에서 설명한 대로 비동기 및 이벤트 기반 통신에 사용할 결정 했으면, 요구 사항에 가장 잘 맞는 서비스 버스 제품을 선택 해야 합니다.

## <a name="integration-events"></a>통합 이벤트

통합 이벤트 여러 microservices 또는 외부 시스템과 동기화 도메인 상태 전환에 사용 됩니다. 이 마이크로 서비스 외부 통합 이벤트를 게시 하 여 수행 됩니다. 이벤트에 여러 개의 수신기 microservices 만큼 microservices 통합 이벤트를 구독 하는 대로) (에 게시 되 면 각 수신기 마이크로 서비스에서 적절 한 이벤트 처리기는 이벤트를 처리 합니다.

통합 이벤트는 기본적으로 다음 예제와 같이 데이터를 보유 중인 클래스:

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

통합 이벤트 클래스는 간단할 수 있습니다. 예를 들어 것 ID에 대 한 GUID를 포함 될 수 있습니다.

Viewmodel 서버와 클라이언트에서 정의 하는 방법에 비교 가능한 방식으로 다른 microservices에서 분리 되어 있으므로 각 마이크로 서비스의 응용 프로그램 수준에서 통합 이벤트를 정의할 수 있습니다. 여러 microservices;에서 일반적인 통합 이벤트 라이브러리 공유는 어떤 권장 되지 않습니다. 이렇게 하면 각 것 될 연결 이러한 microservices 단일 이벤트 정의 데이터 라이브러리입니다. 동일한 이유로 여러 microservices에서 공용 도메인 모델을 공유 하지 않도록 하는 작업을 수행 하 고 원하지 않는: microservices 완전히 자치 이어야 합니다.

몇 가지 유형의 microservices 간에 공유 해야 하는 라이브러리 있습니다. 하나는 마찬가지로 최종 응용 프로그램 블록 되는 라이브러리는 [이벤트 버스 클라이언트 API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/BuildingBlocks/EventBus)와 같이, eShopOnContainers 합니다. 다른 JSON 직렬 변환기와 같은 NuGet 구성 요소와 공유 될 수도 있는 도구를 구성 하는 라이브러리입니다.

## <a name="the-event-bus"></a>이벤트 버스

이벤트 버스 명시적으로 주의 해야 할, 그림 8-19에 나와 있는 것 처럼 구성 요소를 요구 하지 않고 microservices 간의 게시/구독-스타일 통신을 허용 합니다.

![](./media/image20.png)

**그림 8-19**합니다. 게시/구독 이벤트 버스를 사용한 기본 사항

이벤트 버스 관련이 Observer 패턴 및 게시-구독 패턴입니다.

### <a name="observer-pattern"></a>Observer 패턴

에 [관찰자 패턴](https://en.wikipedia.org/wiki/Observer_pattern), 기본 개체 (Observable 라고도 함)에 적절 한 정보 (이벤트)를 (관찰자 라고도 함) 관심 있는 다른 개체를 알립니다.

### <a name="publish-subscribe-pubsub-pattern"></a>게시-구독 패턴 (Pub/Sub) 

용도 [Pub/Sub 패턴](https://msdn.microsoft.com/en-us/library/ff649664.aspx) 관찰자 패턴와 같습니다:를 특정 이벤트가 발생할 때 다른 서비스에 알립니다. 하지만 관찰자 및 Pub/Sub 패턴 간에 중요 한 의미 체계 차이점이 있습니다. Pub/Sub 패턴에서 메시지 브로드캐스트 위주로 설명 됩니다. 반면, 관찰자 패턴의 Observable 알 수 없습니다 게 이벤트, 해당 아웃 인스턴스용으로. 즉, Observable (게시자) 알 수 없습니다 (구독자) Observer 인.

### <a name="the-middleman-or-event-bus"></a>Middleman 또는 이벤트 버스 

게시자와 구독자 간에 익명 목적을 어떻게 달성 하려면? 쉬운 방법은 모든 통신을 처리 하는 middleman 수입니다. 이벤트 버스 이러한 하나 middleman 됩니다.

이벤트 버스는 일반적으로 두 부분으로 구성 됩니다.

-   추상 또는 인터페이스입니다.

-   하나 이상의 구현 합니다.

그림 8-19 어떻게는 응용 프로그램의 관점에서 이벤트 버스 불과합니다 Pub/Sub 채널을 볼 수 있습니다. 이 비동기 통신을 구현 하는 방법은 달라질 수 있습니다. 환경 요구 사항 (예를 들어 개발 환경 및 프로덕션)에 따라 둘 간의 교체할 수 있도록 여러 구현을 가질 수 있습니다.

그림 8-20 RabbitMQ, Azure 서비스 버스 또는 NServiceBus, MassTransit 등과 같은 다른 서비스 버스와 같은 기술을 메시징 인프라를 기반으로 여러 번 구현 된 이벤트 버스에 대 한 추상화를 볼 수 있습니다.

![](./media/image21.png)

**그림 8-20입니다.** 이벤트 버스를 여러 번 구현

그러나 강조 표시 된 대로 이전에 추상화 (이벤트 버스 인터페이스)를 사용 하는 추상화 프로그램에서 지 원하는 기본 이벤트 버스 기능이 필요한 경우에 가능 합니다. 다양 한 서비스 버스 기능이 필요 하면 자신의 추상화 하는 대신 기본 service bus에서 제공 하는 API 사용 해야 있습니다.

### <a name="defining-an-event-bus-interface"></a>이벤트 버스 인터페이스 정의

이벤트 버스 인터페이스에 대 한 몇 가지 구현 코드 및 탐색을 위해 가능한 구현 시작 하겠습니다. 인터페이스는 제네릭이 고 다음 인터페이스에서와 같이 간단 하 게 해야 합니다.

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

게시 방법은 간단 합니다. 이벤트 버스에는 해당 이벤트를 구독 하는 마이크로 서비스에 전달 된 통합 이벤트를 브로드캐스트 됩니다. 이 메서드는 이벤트를 게시 하는 마이크로 서비스에서 사용 됩니다.

Subscribe 메서드는 이벤트를 수신 하려는 microservices에서 사용 됩니다. 이 메서드는 두 부분으로 구성 합니다. 첫 번째는 통합 이벤트 (IntegrationEvent) 구독할 수 있습니다. 두 번째 부분은 통합 이벤트 처리기 (또는 콜백 메서드)를 호출 하려면 (IIntegrationEventHandler&lt;T&gt;) 마이크로 서비스는 해당 통합 이벤트 메시지를 받을 때입니다.


>[!div class="step-by-step"]
[이전] (데이터베이스-서버-container.md) [다음] (rabbitmq-event-bus-development-test-environment.md)
