---
title: ASP.NET Core 앱에서 데이터 작업
description: ASP.NET Core 및 Azure를 사용하여 현대식 웹 응용 프로그램 설계 | asp에서 데이터 작업
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 648e0a4cdd388cf4a322f0fc049d5dcfca53d54b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="working-with-data-in-aspnet-core-apps"></a><span data-ttu-id="2e914-103">ASP.NET Core 앱에서 데이터 작업</span><span class="sxs-lookup"><span data-stu-id="2e914-103">Working with Data in ASP.NET Core Apps</span></span>

> <span data-ttu-id="2e914-104">"데이터는 귀중한 자산이며 시스템 자체보다 더 오래 지속됩니다."</span><span class="sxs-lookup"><span data-stu-id="2e914-104">"Data is a precious thing and will last longer than the systems themselves."</span></span>

<span data-ttu-id="2e914-105">Tim Berners-Lee</span><span class="sxs-lookup"><span data-stu-id="2e914-105">Tim Berners-Lee</span></span>

## <a name="summary"></a><span data-ttu-id="2e914-106">요약</span><span class="sxs-lookup"><span data-stu-id="2e914-106">Summary</span></span>

<span data-ttu-id="2e914-107">데이터 액세스는 거의 모든 소프트웨어 응용 프로그램에서 중요한 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-107">Data access is an important part of almost any software application.</span></span> <span data-ttu-id="2e914-108">ASP.NET Core는 Entity Framework Core(및 Entity Framework 6)를 포함한 다양한 데이터 액세스 옵션을 지원하며, 모든 .NET 데이터 액세스 프레임워크와 함께 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-108">ASP.NET Core supports a variety of data access options, including Entity Framework Core (and Entity Framework 6 as well), and can work with any .NET data access framework.</span></span> <span data-ttu-id="2e914-109">어떤 데이터 액세스 프레임워크를 선택할 것인지는 응용 프로그램 요구 사항에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-109">The choice of which data access framework to use depends on the application's needs.</span></span> <span data-ttu-id="2e914-110">ApplicationCore 및 UI 프로젝트에서 이러한 옵션을 추상화하고, 인프라에서 구현 세부 사항을 캡슐화하면 느슨하게 결합된 테스트 가능 소프트웨어를 만드는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-110">Abstracting these choices from the ApplicationCore and UI projects, and encapsulating implementation details in Infrastructure, helps to produce loosely coupled, testable software.</span></span>

## <a name="entity-framework-core-for-relational-databases"></a><span data-ttu-id="2e914-111">Entity Framework Core(관계형 데이터베이스용)</span><span class="sxs-lookup"><span data-stu-id="2e914-111">Entity Framework Core (for relational databases)</span></span>

<span data-ttu-id="2e914-112">관계형 데이터와 함께 작동해야 하는 새 ASP.NET Core 응용 프로그램을 작성하는 경우 응용 프로그램이 Entity Framework Core(EF Core)를 통해 데이터에 액세스하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-112">If you're writing a new ASP.NET Core application that needs to work with relational data, then Entity Framework Core (EF Core) is the recommended way for your application to access its data.</span></span> <span data-ttu-id="2e914-113">EF Core는 .NET 개발자가 데이터 원본에서 개체를 유지할 수 있게 해주는 개체 관계형 매퍼(O/RM)입니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-113">EF Core is an object-relational mapper (O/RM) that enables .NET developers to persist objects to and from a data source.</span></span> <span data-ttu-id="2e914-114">EF Core를 사용하면 개발자들이 일반적으로 작성해야 하는 데이터 액세스 코드가 대부분 필요하지 않게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-114">It eliminates the need for most of the data access code developers would typically need to write.</span></span> <span data-ttu-id="2e914-115">ASP.NET Core와 마찬가지로, EF Core는 모듈식 플랫폼 간 응용 프로그램을 지원하도록 처음부터 다시 작성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-115">Like ASP.NET Core, EF Core has been rewritten from the ground up to support modular cross-platform applications.</span></span> <span data-ttu-id="2e914-116">응용 프로그램에 NuGet 패키지로 추가하고, 시작에서 구성하고, 필요할 때마다 종속성 주입을 통해 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-116">You add it to your application as a NuGet package, configure it in Startup, and request it through dependency injection wherever you need it.</span></span>

<span data-ttu-id="2e914-117">EF Core를 SQL Server 데이터베이스와 함께 사용하려면 다음 dotnet CLI 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-117">To use EF Core with a SQL Server database, run the following dotnet CLI command:</span></span>

<span data-ttu-id="2e914-118">dotnet add package Microsoft.EntityFrameworkCore.SqlServer</span><span class="sxs-lookup"><span data-stu-id="2e914-118">dotnet add package Microsoft.EntityFrameworkCore.SqlServer</span></span>

<span data-ttu-id="2e914-119">테스트를 목적으로 InMemory 데이터 원본에 대한 지원을 추가하려면:</span><span class="sxs-lookup"><span data-stu-id="2e914-119">To add support for an InMemory data source, for testing:</span></span>

<span data-ttu-id="2e914-120">dotnet add package Microsoft.EntityFrameworkCore.InMemory</span><span class="sxs-lookup"><span data-stu-id="2e914-120">dotnet add package Microsoft.EntityFrameworkCore.InMemory</span></span>

### <a name="the-dbcontext"></a><span data-ttu-id="2e914-121">DbContext</span><span class="sxs-lookup"><span data-stu-id="2e914-121">The DbContext</span></span>

<span data-ttu-id="2e914-122">EF Core를 사용하려면 DbContext 서브클래스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-122">To work with EF Core, you need a subclass of DbContext.</span></span> <span data-ttu-id="2e914-123">이 클래스는 응용 프로그램에서 작업할 엔터티 컬렉션을 나타내는 속성을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-123">This class holds properties representing collections of the entities your application will work with.</span></span> <span data-ttu-id="2e914-124">EShopOnWeb 샘플에는 항목, 브랜드 및 형식에 대한 컬렉션을 제공하는 CatalogContext가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-124">The eShopOnWeb sample includes a CatalogContext with collections for items, brands, and types:</span></span>

```csharp
public class CatalogContext : DbContext
{
    public CatalogContext(DbContextOptions<CatalogContext> options) : base(options)
    {

    }

    public DbSet<CatalogItem> CatalogItems { get; set; }

    public DbSet<CatalogBrand> CatalogBrands { get; set; }

    public DbSet<CatalogType> CatalogTypes { get; set; }
}
```

<span data-ttu-id="2e914-125">DbContext에는 DbContextOptions을 수락하고 이 인수를 기본 DbContext 생성자에게 전달하는 생성자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-125">Your DbContext must have a constructor that accepts DbContextOptions and pass this argument to the base DbContext constructor.</span></span> <span data-ttu-id="2e914-126">응용 프로그램에 DbContext가 하나만 있는 경우 DbContextOptions 인스턴스를 전달할 수 있지만, 둘 이상 있는 경우에는 제네릭 DbContextOptions<T> 형식을 사용하여 DbContext 형식을 제네릭 매개 변수로 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-126">Note that if you have only one DbContext in your application, you can pass an instance of DbContextOptions, but if you have more than one you must use the generic DbContextOptions<T> type, passing in your DbContext type as the generic parameter.</span></span>

### <a name="configuring-ef-core"></a><span data-ttu-id="2e914-127">EF Core 구성</span><span class="sxs-lookup"><span data-stu-id="2e914-127">Configuring EF Core</span></span>

<span data-ttu-id="2e914-128">ASP.NET Core 응용 프로그램에서는 일반적으로 ConfigureServices 메서드에서 EF Core를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-128">In your ASP.NET Core application, you'll typically configure EF Core in your ConfigureServices method.</span></span> <span data-ttu-id="2e914-129">EF Core는 여러 유용한 확장 메서드를 지원하는 DbContextOptionsBuilder를 사용하여 구성을 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-129">EF Core uses a DbContextOptionsBuilder, which supports several helpful extension methods to streamline its configuration.</span></span> <span data-ttu-id="2e914-130">구성에 연결 문자열이 정의된 SQL Server 데이터베이스를 사용하도록 CatalogContext를 구성하려면 다음 코드를 ConfigureServices에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-130">To configure CatalogContext to use a SQL Server database with a connection string defined in Configuration, you would add the following code to ConfigureServices:</span></span>

```csharp
services.AddDbContext<CatalogContext>(options => options.UseSqlServer (Configuration.GetConnectionString("DefaultConnection")));
```

<span data-ttu-id="2e914-131">메모리 내 데이터베이스를 사용하려면:</span><span class="sxs-lookup"><span data-stu-id="2e914-131">To use the in-memory database:</span></span>

```csharp
services.AddDbContext<CatalogContext>(options =>
    options.UseInMemoryDatabase());
```

<span data-ttu-id="2e914-132">EF Core를 설치하고, DbContext 자식 형식을 만들고, ConfigureServices에서 구성을 마쳤으면 EF 코어를 사용할 준비가 완료된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-132">Once you have installed EF Core, created a DbContext child type, and configured it in ConfigureServices, you are ready to use EF Core.</span></span> <span data-ttu-id="2e914-133">DbContext 형식의 인스턴스를 필요로 하는 모든 서비스에서 이 인스턴스를 요청할 수 있으며, 마치 컬렉션에 있는 것처럼 LINQ를 사용하여 지속형 엔터티 작업을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-133">You can request an instance of your DbContext type in any service that needs it, and start working with your persisted entities using LINQ as if they were simply in a collection.</span></span> <span data-ttu-id="2e914-134">EF Core는 LINQ 식을 SQL 쿼리로 변환하여 데이터를 저장하고 검색하는 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-134">EF Core does the work of translating your LINQ expressions into SQL queries to store and retrieve your data.</span></span>

<span data-ttu-id="2e914-135">그림 8-1처럼 로거를 구성하고 그 수준을 정보 이상으로 설정하면 EF Core가 실행하는 쿼리를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-135">You can see the queries EF Core is executing by configuring a logger and ensuring its level is set to at least Information, as shown in Figure 8-1.</span></span>

![](./media/image8-1.png)

<span data-ttu-id="2e914-136">그림 8-1 EF Core 쿼리를 콘솔에 로깅</span><span class="sxs-lookup"><span data-stu-id="2e914-136">Figure 8-1 Logging EF Core queries to the console</span></span>

### <a name="fetching-and-storing-data"></a><span data-ttu-id="2e914-137">데이터 가져오기 및 저장</span><span class="sxs-lookup"><span data-stu-id="2e914-137">Fetching and Storing Data</span></span>

<span data-ttu-id="2e914-138">EF Core에서 데이터를 검색하려면 적절한 속성에 액세스한 후 LINQ를 사용하여 결과를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-138">To retrieve data from EF Core, you access the appropriate property and use LINQ to filter the result.</span></span> <span data-ttu-id="2e914-139">LINQ를 사용하여 프로젝션을 수행하고, 그 결과를 한 형식에서 다른 형식으로 변환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-139">You can also use LINQ to perform projection, transforming the result from one type to another.</span></span> <span data-ttu-id="2e914-140">다음 예제는 이름순으로 정렬되고, [사용] 속성을 기준으로 필터링되고, SelectListItem 형식에 투영되는 CatalogBrands를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-140">The following example would retrieve CatalogBrands, ordered by name, filtered by their Enabled property, and projected onto a SelectListItem type:</span></span>

```csharp
var brandItems = await _context.CatalogBrands
    .Where(b => b.Enabled)
    .OrderBy(b => b.Name)
    .Select(b => new SelectListItem {
        Value = b.Id, Text = b.Name })
    .ToListAsync();
```

<span data-ttu-id="2e914-141">위의 예제에서 쿼리가 즉시 실행되도록 ToListAsync에 대한 호출을 추가하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-141">It's important in the above example to add the call to ToListAsync in order to execute the query immediately.</span></span> <span data-ttu-id="2e914-142">그렇지 않으면 명령문에서 IQueryable<SelectListItem>을 brandItems에 할당하므로 열거될 때까지 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-142">Otherwise, the statement will assign an IQueryable<SelectListItem> to brandItems, which will not be executed until it is enumerated.</span></span> <span data-ttu-id="2e914-143">메서드에서 IQueryable 결과를 반환할 때의 장점과 단점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-143">There are pros and cons to returning IQueryable results from methods.</span></span> <span data-ttu-id="2e914-144">쿼리 EF Core가 추가 수정이 가능하도록 작성되지만, EF Core에서 변환할 수 없는 쿼리에 작업이 추가되면 런타임에만 발생하는 오류가 발생할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-144">It allows the query EF Core will construct to be further modified, but can also result in errors that only occur at runtime, if operations are added to the query that EF Core cannot translate.</span></span> <span data-ttu-id="2e914-145">일반적으로 데이터 액세스를 수행하는 메서드에 필터를 전달하고 메모리 내 컬렉션(예: List<T>)을 반환하는 것이 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-145">It's generally safer to pass any filters into the method performing the data access, and return back an in-memory collection (for example, List<T>) as the result.</span></span>

<span data-ttu-id="2e914-146">EF Core는 지속성 저장소에서 가져오는 엔터티의 변경 내용을 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-146">EF Core tracks changes on entities it fetches from persistence.</span></span> <span data-ttu-id="2e914-147">추적된 엔터티의 변경 내용을 저장하려면 엔터티를 가져올 때 사용한 것과 동일한 DbContext 인스턴스가 되도록 DbContext에서 SaveChanges 메서드를 호출하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-147">To save changes to a tracked entity, you just call the SaveChanges method on the DbContext, making sure it's the same DbContext instance that was used to fetch the entity.</span></span> <span data-ttu-id="2e914-148">엔터티 추가 및 삭제는 적절한 DbSet 속성에서 직접 수행되며, 마찬가지로 SaveChanges를 호출하여 데이터베이스 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-148">Adding and removing entities is directly on the appropriate DbSet property, again with a call to SaveChanges to execute the database commands.</span></span> <span data-ttu-id="2e914-149">다음 예제에서는 지속성 저장소에서 엔터티를 추가, 업데이트 및 제거하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-149">The following example demonstrates adding, updating, and removing entities from persistence.</span></span>

```csharp
// create
var newBrand = new CatalogBrand() { Brand = "Acme" };
_context.Add(newBrand);
await _context.SaveChangesAsync();

// read and update
var existingBrand = _context.CatalogBrands.Find(1);
existingBrand.Brand = "Updated Brand";
await _context.SaveChangesAsync();

// read and delete (alternate Find syntax)
var brandToDelete = _context.Find<CatalogBrand>(2);
_context.CatalogBrands.Remove(brandToDelete);
await _context.SaveChangesAsync();
```

<span data-ttu-id="2e914-150">EF Core는 엔터티를 가져오고 저장하기 위한 동기 및 비동기 메서드를 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-150">EF Core supports both synchronous and async methods for fetching and saving.</span></span> <span data-ttu-id="2e914-151">웹 응용 프로그램에서는 데이터 액세스 작업이 끝나기를 기다리는 동안 웹 서버 스레드가 차단되지 않도록 비동기 메서드에 async/await 패턴을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-151">In web applications, it's recommended to use the async/await pattern with the async methods, so that web server threads are not blocked while waiting for data access operations to complete.</span></span>

### <a name="fetching-related-data"></a><span data-ttu-id="2e914-152">관련 데이터 가져오기</span><span class="sxs-lookup"><span data-stu-id="2e914-152">Fetching Related Data</span></span>

<span data-ttu-id="2e914-153">EF Core는 엔터티를 검색할 때 엔터티와 함께 데이터베이스에 직접 저장되는 모든 속성을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-153">When EF Core retrieves entities, it populates all of the properties that are stored directly with that entity in the database.</span></span> <span data-ttu-id="2e914-154">관련 엔터티 목록 같은 탐색 속성은 채워지지 않으며 값이 Null로 설정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-154">Navigation properties, such as lists of related entities, are not populated and may have their value set to null.</span></span> <span data-ttu-id="2e914-155">이렇게 되면 EF Core가 데이터를 필요 이상으로 가져오지 않으며, 이는 요청을 신속하게 처리하고 효율적인 방식으로 응답을 반환해야 하는 웹 응용 프로그램에서 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-155">This ensures EF Core is not fetching more data than is needed, which is especially important for web applications, which must quickly process requests and return responses in an efficient manner.</span></span> <span data-ttu-id="2e914-156">*즉시 로드*를 사용하여 엔터티와의 관계를 포함하려면 다음과 같이 쿼리에서 Include 확장 메서드를 사용하여 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-156">To include relationships with an entity using *eager loading*, you specify the property using the Include extension method on the query, as shown:</span></span>

```csharp
// .Include requires using Microsoft.EntityFrameworkCore
var brandsWithItems = await _context.CatalogBrands
    .Include(b => b.Items)
    .ToListAsync();
```

<span data-ttu-id="2e914-157">여러 관계를 포함할 수 있으며, ThenInclude를 사용하여 하위 관계를 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-157">You can include multiple relationships, and you can also include sub-relationships using ThenInclude.</span></span> <span data-ttu-id="2e914-158">EF Core는 엔터티의 결과 집합을 검색하는 단일 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-158">EF Core will execute a single query to retrieve the resulting set of entities.</span></span>

<span data-ttu-id="2e914-159">관련 데이터를 로드하는 또 다른 옵션은 *명시적 로드*를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-159">Another option for loading related data is to use *explicit loading*.</span></span> <span data-ttu-id="2e914-160">명시적 로드를 사용하면 이미 검색된 엔터티에 추가 데이터를 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-160">Explicit loading allows you to load additional data into an entity that has already been retrieved.</span></span> <span data-ttu-id="2e914-161">이 방법은 데이터베이스에 대한 별도의 요청이 개입되므로 요청당 데이터베이스 왕복 횟수를 최소화해야 하는 웹 응용 프로그램에는 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-161">Since this involves a separate request to the database, it's not recommended for web applications, which should minimize the number of database round trips made per request.</span></span>

<span data-ttu-id="2e914-162">*지연 로드*는 응용 프로그램에서 참조하는 관련 데이터를 자동으로 로드하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-162">*Lazy loading* is a feature that automatically loads related data as it is referenced by the application.</span></span> <span data-ttu-id="2e914-163">현재 EF Core에서 지원되지 않지만, 명시적 로드와 마찬가지로 웹 응용 프로그램에서는 일반적으로 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-163">It's not currently supported by EF Core, but as with explicit loading it should typically be disabled for web applications.</span></span>

### <a name="resilient-connections"></a><span data-ttu-id="2e914-164">복원력 있는 연결</span><span class="sxs-lookup"><span data-stu-id="2e914-164">Resilient Connections</span></span>

<span data-ttu-id="2e914-165">SQL 데이터베이스 같은 외부 리소스를 사용할 수 없는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-165">External resources like SQL databases may occasionally be unavailable.</span></span> <span data-ttu-id="2e914-166">일시적으로 사용할 수 없는 경우 예외가 발생하지 않도록 하기 위해 응용 프로그램에서 재시도 논리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-166">In cases of temporary unavailability, applications can use retry logic to avoid raising an exception.</span></span> <span data-ttu-id="2e914-167">이 기술을 보통 *연결 복원력*이라고 부릅니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-167">This technique is commonly referred to as *connection resiliency*.</span></span> <span data-ttu-id="2e914-168">최대 다시 시도 횟수에 도달할 때까지 대기 시간이 기하급수적으로 증가하면서 다시 시도하는 [지수 백오프를 사용하여 다시 시도](https://docs.microsoft.com/azure/architecture/patterns/retry) 기술을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-168">You can implement your [own retry with exponential backoff](https://docs.microsoft.com/azure/architecture/patterns/retry) technique by attempting to rety with an exponentially increasing wait time, until a maximum retry count has been reached.</span></span> <span data-ttu-id="2e914-169">이 기술은 클라우드 리소스가 어떤 이유로든 짧은 시간 동안 일시적으로 사용할 수 없다는 팩트를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-169">This technique embraces the fact that cloud resources might intermittently be unavailable for short periods of time, resulting in failure of some requests.</span></span>

<span data-ttu-id="2e914-170">Azure SQL DB의 경우, Entity Framework Core는 이미 내부 데이터베이스 연결 복원력과 다시 시도 논리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-170">For Azure SQL DB, Entity Framework Core already provides internal database connection resiliency and retry logic.</span></span> <span data-ttu-id="2e914-171">그러나 복원력 있는 EF 코어 연결을 원할 경우 각 DbContext 연결에 대한 Entity Framework 실행 전략을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-171">But you need to enable the Entity Framework execution strategy for each DbContext connection if you want to have resilient EF Core connections.</span></span>

<span data-ttu-id="2e914-172">예를 들어, EF 코어 연결 수준의 다음 코드는 연결이 실패할 경우 다시 시도되는 복원력 있는 SQL 연결을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-172">For instance, the following code at the EF Core connection level enables resilient SQL connections that are retried if the connection fails.</span></span>

```csharp
// Startup.cs from any ASP.NET Core Web API
public class Startup
{
    public IServiceProvider ConfigureServices(IServiceCollection services)
    {
        //...
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
```

  #### <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a><span data-ttu-id="2e914-173">BeginTransaction 및 여러 DbContexts를 사용한 실행 전략 및 명시적 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="2e914-173">Execution strategies and explicit transactions using BeginTransaction and multiple DbContexts</span></span> 
  
  <span data-ttu-id="2e914-174">EF 코어 연결에서 다시 시도가 설정되면, EF 코어를 사용하여 수행하는 각 작업은 자체적으로 다시 시도할 수 있는 작업이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-174">When retries are enabled in EF Core connections, each operation you perform using EF Core becomes its own retriable operation.</span></span> <span data-ttu-id="2e914-175">일시적인 오류가 발생할 경우 SaveChanges에 대한 각 쿼리와 각 호출이 하나의 단위로 다시 시도됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-175">Each query and each call to SaveChanges will be retried as a unit if a transient failure occurs.</span></span>
  
  <span data-ttu-id="2e914-176">그러나 코드가 BeginTransaction을 사용하여 트랜잭션을 시작한 경우, 하나의 단위로 처리해야 하는 자신만의 작업 그룹을 정의하게 됩니다. 오류가 발생하면 트랜잭션 내부의 모든 항목이 롤백됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-176">However, if your code initiates a transaction using BeginTransaction, you are defining your own group of operations that need to be treated as a unit—everything inside the transaction has be rolled back if a failure occurs.</span></span> <span data-ttu-id="2e914-177">EF 실행 전략(다시 시도 정책)을 사용할 때 해당 트랜잭션을 실행하려고 시도하고 여러 DbContexts의 여러 SaveChanges를 포함하면 다음과 같은 예외가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-177">You will see an exception like the following if you attempt to execute that transaction when using an EF execution strategy (retry policy) and you include several SaveChanges from multiple DbContexts in it.</span></span>

<span data-ttu-id="2e914-178">System.InvalidOperationException: 구성된 실행 전략 'SqlServerRetryingExecutionStrategy’는 사용자가 시작한 트랜잭션을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-178">System.InvalidOperationException: The configured execution strategy 'SqlServerRetryingExecutionStrategy' does not support user initiated transactions.</span></span> <span data-ttu-id="2e914-179">'DbContext.Database.CreateExecutionStrategy()'에서 반환된 실행 전략을 사용하여 트랜잭션을 다시 시도가 가능한 단위로 트랜잭션의 모든 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-179">Use the execution strategy returned by 'DbContext.Database.CreateExecutionStrategy()' to execute all the operations in the transaction as a retriable unit.</span></span>

<span data-ttu-id="2e914-180">해결책은 실행해야 하는 모든 것을 나타내는 대리자를 사용하여 EF 실행 전략을 수동으로 호출하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-180">The solution is to manually invoke the EF execution strategy with a delegate representing everything that needs to be executed.</span></span> <span data-ttu-id="2e914-181">일시적인 오류가 발생하면, 실행 전략에서 대리자를 다시 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-181">If a transient failure occurs, the execution strategy will invoke the delegate again.</span></span> <span data-ttu-id="2e914-182">다음 코드는 이 방식을 구현하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-182">The following code shows how to implement this approach:</span></span>

```csharp
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
```

<span data-ttu-id="2e914-183">첫 번째 DbContext는 \_catalogContext이고 두 번째 DbContext는 \_integrationEventLogService 개체 내에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-183">The first DbContext is the \_catalogContext and the second DbContext is within the \_integrationEventLogService object.</span></span> <span data-ttu-id="2e914-184">마지막으로, 커밋 작업은 EF 실행 전략을 사용하여 여러 DbContexts를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-184">Finally, the Commit action would be performed multiple DbContexts and using an EF Execution Strategy.</span></span>

> ### <a name="references--entity-framework-core"></a><span data-ttu-id="2e914-185">참조 - Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="2e914-185">References – Entity Framework Core</span></span>
> - <span data-ttu-id="2e914-186">**EF Core Docs**</span><span class="sxs-lookup"><span data-stu-id="2e914-186">**EF Core Docs**</span></span>  
> <span data-ttu-id="2e914-187"><https://docs.microsoft.com/ef/></span><span class="sxs-lookup"><span data-stu-id="2e914-187"><https://docs.microsoft.com/ef/></span></span>
> - <span data-ttu-id="2e914-188">**EF Core: 관련 데이터**</span><span class="sxs-lookup"><span data-stu-id="2e914-188">**EF Core: Related Data**</span></span>  
> <span data-ttu-id="2e914-189"><https://docs.microsoft.com/ef/core/querying/related-data></span><span class="sxs-lookup"><span data-stu-id="2e914-189"><https://docs.microsoft.com/ef/core/querying/related-data></span></span>
> - <span data-ttu-id="2e914-190">**ASPNET 응용 프로그램에서 엔터티 지연 로드 방지**</span><span class="sxs-lookup"><span data-stu-id="2e914-190">**Avoid Lazy Loading Entities in ASPNET Applications**</span></span>  
> <span data-ttu-id="2e914-191"><http://ardalis.com/avoid-lazy-loading-entities-in-asp-net-applications></span><span class="sxs-lookup"><span data-stu-id="2e914-191"><http://ardalis.com/avoid-lazy-loading-entities-in-asp-net-applications></span></span>

## <a name="ef-core-or-micro-orm"></a><span data-ttu-id="2e914-192">EF Core 또는 마이크로 ORM</span><span class="sxs-lookup"><span data-stu-id="2e914-192">EF Core or micro-ORM?</span></span>

<span data-ttu-id="2e914-193">EF Core는 지속성 관리에 매우 유용하고 대부분 응용 프로그램 개발자의 데이터베이스 세부 정보를 캡슐화하지만, 유일한 방법은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-193">While EF Core is a great choice for managing persistence, and for the most part encapsulates database details from application developers, it is not the only choice.</span></span> <span data-ttu-id="2e914-194">또 다른 인기 있는 오픈 소스는 마이크로 ORM이라고도 불리는 [Dapper](https://github.com/StackExchange/Dapper)입니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-194">Another popular open source alternative is [Dapper](https://github.com/StackExchange/Dapper), a so-called micro-ORM.</span></span> <span data-ttu-id="2e914-195">마이크로 ORM은 개체를 데이터 구조에 매핑하는 데 사용되며 기능이 약간 적은 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-195">A micro-ORM is a lightweight, less full-featured tool for mapping objects to data structures.</span></span> <span data-ttu-id="2e914-196">Dapper의 디자인 목표는 데이터를 검색하고 업데이트하는 데 사용되는 기본 쿼리를 완전히 캡슐화하는 것이 아니라 성능에 집중하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-196">In the case of Dapper, its design goals focus on performance, rather than fully encapsulating the underlying queries it uses to retrieve and update data.</span></span> <span data-ttu-id="2e914-197">Dapper는 개발자의 SQL을 추상화하지 않으므로 "금속에 가깝고" 개발자가 특정 데이터 액세스 작업에 사용할 정확한 쿼리를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-197">Because it doesn't abstract SQL from the developer, Dapper is "closer to the metal" and lets developers write the exact queries they want to use for a given data access operation.</span></span>

<span data-ttu-id="2e914-198">EF Core에는 Dapper과 구별되지만 성능 오버헤드를 제공하는 두 가지 중요한 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-198">EF Core has two significant features it provides which separate it from Dapper but also add to its performance overhead.</span></span> <span data-ttu-id="2e914-199">첫 번째는 LINQ 식에서 SQL로의 변환입니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-199">The first is translation from LINQ expressions into SQL.</span></span> <span data-ttu-id="2e914-200">이러한 변환은 캐시되지만, 그럼에도 불구하고 처음으로 수행할 때 오버헤드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-200">These translations are cached, but even so there is overhead in performing them the first time.</span></span> <span data-ttu-id="2e914-201">두 번째는 엔터티 변경 내용 추적(효율적인 update 문을 생성할 수 있도록)입니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-201">The second is change tracking on entities (so that efficient update statements can be generated).</span></span> <span data-ttu-id="2e914-202">AsNotTracking 확장을 사용하여 특정 쿼리에 대해 이 동작을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-202">This behavior can be turned off for specific queries by using the AsNotTracking extension.</span></span> <span data-ttu-id="2e914-203">또한 EF 코어는 일반적으로 매우 효율적이고 어떤 경우에도 성능의 관점에서 완벽하게 허용되는 SQL 쿼리를 생성하지만, 실행할 정확한 쿼리를 세부적으로 제어해야 하는 경우 EF Core를 사용하여 사용자 지정 SQL을 전달(또는 저장 프로시저를 실행)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-203">EF Core also generates SQL queries that usually are very efficient and in any case perfectly acceptable from a performance standpoint, but if you need fine control over the precise query to be executed, you can pass in custom SQL (or execute a stored procedure) using EF Core, too.</span></span> <span data-ttu-id="2e914-204">이 경우 Dapper는 여전히 EF Core보다 성능이 우수하지만, 그 차이는 미미합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-204">In this case, Dapper still outperforms EF Core, but only slightly.</span></span> <span data-ttu-id="2e914-205">Julie Lerman은 2016년 5월에 작성한 MSDN 문서 [Dapper, Entity Framework 및 하이브리드 앱](https://msdn.microsoft.com/magazine/mt703432.aspx)에서 몇 가지 성능 데이터를 제시했습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-205">Julie Lerman presents some performance data in her May 2016 MSDN article [Dapper, Entity Framework, and Hybrid Apps](https://msdn.microsoft.com/magazine/mt703432.aspx).</span></span> <span data-ttu-id="2e914-206">다양한 데이터 액세스 방법에 대한 추가 성능 벤치마크 데이터는 [Dapper 사이트](https://github.com/StackExchange/Dapper)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-206">Additional performance benchmark data for a variety of data access methods can be found on [the Dapper site](https://github.com/StackExchange/Dapper).</span></span>

<span data-ttu-id="2e914-207">Dapper 구문이 EF Core에서 어떻게 달라지는지 살펴보려면 항목의 목록 검색에 사용되는 다음 두 동일한 메서드 버전을 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="2e914-207">To see how the syntax for Dapper varies from EF Core, consider these two versions of the same method for retrieving a list of items:</span></span>

```csharp
// EF Core
private readonly CatalogContext _context;
public async Task<IEnumerable<CatalogType>> GetCatalogTypes()
{
    return await _context.CatalogTypes.ToListAsync();
}

// Dapper
private readonly SqlConnection _conn;
public async Task<IEnumerable<CatalogType>> GetCatalogTypesWithDapper()
{
    return await _conn.QueryAsync<CatalogType>("SELECT * FROM CatalogType");
}
```

<span data-ttu-id="2e914-208">Dapper를 사용하여 좀 더 복잡한 개체 그래프를 작성해야 하는 경우 관련 쿼리를 직접 작성해야 합니다(EF Core에서 Include를 추가하는 것과는 달리).</span><span class="sxs-lookup"><span data-stu-id="2e914-208">If you need to build more complex object graphs with Dapper, you need to write the associated queries yourself (as opposed to adding an Include as you would in EF Core).</span></span> <span data-ttu-id="2e914-209">이것은 개발 행을 여러 매핑된 개체에 매핑할 수 있는 다중 매핑이라는 기능을 포함하여 다양한 구문을 통해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-209">This is supported through a variety of syntaxes, including a feature called Multi Mapping that lets you map individual rows to multiple mapped objects.</span></span> <span data-ttu-id="2e914-210">예를 들어 속성은 Owner, 형식은 User인 Post라는 클래스가 있다고 할 때, 다음 SQL은 모든 필요한 데이터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-210">For example, given a class Post with a property Owner of type User, the following SQL would return all of the necessary data:</span></span>

```sql
select * from #Posts p
left join \#Users u on u.Id = p.OwnerId
Order by p.Id
```

<span data-ttu-id="2e914-211">반환된 각 행에는 User 및 Post 데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-211">Each returned row includes both User and Post data.</span></span> <span data-ttu-id="2e914-212">User 데이터는 Owner 속성을 통해 Post 데이터에 연결되어야 하므로 다음 함수가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-212">Since the User data should be attached to the Post data via its Owner property, the following function is used:</span></span>

```csharp
(post, user) => { post.Owner = user; return post; }
```

<span data-ttu-id="2e914-213">연결된 사용자 데이터로 Owner 속성이 채워진 게시물 컬렉션을 반환하는 전체 코드 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-213">The full code listing to return a collection of posts with their Owner property populated with the associated user data would be:</span></span>

```csharp
var sql = @"select * from #Posts p
left join #Users u on u.Id = p.OwnerId
Order by p.Id";
var data = connection.Query<Post, User, Post>(sql,
(post, user) => { post.Owner = user; return post;});
```

<span data-ttu-id="2e914-214">Dapper는 캡슐화가 덜 이루어지므로 개발자는 데이터가 저장되는 방식, 데이터를 효과적으로 쿼리하는 방법, 데이터를 가져오는 더 많은 코드를 작성하는 방법을 잘 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-214">Because it offers less encapsulation, Dapper requires developers know more about how their data is stored, how to query it efficiently, and write more code to fetch it.</span></span> <span data-ttu-id="2e914-215">모델이 바뀌면 단순히 새 마이그레이션을 만들고(EF Core의 또 다른 기능) DbContext의 한 장소에 매핑 정보를 업데이트하는 대신, 영향을 받는 모든 쿼리를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-215">When the model changes, instead of simply creating a new migration (another EF Core feature), and/or updating mapping information in one place in a DbContext, every query that is impacted must be updated.</span></span> <span data-ttu-id="2e914-216">이러한 쿼리는 컴파일 시간을 보장하지 않으므로 모델 또는 데이터베이스 변경에 대한 응답으로 런타임에 중단될 수 있으며, 오류를 신속하게 감지하기가 더 어려워질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-216">These queries have not compile time guarantees, so they may break at runtime in response to changes to the model or database, making errors more difficult to detect quickly.</span></span> <span data-ttu-id="2e914-217">이러한 단점을 대가로, Dapper는 매우 빠른 성능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-217">In exchange for these tradeoffs, Dapper offers extremely fast performance.</span></span>

<span data-ttu-id="2e914-218">EF Core는 대부분의 응용 프로그램에서, 그리고 응용 프로그램의 대부분에서 납득할 만한 성능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-218">For most applications, and most parts of almost all applications, EF Core offers acceptable performance.</span></span> <span data-ttu-id="2e914-219">따라서 개발자 생산성 이점이 성능 오버헤드보다 클 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-219">Thus, its developer productivity benefits are likely to outweigh its performance overhead.</span></span> <span data-ttu-id="2e914-220">캐싱으로 이점을 얻을 수 있는 쿼리의 경우 실제 쿼리가 실행되는 시간은 극히 일부에 불과할 수 있으며, 무시해도 될 정도로 쿼리 성능 차이가 비교적 작을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-220">For queries that can benefit from caching, the actual query may only be executed a tiny percentage of the time, making relatively small query performance differences moot.</span></span>

## <a name="sql-or-nosql"></a><span data-ttu-id="2e914-221">SQL 또는 NoSQL</span><span class="sxs-lookup"><span data-stu-id="2e914-221">SQL or NoSQL</span></span>

<span data-ttu-id="2e914-222">전통적으로 SQL Server 같은 관계형 데이터베이스가 영구 데이터 저장소 시장을 지배해 왔지만, 유일한 솔루션은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-222">Traditionally, relational databases like SQL Server have dominated the marketplace for persistent data storage, but they are not the only solution available.</span></span> <span data-ttu-id="2e914-223">[MongoDB](https://www.mongodb.com/what-is-mongodb) 같은 NoSQL 데이터베이스는 개체를 저장하는 다른 접근 방식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-223">NoSQL databases like [MongoDB](https://www.mongodb.com/what-is-mongodb) offer a different approach to storing objects.</span></span> <span data-ttu-id="2e914-224">개체를 테이블 및 행에 매핑하는 대신, 전체 개체 그래프를 직렬화하고 결과를 저장하는 또 다른 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-224">Rather than mapping objects to tables and rows, another option is to serialize the entire object graph, and store the result.</span></span> <span data-ttu-id="2e914-225">이 방법의 이점은 적어도 처음에는 간단하고 성능이 우수하다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-225">The benefits of this approach, at least initially, are simplicity and performance.</span></span> <span data-ttu-id="2e914-226">개체를 관계가 있는 여러 테이블로 분해하고 데이터베이스에서 개체가 마지막으로 검색된 이후에 변경되었을 수 있는 행을 업데이트하는 방법보다는 키를 사용하여 직렬화된 단일 개체를 저장하는 방법이 더 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-226">It's certainly simpler to store a single serialized object with a key than to decompose the object into many tables with relationships and update and rows that may have changed since the object was last retrieved from the database.</span></span> <span data-ttu-id="2e914-227">마찬가지로, 관계형 데이터베이스에서 동일한 개체를 완전히 작성하는 데 필요한 복잡한 조인 또는 여러 데이터베이스 쿼리보다는 키 기반 저장소에서 단일 개체를 가져와서 역직렬화하는 방법이 훨씬 쉽고 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-227">Likewise, fetching and deserializing a single object from a key-based store is typically much faster and easier than complex joins or multiple database queries required to fully compose the same object from a relational database.</span></span> <span data-ttu-id="2e914-228">또한 잠금이나 트랜잭션 또는 고정된 스키마가 없으면 여러 컴퓨터에서 NoSQL 데이터베이스를 확장할 수 있으므로 대규모 데이터 집합을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-228">The lack of locks or transactions or a fixed schema also makes NoSQL databases very amenable to scaling across many machines, supporting very large datasets.</span></span>

<span data-ttu-id="2e914-229">반면, NoSQL 데이터베이스는(일반적으로 그 이름처럼) 고유한 단점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-229">On the other hand, NoSQL databases (as they are typically called) have their drawbacks.</span></span> <span data-ttu-id="2e914-230">관계형 데이터베이스는 정규화를 사용하여 일관성을 유지하고 데이터 중복을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-230">Relational databases use normalization to enforce consistency and avoid duplication of data.</span></span> <span data-ttu-id="2e914-231">이렇게 하면 데이터베이스의 전체 크기가 감소하며 즉시 전체 데이터베이스에서 공유 데이터 업데이트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-231">This reduces the total size of the database and ensures that updates to shared data are available immediately throughout the database.</span></span> <span data-ttu-id="2e914-232">관계형 데이터베이스에서 주소 테이블은 ID로 국가 테이블을 참조할 수 있으며, 따라서 한 국가의 이름이 변경되면 주소 레코드 자체를 업데이트할 필요 없이 업데이트의 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-232">In a relational database, an Address table might reference a Country table by ID, such that if a country's name were changed, the address records would benefit from the update without themselves having to be updated.</span></span> <span data-ttu-id="2e914-233">그러나 NoSQL 데이터베이스에는 주소 및 주소와 연결된 국가는 여러 저장된 개체의 일부로 직렬화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-233">However, in a NoSQL database, Address and its associated Country might be serialized as part of many stored objects.</span></span> <span data-ttu-id="2e914-234">국가 이름을 업데이트하려면 단일 행이 아닌 모든 개체를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-234">An update to a country name would require all such objects to be updated, rather than a single row.</span></span> <span data-ttu-id="2e914-235">관계형 데이터베이스는 외래 키 같은 규칙을 적용하여 관계 무결성을 보장할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-235">Relational databases can also ensure relational integrity by enforcing rules like foreign keys.</span></span> <span data-ttu-id="2e914-236">일반적으로 NoSQL 데이터베이스는 데이터에 대한 이러한 제약 조건을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-236">NoSQL databases typically do not offer such constraints on their data.</span></span>

<span data-ttu-id="2e914-237">처리해야 하는 또 다른 복잡성 NoSQL 데이터베이스는 버전 관리입니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-237">Another complexity NoSQL databases must deal with is versioning.</span></span> <span data-ttu-id="2e914-238">개체의 속성이 변경되면 저장된 이전 버전에서 개체를 역직렬화할 수 없을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-238">When an object's properties change, it may not be able to be deserialized from past versions that were stored.</span></span> <span data-ttu-id="2e914-239">따라서 직렬화된(이전) 개체 버전을 갖고 있는 모든 기존 개체를 새 스키마에 맞게 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-239">Thus, all existing objects that have a serialized (previous) version of the object must be updated to conform to its new schema.</span></span> <span data-ttu-id="2e914-240">스키마 변경 시 가끔 업데이트 스크립트 또는 매핑 업데이트가 필요한 관계형 데이터베이스와 개념적 차이는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-240">This is not conceptually different from a relational database, where schema changes sometimes require update scripts or mapping updates.</span></span> <span data-ttu-id="2e914-241">그러나 NoSQL 방식에서는 데이터 중복 때문에 수정해야 하는 항목 수가 훨씬 많은 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-241">However, the number of entries that must be modified is often much greater in the NoSQL approach, because there is more duplication of data.</span></span>

<span data-ttu-id="2e914-242">NoSQL 데이터베이스에서는 개체의 여러 버전을 저장할 수 있으며, 무언가 고정된 스키마 관계형 데이터베이스는 일반적으로 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-242">It's possible in NoSQL databases to store multiple versions of objects, something fixed schema relational databases typically do not support.</span></span> <span data-ttu-id="2e914-243">그러나 이 경우 응용 프로그램 코드에서 개체의 이전 버전이 존재하여 복잡성이 추가되는지 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-243">However, in this case your application code will need to account for the existence of previous versions of objects, adding additional complexity.</span></span>

<span data-ttu-id="2e914-244">NoSQL 데이터베이스는 일반적으로 [ACID](http://en.wikipedia.org/wiki/ACID)를 적용하지 않습니다. 즉, 관계형 데이터베이스보다 성능과 확장성이 더 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-244">NoSQL databases typically do not enforce [ACID](http://en.wikipedia.org/wiki/ACID), which means they have both performance and scalability benefits over relational databases.</span></span> <span data-ttu-id="2e914-245">정규화된 테이블 구조의 저장소에 적합하지 않은 매우 거대한 데이터 집합 및 개체에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-245">They're well-suited to extremely large datasets and objects that are not well-suited to storage in normalized table structures.</span></span> <span data-ttu-id="2e914-246">각 데이터베이스를 적합하게 사용한다면 단일 응용 프로그램으로 관계형 데이터베이스와 NoSQL 데이터베이스의 장점을 모두 취하지 못할 이유가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-246">There is no reason why a single application cannot take advantage of both relational and NoSQL databases, using each where it is best suited.</span></span>

## <a name="azure-documentdb"></a><span data-ttu-id="2e914-247">Azure DocumentDB</span><span class="sxs-lookup"><span data-stu-id="2e914-247">Azure DocumentDB</span></span>

<span data-ttu-id="2e914-248">Azure DocumentDB는 완전히 관리되는 NoSQL 데이터베이스 서비스로 스키마 없는 클라우드 기반 데이터 저장소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-248">Azure DocumentDB is a fully managed NoSQL database service that offers cloud-based schema-free data storage.</span></span> <span data-ttu-id="2e914-249">DocumentDB는 신속하고 예측 가능한 성능, 고가용성, 탄력적인 크기 조정, 글로벌 배포를 위해 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-249">DocumentDB is built for fast and predictable performance, high availability, elastic scaling, and global distribution.</span></span> <span data-ttu-id="2e914-250">NoSQL 데이터베이스임에도 불구하고, 개발자가 풍부하고 친숙한 SQL 쿼리 기능을 JSON 데이터에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-250">Despite being a NoSQL database, developers can use rich and familiar SQL query capabilities on JSON data.</span></span> <span data-ttu-id="2e914-251">DocumentDB의 모든 리소스는 JSON 문서로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-251">All resources in DocumentDB are stored as JSON documents.</span></span> <span data-ttu-id="2e914-252">리소스는 메타데이터를 포함하고 있는 *항목* 및 항목 컬렉션인 *피드*로 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-252">Resources are managed as *items*, which are documents containing metadata, and *feeds*, which are collections of items.</span></span> <span data-ttu-id="2e914-253">그림 8-2는 여러 DocumentDB 리소스 간의 관계를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-253">Figure 8-2 shows the relationship between different DocumentDB resources.</span></span>


![JSON NoSQL 데이터베이스인 DocumentDB의 리소스 간 계층 관계](./media/image8-2.png)

<span data-ttu-id="2e914-255">**그림 8-2.**</span><span class="sxs-lookup"><span data-stu-id="2e914-255">**Figure 8-2.**</span></span> <span data-ttu-id="2e914-256">DocumentDB 리소스 조직.</span><span class="sxs-lookup"><span data-stu-id="2e914-256">DocumentDB resource organization.</span></span>

<span data-ttu-id="2e914-257">DocumentDB 쿼리 언어는 JSON 문서를 쿼리하는 데 사용되는 단순하면서도 강력한 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-257">The DocumentDB query language is a simple yet powerful interface for querying JSON documents.</span></span> <span data-ttu-id="2e914-258">이 언어는 ANSI SQL 문법의 하위 집합을 지원하고 JavaScript 개체, 배열, 개체 생성 및 함수 호출을 긴밀하게 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-258">The language supports a subset of ANSI SQL grammar and adds deep integration of JavaScript object, arrays, object construction, and function invocation.</span></span>

<span data-ttu-id="2e914-259">**참조 – DocumentDB**</span><span class="sxs-lookup"><span data-stu-id="2e914-259">**References – DocumentDB**</span></span>

-   <span data-ttu-id="2e914-260">DocumentDB 소개\\</span><span class="sxs-lookup"><span data-stu-id="2e914-260">DocumentDB Introduction\\</span></span>
    <span data-ttu-id="2e914-261"><https://docs.microsoft.com/azure/documentdb/documentdb-introduction></span><span class="sxs-lookup"><span data-stu-id="2e914-261"><https://docs.microsoft.com/azure/documentdb/documentdb-introduction></span></span>

## <a name="other-persistence-options"></a><span data-ttu-id="2e914-262">다른 지속성 옵션</span><span class="sxs-lookup"><span data-stu-id="2e914-262">Other Persistence Options</span></span>

<span data-ttu-id="2e914-263">관계형 및 NoSQL 저장소 옵션 외에도, ASP.NET Core 응용 프로그램은 Azure Storage를 사용하여 다양한 데이터 형식 및 파일을 클라우드 기반의 확장 가능한 방식으로 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-263">In addition to relational and NoSQL storage options, ASP.NET Core applications can use Azure Storage to store a variety of data formats and files in a cloud-based, scalable fashion.</span></span> <span data-ttu-id="2e914-264">Azure Storage는 대규모로 확장할 수 있으므로 처음에는 적은 양의 데이터를 저장하는 것으로 시작하고, 이후에 응용 프로그램에 필요하면 수백 테라바이트를 저장하도록 강화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-264">Azure Storage is massively scalable, so you can start out storing small amounts of data and scale up to storing hundreds or terabytes if your application requires it.</span></span> <span data-ttu-id="2e914-265">Azure Storage는 다음과 같은 네 가지 데이터를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-265">Azure Storage supports four kinds of data:</span></span>

-   <span data-ttu-id="2e914-266">구조화되지 않은 텍스트 또는 이진 저장소를 위한 Blob Storage. 개체 저장소라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-266">Blob Storage for unstructured text or binary storage, also referred to as object storage.</span></span>

-   <span data-ttu-id="2e914-267">구조화된 데이터 집합을 위한 Table Storage. 행 키를 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-267">Table Storage for structured datasets, accessible via row keys.</span></span>

-   <span data-ttu-id="2e914-268">신뢰할 수 있는 큐 기반 메시지를 위한 Queue Storage.</span><span class="sxs-lookup"><span data-stu-id="2e914-268">Queue Storage for reliable queue-based messaging.</span></span>

-   <span data-ttu-id="2e914-269">Azure 가상 머신과 온-프레미스 응용 프로그램 간의 공유 파일 액세스를 위한 File Storage.</span><span class="sxs-lookup"><span data-stu-id="2e914-269">File Storage for shared file access between Azure virtual machines and on-premises applications.</span></span>

<span data-ttu-id="2e914-270">**참조 – Azure Storage**</span><span class="sxs-lookup"><span data-stu-id="2e914-270">**References – Azure Storage**</span></span>

-   <span data-ttu-id="2e914-271">Azure Storage 소개\\</span><span class="sxs-lookup"><span data-stu-id="2e914-271">Azure Storage Introduction\\</span></span>
    <span data-ttu-id="2e914-272"><https://docs.microsoft.com/azure/storage/storage-introduction></span><span class="sxs-lookup"><span data-stu-id="2e914-272"><https://docs.microsoft.com/azure/storage/storage-introduction></span></span>

## <a name="caching"></a><span data-ttu-id="2e914-273">캐싱</span><span class="sxs-lookup"><span data-stu-id="2e914-273">Caching</span></span>

<span data-ttu-id="2e914-274">웹 응용 프로그램에서 각 웹 요청을 최대한 짧은 시간 내에 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-274">In web applications, each web request should be completed in the shortest time possible.</span></span> <span data-ttu-id="2e914-275">이를 위한 한 가지 방법은 서버가 요청을 완료하기 위해 만들어야 하는 외부 호출의 수를 제한하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-275">One way to achieve this is to limit the number of external calls the server must make to complete the request.</span></span> <span data-ttu-id="2e914-276">캐싱에는 서버(또는 데이터 원본보다 쉽게 쿼리할 수 있는 또 다른 데이터 저장소)에 데이터 복사본을 저장하는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-276">Caching involves storing a copy of data on the server (or another data store that is more easily queried than the source of the data).</span></span> <span data-ttu-id="2e914-277">웹 응용 프로그램, 특히 SPA가 아닌 기존 웹 응용 프로그램은 모든 요청에서 전체 사용자 인터페이스를 빌드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-277">Web applications, and especially non-SPA traditional web applications, need to build the entire user interface with every request.</span></span> <span data-ttu-id="2e914-278">이때 한 사용자 요청에서 다음 사용자 요청으로 동일한 데이터베이스 쿼리를 반복해서 만들어야 하는 경우가 자주 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-278">This frequently involves making many of the same database queries repeatedly from one user request to the next.</span></span> <span data-ttu-id="2e914-279">대부분의 경우 이 데이터가 변경되는 일은 거의 없으므로 데이터베이스에서 이 데이터를 지속적으로 요청할 이유가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-279">In most cases, this data changes rarely, so there is little reason to constantly request it from the database.</span></span> <span data-ttu-id="2e914-280">ASP.NET Core는 전체 페이지를 캐싱하기 위한 응답 캐싱, 그리고 보다 세부적인 캐싱 동작을 지원하는 데이터 캐싱을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-280">ASP.NET Core supports response caching, for caching entire pages, and data caching, which supports more granular caching behavior.</span></span>

<span data-ttu-id="2e914-281">캐싱을 구현할 때 문제 격리를 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-281">When implementing caching, it's important to keep in mind separation of concerns.</span></span> <span data-ttu-id="2e914-282">데이터 액세스 논리 또는 사용자 인터페이스에 캐싱 논리를 구현하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="2e914-282">Avoid implementing caching logic in your data access logic, or in your user interface.</span></span> <span data-ttu-id="2e914-283">그 대신, 캐싱을 자체 클래스에서 캡슐화하고 구성을 사용하여 해당 동작을 관리하세요.</span><span class="sxs-lookup"><span data-stu-id="2e914-283">Instead, encapsulate caching in its own classes, and use configuration to manage its behavior.</span></span> <span data-ttu-id="2e914-284">이렇게 하면 개방/폐쇄 및 단일 책임 원칙을 준수하며, 응용 프로그램의 성장에 따라 응용 프로그램에서 캐싱을 사용하는 방법을 좀 더 간편하게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-284">This follows the Open/Closed and Single Responsibility principles, and will make it easier for you to manage how you use caching in your application as it grows.</span></span>

### <a name="aspnet-core-response-caching"></a><span data-ttu-id="2e914-285">ASP.NET Core 응답 캐싱</span><span class="sxs-lookup"><span data-stu-id="2e914-285">ASP.NET Core Response Caching</span></span>

<span data-ttu-id="2e914-286">ASP.NET Core는 두 가지 수준의 응답 캐시를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-286">ASP.NET Core supports two levels of response caching.</span></span> <span data-ttu-id="2e914-287">첫 번째 수준은 서버의 어떤 항목도 캐시하지 않지만, 클라이언트와 프록시 서버에 응답을 캐시하라고 지시하는 HTTP 헤더를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-287">The first level does not cache anything on the server, but adds HTTP headers that instruct clients and proxy servers to cache responses.</span></span> <span data-ttu-id="2e914-288">이 동작은 개별 컨트롤러 또는 작업에 ResponseCache 특성을 추가하여 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-288">This is implemented by adding the ResponseCache attribute to individual controllers or actions:</span></span>

```csharp
    [ResponseCache(Duration = 60)]
    public IActionResult Contact()
    { }
    
    ViewData["Message"] = "Your contact page.";
    return View();
}

The above example will result in the following header being added to the response, instructing clients to cache the result for up to 60 seconds.

Cache-Control: public,max-age=60

In order to add server-side in-memory caching to the application, you must reference the Microsoft.AspNetCore.ResponseCaching NuGet package, and then add the Response Caching middleware. This middleware is configured in both ConfigureServices and Configure in Startup:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddResponseCaching();
}

public void Configure(IApplicationBuilder app)
{
    app.UseResponseCaching();
}
```

<span data-ttu-id="2e914-289">응답 캐싱 미들웨어는 사용자 지정할 수 있는 조건 집합에 따라 자동으로 응답을 캐싱합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-289">The Response Caching Middleware will automatically cache responses based on a set of conditions, which you can customize.</span></span> <span data-ttu-id="2e914-290">기본적으로 GET 또는 HEAD 메서드를 통해 요청된 200(확인) 응답만 캐시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-290">By default, only 200 (OK) responses requested via GET or HEAD methods are cached.</span></span> <span data-ttu-id="2e914-291">또한 요청에는 캐시 컨트롤: 공용 헤더가 포함된 응답이 있어야 하고, 권한 부여 또는 Set-Cookie에 대한 헤더를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-291">In addition, requests must have a response with a Cache-Control: public header, and cannot include headers for Authorization or Set-Cookie.</span></span> <span data-ttu-id="2e914-292">[응답 캐싱 미들웨어에서 사용하는 캐싱 조건 전체 목록](https://docs.microsoft.com/aspnet/core/performance/caching/middleware#conditions-for-caching)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2e914-292">See a [complete list of the caching conditions used by the response caching middleware](https://docs.microsoft.com/aspnet/core/performance/caching/middleware#conditions-for-caching).</span></span>

### <a name="data-caching"></a><span data-ttu-id="2e914-293">데이터 캐싱</span><span class="sxs-lookup"><span data-stu-id="2e914-293">Data Caching</span></span>

<span data-ttu-id="2e914-294">전체 웹 응답 캐싱 대신(또는 외에도) 개별 데이터 쿼리의 결과를 캐싱할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-294">Rather than (or in addition to) caching full web responses, you can cache the results of individual data queries.</span></span> <span data-ttu-id="2e914-295">이 경우 웹 서버에서 메모리 내 캐싱을 사용하거나 [분산된 캐시](https://docs.microsoft.com/aspnet/core/performance/caching/distributed)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-295">For this, you can use in memory caching on the web server, or use [a distributed cache](https://docs.microsoft.com/aspnet/core/performance/caching/distributed).</span></span> <span data-ttu-id="2e914-296">이 섹션에서는 메모리 내 캐싱을 구현하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-296">This section will demonstrate how to implement in memory caching.</span></span>

<span data-ttu-id="2e914-297">ConfigureServices에서 메모리(또는 분산) 캐싱 지원 추가:</span><span class="sxs-lookup"><span data-stu-id="2e914-297">You add support for memory (or distributed) caching in ConfigureServices:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMemoryCache();
    services.AddMvc();
}
```

<span data-ttu-id="2e914-298">Microsoft.Extensions.Caching.Memory NuGet 패키지를 추가하는 것을 잊지 마세요.</span><span class="sxs-lookup"><span data-stu-id="2e914-298">Be sure to add the Microsoft.Extensions.Caching.Memory NuGet package as well.</span></span>

<span data-ttu-id="2e914-299">서비스를 추가한 후에는 캐시에 액세스해야 할 때마다 종속성 주입을 통해 IMemoryCache를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-299">Once you've added the service, you request IMemoryCache via dependency injection wherever you need to access the cache.</span></span> <span data-ttu-id="2e914-300">이 예제에서는 기본 CatalogService 구현에 대한 액세스를 제어하는(또는 CatalogService 구현에 동작을 추가) ICatalogService 대안 구현을 제공함으로써 CachedCatalogService에서 프록시(또는 Decorator) 디자인 패턴을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-300">In this example, the CachedCatalogService is using the Proxy (or Decorator) design pattern, by providing an alternative implementation of ICatalogService that controls access to (or adds behavior to) the underlying CatalogService implementation.</span></span>

```csharp
public class CachedCatalogService : ICatalogService
{
    private readonly IMemoryCache _cache;
    private readonly CatalogService _catalogService;
    private static readonly string _brandsKey = "brands";
    private static readonly string _typesKey = "types";
    private static readonly string _itemsKeyTemplate = "items-{0}-{1}-{2}-{3}";
    private static readonly TimeSpan _defaultCacheDuration = TimeSpan.FromSeconds(30);
    public CachedCatalogService(IMemoryCache cache,
    CatalogService catalogService)
    {
        _cache = cache;
        _catalogService = catalogService;
    }
    
    public async Task<IEnumerable<SelectListItem>> GetBrands()
    {
        return await _cache.GetOrCreateAsync(_brandsKey, async entry =>
        {
            entry.SlidingExpiration = _defaultCacheDuration;
            return await _catalogService.GetBrands();
        });
    }
    
    public async Task<Catalog> GetCatalogItems(int pageIndex, int itemsPage, int? brandID, int? typeId)
    {
        string cacheKey = String.Format(_itemsKeyTemplate, pageIndex, itemsPage, brandID, typeId);
        return await _cache.GetOrCreateAsync(cacheKey, async entry =>
        {
            entry.SlidingExpiration = _defaultCacheDuration;
            return await _catalogService.GetCatalogItems(pageIndex, itemsPage, brandID, typeId);
        });
    }
    
    public async Task<IEnumerable<SelectListItem>> GetTypes()
    {
        return await _cache.GetOrCreateAsync(_typesKey, async entry =>
        {
            entry.SlidingExpiration = _defaultCacheDuration;
            return await _catalogService.GetTypes();
        });
    }
}
```

<span data-ttu-id="2e914-301">서비스의 캐시된 버전을 사용하지만 서비스가 여전히 생성자에 필요한 CatalogService 인스턴스를 가져올 수 있도록 응용 프로그램을 구성하려면 ConfigureServices에 다음을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-301">To configure the application to use the cached version of the service, but still allow the service to get the instance of CatalogService it needs in its constructor, you would add the following in ConfigureServices:</span></span>

```csharp
services.AddMemoryCache();
services.AddScoped<ICatalogService, CachedCatalogService>();
services.AddScoped<CatalogService>();
```

<span data-ttu-id="2e914-302">이 상태에서 카탈로그 데이터를 가져오는 데이터베이스 호출은 요청마다 만들어지는 것이 아니라 분당 한 번만 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-302">With this in place, the database calls to fetch the catalog data will only be made once per minute, rather than on every request.</span></span> <span data-ttu-id="2e914-303">사이트의 트래픽에 따라, 이는 데이터베이스에 대해 만들어지는 쿼리 수, 그리고 현재 이 서비스에서 노출하는 세 쿼리에 의존하는 홈페이지의 평균 페이지 로드 시간에 매우 큰 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-303">Depending on the traffic to the site, this can have a very significant impact on the number of queries made to the database, and the average page load time for the home page that currently depends on all three of the queries exposed by this service.</span></span>

<span data-ttu-id="2e914-304">캐싱이 구현될 때 발생하는 문제는 *부실 데이터*, 다시 말해서 원본에서 변경되었지만 오래된 버전이 캐시에 남아 있는 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-304">An issue that arises when caching is implemented is *stale data* – that is, data that has changed at the source but an out of date version remains in the cache.</span></span> <span data-ttu-id="2e914-305">이 문제를 완화하는 간단한 방법은 캐시 기간을 짧게 하는 것입니다. 사용량이 많은 응용 프로그램의 경우 데이터가 캐시되는 길이를 연장해서 얻을 수 있는 이점이 제한적이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-305">A simple way to mitigate this issue is to use small cache durations, since for a busy application there is limited additional benefit to extending the length data is cached.</span></span> <span data-ttu-id="2e914-306">예를 들어 단일 데이터베이스 쿼리를 만들고 초당 10회 요청되는 페이지를 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="2e914-306">For example, consider a page that makes a single database query, and is requested 10 times per second.</span></span> <span data-ttu-id="2e914-307">이 페이지가 1분 동안 캐시되면 분당 데이터베이스 쿼리 수가 600에서 1로 99.8% 감소합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-307">If this page is cached for one minute, it will result in the number of database queries made per minute to drop from 600 to 1, a reduction of 99.8%.</span></span> <span data-ttu-id="2e914-308">그 대신 캐시 기간을 1시간으로 하면 전체 감소율이 99.997%가 되겠지만, 부실 데이터 가능성 및 잠재적 연령이 크게 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-308">If instead the cache duration were made one hour, the overall reduction would be 99.997%, but now the likelihood and potential age of stale data are both increased dramatically.</span></span>

<span data-ttu-id="2e914-309">또 다른 방법은 캐시에 포함된 데이터가 업데이트될 때 선제적으로 캐시 항목을 제거하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-309">Another approach is to proactively remove cache entries when the data they contain is updated.</span></span> <span data-ttu-id="2e914-310">키를 알고 있으면 개별 항목을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-310">Any individual entry can be removed if its key is known:</span></span>

```csharp
_cache.Remove(cacheKey);
```

<span data-ttu-id="2e914-311">응용 프로그램이 캐시하는 항목을 업데이트하기 위한 기능을 노출하는 경우 업데이트를 수행하는 코드에서 해당 캐시 항목을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-311">If your application exposes functionality for updating entries that it caches, you can remove the corresponding cache entries in your code that performs the updates.</span></span> <span data-ttu-id="2e914-312">경우에 따라 특정 데이터 집합에 종속된 여러 항목이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-312">Sometimes there may be many different entries that depend on a particular set of data.</span></span> <span data-ttu-id="2e914-313">이 경우 CancellationChangeToken을 사용하여 캐시 항목 간의 종속성을 만드는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-313">In that case, it can be useful to create dependencies between cache entries, by using a CancellationChangeToken.</span></span> <span data-ttu-id="2e914-314">CancellationChangeToken을 사용하면 토큰을 취소하여 여러 캐시 항목을 한꺼번에 만료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e914-314">With a CancellationChangeToken, you can expire multiple cache entries at once by cancelling the token.</span></span>

```csharp
// configure CancellationToken and add entry to cache
var cts = new CancellationTokenSource();
_cache.Set("cts", cts);
_cache.Set(cacheKey,
itemToCache,
new CancellationChangeToken(cts.Token));

// elsewhere, expire the cache by cancelling the token\
_cache.Get<CancellationTokenSource>("cts").Cancel();
```

>[!div class="step-by-step"]
<span data-ttu-id="2e914-315">[이전] (develop-asp-net-core-mvc-apps.md) [다음] (test-asp-net-core-mvc-apps.md)</span><span class="sxs-lookup"><span data-stu-id="2e914-315">[Previous] (develop-asp-net-core-mvc-apps.md) [Next] (test-asp-net-core-mvc-apps.md)</span></span>
