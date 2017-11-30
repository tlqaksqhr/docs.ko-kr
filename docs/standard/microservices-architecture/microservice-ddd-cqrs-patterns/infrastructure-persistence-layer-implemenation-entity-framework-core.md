---
title: "Entity Framework 코어 인프라 지 속성 계층 구현"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | Entity Framework 코어 인프라 지 속성 계층 구현"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 508d60d73eb7c0f0cc2cc909613cc4f8712b4aba
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-the-infrastructure-persistence-layer-with-entity-framework-core"></a><span data-ttu-id="b9261-104">Entity Framework 코어 인프라 지 속성 계층 구현</span><span class="sxs-lookup"><span data-stu-id="b9261-104">Implementing the infrastructure persistence layer with Entity Framework Core</span></span>

<span data-ttu-id="b9261-105">SQL Server, Oracle 또는 PostgreSQL와 같은 관계형 데이터베이스를 사용 하면 Entity Framework (EF)에 따라 지 속성 계층을 구현 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-105">When you use relational databases such as SQL Server, Oracle, or PostgreSQL, a recommended approach is to implement the persistence layer based on Entity Framework (EF).</span></span> <span data-ttu-id="b9261-106">EF는 LINQ 지원 하 고 간소화 된 지 속성 데이터베이스에 뿐만 아니라 모델을 사용자에 대 한 강력한 형식의 개체를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-106">EF supports LINQ and provides strongly typed objects for your model, as well as simplified persistence into your database.</span></span>

<span data-ttu-id="b9261-107">Entity Framework는.NET Framework의 일부로 오랜 전통을 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-107">Entity Framework has a long history as part of the .NET Framework.</span></span> <span data-ttu-id="b9261-108">.NET Core를 사용 하면.NET Core와 마찬가지로 Windows 또는 Linux에서 실행 되는 Entity Framework Core도 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-108">When you use .NET Core, you should also use Entity Framework Core, which runs on Windows or Linux in the same way as .NET Core.</span></span> <span data-ttu-id="b9261-109">EF 핵심은 중요 한 성능 향상과 훨씬 더 작은 사용 공간을 사용 하 여 구현 되는 Entity Framework의 완전히 다시 작성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-109">EF Core is a complete rewrite of Entity Framework, implemented with a much smaller footprint and important improvements in performance.</span></span>

## <a name="introduction-to-entity-framework-core"></a><span data-ttu-id="b9261-110">Entity Framework Core 소개</span><span class="sxs-lookup"><span data-stu-id="b9261-110">Introduction to Entity Framework Core</span></span>

<span data-ttu-id="b9261-111">Entity Framework (EF) Core, 확장 가능한 경량 및 플랫폼 버전의 인기 있는 Entity Framework 데이터 액세스 기술을 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-111">Entity Framework (EF) Core is a lightweight, extensible, and cross-platform version of the popular Entity Framework data access technology.</span></span> <span data-ttu-id="b9261-112">.NET Core 2016 중순에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-112">It was introduced with .NET Core in mid-2016.</span></span>

<span data-ttu-id="b9261-113">EF 코어에 대 한 소개 Microsoft 문서에 이미 이므로 여기 단순히 제공 해당 정보에 대 한 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-113">Since an introduction to EF Core is already available in Microsoft documentation, here we simply provide links to that information.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="b9261-114">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="b9261-114">Additional resources</span></span>

-   <span data-ttu-id="b9261-115">**Entity Framework Core**
    [*https://docs.microsoft.com/ef/core/*](https://docs.microsoft.com/ef/core/)</span><span class="sxs-lookup"><span data-stu-id="b9261-115">**Entity Framework Core**
[*https://docs.microsoft.com/ef/core/*](https://docs.microsoft.com/ef/core/)</span></span>

-   <span data-ttu-id="b9261-116">**Visual Studio를 사용 하 여 Entity Framework Core 및 ASP.NET Core 시작**
    [*https://docs.microsoft.com/aspnet/core/data/ef-mvc/*](https://docs.microsoft.com/aspnet/core/data/ef-mvc/)</span><span class="sxs-lookup"><span data-stu-id="b9261-116">**Getting started with ASP.NET Core and Entity Framework Core using Visual Studio**
[*https://docs.microsoft.com/aspnet/core/data/ef-mvc/*](https://docs.microsoft.com/aspnet/core/data/ef-mvc/)</span></span>

-   <span data-ttu-id="b9261-117">**DbContext 클래스**
    [*https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext*](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext)</span><span class="sxs-lookup"><span data-stu-id="b9261-117">**DbContext Class**
[*https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext*](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext)</span></span>

-   <span data-ttu-id="b9261-118">**EF 코어 & EF6.x 비교**
    [*https://docs.microsoft.com/ef/efcore-and-ef6/index*](https://docs.microsoft.com/ef/efcore-and-ef6/index)</span><span class="sxs-lookup"><span data-stu-id="b9261-118">**Compare EF Core & EF6.x**
[*https://docs.microsoft.com/ef/efcore-and-ef6/index*](https://docs.microsoft.com/ef/efcore-and-ef6/index)</span></span>

## <a name="infrastructure-in-entity-framework-core-from-a-ddd-perspective"></a><span data-ttu-id="b9261-119">DDD 관점에서의 Entity Framework Core 인프라</span><span class="sxs-lookup"><span data-stu-id="b9261-119">Infrastructure in Entity Framework Core from a DDD perspective</span></span>

<span data-ttu-id="b9261-120">DDD 관점에서의 EF는 중요 한 기능은 POCO 도메인 엔터티, 라고도 POCO로 EF 용어를 사용 하는 기능 *코드 중심 엔터티*합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-120">From a DDD point of view, an important capability of EF is the ability to use POCO domain entities, also known in EF terminology as POCO *code-first entities*.</span></span> <span data-ttu-id="b9261-121">도메인 모델 클래스는 지 속성 무시를 따라 POCO 도메인 엔터티를 사용 하는 경우는 [지 속성 무시](http://deviq.com/persistence-ignorance/) 및 [인프라 무시](https://ayende.com/blog/3137/infrastructure-ignorance) 원칙입니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-121">If you use POCO domain entities, your domain model classes are persistence-ignorant, following the [Persistence Ignorance](http://deviq.com/persistence-ignorance/) and the [Infrastructure Ignorance](https://ayende.com/blog/3137/infrastructure-ignorance) principles.</span></span>

<span data-ttu-id="b9261-122">DDD 패턴 당 제어할 수 있도록 고정, 유효성 검사 및 규칙 컬렉션에 액세스할 때 도메인 동작 및 엔터티 클래스 자체 내에 있는 규칙을 캡슐화 해야 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-122">Per DDD patterns, you should encapsulate domain behavior and rules within the entity class itself, so it can control invariants, validations, and rules when accessing any collection.</span></span> <span data-ttu-id="b9261-123">따라서 ddd 엔터티 또는 개체의 자식 컬렉션에 대 한 공용 액세스를 허용 하는 것이 좋습니다 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-123">Therefore, it is not a good practice in DDD to allow public access to collections of child entities or value objects.</span></span> <span data-ttu-id="b9261-124">대신, 시기와 방법을 필드 및 속성 컬렉션, 업데이트를 제어 하는 메서드는 동작 및 동작에 도달 하면 발생 해야 표시 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-124">Instead, you want to expose methods that control how and when your fields and property collections can be updated, and what behavior and actions should occur when that happens.</span></span>

<span data-ttu-id="b9261-125">EF 코어 1.1에서는 이러한 DDD 요구 사항을 충족 하기 위해 일반 필드를 공용 및 개인 setter 사용 하 여 속성 대신 엔터티의 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-125">In EF Core 1.1, to satisfy those DDD requirements you can have plain fields in your entities instead of properties with public and private setters.</span></span> <span data-ttu-id="b9261-126">외부에서 액세스할 수 있도록 엔터티 필드 하지 않으려면 특성 또는 속성 대신 필드가 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-126">If you do not want an entity field to be externally accessible, you can just create the attribute or field instead of a property.</span></span> <span data-ttu-id="b9261-127">이 클리너 방법을 선호 하는 경우 개인 setter를 사용 하도록 않아도가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-127">There is no need to use private setters if you prefer this cleaner approach.</span></span>

<span data-ttu-id="b9261-128">이와 비슷한 방식으로에서 이제 포함할 수 있습니다 컬렉션에 대 한 읽기 전용 액세스 IEnumerable로 형식화 된 public 속성을 사용 하 여&lt;T&gt;는 컬렉션에 대 한 전용 필드 멤버에 의해 지원 됩니다 (목록을 같은&lt;&gt;)에서 프로그램 지 속성에 대 한 EF에 의존 하는 엔터티.</span><span class="sxs-lookup"><span data-stu-id="b9261-128">In a similar way, you can now have read-only access to collections by using a public property typed as IEnumerable&lt;T&gt;, which is backed by a private field member for the collection (like a List&lt;&gt;) in your entity that relies on EF for persistence.</span></span> <span data-ttu-id="b9261-129">ICollection을 지원 하기 위해 컬렉션 속성에 필요한 이전 버전의 Entity Framework&lt;T&gt;, 부모 엔터티 클래스를 사용 하 여 모든 개발자 추가 하거나 해당 속성 컬렉션에서 항목을 제거 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-129">Previous versions of Entity Framework required collection properties to support ICollection&lt;T&gt;, which meant that any developer using the parent entity class could add or remove items from its property collections.</span></span> <span data-ttu-id="b9261-130">이 가능성 ddd에서 권장된 패턴에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-130">That possibility would be against the recommended patterns in DDD.</span></span>

<span data-ttu-id="b9261-131">다음 코드 예제와 같이 읽기 전용 IEnumerable 개체를 노출 하는 동안 개인 컬렉션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-131">You can use a private collection while exposing a read-only IEnumerable object, as shown in the following code example:</span></span>

```csharp
public class Order : Entity
{
    // Using private fields, allowed since EF Core 1.1
    private DateTime _orderDate;
    // Other fields ...
    private readonly List<OrderItem> _orderItems;

    public IEnumerable<OrderItem> OrderItems => _orderItems.AsReadOnly();

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
        var orderItem = new OrderItem(productId, productName, unitPrice, discount,
            pictureUrl, units);
        _orderItems.Add(orderItem);
    }
}
```

<span data-ttu-id="b9261-132">읽기 전용으로 목록을 사용 하 여 OrderItems 속성 액세스할만 있습니다&lt;&gt;합니다. AsReadOnly() 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-132">Note that the OrderItems property can only be accessed as read-only using List&lt;&gt;.AsReadOnly().</span></span> <span data-ttu-id="b9261-133">이 메서드는 외부 업데이트를 방지할 수 있도록 개인 목록에 읽기 전용 래퍼를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-133">This method creates a read-only wrapper around the private list so that it is protected against external updates.</span></span> <span data-ttu-id="b9261-134">새 컬렉션;에 있는 모든 항목을 복사할 필요가 없기 때문에 훨씬 저렴 ToList 메서드를 사용 하는 것은 대신, 래퍼 인스턴스에 대 한 하나의 힙 할당 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-134">It is much cheaper than using the ToList method, because it does not have to copy all the items in a new collection; instead, it performs just one heap alloc operation for the wrapper instance.</span></span>

<span data-ttu-id="b9261-135">EF 핵심 도메인 모델 시키는 하지 않고 도메인 모델 물리적 데이터베이스에 매핑할 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-135">EF Core provides a way to map the domain model to the physical database without contaminating the domain model.</span></span> <span data-ttu-id="b9261-136">순수.NET POCO 코드 매핑 작업은 지 속성 계층에서 구현 되는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-136">It is pure .NET POCO code, because the mapping action is implemented in the persistence layer.</span></span> <span data-ttu-id="b9261-137">해당 매핑 작업에서 데이터베이스에 필드 매핑을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-137">In that mapping action, you need to configure the fields-to-database mapping.</span></span> <span data-ttu-id="b9261-138">OnModelCreating 메서드의 다음 예제에서는 강조 표시 된 코드는 해당 필드를 통해 OrderItems 속성에 액세스 하려면 EF 코어를 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-138">In the following example of an OnModelCreating method, the highlighted code tells EF Core to access the OrderItems property through its field.</span></span>

```csharp
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
    // ...
    modelBuilder.Entity<Order>(ConfigureOrder);
    // Other entities ...
}

void ConfigureOrder(EntityTypeBuilder<Order> orderConfiguration)
{
    // Other configuration ...
    var navigation = orderConfiguration.Metadata.
    FindNavigation(nameof(Order.OrderItems));
    navigation.SetPropertyAccessMode(PropertyAccessMode.Field);
    // Other configuration ...
}
```

<span data-ttu-id="b9261-139">경우 목록을 것 처럼 OrderItem 엔터티 속성 대신 필드를 사용 하는 경우 유지 됩니다&lt;OrderItem&gt; 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-139">When you use fields instead of properties, the OrderItem entity is persisted just as if it had a List&lt;OrderItem&gt; property.</span></span> <span data-ttu-id="b9261-140">그러나 순서에 새 항목을 추가 하기 위한 하나의 접근자 (AddOrderItem 메서드)을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-140">However, it exposes a single accessor (the AddOrderItem method) for adding new items to the order.</span></span> <span data-ttu-id="b9261-141">결과적으로, 동작 및 데이터 함께 연결 되 고 도메인 모델을 사용 하는 응용 프로그램 코드 전체에서 일관성 있게 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-141">As a result, behavior and data are tied together and will be consistent throughout any application code that uses the domain model.</span></span>

## <a name="implementing-custom-repositories-with-entity-framework-core"></a><span data-ttu-id="b9261-142">Entity Framework Core의 사용자 지정 저장소를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-142">Implementing custom repositories with Entity Framework Core</span></span>

<span data-ttu-id="b9261-143">저장소의 데이터 지 속성 코드 단위의 (EF 코어에 DBContext) 작업에 의해 조정 된 클래스는 구현 단계에서 다음과 같은 클래스의 표시 된 것 처럼 업데이트를 수행 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="b9261-143">At the implementation level, a repository is simply a class with data persistence code coordinated by a unit of work (DBContext in EF Core) when performing updates, as shown in the following class:</span></span>

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
    }

    public BuyerRepository(OrderingContext context)
    {
        if (context == null)
        {
            throw new ArgumentNullException(
                nameof(context));
        }
        _context = context;
    }

    public Buyer Add(Buyer buyer)
    {
        return _context.Buyers.Add(buyer).Entity;
    }

    public async Task<Buyer> FindAsync(string BuyerIdentityGuid)
    {
        var buyer = await _context.Buyers.Include(b => b.Payments)
            .Where(b => b.FullName == BuyerIdentityGuid)
            .SingleOrDefaultAsync();
        return buyer;
    }
}
```

<span data-ttu-id="b9261-144">도메인 모델 계층에서 IBuyerRepository 인터페이스가 제공 됨을 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-144">Note that the IBuyerRepository interface comes from the domain model layer.</span></span> <span data-ttu-id="b9261-145">그러나 저장소 구현은 지 속성 및 인프라 계층에서 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-145">However, the repository implementation is done at the persistence and infrastructure layer.</span></span>

<span data-ttu-id="b9261-146">EF DbContext 종속성 주입을 통해 생성자를 통해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-146">The EF DbContext comes through the constructor through Dependency Injection.</span></span> <span data-ttu-id="b9261-147">(또한 설정 될 수 있는 명시적으로 서비스와 IoC 컨테이너에 해당 기본 수명 (ServiceLifetime.Scoped) 덕분에 동일한 HTTP 요청 범위 내에서 여러 저장소 간에 공유 됩니다. AddDbContext&lt;&gt;).</span><span class="sxs-lookup"><span data-stu-id="b9261-147">It is shared between multiple repositories within the same HTTP request scope, thanks to its default lifetime (ServiceLifetime.Scoped) in the IoC container (which can also be explicitly set with services.AddDbContext&lt;&gt;).</span></span>

### <a name="methods-to-implement-in-a-repository-updates-or-transactions-versus-queries"></a><span data-ttu-id="b9261-148">저장소 (업데이트 또는 쿼리 트랜잭션을)에서 구현 하는 방법</span><span class="sxs-lookup"><span data-stu-id="b9261-148">Methods to implement in a repository (updates or transactions versus queries)</span></span>

<span data-ttu-id="b9261-149">각 저장소 클래스 내에서 관련된 해당 집계에 의해 포함 된 엔터티 상태를 업데이트 하는 지 속성 메서드를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-149">Within each repository class, you should put the persistence methods that update the state of entities contained by its related aggregate.</span></span> <span data-ttu-id="b9261-150">집계 및 해당 관련된 저장소 간에 일대일 관계가 기억 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-150">Remember there is one-to-one relationship between an aggregate and its related repository.</span></span> <span data-ttu-id="b9261-151">집계 루트 엔터티 개체 수의 EF 그래프 내의 자식 엔터티 삽입 한 것을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-151">Take into account that an aggregate root entity object might have embedded child entities within its EF graph.</span></span> <span data-ttu-id="b9261-152">예를 들어 구매자 관련된 자식 엔터티로 여러 지불 메서드가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-152">For example, a buyer might have multiple payment methods as related child entities.</span></span>

<span data-ttu-id="b9261-153">EShopOnContainers에 정렬 마이크로 서비스에 대 한 접근 방식을 CQS/CQRS도 기반,으로 하기 때문에 사용자 지정 저장소에서 대부분의 쿼리가 구현 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-153">Since the approach for the ordering microservice in eShopOnContainers is also based on CQS/CQRS, most of the queries are not implemented in custom repositories.</span></span> <span data-ttu-id="b9261-154">개발자는 쿼리 및 일반적으로 집계를 집계 및 DDD 당 사용자 지정 저장소 설정 된 제한을 없이 프레젠테이션 계층에 대 한 필요한 조인을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-154">Developers have the freedom to create the queries and joins they need for the presentation layer without the restrictions imposed by aggregates, custom repositories per aggregate, and DDD in general.</span></span> <span data-ttu-id="b9261-155">이 가이드에서 제시 된 사용자 지정 저장소는 대부분 여러 업데이트나 트랜잭션 메서드 들에 게는 쿼리 메서드 데이터를 업데이트 하기 위해 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-155">Most of the custom repositories suggested by this guide have several update or transactional methods but just the query methods needed to get data to be updated.</span></span> <span data-ttu-id="b9261-156">예를 들어 BuyerRepository 저장소는 응용 프로그램이 특정 구매자 순서와 관련 된 새 구매자를 만들기 전에 있는지 여부를 알고 있어야 하기 때문에 FindAsync 메서드를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-156">For example, the BuyerRepository repository implements a FindAsync method, because the application needs to know whether a particular buyer exists before creating a new buyer related to the order.</span></span>

<span data-ttu-id="b9261-157">그러나 프레젠테이션 계층 또는 클라이언트 응용 프로그램에 보낼 데이터를 가져올 실제 쿼리 메서드의 구현 언급 했 듯이 Dapper를 사용 하 여 유연한 쿼리를 기준으로 CQRS 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-157">However, the real query methods to get data to send to the presentation layer or client apps are implemented, as mentioned, in the CQRS queries based on flexible queries using Dapper.</span></span>

### <a name="using-a-custom-repository-versus-using-ef-dbcontext-directly"></a><span data-ttu-id="b9261-158">및 EF DbContext를 직접 사용 하는 사용자 지정 저장소를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="b9261-158">Using a custom repository versus using EF DbContext directly</span></span>

<span data-ttu-id="b9261-159">Entity Framework DbContext 클래스 기반 작업 단위 및 저장소 패턴으로 하며 수에서 사용할 수 사용자 코드에서 직접과 같은 ASP.NET Core MVC 컨트롤러입니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-159">The Entity Framework DbContext class is based on the Unit of Work and Repository patterns, and can be used directly from your code, such as from an ASP.NET Core MVC controller.</span></span> <span data-ttu-id="b9261-160">즉 방식 eShopOnContainers에서 CRUD 카탈로그 마이크로 서비스와 같이 가장 간단한 코드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-160">That is the way you can create the simplest code, as in the CRUD catalog microservice in eShopOnContainers.</span></span> <span data-ttu-id="b9261-161">저장할 가장 간단한 코드 가능한 경우에서 하려는 직접 DbContext 클래스를 사용 하 여 대부분의 개발자와 마찬가지로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-161">In cases where you want the simplest code possible, you might want to directly use the DbContext class, as many developers do.</span></span>

<span data-ttu-id="b9261-162">그러나 사용자 지정 저장소 구현 보다 복잡 한 microservices 또는 응용 프로그램을 구현 하는 경우 여러 가지 이점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-162">However, implementing custom repositories provides several benefits when implementing more complex microservices or applications.</span></span> <span data-ttu-id="b9261-163">작업 단위 및 저장소 패턴 되는 응용 프로그램 및 도메인 모델 계층에서 분리 되므로 인프라 지 속성 계층을 캡슐화 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-163">The Unit of Work and Repository patterns are intended to encapsulate the infrastructure persistence layer so it is decoupled from the application and domain model layers.</span></span> <span data-ttu-id="b9261-164">이러한 패턴을 구현 모의 리포지토리 데이터베이스에 대 한 액세스를 시뮬레이션을 사용할을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-164">Implementing these patterns can facilitate the use of mock repositories simulating access to the database.</span></span>

<span data-ttu-id="b9261-165">그림 9-18를 쉽게 이러한 저장소의 모의 리포지토리를 사용 하 여와 차이점 (사용 하 여 직접 EF DbContext) 저장소를 사용 하지를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-165">In Figure 9-18 you can see the differences between not using repositories (directly using the EF DbContext) versus using repositories which make it easier to mock those repositories.</span></span>

![](./media/image19.png)

<span data-ttu-id="b9261-166">**그림 9-18**합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-166">**Figure 9-18**.</span></span> <span data-ttu-id="b9261-167">일반 DbContext와 사용자 지정 저장소를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="b9261-167">Using custom repositories versus a plain DbContext</span></span>

<span data-ttu-id="b9261-168">모의 하는 데는 여러 대체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-168">There are multiple alternatives when mocking.</span></span> <span data-ttu-id="b9261-169">정당한 저장소 모의 수 또는 작업의 전체 단위의 모의 알림 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-169">You could mock just repositories or you could mock a whole unit of work.</span></span> <span data-ttu-id="b9261-170">일반적으로 리포지토리만 모의 충분히 이며 복잡성을 추상화 하 고 작업의 전체 단위의 모의 알림 일반적으로 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-170">Usually mocking just the repositories is enough, and the complexity to abstract and mock a whole unit of work is usually not needed.</span></span>

<span data-ttu-id="b9261-171">이상에서는 응용 프로그램 계층에 대해 살펴볼 때 표시 됩니다 ASP.NET Core에서 종속성 삽입의 작동 방식 및 구현 하는 저장소를 사용 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="b9261-171">Later, when we focus on the application layer, you will see how Dependency Injection works in ASP.NET Core and how it is implemented when using repositories.</span></span>

<span data-ttu-id="b9261-172">즉, 사용자 지정 저장소 데이터 계층 상태에 의해 영향을 받지 않는 단위 테스트 코드를 보다 쉽게 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-172">In short, custom repositories allow you to test code more easily with unit tests that are not impacted by the data tier state.</span></span> <span data-ttu-id="b9261-173">또한 엔터티 프레임 워크를 통해 실제 데이터베이스에 액세스 하는 테스트를 실행 하는 경우 없는 단위 테스트 하지만 훨씬 더 느리기 통합 테스트를 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-173">If you run tests that also access the actual database through the Entity Framework, they are not unit tests but integration tests, which are a lot slower.</span></span>

<span data-ttu-id="b9261-174">DbContext를 직접 사용 된 경우 유일한 선택 해야 하는 단위 테스트에 대 한 예측 가능한 데이터를 메모리에 SQL Server를 사용 하 여 단위 테스트를 실행 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-174">If you were using DbContext directly, the only choice you would have would be to run unit tests by using an in-memory SQL Server with predictable data for unit tests.</span></span> <span data-ttu-id="b9261-175">모의 개체 및 가짜 데이터 저장소 수준에서 같은 방식으로 제어할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-175">You would not be able to control mock objects and fake data in the same way at the repository level.</span></span> <span data-ttu-id="b9261-176">물론, 항상 MVC 컨트롤러를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-176">Of course, you could always test the MVC controllers.</span></span>

## <a name="ef-dbcontext-and-iunitofwork-instance-lifetime-in-your-ioc-container"></a><span data-ttu-id="b9261-177">IoC 컨테이너의 EF DbContext 및 IUnitOfWork 인스턴스 수명</span><span class="sxs-lookup"><span data-stu-id="b9261-177">EF DbContext and IUnitOfWork instance lifetime in your IoC container</span></span>

<span data-ttu-id="b9261-178">DbContext 개체 (IUnitOfWork 개체로 노출) 같은 HTTP 요청 범위 내에서 여러 저장소 간에 공유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-178">The DbContext object (exposed as an IUnitOfWork object) might need to be shared among multiple repositories within the same HTTP request scope.</span></span> <span data-ttu-id="b9261-179">예를 들어이 true 인 작업을 실행 중인 여러 집계 또는 단순히 처리 해야 하는 경우 여러 저장소 인스턴스를 사용 중 이므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-179">For example, this is true when the operation being executed must deal with multiple aggregates, or simply because you are using multiple repository instances.</span></span> <span data-ttu-id="b9261-180">것도 IUnitOfWork 인터페이스 EF 형식이 아닌 도메인의 일부 인지 언급 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-180">It is also important to mention that the IUnitOfWork interface is part of the domain, not an EF type.</span></span>

<span data-ttu-id="b9261-181">파일을 수집 하려면에 DbContext 개체의 인스턴스 ServiceLifetime.Scoped로 설정 하 여 서비스 수명 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-181">In order to do that, the instance of the DbContext object has to have its service lifetime set to ServiceLifetime.Scoped.</span></span> <span data-ttu-id="b9261-182">기본 수명 때 서비스와 DbContext를 등록 하는 중입니다. ASP.NET Core 웹 API 프로젝트에 Startup.cs 파일의 ConfigureServices 메서드에서 IoC 컨테이너의 AddDbContext 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-182">This is the default lifetime when registering a DbContext with services.AddDbContext in your IoC container from the ConfigureServices method of the Startup.cs file in your ASP.NET Core Web API project.</span></span> <span data-ttu-id="b9261-183">다음 코드에서는 이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-183">The following code illustrates this.</span></span>

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
        sqlop => sqlop.MigrationsAssembly(typeof(Startup).GetTypeInfo().
        Assembly.GetName().Name));
    },
    ServiceLifetime.Scoped // Note that Scoped is the default choice
    // in AddDbContext. It is shown here only for
    // pedagogic purposes.
    );
}
```

<span data-ttu-id="b9261-184">DbContext 인스턴스화 모드 ServiceLifetime.Transient 또는 ServiceLifetime.Singleton로 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-184">The DbContext instantiation mode should not be configured as ServiceLifetime.Transient or ServiceLifetime.Singleton.</span></span>

## <a name="the-repository-instance-lifetime-in-your-ioc-container"></a><span data-ttu-id="b9261-185">IoC 컨테이너의 저장소 인스턴스 수명</span><span class="sxs-lookup"><span data-stu-id="b9261-185">The repository instance lifetime in your IoC container</span></span>

<span data-ttu-id="b9261-186">비슷한 방식으로 저장소의 수명 범위 지정 된 (Autofac에 InstancePerLifetimeScope)으로 설정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-186">In a similar way, repository’s lifetime should usually be set as scoped (InstancePerLifetimeScope in Autofac).</span></span> <span data-ttu-id="b9261-187">또한 수 범위 지정 된 기간을 사용 하는 경우 서비스 이지만 (Autofac에 InstancePerDependency) 일시적이 지 더욱 효율적으로 메모리에 대 한 예정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-187">It could also be transient (InstancePerDependency in Autofac), but your service will be more efficient in regards memory when using the scoped lifetime.</span></span>

```csharp
// Registering a Repository in Autofac IoC container
builder.RegisterType<OrderRepository>()
    .As<IOrderRepository>()
    .InstancePerLifetimeScope();
```

<span data-ttu-id="b9261-188">Singleton 수명을 사용 하 여 저장소에 대 한 문제를 일으킬 수 있습니다 심각한 동시성에 DbContext로 설정 되는 범위 (InstancePerLifetimeScope) 수명 (DBContext에 대해 기본 수명).</span><span class="sxs-lookup"><span data-stu-id="b9261-188">Note that using the singleton lifetime for the repository could cause you serious concurrency problems when your DbContext is set to scoped (InstancePerLifetimeScope) lifetime (the default lifetimes for a DBContext).</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="b9261-189">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="b9261-189">Additional resources</span></span>

-   <span data-ttu-id="b9261-190">**ASP.NET MVC 응용 프로그램에서 저장소 및 단위 작업 패턴의 구현은**
    [*https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/ implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application*](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)</span><span class="sxs-lookup"><span data-stu-id="b9261-190">**Implementing the Repository and Unit of Work Patterns in an ASP.NET MVC Application**
[*https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application*](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)</span></span>

-   <span data-ttu-id="b9261-191">**Jonathan Allen 합니다. 저장소에 대 한 구현 전략 Dapper, Entity Framework와 함께 패턴을 사용 하며, 연결**
    [*https://www.infoq.com/articles/repository-implementation-strategies*](https://www.infoq.com/articles/repository-implementation-strategies)</span><span class="sxs-lookup"><span data-stu-id="b9261-191">**Jonathan Allen. Implementation Strategies for the Repository Pattern with Entity Framework, Dapper, and Chain**
[*https://www.infoq.com/articles/repository-implementation-strategies*](https://www.infoq.com/articles/repository-implementation-strategies)</span></span>

-   <span data-ttu-id="b9261-192">**Cesar de la Torre. ASP.NET Core IoC 컨테이너 서비스 수명을 Autofac IoC 컨테이너 인스턴스 범위를 비교**
    [*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/ comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)</span><span class="sxs-lookup"><span data-stu-id="b9261-192">**Cesar de la Torre. Comparing ASP.NET Core IoC container service lifetimes with Autofac IoC container instance scopes**
[*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)</span></span>

## <a name="table-mapping"></a><span data-ttu-id="b9261-193">테이블 매핑</span><span class="sxs-lookup"><span data-stu-id="b9261-193">Table mapping</span></span>

<span data-ttu-id="b9261-194">테이블 매핑 테이블 데이터에서 쿼리를 식별 하 고 데이터베이스에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-194">Table mapping identifies the table data to be queried from and saved to the database.</span></span> <span data-ttu-id="b9261-195">이전에 관련 된 데이터베이스 스키마를 생성 하려면 도메인 엔터티 (예: 제품 또는 순서 도메인)를 사용할 수 있는 방법을 배웠습니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-195">Previously you saw how domain entities (for example, a product or order domain) can be used to generate a related database schema.</span></span> <span data-ttu-id="b9261-196">EF의 개념에 맞게 설계 강력한 *규칙*합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-196">EF is strongly designed around the concept of *conventions*.</span></span> <span data-ttu-id="b9261-197">"는 테이블의 이름을 것?" 같은 규칙 주소 질문</span><span class="sxs-lookup"><span data-stu-id="b9261-197">Conventions address questions like “What will the name of a table be?”</span></span> <span data-ttu-id="b9261-198">"속성에는 기본 키가?" 또는</span><span class="sxs-lookup"><span data-stu-id="b9261-198">or “What property is the primary key?”</span></span> <span data-ttu-id="b9261-199">규칙은 일반적으로 이름을 기반으로 기존-id 끝나는 속성으로 기본 키에 대 한 일반적인 예는</span><span class="sxs-lookup"><span data-stu-id="b9261-199">Conventions are typically based on conventional names—for example, it is typical for the primary key to be a property that ends with Id.</span></span>

<span data-ttu-id="b9261-200">규칙에 따라 각 엔터티에 설정 됩니다는 DbSet에서 동일한 이름 갖는 테이블에 매핑하기 위해&lt;TEntity&gt; 파생 컨텍스트에 엔터티를 노출 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-200">By convention, each entity will be set up to map to a table with the same name as the DbSet&lt;TEntity&gt; property that exposes the entity on the derived context.</span></span> <span data-ttu-id="b9261-201">경우 없는 DbSet&lt;TEntity&gt; 값이 제공 지정된 엔터티에 대 한 클래스 이름이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-201">If no DbSet&lt;TEntity&gt; value is provided for the given entity, the class name is used.</span></span>

### <a name="data-annotations-versus-fluent-api"></a><span data-ttu-id="b9261-202">데이터 주석 또는 Fluent API</span><span class="sxs-lookup"><span data-stu-id="b9261-202">Data Annotations versus Fluent API</span></span>

<span data-ttu-id="b9261-203">많은 추가 EF 핵심 규칙 있으며 대부분의 데이터 주석 또는 Fluent API를 OnModelCreating 메서드 내에 구현 중 하나를 사용 하 여 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-203">There are many additional EF Core conventions, and most of them can be changed by using either data annotations or Fluent API, implemented within the OnModelCreating method.</span></span>

<span data-ttu-id="b9261-204">데이터 주석은 DDD 관점에서 침입 가능성이 더 많음 방법 엔터티 모델 클래스 자체에 사용 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-204">Data annotations must be used on the entity model classes themselves, which is a more intrusive way from a DDD point of view.</span></span> <span data-ttu-id="b9261-205">모델을 보호 하는 데이터베이스와 관련 된 인프라 데이터 주석을 사용한 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-205">This is because you are contaminating your model with data annotations related to the infrastructure database.</span></span> <span data-ttu-id="b9261-206">반면에 Fluent API는 명확 하 고 지 속성 인프라에서 분리 된 엔터티 모델 하므로 대부분의 규칙 및 데이터 지 속성 인프라 계층 내에서 매핑을 변경 하는 편리한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-206">On the other hand, Fluent API is a convenient way to change most conventions and mappings within your data persistence infrastructure layer, so the entity model will be clean and decoupled from the persistence infrastructure.</span></span>

### <a name="fluent-api-and-the-onmodelcreating-method"></a><span data-ttu-id="b9261-207">Fluent API 및 OnModelCreating 메서드</span><span class="sxs-lookup"><span data-stu-id="b9261-207">Fluent API and the OnModelCreating method</span></span>

<span data-ttu-id="b9261-208">했 듯이, 규칙 및 매핑을 변경 하기 위해 사용할 수 있습니다 OnModelCreating 메서드 DbContext 클래스에서.</span><span class="sxs-lookup"><span data-stu-id="b9261-208">As mentioned, in order to change conventions and mappings, you can use the OnModelCreating method in the DbContext class.</span></span> <span data-ttu-id="b9261-209">다음 예제에서는 어떻게 수행 eShopOnContainers에 정렬 마이크로 서비스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-209">The following example shows how we do this in the ordering microservice in eShopOnContainers.</span></span>

```csharp
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
    //Other entities
    modelBuilder.Entity<OrderStatus>(ConfigureOrderStatus);
    //Other entities
}

void ConfigureOrder(EntityTypeBuilder<Order> orderConfiguration)
{
    orderConfiguration.ToTable("orders", DEFAULT_SCHEMA);
    orderConfiguration.HasKey(o => o.Id);
    orderConfiguration.Property(o => o.Id).ForSqlServerUseSequenceHiLo("orderseq", DEFAULT_SCHEMA);
    orderConfiguration.Property<DateTime>("OrderDate").IsRequired();
    orderConfiguration.Property<string>("Street").IsRequired();
    orderConfiguration.Property<string>("State").IsRequired();
    orderConfiguration.Property<string>("City").IsRequired();
    orderConfiguration.Property<string>("ZipCode").IsRequired();
    orderConfiguration.Property<string>("Country").IsRequired();
    orderConfiguration.Property<int>("BuyerId").IsRequired();
    orderConfiguration.Property<int>("OrderStatusId").IsRequired();
    orderConfiguration.Property<int>("PaymentMethodId").IsRequired();

    var navigation =
    orderConfiguration.Metadata.FindNavigation(nameof(Order.OrderItems));
    // DDD Patterns comment:
    // Set as Field (new since EF 1.1) to access
    // the OrderItem collection property as a field
    navigation.SetPropertyAccessMode(PropertyAccessMode.Field);

    orderConfiguration.HasOne(o => o.PaymentMethod)
        .WithMany()
        .HasForeignKey("PaymentMethodId")
        .OnDelete(DeleteBehavior.Restrict);
        orderConfiguration.HasOne(o => o.Buyer)
        .WithMany()
        .HasForeignKey("BuyerId");
        orderConfiguration.HasOne(o => o.OrderStatus)
        .WithMany()
        .HasForeignKey("OrderStatusId");
}
```

<span data-ttu-id="b9261-210">동일한 OnModelCreating 메서드 내에서 모든 Fluent API 매핑을 설정할 수 있습니다 하지만 예제에 나와 있는 것 처럼 여러 submethods 엔터티에 하나씩 있고 해당 코드를 분할 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-210">You could set all the Fluent API mappings within the same OnModelCreating method, but it is advisable to partition that code and have multiple submethods, one per entity, as shown in the example.</span></span> <span data-ttu-id="b9261-211">매우 큰 모델에 대 한도 수 별도 소스 파일 (정적 클래스) 서로 다른 엔터티 형식을 구성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-211">For particularly large models, it can even be advisable to have separate source files (static classes) for configuring different entity types.</span></span>

<span data-ttu-id="b9261-212">예제에서 코드는 명시적입니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-212">The code in the example is explicit.</span></span> <span data-ttu-id="b9261-213">그러나 EF 코어 규칙이 중 대부분을 자동으로 수행, 있으므로 실제 코드를 동일한 작업을 달성 하기 위해 작성 해야 하는 것이 훨씬 더 작은 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-213">However, EF Core conventions do most of this automatically, so the actual code you would need to write to achieve the same thing would be much smaller.</span></span>

### <a name="the-hilo-algorithm-in-ef-core"></a><span data-ttu-id="b9261-214">EF 코어에서 Hi/Lo 알고리즘</span><span class="sxs-lookup"><span data-stu-id="b9261-214">The Hi/Lo algorithm in EF Core</span></span>

<span data-ttu-id="b9261-215">앞의 예제에서 코드의 한 흥미로운 끝점이 사용 한다는 것입니다는 [Hi/Lo 알고리즘](https://vladmihalcea.com/2014/06/23/the-hilo-algorithm/) 키 생성 전략으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-215">An interesting aspect of code in the preceding example is that it uses the [Hi/Lo algorithm](https://vladmihalcea.com/2014/06/23/the-hilo-algorithm/) as the key generation strategy.</span></span>

<span data-ttu-id="b9261-216">Hi/Lo 알고리즘 고유 키가 필요한 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-216">The Hi/Lo algorithm is useful when you need unique keys.</span></span> <span data-ttu-id="b9261-217">요약, Hi-Lo 알고리즘 고유한 식별자를 할당 테이블 행 동안 하지에 따라 즉시 데이터베이스에 행을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-217">As a summary, the Hi-Lo algorithm assigns unique identifiers to table rows while not depending on storing the row in the database immediately.</span></span> <span data-ttu-id="b9261-218">이렇게 하면 일반 순차적 데이터베이스 Id와 함께 발생 하는 식별자를 사용 하 여 바로 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-218">This lets you start using the identifiers right away, as happens with regular sequential database IDs.</span></span>

<span data-ttu-id="b9261-219">Hi/Lo 알고리즘 데이터베이스가 아닌 클라이언트 쪽에서 안전 하 게 보호 Id를 생성 하기 위한 메커니즘을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-219">The Hi/Lo algorithm describes a mechanism for generating safe IDs on the client side rather than in the database.</span></span> <span data-ttu-id="b9261-220">*안전* 충돌 없이이 컨텍스트에서 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-220">*Safe* in this context means without collisions.</span></span> <span data-ttu-id="b9261-221">이 알고리즘은 이러한 이유로 흥미로운:</span><span class="sxs-lookup"><span data-stu-id="b9261-221">This algorithm is interesting for these reasons:</span></span>

-   <span data-ttu-id="b9261-222">작업 단위 패턴은 중단 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-222">It does not break the Unit of Work pattern.</span></span>

-   <span data-ttu-id="b9261-223">다른 Dbms에서 작업을 수행 왕복 방식으로 시퀀스 생성기는 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-223">It does not require round trips the way sequence generators do in other DBMSs.</span></span>

-   <span data-ttu-id="b9261-224">Guid를 사용 하는 기술은 달리 사람이 읽을 수 있는 식별자를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-224">It generates a human readable identifier, unlike techniques that use GUIDs.</span></span>

<span data-ttu-id="b9261-225">EF Core 지원 [HiLo](http://stackoverflow.com/questions/282099/whats-the-hi-lo-algorithm) 앞의 예제와 같이 ForSqlServerUseSequenceHiLo 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-225">EF Core supports [HiLo](http://stackoverflow.com/questions/282099/whats-the-hi-lo-algorithm) with the ForSqlServerUseSequenceHiLo method, as shown in the preceding example.</span></span>

### <a name="mapping-fields-instead-of-properties"></a><span data-ttu-id="b9261-226">속성 대신 필드 매핑</span><span class="sxs-lookup"><span data-stu-id="b9261-226">Mapping fields instead of properties</span></span>

<span data-ttu-id="b9261-227">기능을 사용 하면 필드에 열을 매핑하는 EF 코어 1.1의 엔터티 클래스에서 속성을 사용 하지 않도록을 필드에는 테이블에서 열을 매핑할 수 있으며 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-227">With the feature of EF Core 1.1 that maps columns to fields, it is possible to not use any properties in the entity class, and just to map columns from a table to fields.</span></span> <span data-ttu-id="b9261-228">일반적인 용도 대 한 엔터티 외부에서 액세스할 수는 필요 하지 않은 내부 상태에 대 한 전용 필드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-228">A common use for that would be private fields for any internal state that do not need to be accessed from outside the entity.</span></span>

<span data-ttu-id="b9261-229">EF 1.1 데이터베이스에서 열을 관련된 속성이 없는 필드를 매핑할 수 있는 방법을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-229">EF 1.1 supports a way to map a field without a related property to a column in the database.</span></span> <span data-ttu-id="b9261-230">이렇게 하려면 단일 필드와 함께 또는 목록 처럼 컬렉션을 사용한&lt; &gt; 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-230">You can do this with single fields or also with collections, like a List&lt;&gt; field.</span></span> <span data-ttu-id="b9261-231">이 지점 위에 언급 한 도메인 모델 클래스를 모델링 하는 것이 설명한 하지만 이전 코드에서 강조 표시 PropertyAccessMode.Field 구성을 사용 하 여 해당 매핑을 수행 방법 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-231">This point was mentioned earlier when we discussed modeling the domain model classes, but here you can see how that mapping is performed with the PropertyAccessMode.Field configuration highlighted in the previous code.</span></span>

### <a name="using-shadow-properties-in-value-objects-for-hidden-ids-at-the-infrastructure-level"></a><span data-ttu-id="b9261-232">값 개체의 그림자 속성을 사용 하 여 인프라 수준에서 숨겨진된 Id에 대 한</span><span class="sxs-lookup"><span data-stu-id="b9261-232">Using shadow properties in value objects for hidden IDs at the infrastructure level</span></span>

<span data-ttu-id="b9261-233">EF Core에서 섀도 속성은 엔터티 클래스 모델에 존재 하지 않는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-233">Shadow properties in EF Core are properties that do not exist in your entity class model.</span></span> <span data-ttu-id="b9261-234">값과 이러한 속성의 상태에 순수 하 게 유지 됩니다는 [ChangeTracker](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.changetracking.changetracker) 인프라 수준에서 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-234">The values and states of these properties are maintained purely in the [ChangeTracker](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.changetracking.changetracker) class at the infrastructure level.</span></span>

<span data-ttu-id="b9261-235">DDD 관점에서 섀도 속성 값 개체를 섀도 속성 기본 키로 ID 숨기는 방식으로 구현 하는 편리한 방법은입니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-235">From a DDD point of view, shadow properties are a convenient way to implement value objects by hiding the ID as a shadow property primary key.</span></span> <span data-ttu-id="b9261-236">값 개체 id가 없는 경우 해야 하기 때문에 이것은 중요, (적어도 없어야 ID 도메인 모델 계층에서 개체를 셰이핑 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="b9261-236">This is important, because a value object should not have identity (at least, you should not have the ID in the domain model layer when shaping value objects).</span></span> <span data-ttu-id="b9261-237">EF 코어의 현재 버전을 기준으로 EF 코어 하지 않았는지 값 개체를 구현 하는 방법을 [복합 형식을](https://msdn.microsoft.com/library/jj680147(v=vs.113).aspx), EF에서 최대한 6.x 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-237">The point here is that as of the current version of EF Core, EF Core does not have a way to implement value objects as [complex types](https://msdn.microsoft.com/library/jj680147(v=vs.113).aspx), as is possible in EF 6.x.</span></span> <span data-ttu-id="b9261-238">현재는 섀도 속성으로 설정 된 숨겨진된 ID (기본 키) 엔터티를 값 개체를 구현 해야 하는 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-238">That is why you currently need to implement a value object as an entity with a hidden ID (primary key) set as a shadow property.</span></span>

<span data-ttu-id="b9261-239">볼 수는 [주소 값 개체](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs) eShopOnContainers에서 주소 모델에 표시 되지 않으면 ID:</span><span class="sxs-lookup"><span data-stu-id="b9261-239">As you can see in the [Address value object](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs) in eShopOnContainers, in the Address model you do not see an ID:</span></span>

```csharp
public class Address : ValueObject
{
    public String Street { get; private set; }
    public String City { get; private set; }
    public String State { get; private set; }
    public String Country { get; private set; }
    public String ZipCode { get; private set; }
    //Constructor initializing, etc
}
```

<span data-ttu-id="b9261-240">그러나 내부적으로 EF 코어를 데이터베이스 테이블에이 데이터를 지속할 수 있도록 ID를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-240">But under the covers, we need to provide an ID so that EF Core is able to persist this data in the database tables.</span></span> <span data-ttu-id="b9261-241">ConfigureAddress 메서드에서 수행 하는 [OrderingContext.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Infrastructure/OrderingContext.cs) EF는 인프라 코드를 사용 하 여 도메인 모델 오염 되지 않는 우리 하므로 인프라 수준에서 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b9261-241">We do that in the ConfigureAddress method of the [OrderingContext.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Infrastructure/OrderingContext.cs) class at the infrastructure level, so we do not pollute the domain model with EF infrastructure code.</span></span>

```csharp
void ConfigureAddress(EntityTypeBuilder<Address> addressConfiguration)
{
    addressConfiguration.ToTable("address", DEFAULT_SCHEMA);
    // DDD pattern comment:
    // Implementing the Address ID as a shadow property, because the
    // address is a value object and an identity is not required for a
    // value object
    // EF Core just needs the ID so it can store it in a database table
    // See: https://docs.microsoft.com/ef/core/modeling/shadow-properties
    addressConfiguration.Property<int>("Id").IsRequired();
    addressConfiguration.HasKey("Id");
}
```

#### <a name="additional-resources"></a><span data-ttu-id="b9261-242">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="b9261-242">Additional resources</span></span>

-   <span data-ttu-id="b9261-243">**매핑 테이블**
    [*https://docs.microsoft.com/ef/core/modeling/relational/tables*](https://docs.microsoft.com/ef/core/modeling/relational/tables)</span><span class="sxs-lookup"><span data-stu-id="b9261-243">**Table Mapping**
[*https://docs.microsoft.com/ef/core/modeling/relational/tables*](https://docs.microsoft.com/ef/core/modeling/relational/tables)</span></span>

-   <span data-ttu-id="b9261-244">**HiLo를 사용 하 여 Entity Framework Core를 사용 하 여 키 생성**
    [*http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/*](http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/)</span><span class="sxs-lookup"><span data-stu-id="b9261-244">**Use HiLo to generate keys with Entity Framework Core**
[*http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/*](http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/)</span></span>

-   <span data-ttu-id="b9261-245">**필드 백업**
    [*https://docs.microsoft.com/ef/core/modeling/backing-field*](https://docs.microsoft.com/ef/core/modeling/backing-field)</span><span class="sxs-lookup"><span data-stu-id="b9261-245">**Backing Fields**
[*https://docs.microsoft.com/ef/core/modeling/backing-field*](https://docs.microsoft.com/ef/core/modeling/backing-field)</span></span>

-   <span data-ttu-id="b9261-246">**Steve Smith 합니다. Entity Framework Core에서 컬렉션을 캡슐화**
    [*http://ardalis.com/encapsulated-collections-in-entity-framework-core*](http://ardalis.com/encapsulated-collections-in-entity-framework-core)</span><span class="sxs-lookup"><span data-stu-id="b9261-246">**Steve Smith. Encapsulated Collections in Entity Framework Core**
[*http://ardalis.com/encapsulated-collections-in-entity-framework-core*](http://ardalis.com/encapsulated-collections-in-entity-framework-core)</span></span>

-   <span data-ttu-id="b9261-247">**그림자 속성이**
    [*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span><span class="sxs-lookup"><span data-stu-id="b9261-247">**Shadow Properties**
[*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="b9261-248">[이전] (인프라-지 속성-계층-design.md) [다음] (nosql-데이터베이스-지 속성-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="b9261-248">[Previous] (infrastructure-persistence-layer-design.md) [Next] (nosql-database-persistence-infrastructure.md)</span></span>
