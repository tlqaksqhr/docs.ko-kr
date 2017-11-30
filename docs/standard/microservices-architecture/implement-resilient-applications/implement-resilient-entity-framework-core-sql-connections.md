---
title: "복원 력 있는 Entity Framework Core SQL 연결 구현"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 복원 력 있는 Entity Framework Core SQL 연결 구현"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 8600625c2022d69ebaa2645c2a8159a848b12ff0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-resilient-entity-framework-core-sql-connections"></a>복원 력 있는 Entity Framework Core SQL 연결 구현

Azure SQL DB에 대 한 Entity Framework Core 이미 내부 데이터베이스 연결 복원 력 및 재시도 논리를 제공합니다. 포함 하려는 경우 각 DbContext 연결에 대 한 Entity Framework 실행 전략을 사용 하도록 설정 해야 하지만 [EF 코어 연결 복원 력 있는](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)합니다.

예를 들어, EF 코어 연결 수준에서 다음 코드에는 연결에 실패 하면 다시 시도 되는 복원 력이 SQL 연결할 수 있습니다.

```csharp
// Startup.cs from any ASP.NET Core Web API
public class Startup
{
    // Other code ...
    public IServiceProvider ConfigureServices(IServiceCollection services)
    {
        // ...
        services.AddDbContext<OrderingContext>(options =>
        {
            options.UseSqlServer(Configuration["ConnectionString"],
            sqlServerOptionsAction: sqlOptions =>
            {
                sqlOptions.EnableRetryOnFailure(
                maxRetryCount: 5,
                maxRetryDelay: TimeSpan.FromSeconds(30),
                errorNumbersToAdd: null);
            });
        });
    }
//...
}
```

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a>실행 전략 및 BeginTransaction 및 여러 DbContexts를 사용 하 여 명시적 트랜잭션을

재시도 EF 코어 연결에서 설정 되 면 EF 코어를 사용 하 여 수행한 각 작업 다시 시도할 수 연산이 됩니다. 일시적인 오류가 발생 하는 경우 각 쿼리 및 SaveChanges 호출할 때마다 하나의 단위로 재시도 됩니다.

그러나 BeginTransaction를 사용 하 여 트랜잭션을 시작 하는 코드를 정의 하는 경우 하나의 단위로 처리 해야 하는 작업의 사용자 정의 그룹-오류가 발생할 경우 롤백할 수에 트랜잭션 내의 모든 항목입니다. EF 실행 전략 (다시 시도 정책)를 사용 하는 경우 해당 트랜잭션을 실행 하 려 하 고 트랜잭션에 여러 DbContexts에서 여러 개의 SaveChanges 호출을 포함 하는 경우 다음과 같은 예외가 표시 됩니다.

> System.InvalidOperationException: 구성 된 실행 전략 'SqlServerRetryingExecutionStrategy' 사용자가 시작한 트랜잭션을 지원 하지 않습니다. 'DbContext.Database.CreateExecutionStrategy()'에서 반환 된 실행 전략을 사용 하 여 트랜잭션을 다시 시도할 수 한 단위로 모든 작업을 실행 합니다.

해결 방법은 수동으로 실행 해야 하는 모든 항목을 나타내는 대리자를 사용 하 여 EF 실행 전략을 호출 합니다. 일시적인 오류가 발생 하는 경우 실행 전략 대리자를 다시 호출 합니다. 예를 들어 다음 코드에 표시 두 개의 eShopOnContainers에서 구현 하는 방법을 여러 DbContexts (\_catalogContext 및는 IntegrationEventLogContext) 제품 및 저장 한 다음 업데이트할 때의 ProductPriceChangedIntegrationEvent 개체로, 다른 DbContext를 사용 해야 합니다.

```csharp
public async Task<IActionResult> UpdateProduct([FromBody]CatalogItem
    productToUpdate)
{
    // Other code ...
    // Update current product
    catalogItem = productToUpdate;

    // Use of an EF Core resiliency strategy when using multiple DbContexts
    // within an explicit transaction
    // See:
    // https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency
    var strategy = _catalogContext.Database.CreateExecutionStrategy();
    await strategy.ExecuteAsync(async () =>
    {
        // Achieving atomicity between original Catalog database operation and the
        // IntegrationEventLog thanks to a local transaction
        using (var transaction = _catalogContext.Database.BeginTransaction())
        {
            _catalogContext.CatalogItems.Update(catalogItem);
            await _catalogContext.SaveChangesAsync();
            // Save to EventLog only if product price changed
            if (raiseProductPriceChangedEvent)
            await _integrationEventLogService.SaveEventAsync(priceChangedEvent);
            transaction.Commit();
        }
    });
}
```

첫 번째 DbContext가 \_DbContext 내인지 catalogContext 및 두 번째는 \_integrationEventLogService 개체입니다. 커밋 작업이 EF 실행 전략을 사용 하 여 여러 DbContexts 간에 수행 됩니다.

## <a name="additional-resources"></a>추가 리소스

-   **연결 복원 력 및 Entity Framework와 함께 명령 인터 셉 션**
    [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)

-   **Cesar de la Torre. 복원 력 있는 엔터티 프레임 워크 코어 Sql 연결 및 트랜잭션을 사용 하 여**
    <https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/>


>[!div class="step-by-step"]
[이전] (구현-다시 시도-지 수-backoff.md) [다음] (implement-custom-http-call-retries-exponential-backoff.md)
