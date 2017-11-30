---
title: "단순 데이터 기반 CRUD 마이크로 서비스 만들기"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 단순 데이터 기반 CRUD 마이크로 서비스 만들기"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: b814d344f2c78e7cf57f9e2896cf1d6b52db38d9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="creating-a-simple-data-driven-crud-microservice"></a>단순 데이터 기반 CRUD 마이크로 서비스 만들기

이 섹션 윤곽선 방법 간단한 만들기를 수행 하는 마이크로 서비스 만듭니다, 읽기, 업데이트 및 삭제 (CRUD) 작업을 데이터 원본.

## <a name="designing-a-simple-crud-microservice"></a>간단한 CRUD 마이크로 서비스를 디자인합니다.

디자인 관점에서 이러한 종류의 컨테이너 화 된 마이크로 서비스는 매우 간단 합니다. 아마도 문제를 해결 하는 것은 간단 하거나 구현만 개념 증명을 가장 합니다.

![](./media/image4.png)

**그림 8-4**합니다. 간단한 CRUD microservices에 대 한 내부 디자인

이러한 종류의 단순 데이터 드라이브 서비스 예 eShopOnContainers 샘플 응용 프로그램에서 카탈로그 마이크로 서비스입니다. 이 유형의 서비스 채널의 데이터 모델, 해당 비즈니스 논리 및 해당 데이터 액세스 코드에 대 한 클래스를 포함 하는 단일 ASP.NET Core 웹 API 프로젝트에서 모든 기능을 구현 합니다. 또한 (다른 컨테이너와 개발/테스트 용도로), SQL Server에서 실행 되는 데이터베이스에 관련된 데이터를 저장 하 이지만 그림 8-5와 같이 모든 일반 SQL Server 호스트 일 수도 있습니다.

![](./media/image5.png)

**그림 8-5**합니다. 단순 데이터 구동/CRUD 마이크로 서비스 디자인

이러한 종류의 서비스를 개발 하는 경우 하기만 하면 [ASP.NET Core](https://docs.microsoft.com/aspnet/core/) 와 같은 데이터 액세스 API 또는 ORM [Entity Framework Core](https://docs.microsoft.com/ef/core/index)합니다. 생성할 수도 있습니다 [Swagger](http://swagger.io/) 메타 데이터를 통해 자동으로 [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) 하려면 다음 섹션에 설명 된 대로 서비스를 제공 하는 기능에 대 한 설명을 제공 합니다.

Docker 컨테이너 내에서 SQL Server가 모든 종속성 가질 수 있으므로 개발 환경에 대 한 높으면와 같은 데이터베이스 서버를 실행 하 고 클라우드 또는 온-프레미스 데이터베이스를 프로 비전 하지 않고도 실행 하는 note 합니다. 테스트를 실행 하는 통합 하는 경우에 매우 유용 합니다. 그러나 프로덕션 환경에 대 한 데이터베이스 서버 컨테이너에서 실행 권장 되지 않습니다, 하므로 일반적으로 해당 접근 방식의 고가용성 발생 하지 않습니다. Azure에서 프로덕션 환경에 대 한 Azure SQL DB 나 고가용성 및 높은 확장성을 제공할 수 있는 기타 데이터베이스 기술을 사용 하는 것이 좋습니다. 예를 들어 NoSQL 방법을 DocumentDB를 선택할 수 있습니다.

마지막으로, Dockerfile 및 docker compose.yml 메타 데이터 파일을 편집 하 여 구성할 수 있습니다이 컨테이너의 이미지를 만들 수는 방법-어떤 기본 이미지 것을 사용 및 설정 예: 내부 및 외부 이름 및 TCP 포트를 디자인 합니다. 

## <a name="implementing-a-simple-crud-microservice-with-aspnet-core"></a>ASP.NET Core 포함 간단한 CRUD 마이크로 서비스를 구현합니다.

.NET Core 및 Visual Studio를 사용 하 여 간단한 CRUD 마이크로 서비스를 구현 하려면 먼저를 만듭니다 (실행.NET Core Linux Docker 호스트에서 실행할 수 있도록), 간단한 ASP.NET Core 웹 API 프로젝트에 표시 된 그림 8-6으로 합니다.

  ------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------
  ![](./media/image6.png)   ![](./media/image7.png)
  ------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------

**그림 8-6**합니다. Visual Studio에서 ASP.NET Core 웹 API 프로젝트 만들기

프로젝트를 만든 후 엔터티 프레임 워크 API 또는 다른 API를 사용 하 여 다른 Web API 프로젝트에서와 MVC 컨트롤러를 구현할 수 있습니다. EShopOnContainers.Catalog.API 프로젝트 있습니다 수는 것을 확인할 해당 마이크로 서비스에 대 한 주요 종속성 자체 ASP.NET Core, Entity Framework 및 Swashbuckle, 그림 8-7에 표시 된 것 처럼 합니다.

![](./media/image8.PNG)

**그림 8-7**합니다. 간단한 CRUD 웹 API 마이크로 서비스의 종속성

### <a name="implementing-crud-web-api-services-with-entity-framework-core"></a>Entity Framework Core를 사용 하 여 CRUD 웹 API 서비스를 구현합니다.

Entity Framework (EF) Core, 확장 가능한 경량 및 플랫폼 버전의 인기 있는 Entity Framework 데이터 액세스 기술을 합니다. EF 코어는.NET 개발자가.NET 개체를 사용 하 여 데이터베이스를 사용할 수 있도록 개체 관계형 매퍼 (ORM)입니다.

카탈로그 마이크로 서비스 데이터베이스 Linux Docker 이미지에 대 한 SQL Server를 사용 하 여 컨테이너에서 실행 되 고 있어서 EF 및 SQL Server 공급자를 사용 합니다. 그러나 데이터베이스 Windows 온-프레미스 또는 Azure SQL DB와 같은 모든 SQL Server에 배포 될 수 없습니다. 변경 해야 하는 유일한 항목은 ASP.NET Web API 마이크로 서비스에 연결 문자열입니다.

#### <a name="add-entity-framework-core-to-your-dependencies"></a>Entity Framework Core 종속성 추가

이 경우 SQL Server에서 사용할 Visual Studio IDE 내에서 또는 NuGet 콘솔을 사용 하려는 데이터베이스 공급자에 대 한 NuGet 패키지를 설치할 수 있습니다. 다음 명령을 사용합니다.

```
  Install-Package Microsoft.EntityFrameworkCore.SqlServer
```

#### <a name="the-data-model"></a>데이터 모델

EF 코어 데이터 액세스 모델을 사용 하 여 수행 됩니다. 모델은 엔터티 클래스 및 파생된 컨텍스트를 쿼리하고 데이터를 저장할 수 있도록 데이터베이스와 세션을 나타내는으로 이루어져 있습니다. 기존 데이터베이스에서 모델을 생성, 수동으로 코드는 모델 데이터베이스와 일치 하도록 하거나 사용할 수 있습니다 EF 마이그레이션을 모델에서 데이터베이스를 만듭니다 (및 그 시간이 지남에 따라 변경 모델에 따라 엔터티와 관계도 개발). 카탈로그 마이크로 서비스에 대 한 마지막 접근 방식을 사용 합니다. 다음 코드 예제는 간단한 일반 이전 CLR 개체에서 CatalogItem 엔터티 클래스의 예제를 볼 수 있습니다 ([POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)) 엔터티 클래스입니다.

```csharp
public class CatalogItem
{
    public int Id { get; set; }
    public string Name { get; set; }
    public string Description { get; set; }
    public decimal Price { get; set; }
    public string PictureUri { get; set; }
    public int CatalogTypeId { get; set; }
    public CatalogType CatalogType { get; set; }
    public int CatalogBrandId { get; set; }
    public CatalogBrand CatalogBrand { get; set; }
    public CatalogItem() { }
}
```

데이터베이스와 세션을 나타내는 DbContext 해야 합니다. 다음 예제와 같이 카탈로그 마이크로 서비스에 대 한 CatalogContext 클래스 DbContext 기본 클래스에서 파생:

```csharp
public class CatalogContext : DbContext
{
    public CatalogContext(DbContextOptions<CatalogContext> options) : base(options)
    {
    }

    public DbSet<CatalogItem> CatalogItems { get; set; }
    public DbSet<CatalogBrand> CatalogBrands { get; set; }
    public DbSet<CatalogType> CatalogTypes { get; set; }

    // Additional code ...

}
```

DbContext 구현에 추가 코드를 포함할 수 있습니다. 예를 들어 샘플 응용 프로그램에서 OnModelCreating 메서드에에서 있는 데이터베이스에 액세스 하려고 처음으로 샘플 데이터를 자동으로 채우려고 CatalogContext 클래스입니다. 이 메서드는 데모 데이터에 유용 합니다. 다양 한 기타 포함 된 개체/데이터베이스 엔터티 매핑을 사용자 지정 하려면 OnModelCreating 메서드를 사용할 수도 있습니다 [EF 확장 지점을](https://blogs.msdn.microsoft.com/dotnet/2016/09/29/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/)합니다.

OnModelCreating에 대 한 세부 정보가 추가로 표시 수는 [Entity Framework Core와 인프라를 지 속성 계층 구현](#implementing_infrastructure_persistence) 이 가이드의 뒷부분에 나오는 섹션.

##### <a name="querying-data-from-web-api-controllers"></a>Web API 컨트롤러에서 데이터를 쿼리

다음 예제와 같이 엔터티 클래스의 인스턴스는 일반적으로 언어 통합 쿼리 (LINQ)를 사용 하 여 데이터베이스에서 검색 한:

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    private readonly CatalogContext _catalogContext;
    private readonly CatalogSettings _settings;
    private readonly ICatalogIntegrationEventService _catalogIntegrationEventService;

    public CatalogController(CatalogContext context,
        IOptionsSnapshot<CatalogSettings> settings,
        ICatalogIntegrationEventService catalogIntegrationEventService)
    {
        _catalogContext = context ?? throw new ArgumentNullException(nameof(context));
        _catalogIntegrationEventService = catalogIntegrationEventService ??
           throw new ArgumentNullException(nameof(catalogIntegrationEventService));
        _settings = settings.Value;
        ((DbContext)context).ChangeTracker.QueryTrackingBehavior = QueryTrackingBehavior.NoTracking;
    }

    // GET api/v1/[controller]/items[?pageSize=3&pageIndex=10]
    [HttpGet]
    [Route("[action]")]
    public async Task<IActionResult> Items([FromQuery]int pageSize = 10,
    [FromQuery]int pageIndex = 0)
    {
        var totalItems = await _catalogContext.CatalogItems
            .LongCountAsync();
        var itemsOnPage = await _catalogContext.CatalogItems
            .OrderBy(c => c.Name)
            .Skip(pageSize * pageIndex)
            .Take(pageSize)
            .ToListAsync();
        itemsOnPage = ChangeUriPlaceholder(itemsOnPage);
        var model = new PaginatedItemsViewModel<CatalogItem>(
            pageIndex, pageSize, totalItems, itemsOnPage);
        return Ok(model);
    } 

    //...
}
```

##### <a name="saving-data"></a>데이터 저장

데이터 생성, 삭제 및 엔터티 클래스의 인스턴스를 사용 하 여 데이터베이스에서 수정 합니다. 다음 하드 코딩 된 예제 (이 경우 모의 데이터) Web API 컨트롤러에 같은 코드를 추가할 수 있습니다.

```csharp
var catalogItem = new CatalogItem() {CatalogTypeId=2, CatalogBrandId=2,
   Name="Roslyn T-Shirt", Price = 12};
_context.Catalog.Add(catalogItem);
_context.SaveChanges();
```

##### <a name="dependency-injection-in-aspnet-core-and-web-api-controllers"></a>ASP.NET Core 및 Web API 컨트롤러의 종속성 주입

ASP.NET Core 즉시 DI (Dependency Injection)를 사용할 수 있습니다. 원하는 경우 ASP.NET Core 인프라에 기본 IoC 컨테이너를 연결할 수 있지만 제 3 자 Inversion of Control (IoC) 컨테이너를 설정할 필요가 없습니다. 이 경우 직접 필요한 EF DBContext 또는 컨트롤러 생성자를 통해 추가 저장소 주입할 수를 의미 합니다. CatalogController 클래스의 위의 예제에서는 CatalogContext 형식의 개체와 다른 개체 CatalogController 생성자를 통해 삽입는 했습니다.

웹 API 프로젝트에을 설정 하는 중요 한 구성이 서비스의 IoC 컨테이너에는 DbContext 클래스를 등록 합니다. 일반적으로 이렇게 하면 시작 클래스에 서비스를 호출 하 여 합니다. 다음 예제와 같이 ConfigureServices 메서드에 AddDbContext 메서드:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddDbContext<CatalogContext>(options =>
    {
        options.UseSqlServer(Configuration["ConnectionString"],
        sqlServerOptionsAction: sqlOptions =>
        {
           sqlOptions.
               MigrationsAssembly(
               typeof(Startup).
               GetTypeInfo().
               Assembly.
               GetName().Name);

           //Configuring Connection Resiliency:
           sqlOptions.
               EnableRetryOnFailure(maxRetryCount: 5,
               maxRetryDelay: TimeSpan.FromSeconds(30),
               errorNumbersToAdd: null);

       });

       // Changing default behavior when client evaluation occurs to throw.
       // Default in EFCore would be to log warning when client evaluation is done.
       options.ConfigureWarnings(warnings => warnings.Throw(
           RelationalEventId.QueryClientEvaluationWarning));
   });

  //...

}
```

### <a name="additional-resources"></a>추가 리소스

-   **데이터 쿼리**
    [*https://docs.microsoft.com/ef/core/querying/index*](https://docs.microsoft.com/ef/core/querying/index)

-   **데이터 저장**
    [*https://docs.microsoft.com/ef/core/saving/index*](https://docs.microsoft.com/ef/core/saving/index)

## <a name="the-db-connection-string-and-environment-variables-used-by-docker-containers"></a>Docker 컨테이너에서 사용 하는 DB 연결 문자열 및 환경 변수

ASP.NET Core 설정을 사용 하 여 및 다음 예제와 같이 settings.json 파일에 ConnectionString 속성을 추가할 수 있습니다.

```csharp
{
    "ConnectionString": "Server=tcp:127.0.0.1,5433;Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word",
    "ExternalCatalogBaseUrl": "http://localhost:5101",
    "Logging": {
        "IncludeScopes": false,
        "LogLevel": {
            "Default": "Debug",
            "System": "Information",
            "Microsoft": "Information"
        }
    }
}
```

Settings.json 파일 ConnectionString 속성에 대 한 또는 다른 속성에 대 한 기본값을 가질 수 있습니다. 그러나 이러한 속성은 docker compose.override.yml 파일에서 지정 하는 환경 변수 값에 의해 재정의 됩니다.

Docker compose.yml 또는 docker compose.override.yml 파일에서 초기화할 수 있습니다 이러한 환경 변수 있으므로 해당 Docker는 설정으로 운영 체제 환경 변수로, 다음 docker compose.override.yml 파일 (연결에에서 표시 된 것 처럼 이 예제에서는 문자열 및 다른 줄에서 줄 바꿈이 되지만 자신의 파일에 줄 바꿈을 하지 것).

```yml
# docker-compose.override.yml

#
catalog.api:
  environment:
    - ConnectionString=Server=sql.data;Database=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word
    - ExternalCatalogBaseUrl=http://10.0.75.1:5101
    #- ExternalCatalogBaseUrl=http://dockerhoststaging.westus.cloudapp.azure.com:5101
  
  ports:
    - "5101:5101"
```

솔루션 수준에서 docker compose.yml 파일은 뿐만 프로젝트 또는 마이크로 서비스 수준에서 구성 파일 보다 좀 더 융통적 아니라 더 안전한도 합니다. 고려 이진 파일과 구성 파일에서 Dockerfile을 포함 하 여, 각 마이크로 서비스에 대 한 파일 마이크로 서비스 당 작성 하는 Docker 이미지 docker compose.yml는 포함 되지 않아야 합니다. Docker compose.yml 파일; 응용 프로그램과 함께 배포 되지 않은 하지만 배포 시에만 사용 됩니다. 따라서 (없이 암호화 된 값) 환경 변수 값을 해당 docker compose.yml 파일에 배치 합니다.이 코드와 함께 배포 되는 일반.NET 구성 파일에 해당 값을 배치 하는 보다 더 안전 합니다.

구성을 사용 하 여 사용자 코드에서 해당 값을 가져올 수는 마지막으로,\["ConnectionString"\]ConfigureServices 메서드는 이전 코드 예제에서에 나온 것 처럼 합니다.

하지만, 프로덕션 환경에 대 한 연결 문자열 처럼 비밀 정보를 저장 하는 방법에는 추가 방법을 탐색기 필요할 수 있습니다. 일반적으로 관리 되 선택한 orchestrator 사용자 할 수 있는 처럼 [암호 관리 docker는 Docker Swarm](https://docs.docker.com/engine/swarm/secrets/)합니다.

### <a name="implementing-versioning-in-aspnet-web-apis"></a>ASP.NET 웹 Api의 버전 관리 구현

비즈니스 요구 사항 변화에 따른 리소스의 새 컬렉션에 추가 될 수 있습니다, 리소스 간의 관계 변경 될 수 있습니다 및 리소스에 있는 데이터의 구조를 수정할 수 있습니다. 새 요구 사항을 처리 하는 Web API를 업데이트는 비교적 간단 하므로 프로세스 않지만 웹 API를 사용 하는 클라이언트 응용 프로그램을 이러한 변경 내용이 있는 효과 고려해 야 합니다. 디자인 및 구현 웹 API를 개발자에 해당 API에 대 한 모든 권한을으로 개발자는 동일한 수준의 원격으로 작동 하는 타사 조직 에서도 빌드할 수 있는 클라이언트 응용 프로그램에 대 한 제어 필요가 없습니다.

버전 관리 기능 및 노출 하는 리소스를 나타내는 웹 API를 수 있습니다. 클라이언트 응용 프로그램이 기능 또는 리소스의 특정 버전에 대 한 요청을 제출한 다음 수 있습니다. 버전 관리를 구현 하는 방법은 몇 가지가 있습니다.

-   URI 버전 관리

-   쿼리 문자열 버전 관리

-   헤더 버전 관리

쿼리 문자열 및 버전 관리 URI는를 구현 하는 가장 간단한입니다. 버전 관리 헤더에 있는 좋은 방법입니다. 그러나 같이 명시적 없고 간단 하 게 URI 버전 관리 헤더 버전 관리 합니다. URL 버전 관리는 간단 하 고 가장 명시적 이므로 eShopOnContainers 예제 응용 프로그램 URI 버전 관리를 사용 합니다.

EShopOnContainers 샘플 응용 프로그램에서와 같이 URI 버전 관리를 사용 웹 API를 수정 하거나 리소스의 스키마를 변경할 때마다 버전 번호에 추가한 각 리소스에 대 한 URI입니다. 기존 Uri는 이전과 마찬가지로 요청 된 버전과 일치 하는 스키마를 준수 하는 리소스를 반환 하도록 계속 해야 합니다.

다음 코드 예제와 같이 버전 URI에서 명시적으로 버전을 낮추는 Web API에서 경로 특성을 사용 하 여 설정할 수 있습니다 (이 경우 v1).

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    // Implementation ...
```

이 버전 관리 메커니즘은 간단 하 고 요청을 라우팅하는 적절 한 끝점을 서버에 따라 달라 집니다. 그러나 보다 복잡 한 버전 관리 및 REST를 사용 하는 경우에 가장 좋은 방법은 해야 하이퍼미디어를 사용 하 고 구현 하기 [HATEOAS (응용 프로그램 상태 엔진으로 하이퍼텍스트)](https://docs.microsoft.com/azure/architecture/best-practices/api-design#using-the-hateoas-approach-to-enable-navigation-to-related-resources)합니다.

### <a name="additional-resources"></a>추가 리소스

-   **Scott Hanselman 합니다. ASP.NET Core RESTful 웹 API 버전 관리를 쉽게**
    [*http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx*](http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx)

-   **버전 관리는 RESTful 웹 API**

    [*https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api*](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)

-   **로 Fielding 합니다. 버전 관리, 하이퍼미디어, 및 REST**
    [*https://www.infoq.com/articles/roy-fielding-on-versioning*](https://www.infoq.com/articles/roy-fielding-on-versioning)

## <a name="generating-swagger-description-metadata-from-your-aspnet-core-web-api"></a>ASP.NET Core 웹 API에서 Swagger 설명 메타 데이터를 생성합니다. 

[Swagger](http://swagger.io/) 디자인, 빌드, 문서에 자주 사용 되는 오픈 소스 프레임 워크 하는 데 유용한 도구 중 큰 생태계에서 지원 되 고 RESTful Api를 사용 합니다. Api 설명 메타 데이터 도메인에 대 한 표준 확대 되 고 있습니다. 모든 종류의 데이터 기반 microservices 또는 더 높은 수준의 (다음 섹션에서 설명한) 하는 대로 microservices 도메인 기반 마이크로 서비스 Swagger 설명 메타 데이터를 포함 해야 합니다.

Swagger의 핵심은 JSON 또는 YAML 파일에서 API 설명 메타 데이터는 Swagger 사양입니다. 사양에 대 한 모든 리소스와 쉽게 개발, 검색 및 통합에 대 한 두 사람이 및 machine readable 형식에서 작업에 자세히 설명 하 여 API RESTful 계약을 만듭니다.

사양은 OpenAPI 사양 (OAS)의 기본 및 RESTful 인터페이스를 정의 하는 방식을 표준화 하는 열기, 투명 및 공동 작업 커뮤니티에서 개발 됩니다.

서비스의 검색 방법을 그 기능 파악 하는 방법에 대 한 구조를 정의 합니다. 자세한 내용은 Swagger 사이트 참조 웹 편집기 및 Spotify, Uber, 여유 시간 및 Microsoft과 같은 회사에서 Swagger 사양의 예제를 포함 하 여 (<http://swagger.io>).

### <a name="why-use-swagger"></a>Swagger를 사용 하는 이유는?

Api에 대 한 Swagger 메타 데이터를 생성 하는 주된 이유는 다음과 같습니다.

**자동으로 사용 하 고 프로그램 Api를 통합 하는 다른 제품에 대 한 기능**합니다. 다양 한 제품 및 [고급 도구](http://swagger.io/commercial-tools/) 많은 및 [라이브러리 및 프레임 워크](http://swagger.io/open-source-integrations/) Swagger를 지원 합니다. Microsoft는 높은 수준의 제품 및 자동으로 다음과 같은 Swagger 기반 Api를 사용할 수 있는 도구에 있습니다.

-   [AutoRest](https://github.com/Azure/AutoRest)합니다. Swagger를 호출 하기 위한.NET 클라이언트 클래스를 자동으로 생성할 수 있습니다. This

-   CLI에서 도구를 사용할 수 있습니다 및 통합 하는 또한 Visual Studio와 함께 GUI 통해 쉽게 사용 하도록 합니다.

-   [Microsoft Flow](https://flow.microsoft.com/en-us/)합니다. 자동으로 수행할 수 [사용 및 API 통합](https://flow.microsoft.com/en-us/blog/integrating-custom-api/) 높은 수준의 Microsoft Flow 워크플로 없이 프로그래밍 기술이 필요 합니다.

-   [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)합니다. API를 자동으로 사용할 수 있는 [PowerApps 모바일 앱](https://powerapps.microsoft.com/en-us/blog/register-and-use-custom-apis-in-powerapps/) 사용 하 여 빌드한 [PowerApps Studio](https://powerapps.microsoft.com/en-us/guided-learning/learning-powerapps-parts/), 필요한 프로그래밍 기술이 사용 합니다.

-   [Azure 앱 서비스 논리 앱](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps)합니다. 자동으로 수행할 수 [사용 및 API 앱에 통합 Azure 앱 서비스 논리](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api)와 프로그래밍 기술이 필요 합니다.

**API 설명서를 자동으로 생성 하는 기능**합니다. 복잡 한 마이크로 서비스 기반 응용 프로그램을 같은 대규모 RESTful Api를 만들 때 요청 및 응답 페이로드에 사용 되는 서로 다른 데이터 모델을 여러 끝점을 처리 해야 합니다. 적절 한 설명서 및 Swagger와 얻게을 solid API 탐색기 것은 API와 개발자가 채택의 성공에 대 한 키입니다.

Swagger의 메타 데이터 뿐만 아니라 Api를 사용 및 연결 하는 방법을 이해 하는 위해 Microsoft Flow, PowerApps, 및 Azure 논리 앱 사용 하는 것입니다.

### <a name="how-to-automate-api-swagger-metadata-generation-with-the-swashbuckle-nuget-package"></a>Swashbuckle NuGet 패키지와 API Swagger 메타 데이터 생성을 자동화 하는 방법

수동으로 (JSON 또는 파일 내에서 YAML) Swagger 메타 데이터를 생성 하면 지루한 작업 될 수 있습니다. 사용 하 여 ASP.NET 웹 API 서비스의 API 검색 자동화할 수 있습니다는 [Swashbuckle NuGet 패키지](http://aka.ms/swashbuckledotnetcore) 를 동적으로 API Swagger 메타 데이터를 생성 합니다.

Swashbuckle는 ASP.NET Web API 프로젝트에 대 한 Swagger 메타 데이터를 자동으로 생성합니다. ASP.NET Core 웹 API 프로젝트와 기존의 ASP.NET 웹 API 및 Azure API 앱, Azure 모바일 앱, ASP.NET에 따라 Azure 서비스 패브릭 microservices 등의 다른 버전을 지원 합니다. 또한 참조 응용 프로그램에서 같이 컨테이너에 배포 하는 일반 웹 API를 지원 합니다.

API 탐색기 및 Swagger Swashbuckle 결합 또는 [swagger ui](https://github.com/swagger-api/swagger-ui) API 소비자에 대 한 풍부한 검색 및 설명서 경험할 수 있도록 합니다. Swashbuckle는 Swagger 메타 데이터 생성기 엔진 외에도 자동으로 제공할 서비스를 Swashbuckle가 설치 되 면 있는 swagger-ui의 포함된 된 버전을 포함 되어 있습니다.

즉, 개발자가 API를 사용 하는 UI는 좋은 검색 API를 보충할 수 있습니다. 자동으로 생성 되므로, API 구축에 전념할 수 있도록 매우 적은 양의 코드 및 유지 관리 해야 합니다. API 탐색기에 대 한 결과 같은 그림 8-8을 찾습니다.

![](./media/image9.png)

**그림 8-8**합니다. Swagger 메타 데이터를 기반으로 Swashbuckle API 탐색기-eShopOnContainers 마이크로 서비스 카탈로그

API 탐색기 여기에서 가장 중요 한 사항은 않습니다. Swagger 메타 데이터에 자체를 설명할 수 있는 웹 API를 사용 하는 후 Swagger 기반 도구를 다 수의 플랫폼 대상으로 지정할 수 있는 클라이언트 프록시 클래스 코드 생성기를 포함 하 여에서 원활 하 게 API는 사용할 수 있습니다. 예를 들어 듯이 [AutoRest](https://github.com/Azure/AutoRest) .NET 클라이언트 클래스를 자동으로 생성 합니다. 이지만 추가 도구와 [swagger codegen](https://github.com/swagger-api/swagger-codegen) 도 사용할 수 있는 API 클라이언트의 코드 생성 라이브러리, 서버 스텁 및 설명서 자동으로 됩니다.

현재 두 개의 NuGet 패키지 Swashbuckle 구성: Swashbuckle.SwaggerGen 및 Swashbuckle.SwaggerUi 합니다. 전자 API 구현에서 직접 하나 이상의 Swagger 문서를 생성 한 JSON 끝점으로 노출 하는 기능을 제공 합니다. 후자는 포함 된 버전의 응용 프로그램에서 제공 하 고 API를 설명 하기 위해 생성 된 Swagger 문서 기반의 수 있는 swagger ui 도구를 제공 합니다. 그러나 최신 버전의 Swashbuckle 겹칠 Swashbuckle.AspNetCore metapackage와 합니다.

.NET Core Web API 프로젝트에 대 한 사용 하 여 필요 하면 [Swashbuckle.AspNetCore](https://www.nuget.org/packages/Swashbuckle.AspNetCore/1.0.0) 버전 1.0.0 이후 버전입니다.

웹 API 프로젝트에 이러한 NuGet 패키지를 설치한 후 다음 코드 에서처럼 시작 클래스에 Swagger를 구성 해야 합니다.

```csharp
public class Startup
{
    public IConfigurationRoot Configuration { get; }
    // Other startup code...

    public void ConfigureServices(IServiceCollection services)
    {
        // Other ConfigureServices() code...
        services.AddSwaggerGen();
        services.ConfigureSwaggerGen(options =>
        {
            options.DescribeAllEnumsAsStrings();
            options.SingleApiVersion(new Swashbuckle.Swagger.Model.Info()
            {
                Title = "eShopOnContainers - Catalog HTTP API",
                Version = "v1",
                Description = "The Catalog Microservice HTTP API",
                TermsOfService = "eShopOnContainers terms of service"
            });
        });
        // Other ConfigureServices() code...
    }

    public void Configure(IApplicationBuilder app,
        IHostingEnvironment env,
        ILoggerFactory loggerFactory)
    {
        // Other Configure() code...
        // ...
        app.UseSwagger()
            .UseSwaggerUi();
    }
}
```

이 작업이 완료 되 면 응용 프로그램을 시작할 수 있으며 이와 같은 Url을 사용 하 여 다음 JSON Swagger 및 UI 끝점 찾아보기:

```json
  http://<your-root-url>/swagger/v1/swagger.json
  
  http://<your-root-url>/swagger/ui
```

이전에 언급 했 듯이 http://와 같은 URL에 대 한 Swashbuckle에서 만든 생성 된 UI&lt;루트 url your &gt; /swagger/ui입니다. 그림 8-9 API 메서드를 테스트 하는 방법을 참조 수도 있습니다.

![](./media/image10.png)

**그림 8-9**합니다. Swashbuckle UI 카탈로그/항목 API 메서드를 테스트 합니다.

그림 8-10 eShopOnContainers 마이크로 서비스에서 생성 된 JSON Swagger 메타 데이터를 보여줍니다 (변수인 아래 도구 사용 하는 것) 요청 하는 경우 &lt;루트 url your&gt;/swagger/v1/swagger.json을 사용 하 여 [우체부](https://www.getpostman.com/).

![](./media/image11.png)

**그림 8-10**합니다. Swagger JSON 메타 데이터

매우 간단 합니다. 및 API에 더 많은 기능을 추가 하면 Swagger 메타 데이터가 자동으로 생성 되므로 커집니다.

### <a name="additional-resources"></a>추가 리소스

-   **ASP.NET 웹 API 도움말 페이지 Swagger를 사용 하 여**
    [*https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger*](https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger)


>[!div class="step-by-step"]
[이전] (마이크로 서비스-응용 프로그램-design.md) [다음] (다중-container-응용 프로그램-docker-compose.md)
