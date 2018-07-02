---
title: 복원력 있는 Entity Framework Core SQL 연결 구현
description: 컨테이너화된 .NET 응용 프로그램용 .NET 마이크로 서비스 아키텍처 | 복원력 있는 Entity Framework Core SQL 연결 구현
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 79f115a2d897463c213eda6f4d6951ff0cbeb3ca
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105477"
---
# <a name="implementing-resilient-entity-framework-core-sql-connections"></a><span data-ttu-id="0c053-103">복원력 있는 Entity Framework Core SQL 연결 구현</span><span class="sxs-lookup"><span data-stu-id="0c053-103">Implementing resilient Entity Framework Core SQL connections</span></span>

<span data-ttu-id="0c053-104">Azure SQL DB의 경우, Entity Framework Core는 이미 내부 데이터베이스 연결 복원력과 다시 시도 논리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0c053-104">For Azure SQL DB, Entity Framework Core already provides internal database connection resiliency and retry logic.</span></span> <span data-ttu-id="0c053-105">그러나 [복원력 있는 EF 코어 연결](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)을 원할 경우 각 DbContext 연결에 대한 Entity Framework 실행 전략을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c053-105">But you need to enable the Entity Framework execution strategy for each DbContext connection if you want to have [resilient EF Core connections](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency).</span></span>

<span data-ttu-id="0c053-106">예를 들어, EF 코어 연결 수준의 다음 코드는 연결이 실패할 경우 다시 시도되는 복원력 있는 SQL 연결을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c053-106">For instance, the following code at the EF Core connection level enables resilient SQL connections that are retried if the connection fails.</span></span>

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

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a><span data-ttu-id="0c053-107">BeginTransaction 및 여러 DbContexts를 사용한 실행 전략 및 명시적 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="0c053-107">Execution strategies and explicit transactions using BeginTransaction and multiple DbContexts</span></span>

<span data-ttu-id="0c053-108">EF 코어 연결에서 다시 시도가 설정되면, EF 코어를 사용하여 수행하는 각 작업은 자체적으로 다시 시도할 수 있는 작업이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c053-108">When retries are enabled in EF Core connections, each operation you perform using EF Core becomes its own retriable operation.</span></span> <span data-ttu-id="0c053-109">일시적인 오류가 발생할 경우 SaveChanges에 대한 각 쿼리와 각 호출이 하나의 단위로 다시 시도됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c053-109">Each query and each call to SaveChanges will be retried as a unit if a transient failure occurs.</span></span>

<span data-ttu-id="0c053-110">그러나 코드가 BeginTransaction을 사용하여 트랜잭션을 시작한 경우, 하나의 단위로 처리해야 하는 자신만의 작업 그룹을 정의하게 됩니다. 오류가 발생하면 트랜잭션 내부의 모든 항목이 롤백됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c053-110">However, if your code initiates a transaction using BeginTransaction, you are defining your own group of operations that need to be treated as a unit—everything inside the transaction has be rolled back if a failure occurs.</span></span> <span data-ttu-id="0c053-111">EF 실행 전략(다시 시도 정책)을 사용할 때 해당 트랜잭션을 실행하려고 시도하고 트랜잭션의 여러 DbContexts에서 여러 SaveChanges 호출을 포함하면 다음과 같은 예외가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c053-111">You will see an exception like the following if you attempt to execute that transaction when using an EF execution strategy (retry policy) and you include several SaveChanges calls from multiple DbContexts in the transaction.</span></span>

> <span data-ttu-id="0c053-112">System.InvalidOperationException: 구성된 실행 전략 'SqlServerRetryingExecutionStrategy’는 사용자가 시작한 트랜잭션을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c053-112">System.InvalidOperationException: The configured execution strategy 'SqlServerRetryingExecutionStrategy' does not support user initiated transactions.</span></span> <span data-ttu-id="0c053-113">'DbContext.Database.CreateExecutionStrategy()'에서 반환된 실행 전략을 사용하여 트랜잭션을 다시 시도가 가능한 단위로 트랜잭션의 모든 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0c053-113">Use the execution strategy returned by 'DbContext.Database.CreateExecutionStrategy()' to execute all the operations in the transaction as a retriable unit.</span></span>

<span data-ttu-id="0c053-114">해결책은 실행해야 하는 모든 것을 나타내는 대리자를 사용하여 EF 실행 전략을 수동으로 호출하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0c053-114">The solution is to manually invoke the EF execution strategy with a delegate representing everything that needs to be executed.</span></span> <span data-ttu-id="0c053-115">일시적인 오류가 발생하면, 실행 전략에서 대리자를 다시 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="0c053-115">If a transient failure occurs, the execution strategy will invoke the delegate again.</span></span> <span data-ttu-id="0c053-116">예를 들어, 다음 코드는 제품을 업데이트한 다음, 다른 DbContext를 사용해야 하는 ProductPriceChangedIntegrationEvent 개체를 저장할 때 두개의 다중 DbContext(\_catalogContext 및 IntegrationEventLogContext)를 사용하여 eShopOnContainers에서 구현하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="0c053-116">For example, the following code show how it is implemented in eShopOnContainers with two multiple DbContexts (\_catalogContext and the IntegrationEventLogContext) when updating a product and then saving the ProductPriceChangedIntegrationEvent object, which needs to use a different DbContext.</span></span>

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

<span data-ttu-id="0c053-117">첫 번째 DbContext는 \_ catalogContext이고 두 번째 DbContext는 \_integrationEventLogService 개체 내에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c053-117">The first DbContext is \_catalogContext and the second DbContext is within the \_integrationEventLogService object.</span></span> <span data-ttu-id="0c053-118">커밋 작업은 EF 실행 전략을 사용하여 여러 DbContexts를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0c053-118">The Commit action is performed across multiple DbContexts using an EF execution strategy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0c053-119">추가 자료</span><span class="sxs-lookup"><span data-stu-id="0c053-119">Additional resources</span></span>

-   <span data-ttu-id="0c053-120">**Entity Framework를 사용하여 연결 복원력 및 명령 인터셉션**
    [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)</span><span class="sxs-lookup"><span data-stu-id="0c053-120">**Connection Resiliency and Command Interception with the Entity Framework**
[*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)</span></span>

-   <span data-ttu-id="0c053-121">**Cesar de la Torre. 복원력 있는 Entity Framework Core Sql 연결 및 트랜잭션 사용**
    <https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/></span><span class="sxs-lookup"><span data-stu-id="0c053-121">**Cesar de la Torre. Using Resilient Entity Framework Core Sql Connections and Transactions**
<https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/></span></span>


>[!div class="step-by-step"]
<span data-ttu-id="0c053-122">[이전](implement-retries-exponential-backoff.md)
[다음](implement-custom-http-call-retries-exponential-backoff.md)</span><span class="sxs-lookup"><span data-stu-id="0c053-122">[Previous](implement-retries-exponential-backoff.md)
[Next](implement-custom-http-call-retries-exponential-backoff.md)</span></span>
