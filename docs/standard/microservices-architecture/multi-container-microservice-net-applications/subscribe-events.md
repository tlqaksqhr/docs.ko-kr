---
title: "이벤트 구독"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 이벤트 구독"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: fe17b53a39ff2964cd60183e291e2936d3ba28df
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="subscribing-to-events"></a>이벤트 구독

이벤트 버스를 사용 하기 위한 첫 번째 단계 microservices 수신 하려는 이벤트를 구독 하는 것입니다. 수신기 microservices에서 수행 되어야 합니다.

다음과 같은 간단한 코드 서비스를 시작할 때 구현 해야 하는 각 수신기 마이크로 서비스를 보여 줍니다 (즉,를 시작 하는 클래스) 하므로 구독 이벤트를이 필요 합니다. 예를 들어, basket.api 마이크로 서비스 ProductPriceChangedIntegrationEvent 메시지에 등록 해야 합니다. 이 제품 가격을는 마이크로 서비스를 한 모든 변경 내용을 인식 하 고 해당 제품을 사용자의 알려진 문제점을 해결 하는 경우 변경에 대 한 사용자에 게 경고 수입니다.

```csharp
var eventBus = app.ApplicationServices.GetRequiredService<IEventBus>();
eventBus.Subscribe<ProductPriceChangedIntegrationEvent>(
    ProductPriceChangedIntegrationEventHandler);
```

이 코드를 실행 한 후 구독자 마이크로 서비스 RabbitMQ 채널을 통해 수신 하 게 됩니다. ProductPriceChangedIntegrationEvent 유형의 모든 메시지 도착 하면 코드에 전달 하 고 이벤트를 처리 하는 이벤트 처리기를 호출 합니다.

## <a name="publishing-events-through-the-event-bus"></a>이벤트 버스를 통해 이벤트를 게시합니다.

마지막으로, 메시지 보낸 사람 (원점 마이크로 서비스)는 다음 예제와 비슷한 코드와 함께 통합 이벤트를 게시합니다. (이 계정에 대 한 원자성을 사용 하지 않는 간단한 예입니다.) 이벤트 데이터 또는 원본 마이크로 서비스에서 트랜잭션을 커밋한 후 일반적으로 오른쪽 여러 microservices를 통해 전파 해야 때마다 비슷한 코드를 구현 합니다.

첫째, 이벤트 버스 구현 개체 (RabbitMQ에 따라 또는 서비스 버스에 따라) 다음 코드 에서처럼 컨트롤러 생성자에 삽입 합니다.

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

그런 다음 하면 컨트롤러의 메서드에서 처럼 사용할 UpdateProduct 메서드:

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

이 경우 origin 마이크로 서비스 간단한 CRUD 마이크로 서비스 이므로, 해당 코드는 Web API 컨트롤러에 오른쪽을 배치 됩니다. 더 많은 고급 microservices 것 구현할 수 있습니다 CommandHandler 클래스 오른쪽에서 원래 데이터는 커밋된 후.

### <a name="designing-atomicity-and-resiliency-when-publishing-to-the-event-bus"></a>이벤트 버스에 게시할 때 원자성 및 탄력성 디자인

분산 메시징를 통해 통합 이벤트를 게시할 때 시스템 마찬가지로 이벤트 버스를 원자적으로 원래 데이터베이스를 업데이트 하 고 이벤트를 게시 하는 문제를 수 있습니다. 예를 들어, 앞에 표시 된 간단한 예제에서는 코드에서 커밋 데이터 데이터베이스에 제품 가격 변경 되 고 다음 ProductPriceChangedIntegrationEvent 메시지를 게시 합니다. 처음 두 가지 동작 하나씩 수행 될 필수 보일 수 있습니다. 그러나 관련 된 분산된 트랜잭션을 사용 하는 경우 데이터베이스와 메시지 브로커와 같은 이전 시스템에서와 마찬가지로 [Microsoft 메시지 큐 (MSMQ)](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx)는 에설명된이유로권장되지않습니다[CAP 정리](https://www.quora.com/What-Is-CAP-Theorem-1)합니다.

기본적으로, 사용 microservices 확장 가능 하 고 항상 사용 가능한 시스템을 구축 합니다. 어느 정도 쉽게 CAP 정리에 따르면 데이터베이스 (또는 해당 모델을 소유 하는 마이크로 서비스)를 빌드할 수 없습니다 지속적으로 사용할 수 있는, 일관성이 매우 *및* 파티션의에 적절 하 게 합니다. 이러한 세 가지 속성을 선택 해야 합니다.

Microservices 기반 아키텍처의 가용성 및 내결함성을 선택 해야 하 고 강력한 일관성을 곱하면가 낮아집니다 해야 합니다. 따라서 대부분의 요즘 마이크로 서비스 기반 응용 프로그램에서 일반적으로 원하지 않는 메시징에서는 분산된 트랜잭션을 사용 하도록 구현 하는 경우와 마찬가지로 [분산 트랜잭션](https://msdn.microsoft.com/library/ms978430.aspx#bdadotnetasync2_topic3c) Windows 분산 트랜잭션 기반 Coordinator (DTC)와 [MSMQ](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx)합니다.

초기 문제 및 해당 예제에 다시 해 보겠습니다. 데이터베이스를 업데이트 한 후 서비스가 손상 될 경우 (이 경우 사용 하 여 코드의 줄 다음 마우스 오른쪽 단추로 \_컨텍스트. SaveChangesAsync()), 하지만 전체 시스템 통합 이벤트를 게시 하기 전에 일치 하지 않는 될 수 있습니다. 이 처리 하는 특정 비즈니스 작업에 따라 중요 한 비즈니스 수 있습니다.

아키텍처 섹션에서 설명한 바와 같이이 문제를 처리 하기 위한 여러 가지 방법으로 가질 수 있습니다.

-   전체를 사용 하 여 [이벤트 소싱 패턴](https://msdn.microsoft.com/en-us/library/dn589792.aspx)합니다.

-   사용 하 여 [트랜잭션 로그 마이닝](http://www.scoop.it/t/sql-server-transaction-log-mining)합니다.

-   사용 하 여 [보낼 편지함 패턴](http://gistlabs.com/2014/05/the-outbox/)합니다. 이것이 (로컬 트랜잭션을 확장) 통합 이벤트를 저장 하는 트랜잭션 테이블입니다.

이 시나리오에서 전체 이벤트 소싱 (ES) 패턴을 사용 하는 가장 좋은 방법 중 하나 그렇지 않은 경우 *는* 가장 합니다. 그러나 대부분의 응용 프로그램 시나리오에서 있습니다 못할 전체 ES 시스템을 구현 하 합니다. ES 의미 도메인 이벤트만 현재 상태 데이터를 저장 하는 대신 트랜잭션 데이터베이스에 저장 합니다. 도메인 이벤트만 저장 등 사용 가능한 시스템의 기록 및 과거의 모든 시점에서 시스템의 상태를 발견할 때 큰 혜택을 가질 수 있습니다. 그러나 전체 ES 시스템을 구현 하려면 대부분의 시스템 아키텍처를 변경 해야 고 다른 복잡 하 고 요구 사항을 소개 합니다. 예를 들어 특별히 설정 된 이벤트 소싱에 대 한 같은 데이터베이스를 사용 하도록 원할 [이벤트 저장소](https://geteventstore.com/), 또는 Azure Cosmos DB, MongoDB, Cassandra, CouchDB, 또는 RavenDB 같은 문서 관련 데이터베이스입니다. ES는 효과적입니다.이 문제를 있지만 가장 쉬운 솔루션 하지 않는 이벤트 소싱 된 하 던입니다.

처음 마이닝 트랜잭션 로그를 사용 하는 옵션은 매우 투명 하 게 찾습니다. 그러나이 방법을 사용 하려면 SQL Server 트랜잭션 로그와 같은 프로그램 RDBMS 트랜잭션 로그에 연결 하는 마이크로 서비스에 있습니다. 이것이 바람직하지 않은 것입니다. 또 다른 단점이입니다 트랜잭션 로그에 기록 된 하위 수준 업데이트에 높은 수준의 통합 이벤트와 같은 수준에 없을 수 있습니다. 이 경우 리버스 엔지니어링 프로세스 해당 트랜잭션 로그 작업이 어려울 수 있습니다.

균형 잡힌된 방법에는 트랜잭션 데이터베이스 테이블 및 간소화 된 ES 패턴의 조합입니다. "준비 이벤트를 게시 하려면" 원래 이벤트 통합 이벤트 테이블에 커밋하는 경우에 설정 등의 상태를 사용할 수 있습니다. 다음은 이벤트 버스에 이벤트를 게시 하려고 합니다. Origin 서비스에서 다른 트랜잭션이 시작 하 고 "게시할 준비가 이벤트"에서 "이벤트 이미 게시 되었습니다." 상태를 이동 하에서 게시 이벤트 작업에 성공 하면

이벤트에 이벤트 게시 작업 실패를 버스, 데이터 여전히 됩니다 원본 마이크로 서비스 내에서 일치 하지 않는-"준비 완료 상태로 이벤트를 게시 하려면" 계속 표시 되 고 서비스의 나머지 부분에서는 관련 하 여 결국 됩니다 일치 합니다. 트랜잭션 또는 통합 이벤트 상태를 확인 하는 백그라운드 작업을 항상 사용할 수 있습니다. 작업 이벤트는 "이벤트를 게시 하려면 준비" 상태에서를 발견 하는 경우 해당 이벤트를 이벤트 버스에 다시 게시 하려면 시도할 수 있습니다.

이 방법에서는 유지 하는 각 원본 마이크로 서비스에 대 한 통합 이벤트와 이벤트 다른 microservices 또는 외부 시스템과 통신할 수를 확인 합니다. 반대로 전체 ES 시스템에서는 모든 도메인 이벤트를 저장할 수 있습니다.

따라서이 균형 잡힌된 방식을 간소화 된 ES 시스템. 현재 상태와 통합 이벤트 목록이 필요 하면 ("준비 게시 하려면"와 "게시"). 하지만 통합 이벤트에 대 한 이러한 상태를 구현 해야 합니다. 및이 방법에서는 필요가 없습니다 트랜잭션 데이터베이스에서 이벤트로 모든 도메인 데이터를 저장 하는 전체 ES 시스템에서와 마찬가지로 합니다.

관계형 데이터베이스를 이미 사용 중인 경우에 통합 이벤트를 저장 하는 트랜잭션 테이블을 사용할 수 있습니다. 응용 프로그램에서 원자성을 얻기 위해 로컬 트랜잭션을 기반 2 단계 프로세스를 사용 합니다. 기본적으로, 도메인 엔터티 있는 동일한 데이터베이스의 IntegrationEvent 테이블을가지고 있습니다. 해당 테이블에는 도메인 데이터를 커밋하는 동일한 트랜잭션에 포함 되도록 원자성을 얻기 위해 insurance 지속할 통합 이벤트와 작동 합니다.

다음과 같이 전환 과정을 단계별로,: 응용 프로그램에는 로컬 데이터베이스 트랜잭션을 시작 합니다. 도메인 엔터티의 상태를 업데이트 하 고 이벤트 통합 이벤트 테이블에 삽입 합니다. 마지막으로 트랜잭션을 커밋합니다. 원하는 원자성을 얻게 됩니다.

이벤트를 게시 하는 단계를 구현할 때는 이러한 선택 옵션이 있습니다.

-   트랜잭션을 커밋한 직후 통합 이벤트를 게시 하 고 다른 로컬 트랜잭션을 사용 하 여 테이블에 게시 되 고로 이벤트를 표시 합니다. 그런 다음 아티팩트와 마찬가지로 테이블을 사용 하 여 원격 microservices에 문제가 발생할 경우 통합 이벤트를 추적 하 고 저장 된 통합 이벤트에 따라 compensatory 작업을 수행 합니다.

-   큐의 일종으로 테이블을 사용 합니다. 별도 응용 프로그램 스레드 또는 프로세스 통합 이벤트 테이블을 쿼리하여 이벤트 버스에는 이벤트를 게시 한 다음 로컬 트랜잭션을 사용 하 여 게시 된 이벤트를 표시 합니다.

그림 8-22 이러한 방법 중 첫 번째 범위에 대 한 아키텍처를 보여 줍니다.

![](./media/image23.png)

**그림 8-22**합니다. 이벤트 버스에 이벤트를 게시할 때 원자성

그림 8-22에서 설명 하는 방법에는 게시 된 통합 이벤트의 성공 여부를 확인 하 고 검사를 담당 하는 추가 작업자 마이크로 서비스가 없습니다. 오류가 발생 한 경우 해당 추가 검사기 작업자 마이크로 서비스 이벤트 테이블에서 읽을 수 및 다시 게시 합니다.

두 번째 방법에 대 한: 큐로 이벤트 로그 테이블을 사용 하 고 항상 작업자 마이크로 서비스를 사용 하 여 메시지를 게시 합니다. 이 경우이 프로세스는 그림 8-23 나와 유사 합니다. 이벤트를 게시할 때 테이블은 단일 소스 및이 추가 마이크로 서비스를 보여 줍니다.

![](./media/image24.png)

**그림 8-23**합니다. 원자성 작업자 마이크로 서비스를 사용 하 여 이벤트 버스에 이벤트를 게시할 때

간단한 설명을 위해 eShopOnContainers 샘플 이벤트 버스 더하기 (있음: 프로세스를 추가로 또는 검사기 microservices) 첫 번째 방법인을 사용합니다. 그러나는 eShopOnContainers 모든 가능한 실패의 경우를 처리 하지 않는 합니다. 클라우드에 배포 실제 응용 프로그램을 확인 하 고 논리를 다시 전송 하는 결국 문제가 발생 하 고 구현 해야 하는 팩트를 도입 해야 합니다. 이벤트 버스를 통해 게시할 때 이벤트의 단일 원본으로 해당 테이블에 있는 경우 큐로 테이블을 사용 하 여 첫 번째 방법을 보다 효과적인 수 있습니다.

### <a name="implementing-atomicity-when-publishing-integration-events-through-the-event-bus"></a>이벤트 버스를 통해 통합 이벤트를 게시할 때 원자성 구현

다음 코드는 여러 DbContext 개체와 관련 된 단일 트랜잭션을 만드는 방법을 보여 줍니다.-업데이트 되는 원래 데이터와 관련 한 컨텍스트와 IntegrationEventLog 테이블과 관련 된 두 번째 컨텍스트.

아래 예제에서는 코드의 트랜잭션 데이터베이스에 대 한 연결의 코드가 실행 되 고 시간에 모든 문제가 있는 경우 복원 되지 않는 참고 합니다. 이 서버에서 데이터베이스를 이동할 수 있는 Azure SQL DB와 같은 클라우드 기반 시스템에서 발생할 수 있습니다. 복원 력 있는 트랜잭션을 여러 컨텍스트 간에 구현에 대 한 참조는 [Entity Framework Core SQL 연결 복원 력 있는 구현](#implementing_resilient_EFCore_SQL_conns) 이 가이드의 뒷부분에 나오는 섹션.

다음 예제에서는 이해를 돕기 위해 코드의 한 부분에는 전체 프로세스를 보여 줍니다. 그러나 eShopOnContainers 실제로 리팩터링 되었습니다 및 구현을 쉽게 유지 관리 되기 때문에 여러 클래스로이 논리를 분할 합니다.

```csharp
// Update Product from the Catalog microservice
//
public async Task<IActionResult>
    UpdateProduct([FromBody]CatalogItem productToUpdate)
{
    var catalogItem = await _catalogContext.CatalogItems
        .SingleOrDefaultAsync(i => i.Id == productToUpdate.Id);

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

   // Publish to event bus only if product price changed

   if (raiseProductPriceChangedEvent)
   {
       _eventBus.Publish(priceChangedEvent);
       integrationEventLogService.MarkEventAsPublishedAsync(
           priceChangedEvent);
   }

   return Ok();
}
```

ProductPriceChangedIntegrationEvent 통합 이벤트를 만든 후 원래 도메인 작업 (카탈로그 항목을 업데이트 하는 경우)를 저장 하는 트랜잭션의 지 속성 이벤트의 이벤트 로그 테이블에도 포함 합니다. 이렇게 하면 단일 트랜잭션으로 하 고는 항상 이벤트 메시지가 전송 된 있는지 여부를 확인할 수 있습니다.

이벤트 로그 테이블 동일한 데이터베이스에 대해 로컬 트랜잭션을 사용 하 여 원래 데이터베이스 작업을 자동으로 업데이트 됩니다. 작업 중 하나라도 실패할 경우 예외가 발생 하 고 트랜잭션이 있으므로 도메인 작업 및 전송 이벤트 메시지 간의 일관성을 유지할 모든 완료 된 작업을 롤백합니다.

### <a name="receiving-messages-from-subscriptions-event-handlers-in-receiver-microservices"></a>구독에서 메시지를 받는: microservices 수신기에서에서 이벤트 처리기

이벤트 구독 논리 외에도 통합 이벤트 처리기 (예: 콜백 메서드)에 대 한 내부 코드를 구현 해야 합니다. 이벤트 처리기가 특정 종류의 이벤트 메시지는 수신 및 처리를 지정할 수 있습니다.

이벤트 처리기는 이벤트 버스에서 이벤트 인스턴스를 먼저 받습니다. 배포 하 고 이벤트 수신기 마이크로 서비스에서 상태에서 변경 내용으로 유지할 수 있도록 해당 통합 이벤트와 관련 된 구성 요소 처리를 찾습니다 그런 다음. 예를 들어 ProductPriceChanged 이벤트 카탈로그 마이크로 서비스에서 발생 하는 경우 바구니 마이크로 서비스에서 처리 되 고 다음 코드에 나와 있는 것 처럼이 수신기 바구니 마이크로 서비스와의 상태를 변경 합니다.

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

이벤트 처리기는 제품 바구니 인스턴스 중 하나에 있는지 여부를 확인 해야 합니다. 또한 바구니 관련된 품목에 대해 항목 가격을 업데이트합니다. 마지막으로, 그림 8-24 나와 있는 것 처럼 가격 변경에 대 한 사용자에 게 표시 하는 경고를 만듭니다.

![](./media/image25.png)

**그림 8-24**합니다. 통합 이벤트에 의해 전달 되는 장바구니에 항목 가격 변경을 표시

## <a name="idempotency-in-update-message-events"></a>업데이트 메시지 이벤트에는 멱

업데이트 메시지 이벤트의 중요 한 측면은 언제 든 지 통신에서 오류 메시지를 다시 시도 인해 해야 함을입니다. 그렇지 않으면 백그라운드 작업을 이미 게시 된 경합 상태를 작성 하는 이벤트를 게시 하려고 할 수 있습니다. 업데이트는 idempotent 또는 복제를 검색할 수 있도록 충분 한 정보를 제공 하 고 있는지 확인, 삭제 및 하 백 하나에만 응답을 보냅니다.

앞에서 설명한 대로 작업을 수행할 수 있도록 여러 번 결과 변경 하지 않고 멱 의미 합니다. 메시징 환경에서 이벤트를 통신할 때 이벤트도로 idempotent 수신기 마이크로 서비스에 대 한 결과 변경 하지 않고 여러 번 전달할 수 있습니다. 이 자체, 이벤트의 특성 덕분에 필요할 수 있습니다 또는 방식으로 인해 시스템 이벤트를 처리 합니다. 이벤트 버스 패턴을 구현 하는 응용 프로그램 뿐 아니라, 메시징을 사용 하는 모든 응용 프로그램에서 메시지를 멱 유용 합니다.

Idempotent 작업의 예로 해당 데이터가는 테이블에 아직 없는 경우에 데이터를 테이블에 삽입 하는 SQL 문을 있습니다. 몇 번 실행 하면 SQL 문이 삽입 하는 중요 하지 않습니다. 결과 동일한 됩니다-테이블에서 해당 데이터를 포함 합니다. 필요한 경우 메시지를 보낼 수 잠재적으로 메시지를 처리할 때을 두 번 이상 처리 하므로 효율적 멱 등이 될 수도 있습니다. 예를 들어, 재시도 논리에 두 번 이상 정확히 동일한 메시지를 보낼 발신자 시키면 idempotent 인지 확인 해야 합니다.

디자인 idempotent 메시지를 두는 것이 가능 합니다. 예를 들어 라고 표시 하는 이벤트를 만들 수 있습니다 "제품 가격 설정 \$25" 대신 "추가 \$5 제품 가격을 합니다." 있습니다 안전 하 게 처리할 수 있는 첫 번째 메시지에 여러 번 하 고 동일한 결과 됩니다. 두 번째 메시지에 대 한 true가 아닙니다. 하지만 첫 번째 경우에도 수 원하지 시스템 최신 가격 변경 이벤트를 보낼 수도 없습니다 및 새 가격을 덮어쓰는 것 때문에 첫 번째 이벤트를 처리할 수 있습니다.

또 다른 예로 여러 구독자에 전파 되 고 순서 완료 이벤트를 수 있습니다. 반드시 주문 정보 다른 시스템에서 한 번만 업데이트할 수 같은 순서 완료 이벤트에 대 한 중복 된 메시지 이벤트 경우에 합니다.

각 이벤트 수신기 당 한 번만 처리 됩니다을 적용 하는 논리를 만들 수 있도록 이벤트당 id의 몇 가지 종류 있어야 유용 합니다.

일부 메시지 처리 idempotent입니다. 예를 들어 시스템에서 축소판 이미지를 생성할 경우 것 수 중요 하지 몇 번 생성된 된 미리 보기에 대 한 메시지를 처리 합니다. 결과 축소판 그림 생성은 동일한 때마다입니다. 반면에 지불 게이트웨이 신용 카드 청구를 호출 하는 등 operations 아니어야 idempotent 전혀 합니다. 이러한 경우에는 여러 번 메시지를 처리 하는 효과가 있어야 하는 확인 해야 합니다.

### <a name="additional-resources"></a>추가 리소스

-   **메시지 멱을 구분 하지 않고** (이 페이지에 부제목) [ *https://msdn.microsoft.com/en-us/library/jj591565.aspx*](https://msdn.microsoft.com/en-us/library/jj591565.aspx)

## <a name="deduplicating-integration-event-messages"></a>통합 이벤트 메시지를 제거합니다.

메시지 이벤트 전송 되 고 서로 다른 수준에서 구독자 당 한 번만 처리 되었는지을 만들 수 있습니다. 한 가지 방법은 사용 하는 메시징 인프라에서 제공 하는 중복 제거 기능을 사용 하는 것입니다. 사용자 대상 마이크로 서비스에서 사용자 지정 논리를 구현 하는 방법도 있습니다. 전송 수준 및 응용 프로그램 수준 모두에 유효성 검사를 것이 가장 좋은 방법입니다.

### <a name="deduplicating-message-events-at-the-eventhandler-level"></a>이벤트 처리기 수준에서 메시지 이벤트를 제거합니다.

이벤트는 수신자에 의해 한 번만 처리 되도록 하는 한 가지 방법은 이벤트 처리기의 메시지 이벤트를 처리할 때 특정 논리를 구현 하 여 됩니다. 예를 들어, 즉 eShopOnContainers 응용 프로그램에서 사용 하는 방법에서 볼 수는 [소스 코드](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Controllers/OrdersController.cs) CreateOrderCommand 명령을 받은 경우 OrdersController 클래스의 합니다. (이 경우에 HTTP 요청 명령이 메시지 기반 명령이 아니라 사용 하지만 명령 메시지 기반 idempotent 확인 해야 하는 논리는 유사 합니다.)

### <a name="deduplicating-messages-when-using-rabbitmq"></a>RabbitMQ를 사용 하는 경우 메시지 제거

메시지 중복 될 수 있습니다, 일시적인 네트워크 오류가 발생 하는 경우에 메시지 받는 사람 이러한 중복 된 메시지를 처리할 준비가 여야 합니다. 가능 하면 수신자가 명시적으로 중복 제거 사용 하 여 처리 보다 우수한를 idempotent 방식으로 메시지를 처리 해야 합니다.

에 따라는 [RabbitMQ 설명서](https://www.rabbitmq.com/reliability.html#consumer), "메시지는 소비자에 게 배달를 후 (소비자 연결 삭제 하기 전에 승인 되지 않았습니다) 이므로 다시 대기 경우 RabbitMQ에 다시 전달한 플래그를 설정 합니다 다시 말하면 (여부를 동일한 소비자나 다른) 다시 배달 됩니다.

"다시 전달한" 플래그를 설정 하는 경우 수신기 고려해 야 하는, 메시지 처리 이미 수 있기 때문에 있습니다. 하지만; 보장 되지 않습니다. 메시지 수 되지에 도달 했습니다 수신기 네트워크 문제로 인해 메시지 브로커 아마도 중단 후. 반면에 "다시 전달한" 플래그를 설정 하지 않으면는 메시지가 전송 되지 않은 한 번만 보장 됩니다. 따라서 받는 사람이 메시지에 "다시 전달한" 플래그가 설정 되어 있는 경우에 idempotent 방식에서 프로세스 메시지나 메시지 중복을 제거 해야 합니다.

### <a name="additional-resources"></a>추가 리소스

-   **이벤트 구동 메시징**
    [*http://soapatterns.org/design\_패턴/이벤트\_구동\_메시징*](http://soapatterns.org/design_patterns/event_driven_messaging)

-   **Jimmy Bogard. 복원 력으로 리팩터링: 결합 평가**
    [*https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/*](https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/)

-   **게시-구독 채널**
    [*http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html*](http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html)

-   **경계가 지정 된 컨텍스트 간 통신**
    [*https://msdn.microsoft.com/en-us/library/jj591572.aspx*](https://msdn.microsoft.com/en-us/library/jj591572.aspx)

-   **결과적 일관성**
    [*https://en.wikipedia.org/wiki/Eventual\_일관성*](https://en.wikipedia.org/wiki/Eventual_consistency)

-   **Philip Brown 합니다. 통합 하기 위한 전략 제한 컨텍스트**
    [*http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/*](http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/)

-   **Chris Richardson 합니다. 집계, 이벤트 소싱 및 CQRS-2 부를 사용 하 여 트랜잭션 Microservices 개발**
    [*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson)

-   **Chris Richardson 합니다. 이벤트 소싱 패턴**
    [*http://microservices.io/patterns/data/event-sourcing.html*](http://microservices.io/patterns/data/event-sourcing.html)

-   **이벤트 소싱 소개**
    [*https://msdn.microsoft.com/en-us/library/jj591559.aspx*](https://msdn.microsoft.com/en-us/library/jj591559.aspx)

-   **이벤트 저장소 데이터베이스**합니다. 공식 사이트입니다.
    [*https://geteventstore.com/*](https://geteventstore.com/)

-   **Patrick Nommensen 합니다. 이벤트 구동 Microservices에 대 한 데이터 관리**
    *<https://dzone.com/articles/event-driven-data-management-for-microservices-1>*

-   **단면 정리**
    [*https://en.wikipedia.org/wiki/CAP\_정리*](https://en.wikipedia.org/wiki/CAP_theorem)

-   **단면 정리 이란? ** 
     [ *https://www.quora.com/What-Is-CAP-Theorem-1*](https://www.quora.com/What-Is-CAP-Theorem-1)

-   **데이터 일관성 입문**
    [*https://msdn.microsoft.com/en-us/library/dn589800.aspx*](https://msdn.microsoft.com/en-us/library/dn589800.aspx)

-   **Rick Saling 합니다. 단면 정리: 때문에 "모든 항목은 다르게 지정" 된 클라우드 및 인터넷**
    [*https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/*](https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/)

-   **Eric 가나다 합니다. 단면 12 년간 나중: "규칙" 어떻게 변경 되었는지를**
    [*https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed*](https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed)

-   **외부 (DTC) 트랜잭션에 참여** (MSMQ) [ *https://msdn.microsoft.com/en-us/library/ms978430.aspx\#bdadotnetasync2\_topic3c*](https://msdn.microsoft.com/en-us/library/ms978430.aspx%23bdadotnetasync2_topic3c)

-   **Azure 서비스 버스입니다. 조정 된 메시징: 중복 검색**
    [*https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25*](https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25)

-   **안정성 가이드** (RabbitMQ 설명서) [ *https://www.rabbitmq.com/reliability.html\#소비자*](https://www.rabbitmq.com/reliability.html%23consumer)




>[!div class="step-by-step"]
[이전] [다음] (test-aspnet-core-services-web-apps.md) (rabbitmq-event-bus-development-test-environment.md)
