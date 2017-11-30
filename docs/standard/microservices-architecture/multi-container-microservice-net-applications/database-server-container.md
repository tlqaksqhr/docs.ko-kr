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
# <a name="using-a-database-server-running-as-a-container"></a>컨테이너 실행 하는 데이터베이스 서버를 사용 하 여

온-프레미스 클러스터에서 또는 Azure SQL DB와 같은 클라우드 서비스 PaaS의에서 일반 독립 실행형 서버에 데이터베이스 (SQL Server, PostgreSQL, MySQL 등)를 포함할 수 있습니다. 그러나 개발 및 테스트 환경에 대 한 컨테이너로 서 실행 되는 프로그램 데이터베이스에 있는 단순히 실행 되 고 한 외부 종속성이 없기 때문에 편리한는 docker 구성 명령은 전체 응용 프로그램을 시작 합니다. 가 있으면 컨테이너와 해당 데이터베이스도 통합 테스트에 매우 유용 하므로 데이터베이스는 컨테이너에서 시작 되 고 테스트는 예측 가능성이 더욱 뛰어난 될 수 있도록 항상 동일한 샘플 데이터로 채워진 합니다.

### <a name="sql-server-running-as-a-container-with-a-microservice-related-database"></a>마이크로 서비스와 관련 된 데이터베이스와 컨테이너를 실행 중인 SQL Server

EShopOnContainers에 sql.data에 정의 된 명명 된 컨테이너는 [docker compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml) 는 microservices에 필요한 모든 SQL Server 데이터베이스와 Linux 용 SQL Server를 실행 하는 파일입니다. (각 데이터베이스에 대 한 SQL Server 컨테이너 있을 만들 수 있지만 더 많은 메모리를 Docker에 할당 해야 합니다.) Microservices에 중요 한 점은 각 마이크로 서비스 소유 하 고 있음이 관련된 데이터를 따라서 SQL 데이터베이스 관련된이 경우입니다. 하지만 원격 데이터베이스가 있을 수 있습니다.

샘플 응용 프로그램의 컨테이너를 실행할 때 실행 되는 docker compose.yml 파일에 다음 YAML 코드로 구성 된 SQL Server docker-작성을 합니다. 참고 YAML 코드는 제네릭 docker compose.yml 파일 및 docker compose.override.yml 파일에서 구성 정보를 통합 합니다. (일반적으로 분리 기반 또는 정적 정보 이미지와 관련 된 SQL Server에서에서 환경 설정 합니다.)

```yml
sql.data:
  image: microsoft/mssql-server-linux
  environment:
    - SA_PASSWORD=your@password
    - ACCEPT_EULA=Y
  ports:
    - "5434:1433"
```

다음 docker run 명령에는 해당 컨테이너를 실행할 수 있습니다.

```
  docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD= your@password' -p 1433:1433 -d microsoft/mssql-server-linux
```

그러나 eShopOnContainers 같은 다중 컨테이너 응용 프로그램을 배포 하는 것이 간편 사용 하는 docker-작성 명령을 응용 프로그램에 필요한 모든 컨테이너 배포 되도록 합니다.

처음으로이 SQL Server 컨테이너를 시작할 때 컨테이너를 제공 하는 암호와 함께 SQL Server를 초기화 합니다. SQL Server Management Studio, Visual Studio 또는 C와 같은 모든 일반 SQL 연결을 통해 연결 하 여 데이터베이스를 업데이트할 수는 컨테이너로 SQL Server를 실행 하 고\# 코드입니다.

EShopOnContainers 응용 프로그램의 다음 섹션에 설명 된 대로 시작 시 데이터로 시드 여 샘플 데이터와 함께 각 마이크로 서비스 데이터베이스를 초기화 합니다.

SQL server의 컨테이너 실행 유용 하지 않습니다 방금 데모는 여기서 없을 수도 있습니다 SQL Server의 인스턴스에 대 한 액세스. 앞서 언급 한 대로 이기도 개발 및 테스트 환경에 대 한 훌륭한 쉽게 정리 하는 SQL Server 이미지에서 시작 하는 통합 테스트를 실행 하 고 시드 새 예제 데이터에서 데이터를 알 수 있도록 합니다.

#### <a name="additional-resources"></a>추가 리소스

-   **Linux, Mac, 또는 Windows에서 SQL Server Docker 이미지를 실행**
    [*https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker*](https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker)

-   **연결 및 sqlcmd Linux에서 SQL Server에 쿼리할**
    [*https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd*](https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd)

### <a name="seeding-with-test-data-on-web-application-startup"></a>웹 응용 프로그램 시작 시 테스트 데이터로 시드

응용 프로그램이 시작 될 때 데이터베이스에 데이터를 추가, 웹 API 프로젝트의 시작 클래스에서 구성 메서드에 다음과 같은 코드를 추가할 수 있습니다.

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

사용자 지정 CatalogContextSeed 클래스에 다음 코드는 데이터를 채웁니다.

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

통합 테스트를 실행할 때 통합 테스트와 일치 하는 데이터를 생성 하는 방법을 유용 합니다. 모든 컨테이너를 실행 중인 SQL Server의 인스턴스를 포함 하 여 처음부터 새로 작성할 수 있도록 테스트 환경에 유용 합니다.

### <a name="ef-core-inmemory-database-versus-sql-server-running-as-a-container"></a>컨테이너 실행 중인 SQL Server와 EF 코어 InMemory 데이터베이스

테스트를 실행할 때 또 다른 좋은 선택권 Entity Framework InMemory 데이터베이스 공급자를 사용 하는 것입니다. 웹 API 프로젝트에 해당 구성을 시작 클래스의 ConfigureServices 메서드에 지정할 수 있습니다.

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

경우에 중요 한 catch가 있습니다. 메모리 내 데이터베이스에는 특정 데이터베이스에만 적용 되는 여러 제약 조건을 지원 하지 않습니다. 예를 들어, EF 코어 모델의 열에 고유 인덱스를 추가할 수도 있으며 있는지 수 없습니다 중복 값을 추가할 수를 확인 하려면 메모리 내 데이터베이스에 대해 테스트를 작성할 수 있습니다. 열에 고유 인덱스를 처리할 수 없는 메모리 내 데이터베이스를 사용 하는 경우 뿐입니다. 따라서 메모리 내 데이터베이스 작동 하지 않으면 실제 SQL Server 데이터베이스와 똑같이-데이터베이스 관련 제약 조건을 에뮬레이트하 지 않습니다.

그럼에도 메모리 내 데이터베이스는 테스트 및 프로토타입을 생성 하는 데 유용 합니다. 하지만 특정 데이터베이스 구현의 동작을 고려 하는 정확 하 게 통합 테스트를 만들려는 경우 SQL Server와 같은 실제 데이터베이스를 사용 해야 합니다. 이 위해 선택 하 고 EF 코어 InMemory 데이터베이스 공급자 보다 더 정확 하는 좋은 컨테이너에서 SQL Server를 실행 합니다.

### <a name="using-a-redis-cache-service-running-in-a-container"></a>컨테이너에서 실행 되는 Redis 캐시 서비스를 사용 하 여

Redis는 개발 및 테스트에 특히 및 개념 증명 시나리오에 대 한 컨테이너를 실행할 수 있습니다. 이 시나리오는 컨테이너에서 실행 중인 모든 종속성을 가질 수 있으므로 편리 하 고-로컬 개발 컴퓨터에 대 한 하지만 CI/CD 파이프라인에서 테스트 환경에 대해 뿐만 아니라 합니다.

그러나 프로덕션 환경에서 Redis를 실행할 때 PaaS (Platform 서비스로)으로 실행 되는 Redis Microsoft Azure 같은 고가용성 솔루션을 찾도록 향상 됩니다. 코드에서 연결 문자열을 변경 하기만 하면 됩니다.

Redis는 Redis와 함께 Docker 이미지를 제공합니다. 해당 이미지는이 URL에서 Docker 허브에서 제공 됩니다.

<https://hub.docker.com/_/redis/>

명령 프롬프트에서 다음 Docker CLI 명령을 실행 하 여 Docker Redis 컨테이너를 직접 실행할 수 있습니다.

```
  docker run --name some-redis -d redis
```

따라서 표준 컨테이너 연결는 자동으로 사용할 수 있도록 연결 된 컨테이너, Redis 이미지 노출: 6379 (Redis에서 사용 하는 포트)를 포함 됩니다.

EShopOnContainers, basket.api 마이크로 서비스의 컨테이너를 실행 하는 Redis cache를 사용 합니다. 다음 예제와 같이 해당 basket.data 컨테이너 다중 컨테이너 docker compose.yml 파일의 일부로 정의 됩니다.

```yml
#docker-compose.yml file
#...
  basket.data:
    image: redis
    expose:
      - "6379"
```

이 코드에서 docker compose.yml redis 이미지에 따라 및 포트 6379을 내부적으로 게시 하 여 Docker 호스트 내에서 실행 되는 다른 컨테이너를 통해서만 액세스할 것 것을 의미 basket.data 라는 컨테이너를 정의 합니다.

마지막으로, docker compose.override.yml 파일 eShopOnContainers 샘플에 대 한 basket.api 마이크로 서비스 해당 Redis 컨테이너에 사용할 연결 문자열을 정의 합니다.

```yml
  basket.api:
    environment:
      # Other data ...
      - ConnectionString=basket.data
      - EventBusConnection=rabbitmq
```


>[!div class="step-by-step"]
[이전] (다중-container-응용 프로그램-docker-compose.md) [다음] (통합-이벤트-기반-마이크로 서비스-communications.md)
