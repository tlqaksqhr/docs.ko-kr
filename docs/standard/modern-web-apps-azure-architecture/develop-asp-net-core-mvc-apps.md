---
title: "ASP.NET Core MVC 앱 개발"
description: "ASP.NET Core와 Azure의 최신 웹 응용 프로그램을 설계 | ASP.NET Core MVC 앱 개발"
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c10bf66dd37f0d99c038db7f95999d84986152fa
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="develop-aspnet-core-mvc-apps"></a>ASP.NET Core MVC 응용 프로그램 개발

> "을 내려 처음으로 중요 하지 않습니다. 반드시을 내려 마지막 시간입니다. "  
> _-Andrew 사냥과 David Thomas_

## <a name="summary"></a>요약

ASP.NET Core는 최신 클라우드 액세스에 최적화 된 웹 응용 프로그램을 빌드하기 위한 플랫폼, 오픈 소스 프레임 워크입니다. ASP.NET Core 응용 프로그램은 간단한 및 큰 테스트 용이성 및 유지 관리에 사용 되는 종속성 주입을 위한 기본 제공 지원으로 모듈식입니다. 엔터프라이즈 웹 응용 프로그램을 빌드할 수 있는 강력한 프레임 워크를 ASP.NET Core MVC 뷰 기반 응용 프로그램 뿐만 아니라 최신 웹 Api 작성을 지 원하는와 결합 합니다.

## <a name="mapping-requests-to-responses"></a>요청 응답에 매핑

기본적으로 다중에서 ASP.NET Core 응용 프로그램을 나가는 응답 들어오는 요청을 매핑합니다. 낮은 수준에서 미들웨어를 사용 하 고 간단한 ASP.NET Core 응용 프로그램 및 microservices 사용자 지정 미들웨어의만 구성 될 수 있습니다. 측면에서 생각할 높은 수준에서 작업할 수 ASP.NET Core MVC를 사용 하면 *경로*, *컨트롤러*, 및 *동작*합니다. 응용 프로그램의 라우팅 테이블을 들어오는 각 요청은 비교 하 고, 일치 하는 경로가 있으면 요청을 처리할 (컨트롤러에 속하는) 연결 된 동작 메서드가 호출 됩니다. 일치 하는 경로가 없는 발견 되 면 (NotFound 결과 반환 합니다.이 경우)에서 오류 처리기가 호출 됩니다.

ASP.NET Core MVC 앱 규칙에 따른 경로, 특성 경로 또는 둘 다 사용할 수 있습니다. 라우팅을 지정 하는 코드에서 정의 된 규칙에 따른 경로 *규칙* 아래 예제에서는 같은 구문을 사용 하 여:

```csharp
app.UseMvc(routes =>;
{
    routes.MapRoute("default","{controller=Home}/{action=Index}/{id?}");
});
```

이 예제에서는 "default" 라는 경로 라우팅 테이블에 추가 되었습니다. 에 대 한 자리 표시자를 포함 하는 경로 템플릿을 정의 *컨트롤러*, *동작*, 및 *id*합니다. 컨트롤러 및 작업 자리 표시자 기본값이 지정 되어 ("홈" 및 "인덱스"를 각각), id 자리 표시자는 선택 사항 (인해는 "?" 적용). 규칙에 따라 여기에 정의 된 상태는 요청의 첫 번째 부분 일치 해야 하는 작업에 두 번째 부분은 컨트롤러의 이름을 나타내고 필요에 따라 세 번째 부분은 됩니다는 id 매개 변수. 기본 경로 시작 클래스의 구성 메서드에서 같은 응용 프로그램을 한 곳에 일반적으로 정의 합니다.

특성 경로 전역적으로 지정 되지 않고 직접, 컨트롤러 및 작업에 적용 됩니다. 이 특정 메서드를 찾고 있지만 라우팅 정보가 응용 프로그램에서 한 곳에 저장 되지 않습니다는 의미 하는 경우 훨씬 더 쉽게 검색할 수 있게의 이점이 있습니다. 특성 경로와 있습니다 수 쉽게 지정된 된 동작에 대 한 여러 경로 지정으로 컨트롤러 및 작업 간 경로 결합 합니다. 예:

```csharp
[Route("Home")]
public class HomeController : Controller
{
    [Route("")] // Combines to define the route template "Home"
    [Route("Index")] // Combines to define route template "Home/Index"
    [Route("/")] // Does not combine, defines the route template ""
    public IActionResult Index() {}
```

[HttpGet]에 경로 지정할 수 있습니다 및 비슷한 특성을 추가할 필요가 없도록 분리 [경로\] 특성입니다. 특성 경로 토큰을 사용 하 여 아래와 같이 이름, 컨트롤러 또는 작업을 반복할 필요가 줄이기 위해 수 있습니다.:

```csharp
[Route("[controller\]")]
public class ProductsController : Controller
{
    [Route("")] // Matches 'Products'
    [Route("Index")] // Matches 'Products/Index'
    public IActionResult Index()
}
```

지정된 된 요청을 경로에 일치 작업 전에 메서드가 호출 되 면 ASP.NET Core MVC 수행될지 [모델 바인딩](https://docs.microsoft.com/aspnet/core/mvc/models/model-binding) 및 [유효성 검사 모델](https://docs.microsoft.com/aspnet/core/mvc/models/validation) 요청에 합니다. 모델 바인딩에 들어오는 HTTP 데이터를 호출할 수는 동작 메서드의 매개 변수로 지정 된.NET 형식으로 변환 합니다. 예를 들어 들어 동작 메서드가 요구는 int id 매개 변수, 모델 바인딩 요청의 일부로 제공 된 값에서이 매개 변수를 제공 하려고 합니다. 이렇게 하려면 게시 된 폼 값, 경로 자체의 값 및 쿼리 문자열 값에 대 한 모델 바인딩이 찾습니다. Id 값을 찾으면 라고 가정할 경우이 변환 됩니다는 정수 작업 메서드로 전달 하기 전에.

모델을 바인딩한 후 표시 되지만 작업 메서드를 호출 하기 전에 모델 유효성 검사가 발생 합니다. 모델 유효성 검사 모델 형식에 선택적 특성을 사용 하 고 제공 된 모델 개체에 특정 데이터 요구 사항을 준수 하는지 확인 합니다. 특정 값으로 지정할 수 있습니다, 필요한 또는 특정 길이 나 숫자 범위 제한, 등입니다. 유효성 검사 특성을 지정 하는 경우 모델의 요구 사항에 맞지 않는 속성 ModelState.IsValid을 false 되며 실패 유효성 검사 규칙의 집합 요청을 만드는 클라이언트에 보낼 수 있습니다.

모델 유효성 검사를 사용 하는 경우에 항상 모든 상태 변경 명령을 앱 잘못 된 데이터가 손상 되지 않았는지 확인을 수행 하기 전에 모델이 유효한 지를 확인 해야 해야 합니다. 사용할 수는 [필터](https://docs.microsoft.com/aspnet/core/mvc/controllers/filters) 코드를 추가 하려면이 대 한 모든 작업에 필요 하면 합니다. ASP.NET Core MVC 필터 일반적인 정책 및 일반적인 문제를 대상으로 적용할 수 있도록 그룹 요청을 가로채는 방법을 제공 합니다. 개별 작업을 전체 컨트롤러 또는 응용 프로그램에 대 한 전역 필터를 적용할 수 있습니다.

ASP.NET Core MVC 웹 Api에 대 한 지원 [ *콘텐츠 협상*](https://docs.microsoft.com/aspnet/core/mvc/models/formatting), 때문에 요청이 응답 해야 형식을 지정 합니다. 요청에 제공 하는 헤더에 따라, 데이터 반환 작업은 응답 XML, JSON, 또는 다른 지원 되는 형식에 서식을 지정 합니다. 이 기능에는 동일한 API를 다른 데이터 형식 요구 사항을 여러 클라이언트에서 사용할 수 있습니다.

> ### <a name="references--mapping-requests-to-responses"></a>참조 – 요청 응답에 매핑
> - **컨트롤러 작업에 대 한 라우팅을**
> <https://docs.microsoft.com/aspnet/core/mvc/controllers/routing>
> - **모델 바인딩** https://docs.microsoft.com/aspnet/core/mvc/models/model-binding
> - **유효성 검사 모델**
> <https://docs.microsoft.com/aspnet/core/mvc/models/validation>
> - **Filters** https://docs.microsoft.com/aspnet/core/mvc/controllers/filters

## <a name="working-with-dependencies"></a>종속성 사용

ASP.NET Core에서 기본적으로 지원 하 고에서는 기술을 활용 하는 내부적으로 [종속성 주입](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection)합니다. 종속성 주입 방법은 응용 프로그램의 다른 부분 간의 느슨한 결합을 사용 하도록 설정 합니다. 이보다 결합 하면 손쉽게 테스트 또는 교체 허용 범위를 응용 프로그램의 일부를 격리 하기 때문에 좋습니다. 하기가 응용 프로그램의 한 부분에 있는 변경 다른 위치에서 응용 프로그램에 예기치 않은 영향을 미치게 됩니다는 가능성이 더 낮아집니다. 종속성 주입 종속성 반전 원칙에 따라이 고, 열기/닫기 원칙을 구현 하려면 있습니다. 응용 프로그램이 종속성과 함께 작동 하는 방법을 평가할 때는 조심는 [정적 문에 붙이는](http://deviq.com/static-cling/) 후 각 코드 하 고는 aphorism 기억 "[새 작업은](http://ardalis.com/new-is-glue)."

정적 문에 붙이는 클래스에 정적 메서드를 호출 하거나 인프라에 대 한 부작용 또는 종속성 정적 속성에 액세스 하는 경우에 발생 합니다. 예를 들어 데이터베이스에 다시 기록, 정적 메서드를 호출 하는 메서드를 설정한 경우 메서드는 밀접 하 게 데이터베이스에 관련 됩니다. 아무 것도 해당 데이터베이스 호출을 중단 하는 방법에 끊어집니다. 이러한 메서드 까다로운가 있으므로 테스트를 이러한 테스트를 정적 호출 모의 상용 모의 개체 라이브러리가 필요 하거나 현재 위치에서 테스트 데이터베이스와 함께 테스트할 수 있습니다. 특히는 완전히 상태를 저장 하는 인프라에 대 한 모든 종속성을 갖지 않는 정적 호출은 됩니다 세밀 하 게 호출 하 고 결합 또는 테스트 용이성 (정적 호출 자체에 코드를 결합) 외에 영향을 주지 않습니다.

대부분의 개발자 문에 붙이는 정적 및 전역 상태의 위험이 있지만 직접 인스턴스화를 통해 특정 구현에 코드를 여전히 밀접 하 게 결합 됩니다. "새는 글 루" 결합이 미리 알림 및 new 키워드의 사용의 일반적인 condemnation 하지 알 수 있도록 합니다. 과 마찬가지로 정적 메서드 호출 일반적으로 외부 종속성이 없는 형식의 새 인스턴스 하지 밀접 하 게 구현 세부 정보를 코드를 결합에 있거나 테스트 더 어렵게 만들 합니다. 그러나는 클래스를 인스턴스화할 때마다 걸릴 잠시 또는 종속성으로 해당 인스턴스를 요청 하려면 더 나은 디자인 하는 의미가 하드 코딩 특정 인스턴스에 해당 특정 위치에 있는지 여부를 고려해 야 할 뿐입니다.

### <a name="declare-your-dependencies"></a>종속성을 선언

ASP.NET Core 메서드 것으로 구축 되었습니다 및 클래스를 인수로 요청 하는 해당 종속성을 선언 합니다. ASP.NET 응용 프로그램 시작 클래스에서 설정 일반적으로 하는 시점에 종속성 주입을 지원 하도록 구성 된 논리입니다. 생성자를 통해 종속성을 요청할 수 있는 경우 시작 클래스에 생성자 같이:

```csharp
public class Startup
{
    public Startup(IHostingEnvironment env)
    {
        var builder = new ConfigurationBuilder()
        .SetBasePath(env.ContentRootPath)
        .AddJsonFile("appsettings.json", optional: false, reloadOnChange: true)
        .AddJsonFile(\$"appsettings.{env.EnvironmentName}.json", optional: true);
    }
}
```

시작 클래스에 대 한 명시적 형식 요구는 흥미로운 부분입니다. 특별 한 시작 기본 클래스에서 상속 하지 않습니다 하거나 특정 인터페이스를 구현지 않습니다. 지정할 수 있습니다는 생성자를 한 수의 매개 변수는 생성자에서 원하는 대로 지정할 수 있습니다. 응용 프로그램에 대해 구성 하는 웹 호스트 시작 시작 클래스를 사용 하도록 지시를 호출 합니다 또는 시작 클래스에 필요한 모든 종속성을 채우는 데 종속성 주입을 사용 합니다. 물론, ASP.NET Core에서 사용 하는 서비스 컨테이너에 구성 되지 않은 매개 변수를 요청 하는 경우 예외를 받습니다 하지만 종속성에 집중으로 컨테이너에 대해 알고를 원하는 대로 요청할 수 있습니다.

종속성 주입 시작 인스턴스를 만들 때, 처음부터 ASP.NET Core 응용 프로그램에 포함 됩니다. 여기서 시작 클래스에 대 한 중지 하지 않습니다. Configure 메서드에서 종속성을 요청할 수 있습니다.

```csharp
public void Configure(IApplicationBuilder app,
    IHostingEnvironment env,
    ILoggerFactory loggerFactory)
{

}
```

ConfigureServices 메서드는이 동작에 대 한 예외 IServiceCollection 형식의 매개 변수 하나에 수행 해야 할 합니다. 가구의 서비스 컨테이너에 개체를 추가 하는 일을 담당 하는 한편 IServiceCollection 매개 변수를 통해 모든 현재 구성 된 서비스를 수행할 액세스 권한이 다른 종속성 주입을 지원 하기 위해 실제로 필요 하지 않습니다. 따라서 매개 변수로 필요한 서비스를 요청 하거나 IServiceCollection ConfigureServices에서 사용 하 여 시작 클래스의 모든 부분에서 ASP.NET Core 서비스 컬렉션에 정의 된 종속성 작업할 수 있습니다.

> [!NOTE]
> 특정 서비스를 시작 클래스를 사용할 수 있는지 확인 해야 할 경우 구성할 수 있습니다 WebHostBuilder와 해당 ConfigureServices 메서드를 사용 하 여 합니다.

시작 클래스는 자신의 서비스에 대 한 필터를 미들웨어 컨트롤러에서 ASP.NET Core 응용 프로그램의 다른 부분을 구성 해야 하는 것에 대 한 모델입니다. 각각의 경우에 따라야는 [명시적 종속성 원칙](http://deviq.com/explicit-dependencies-principle/), 종속성 요청 하지 않고 직접 만들기, 및 응용 프로그램에서 종속성 주입을 활용 합니다. 구현에서는 특히 서비스 및 인프라를 사용 하거나 의도 하지 않은 개체를 직접 인스턴스화할 위치와 방법을 주의 해야 합니다. 추상화 형식 특정 구현에 하드 코딩 참조에 대 한 인수로 전달 하 고 응용 프로그램 코어에 정의 된 사용을 선호 합니다.

## <a name="structuring-the-application"></a>응용 프로그램 구성

일반적으로 단일 응용 프로그램의 단일 진입점을 가집니다. ASP.NET Core 웹 응용 프로그램의 경우 진입점 ASP.NET Core 웹 프로젝트 됩니다. 그러나 솔루션이 하나의 프로젝트만 구성 되어야 한다는 의미 하지 않습니다. 문제의 분리를 수행 하려면 다른 계층으로 응용 프로그램을 중단 하는 것이 유용 합니다. 계층으로 분리 되 면를 별도 프로젝트로 효율적으로 캡슐화를 달성 하는 데 도움이 되는 폴더 외에 유용 합니다. ASP.NET Core 응용 프로그램으로 이러한 목표를 달성 하는 좋은 방법이 5 장에 설명 된 정리 아키텍처의 변형입니다. 이 방법에서는 다음 인프라 및 ApplicationCore, UI에 대 한 응용 프로그램의 솔루션 별도 라이브러리 구성 됩니다.

이러한 프로젝트 뿐만 아니라 별도 테스트 프로젝트도 포함 (테스트 장 9에 설명 되어 있음).

응용 프로그램의 개체 모델 및 인터페이스 ApplicationCore 프로젝트에 배치 해야 합니다. 이 프로젝트를 가능한 적은 종속성을 갖습니다 하 고 솔루션의 다른 프로젝트에서 참조 합니다. 직접 인프라에 종속 되지 않는 서비스는 유지 해야 하는 비즈니스 엔터티 ApplicationCore 프로젝트에서 정의 됩니다.

지 속성을 수행 하는 방법 또는 사용자에 게 알림을 전송 될 수 있습니다 어떻게 같은 구현 세부 인프라 프로젝트에 유지 됩니다. 이 프로젝트는 Entity Framework Core와 같은 구현 별 패키지를 참조 하지만 프로젝트 외부에서 이러한 구현에 대 한 세부 정보를 노출 하면 안 합니다. 인프라 서비스 및 저장소 ApplicationCore 프로젝트에 정의 된 인터페이스를 구현 해야 하 고 지 속성 구현 과정은 검색 하 고 ApplicationCore에 정의 된 엔터티를 저장 하는 일을 담당 합니다.

ASP.NET Core 프로젝트 자체는 UI 수준 문제를 담당 하지만 비즈니스 논리 나 인프라 세부 정보를 포함 하지 않아야 합니다. 사실, 이상적으로 것도 없어야 종속성 인프라 프로젝트를 구성 하면 두 개의 프로젝트 간의 종속성 없이 실수로 도입 합니다. 각 프로젝트에 대 한 레지스트리 클래스에서 DI 규칙을 정의할 수 있는 StructureMap 같은 제 3 자 DI 컨테이너 사용 하 여 수행할 수 있습니다.

또 다른 방법은 구현 세부 사항 으로부터 응용 프로그램을 분리 하는 아마도 개별 Docker 컨테이너에 배포 하는 응용 프로그램 호출 microservices을 것입니다. 이 고려 사항 및 분리 DI를 활용 하 여 두 개의 프로젝트 간에 보다 더 높은 분리를 제공 하지만 더 복잡해졌습니다.

### <a name="feature-organization"></a>기능 조직

기본적으로 ASP.NET Core 응용 프로그램 컨트롤러와 뷰 및 자주 Viewmodel 포함 하도록 해당 폴더 구조를 구성 합니다. 이러한 서버 쪽 구조를 지원 하기 위해 클라이언트 쪽 코드는 일반적으로 wwwroot 폴더에서 별도로 저장 됩니다. 그러나 대규모 응용 프로그램 필요한 기능에서 작업 하는 종종 이러한 폴더 사이 이동 필요 하므로이 조직에 문제가 발생할 수 있습니다. 이 더 어려운 늘어나면 각 폴더의 파일과 하위 폴더 수 있는 다양 한 솔루션 탐색기를 통해 스크롤에 가져옵니다. 이 문제에 대 한 한 가지 해결 하 여 응용 프로그램 코드를 구성 하는 *기능* 순서가 아니라 파일 유형입니다. 이 조직 스타일은 일반적으로 기능 폴더 또는 라고 기능 분할 영역 (참고 항목: [수직 분할 영역](http://deviq.com/vertical-slices/)).

ASP.NET Core MVC이이 용도 대 한 영역을 지원합니다. 영역을 사용 하 여 별도의 컨트롤러 및 보기 폴더 (으로 모든 관련된 모델)에서 각 영역 폴더 집합을 만들 수 있습니다. 그림 7-1 영역을 사용 하는 예제 폴더 구조를 보여 줍니다.

![](./media/image7-1.png)

그림 7-1 샘플 영역 조직

영역을 사용 하는 경우를 위해 컨트롤러 소속 된 영역의 이름을를 데코레이팅하 특성을 사용 해야 합니다.

```csharp
[Area("Catalog")]
public class HomeController
{}
```

또한 해야 사용자 경로에 영역 지원을 추가 하려면:

```csharp
app.UseMvc(routes =>
{
    // Areas support
    routes.MapRoute(
    name: "areaRoute",
    template: "{area:exists}/{controller=Home}/{action=Index}/{id?}");
    routes.MapRoute(
    name: "default",
    template: "{controller=Home}/{action=Index}/{id?}");
});
```

영역에 대 한 기본 제공 지원을 외에도 고유한 폴더 구조 및 대신 특성 및 사용자 지정 경로 규칙을 사용할 수 있습니다. 그러면 뷰, 컨트롤러, 계층 구조를 일반적인 방법으로 유지 하 고 모든 관련 파일을 한 곳에서 각 기능에 대 한 참조를 더욱 쉽게 등에 대 한 별도 폴더를 포함 하지 않은 기능 폴더를 가질 수 있습니다.

ASP.NET Core 기본 제공 규칙 형식을 사용 하 여 동작을 제어 합니다. 수정 하거나 이러한 규칙을 바꿀 수 있습니다. 예를 들어, 해당 네임 스페이스 (일반적으로 컨트롤러의 위치를 가리키는 폴더와 관련이)에 따라 지정 된 컨트롤러에 대 한 기능 이름을 받습니다 자동으로 포함 하는 규칙을 만들 수 있습니다.

```csharp
FeatureConvention : IControllerModelConvention
{
    public void Apply(ControllerModel controller)
    {
        controller.Properties.Add("feature",
        GetFeatureName(controller.ControllerType));
    }

    private string GetFeatureName(TypeInfo controllerType)
    {
        string[] tokens = controllerType.FullName.Split('.');
        if (!tokens.Any(t => t == "Features")) return "";
        string featureName = tokens
        .SkipWhile(t => !t.Equals("features",
        StringComparison.CurrentCultureIgnoreCase))
        .Skip(1)
        .Take(1)
        .FirstOrDefault();
        return featureName;
    }
}
```

그런 다음 지정할수록이 규칙 옵션으로 ConfigureServices에서 응용 프로그램에 대 한 MVC에 대 한 지원을 추가 하면:

```csharp
services.AddMvc(o => o.Conventions.Add(new FeatureConvention()));
```

또한 ASP.NET Core MVC 보기를 찾는 한 규칙을 사용 합니다. 뷰 (위에 FeatureConvention에서 제공 된 기능 이름 사용) 기능 폴더에 있을 수 있도록 사용자 지정 규칙을 통해 그를 재정의할 수 있습니다. 이 방법을 사용 하는 방법에 대 한 자세한 정보 및 MSDN 문서에서 작업 예제를 다운로드할 수 있습니다 [ASP.NET Core MVC에 대 한 기능 슬라이스](https://msdn.microsoft.com/magazine/mt763233.aspx)합니다.

### <a name="cross-cutting-concerns"></a>교차 편집 문제

응용 프로그램 성장 함에 따라 중복 제거 및 일관성을 유지 하는 일반적인 문제를 팩터링 하 점점 더 중요 해 집니다. 몇 가지 ASP.NET Core 응용 프로그램의 일반적인 문제는 인증, 모델 유효성 검사 규칙, 출력 캐싱 및 오류 처리, 경우에 많은 키워드가 있습니다. ASP.NET Core MVC [필터](https://docs.microsoft.com/aspnet/core/mvc/controllers/filters) 전이나 요청 처리 파이프라인의 특정 단계 후 코드를 실행할 수 있습니다. 예를 들어, 필터는 모델 바인딩 및 동작을 후 또는 하기 전에 전과 후 작업의 결과 전후 실행할 수 있습니다. 또한 파이프라인의 나머지 부분에 대 한 액세스를 제어 하는 권한 부여 필터를 사용할 수 있습니다. 그림 7-2 방법을 요청 실행 흐름 필터를 구성 합니다.

![요청은 권한 부여 필터, 리소스 필터, 모델 바인딩, 작업 필터, 작업 실행 및 작업 결과 변환, 예외 필터, 결과 필터 및 결과 실행을 통해 처리됩니다. 주의할 점은 요청이 응답이 클라이언트에 전송되기 전에 결과 필터 및 리소스 필터에 따라서만 처리된다는 것입니다.](./media/image7-2.png)

필터 및 요청 파이프라인을 통해 그림 7-2 요청 실행 합니다.

컨트롤러 또는 동작 적용할 수 있도록에 일반적으로 필터 특성으로 구현 됩니다. 이 방식으로 동작 수준 재정의 또는 빌드 컨트롤러 수준에서 지정 된 필터에 지정 된 필터에 추가할 때 자체가 전역 필터를 재정의 합니다. 예를 들어는 \[경로\] 특성 컨트롤러 및 작업 간 경로를 만드는 데 사용할 수 있습니다. 마찬가지로, 권한 부여 컨트롤러 수준에서 구성 및 다음 샘플을 참조 하십시오. 그런 다음 개별 작업에 의해 재정의 될 수 있습니다.

```csharp
[Authorize]
public class AccountController : Controller

{
    [AllowAnonymous]
    public async Task<IActionResult> Login() {}
    public async Task<IActionResult> ForgotPassword() {}
}
```

AllowAnonymous 필터 (특성)를 사용 하 여 컨트롤러 수준에서 설정 하는 권한 부여 필터를 재정의 하는 첫 번째 방법은 로그인 합니다. ForgotPassword 동작 (및 다른 작업에는 AllowAnonymous 특성 없는 클래스에서) 인증 된 요청에 필요 합니다.

일반적인 오류 Api에 대 한 정책 처리의 형태로 중복 제거에 필터를 사용할 수 있습니다. 예를 들어 모델 유효성 검사가 실패할 경우이 존재 하지 않는 키를 참조 하는 요청에 대 한 NotFound 응답 및 잘못 된 요청 응답을 반환 하는 일반적인 API 정책은입니다. 다음 예제에서는 작업에서 이러한 두 정책을 보여 줍니다.

```csharp
[HttpPut("{id}")]
public async Task<IActionResult> Put(int id, [FromBody]Author author)
{
    if ((await _authorRepository.ListAsync()).All(a => a.Id != id))
    {
        return NotFound(id);
    }
    if (!ModelState.IsValid)
    {
        return BadRequest(ModelState);
    }
    author.Id = id;
    await _authorRepository.UpdateAsync(author);
    return Ok();
}
```

다음과 같은 조건부 코드로 겹쳐 화면이 복잡 해질 하는 작업 메서드를 허용 하지 않음. 대신, 필요할 때에 적용할 수 있는 필터에는 정책을 끌어옵니다. 이 예제에서는 명령이 전송 되는 API에 언제 든 지 발생 해야 하 고 모델 유효성 검사는 다음 특성으로 바꿀 수 있습니다.

```csharp
public class ValidateModelAttribute : ActionFilterAttribute
{
    public override void OnActionExecuting(ActionExecutingContext context)
    {
        if (!context.ModelState.IsValid)
        {
            context.Result = new BadRequestObjectResult(context.ModelState);
        }
    }
}
```

마찬가지로, 필터 레코드 존재 동작이 실행 되는 동작의 이러한 검사를 수행 하지 않아도 전에 404를 반환 하는지 확인 데 사용할 수 있습니다. 공통 규칙 빠져 되었으며 UI에서 인프라 코드 및 비즈니스 논리를 분리 하 여 솔루션을 구성 되 면 MVC 동작 메서드는 매우 간소한 같아야 합니다.

```csharp
// PUT api/authors/2/5
[HttpPut("{id}")]
[ValidateAuthorExists]
public async Task<IActionResult> Put(int id, [FromBody]Author author)
{
    await _authorRepository.UpdateAsync(author);
    return Ok();
}
```

읽어볼 수 있는 필터를 구현 하 고 MSDN 문서에서 작업 예제를 다운로드에 대 한 [실제 세계 ASP.NET Core MVC 필터](https://msdn.microsoft.com/magazine/mt767699.aspx)합니다.

> ### <a name="references--structuring-applications"></a>참조-응용 프로그램 구성
> - **영역**  
> <https://docs.microsoft.com/aspnet/core/mvc/controllers/areas>
> - **MSDN-MVC ASP.NET Core에 대 한 기능 슬라이스**
>  <https://msdn.microsoft.com/magazine/mt763233.aspx>
> - **필터**  
> <https://docs.microsoft.com/aspnet/core/mvc/controllers/filters>
> - **MSDN – 실제 코어 ASP.NET MVC 필터**  
> <https://msdn.microsoft.com/magazine/mt767699.aspx>

## <a name="security"></a>보안

웹 응용 프로그램 보안은 큰, 많은 고려 사항입니다. 가장 기본적인 수준에서 보안 사용자에 게 지정된 된 요청와 서 다음 해당 요청 해야 하는 리소스에 대 한 액세스를만 있는지를 확인 하도록 해야 합니다. 인증은 요청 알려진된 엔터티에서 오는 것으로 처리 해야 하는지 확인 하려면 요청에 신뢰할 수 있는 데이터 저장소에 제공 된 자격 증명을 비교 하는 프로세스입니다. 권한 부여는 사용자 id에 따라 특정 리소스에 대 한 액세스를 제한 하는 과정입니다. 세 번째 보안 문제가 발생 요청을 수행 해야 이상 제 3 자가 도청에서 보호 [SSL 응용 프로그램에서 사용 되도록](https://docs.microsoft.com/aspnet/core/security/enforcing-ssl)합니다.

### <a name="authentication"></a>인증

ASP.NET Core Identity는 멤버 자격 시스템으로 응용 프로그램에 대 한 로그인 기능을 지 원하는 데 사용할 수 있습니다. 로컬 사용자 계정에 대 한 지원을 지원 뿐 아니라 외부 로그인 공급자 Microsoft 계정, Twitter, Facebook, Google, 등 같은 공급자 로부터 있습니다. ASP.NET Core Id 외에도 응용 프로그램이 windows 인증을 사용할 수 또는 타사 id 공급자와 같은 [Identityserver](https://github.com/IdentityServer/IdentityServer4)합니다.

ASP.NET Core Id는 개별 사용자 계정 옵션을 선택 하는 경우에 새 프로젝트 템플릿이 포함 됩니다. 이 서식 파일에 등록, 로그인, 외부 로그인, 암호를 잊어버리거나 및 추가 기능에 대 한 지원이 포함 되어 있습니다.

![](./media/image7-3.png)

그림 7-3 선택 개별 사용자 계정에 미리 구성 된 Id가 있습니다.

Id가 지원 시작 시 ConfigureServices 및 구성 모두에서 구성 되어 있습니다.

```csharp
public void ConfigureServices(IServiceCollection services)
{
    // Add framework services.
    services.AddDbContext<ApplicationDbContext>(options =>
    options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection")));
    services.AddIdentity<ApplicationUser, IdentityRole>()
    .AddEntityFrameworkStores<ApplicationDbContext>()
    .AddDefaultTokenProviders();
    services.AddMvc();
}

public void Configure(IApplicationBuilder app)
{
    app.UseStaticFiles();
    app.UseIdentity();
    app.UseMvc(routes =>
    {
        routes.MapRoute(
        name: "default",
        template: "{controller=Home}/{action=Index}/{id?}");
    });
}
```

Configure 메서드에 UseMvc 앞에 UseIdentity가 나타나는지 유용 합니다. ConfigureServices에 Id를 구성 하는 경우에 AddDefaultTokenProviders에 대 한 호출을 확인할 수 있습니다. 이 웹 통신 보안을 사용할 수 있지만 만들 SMS 또는 메일에 대 한 신원을 확인을 통해 사용자에 게 보낼 수 있는 메시지를 표시 하는 공급자를 대신 참조 하는 토큰으로 수행할 작업을 전혀 관계가 없습니다.

에 대 한 자세한 내용은 [다단계 인증 구성](https://docs.microsoft.com/aspnet/core/security/authentication/2fa) 및 [외부 로그인 공급자를 사용 하도록 설정](https://docs.microsoft.com/aspnet/core/security/authentication/social/) 공식 ASP.NET Core docs에서 합니다.

### <a name="authorization"></a>권한 부여

권한 부여의 가장 간단한 형태는 익명 사용자에 대 한 액세스를 제한 하는 작업이 포함 됩니다. 단순히 적용 하 여 수행할 수 있습니다는 \[Authorize\] 특성 특정 컨트롤러 또는 동작을 합니다. 역할을 사용 하는 경우와 같이 특정 역할에 속한 사용자에 게 액세스를 제한 하는 특성을 추가로 확장할 수 있습니다.

```csharp
[Authorize(Roles = "HRManager,Finance")]
public class SalaryController : Controller
{

}
```

이 경우에 HRManager 또는 재무 역할 (또는 둘 다)에 속하는 사용자는 SalaryController에 대 한 액세스 권한을 갖기 합니다. 사용자 (뿐 아니라 여러 가지 방법 중 하나)는 여러 역할에 속해 있는지를 요구 하려면 있습니다 특성을 적용할 수를 여러 번 때마다 필요한 역할을 지정 합니다.

여러 다른 컨트롤러 및 작업에 대 한 문자열 바람직하지 않은 반복 발생할 수 있습니다 역할의 특정 집합을 지정 합니다. 권한 부여 규칙을 캡슐화 하는 권한 부여 정책을 구성 하 고 적용할 때 다음 개별 역할 대신 정책을 지정할 수는 \[Authorize\] 특성:

```csharp
[Authorize(Policy = "CanViewPrivateReport")]
public IActionResult ExecutiveSalaryReport()
{
    return View();
}
```

이러한 방식으로 정책을 사용 하 여, 특정 역할이 나에 적용 되는 규칙에서 제한 되는 작업의 종류를 구분할 수 있습니다. 나중에, 특정 리소스에 액세스 하는 새 역할을 만들 경우 업데이트할 수 있습니다 방금는 정책에서 모든 역할 목록을 업데이트 하는 대신 모든 \[Authorize\] 특성입니다.

#### <a name="claims"></a>클레임

클레임은 인증된 된 사용자의 속성을 나타내는 이름/값 쌍입니다. 예를 들어 사용자의 직원을 클레임으로 저장할 수 있습니다. 클레임 권한 부여 정책의 일부로 다음 사용할 수 있습니다. "EmployeeOnly" 이라는 정책을 만들 수 있습니다이 예제에 표시 된 대로 "이"를 호출 하는 클레임의 존재를 필요로 하 합니다.

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc();
    services.AddAuthorization(options =>
    {
        options.AddPolicy("EmployeeOnly", policy => policy.RequireClaim("EmployeeNumber"));
    });
}
```

이 정책은 함께 사용 될 수도 \[Authorize\] 위에서 설명한 것 처럼 모든 컨트롤러 및/또는 동작을 보호 하는 특성입니다.

#### <a name="securing-web-apis"></a>웹 Api 보안 설정

대부분의 웹 Api 토큰 기반 인증 시스템을 구현 해야 합니다. 토큰 인증을 상태 비저장 및 확장 가능 하도록 설계 된 됩니다. 토큰 기반 인증 시스템에서는 클라이언트 인증 공급자와 함께 먼저 인증 해야 합니다. 성공 하면 클라이언트는 문자의 암호화 방식으로 의미 있는 문자열에 토큰을 발급 합니다. 클라이언트는 다음 API에 요청을 발급 하도록 설정 해야,이 토큰 요청에 헤더를 추가 합니다. 서버에는 다음 요청을 완료 하기 전에 요청 헤더에 위치한 토큰 유효성을 검사 합니다. 그림 7-4이이 프로세스를 보여 줍니다.

![TokenAuth](./media/image7-4.png)

**그림 7-4입니다.** 웹 Api에 대 한 토큰 기반 인증

> ### <a name="references--security"></a>참조-보안
> - **보안 문서 개요**  
> https://docs.microsoft.com/aspnet/core/security/
> - **ASP.NET Core 응용 프로그램에서 SSL을 강제 적용**  
> <https://docs.microsoft.com/aspnet/core/security/enforcing-ssl>
> - **ID 소개**  
> <https://docs.microsoft.com/aspnet/core/security/authentication/identity>
> - **권한 부여 소개**  
> <https://docs.microsoft.com/aspnet/core/security/authorization/introduction>
> - **인증 및 Azure 앱 서비스에서 API 앱에 대 한 권한 부여**  
> <https://docs.microsoft.com/azure/app-service-api/app-service-api-authentication>

## <a name="client-communication"></a>클라이언트 통신

페이지를 처리 하 고 웹 Api 통해 데이터에 대 한 요청에 응답 하는 것 외에도 ASP.NET Core 응용 프로그램은 연결 된 클라이언트와 직접 통신할 수 있습니다. 이 아웃 바운드 통신 전송 기술의 다양 가장 일반적인 되 고 Websocket 사용할 수 있습니다. ASP.NET Core SignalR는 종류의 응용 프로그램에 대 한 실시간 서버와 클라이언트 간 통신 기능에 간단한 수행 하는 라이브러리입니다. SignalR 다양 한 기술 전송 Websocket을 지원 하 고 트래버스하여 다 개발자의 구현 세부 사항을 추상화 합니다.

ASP.NET Core SignalR은 개발, 현재 및 ASP.NET 코어의 다음 릴리스에서 사용할 수 있습니다. 그러나 다른 [소스 Websocket 라이브러리를 열고](https://github.com/radu-matei/websocket-manager) 현재 사용할 수 있습니다.

실시간 클라이언트 통신을 WebSockets 직접 또는 기타 기술을 사용 하 여 다양 한 응용 프로그램 시나리오에서에서 유용 지 합니다. 예를 들면 다음과 같습니다.

-   라이브 대화방 응용 프로그램

-   응용 프로그램 모니터링

-   작업 진행 상황 업데이트

-   알림

-   대화형 forms 응용 프로그램

응용 프로그램에 대 한 클라이언트 통신을 빌드하는 경우 일반적으로 두 구성 요소가 있습니다.

-   서버 쪽 연결 관리자 (SignalR 허브, WebSocketManager WebSocketHandler)

-   클라이언트 쪽 라이브러리

클라이언트 브라우저 – 모바일 응용 프로그램, 콘솔 응용 프로그램으로 제한 되지 않으며 다른 네이티브 앱 SignalR/Websocket을 사용 하 여도 통신할 수 있습니다. 다음 간단한 프로그램 에코 WebSocketManager 샘플 응용 프로그램의 일부분으로 콘솔에 채팅 응용 프로그램에 전달 된 모든 콘텐츠:

```csharp
public class Program
{
    private static Connection _connection;
    public static void Main(string[] args)
    {
        StartConnectionAsync();
        _connection.On("receiveMessage", (arguments) =>;
        {
            Console.WriteLine(\$"{arguments\[0\]} said: {arguments\[1\]}");
        });
        Console.ReadLine();
        StopConnectionAsync();
    }
    
    public static async Task StartConnectionAsync()
    {
        _connection = new Connection();
        await _connection.StartConnectionAsync("ws://localhost:65110/chat");
    }
    
    public static async Task StopConnectionAsync()
    {
        await _connection.StopConnectionAsync();
    }
```

발생 하는 방법으로 응용 프로그램 클라이언트 응용 프로그램과 직접 통신 및 실시간 통신 응용 프로그램의 사용자를 향상 시킬 수 있는지 여부를 고려 하는 것이 좋습니다.

> ### <a name="references--client-communication"></a>참조-클라이언트 통신
> - **ASP.NET Core SignalR**  
> <https://github.com/aspnet/SignalR>
> - **WebSocket 관리자**  
> https://github.com/radu-matei/websocket-manager

## <a name="domain-driven-design--should-you-apply-it"></a>도메인 기반 디자인 – 적용 해야 할 것?

도메인 기반 디자인 (DDD)는에 초점을 강조 하는 소프트웨어를 작성 하는 민첩 한 방식에서 *비즈니스 도메인*합니다. 통신 및 실제 시스템 작동 하는 방법을 개발자에 게 연결할 수 있는 비즈니스 도메인 expert(s)와의 상호 작용을 크게 강조를 파악할 수 있습니다. 예를 들어 주식 거래를 처리 하는 시스템을 작성 하는 경우 도메인 전문가 숙련 된 스톡 브로커 수도 있습니다. DDD 대규모의 복잡 한 비즈니스 문제를 해결 하도록 설계 되었습니다과 종종 하지 않습니다를 작고 간단한 응용 프로그램에 대 한 적절 한 이해 하 고 도메인 모델링에 대 한 투자 도움이 되지 않습니다.

기술 이외의 기타 관련자와 참가자 등 팀 개발 해야 DDD 접근 방식에 따라 소프트웨어를 빌드하는 경우는 *유비쿼터스 언어* 꼽자면 문제에 대 한 합니다. 즉, 동일한 용어가 모델링 되는 실제 개념, 소프트웨어를 해당 하는 및 개념 (데이터베이스 테이블 등)를 지 속하는 존재할 수 있는 모든 구조에 사용할 해야 합니다. 유비쿼터스 언어에 설명 된 개념에 대 한 기초를 형성 해야 따라서 프로그램 *도메인 모델*합니다.

시스템의 동작을 나타내는 데 서로 상호 작용 하는 개체의 도메인 모델 구성 됩니다. 이러한 개체는 다음 범주에 해당 될 수 있습니다.

-   [엔터티](http://deviq.com/entity/), 있으며 id의 스레드를 사용 하 여 개체를 나타냅니다. 엔터티는 일반적으로 기준인 나중에 검색할 수 있는 키와 지 속성에 저장 됩니다.

-   [집계](http://deviq.com/aggregate-pattern/), 있으며 하나의 단위로 유지 해야 하는 개체의 그룹을 나타냅니다.

-   [값 개체](http://deviq.com/value-object/), 있으며 속성 값의 합계를 기반으로 비교할 수 있는 개념을 나타냅니다. 예를 들어, 시작 및 종료 날짜의 구성 된 DateRange 합니다.

-   [도메인 이벤트](https://martinfowler.com/eaaDev/DomainEvent.html), 있으며이 시스템의 다른 부분에 관심 있는 시스템 내에서 발생 하는 것을 나타냅니다.

참고 DDD 도메인 모델에 있는 모델 내에서 복잡 한 동작을 캡슐화 해야 합니다. 엔터티, 특히 단순히 안 속성 모음 됩니다. 라고 도메인 모델 동작에 게 없는 경우 단순히 시스템의 상태를 나타내는 경우는 [anemic 모델](http://deviq.com/anemic-model/), ddd에서 바람직하지 않습니다.

DDD에 이러한 모델 형식 외에도 일반적으로 다양 한 패턴에서 적용합니다.

-   [리포지토리](http://deviq.com/repository-pattern/), 지 속성 세부 정보를 추상화에 대 한 합니다.

-   [공장](https://en.wikipedia.org/wiki/Factory_method_pattern), 복잡 한 개체 생성을 캡슐화 하는 데 있습니다.

-   분리 트리거되는 동작 종속 동작에 대 한 도메인 이벤트

-   [서비스](http://gorodinski.com/blog/2012/04/14/services-in-domain-driven-design-ddd/), 캡슐화 복잡 한 동작 및/또는 인프라 구현 세부 정보에 대 한 합니다.

-   [명령](https://en.wikipedia.org/wiki/Command_pattern), 분리에 대 한 명령을 실행 하 고 자체 명령을 실행 합니다.

-   [사양](http://deviq.com/specification-pattern/), 쿼리 세부 정보를 캡슐화 하는 데 있습니다.

또한 DDD 앞에서 설명한 정리 아키텍처를 사용 하는 권장 느슨한 결합, 간략화 및 단위 테스트를 사용 하 여 쉽게 확인할 수 있는 코드에 대 한 허용 합니다.

### <a name="when-should-you-apply-ddd"></a>DDD 적용할 때

DDD는 중요 한 비즈니스 (되지 기술적인) 복잡성 함께 큰 응용 프로그램에 적합 합니다. 응용 프로그램 도메인 전문가의 기술을 해야 합니다. 비즈니스 규칙 및 단순히 저장 하 고 데이터 저장소에서 다양 한 레코드의 현재 상태를 검색 하는 다음 상호 작용을 나타내는 도메인 모델 자체에 중요 한 동작이 있어야 합니다.

### <a name="when-shouldnt-you-apply-ddd"></a>서는 안 적용 하는 경우 DDD

DDD는 모델링, 아키텍처 및 더 작은 응용 프로그램 또는 방금 CRUD (만들기/읽기/업데이트/삭제)는 기본적으로 응용 프로그램에 대해 만들 수 있습니다 하는 통신에 대 한 투자를 해야 합니다. DDD, 다음 응용 프로그램에 가깝지만 도메인 없는 동작으로는 anemic 모델을 알게 하려는 경우 접근 방식을 재구성 해야 합니다. 응용 프로그램 DDD, 필요 하지 않을 또는 데이터베이스 또는 사용자 인터페이스에서 하지 않고 도메인 모델에서 비즈니스 논리를 캡슐화 하는 응용 프로그램을 리팩터링 도움이 필요할 수 있습니다.

혼합 접근 방식을 DDD는 응용 프로그램의 트랜잭션 또는 더 복잡 한 영역에 대 한 아니라 사용 응용 프로그램의 읽기 전용 부분 또는 간단한 CRUD 수 있습니다. 예를 들어, 데이터를 보고서를 표시 하거나 대시보드에 대 한 데이터 시각화를 쿼리 하는 경우 집계의 제약 조건이 있는 채울 필요가 없습니다. 완벽 하 게 이러한 요구 사항에 대 한 별도, 더 간단한 읽기 모델을 가져야 하는 것이 좋습니다.

> ### <a name="references--domain-driven-design"></a>참조 – 도메인 기반 디자인
> - **DDD 내용만 (StackOverflow 응답)**  
> <https://stackoverflow.com/questions/1222392/can-someone-explain-domain-driven-design-ddd-in-plain-english-please/1222488#1222488>

## <a name="deployment"></a>배포

ASP.NET Core 응용 프로그램 호스트 위치에 관계 없이 배포 프로세스와 관련 된 몇 가지 단계가 있습니다. 첫 번째 단계는 변환을 수행할 수 있는 응용 프로그램을 게시 하는 CLI 명령을 게시는 dotnet를 사용 하 여 합니다. 응용 프로그램을 컴파일하 되 고 모든 지정 된 폴더에 응용 프로그램을 실행 하는 데 필요한 파일을 배치 합니다. Visual Studio에서 배포할 때이 단계를 자동으로 수행 됩니다. 게시 폴더에는 응용 프로그램 및 해당 종속성에 대 한.exe 및.dll 파일 포함 되어 있습니다. 자체 포함 된 응용 프로그램에는.NET 런타임 버전도 포함 됩니다. ASP.NET Core 응용 프로그램 구성 파일, 정적 클라이언트 자산, 및 MVC 뷰도 포함 됩니다.

ASP.NET Core 응용 프로그램은 서버를 부팅 하 고 응용 프로그램 (또는 서버)가 충돌 하는 경우 다시 시작 하는 경우 시작 되어야 하는 콘솔 응용 프로그램. 이 프로세스를 자동화 프로세스 관리자를 사용할 수 있습니다. ASP.NET Core에 대 한 가장 일반적인 프로세스 관리자는 Nginx 및 Linux 및 IIS에서 Apache 또는 Windows에서 Windows 서비스입니다.

프로세스 관리자 외에도 Kestrel 웹 서버에서 호스팅되는 ASP.NET Core 응용 프로그램에는 역방향 프록시 서버를 사용 해야 합니다. 역방향 프록시 서버는 인터넷에서 HTTP 요청을 받고를 몇 가지 예비 처리 후 Kestrel에 전달 합니다. 역방향 프록시 서버는 응용 프로그램에 대 한 보안 계층을 제공 하 고 (인터넷에서 트래픽에 노출) 하는 가장자리 배포에 필요한 합니다. Kestrel 비교적 새로운 기능이 며 특정 공격에 대 한 방어를 제공 하지 않습니다. 또한 kestrel 호스트 헤더와 같은 기법 동일한 포트 및 IP 주소에서 여러 응용 프로그램을 사용 하도록 설정 하려면 함께 사용할 수 없도록 같은 포트에서 여러 응용 프로그램을 호스팅 지원 하지 않습니다.

![인터넷에 kestrel](./media/image7-5.png)

그림 7-역방향 프록시 서버 뒤 Kestrel에서 호스팅되는 ASP.NET 5

SSL/HTTPS를 사용 하 여 여러 응용 프로그램을 보호 하는 역방향 프록시 도움이 될 수 있는 다른 시나리오가입니다. 이 경우 역방향 프록시만 ssl이 구성 해야 합니다. 그림 7-6에 나와 있는 것 처럼 역방향 프록시 서버와 Kestrel 간의 통신 HTTP를 통한 위치를 걸릴 수 있습니다.

![](./media/image7-6.png)

그림 7-6 HTTPS 보안 역방향 프록시 서버 뒤에 호스팅되는 ASP.NET

점차 인기를 더해가는 되는 방법은 다음 하거나 될 수 있는 로컬로 호스팅되고 호스팅용 클라우드 기반 Azure에 배포 된 Docker 컨테이너에서 ASP.NET Core 응용 프로그램을 호스트 하는 것입니다. Docker 컨테이너 Kestrel에서 실행 중인 응용 프로그램 코드를 포함 될 수 하 고 위와 같이 역방향 프록시 서버 뒤 배포할 수 있습니다.

Azure에서 응용 프로그램을 호스팅 중인 경우 몇 가지 서비스를 제공 하는 전용된 가상 어플라이언스로 Microsoft Azure 응용 프로그램 게이트웨이 사용할 수 있습니다. 개별 응용 프로그램에 대 한 역방향 프록시 역할을 하는 것 외에도 응용 프로그램 게이트웨이 다음과 같은 기능이 제공할 수도 있습니다.

-   HTTP 부하 분산

-   SSL 오프 로드 (인터넷에만 SSL)

-   End-to-end SSL

-   다중 사이트 라우팅 (단일 응용 프로그램 게이트웨이에 최대 20 개의 사이트 통합)

-   웹 응용 프로그램 방화벽

-   Websocket 지원

-   고급 진단

*장 10의 Azure 배포 옵션에 대해 자세히 알아보기*

> ### <a name="references--deployment"></a>참조 – 배포
> - **호스팅 및 배포 개요**  
> <https://docs.microsoft.com/aspnet/core/publishing/>
> - Kestrel 역방향 프록시를 사용 하는 경우  
> <https://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel#when-to-use-kestrel-with-a-reverse-proxy>
> - **Docker에서 ASP.NET Core 앱 호스트**  
> <https://docs.microsoft.com/aspnet/core/publishing/docker>
> - **Azure 응용 프로그램 게이트웨이 소개합니다.**  
> <https://docs.microsoft.com/azure/application-gateway/application-gateway-introduction>

>[!div class="step-by-step"]
[이전] (공통-클라이언트-쪽-웹-technologies.md) [다음] (work-with-data-in-asp-net-core-apps.md)
