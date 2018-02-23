---
title: "Entity Framework Core를 사용하여 인프라 지속성 레이어 구현"
description: "컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | Entity Framework Core를 사용하여 인프라 지속성 레이어 구현"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/12/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 67f89b4ee42d896497f462b80d41afff6b347e05
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="implementing-the-infrastructure-persistence-layer-with-entity-framework-core"></a><span data-ttu-id="7e3c6-104">Entity Framework Core를 사용하여 인프라 지속성 레이어 구현</span><span class="sxs-lookup"><span data-stu-id="7e3c6-104">Implementing the infrastructure persistence layer with Entity Framework Core</span></span>

<span data-ttu-id="7e3c6-105">SQL Server, Oracle 또는 PostgreSQL 같은 관계형 데이터베이스를 사용하는 경우 EF(Entity Framework) 기반의 지속성 레이어를 구현하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-105">When you use relational databases such as SQL Server, Oracle, or PostgreSQL, a recommended approach is to implement the persistence layer based on Entity Framework (EF).</span></span> <span data-ttu-id="7e3c6-106">EF는 LINQ 지원하며 데이터베이스에 간소화된 지속성을 제공할 뿐 아니라 모델에 대한 강력한 형식의 개체를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-106">EF supports LINQ and provides strongly typed objects for your model, as well as simplified persistence into your database.</span></span>

<span data-ttu-id="7e3c6-107">Entity Framework는 .NET Framework의 일부로 오랜 역사를 갖고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-107">Entity Framework has a long history as part of the .NET Framework.</span></span> <span data-ttu-id="7e3c6-108">.NET Core를 사용하는 경우 .NET Core와 마찬가지로 Windows 또는 Linux에서 실행되는 Entity Framework Core도 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-108">When you use .NET Core, you should also use Entity Framework Core, which runs on Windows or Linux in the same way as .NET Core.</span></span> <span data-ttu-id="7e3c6-109">EF Core는 Entity Framework를 완전히 새로 작성한 것으로, 훨씬 적은 공간을 차지하며 성능이 대폭 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-109">EF Core is a complete rewrite of Entity Framework, implemented with a much smaller footprint and important improvements in performance.</span></span>

## <a name="introduction-to-entity-framework-core"></a><span data-ttu-id="7e3c6-110">Entity Framework Core 소개</span><span class="sxs-lookup"><span data-stu-id="7e3c6-110">Introduction to Entity Framework Core</span></span>

<span data-ttu-id="7e3c6-111">EF(Entity Framework) Core는 널리 사용되는 Entity Framework 데이터 액세스 기술의 가볍고 확장 가능하며 플랫폼 교차적인 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-111">Entity Framework (EF) Core is a lightweight, extensible, and cross-platform version of the popular Entity Framework data access technology.</span></span> <span data-ttu-id="7e3c6-112">2016년 중순에 .NET Core에 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-112">It was introduced with .NET Core in mid-2016.</span></span>

<span data-ttu-id="7e3c6-113">EF Core를 소개하는 내용은 이미 Microsoft 설명서에 있으므로 여기서는 간단하게 해당 정보에 대한 링크만 제공하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-113">Since an introduction to EF Core is already available in Microsoft documentation, here we simply provide links to that information.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="7e3c6-114">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="7e3c6-114">Additional resources</span></span>

-   <span data-ttu-id="7e3c6-115">**Entity Framework Core**
    [*https://docs.microsoft.com/ef/core/*](https://docs.microsoft.com/ef/core/)</span><span class="sxs-lookup"><span data-stu-id="7e3c6-115">**Entity Framework Core**
[*https://docs.microsoft.com/ef/core/*](https://docs.microsoft.com/ef/core/)</span></span>

-   <span data-ttu-id="7e3c6-116">**Visual Studio를 사용하여 ASP.NET Core 및 Entity Framework Core 시작**
    [*https://docs.microsoft.com/aspnet/core/data/ef-mvc/*](https://docs.microsoft.com/aspnet/core/data/ef-mvc/)</span><span class="sxs-lookup"><span data-stu-id="7e3c6-116">**Getting started with ASP.NET Core and Entity Framework Core using Visual Studio**
[*https://docs.microsoft.com/aspnet/core/data/ef-mvc/*](https://docs.microsoft.com/aspnet/core/data/ef-mvc/)</span></span>

-   <span data-ttu-id="7e3c6-117">**DbContext 클래스**
    [*https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext*](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext)</span><span class="sxs-lookup"><span data-stu-id="7e3c6-117">**DbContext Class**
[*https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext*](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext)</span></span>

-   <span data-ttu-id="7e3c6-118">**Compare EF Core 및 EF6.x**
    [*https://docs.microsoft.com/ef/efcore-and-ef6/index*](https://docs.microsoft.com/ef/efcore-and-ef6/index)</span><span class="sxs-lookup"><span data-stu-id="7e3c6-118">**Compare EF Core & EF6.x**
[*https://docs.microsoft.com/ef/efcore-and-ef6/index*](https://docs.microsoft.com/ef/efcore-and-ef6/index)</span></span>

## <a name="infrastructure-in-entity-framework-core-from-a-ddd-perspective"></a><span data-ttu-id="7e3c6-119">DDD 관점에서 본 Entity Framework Core의 인프라</span><span class="sxs-lookup"><span data-stu-id="7e3c6-119">Infrastructure in Entity Framework Core from a DDD perspective</span></span>

<span data-ttu-id="7e3c6-120">DDD 관점에서 본 EF의 중요한 기능은 POCO 도메인 엔터티를 사용하는 기능으로, EF 용어로는 POCO *코드 중심 엔터티*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-120">From a DDD point of view, an important capability of EF is the ability to use POCO domain entities, also known in EF terminology as POCO *code-first entities*.</span></span> <span data-ttu-id="7e3c6-121">POCO 도메인 엔터티를 사용하는 경우 도메인 모델 클래스는 [지속성 무시](http://deviq.com/persistence-ignorance/) 및 [인프라 무시](https://ayende.com/blog/3137/infrastructure-ignorance) 원칙에 따라 지속성을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-121">If you use POCO domain entities, your domain model classes are persistence-ignorant, following the [Persistence Ignorance](http://deviq.com/persistence-ignorance/) and the [Infrastructure Ignorance](https://ayende.com/blog/3137/infrastructure-ignorance) principles.</span></span>

<span data-ttu-id="7e3c6-122">DDD 패턴마다 엔터티 클래스 자체 내의 도메인 동작과 규칙을 캡슐화해야만 컬렉션에 액세스할 때 고정, 유효성 검사 및 규칙을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-122">Per DDD patterns, you should encapsulate domain behavior and rules within the entity class itself, so it can control invariants, validations, and rules when accessing any collection.</span></span> <span data-ttu-id="7e3c6-123">따라서 DDD에서 자식 엔터티 또는 값 개체 컬렉션에 대한 공용 액세스를 허용하는 것은 좋지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-123">Therefore, it is not a good practice in DDD to allow public access to collections of child entities or value objects.</span></span> <span data-ttu-id="7e3c6-124">그 대신, 속성 컬렉션을 업데이트할 수 있는 방법 및 시기 그리고 속성 컬렉션 업데이트가 발생할 때 수행할 동작 및 작업을 제어하는 메서드를 노출하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-124">Instead, you want to expose methods that control how and when your fields and property collections can be updated, and what behavior and actions should occur when that happens.</span></span>

<span data-ttu-id="7e3c6-125">EF Core 1.1부터는 DDD 요구 사항을 충족하기 위해 엔터티에 공용 속성 대신 일반 필드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-125">Since EF Core 1.1, to satisfy those DDD requirements, you can have plain fields in your entities instead of public properties.</span></span> <span data-ttu-id="7e3c6-126">외부에서 엔터티 필드에 액세스하지 못하게 하려면 속성 대신 특성 또는 필드를 만들면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-126">If you do not want an entity field to be externally accessible, you can just create the attribute or field instead of a property.</span></span> <span data-ttu-id="7e3c6-127">개인 속성 setter를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-127">You can also use private property setters.</span></span>

<span data-ttu-id="7e3c6-128">이와 비슷한 방법으로, 이제 `IReadOnlyCollection<T>`으로 형식화된 공용 속성을 사용하여 컬렉션에 읽기 전용으로 액세스할 수 있으며, 이 형식은 지속성 때문에 EF를 사용하는 엔터티의 컬렉션에 대한 전용 필드 멤버(예: `List<T>`)를 통해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-128">In a similar way, you can now have read-only access to collections by using a public property typed as  `IReadOnlyCollection<T>`, which is backed by a private field member for the collection (like a `List<T>`) in your entity that relies on EF for persistence.</span></span> <span data-ttu-id="7e3c6-129">이전 버전의 Entity Framework는 `ICollection<T>`을 지원하려면 컬렉션 속성이 필요했으며, 부모 엔터티 클래스를 사용하는 개발자가 속성 컬렉션을 통해 항목을 추가 또는 제거할 수 있었다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-129">Previous versions of Entity Framework required collection properties to support `ICollection<T>`, which meant that any developer using the parent entity class could add or remove items through its property collections.</span></span> <span data-ttu-id="7e3c6-130">이 가능성은 DDD의 권장 패턴과 상반됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-130">That possibility would be against the recommended patterns in DDD.</span></span>

<span data-ttu-id="7e3c6-131">다음 코드 예제와 같이, 읽기 전용 `IReadOnlyCollection<T>` 개체를 노출할 때 전용 컬렉션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-131">You can use a private collection while exposing a read-only `IReadOnlyCollection<T>` object, as shown in the following code example:</span></span>

```csharp
public class Order : Entity
{
    // Using private fields, allowed since EF Core 1.1
    private DateTime _orderDate;
    // Other fields ...

    private readonly List<OrderItem> _orderItems; 
    public IReadOnlyCollection<OrderItem> OrderItems => _orderItems;

    protected Order() { }

    public Order(int buyerId, int paymentMethodId, Address address)
    {
        // Initializations ...
    }

    public void AddOrderItem(int productId, string productName,
                             decimal unitPrice, decimal discount,
                             string pictureUrl, int units = 1)
    {
        // Validation logic...

        var orderItem = new OrderItem(productId, productName, 
                                      unitPrice, discount,
                                      pictureUrl, units);
        _orderItems.Add(orderItem);
    }
}
```

<span data-ttu-id="7e3c6-132">`OrderItems` 속성은 `IReadOnlyCollection<OrderItem>`을 사용하여 읽기 전용으로만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-132">Note that the `OrderItems` property can only be accessed as read-only using `IReadOnlyCollection<OrderItem>`.</span></span> <span data-ttu-id="7e3c6-133">이 형식은 읽기 전용이므로 정기적인 업데이트로부터 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-133">This type is read-only so it is protected against regular external updates.</span></span> 

<span data-ttu-id="7e3c6-134">EF Core는 도메인 모델을 "오염"시키지 않고 도메인 모델을 물리적 데이터베이스에 매핑할 수 있는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-134">EF Core provides a way to map the domain model to the physical database without "contaminating" the domain model.</span></span> <span data-ttu-id="7e3c6-135">매핑 작업이 지속성 레이어에서 구현되는 순수 .NET POCO 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-135">It is pure .NET POCO code, because the mapping action is implemented in the persistence layer.</span></span> <span data-ttu-id="7e3c6-136">이 매핑 작업에서 필드-데이터베이스 매핑을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-136">In that mapping action, you need to configure the fields-to-database mapping.</span></span> <span data-ttu-id="7e3c6-137">다음 OnModelCreating 메서드 예제에서 강조 표시된 코드는 필드를 통해 OrderItems 속성에 액세스하라고 EF 코어에 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-137">In the following example of an OnModelCreating method, the highlighted code tells EF Core to access the OrderItems property through its field.</span></span>

```csharp
// At OrderingContext.cs from eShopOnContainers
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
   // ...
   modelBuilder.ApplyConfiguration(new OrderEntityTypeConfiguration());
   // Other entities’ configuration ...
}

// At OrderEntityTypeConfiguration.cs from eShopOnContainers
class OrderEntityTypeConfiguration : IEntityTypeConfiguration<Order>
{
    public void Configure(EntityTypeBuilder<Order> orderConfiguration)
    {
        orderConfiguration.ToTable("orders", OrderingContext.DEFAULT_SCHEMA);
        // Other configuration

        var navigation = 
              orderConfiguration.Metadata.FindNavigation(nameof(Order.OrderItems));

        //EF access the OrderItem collection property through its backing field
        navigation.SetPropertyAccessMode(PropertyAccessMode.Field);

        // Other configuration
    }
}
```

<span data-ttu-id="7e3c6-138">속성 대신 필드를 사용하면 OrderItem 엔터티는 마치 List&lt;OrderItem&gt; 속성이 있는 것처럼 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-138">When you use fields instead of properties, the OrderItem entity is persisted just as if it had a List&lt;OrderItem&gt; property.</span></span> <span data-ttu-id="7e3c6-139">그러나 주문에 새 항목을 추가하기 위한 단일 접근자인 `AddOrderItem` 메서드를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-139">However, it exposes a single accessor, the `AddOrderItem` method for adding new items to the order.</span></span> <span data-ttu-id="7e3c6-140">결과적으로 동작 및 데이터는 서로 연결되고 도메인 모델을 사용하는 응용 프로그램 코드 전체에서 일관적으로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-140">As a result, behavior and data are tied together and will be consistent throughout any application code that uses the domain model.</span></span>

## <a name="implementing-custom-repositories-with-entity-framework-core"></a><span data-ttu-id="7e3c6-141">Entity Framework Core를 사용하여 사용자 지정 리포지토리 구현</span><span class="sxs-lookup"><span data-stu-id="7e3c6-141">Implementing custom repositories with Entity Framework Core</span></span>

<span data-ttu-id="7e3c6-142">구현 수준에서 보자면, 리포지토리는 다음 클래스에서 볼 수 있듯이 업데이트를 수행할 때 작업 단위(EF Core의 DBContext)에 의해 조정되는 데이터 지속성 코드가 있는 클래스일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-142">At the implementation level, a repository is simply a class with data persistence code coordinated by a unit of work (DBContext in EF Core) when performing updates, as shown in the following class:</span></span>

```csharp
// using statements...
namespace Microsoft.eShopOnContainers.Services.Ordering.Infrastructure.Repositories
{
    public class BuyerRepository : IBuyerRepository
    {
        private readonly OrderingContext _context;
        public IUnitOfWork UnitOfWork
        {
            get
            {
                return _context;
            }
        }

        public BuyerRepository(OrderingContext context)
        {
            _context = context ?? throw new ArgumentNullException(nameof(context));
        }

        public Buyer Add(Buyer buyer)
        {
            return _context.Buyers.Add(buyer).Entity; 
        }

        public async Task<Buyer> FindAsync(string BuyerIdentityGuid)
        {
            var buyer = await _context.Buyers
                .Include(b => b.Payments)
                .Where(b => b.FullName == BuyerIdentityGuid)
                .SingleOrDefaultAsync();

            return buyer;
        }
    }
}
```

<span data-ttu-id="7e3c6-143">IBuyerRepository 인터페이스는 도메인 모델 레이어에서 계약으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-143">Note that the IBuyerRepository interface comes from the domain model layer as a contract.</span></span> <span data-ttu-id="7e3c6-144">그러나 리포지토리 구현은 지속성 및 인프라 레이어에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-144">However, the repository implementation is done at the persistence and infrastructure layer.</span></span>

<span data-ttu-id="7e3c6-145">EF DbContext는 종속성 주입을 통해 생성자를 거쳐 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-145">The EF DbContext comes through the constructor through Dependency Injection.</span></span> <span data-ttu-id="7e3c6-146">IoC 컨테이너(services.AddDbContext&lt;&gt;를 사용하여 명시적으로도 설정 가능)의 기본 수명 주기(ServiceLifetime.Scoped) 덕분에 동일한 HTTP 요청 범위 내의 여러 리포지토리 간에 공유됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-146">It is shared between multiple repositories within the same HTTP request scope, thanks to its default lifetime (ServiceLifetime.Scoped) in the IoC container (which can also be explicitly set with services.AddDbContext&lt;&gt;).</span></span>

### <a name="methods-to-implement-in-a-repository-updates-or-transactions-versus-queries"></a><span data-ttu-id="7e3c6-147">리포지토리에서 구현하는 메서드(업데이트 또는 트랜잭션과 쿼리 비교)</span><span class="sxs-lookup"><span data-stu-id="7e3c6-147">Methods to implement in a repository (updates or transactions versus queries)</span></span>

<span data-ttu-id="7e3c6-148">각 리포지토리 클래스 내에서, 관련 집계에 의해 포함되는 엔터티 상태를 업데이트하는 지속성 메서드를 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-148">Within each repository class, you should put the persistence methods that update the state of entities contained by its related aggregate.</span></span> <span data-ttu-id="7e3c6-149">집계와 집계 관련 리포지토리 사이에는 일대일 관계가 성립합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-149">Remember there is one-to-one relationship between an aggregate and its related repository.</span></span> <span data-ttu-id="7e3c6-150">집계 루트 엔터티 개체가 EF 그래프 내에 자식 엔터티를 포함할 수 있다는 점을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-150">Take into account that an aggregate root entity object might have embedded child entities within its EF graph.</span></span> <span data-ttu-id="7e3c6-151">예를 들어 구매자가 관련 자식 엔터티로 여러 지불 방법을 보유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-151">For example, a buyer might have multiple payment methods as related child entities.</span></span>

<span data-ttu-id="7e3c6-152">eShopOnContainers에서 마이크로 서비스를 주문하는 방식도 CQS/CQRS 기반이므로 대부분의 쿼리가 사용자 지정 리포지토리에서 구현되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-152">Since the approach for the ordering microservice in eShopOnContainers is also based on CQS/CQRS, most of the queries are not implemented in custom repositories.</span></span> <span data-ttu-id="7e3c6-153">개발자는 집계, 집계별 사용자 지정 리포지토리 그리고 일반적으로 DDD에서 부과하는 제한 없이 프레젠테이션 레이어에 필요한 쿼리 및 조인을 자유롭게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-153">Developers have the freedom to create the queries and joins they need for the presentation layer without the restrictions imposed by aggregates, custom repositories per aggregate, and DDD in general.</span></span> <span data-ttu-id="7e3c6-154">이 가이드에서 권장하는 대부분의 사용자 지정 리포지토리는 여러 업데이트 또는 트랜잭션 메서드를 갖고 있지만 데이터를 가져오는 데 필요한 쿼리 메서드만 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-154">Most of the custom repositories suggested by this guide have several update or transactional methods but just the query methods needed to get data to be updated.</span></span> <span data-ttu-id="7e3c6-155">예를 들어 BuyerRepository 리포지토리는 FindAsync 메서드를 구현합니다. 응용 프로그램에서 특정 구매자의 존재 여부를 알아야만 주문과 관련된 새 구매자를 만들 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-155">For example, the BuyerRepository repository implements a FindAsync method, because the application needs to know whether a particular buyer exists before creating a new buyer related to the order.</span></span>

<span data-ttu-id="7e3c6-156">그러나 프레젠테이션 레이어 또는 클라이언트 앱으로 보낼 데이터를 가져오는 실제 쿼리 메서드는 앞서 언급했듯이 Dapper를 사용하여 유연한 쿼리를 기반으로 CQRS 쿼리로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-156">However, the real query methods to get data to send to the presentation layer or client apps are implemented, as mentioned, in the CQRS queries based on flexible queries using Dapper.</span></span>

### <a name="using-a-custom-repository-versus-using-ef-dbcontext-directly"></a><span data-ttu-id="7e3c6-157">사용자 지정 리포지토리를 사용하는 방법과 EF DbContext를 직접 사용하는 방법 비교</span><span class="sxs-lookup"><span data-stu-id="7e3c6-157">Using a custom repository versus using EF DbContext directly</span></span>

<span data-ttu-id="7e3c6-158">Entity Framework DbContext 클래스는 작업 단위 및 리포지토리 패턴을 기반으로 하며, ASP.NET Core MVC 컨트롤러처럼 코드에서 직접 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-158">The Entity Framework DbContext class is based on the Unit of Work and Repository patterns, and can be used directly from your code, such as from an ASP.NET Core MVC controller.</span></span> <span data-ttu-id="7e3c6-159">eShopOnContainers의 CRUD 카탈로그 마이크로 서비스에서 하듯이, 이 방법으로 가장 간단한 코드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-159">That is the way you can create the simplest code, as in the CRUD catalog microservice in eShopOnContainers.</span></span> <span data-ttu-id="7e3c6-160">최대한 간단한 코드를 원하는 경우 여러 개발자들이 하는 것처럼 DbContext 클래스를 직접 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-160">In cases where you want the simplest code possible, you might want to directly use the DbContext class, as many developers do.</span></span>

<span data-ttu-id="7e3c6-161">그러나 사용자 지정 리포지토리를 구현하면 보다 복잡한 마이크로 서비스 또는 응용 프로그램을 구현할 때 여러 가지 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-161">However, implementing custom repositories provides several benefits when implementing more complex microservices or applications.</span></span> <span data-ttu-id="7e3c6-162">작업 단위 및 리포지토리 패턴은 응용 프로그램 및 도메인 모델 레이어에서 분리되는 인프라 지속성 레이어를 캡슐화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-162">The Unit of Work and Repository patterns are intended to encapsulate the infrastructure persistence layer so it is decoupled from the application and domain model layers.</span></span> <span data-ttu-id="7e3c6-163">이러한 패턴을 구현하면 모의 리포지토리를 사용하여 데이터베이스에 대한 액세스를 시뮬레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-163">Implementing these patterns can facilitate the use of mock repositories simulating access to the database.</span></span>

<span data-ttu-id="7e3c6-164">그림 9-18에서는 리포지토리를 사용하지 않을 때와(EF DbContext를 직접 사용) 리포지토리를 사용하여 좀 더 쉽게 리포지토리 모형을 만들 때의 차이를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-164">In Figure 9-18 you can see the differences between not using repositories (directly using the EF DbContext) versus using repositories which make it easier to mock those repositories.</span></span>

![](./media/image19.png)

<span data-ttu-id="7e3c6-165">**그림 9-18**.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-165">**Figure 9-18**.</span></span> <span data-ttu-id="7e3c6-166">사용자 지정 리포지토리와 일반 DbContext 비교</span><span class="sxs-lookup"><span data-stu-id="7e3c6-166">Using custom repositories versus a plain DbContext</span></span>

<span data-ttu-id="7e3c6-167">모형을 만들 때 여러 가지 대안이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-167">There are multiple alternatives when mocking.</span></span> <span data-ttu-id="7e3c6-168">리포지토리 모형만 만들 수도 있고 작업 단위 전체의 모형을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-168">You could mock just repositories or you could mock a whole unit of work.</span></span> <span data-ttu-id="7e3c6-169">일반적으로 리포지토리 모형만 만들면 충분하며, 복잡하게 작업 단위 전체를 추상화하고 모형을 만들 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-169">Usually mocking just the repositories is enough, and the complexity to abstract and mock a whole unit of work is usually not needed.</span></span>

<span data-ttu-id="7e3c6-170">뒤에서 응용 프로그램 계층을 살펴볼 때, ASP.NET Core에서 종속성 주입의 작동 원리와 리포지토리를 사용할 때 구현 방식을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-170">Later, when we focus on the application layer, you will see how Dependency Injection works in ASP.NET Core and how it is implemented when using repositories.</span></span>

<span data-ttu-id="7e3c6-171">요약하자면, 사용자 지정 리포지토리를 사용하면 데이터 계층 상태의 영향을 받지 않는 단위 테스트로 코드를 보다 쉽게 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-171">In short, custom repositories allow you to test code more easily with unit tests that are not impacted by the data tier state.</span></span> <span data-ttu-id="7e3c6-172">Entity Framework를 통해 실제 데이터베이스에 액세스하는 테스트를 실행하는 경우 통합 테스트가 아닌 단위 테스트이며, 속도가 훨씬 느립니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-172">If you run tests that also access the actual database through the Entity Framework, they are not unit tests but integration tests, which are a lot slower.</span></span>

<span data-ttu-id="7e3c6-173">DbContext를 직접 사용하는 경우 개발자가 할 수 있는 유일한 선택은 예측 가능한 데이터와 함께 메모리 내 SQL Server를 단위 테스트에 사용하여 단위 테스트를 실행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-173">If you were using DbContext directly, the only choice you would have would be to run unit tests by using an in-memory SQL Server with predictable data for unit tests.</span></span> <span data-ttu-id="7e3c6-174">모의 개체 및 모조 데이터를 리포지토리 수준에서 하는 것과 동일한 방식으로 제어할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-174">You would not be able to control mock objects and fake data in the same way at the repository level.</span></span> <span data-ttu-id="7e3c6-175">물론, 항상 MVC 컨트롤러를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-175">Of course, you could always test the MVC controllers.</span></span>

## <a name="ef-dbcontext-and-iunitofwork-instance-lifetime-in-your-ioc-container"></a><span data-ttu-id="7e3c6-176">IoC 컨테이너의 EF DbContext 및 IUnitOfWork 인스턴스 수명</span><span class="sxs-lookup"><span data-stu-id="7e3c6-176">EF DbContext and IUnitOfWork instance lifetime in your IoC container</span></span>

<span data-ttu-id="7e3c6-177">DbContext 개체(IUnitOfWork 개체로 노출)는 동일한 HTTP 요청 범위 내에 있는 여러 리포지토리 간에 공유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-177">The DbContext object (exposed as an IUnitOfWork object) might need to be shared among multiple repositories within the same HTTP request scope.</span></span> <span data-ttu-id="7e3c6-178">실행 중인 작업에서 여러 집계를 처리해야 하거나 여러 리포지토리 인스턴스를 사용하는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-178">For example, this is true when the operation being executed must deal with multiple aggregates, or simply because you are using multiple repository instances.</span></span> <span data-ttu-id="7e3c6-179">IUnitOfWork 인터페이스는 EF Core 형식이 아닌 도메인 레이어의 일부라는 점도 언급해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-179">It is also important to mention that the IUnitOfWork interface is part of your domain layer, not an EF Core type.</span></span>

<span data-ttu-id="7e3c6-180">그러려면 DbContext 개체 인스턴스의 서비스 수명이 ServiceLifetime.Scoped로 설정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-180">In order to do that, the instance of the DbContext object has to have its service lifetime set to ServiceLifetime.Scoped.</span></span> <span data-ttu-id="7e3c6-181">이것은 ASP.NET Core Web API 프로젝트에서 Startup.cs 파일의 ConfigureServices 메서드에 있는 IoC 컨테이너의 services.AddDbContext에 DbContext를 등록할 때 기본 수명입니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-181">This is the default lifetime when registering a DbContext with services.AddDbContext in your IoC container from the ConfigureServices method of the Startup.cs file in your ASP.NET Core Web API project.</span></span> <span data-ttu-id="7e3c6-182">다음 코드에서는 이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-182">The following code illustrates this.</span></span>

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{
    // Add framework services.
    services.AddMvc(options =>
    {
        options.Filters.Add(typeof(HttpGlobalExceptionFilter));
    }).AddControllersAsServices();

    services.AddEntityFrameworkSqlServer()
      .AddDbContext<OrderingContext>(options =>
      {
          options.UseSqlServer(Configuration["ConnectionString"],
                               sqlOptions => sqlOptions.MigrationsAssembly(typeof(Startup).GetTypeInfo().
                                                                                    Assembly.GetName().Name));
      },
      ServiceLifetime.Scoped // Note that Scoped is the default choice
                             // in AddDbContext. It is shown here only for
                             // pedagogic purposes.
      );
}
```

<span data-ttu-id="7e3c6-183">DbContext 인스턴스화 모드를 ServiceLifetime.Transient 또는 ServiceLifetime.Singleton로 구성하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-183">The DbContext instantiation mode should not be configured as ServiceLifetime.Transient or ServiceLifetime.Singleton.</span></span>

## <a name="the-repository-instance-lifetime-in-your-ioc-container"></a><span data-ttu-id="7e3c6-184">IoC 컨테이너의 리포지토리 인스턴스 수명</span><span class="sxs-lookup"><span data-stu-id="7e3c6-184">The repository instance lifetime in your IoC container</span></span>

<span data-ttu-id="7e3c6-185">마찬가지로 리포지토리 수명은 일반적으로 그 범위를 지정해야 합니다(Autofac의 InstancePerLifetimeScope).</span><span class="sxs-lookup"><span data-stu-id="7e3c6-185">In a similar way, repository’s lifetime should usually be set as scoped (InstancePerLifetimeScope in Autofac).</span></span> <span data-ttu-id="7e3c6-186">임시로 지정할 수도 있지만(Autofac의 InstancePerDependency) 수명 범위를 지정하면 메모리와 관련한 서비스 효율이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-186">It could also be transient (InstancePerDependency in Autofac), but your service will be more efficient in regards memory when using the scoped lifetime.</span></span>

```csharp
// Registering a Repository in Autofac IoC container
builder.RegisterType<OrderRepository>()
    .As<IOrderRepository>()
    .InstancePerLifetimeScope();
```

<span data-ttu-id="7e3c6-187">리포지토리에 singleton 수명을 사용하면 DbContext를 범위가 지정된(InstancePerLifetimeScope) 수명으로 설정(DBContext의 기본 수명)할 경우 심각한 동시성 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-187">Note that using the singleton lifetime for the repository could cause you serious concurrency problems when your DbContext is set to scoped (InstancePerLifetimeScope) lifetime (the default lifetimes for a DBContext).</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="7e3c6-188">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="7e3c6-188">Additional resources</span></span>

-   <span data-ttu-id="7e3c6-189">**ASP.NET MVC 응용 프로그램에서 리포지토리 및 작업 단위 패턴 구현**
    [*https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application*](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)</span><span class="sxs-lookup"><span data-stu-id="7e3c6-189">**Implementing the Repository and Unit of Work Patterns in an ASP.NET MVC Application**
[*https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application*](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)</span></span>

-   <span data-ttu-id="7e3c6-190">**Jonathan Allen. Entity Framework, Dapper 및 체인을 사용하여 리포지토리 패턴에 대한 전략 구현**
    [*https://www.infoq.com/articles/repository-implementation-strategies*](https://www.infoq.com/articles/repository-implementation-strategies)</span><span class="sxs-lookup"><span data-stu-id="7e3c6-190">**Jonathan Allen. Implementation Strategies for the Repository Pattern with Entity Framework, Dapper, and Chain**
[*https://www.infoq.com/articles/repository-implementation-strategies*](https://www.infoq.com/articles/repository-implementation-strategies)</span></span>

-   <span data-ttu-id="7e3c6-191">**Cesar de la Torre. Autofac IoC 컨테이너 인스턴스 범위와 ASP.NET Core IoC 컨테이너 서비스 수명 비교**
    [*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)</span><span class="sxs-lookup"><span data-stu-id="7e3c6-191">**Cesar de la Torre. Comparing ASP.NET Core IoC container service lifetimes with Autofac IoC container instance scopes**
[*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)</span></span>

## <a name="table-mapping"></a><span data-ttu-id="7e3c6-192">테이블 매핑</span><span class="sxs-lookup"><span data-stu-id="7e3c6-192">Table mapping</span></span>

<span data-ttu-id="7e3c6-193">테이블 매핑은 데이터베이스에서 쿼리하고 저장할 테이블 데이터를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-193">Table mapping identifies the table data to be queried from and saved to the database.</span></span> <span data-ttu-id="7e3c6-194">앞에서 도메인 엔터티(예: 제품 또는 주문 도메인)를 사용하여 관련 데이터베이스 스키마를 생성하는 방법을 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-194">Previously you saw how domain entities (for example, a product or order domain) can be used to generate a related database schema.</span></span> <span data-ttu-id="7e3c6-195">EF는 *규칙* 개념을 중심으로 강력하게 설계됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-195">EF is strongly designed around the concept of *conventions*.</span></span> <span data-ttu-id="7e3c6-196">규칙은 "테이블의 이름은 무엇이 될까요?"</span><span class="sxs-lookup"><span data-stu-id="7e3c6-196">Conventions address questions like “What will the name of a table be?”</span></span> <span data-ttu-id="7e3c6-197">또는 “기본 키는 무슨 속성입니까?”와 같은 질문을 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-197">or “What property is the primary key?”</span></span> <span data-ttu-id="7e3c6-198">규칙은 일반적으로 관습적 이름을 기반으로 합니다. 예를 들어 일반적으로 기본 키는 Id로 끝나는 속성이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-198">Conventions are typically based on conventional names—for example, it is typical for the primary key to be a property that ends with Id.</span></span>

<span data-ttu-id="7e3c6-199">규칙에 따라 각 엔터티는 파생 컨텍스트에 엔터티를 노출하는 DbSet&lt;TEntity&gt; 속성과 이름이 같은 테이블에 매핑되도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-199">By convention, each entity will be set up to map to a table with the same name as the DbSet&lt;TEntity&gt; property that exposes the entity on the derived context.</span></span> <span data-ttu-id="7e3c6-200">특정 엔터티에 DbSet&lt;TEntity&gt; 값이 제공되지 않으면 클래스 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-200">If no DbSet&lt;TEntity&gt; value is provided for the given entity, the class name is used.</span></span>

### <a name="data-annotations-versus-fluent-api"></a><span data-ttu-id="7e3c6-201">데이터 주석과 흐름 API 비교</span><span class="sxs-lookup"><span data-stu-id="7e3c6-201">Data Annotations versus Fluent API</span></span>

<span data-ttu-id="7e3c6-202">여러 가지 추가 EF Core 규칙이 있으며, 그 중 대부분은 데이터 주석 또는 흐름 API를 사용하여 변경하고, OnModelCreating 메서드 내에서 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-202">There are many additional EF Core conventions, and most of them can be changed by using either data annotations or Fluent API, implemented within the OnModelCreating method.</span></span>

<span data-ttu-id="7e3c6-203">데이터 주석은 엔터티 모델 클래스 자체에 사용해야 하며, DDD 관점에서 개입 수준이 높은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-203">Data annotations must be used on the entity model classes themselves, which is a more intrusive way from a DDD point of view.</span></span> <span data-ttu-id="7e3c6-204">인프라 데이터베이스와 관련된 데이터 주석으로 모델을 오염시키기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-204">This is because you are contaminating your model with data annotations related to the infrastructure database.</span></span> <span data-ttu-id="7e3c6-205">반면 흐름 API는 데이터 지속성 인프라 계층 내부의 규칙과 매핑을 대부분 변경할 수 있는 편리한 방법으로, 엔터티 모델이 깔끔하고 지속성 인프라와 분리됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-205">On the other hand, Fluent API is a convenient way to change most conventions and mappings within your data persistence infrastructure layer, so the entity model will be clean and decoupled from the persistence infrastructure.</span></span>

### <a name="fluent-api-and-the-onmodelcreating-method"></a><span data-ttu-id="7e3c6-206">흐름 API 및 OnModelCreating 메서드</span><span class="sxs-lookup"><span data-stu-id="7e3c6-206">Fluent API and the OnModelCreating method</span></span>

<span data-ttu-id="7e3c6-207">앞서 언급했듯이, 규칙 및 매핑을 변경하려면 DbContext 클래스의 OnModelCreating 메서드를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-207">As mentioned, in order to change conventions and mappings, you can use the OnModelCreating method in the DbContext class.</span></span> 

<span data-ttu-id="7e3c6-208">eShopOnContainers의 주문 마이크로 서비스는 다음 코드에 보이는 것처럼 필요에 따라 명시적 매핑 및 구성을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-208">The ordering microservice in eShopOnContainers implements explicit mapping and configuration, when needed, as shown in the following code.</span></span>

```csharp
// At OrderingContext.cs from eShopOnContainers
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
   // ...
   modelBuilder.ApplyConfiguration(new OrderEntityTypeConfiguration());
   // Other entities’ configuration ...
}

// At OrderEntityTypeConfiguration.cs from eShopOnContainers
class OrderEntityTypeConfiguration : IEntityTypeConfiguration<Order>
{
    public void Configure(EntityTypeBuilder<Order> orderConfiguration)
    {
            orderConfiguration.ToTable("orders", OrderingContext.DEFAULT_SCHEMA);

            orderConfiguration.HasKey(o => o.Id);

            orderConfiguration.Ignore(b => b.DomainEvents);

            orderConfiguration.Property(o => o.Id)
                .ForSqlServerUseSequenceHiLo("orderseq", OrderingContext.DEFAULT_SCHEMA);

            //Address Value Object persisted as owned entity type supported since EF Core 2.0
            orderConfiguration.OwnsOne(o => o.Address);

            orderConfiguration.Property<DateTime>("OrderDate").IsRequired();
            orderConfiguration.Property<int?>("BuyerId").IsRequired(false);
            orderConfiguration.Property<int>("OrderStatusId").IsRequired();
            orderConfiguration.Property<int?>("PaymentMethodId").IsRequired(false);
            orderConfiguration.Property<string>("Description").IsRequired(false);

            var navigation = orderConfiguration.Metadata.FindNavigation(nameof(Order.OrderItems));
            
            // DDD Patterns comment:
            //Set as field (New since EF 1.1) to access the OrderItem collection property through its field
            navigation.SetPropertyAccessMode(PropertyAccessMode.Field);

            orderConfiguration.HasOne<PaymentMethod>()
                .WithMany()
                .HasForeignKey("PaymentMethodId")
                .IsRequired(false)
                .OnDelete(DeleteBehavior.Restrict);

            orderConfiguration.HasOne<Buyer>()
                .WithMany()
                .IsRequired(false)
                .HasForeignKey("BuyerId");

            orderConfiguration.HasOne(o => o.OrderStatus)
                .WithMany()
                .HasForeignKey("OrderStatusId");
    }
}
```

<span data-ttu-id="7e3c6-209">동일한 OnModelCreating 메서드 내에서 모든 흐름 API 매핑을 설정할 수 있지만, 예제에 보이는 것처럼 해당 코드를 분할하여 여러 구성 클래스를 두는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-209">You could set all the Fluent API mappings within the same OnModelCreating method, but it is advisable to partition that code and have multiple configuration classes, one per entity, as shown in the example.</span></span> <span data-ttu-id="7e3c6-210">특히 매우 큰 모델의 경우 여러 엔터티 형식을 구성하기 위한 별도의 클래스를 두는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-210">Especially for particularly large models, it is advisable to have separate configuration classes for configuring different entity types.</span></span>

<span data-ttu-id="7e3c6-211">예제의 코드는 몇 가지 명시적 선언 및 매핑을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-211">The code in the example shows a few explicit declarations and mapping.</span></span> <span data-ttu-id="7e3c6-212">그러나 EF Core 규칙에서 이러한 매핑의 상당수를 자동으로 처리하므로 필요한 실제 코드 크기는 더 작아질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-212">However, EF Core conventions do many of those mappings automatically, so the actual code you would need in your case might be smaller.</span></span>


### <a name="the-hilo-algorithm-in-ef-core"></a><span data-ttu-id="7e3c6-213">EF Core의 Hi/Lo 알고리즘</span><span class="sxs-lookup"><span data-stu-id="7e3c6-213">The Hi/Lo algorithm in EF Core</span></span>

<span data-ttu-id="7e3c6-214">앞의 예제에서 본 코드의 흥미로운 점은 키 생성 전략으로 [Hi/Lo 알고리즘](https://vladmihalcea.com/2014/06/23/the-hilo-algorithm/)을 사용한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-214">An interesting aspect of code in the preceding example is that it uses the [Hi/Lo algorithm](https://vladmihalcea.com/2014/06/23/the-hilo-algorithm/) as the key generation strategy.</span></span>

<span data-ttu-id="7e3c6-215">Hi/Lo 알고리즘은 고유 키가 필요한 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-215">The Hi/Lo algorithm is useful when you need unique keys.</span></span> <span data-ttu-id="7e3c6-216">요약하자면, Hi-Lo 알고리즘은 테이블 행에 고유 식별자를 할당하지만 행을 데이터베이스에 즉시 저장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-216">As a summary, the Hi-Lo algorithm assigns unique identifiers to table rows while not depending on storing the row in the database immediately.</span></span> <span data-ttu-id="7e3c6-217">따라서 일반 순차적 데이터베이스 ID와 마찬가지로 식별자를 사용하여 바로 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-217">This lets you start using the identifiers right away, as happens with regular sequential database IDs.</span></span>

<span data-ttu-id="7e3c6-218">Hi/Lo 알고리즘은 데이터베이스가 아닌 클라이언트 쪽에서 안전한 ID를 생성하는 메커니즘을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-218">The Hi/Lo algorithm describes a mechanism for generating safe IDs on the client side rather than in the database.</span></span> <span data-ttu-id="7e3c6-219">여기서 말하는 *안전*이란 충돌이 없다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-219">*Safe* in this context means without collisions.</span></span> <span data-ttu-id="7e3c6-220">이 알고리즘이 흥미로운 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-220">This algorithm is interesting for these reasons:</span></span>

-   <span data-ttu-id="7e3c6-221">작업 단위 패턴을 중단하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-221">It does not break the Unit of Work pattern.</span></span>

-   <span data-ttu-id="7e3c6-222">시퀀스 생성기가 다른 DBMS에서 하는 방식으로 라운드트립을 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-222">It does not require round trips the way sequence generators do in other DBMSs.</span></span>

-   <span data-ttu-id="7e3c6-223">GUID를 사용하는 기술은 달리, 사람이 읽을 수 있는 식별자를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-223">It generates a human readable identifier, unlike techniques that use GUIDs.</span></span>

<span data-ttu-id="7e3c6-224">EF Core는 앞의 예제와 같이 ForSqlServerUseSequenceHiLo 메서드를 통해 [HiLo](http://stackoverflow.com/questions/282099/whats-the-hi-lo-algorithm)를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-224">EF Core supports [HiLo](http://stackoverflow.com/questions/282099/whats-the-hi-lo-algorithm) with the ForSqlServerUseSequenceHiLo method, as shown in the preceding example.</span></span>

### <a name="mapping-fields-instead-of-properties"></a><span data-ttu-id="7e3c6-225">속성 대신 필드 매핑</span><span class="sxs-lookup"><span data-stu-id="7e3c6-225">Mapping fields instead of properties</span></span>

<span data-ttu-id="7e3c6-226">EF Core 1.1부터 제공되는 이 기능을 사용하면 열을 필드로 직접 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-226">With this feature, available since EF Core 1.1, you can directly map columns to fields.</span></span> <span data-ttu-id="7e3c6-227">엔터티 클래스에서 속성을 사용하지 않고 테이블에서 필드로 열을 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-227">It is possible to not use properties in the entity class, and just to map columns from a table to fields.</span></span> <span data-ttu-id="7e3c6-228">엔터티 외부에서 액세스할 필요가 없는 내부 상태에 대한 전용 필드가 대표적인 사용 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-228">A common use for that would be private fields for any internal state that do not need to be accessed from outside the entity.</span></span> 

<span data-ttu-id="7e3c6-229">단일 필드를 사용하여 또는 `List<>` 필드 같은 컬렉션을 사용하여 이렇게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-229">You can do this with single fields or also with collections, like a `List<>` field.</span></span> <span data-ttu-id="7e3c6-230">이 부분은 도메인 모델 클래스 모델링에 대해 토론할 때 살펴보았지만, 여기서는 이전 코드에서 강조 표시된 `PropertyAccessMode.Field` 구성을 통해 매핑이 수행되는 방식을 살펴볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-230">This point was mentioned earlier when we discussed modeling the domain model classes, but here you can see how that mapping is performed with the `PropertyAccessMode.Field` configuration highlighted in the previous code.</span></span>

### <a name="using-shadow-properties-in-ef-core-hidden-at-the-infrastructure-level"></a><span data-ttu-id="7e3c6-231">인프라 수준에서 숨겨진 EF Core의 섀도 속성 사용</span><span class="sxs-lookup"><span data-stu-id="7e3c6-231">Using shadow properties in EF Core, hidden at the infrastructure level</span></span>

<span data-ttu-id="7e3c6-232">EF Core의 섀도 속성은 엔터티 클래스 모델에 존재하지 않는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-232">Shadow properties in EF Core are properties that do not exist in your entity class model.</span></span> <span data-ttu-id="7e3c6-233">이러한 속성의 값과 상태는 인프라 수준에서 [ChangeTracker](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.changetracking.changetracker) 클래스에 순수하게 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-233">The values and states of these properties are maintained purely in the [ChangeTracker](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.changetracking.changetracker) class at the infrastructure level.</span></span>


## <a name="implementing-the-specification-pattern"></a><span data-ttu-id="7e3c6-234">사양 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="7e3c6-234">Implementing the Specification pattern</span></span>

<span data-ttu-id="7e3c6-235">디자인 섹션에서 언급했듯이, 사양 패턴(전체 이름은 쿼리 사양 패턴입니다)은 선택적 정렬과 페이징 논리를 사용해 쿼리를 정의 내릴 수 있는 공간으로 디자인된 도메인 기반 디자인 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-235">As introduced earlier in the design section, the Specification pattern (its full name would be Query-specification pattern) is a Domain-Driven Design pattern designed as the place where you can put the definition of a query with optional sorting and paging logic.</span></span> <span data-ttu-id="7e3c6-236">사양 패턴은 개체에서 쿼리를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-236">The Specification pattern defines a query in an object.</span></span> <span data-ttu-id="7e3c6-237">예를 들어 일부 제품을 검색하는 페이징된 쿼리를 캡슐화하려면 필요한 입력 매개 변수(pageNumber, pageSize, 필터 등)를 사용하는 PagedProduct 사양을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-237">For example, in order to encapsulate a paged query that searches for some products you can create a PagedProduct specification that takes the necessary input parameters (pageNumber, pageSize, filter, etc.).</span></span> <span data-ttu-id="7e3c6-238">그런 다음, 리포지토리의 메서드(일반적으로 목록() 오버로드)가 ISpecification을 수용하고 해당 사양을 기반으로 필요한 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-238">Then, any Repository’s method (usually a List() overload) would accept an ISpecification and run the expected query based on that specification.</span></span>

<span data-ttu-id="7e3c6-239">제네릭 사양 인터페이스의 예제는 [eShopOnweb](https://github.com/dotnet-architecture/eShopOnWeb)의 다음 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-239">An example of a generic Specification interface is the following code from [eShopOnweb](https://github.com/dotnet-architecture/eShopOnWeb).</span></span> 

```csharp
// GENERIC SPECIFICATION INTERFACE
// https://github.com/dotnet-architecture/eShopOnWeb 

public interface ISpecification<T>
{
    Expression<Func<T, bool>> Criteria { get; }
    List<Expression<Func<T, object>>> Includes { get; }
    List<string> IncludeStrings { get; }
}
```

<span data-ttu-id="7e3c6-240">그런 다음, 제네릭 사양 기본 클래스의 구현은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-240">Then, the implementation of a generic specification base class is the following.</span></span>

```csharp
// GENERIC SPECIFICATION IMPLEMENTATION (BASE CLASS)
// https://github.com/dotnet-architecture/eShopOnWeb
 
public abstract class BaseSpecification<T> : ISpecification<T>
{
    public BaseSpecification(Expression<Func<T, bool>> criteria)
    {
        Criteria = criteria;
    }
    public Expression<Func<T, bool>> Criteria { get; }

    public List<Expression<Func<T, object>>> Includes { get; } = 
                                           new List<Expression<Func<T, object>>>();

    public List<string> IncludeStrings { get; } = new List<string>();
 
    protected virtual void AddInclude(Expression<Func<T, object>> includeExpression)
    {
        Includes.Add(includeExpression);
    }
    
    // string-based includes allow for including children of children
    // e.g. Basket.Items.Product
    protected virtual void AddInclude(string includeString)
    {
        IncludeStrings.Add(includeString);
    }
}
```

<span data-ttu-id="7e3c6-241">다음 사양은 장바구니의 ID 또는 장바구니가 속한 구매자의 ID가 지정된 단일 장바구니 엔터티를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-241">The following specification loads a single basket entity given either the basket’s ID or the ID of the buyer to whom the basket belongs.</span></span> <span data-ttu-id="7e3c6-242">장바구니의 항목 컬렉션을 [즉시 로드](https://docs.microsoft.com/en-us/ef/core/querying/related-data)합니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-242">It will [eager load](https://docs.microsoft.com/en-us/ef/core/querying/related-data) the basket’s Items collection.</span></span>

```csharp
// SAMPLE QUERY SPECIFICATION IMPLEMENTATION

public class BasketWithItemsSpecification : BaseSpecification<Basket>
{
    public BasketWithItemsSpecification(int basketId)
        : base(b => b.Id == basketId)
    {
        AddInclude(b => b.Items);
    }
    public BasketWithItemsSpecification(string buyerId)
        : base(b => b.BuyerId == buyerId)
    {
        AddInclude(b => b.Items);
    }
}
```

<span data-ttu-id="7e3c6-243">마지막으로, 아래를 보시면 제네릭 EF 리포지토리가 사양을 사용하여 특정 엔터티 형식 T와 관련된 데이터를 필터링하고 즉시 로드하는 원리를 살펴볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-243">And finally, you can see below how a generic EF Repository can use such a specification to filter and eager-load data related to a given entity type T.</span></span>

```csharp
// GENERIC EF REPOSITORY WITH SPECIFICATION
// https://github.com/dotnet-architecture/eShopOnWeb

public IEnumerable<T> List(ISpecification<T> spec)
{
    // fetch a Queryable that includes all expression-based includes
    var queryableResultWithIncludes = spec.Includes
        .Aggregate(_dbContext.Set<T>().AsQueryable(),
            (current, include) => current.Include(include));
 
    // modify the IQueryable to include any string-based include statements
    var secondaryResult = spec.IncludeStrings
        .Aggregate(queryableResultWithIncludes,
            (current, include) => current.Include(include));
 
    // return the result of the query using the specification's criteria expression
    return secondaryResult
                    .Where(spec.Criteria)
                    .AsEnumerable();
}
```
<span data-ttu-id="7e3c6-244">사양은 필터링 논리를 캡슐화할 뿐 아니라 채울 속성을 포함하여 반환될 데이터의 모양을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-244">In addition to encapsulating filtering logic, the specification can specify the shape of the data to be returned, including which properties to populate.</span></span> 

<span data-ttu-id="7e3c6-245">리포지토리에서 IQueryable을 반환하는 것을 권장하지는 않지만, 리포지토리 내에서 사용하여 결과 집합을 빌드하는 데 사용하는 것은 아무 문제 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-245">Although we don't recommended to return IQueryable from a repository, it’s perfectly fine to use them within the repository to build up a set of results.</span></span> <span data-ttu-id="7e3c6-246">위의 List 메서드에 이 접근 방식이 사용된 것을 볼 수 있습니다. 중간 IQueryable 식을 사용하여 쿼리의 포함 목록을 빌드한 후 마지막 줄에서 사양의 기준을 사용하여 쿼리가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e3c6-246">You can see this approach used in the List method above, which uses intermediate IQueryable expressions to build up the query’s list of includes before executing the query with the specification’s criteria on the last line.</span></span>


#### <a name="additional-resources"></a><span data-ttu-id="7e3c6-247">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="7e3c6-247">Additional resources</span></span>

-   <span data-ttu-id="7e3c6-248">**테이블 매핑**
    [*https://docs.microsoft.com/ef/core/modeling/relational/tables*](https://docs.microsoft.com/ef/core/modeling/relational/tables)</span><span class="sxs-lookup"><span data-stu-id="7e3c6-248">**Table Mapping**
[*https://docs.microsoft.com/ef/core/modeling/relational/tables*](https://docs.microsoft.com/ef/core/modeling/relational/tables)</span></span>

-   <span data-ttu-id="7e3c6-249">**HiLo를 사용하여 Entity Framework Core로 키 생성**
    [*http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/*](http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/)</span><span class="sxs-lookup"><span data-stu-id="7e3c6-249">**Use HiLo to generate keys with Entity Framework Core**
[*http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/*](http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/)</span></span>

-   <span data-ttu-id="7e3c6-250">**필드 백업**
    [*https://docs.microsoft.com/ef/core/modeling/backing-field*](https://docs.microsoft.com/ef/core/modeling/backing-field)</span><span class="sxs-lookup"><span data-stu-id="7e3c6-250">**Backing Fields**
[*https://docs.microsoft.com/ef/core/modeling/backing-field*](https://docs.microsoft.com/ef/core/modeling/backing-field)</span></span>

-   <span data-ttu-id="7e3c6-251">**Steve Smith. Entity Framework Core에서 컬렉션 캡슐화**
    [*http://ardalis.com/encapsulated-collections-in-entity-framework-core*](http://ardalis.com/encapsulated-collections-in-entity-framework-core)</span><span class="sxs-lookup"><span data-stu-id="7e3c6-251">**Steve Smith. Encapsulated Collections in Entity Framework Core**
[*http://ardalis.com/encapsulated-collections-in-entity-framework-core*](http://ardalis.com/encapsulated-collections-in-entity-framework-core)</span></span>

-   <span data-ttu-id="7e3c6-252">**섀도 속성**
    [*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span><span class="sxs-lookup"><span data-stu-id="7e3c6-252">**Shadow Properties**
[*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span></span>

-   <span data-ttu-id="7e3c6-253">**사양 패턴**
    [*http://deviq.com/specification-pattern/*](http://deviq.com/specification-pattern/)</span><span class="sxs-lookup"><span data-stu-id="7e3c6-253">**The Specification pattern**
[*http://deviq.com/specification-pattern/*](http://deviq.com/specification-pattern/)</span></span>
    

>[!div class="step-by-step"]
<span data-ttu-id="7e3c6-254">[이전] (infrastructure-persistence-layer-design.md) [다음] (nosql-database-persistence-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="7e3c6-254">[Previous] (infrastructure-persistence-layer-design.md) [Next] (nosql-database-persistence-infrastructure.md)</span></span>
