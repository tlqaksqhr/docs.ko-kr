---
title: "ASP.NET Core 응용 프로그램에서 데이터 작업"
description: "ASP.NET Core와 Azure의 최신 웹 응용 프로그램을 설계 | asp에서 데이터 사용"
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: bcb8f7bbfa83db9c86cd1278a89750b9f02061d9
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2017
---
# <a name="working-with-data-in-aspnet-core-apps"></a><span data-ttu-id="df7ad-103">ASP.NET Core 응용 프로그램에서 데이터 사용</span><span class="sxs-lookup"><span data-stu-id="df7ad-103">Working with Data in ASP.NET Core Apps</span></span>

> <span data-ttu-id="df7ad-104">"데이터는 귀중 한 항목 및 시스템 자체 보다 더 오래 지속 됩니다."</span><span class="sxs-lookup"><span data-stu-id="df7ad-104">"Data is a precious thing and will last longer than the systems themselves."</span></span>

<span data-ttu-id="df7ad-105">Tim Berners-lee</span><span class="sxs-lookup"><span data-stu-id="df7ad-105">Tim Berners-Lee</span></span>

## <a name="summary"></a><span data-ttu-id="df7ad-106">요약</span><span class="sxs-lookup"><span data-stu-id="df7ad-106">Summary</span></span>

<span data-ttu-id="df7ad-107">데이터 액세스는 거의 모든 소프트웨어 응용 프로그램의 중요 한 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-107">Data access is an important part of almost any software application.</span></span> <span data-ttu-id="df7ad-108">ASP.NET Core 다양 한 Entity Framework Core (및 Entity Framework 6)를 포함 하 여 데이터 액세스 옵션을 지원 하 고 모든.NET 데이터 액세스 프레임 워크와 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-108">ASP.NET Core supports a variety of data access options, including Entity Framework Core (and Entity Framework 6 as well), and can work with any .NET data access framework.</span></span> <span data-ttu-id="df7ad-109">응용 프로그램의 요구에 따라는 데이터 액세스 프레임 워크를 사용 하 여 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-109">The choice of which data access framework to use depends on the application's needs.</span></span> <span data-ttu-id="df7ad-110">ApplicationCore 및 UI 프로젝트에서이 옵션을 추상화 하 고, 인프라에서 구현 세부 사항을 캡슐화 느슨하게 결합 된 하 고 테스트 가능 소프트웨어를 생성 하기 위해 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-110">Abstracting these choices from the ApplicationCore and UI projects, and encapsulating implementation details in Infrastructure, helps to produce loosely coupled, testable software.</span></span>

## <a name="entity-framework-core-for-relational-databases"></a><span data-ttu-id="df7ad-111">Entity Framework 코어 (용 관계형 데이터베이스)</span><span class="sxs-lookup"><span data-stu-id="df7ad-111">Entity Framework Core (for relational databases)</span></span>

<span data-ttu-id="df7ad-112">관계형 데이터로 작업 하는 새 ASP.NET Core 응용 프로그램을 작성 하는 경우 Entity Framework Core (EF 코어)는 해당 데이터에 액세스 하는 응용 프로그램에 대 한 권장된 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-112">If you're writing a new ASP.NET Core application that needs to work with relational data, then Entity Framework Core (EF Core) is the recommended way for your application to access its data.</span></span> <span data-ttu-id="df7ad-113">EF 핵심 개체와 데이터 원본에서 유지 하도록.NET 개발자가 개체 관계형 매퍼 (O/RM)입니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-113">EF Core is an object-relational mapper (O/RM) that enables .NET developers to persist objects to and from a data source.</span></span> <span data-ttu-id="df7ad-114">대부분의 개발자를 작성 해야 일반적으로 데이터 액세스 코드에 대 한 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-114">It eliminates the need for most of the data access code developers would typically need to write.</span></span> <span data-ttu-id="df7ad-115">ASP.NET Core 처럼 EF 코어 지원 모듈식 플랫폼 간 응용 프로그램에 이르기까지 처음부터 다시 작성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-115">Like ASP.NET Core, EF Core has been rewritten from the ground up to support modular cross-platform applications.</span></span> <span data-ttu-id="df7ad-116">시작 시 구성을 해야 할 때마다 종속성 주입을 통해 요청 NuGet 패키지로 응용 프로그램에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-116">You add it to your application as a NuGet package, configure it in Startup, and request it through dependency injection wherever you need it.</span></span>

<span data-ttu-id="df7ad-117">SQL Server 데이터베이스와 EF 코어를 사용 하려면 다음 dotnet CLI 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-117">To use EF Core with a SQL Server database, run the following dotnet CLI command:</span></span>

<span data-ttu-id="df7ad-118">dotnet은 Microsoft.EntityFrameworkCore.SqlServer 패키지를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-118">dotnet add package Microsoft.EntityFrameworkCore.SqlServer</span></span>

<span data-ttu-id="df7ad-119">테스트 하는 InMemory 데이터 원본에 대 한 지원을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-119">To add support for an InMemory data source, for testing:</span></span>

<span data-ttu-id="df7ad-120">dotnet은 Microsoft.EntityFrameworkCore.InMemory 패키지를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-120">dotnet add package Microsoft.EntityFrameworkCore.InMemory</span></span>

### <a name="the-dbcontext"></a><span data-ttu-id="df7ad-121">DbContext</span><span class="sxs-lookup"><span data-stu-id="df7ad-121">The DbContext</span></span>

<span data-ttu-id="df7ad-122">EF 코어를 사용 하려면 DbContext의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-122">To work with EF Core, you need a subclass of DbContext.</span></span> <span data-ttu-id="df7ad-123">이 클래스는 응용 프로그램 호환 엔터티 컬렉션을 나타내는 속성을 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-123">This class holds properties representing collections of the entities your application will work with.</span></span> <span data-ttu-id="df7ad-124">EShopOnWeb 샘플 항목, 브랜드, 및 형식에 대 한 컬렉션을 사용한 CatalogContext을 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-124">The eShopOnWeb sample includes a CatalogContext with collections for items, brands, and types:</span></span>

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

<span data-ttu-id="df7ad-125">프로그램 DbContext DbContextOptions 허용 하는 생성자가 하 고 기본 DbContext 생성자에 게이 인수를 전달 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-125">Your DbContext must have a constructor that accepts DbContextOptions and pass this argument to the base DbContext constructor.</span></span> <span data-ttu-id="df7ad-126">경우에 하나의 DbContext 응용 프로그램에 있는, DbContextOptions의 인스턴스를 전달할 수 있지만 있는 경우 여러 개 사용 해야 제네릭 DbContextOptions<T> 형식, 제네릭 매개 변수로 DbContext 형식에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-126">Note that if you have only one DbContext in your application, you can pass an instance of DbContextOptions, but if you have more than one you must use the generic DbContextOptions<T> type, passing in your DbContext type as the generic parameter.</span></span>

### <a name="configuring-ef-core"></a><span data-ttu-id="df7ad-127">EF 핵심 구성</span><span class="sxs-lookup"><span data-stu-id="df7ad-127">Configuring EF Core</span></span>

<span data-ttu-id="df7ad-128">ASP.NET Core 응용 프로그램에서 일반적으로 ConfigureServices 메서드에서 EF 코어를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-128">In your ASP.NET Core application, you'll typically configure EF Core in your ConfigureServices method.</span></span> <span data-ttu-id="df7ad-129">EF 코어는 DbContextOptionsBuilder 수 있도록 지 원하는 구성을 간소화 하는 여러 유용한 확장 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-129">EF Core uses a DbContextOptionsBuilder, which supports several helpful extension methods to streamline its configuration.</span></span> <span data-ttu-id="df7ad-130">SQL Server 데이터베이스 구성에 정의 된 연결 문자열을 함께 사용 하는 CatalogContext를 구성 하려면 다음 코드에 추가한 ConfigureServices:</span><span class="sxs-lookup"><span data-stu-id="df7ad-130">To configure CatalogContext to use a SQL Server database with a connection string defined in Configuration, you would add the following code to ConfigureServices:</span></span>

```csharp
services.AddDbContext<CatalogContext>(options => options.UseSqlServer (Configuration.GetConnectionString("DefaultConnection")));
```

<span data-ttu-id="df7ad-131">사용 하려면 메모리 내 데이터베이스:</span><span class="sxs-lookup"><span data-stu-id="df7ad-131">To use the in-memory database:</span></span>

```csharp
services.AddDbContext<CatalogContext>(options =>
    options.UseInMemoryDatabase());
```

<span data-ttu-id="df7ad-132">DbContext 자식 형식을 만든 EF Core를 설치 하 고 ConfigureServices에 구성 된 후 EF 코어를 사용할 준비가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-132">Once you have installed EF Core, created a DbContext child type, and configured it in ConfigureServices, you are ready to use EF Core.</span></span> <span data-ttu-id="df7ad-133">필요로 하는 서비스에 DbContext 형식의 인스턴스를 요청 하 고 컬렉션 단순히에서 듯 LINQ를 사용 하 여 지속형된 엔터티 작업을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-133">You can request an instance of your DbContext type in any service that needs it, and start working with your persisted entities using LINQ as if they were simply in a collection.</span></span> <span data-ttu-id="df7ad-134">EF 코어 LINQ 식을 저장 하 고 데이터를 검색할 SQL 쿼리로 변환 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-134">EF Core does the work of translating your LINQ expressions into SQL queries to store and retrieve your data.</span></span>

<span data-ttu-id="df7ad-135">로 거를 구성 하 고 해당 수준이 이상으로 설정 되어 여 EF 코어 실행 되는 쿼리를 볼 수 정보, 그림 8-1에 나와 있는 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-135">You can see the queries EF Core is executing by configuring a logger and ensuring its level is set to at least Information, as shown in Figure 8-1.</span></span>

![](./media/image8-1.png)

<span data-ttu-id="df7ad-136">콘솔에 대 한 그림 8-1 EF 코어 로깅 쿼리</span><span class="sxs-lookup"><span data-stu-id="df7ad-136">Figure 8-1 Logging EF Core queries to the console</span></span>

### <a name="fetching-and-storing-data"></a><span data-ttu-id="df7ad-137">인출 및 데이터 저장</span><span class="sxs-lookup"><span data-stu-id="df7ad-137">Fetching and Storing Data</span></span>

<span data-ttu-id="df7ad-138">EF 코어에서 데이터를 검색 하려면 적절 한 속성에 액세스 및 LINQ를 사용 하 여 결과 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-138">To retrieve data from EF Core, you access the appropriate property and use LINQ to filter the result.</span></span> <span data-ttu-id="df7ad-139">또한 다른 결과 한 형식에서 변환 투영을 수행 하려면 LINQ를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-139">You can also use LINQ to perform projection, transforming the result from one type to another.</span></span> <span data-ttu-id="df7ad-140">다음 예제에서는 CatalogBrands를 이름으로 정렬 된의 Enabled 속성으로 필터링 및 SelectListItem 형식 투영 검색:</span><span class="sxs-lookup"><span data-stu-id="df7ad-140">The following example would retrieve CatalogBrands, ordered by name, filtered by their Enabled property, and projected onto a SelectListItem type:</span></span>

```csharp
var brandItems = await _context.CatalogBrands
    .Where(b => b.Enabled)
    .OrderBy(b => b.Name)
    .Select(b => new SelectListItem {
        Value = b.Id, Text = b.Name })
    .ToListAsync();
```

<span data-ttu-id="df7ad-141">즉시 쿼리를 실행 하기 위해 ToListAsync에 대 한 호출을 추가 하려면 위의 예에는 것이 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-141">It's important in the above example to add the call to ToListAsync in order to execute the query immediately.</span></span> <span data-ttu-id="df7ad-142">그렇지 않으면 문이 IQueryable를 할당 합니다<SelectListItem> brandItems에 실행 되지 것입니다 열거 될 때까지 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-142">Otherwise, the statement will assign an IQueryable<SelectListItem> to brandItems, which will not be executed until it is enumerated.</span></span> <span data-ttu-id="df7ad-143">장점 및 단점 메서드에서 IQueryable 결과 반환에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-143">There are pros and cons to returning IQueryable results from methods.</span></span> <span data-ttu-id="df7ad-144">사용 하면 쿼리 EF 코어 추가로 수정할 수 있지만 작업은 EF 코어 변환할 수 없는 쿼리에 추가 하는 경우만 런타임 시 발생 하는 오류를 발생 할 수도 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-144">It allows the query EF Core will construct to be further modified, but can also result in errors that only occur at runtime, if operations are added to the query that EF Core cannot translate.</span></span> <span data-ttu-id="df7ad-145">입니다 일반적으로 안전 하 게 데이터 액세스를 수행 메서드에 필터를 전달 하 고 반환 다시 메모리에 컬렉션 (예: 목록<T>)로 인해 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-145">It's generally safer to pass any filters into the method performing the data access, and return back an in-memory collection (for example, List<T>) as the result.</span></span>

<span data-ttu-id="df7ad-146">EF 코어 지 속성 저장소에서 인출 되는 엔터티에 대해 변경 내용을 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-146">EF Core tracks changes on entities it fetches from persistence.</span></span> <span data-ttu-id="df7ad-147">변경 내용을 추적 된 엔터티를 저장 하려면 단순히 확인 해야는 엔터티를 인출 하는 데 사용 된 동일한 DbContext 인스턴스에 DbContext에 대해 SaveChanges 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-147">To save changes to a tracked entity, you just call the SaveChanges method on the DbContext, making sure it's the same DbContext instance that was used to fetch the entity.</span></span> <span data-ttu-id="df7ad-148">데이터베이스 명령을 실행 하는 SaveChanges 호출을 사용 하 여 다시 적절 한 DbSet 속성에 직접 추가 및 제거 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-148">Adding and removing entities is directly on the appropriate DbSet property, again with a call to SaveChanges to execute the database commands.</span></span> <span data-ttu-id="df7ad-149">다음 예제에서는 추가, 업데이트 및 지 속성 저장소에서 엔터티를 제거 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-149">The following example demonstrates adding, updating, and removing entities from persistence.</span></span>

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

<span data-ttu-id="df7ad-150">EF Core 지원 둘 다 동기 및 비동기 메서드를 가져오고 저장 하기 위해 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-150">EF Core supports both synchronous and async methods for fetching and saving.</span></span> <span data-ttu-id="df7ad-151">에서는 웹 응용 프로그램 것이 좋습니다 비동기 메서드와 async/await 패턴을 사용 하려면 웹 서버 스레드는 데이터 액세스 작업이 끝나기를 기다리는 동안 차단 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-151">In web applications, it's recommended to use the async/await pattern with the async methods, so that web server threads are not blocked while waiting for data access operations to complete.</span></span>

### <a name="fetching-related-data"></a><span data-ttu-id="df7ad-152">관련된 데이터를 인출합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-152">Fetching Related Data</span></span>

<span data-ttu-id="df7ad-153">EF 코어 엔터티를 검색 하는 경우 직접 엔터티와 해당 데이터베이스에 저장 된 속성을 모두 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-153">When EF Core retrieves entities, it populates all of the properties that are stored directly with that entity in the database.</span></span> <span data-ttu-id="df7ad-154">관련 엔터티의 목록과 같은 탐색 속성은 채워지지 않으며 해당 값으로 설정 되어 있을 수는 null입니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-154">Navigation properties, such as lists of related entities, are not populated and may have their value set to null.</span></span> <span data-ttu-id="df7ad-155">이렇게 하면 EF 코어는 가져오지는 필요한 것 보다 더 많은 데이터를 신속 하 게 요청을 처리 하 고 효율적인 방식으로 응답을 반환 해야 하는 웹 응용 프로그램에 특히 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-155">This ensures EF Core is not fetching more data than is needed, which is especially important for web applications, which must quickly process requests and return responses in an efficient manner.</span></span> <span data-ttu-id="df7ad-156">관계를 사용 하 여 엔터티를 포함 하도록 *즉시 로드*, 표시 된 것 처럼 쿼리를 포함 확장 메서드를 사용 하는 속성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-156">To include relationships with an entity using *eager loading*, you specify the property using the Include extension method on the query, as shown:</span></span>

```csharp
// .Include requires using Microsoft.EntityFrameworkCore
var brandsWithItems = await _context.CatalogBrands
    .Include(b => b.Items)
    .ToListAsync();
```

<span data-ttu-id="df7ad-157">관계가 여러 개 포함할 수 있으며 하위 관계를 포함할 수도 있습니다 ThenInclude를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-157">You can include multiple relationships, and you can also include sub-relationships using ThenInclude.</span></span> <span data-ttu-id="df7ad-158">EF 코어 엔터티의 결과 집합을 검색 하는 단일 쿼리를 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-158">EF Core will execute a single query to retrieve the resulting set of entities.</span></span>

<span data-ttu-id="df7ad-159">관련된 데이터를 로드 하기 위한 또 다른 옵션은 사용 하도록 *명시적 로딩*합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-159">Another option for loading related data is to use *explicit loading*.</span></span> <span data-ttu-id="df7ad-160">명시적 로드를 사용 하면 이미 검색 된 엔터티로 추가 데이터를 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-160">Explicit loading allows you to load additional data into an entity that has already been retrieved.</span></span> <span data-ttu-id="df7ad-161">데이터베이스의 수를 최소화 해야 하는 웹 응용 프로그램에 대 한 이후 데이터베이스에 별도 요청을 포함 하는이 권장 되지 않습니다 왕복 요청에 따라 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-161">Since this involves a separate request to the database, it's not recommended for web applications, which should minimize the number of database round trips made per request.</span></span>

<span data-ttu-id="df7ad-162">*지연 로드* 은 자동으로 응용 프로그램에서 참조 되므로 관련된 데이터를 로드 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-162">*Lazy loading* is a feature that automatically loads related data as it is referenced by the application.</span></span> <span data-ttu-id="df7ad-163">현재 EF Core에서 지원 되지만으로 명시적 로드 하 여 것은 일반적으로 사용 되지 웹 응용 프로그램에 대 한.</span><span class="sxs-lookup"><span data-stu-id="df7ad-163">It's not currently supported by EF Core, but as with explicit loading it should typically be disabled for web applications.</span></span>

### <a name="resilient-connections"></a><span data-ttu-id="df7ad-164">복원 력 있는 연결</span><span class="sxs-lookup"><span data-stu-id="df7ad-164">Resilient Connections</span></span>

<span data-ttu-id="df7ad-165">SQL 데이터베이스와 같은 외부 리소스 수 경우에 따라 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-165">External resources like SQL databases may occasionally be unavailable.</span></span> <span data-ttu-id="df7ad-166">일시적으로 사용할 수의 경우에서 응용 프로그램 예외가 발생 하지 않도록 하려면 재시도 논리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-166">In cases of temporary unavailability, applications can use retry logic to avoid raising an exception.</span></span> <span data-ttu-id="df7ad-167">이 방법은 일반적으로 라고 *연결 복원 력*합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-167">This technique is commonly referred to as *connection resiliency*.</span></span> <span data-ttu-id="df7ad-168">구현할 수 있습니다 프로그램 [지 수 백오프도 직접 재시도](https://docs.microsoft.com/azure/architecture/patterns/retry) 최대 다시 시도 횟수에 도달할 때까지 대기 시간이 기하급수적으로 증가 시켜 다시 시도 하 여 기술 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-168">You can implement your [own retry with exponential backoff](https://docs.microsoft.com/azure/architecture/patterns/retry) technique by attempting to rety with an exponentially increasing wait time, until a maximum retry count has been reached.</span></span> <span data-ttu-id="df7ad-169">이 방법을 채택 팩트는 클라우드 리소스 일시적으로 사용할 수 없습니다 짧은 기간 동안, 일부 요청 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-169">This technique embraces the fact that cloud resources might intermittently be unavailable for short periods of time, resulting in failure of some requests.</span></span>

<span data-ttu-id="df7ad-170">Azure SQL DB에 대 한 Entity Framework Core 이미 내부 데이터베이스 연결 복원 력 및 재시도 논리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-170">For Azure SQL DB, Entity Framework Core already provides internal database connection resiliency and retry logic.</span></span> <span data-ttu-id="df7ad-171">하지만 복원 력 있는 EF 코어 연결 하려는 경우 각 DbContext 연결에 대 한 Entity Framework 실행 전략을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-171">But you need to enable the Entity Framework execution strategy for each DbContext connection if you want to have resilient EF Core connections.</span></span>

<span data-ttu-id="df7ad-172">예를 들어, EF 코어 연결 수준에서 다음 코드에는 연결에 실패 하면 다시 시도 되는 복원 력이 SQL 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-172">For instance, the following code at the EF Core connection level enables resilient SQL connections that are retried if the connection fails.</span></span>

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

  #### <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a><span data-ttu-id="df7ad-173">실행 전략 및 BeginTransaction 및 여러 DbContexts를 사용 하 여 명시적 트랜잭션을</span><span class="sxs-lookup"><span data-stu-id="df7ad-173">Execution strategies and explicit transactions using BeginTransaction and multiple DbContexts</span></span> 
  
  <span data-ttu-id="df7ad-174">재시도 EF 코어 연결에서 설정 되 면 EF 코어를 사용 하 여 수행한 각 작업 다시 시도할 수 연산이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-174">When retries are enabled in EF Core connections, each operation you perform using EF Core becomes its own retriable operation.</span></span> <span data-ttu-id="df7ad-175">일시적인 오류가 발생 하는 경우 각 쿼리 및 SaveChanges 호출할 때마다 하나의 단위로 재시도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-175">Each query and each call to SaveChanges will be retried as a unit if a transient failure occurs.</span></span>
  
  <span data-ttu-id="df7ad-176">그러나 BeginTransaction를 사용 하 여 트랜잭션을 시작 하는 코드를 정의 하는 경우 하나의 단위로 처리 해야 하는 작업의 사용자 정의 그룹-오류가 발생할 경우 롤백할 수에 트랜잭션 내의 모든 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-176">However, if your code initiates a transaction using BeginTransaction, you are defining your own group of operations that need to be treated as a unit—everything inside the transaction has be rolled back if a failure occurs.</span></span> <span data-ttu-id="df7ad-177">EF 실행 전략 (다시 시도 정책)를 사용 하는 경우 해당 트랜잭션을 실행 하려고 하면 그 안에 여러 DbContexts에서 여러 SaveChanges를 포함 하는 경우 다음과 같은 예외가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-177">You will see an exception like the following if you attempt to execute that transaction when using an EF execution strategy (retry policy) and you include several SaveChanges from multiple DbContexts in it.</span></span>

<span data-ttu-id="df7ad-178">System.InvalidOperationException: 구성 된 실행 전략 'SqlServerRetryingExecutionStrategy' 사용자가 시작한 트랜잭션을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-178">System.InvalidOperationException: The configured execution strategy 'SqlServerRetryingExecutionStrategy' does not support user initiated transactions.</span></span> <span data-ttu-id="df7ad-179">'DbContext.Database.CreateExecutionStrategy()'에서 반환 된 실행 전략을 사용 하 여 트랜잭션을 다시 시도할 수 한 단위로 모든 작업을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-179">Use the execution strategy returned by 'DbContext.Database.CreateExecutionStrategy()' to execute all the operations in the transaction as a retriable unit.</span></span>

<span data-ttu-id="df7ad-180">해결 방법은 수동으로 실행 해야 하는 모든 항목을 나타내는 대리자를 사용 하 여 EF 실행 전략을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-180">The solution is to manually invoke the EF execution strategy with a delegate representing everything that needs to be executed.</span></span> <span data-ttu-id="df7ad-181">일시적인 오류가 발생 하는 경우 실행 전략 대리자를 다시 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-181">If a transient failure occurs, the execution strategy will invoke the delegate again.</span></span> <span data-ttu-id="df7ad-182">다음 코드에는이 구현 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-182">The following code shows how to implement this approach:</span></span>

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

<span data-ttu-id="df7ad-183">첫 번째 DbContext가는 \_DbContext 내인지 catalogContext 및 두 번째는 \_integrationEventLogService 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-183">The first DbContext is the \_catalogContext and the second DbContext is within the \_integrationEventLogService object.</span></span> <span data-ttu-id="df7ad-184">마지막으로, 작업 수는 커밋 여러 DbContexts 및 EF 실행 전략을 사용 하 여 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-184">Finally, the Commit action would be performed multiple DbContexts and using an EF Execution Strategy.</span></span>

> ### <a name="references--entity-framework-core"></a><span data-ttu-id="df7ad-185">참조-Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="df7ad-185">References – Entity Framework Core</span></span>
> - <span data-ttu-id="df7ad-186">**EF Core Docs**</span><span class="sxs-lookup"><span data-stu-id="df7ad-186">**EF Core Docs**</span></span>  
> <span data-ttu-id="df7ad-187"><https://docs.microsoft.com/ef/></span><span class="sxs-lookup"><span data-stu-id="df7ad-187"><https://docs.microsoft.com/ef/></span></span>
> - <span data-ttu-id="df7ad-188">**EF 핵심: 관련된 데이터**</span><span class="sxs-lookup"><span data-stu-id="df7ad-188">**EF Core: Related Data**</span></span>  
> <span data-ttu-id="df7ad-189"><https://docs.microsoft.com/ef/core/querying/related-data></span><span class="sxs-lookup"><span data-stu-id="df7ad-189"><https://docs.microsoft.com/ef/core/querying/related-data></span></span>
> - <span data-ttu-id="df7ad-190">**ASPNET 응용 프로그램의 엔터티를 지연 로드를 방지 합니다.**</span><span class="sxs-lookup"><span data-stu-id="df7ad-190">**Avoid Lazy Loading Entities in ASPNET Applications**</span></span>  
> <span data-ttu-id="df7ad-191"><http://ardalis.com/avoid-lazy-loading-entities-in-asp-net-applications></span><span class="sxs-lookup"><span data-stu-id="df7ad-191"><http://ardalis.com/avoid-lazy-loading-entities-in-asp-net-applications></span></span>

## <a name="ef-core-or-micro-orm"></a><span data-ttu-id="df7ad-192">EF 코어 또는 마이크로 ORM?</span><span class="sxs-lookup"><span data-stu-id="df7ad-192">EF Core or micro-ORM?</span></span>

<span data-ttu-id="df7ad-193">이 지 속성을 관리 하기 위한 최선의 선택 하 고 대부분의 응용 프로그램 개발자의 데이터베이스 세부 정보를 캡슐화 하는 EF 코어, 유일한 선택은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-193">While EF Core is a great choice for managing persistence, and for the most part encapsulates database details from application developers, it is not the only choice.</span></span> <span data-ttu-id="df7ad-194">인기 있는 오픈 소스 있는 다른 방법은 [Dapper](https://github.com/StackExchange/Dapper), 마이크로 ORM 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-194">Another popular open source alternative is [Dapper](https://github.com/StackExchange/Dapper), a so-called micro-ORM.</span></span> <span data-ttu-id="df7ad-195">마이크로 ORM은 개체 데이터 구조를 매핑하기 위한 모든 기능을 갖춘 도구 보다 간단한 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-195">A micro-ORM is a lightweight, less full-featured tool for mapping objects to data structures.</span></span> <span data-ttu-id="df7ad-196">Dapper의 경우의 디자인 목표 보다 쿼리하여 내부를 완벽 하 게 캡슐화 하는 성능에 집중 데이터 검색 및 업데이트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-196">In the case of Dapper, its design goals focus on performance, rather than fully encapsulating the underlying queries it uses to retrieve and update data.</span></span> <span data-ttu-id="df7ad-197">Dapper "금속에 가까운" 및 개발자는 정확 하 게 작성할 수 있습니다 개발자의 SQL 추상 하지 않는 것을 하기 때문에 지정 된 데이터에 대 한 사용 하려는 쿼리 작업에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-197">Because it doesn't abstract SQL from the developer, Dapper is "closer to the metal" and lets developers write the exact queries they want to use for a given data access operation.</span></span>

<span data-ttu-id="df7ad-198">EF 코어에 두 가지 중요 한 기능이 제공 Dapper에서 분리할 수는 있지만 해당 성능 오버 헤드를 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-198">EF Core has two significant features it provides which separate it from Dapper but also add to its performance overhead.</span></span> <span data-ttu-id="df7ad-199">첫 번째는 SQL로 LINQ 식에서 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-199">The first is translation from LINQ expressions into SQL.</span></span> <span data-ttu-id="df7ad-200">이러한 번역 캐시 되며 있지만 그럼에도 오버 헤드를 수행 하 여 처음에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-200">These translations are cached, but even so there is overhead in performing them the first time.</span></span> <span data-ttu-id="df7ad-201">두 번째 (있도록 효율적인 update 문을 생성할 수 있습니다) 엔터티에 대해 변경 내용 추적입니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-201">The second is change tracking on entities (so that efficient update statements can be generated).</span></span> <span data-ttu-id="df7ad-202">AsNotTracking 확장을 사용 하 여 특정 쿼리에 대해이 동작이 해제 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-202">This behavior can be turned off for specific queries by using the AsNotTracking extension.</span></span> <span data-ttu-id="df7ad-203">EF 코어도 일반적으로 매우 효율적이 고 어떤 경우 든 성능 관점에서 완벽 하 게 허용 하는 SQL 쿼리를 생성 하지만 세부적으로 제어 해야 실행할 정확한 쿼리를 통해, 사용자 지정 SQL에서 전달할 수 있습니다 (또는 저장된 프로시저를 실행) EF를 사용 하 여 핵심, 너무 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-203">EF Core also generates SQL queries that usually are very efficient and in any case perfectly acceptable from a performance standpoint, but if you need fine control over the precise query to be executed, you can pass in custom SQL (or execute a stored procedure) using EF Core, too.</span></span> <span data-ttu-id="df7ad-204">이 경우 Dapper 된 상태는 EF 코어 하지만 약간만 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-204">In this case, Dapper still outperforms EF Core, but only slightly.</span></span> <span data-ttu-id="df7ad-205">Julie Lerman 표시 합니다. 일부 성능 데이터를 보려면 아래 2016 MSDN 문서 수 [Dapper, Entity Framework 및 하이브리드 앱](https://msdn.microsoft.com/magazine/mt703432.aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-205">Julie Lerman presents some performance data in her May 2016 MSDN article [Dapper, Entity Framework, and Hybrid Apps](https://msdn.microsoft.com/magazine/mt703432.aspx).</span></span> <span data-ttu-id="df7ad-206">다양 한 데이터 액세스 방법에 대 한 추가 성능 벤치 마크 데이터에 있습니다 [Dapper 사이트](https://github.com/StackExchange/Dapper)합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-206">Additional performance benchmark data for a variety of data access methods can be found on [the Dapper site](https://github.com/StackExchange/Dapper).</span></span>

<span data-ttu-id="df7ad-207">EF 코어에서 Dapper 구문은 변화를 보려면 항목의 목록을 검색 하는 것에 대 한 동일한 메서드의 이러한 두 가지 버전을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-207">To see how the syntax for Dapper varies from EF Core, consider these two versions of the same method for retrieving a list of items:</span></span>

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

<span data-ttu-id="df7ad-208">Dapper와 더 복잡 한 개체 그래프를 작성 해야 할 경우 (EF 코어에서와 마찬가지로 Include 추가) 대비 직접 연결 된 쿼리를 작성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-208">If you need to build more complex object graphs with Dapper, you need to write the associated queries yourself (as opposed to adding an Include as you would in EF Core).</span></span> <span data-ttu-id="df7ad-209">이 다양 한 구문에서 매핑된 개체를 여러 개를 개별 행에 매핑할 수 있도록 다중 매핑 이라는 기능을 포함 하 여 통해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-209">This is supported through a variety of syntaxes, including a feature called Multi Mapping that lets you map individual rows to multiple mapped objects.</span></span> <span data-ttu-id="df7ad-210">예를 들어 사용자 형식의 소유자 속성을 가진 Post 클래스가 있다고 가정, 다음 SQL를 반환 합니다의 모든 필요한 데이터.</span><span class="sxs-lookup"><span data-stu-id="df7ad-210">For example, given a class Post with a property Owner of type User, the following SQL would return all of the necessary data:</span></span>

```sql
select * from #Posts p
left join \#Users u on u.Id = p.OwnerId
Order by p.Id
```

<span data-ttu-id="df7ad-211">반환 된 각 행에는 사용자와 Post 데이터가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-211">Each returned row includes both User and Post data.</span></span> <span data-ttu-id="df7ad-212">사용자 데이터의 소유자 속성을 통해 게시 데이터에 연결, 하므로 다음 함수는 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-212">Since the User data should be attached to the Post data via its Owner property, the following function is used:</span></span>

```csharp
(post, user) => { post.Owner = user; return post; }
```

<span data-ttu-id="df7ad-213">연결 된 사용자 데이터로 채워진 소유자 속성와 게시물의 컬렉션을 반환 하는 전체 코드 목록을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-213">The full code listing to return a collection of posts with their Owner property populated with the associated user data would be:</span></span>

```csharp
var sql = @"select * from #Posts p
left join #Users u on u.Id = p.OwnerId
Order by p.Id";
var data = connection.Query<Post, User, Post>(sql,
(post, user) => { post.Owner = user; return post;});
```

<span data-ttu-id="df7ad-214">덜 캡슐화를 제공 하기 때문에 Dapper 필요 개발자가 해당 데이터가 저장 되는 방법에 대 한 자세한 내용을 효율적으로 쿼리를 가져오기 위해 더 많은 코드를 작성 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-214">Because it offers less encapsulation, Dapper requires developers know more about how their data is stored, how to query it efficiently, and write more code to fetch it.</span></span> <span data-ttu-id="df7ad-215">단순히 새 마이그레이션 (다른 EF 핵심 기능) 만들기 및/또는 DbContext에서 한 단계에서 매핑 정보를 업데이트 하는 대신 모델 변경 될 때 모든 쿼리는 영향을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-215">When the model changes, instead of simply creating a new migration (another EF Core feature), and/or updating mapping information in one place in a DbContext, every query that is impacted must be updated.</span></span> <span data-ttu-id="df7ad-216">이러한 쿼리 컴파일 시간 보장 하지 없으므로 중단 될 수 있습니다 런타임에 변경 사항에 따라 모델이 나 데이터베이스를 오류를 신속 하 게 감지 하기가 더 어려운 만들기.</span><span class="sxs-lookup"><span data-stu-id="df7ad-216">These queries have not compile time guarantees, so they may break at runtime in response to changes to the model or database, making errors more difficult to detect quickly.</span></span> <span data-ttu-id="df7ad-217">이러한 장단점 수준은 낮은 대신 Dapper 매우 빠른 성능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-217">In exchange for these tradeoffs, Dapper offers extremely fast performance.</span></span>

<span data-ttu-id="df7ad-218">대부분의 응용 프로그램 및 거의 모든 응용 프로그램의 대부분 부분에 대 한 EF 코어 허용 가능한 성능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-218">For most applications, and most parts of almost all applications, EF Core offers acceptable performance.</span></span> <span data-ttu-id="df7ad-219">따라서 개발자 생산성 이점을 해당 성능 오버 헤드 보다 클 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-219">Thus, its developer productivity benefits are likely to outweigh its performance overhead.</span></span> <span data-ttu-id="df7ad-220">캐싱 활용할 수 있는 쿼리에 대 한 실제 쿼리만 실행 될 수 있습니다 상대적으로 작은 만드는 시간의 작은 비율 성능 차이 moot를 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-220">For queries that can benefit from caching, the actual query may only be executed a tiny percentage of the time, making relatively small query performance differences moot.</span></span>

## <a name="sql-or-nosql"></a><span data-ttu-id="df7ad-221">SQL 또는 비 Sql</span><span class="sxs-lookup"><span data-stu-id="df7ad-221">SQL or NoSQL</span></span>

<span data-ttu-id="df7ad-222">일반적으로 SQL Server와 같은 관계형 데이터베이스 영구 데이터 저장소에 대 한 마켓플레이스 지배 있어야 하지만 사용할 수 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-222">Traditionally, relational databases like SQL Server have dominated the marketplace for persistent data storage, but they are not the only solution available.</span></span> <span data-ttu-id="df7ad-223">와 같은 NoSQL 데이터베이스 [MongoDB](https://www.mongodb.com/what-is-mongodb) 에 개체를 저장 하는 다른 접근 방식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-223">NoSQL databases like [MongoDB](https://www.mongodb.com/what-is-mongodb) offer a different approach to storing objects.</span></span> <span data-ttu-id="df7ad-224">테이블 및 행에 개체를 매핑, 대신 두 번째 방법은 하 전체 개체 그래프를 serialize 하 고 결과 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-224">Rather than mapping objects to tables and rows, another option is to serialize the entire object graph, and store the result.</span></span> <span data-ttu-id="df7ad-225">이 방법의 이점은 간단 하 고 성능에 최소한 초기에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-225">The benefits of this approach, at least initially, are simplicity and performance.</span></span> <span data-ttu-id="df7ad-226">하는 것이 분명를 분해 개체 관계를 가진 여러 테이블 보다는 키를 사용 하 여 단일 직렬화 된 개체를 저장 하 고 업데이트 하 고 개체를 마지막 이후 변경 수 있는 행은 데이터베이스에서 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-226">It's certainly simpler to store a single serialized object with a key than to decompose the object into many tables with relationships and update and rows that may have changed since the object was last retrieved from the database.</span></span> <span data-ttu-id="df7ad-227">마찬가지로, 인출 하 고 키 기반 저장소에서 단일 개체를 역직렬화 하는 동안는 일반적으로 훨씬 손쉽고 빠릅니다 보다 복잡 한 조인이 나 완전 하 게 관계형 데이터베이스에서 동일한 개체를 작성 하는 데 필요한 여러 데이터베이스 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-227">Likewise, fetching and deserializing a single object from a key-based store is typically much faster and easier than complex joins or multiple database queries required to fully compose the same object from a relational database.</span></span> <span data-ttu-id="df7ad-228">잠금 또는 트랜잭션 또는 고정된 스키마의 부족 하면 NoSQL 데이터베이스 매우 많은 컴퓨터를 매우 큰 데이터 집합을 지 원하는 확장 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-228">The lack of locks or transactions or a fixed schema also makes NoSQL databases very amenable to scaling across many machines, supporting very large datasets.</span></span>

<span data-ttu-id="df7ad-229">반면에 NoSQL 데이터베이스 (일반적으로 이라고) 있을 단점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-229">On the other hand, NoSQL databases (as they are typically called) have their drawbacks.</span></span> <span data-ttu-id="df7ad-230">관계형 데이터베이스 일관성을 유지 하 고 데이터 중복 방지를 정규화를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-230">Relational databases use normalization to enforce consistency and avoid duplication of data.</span></span> <span data-ttu-id="df7ad-231">이 데이터베이스의 전체 크기를 줄일 수 및 공유 데이터에 대 한 업데이트를 즉시 데이터베이스 전체에서 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-231">This reduces the total size of the database and ensures that updates to shared data are available immediately throughout the database.</span></span> <span data-ttu-id="df7ad-232">관계형 데이터베이스에서 해당 국가의 이름이 변경 된 경우 주소 레코드 도움이 되는 업데이트 작업에서 업데이트 해야 자체 없이 되도록 주소 테이블 국가 테이블 ID로 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-232">In a relational database, an Address table might reference a Country table by ID, such that if a country's name were changed, the address records would benefit from the update without themselves having to be updated.</span></span> <span data-ttu-id="df7ad-233">그러나 NoSQL 데이터베이스 주소와 연결 된 해당 국가 수 직렬화 할 수 많은 저장 된 개체의 일부로 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-233">However, in a NoSQL database, Address and its associated Country might be serialized as part of many stored objects.</span></span> <span data-ttu-id="df7ad-234">국가 이름에 대 한 업데이트는 단일 행 대신 업데이트를 이러한 개체를 모두 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-234">An update to a country name would require all such objects to be updated, rather than a single row.</span></span> <span data-ttu-id="df7ad-235">관계형 데이터베이스는 외래 키와 같은 규칙을 적용 하 여 관계 무결성을 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-235">Relational databases can also ensure relational integrity by enforcing rules like foreign keys.</span></span> <span data-ttu-id="df7ad-236">일반적으로 NoSQL 데이터베이스는 이러한 제약 조건에 게 데이터를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-236">NoSQL databases typically do not offer such constraints on their data.</span></span>

<span data-ttu-id="df7ad-237">다른 복잡성 데이터베이스를 처리 해야 하는 NoSQL 버전 관리입니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-237">Another complexity NoSQL databases must deal with is versioning.</span></span> <span data-ttu-id="df7ad-238">개체의 속성이 변경 될 때 저장 된 이전 버전에서 역직렬화 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-238">When an object's properties change, it may not be able to be deserialized from past versions that were stored.</span></span> <span data-ttu-id="df7ad-239">따라서 개체의 직렬화 된 (이전) 버전을 포함 하는 모든 기존 개체의 새 스키마에 맞게 업데이트 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-239">Thus, all existing objects that have a serialized (previous) version of the object must be updated to conform to its new schema.</span></span> <span data-ttu-id="df7ad-240">이것이 관계형 데이터베이스에서 다른 개념적으로, 업데이트 스크립트를 필요 하거나 업데이트 매핑 스키마가 경우에 따라 변경 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="df7ad-240">This is not conceptually different from a relational database, where schema changes sometimes require update scripts or mapping updates.</span></span> <span data-ttu-id="df7ad-241">그러나 파일을 수정 해야 하는 항목의 수는 종종 훨씬 더 많은 데이터 중복 있기 때문에 NoSQL 접근 방식에서 큰 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-241">However, the number of entries that must be modified is often much greater in the NoSQL approach, because there is more duplication of data.</span></span>

<span data-ttu-id="df7ad-242">개체의 여러 버전을 저장 하는 NoSQL 데이터베이스에서는, 관계형 데이터베이스 항목 합계의 고정된 스키마가 일반적으로 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-242">It's possible in NoSQL databases to store multiple versions of objects, something fixed schema relational databases typically do not support.</span></span> <span data-ttu-id="df7ad-243">그러나이 경우 응용 프로그램 코드 고려해 야 합니다 복잡성이 추가 추가 하는 개체의 이전 버전의 존재 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-243">However, in this case your application code will need to account for the existence of previous versions of objects, adding additional complexity.</span></span>

<span data-ttu-id="df7ad-244">NoSQL 데이터베이스를 일반적으로 실행 하지 않는 [ACID](http://en.wikipedia.org/wiki/ACID), 즉, 관계형 데이터베이스에 대해 모두 성능 및 확장성 이점을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-244">NoSQL databases typically do not enforce [ACID](http://en.wikipedia.org/wiki/ACID), which means they have both performance and scalability benefits over relational databases.</span></span> <span data-ttu-id="df7ad-245">하기가 매우 큰 데이터 집합을 정규화 테이블 구조에는 저장소에 적합 하지 않은 개체에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-245">They're well-suited to extremely large datasets and objects that are not well-suited to storage in normalized table structures.</span></span> <span data-ttu-id="df7ad-246">이유는 단일 응용 프로그램 변수 모두 사용할 관계형을 적합 한 것이 가장 좋습니다을 각각에 사용 하 여 NoSQL 데이터베이스 않아도가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-246">There is no reason why a single application cannot take advantage of both relational and NoSQL databases, using each where it is best suited.</span></span>

## <a name="azure-documentdb"></a><span data-ttu-id="df7ad-247">Azure DocumentDB</span><span class="sxs-lookup"><span data-stu-id="df7ad-247">Azure DocumentDB</span></span>

<span data-ttu-id="df7ad-248">Azure DocumentDB는 완전히 관리 되는 NoSQL 데이터베이스 서비스를 스키마가 없는 클라우드 기반 데이터 저장소를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-248">Azure DocumentDB is a fully managed NoSQL database service that offers cloud-based schema-free data storage.</span></span> <span data-ttu-id="df7ad-249">DocumentDB는 신속 하 고 예측 가능한 성능, 고가용성, 탄력적인 크기 조정 및 글로벌 배포에 대 한 작성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-249">DocumentDB is built for fast and predictable performance, high availability, elastic scaling, and global distribution.</span></span> <span data-ttu-id="df7ad-250">NoSQL 데이터베이스 되 고, 불구 하 고 개발자는 JSON 데이터에 대해 풍부 하 고 친숙 한 SQL 쿼리 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-250">Despite being a NoSQL database, developers can use rich and familiar SQL query capabilities on JSON data.</span></span> <span data-ttu-id="df7ad-251">DocumentDB의 모든 리소스를 JSON 문서로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-251">All resources in DocumentDB are stored as JSON documents.</span></span> <span data-ttu-id="df7ad-252">리소스와 관리 *항목*어떤, 메타 데이터를 포함 하는 문서는 및 *피드*, 항목의 컬렉션인 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-252">Resources are managed as *items*, which are documents containing metadata, and *feeds*, which are collections of items.</span></span> <span data-ttu-id="df7ad-253">그림 8-2는 서로 다른 DocumentDB 리소스 간의 관계를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-253">Figure 8-2 shows the relationship between different DocumentDB resources.</span></span>


![Documentdb에서 JSON NoSQL 데이터베이스 리소스 간의 계층 관계](./media/image8-2.png)

<span data-ttu-id="df7ad-255">**그림 8-2입니다.**</span><span class="sxs-lookup"><span data-stu-id="df7ad-255">**Figure 8-2.**</span></span> <span data-ttu-id="df7ad-256">DocumentDB 리소스 조직입니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-256">DocumentDB resource organization.</span></span>

<span data-ttu-id="df7ad-257">DocumentDB 쿼리 언어에는 JSON 문서를 쿼리 하기 위한 단순 하면서도 강력한 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-257">The DocumentDB query language is a simple yet powerful interface for querying JSON documents.</span></span> <span data-ttu-id="df7ad-258">언어는 ANSI SQL 문법의 하위 집합을 지원 하 고 JavaScript 개체, 배열, 개체 생성 및 함수 호출의 긴밀 한 통합을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-258">The language supports a subset of ANSI SQL grammar and adds deep integration of JavaScript object, arrays, object construction, and function invocation.</span></span>

<span data-ttu-id="df7ad-259">**DocumentDB-참조**</span><span class="sxs-lookup"><span data-stu-id="df7ad-259">**References – DocumentDB**</span></span>

-   <span data-ttu-id="df7ad-260">DocumentDB Introduction\\</span><span class="sxs-lookup"><span data-stu-id="df7ad-260">DocumentDB Introduction\\</span></span>
    <span data-ttu-id="df7ad-261"><https://docs.microsoft.com/azure/documentdb/documentdb-introduction></span><span class="sxs-lookup"><span data-stu-id="df7ad-261"><https://docs.microsoft.com/azure/documentdb/documentdb-introduction></span></span>

## <a name="other-persistence-options"></a><span data-ttu-id="df7ad-262">다른 지 속성 옵션</span><span class="sxs-lookup"><span data-stu-id="df7ad-262">Other Persistence Options</span></span>

<span data-ttu-id="df7ad-263">ASP.NET Core 응용 프로그램 외에 관계형 및 NoSQL 저장소 옵션에 클라우드 기반이 고 확장 가능한 방식으로 다양 한 데이터 형식 및 파일을 저장할 Azure 저장소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-263">In addition to relational and NoSQL storage options, ASP.NET Core applications can use Azure Storage to store a variety of data formats and files in a cloud-based, scalable fashion.</span></span> <span data-ttu-id="df7ad-264">Azure 저장소 확장성이 뛰어난, 이므로 적은 양의 데이터와 응용 프로그램에서 필요한 경우 수백 또는 테라바이트 저장 크기를 저장 하기 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-264">Azure Storage is massively scalable, so you can start out storing small amounts of data and scale up to storing hundreds or terabytes if your application requires it.</span></span> <span data-ttu-id="df7ad-265">Azure 저장소는 네 가지 종류의 데이터를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-265">Azure Storage supports four kinds of data:</span></span>

-   <span data-ttu-id="df7ad-266">구조화 되지 않은 텍스트 또는 개체 저장소 라고도 하는 이진 저장소에 대 한 blob 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-266">Blob Storage for unstructured text or binary storage, also referred to as object storage.</span></span>

-   <span data-ttu-id="df7ad-267">구조화 된 데이터 집합, 행 키를 통해 액세스할 수에 대 한 테이블 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-267">Table Storage for structured datasets, accessible via row keys.</span></span>

-   <span data-ttu-id="df7ad-268">신뢰할 수 있는 큐 기반 메시징을 위한 큐 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-268">Queue Storage for reliable queue-based messaging.</span></span>

-   <span data-ttu-id="df7ad-269">Azure 가상 컴퓨터와 온-프레미스 응용 프로그램 간에 공유 파일 액세스에 대 한 저장소를 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-269">File Storage for shared file access between Azure virtual machines and on-premises applications.</span></span>

<span data-ttu-id="df7ad-270">**참조 – Azure 저장소**</span><span class="sxs-lookup"><span data-stu-id="df7ad-270">**References – Azure Storage**</span></span>

-   <span data-ttu-id="df7ad-271">Azure 저장소 Introduction\\</span><span class="sxs-lookup"><span data-stu-id="df7ad-271">Azure Storage Introduction\\</span></span>
    <span data-ttu-id="df7ad-272"><https://docs.microsoft.com/azure/storage/storage-introduction></span><span class="sxs-lookup"><span data-stu-id="df7ad-272"><https://docs.microsoft.com/azure/storage/storage-introduction></span></span>

## <a name="caching"></a><span data-ttu-id="df7ad-273">캐싱</span><span class="sxs-lookup"><span data-stu-id="df7ad-273">Caching</span></span>

<span data-ttu-id="df7ad-274">웹 응용 프로그램에서 각 웹 요청 가능한 가장 짧은 시간 내에 완료 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-274">In web applications, each web request should be completed in the shortest time possible.</span></span> <span data-ttu-id="df7ad-275">이 작업을 수행할 가지 방법은 서버에서 요청을 완료할 확인 해야 하는 외부 호출의 수를 제한 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-275">One way to achieve this is to limit the number of external calls the server must make to complete the request.</span></span> <span data-ttu-id="df7ad-276">서버에서 데이터의 복사본을 저장 하 캐싱 (또는 다른 데이터 저장소는 데이터의 원본을 보다 쉽게 쿼리할 더 즉).</span><span class="sxs-lookup"><span data-stu-id="df7ad-276">Caching involves storing a copy of data on the server (or another data store that is more easily queried than the source of the data).</span></span> <span data-ttu-id="df7ad-277">웹 응용 프로그램 및 특히 SPA 아닌 기존 웹 응용 프로그램 모든 요청에 전체 사용자 인터페이스를 작성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-277">Web applications, and especially non-SPA traditional web applications, need to build the entire user interface with every request.</span></span> <span data-ttu-id="df7ad-278">이 자주 다음 한 사용자 요청에서 반복 해 서 동일한 데이터베이스 쿼리를 여러 개 만들고 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-278">This frequently involves making many of the same database queries repeatedly from one user request to the next.</span></span> <span data-ttu-id="df7ad-279">대부분의 경우가이 데이터 지속적으로 데이터베이스에서 요청 하는 거의 필요가 있으므로 매우 드문 경우를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-279">In most cases, this data changes rarely, so there is little reason to constantly request it from the database.</span></span> <span data-ttu-id="df7ad-280">ASP.NET Core 응답 캐시를 전체 페이지 및 데이터 캐싱, 캐싱 있는 지원 보다 세부적인 캐싱 동작을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-280">ASP.NET Core supports response caching, for caching entire pages, and data caching, which supports more granular caching behavior.</span></span>

<span data-ttu-id="df7ad-281">캐싱을 구현할 때에 문제의 분리 염두에에서 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-281">When implementing caching, it's important to keep in mind separation of concerns.</span></span> <span data-ttu-id="df7ad-282">데이터 액세스 논리 사용자 또는 사용자 인터페이스에 캐싱 논리를 구현 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="df7ad-282">Avoid implementing caching logic in your data access logic, or in your user interface.</span></span> <span data-ttu-id="df7ad-283">대신, 자체 클래스에서 캐싱을 캡슐화 하 고 구성을 사용 하 여 해당 동작을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-283">Instead, encapsulate caching in its own classes, and use configuration to manage its behavior.</span></span> <span data-ttu-id="df7ad-284">이 열기/종결 됨 및 단일 책임 원칙을 따르며 쉽게 커짐에 따라 응용 프로그램에서 캐싱 사용 방법을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-284">This follows the Open/Closed and Single Responsibility principles, and will make it easier for you to manage how you use caching in your application as it grows.</span></span>

### <a name="aspnet-core-response-caching"></a><span data-ttu-id="df7ad-285">ASP.NET Core 응답 캐싱</span><span class="sxs-lookup"><span data-stu-id="df7ad-285">ASP.NET Core Response Caching</span></span>

<span data-ttu-id="df7ad-286">ASP.NET Core 두 가지 수준의 응답 캐시를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-286">ASP.NET Core supports two levels of response caching.</span></span> <span data-ttu-id="df7ad-287">첫 번째 수준 서버에서 모든 항목을 캐시 하지 하지만 클라이언트와 프록시 서버 응답을 캐시 하도록 지시 하는 HTTP 헤더를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-287">The first level does not cache anything on the server, but adds HTTP headers that instruct clients and proxy servers to cache responses.</span></span> <span data-ttu-id="df7ad-288">이 개별 컨트롤러 또는 동작에 ResponseCache 특성을 추가 하 여 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-288">This is implemented by adding the ResponseCache attribute to individual controllers or actions:</span></span>

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

<span data-ttu-id="df7ad-289">응답의 캐싱 미들웨어는 자동으로 사용자 지정할 수 있는 조건의 집합에 따라 응답을 캐시 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-289">The Response Caching Middleware will automatically cache responses based on a set of conditions, which you can customize.</span></span> <span data-ttu-id="df7ad-290">GET 또는 HEAD 메서드를 통해 요청만 200 (정상) 응답은 기본적으로 캐시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-290">By default, only 200 (OK) responses requested via GET or HEAD methods are cached.</span></span> <span data-ttu-id="df7ad-291">또한, 요청 된 응답으로 캐시 제어 있어야: 공용 헤더를 권한 부여 또는 Set-cookie 헤더를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-291">In addition, requests must have a response with a Cache-Control: public header, and cannot include headers for Authorization or Set-Cookie.</span></span> <span data-ttu-id="df7ad-292">참조는 [미들웨어 캐싱 응답에 의해 사용 되는 캐싱 조건의 전체 목록은](https://docs.microsoft.com/aspnet/core/performance/caching/middleware#conditions-for-caching)합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-292">See a [complete list of the caching conditions used by the response caching middleware](https://docs.microsoft.com/aspnet/core/performance/caching/middleware#conditions-for-caching).</span></span>

### <a name="data-caching"></a><span data-ttu-id="df7ad-293">데이터 캐싱</span><span class="sxs-lookup"><span data-stu-id="df7ad-293">Data Caching</span></span>

<span data-ttu-id="df7ad-294">대신 (또는 외에) 전체 웹 응답 캐시를 개별 데이터 쿼리의 결과 캐시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-294">Rather than (or in addition to) caching full web responses, you can cache the results of individual data queries.</span></span> <span data-ttu-id="df7ad-295">이 경우 웹 서버의 메모리 캐싱을 사용 하거나 사용할 수 있습니다 [분산된 캐시](https://docs.microsoft.com/aspnet/core/performance/caching/distributed)합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-295">For this, you can use in memory caching on the web server, or use [a distributed cache](https://docs.microsoft.com/aspnet/core/performance/caching/distributed).</span></span> <span data-ttu-id="df7ad-296">이 섹션에서는 메모리 캐시에 구현 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-296">This section will demonstrate how to implement in memory caching.</span></span>

<span data-ttu-id="df7ad-297">메모리에 대 한 지원 추가 (또는 분산) ConfigureServices의 캐싱 기능:</span><span class="sxs-lookup"><span data-stu-id="df7ad-297">You add support for memory (or distributed) caching in ConfigureServices:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMemoryCache();
    services.AddMvc();
}
```

<span data-ttu-id="df7ad-298">Microsoft.Extensions.Caching.Memory NuGet 패키지를 사용할 경우에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-298">Be sure to add the Microsoft.Extensions.Caching.Memory NuGet package as well.</span></span>

<span data-ttu-id="df7ad-299">서비스를 추가 하면 요청 IMemoryCache 종속성 주입을 통해 고 캐시에 액세스 해야 할 때마다 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-299">Once you've added the service, you request IMemoryCache via dependency injection wherever you need to access the cache.</span></span> <span data-ttu-id="df7ad-300">이 예제에서는 CachedCatalogService를 사용 하는 프록시 (또는 Decorator) 디자인 패턴의 ICatalogService에 대 한 액세스 제어 (또는 동작을 추가) 하 여 대체 구현을 제공 하 여 기본 CatalogService 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-300">In this example, the CachedCatalogService is using the Proxy (or Decorator) design pattern, by providing an alternative implementation of ICatalogService that controls access to (or adds behavior to) the underlying CatalogService implementation.</span></span>

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

<span data-ttu-id="df7ad-301">서비스의 캐시 된 버전을 사용 하지만 여전히 CatalogService의 생성자에 필요한 인스턴스를 가져올 서비스를 허용 하도록 응용 프로그램을 구성 하려면 ConfigureServices에 다음 추가.</span><span class="sxs-lookup"><span data-stu-id="df7ad-301">To configure the application to use the cached version of the service, but still allow the service to get the instance of CatalogService it needs in its constructor, you would add the following in ConfigureServices:</span></span>

```csharp
services.AddMemoryCache();
services.AddScoped<ICatalogService, CachedCatalogService>();
services.AddScoped<CatalogService>();
```

<span data-ttu-id="df7ad-302">이 위치를 카탈로그 데이터를 가져올 데이터베이스 호출만 가능 합니다 분당 한 번이 아닌 모든 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-302">With this in place, the database calls to fetch the catalog data will only be made once per minute, rather than on every request.</span></span> <span data-ttu-id="df7ad-303">사이트 트래픽에 따라 데이터베이스 및 현재이 서비스에서 노출 하는 쿼리의 모든 3에 의존 하는 홈 페이지에 대 한 평균 페이지 로드 시간에 수행 된 쿼리의 수에 매우 중요 한 영향을 미칠 수 있습니다이 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-303">Depending on the traffic to the site, this can have a very significant impact on the number of queries made to the database, and the average page load time for the home page that currently depends on all three of the queries exposed by this service.</span></span>

<span data-ttu-id="df7ad-304">캐싱을 구현 되는 경우 발생할 수 있는 문제는 *오래 된 데이터* – 원본 않지만 최신 버전에서 변경 된 데이터를 캐시에 남아 즉, 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-304">An issue that arises when caching is implemented is *stale data* – that is, data that has changed at the source but an out of date version remains in the cache.</span></span> <span data-ttu-id="df7ad-305">이 문제를 완화 하는 간단한 방법이 되므로 사용 중인 응용 프로그램에 대 한 데이터가 캐시 된 길이 확장 하는 데 제한 장점이 작은 캐시 기간을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-305">A simple way to mitigate this issue is to use small cache durations, since for a busy application there is limited additional benefit to extending the length data is cached.</span></span> <span data-ttu-id="df7ad-306">예를 들어 단일 데이터베이스 쿼리에 대해 수행 하는 페이지와 초당 10 회를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-306">For example, consider a page that makes a single database query, and is requested 10 times per second.</span></span> <span data-ttu-id="df7ad-307">1 분 동안 캐시 되는이 페이지, 수행한 분당 1, 99.8% 감소를 600를 삭제 하는 데이터베이스 쿼리 수에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-307">If this page is cached for one minute, it will result in the number of database queries made per minute to drop from 600 to 1, a reduction of 99.8%.</span></span> <span data-ttu-id="df7ad-308">대신 캐시 기간 1 시간 동안 수행 된, 전체 감소는 99.997% 하지만 이제 유효 하지 않은 데이터의 가능성 및 잠재적인 나이 둘 다 크게 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-308">If instead the cache duration were made one hour, the overall reduction would be 99.997%, but now the likelihood and potential age of stale data are both increased dramatically.</span></span>

<span data-ttu-id="df7ad-309">다른 방법은 사전 포함 된 데이터 업데이트 될 때 캐시 항목을 제거 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-309">Another approach is to proactively remove cache entries when the data they contain is updated.</span></span> <span data-ttu-id="df7ad-310">해당 키를 식별 하는 경우 모든 개별 항목을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-310">Any individual entry can be removed if its key is known:</span></span>

```csharp
_cache.Remove(cacheKey);
```

<span data-ttu-id="df7ad-311">캐시 항목을 업데이트 하기 위한 기능을 노출 하는 응용 프로그램에 업데이트를 수행 하는 코드에서 해당 캐시 항목을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-311">If your application exposes functionality for updating entries that it caches, you can remove the corresponding cache entries in your code that performs the updates.</span></span> <span data-ttu-id="df7ad-312">경우에 따라 특정 데이터 집합에 종속 된 여러 다른 항목이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-312">Sometimes there may be many different entries that depend on a particular set of data.</span></span> <span data-ttu-id="df7ad-313">이 경우에 CancellationChangeToken를 사용 하 여 캐시 항목 간의 종속성을 만들 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-313">In that case, it can be useful to create dependencies between cache entries, by using a CancellationChangeToken.</span></span> <span data-ttu-id="df7ad-314">CancellationChangeToken와 토큰을 취소 하 여 여러 캐시 항목을 한 번에 만료 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df7ad-314">With a CancellationChangeToken, you can expire multiple cache entries at once by cancelling the token.</span></span>

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
<span data-ttu-id="df7ad-315">[이전] [다음] (test-asp-net-core-mvc-apps.md) (develop-asp-net-core-mvc-apps.md)</span><span class="sxs-lookup"><span data-stu-id="df7ad-315">[Previous] (develop-asp-net-core-mvc-apps.md) [Next] (test-asp-net-core-mvc-apps.md)</span></span>
