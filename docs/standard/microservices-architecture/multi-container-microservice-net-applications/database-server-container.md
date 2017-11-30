---
title: "컨테이너 실행 하는 데이터베이스 서버를 사용 하 여"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 컨테이너 실행 하는 데이터베이스 서버를 사용 하 여"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 7e5f33c4e7edf9d0d4551c5125976fcb8fda392f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="using-a-database-server-running-as-a-container"></a><span data-ttu-id="2ae49-104">컨테이너 실행 하는 데이터베이스 서버를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="2ae49-104">Using a database server running as a container</span></span>

<span data-ttu-id="2ae49-105">온-프레미스 클러스터에서 또는 Azure SQL DB와 같은 클라우드 서비스 PaaS의에서 일반 독립 실행형 서버에 데이터베이스 (SQL Server, PostgreSQL, MySQL 등)를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-105">You can have your databases (SQL Server, PostgreSQL, MySQL, etc.) on regular standalone servers, in on-premises clusters, or in PaaS services in the cloud like Azure SQL DB.</span></span> <span data-ttu-id="2ae49-106">그러나 개발 및 테스트 환경에 대 한 컨테이너로 서 실행 되는 프로그램 데이터베이스에 있는 단순히 실행 되 고 한 외부 종속성이 없기 때문에 편리한는 docker 구성 명령은 전체 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-106">However, for development and test environments, having your databases running as containers is convenient, because you do not have any external dependency, and simply running the docker-compose command starts the whole application.</span></span> <span data-ttu-id="2ae49-107">가 있으면 컨테이너와 해당 데이터베이스도 통합 테스트에 매우 유용 하므로 데이터베이스는 컨테이너에서 시작 되 고 테스트는 예측 가능성이 더욱 뛰어난 될 수 있도록 항상 동일한 샘플 데이터로 채워진 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-107">Having those databases as containers is also great for integration tests, because the database is started in the container and is always populated with the same sample data, so tests can be more predictable.</span></span>

### <a name="sql-server-running-as-a-container-with-a-microservice-related-database"></a><span data-ttu-id="2ae49-108">마이크로 서비스와 관련 된 데이터베이스와 컨테이너를 실행 중인 SQL Server</span><span class="sxs-lookup"><span data-stu-id="2ae49-108">SQL Server running as a container with a microservice-related database</span></span>

<span data-ttu-id="2ae49-109">EShopOnContainers에 sql.data에 정의 된 명명 된 컨테이너는 [docker compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml) 는 microservices에 필요한 모든 SQL Server 데이터베이스와 Linux 용 SQL Server를 실행 하는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-109">In eShopOnContainers, there is a container named sql.data defined in the [docker-compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml) file that runs SQL Server for Linux with all the SQL Server databases needed for the microservices.</span></span> <span data-ttu-id="2ae49-110">(각 데이터베이스에 대 한 SQL Server 컨테이너 있을 만들 수 있지만 더 많은 메모리를 Docker에 할당 해야 합니다.) Microservices에 중요 한 점은 각 마이크로 서비스 소유 하 고 있음이 관련된 데이터를 따라서 SQL 데이터베이스 관련된이 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-110">(You could also have one SQL Server container for each database, but that would require more memory assigned to Docker.) The important point in microservices is that each microservice owns its related data, therefore its related SQL database in this case.</span></span> <span data-ttu-id="2ae49-111">하지만 원격 데이터베이스가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-111">But the databases can be anywhere.</span></span>

<span data-ttu-id="2ae49-112">샘플 응용 프로그램의 컨테이너를 실행할 때 실행 되는 docker compose.yml 파일에 다음 YAML 코드로 구성 된 SQL Server docker-작성을 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-112">The SQL Server container in the sample application is configured with the following YAML code in the docker-compose.yml file, which is executed when you run docker-compose up.</span></span> <span data-ttu-id="2ae49-113">참고 YAML 코드는 제네릭 docker compose.yml 파일 및 docker compose.override.yml 파일에서 구성 정보를 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-113">Note that the YAML code has consolidated configuration information from the generic docker-compose.yml file and the docker-compose.override.yml file.</span></span> <span data-ttu-id="2ae49-114">(일반적으로 분리 기반 또는 정적 정보 이미지와 관련 된 SQL Server에서에서 환경 설정 합니다.)</span><span class="sxs-lookup"><span data-stu-id="2ae49-114">(Usually you would separate the environment settings from the base or static information related to the SQL Server image.)</span></span>

```yml
sql.data:
  image: microsoft/mssql-server-linux
  environment:
    - SA_PASSWORD=your@password
    - ACCEPT_EULA=Y
  ports:
    - "5434:1433"
```

<span data-ttu-id="2ae49-115">다음 docker run 명령에는 해당 컨테이너를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-115">The following docker run command can run that container:</span></span>

```
  docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD= your@password' -p 1433:1433 -d microsoft/mssql-server-linux
```

<span data-ttu-id="2ae49-116">그러나 eShopOnContainers 같은 다중 컨테이너 응용 프로그램을 배포 하는 것이 간편 사용 하는 docker-작성 명령을 응용 프로그램에 필요한 모든 컨테이너 배포 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-116">However, if you are deploying a multi-container application like eShopOnContainers, it is more convenient to use the docker-compose up command so that it deploys all the required containers for the application.</span></span>

<span data-ttu-id="2ae49-117">처음으로이 SQL Server 컨테이너를 시작할 때 컨테이너를 제공 하는 암호와 함께 SQL Server를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-117">When you start this SQL Server container for the first time, the container initializes SQL Server with the password that you provide.</span></span> <span data-ttu-id="2ae49-118">SQL Server Management Studio, Visual Studio 또는 C와 같은 모든 일반 SQL 연결을 통해 연결 하 여 데이터베이스를 업데이트할 수는 컨테이너로 SQL Server를 실행 하 고\# 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-118">Once SQL Server is running as a container, you can update the database by connecting through any regular SQL connection, such as from SQL Server Management Studio, Visual Studio, or C\# code.</span></span>

<span data-ttu-id="2ae49-119">EShopOnContainers 응용 프로그램의 다음 섹션에 설명 된 대로 시작 시 데이터로 시드 여 샘플 데이터와 함께 각 마이크로 서비스 데이터베이스를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-119">The eShopOnContainers application initializes each microservice database with sample data by seeding it with data on startup, as explained in the following section.</span></span>

<span data-ttu-id="2ae49-120">SQL server의 컨테이너 실행 유용 하지 않습니다 방금 데모는 여기서 없을 수도 있습니다 SQL Server의 인스턴스에 대 한 액세스.</span><span class="sxs-lookup"><span data-stu-id="2ae49-120">Having SQL Server running as a container is not just useful for a demo where you might not have access to an instance of SQL Server.</span></span> <span data-ttu-id="2ae49-121">앞서 언급 한 대로 이기도 개발 및 테스트 환경에 대 한 훌륭한 쉽게 정리 하는 SQL Server 이미지에서 시작 하는 통합 테스트를 실행 하 고 시드 새 예제 데이터에서 데이터를 알 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-121">As noted, it is also great for development and testing environments so that you can easily run integration tests starting from a clean SQL Server image and known data by seeding new sample data.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="2ae49-122">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="2ae49-122">Additional resources</span></span>

-   <span data-ttu-id="2ae49-123">**Linux, Mac, 또는 Windows에서 SQL Server Docker 이미지를 실행**
    [*https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker*](https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker)</span><span class="sxs-lookup"><span data-stu-id="2ae49-123">**Run the SQL Server Docker image on Linux, Mac, or Windows**
[*https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker*](https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker)</span></span>

-   <span data-ttu-id="2ae49-124">**연결 및 sqlcmd Linux에서 SQL Server에 쿼리할**
    [*https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd*](https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd)</span><span class="sxs-lookup"><span data-stu-id="2ae49-124">**Connect and query SQL Server on Linux with sqlcmd**
[*https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd*](https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd)</span></span>

### <a name="seeding-with-test-data-on-web-application-startup"></a><span data-ttu-id="2ae49-125">웹 응용 프로그램 시작 시 테스트 데이터로 시드</span><span class="sxs-lookup"><span data-stu-id="2ae49-125">Seeding with test data on Web application startup</span></span>

<span data-ttu-id="2ae49-126">응용 프로그램이 시작 될 때 데이터베이스에 데이터를 추가, 웹 API 프로젝트의 시작 클래스에서 구성 메서드에 다음과 같은 코드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-126">To add data to the database when the application starts up, you can add code like the following to the Configure method in the Startup class of the Web API project:</span></span>

```csharp
public class Startup
{
    // Other Startup code...
    public void Configure(IApplicationBuilder app,
        IHostingEnvironment env,
        ILoggerFactory loggerFactory)
    {
        // Other Configure code...
        // Seed data through our custom class
        CatalogContextSeed.SeedAsync(app)
            .Wait();
        // Other Configure code...
    }
}
```

<span data-ttu-id="2ae49-127">사용자 지정 CatalogContextSeed 클래스에 다음 코드는 데이터를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-127">The following code in the custom CatalogContextSeed class populates the data.</span></span>

```csharp
public class CatalogContextSeed
{
    public static async Task SeedAsync(IApplicationBuilder applicationBuilder)
    {
        var context = (CatalogContext)applicationBuilder
            .ApplicationServices.GetService(typeof(CatalogContext));
        using (context)
        {
            context.Database.Migrate();
            if (!context.CatalogBrands.Any())
            {
                context.CatalogBrands.AddRange(
                    GetPreconfiguredCatalogBrands());
                await context.SaveChangesAsync();
            }
            if (!context.CatalogTypes.Any())
            {
                context.CatalogTypes.AddRange(
                    GetPreconfiguredCatalogTypes());
                await context.SaveChangesAsync();
            }
        }
    }

    static IEnumerable<CatalogBrand> GetPreconfiguredCatalogBrands()
    {
        return new List<CatalogBrand>()
       {
           new CatalogBrand() { Brand = "Azure"},
           new CatalogBrand() { Brand = ".NET" },
           new CatalogBrand() { Brand = "Visual Studio" },
           new CatalogBrand() { Brand = "SQL Server" }
       };
    }

    static IEnumerable<CatalogType> GetPreconfiguredCatalogTypes()
    {
        return new List<CatalogType>()
        {
            new CatalogType() { Type = "Mug"},
            new CatalogType() { Type = "T-Shirt" },
            new CatalogType() { Type = "Backpack" },
            new CatalogType() { Type = "USB Memory Stick" }
        };
    }
}
```

<span data-ttu-id="2ae49-128">통합 테스트를 실행할 때 통합 테스트와 일치 하는 데이터를 생성 하는 방법을 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-128">When you run integration tests, having a way to generate data consistent with your integration tests is useful.</span></span> <span data-ttu-id="2ae49-129">모든 컨테이너를 실행 중인 SQL Server의 인스턴스를 포함 하 여 처음부터 새로 작성할 수 있도록 테스트 환경에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-129">Being able to create everything from scratch, including an instance of SQL Server running on a container, is great for test environments.</span></span>

### <a name="ef-core-inmemory-database-versus-sql-server-running-as-a-container"></a><span data-ttu-id="2ae49-130">컨테이너 실행 중인 SQL Server와 EF 코어 InMemory 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="2ae49-130">EF Core InMemory database versus SQL Server running as a container</span></span>

<span data-ttu-id="2ae49-131">테스트를 실행할 때 또 다른 좋은 선택권 Entity Framework InMemory 데이터베이스 공급자를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-131">Another good choice when running tests is to use the Entity Framework InMemory database provider.</span></span> <span data-ttu-id="2ae49-132">웹 API 프로젝트에 해당 구성을 시작 클래스의 ConfigureServices 메서드에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-132">You can specify that configuration in the ConfigureServices method of the Startup class in your Web API project:</span></span>

```csharp
public class Startup
{
    // Other Startup code ...
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddSingleton<IConfiguration>(Configuration);
        // DbContext using an InMemory database provider
        services.AddDbContext<CatalogContext>(opt => opt.UseInMemoryDatabase());
        //(Alternative: DbContext using a SQL Server provider
        //services.AddDbContext<CatalogContext>(c =>
        //{
            // c.UseSqlServer(Configuration["ConnectionString"]);
            //
        //});
    }
  
    // Other Startup code ...

}
```

<span data-ttu-id="2ae49-133">경우에 중요 한 catch가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-133">There is an important catch, though.</span></span> <span data-ttu-id="2ae49-134">메모리 내 데이터베이스에는 특정 데이터베이스에만 적용 되는 여러 제약 조건을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-134">The in-memory database does not support many constraints that are specific to a particular database.</span></span> <span data-ttu-id="2ae49-135">예를 들어, EF 코어 모델의 열에 고유 인덱스를 추가할 수도 있으며 있는지 수 없습니다 중복 값을 추가할 수를 확인 하려면 메모리 내 데이터베이스에 대해 테스트를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-135">For instance, you might add a unique index on a column in your EF Core model and write a test against your in-memory database to check that it does not let you add a duplicate value.</span></span> <span data-ttu-id="2ae49-136">열에 고유 인덱스를 처리할 수 없는 메모리 내 데이터베이스를 사용 하는 경우 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-136">But when you are using the in-memory database, you cannot handle unique indexes on a column.</span></span> <span data-ttu-id="2ae49-137">따라서 메모리 내 데이터베이스 작동 하지 않으면 실제 SQL Server 데이터베이스와 똑같이-데이터베이스 관련 제약 조건을 에뮬레이트하 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-137">Therefore, the in-memory database does not behave exactly the same as a real SQL Server database—it does not emulate database-specific constraints.</span></span>

<span data-ttu-id="2ae49-138">그럼에도 메모리 내 데이터베이스는 테스트 및 프로토타입을 생성 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-138">Even so, an in-memory database is still useful for testing and prototyping.</span></span> <span data-ttu-id="2ae49-139">하지만 특정 데이터베이스 구현의 동작을 고려 하는 정확 하 게 통합 테스트를 만들려는 경우 SQL Server와 같은 실제 데이터베이스를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-139">But if you want to create accurate integration tests that take into account the behavior of a specific database implementation, you need to use a real database like SQL Server.</span></span> <span data-ttu-id="2ae49-140">이 위해 선택 하 고 EF 코어 InMemory 데이터베이스 공급자 보다 더 정확 하는 좋은 컨테이너에서 SQL Server를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-140">For that purpose, running SQL Server in a container is a great choice and more accurate than the EF Core InMemory database provider.</span></span>

### <a name="using-a-redis-cache-service-running-in-a-container"></a><span data-ttu-id="2ae49-141">컨테이너에서 실행 되는 Redis 캐시 서비스를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="2ae49-141">Using a Redis cache service running in a container</span></span>

<span data-ttu-id="2ae49-142">Redis는 개발 및 테스트에 특히 및 개념 증명 시나리오에 대 한 컨테이너를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-142">You can run Redis on a container, especially for development and testing and for proof-of-concept scenarios.</span></span> <span data-ttu-id="2ae49-143">이 시나리오는 컨테이너에서 실행 중인 모든 종속성을 가질 수 있으므로 편리 하 고-로컬 개발 컴퓨터에 대 한 하지만 CI/CD 파이프라인에서 테스트 환경에 대해 뿐만 아니라 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-143">This scenario is convenient, because you can have all your dependencies running on containers—not just for your local development machines, but for your testing environments in your CI/CD pipelines.</span></span>

<span data-ttu-id="2ae49-144">그러나 프로덕션 환경에서 Redis를 실행할 때 PaaS (Platform 서비스로)으로 실행 되는 Redis Microsoft Azure 같은 고가용성 솔루션을 찾도록 향상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-144">However, when you run Redis in production, it is better to look for a high-availability solution like Redis Microsoft Azure, which runs as a PaaS (Platform as a Service).</span></span> <span data-ttu-id="2ae49-145">코드에서 연결 문자열을 변경 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-145">In your code, you just need to change your connection strings.</span></span>

<span data-ttu-id="2ae49-146">Redis는 Redis와 함께 Docker 이미지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-146">Redis provides a Docker image with Redis.</span></span> <span data-ttu-id="2ae49-147">해당 이미지는이 URL에서 Docker 허브에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-147">That image is available from Docker Hub at this URL:</span></span>

<span data-ttu-id="2ae49-148"><https://hub.docker.com/_/redis/></span><span class="sxs-lookup"><span data-stu-id="2ae49-148"><https://hub.docker.com/_/redis/></span></span>

<span data-ttu-id="2ae49-149">명령 프롬프트에서 다음 Docker CLI 명령을 실행 하 여 Docker Redis 컨테이너를 직접 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-149">You can directly run a Docker Redis container by executing the following Docker CLI command in your command prompt:</span></span>

```
  docker run --name some-redis -d redis
```

<span data-ttu-id="2ae49-150">따라서 표준 컨테이너 연결는 자동으로 사용할 수 있도록 연결 된 컨테이너, Redis 이미지 노출: 6379 (Redis에서 사용 하는 포트)를 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-150">The Redis image includes expose:6379 (the port used by Redis), so standard container linking will make it automatically available to the linked containers.</span></span>

<span data-ttu-id="2ae49-151">EShopOnContainers, basket.api 마이크로 서비스의 컨테이너를 실행 하는 Redis cache를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-151">In eShopOnContainers, the basket.api microservice uses a Redis cache running as a container.</span></span> <span data-ttu-id="2ae49-152">다음 예제와 같이 해당 basket.data 컨테이너 다중 컨테이너 docker compose.yml 파일의 일부로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-152">That basket.data container is defined as part of the multi-container docker-compose.yml file, as shown in the following example:</span></span>

```yml
#docker-compose.yml file
#...
  basket.data:
    image: redis
    expose:
      - "6379"
```

<span data-ttu-id="2ae49-153">이 코드에서 docker compose.yml redis 이미지에 따라 및 포트 6379을 내부적으로 게시 하 여 Docker 호스트 내에서 실행 되는 다른 컨테이너를 통해서만 액세스할 것 것을 의미 basket.data 라는 컨테이너를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-153">This code in the docker-compose.yml defines a container named basket.data based on the redis image and publishing the port 6379 internally, meaning that it will be accessible only from other containers running within the Docker host.</span></span>

<span data-ttu-id="2ae49-154">마지막으로, docker compose.override.yml 파일 eShopOnContainers 샘플에 대 한 basket.api 마이크로 서비스 해당 Redis 컨테이너에 사용할 연결 문자열을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ae49-154">Finally, in the docker-compose.override.yml file, the basket.api microservice for the eShopOnContainers sample defines the connection string to use for that Redis container:</span></span>

```yml
  basket.api:
    environment:
      # Other data ...
      - ConnectionString=basket.data
      - EventBusConnection=rabbitmq
```


>[!div class="step-by-step"]
<span data-ttu-id="2ae49-155">[이전] (다중-container-응용 프로그램-docker-compose.md) [다음] (통합-이벤트-기반-마이크로 서비스-communications.md)</span><span class="sxs-lookup"><span data-stu-id="2ae49-155">[Previous] (multi-container-applications-docker-compose.md) [Next] (integration-event-based-microservice-communications.md)</span></span>
