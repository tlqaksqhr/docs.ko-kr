---
title: "ASP.NET Core MVC 앱 개발"
description: "ASP.NET Core와 Azure의 최신 웹 응용 프로그램을 설계 | ASP.NET Core MVC 앱 개발"
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: 54e7ed6fff9ac709e411d0ac1e345c63fd753201
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2017
---
# <a name="develop-aspnet-core-mvc-apps"></a><span data-ttu-id="c396f-103">ASP.NET Core MVC 응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="c396f-103">Develop ASP.NET Core MVC Apps</span></span>

> <span data-ttu-id="c396f-104">"을 내려 처음으로 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-104">"It's not important to get it right the first time.</span></span> <span data-ttu-id="c396f-105">반드시을 내려 마지막 시간입니다. "</span><span class="sxs-lookup"><span data-stu-id="c396f-105">It's vitally important to get it right the last time."</span></span>  
> <span data-ttu-id="c396f-106">_-Andrew 사냥과 David Thomas_</span><span class="sxs-lookup"><span data-stu-id="c396f-106">_- Andrew Hunt and David Thomas_</span></span>

## <a name="summary"></a><span data-ttu-id="c396f-107">요약</span><span class="sxs-lookup"><span data-stu-id="c396f-107">Summary</span></span>

<span data-ttu-id="c396f-108">ASP.NET Core는 최신 클라우드 액세스에 최적화 된 웹 응용 프로그램을 빌드하기 위한 플랫폼, 오픈 소스 프레임 워크입니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-108">ASP.NET Core is a cross-platform, open-source framework for building modern cloud-optimized web applications.</span></span> <span data-ttu-id="c396f-109">ASP.NET Core 응용 프로그램은 간단한 및 큰 테스트 용이성 및 유지 관리에 사용 되는 종속성 주입을 위한 기본 제공 지원으로 모듈식입니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-109">ASP.NET Core apps are lightweight and modular, with built-in support for dependency injection, enabling in greater testability and maintainability.</span></span> <span data-ttu-id="c396f-110">엔터프라이즈 웹 응용 프로그램을 빌드할 수 있는 강력한 프레임 워크를 ASP.NET Core MVC 뷰 기반 응용 프로그램 뿐만 아니라 최신 웹 Api 작성을 지 원하는와 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-110">Combined with MVC, which supports building modern web APIs in addition to view-based apps, ASP.NET Core is a powerful framework with which to build enterprise web applications.</span></span>

## <a name="mapping-requests-to-responses"></a><span data-ttu-id="c396f-111">요청 응답에 매핑</span><span class="sxs-lookup"><span data-stu-id="c396f-111">Mapping Requests to Responses</span></span>

<span data-ttu-id="c396f-112">기본적으로 다중에서 ASP.NET Core 응용 프로그램을 나가는 응답 들어오는 요청을 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-112">At its heart, ASP.NET Core apps map incoming requests to outgoing responses.</span></span> <span data-ttu-id="c396f-113">낮은 수준에서 미들웨어를 사용 하 고 간단한 ASP.NET Core 응용 프로그램 및 microservices 사용자 지정 미들웨어의만 구성 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-113">At a low level, this is done with middleware, and simple ASP.NET Core apps and microservices may be comprised solely of custom middleware.</span></span> <span data-ttu-id="c396f-114">측면에서 생각할 높은 수준에서 작업할 수 ASP.NET Core MVC를 사용 하면 *경로*, *컨트롤러*, 및 *동작*합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-114">When using ASP.NET Core MVC, you can work at a somewhat higher level, thinking in terms of *routes*, *controllers*, and *actions*.</span></span> <span data-ttu-id="c396f-115">응용 프로그램의 라우팅 테이블을 들어오는 각 요청은 비교 하 고, 일치 하는 경로가 있으면 요청을 처리할 (컨트롤러에 속하는) 연결 된 동작 메서드가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-115">Each incoming request is compared with the application's routing table, and if a matching route is found, the associated action method (belonging to a controller) is called to handle the request.</span></span> <span data-ttu-id="c396f-116">일치 하는 경로가 없는 발견 되 면 (NotFound 결과 반환 합니다.이 경우)에서 오류 처리기가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-116">If no matching route is found, an error handler (in this case, returning a NotFound result) is called.</span></span>

<span data-ttu-id="c396f-117">ASP.NET Core MVC 앱 규칙에 따른 경로, 특성 경로 또는 둘 다 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-117">ASP.NET Core MVC apps can use conventional routes, attribute routes, or both.</span></span> <span data-ttu-id="c396f-118">라우팅을 지정 하는 코드에서 정의 된 규칙에 따른 경로 *규칙* 아래 예제에서는 같은 구문을 사용 하 여:</span><span class="sxs-lookup"><span data-stu-id="c396f-118">Conventional routes are defined in code, specifying routing *conventions* using syntax like in the example below:</span></span>

```csharp
app.UseMvc(routes =>;
{
    routes.MapRoute("default","{controller=Home}/{action=Index}/{id?}");
});
```

<span data-ttu-id="c396f-119">이 예제에서는 "default" 라는 경로 라우팅 테이블에 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-119">In this example, a route named "default" has been added to the routing table.</span></span> <span data-ttu-id="c396f-120">에 대 한 자리 표시자를 포함 하는 경로 템플릿을 정의 *컨트롤러*, *동작*, 및 *id*합니다. 컨트롤러 및 작업 자리 표시자 기본값이 지정 되어 ("홈" 및 "인덱스"를 각각), id 자리 표시자는 선택 사항 (인해는 "?" 적용).</span><span class="sxs-lookup"><span data-stu-id="c396f-120">It defines a route template with placeholders for *controller*, *action*, and *id*. The controller and action placeholders have default specified ("Home" and "Index", respectively), and the id placeholder is optional (by virtue of a "?" applied to it).</span></span> <span data-ttu-id="c396f-121">규칙에 따라 여기에 정의 된 상태는 요청의 첫 번째 부분 일치 해야 하는 작업에 두 번째 부분은 컨트롤러의 이름을 나타내고 필요에 따라 세 번째 부분은 됩니다는 id 매개 변수.</span><span class="sxs-lookup"><span data-stu-id="c396f-121">The convention defined here states that the first part of a request should correspond to the name of the controller, the second part to the action, and then if necessary a third part will represent an id parameter.</span></span> <span data-ttu-id="c396f-122">기본 경로 시작 클래스의 구성 메서드에서 같은 응용 프로그램을 한 곳에 일반적으로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-122">Conventional routes are typically defined in one place for the application, such as in the Configure method in the Startup class.</span></span>

<span data-ttu-id="c396f-123">특성 경로 전역적으로 지정 되지 않고 직접, 컨트롤러 및 작업에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-123">Attribute routes are applied to controllers and actions directly, rather than specified globally.</span></span> <span data-ttu-id="c396f-124">이 특정 메서드를 찾고 있지만 라우팅 정보가 응용 프로그램에서 한 곳에 저장 되지 않습니다는 의미 하는 경우 훨씬 더 쉽게 검색할 수 있게의 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-124">This has the advantage of making them much more discoverable when you're looking at a particular method, but does mean that routing information is not kept in one place in the application.</span></span> <span data-ttu-id="c396f-125">특성 경로와 있습니다 수 쉽게 지정된 된 동작에 대 한 여러 경로 지정으로 컨트롤러 및 작업 간 경로 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-125">With attribute routes, you can easily specify multiple routes for a given action, as well as combine routes between controllers and actions.</span></span> <span data-ttu-id="c396f-126">예:</span><span class="sxs-lookup"><span data-stu-id="c396f-126">For example:</span></span>

```csharp
[Route("Home")]
public class HomeController : Controller
{
    [Route("")] // Combines to define the route template "Home"
    [Route("Index")] // Combines to define route template "Home/Index"
    [Route("/")] // Does not combine, defines the route template ""
    public IActionResult Index() {}
```

<span data-ttu-id="c396f-127">[HttpGet]에 경로 지정할 수 있습니다 및 비슷한 특성을 추가할 필요가 없도록 분리 [경로\] 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-127">Routes can be specified on [HttpGet] and similar attributes, avoiding the need to add separate [Route\] attributes.</span></span> <span data-ttu-id="c396f-128">특성 경로 토큰을 사용 하 여 아래와 같이 이름, 컨트롤러 또는 작업을 반복할 필요가 줄이기 위해 수 있습니다.:</span><span class="sxs-lookup"><span data-stu-id="c396f-128">Attribute routes can also use tokens to reduce the need to repeat controller or action names, as shown below:</span></span>

```csharp
[Route("[controller\]")]
public class ProductsController : Controller
{
    [Route("")] // Matches 'Products'
    [Route("Index")] // Matches 'Products/Index'
    public IActionResult Index()
}
```

<span data-ttu-id="c396f-129">지정된 된 요청을 경로에 일치 작업 전에 메서드가 호출 되 면 ASP.NET Core MVC 수행될지 [모델 바인딩](https://docs.microsoft.com/aspnet/core/mvc/models/model-binding) 및 [유효성 검사 모델](https://docs.microsoft.com/aspnet/core/mvc/models/validation) 요청에 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-129">Once a given request has been matched to a route, but before the action method is called, ASP.NET Core MVC will perform [model binding](https://docs.microsoft.com/aspnet/core/mvc/models/model-binding) and [model validation](https://docs.microsoft.com/aspnet/core/mvc/models/validation) on the request.</span></span> <span data-ttu-id="c396f-130">모델 바인딩에 들어오는 HTTP 데이터를 호출할 수는 동작 메서드의 매개 변수로 지정 된.NET 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-130">Model binding is responsible for converting incoming HTTP data into the .NET types specified as parameters of the action method to be called.</span></span> <span data-ttu-id="c396f-131">예를 들어 들어 동작 메서드가 요구는 int id 매개 변수, 모델 바인딩 요청의 일부로 제공 된 값에서이 매개 변수를 제공 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-131">For example, if the action method expects an int id parameter, model binding will attempt to provide this parameter from a value provided as part of the request.</span></span> <span data-ttu-id="c396f-132">이렇게 하려면 게시 된 폼 값, 경로 자체의 값 및 쿼리 문자열 값에 대 한 모델 바인딩이 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-132">To do so, model binding looks for values in a posted form, values in the route itself, and query string values.</span></span> <span data-ttu-id="c396f-133">Id 값을 찾으면 라고 가정할 경우이 변환 됩니다는 정수 작업 메서드로 전달 하기 전에.</span><span class="sxs-lookup"><span data-stu-id="c396f-133">Assuming an id value is found, it will be converted to an integer before being passed into the action method.</span></span>

<span data-ttu-id="c396f-134">모델을 바인딩한 후 표시 되지만 작업 메서드를 호출 하기 전에 모델 유효성 검사가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-134">After binding the model but before calling the action method, model validation occurs.</span></span> <span data-ttu-id="c396f-135">모델 유효성 검사 모델 형식에 선택적 특성을 사용 하 고 제공 된 모델 개체에 특정 데이터 요구 사항을 준수 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-135">Model validation uses optional attributes on the model type, and can help ensure that the provided model object conforms to certain data requirements.</span></span> <span data-ttu-id="c396f-136">특정 값으로 지정할 수 있습니다, 필요한 또는 특정 길이 나 숫자 범위 제한, 등입니다. 유효성 검사 특성을 지정 하는 경우 모델의 요구 사항에 맞지 않는 속성 ModelState.IsValid을 false 되며 실패 유효성 검사 규칙의 집합 요청을 만드는 클라이언트에 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-136">Certain values may be specified as required, or limited to a certain length or numeric range, etc. If validation attributes are specified but the model does not conform to their requirements, the property ModelState.IsValid will be false, and the set of failing validation rules will be available to send to the client making the request.</span></span>

<span data-ttu-id="c396f-137">모델 유효성 검사를 사용 하는 경우에 항상 모든 상태 변경 명령을 앱 잘못 된 데이터가 손상 되지 않았는지 확인을 수행 하기 전에 모델이 유효한 지를 확인 해야 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-137">If you are using model validation, you should be sure to always check that the model is valid before performing any state-altering commands, to ensure your app is not corrupted by invalid data.</span></span> <span data-ttu-id="c396f-138">사용할 수는 [필터](https://docs.microsoft.com/aspnet/core/mvc/controllers/filters) 코드를 추가 하려면이 대 한 모든 작업에 필요 하면 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-138">You can use a [filter](https://docs.microsoft.com/aspnet/core/mvc/controllers/filters) to avoid the need to add code for this in every action.</span></span> <span data-ttu-id="c396f-139">ASP.NET Core MVC 필터 일반적인 정책 및 일반적인 문제를 대상으로 적용할 수 있도록 그룹 요청을 가로채는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-139">ASP.NET Core MVC filters offer a way of intercepting groups of requests, so that common policies and cross-cutting concerns can be applied on a targeted basis.</span></span> <span data-ttu-id="c396f-140">개별 작업을 전체 컨트롤러 또는 응용 프로그램에 대 한 전역 필터를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-140">Filters can be applied to individual actions, whole controllers, or globally for an application.</span></span>

<span data-ttu-id="c396f-141">ASP.NET Core MVC 웹 Api에 대 한 지원 [ *콘텐츠 협상*](https://docs.microsoft.com/aspnet/core/mvc/models/formatting), 때문에 요청이 응답 해야 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-141">For web APIs, ASP.NET Core MVC supports [*content negotiation*](https://docs.microsoft.com/aspnet/core/mvc/models/formatting), allowing requests to specify how responses should be formatted.</span></span> <span data-ttu-id="c396f-142">요청에 제공 하는 헤더에 따라, 데이터 반환 작업은 응답 XML, JSON, 또는 다른 지원 되는 형식에 서식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-142">Based on headers provided in the request, actions returning data will format the response in XML, JSON, or another supported format.</span></span> <span data-ttu-id="c396f-143">이 기능에는 동일한 API를 다른 데이터 형식 요구 사항을 여러 클라이언트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-143">This feature enables the same API to be used by multiple clients with different data format requirements.</span></span>

> ### <a name="references--mapping-requests-to-responses"></a><span data-ttu-id="c396f-144">참조 – 요청 응답에 매핑</span><span class="sxs-lookup"><span data-stu-id="c396f-144">References – Mapping Requests to Responses</span></span>
> - <span data-ttu-id="c396f-145">**컨트롤러 작업에 대 한 라우팅을**
> <https://docs.microsoft.com/aspnet/core/mvc/controllers/routing></span><span class="sxs-lookup"><span data-stu-id="c396f-145">**Routing to Controller Actions**
<https://docs.microsoft.com/aspnet/core/mvc/controllers/routing></span></span>
> - <span data-ttu-id="c396f-146">**모델 바인딩** https://docs.microsoft.com/aspnet/core/mvc/models/model-binding</span><span class="sxs-lookup"><span data-stu-id="c396f-146">**Model Binding** https://docs.microsoft.com/aspnet/core/mvc/models/model-binding</span></span>
> - <span data-ttu-id="c396f-147">**유효성 검사 모델**
> <https://docs.microsoft.com/aspnet/core/mvc/models/validation></span><span class="sxs-lookup"><span data-stu-id="c396f-147">**Model Validation**
<https://docs.microsoft.com/aspnet/core/mvc/models/validation></span></span>
> - <span data-ttu-id="c396f-148">**필터** https://docs.microsoft.com/aspnet/core/mvc/controllers/filters</span><span class="sxs-lookup"><span data-stu-id="c396f-148">**Filters** https://docs.microsoft.com/aspnet/core/mvc/controllers/filters</span></span>

## <a name="working-with-dependencies"></a><span data-ttu-id="c396f-149">종속성 사용</span><span class="sxs-lookup"><span data-stu-id="c396f-149">Working with Dependencies</span></span>

<span data-ttu-id="c396f-150">ASP.NET Core에서 기본적으로 지원 하 고에서는 기술을 활용 하는 내부적으로 [종속성 주입](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection)합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-150">ASP.NET Core has built-in support for and internally makes use of a technique known as [dependency injection](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection).</span></span> <span data-ttu-id="c396f-151">종속성 주입 방법은 응용 프로그램의 다른 부분 간의 느슨한 결합을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-151">Dependency injection is a technique that enabled loose coupling between different parts of an application.</span></span> <span data-ttu-id="c396f-152">이보다 결합 하면 손쉽게 테스트 또는 교체 허용 범위를 응용 프로그램의 일부를 격리 하기 때문에 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-152">Looser coupling is desirable because it makes it easier to isolate parts of the application, allowing for testing or replacement.</span></span> <span data-ttu-id="c396f-153">하기가 응용 프로그램의 한 부분에 있는 변경 다른 위치에서 응용 프로그램에 예기치 않은 영향을 미치게 됩니다는 가능성이 더 낮아집니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-153">It also makes it less likely that a change in one part of the application will have an unexpected impact somewhere else in the application.</span></span> <span data-ttu-id="c396f-154">종속성 주입 종속성 반전 원칙에 따라이 고, 열기/닫기 원칙을 구현 하려면 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-154">Dependency injection is based on the dependency inversion principle, and is often key to achieving the open/closed principle.</span></span> <span data-ttu-id="c396f-155">응용 프로그램이 종속성과 함께 작동 하는 방법을 평가할 때는 조심는 [정적 문에 붙이는](http://deviq.com/static-cling/) 후 각 코드 하 고는 aphorism 기억 "[새 작업은](http://ardalis.com/new-is-glue)."</span><span class="sxs-lookup"><span data-stu-id="c396f-155">When evaluating how your application works with its dependencies, beware of the [static cling](http://deviq.com/static-cling/) code smell, and remember the aphorism "[new is glue](http://ardalis.com/new-is-glue)."</span></span>

<span data-ttu-id="c396f-156">정적 문에 붙이는 클래스에 정적 메서드를 호출 하거나 인프라에 대 한 부작용 또는 종속성 정적 속성에 액세스 하는 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-156">Static cling occurs when your classes make calls to static methods, or access static properties, which have side effects or dependencies on infrastructure.</span></span> <span data-ttu-id="c396f-157">예를 들어 데이터베이스에 다시 기록, 정적 메서드를 호출 하는 메서드를 설정한 경우 메서드는 밀접 하 게 데이터베이스에 관련 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-157">For example, if you have a method that calls a static method, which in turn writes to a database, your method is tightly coupled to the database.</span></span> <span data-ttu-id="c396f-158">아무 것도 해당 데이터베이스 호출을 중단 하는 방법에 끊어집니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-158">Anything that breaks that database call will break your method.</span></span> <span data-ttu-id="c396f-159">이러한 메서드 까다로운가 있으므로 테스트를 이러한 테스트를 정적 호출 모의 상용 모의 개체 라이브러리가 필요 하거나 현재 위치에서 테스트 데이터베이스와 함께 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-159">Testing such methods is notoriously difficult, since such tests either require commercial mocking libraries to mock the static calls, or can only be tested with a test database in place.</span></span> <span data-ttu-id="c396f-160">특히는 완전히 상태를 저장 하는 인프라에 대 한 모든 종속성을 갖지 않는 정적 호출은 됩니다 세밀 하 게 호출 하 고 결합 또는 테스트 용이성 (정적 호출 자체에 코드를 결합) 외에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-160">Static calls that don't have any dependence on infrastructure, especially those that are completely stateless, are fine to call and have no impact on coupling or testability (beyond coupling code to the static call itself).</span></span>

<span data-ttu-id="c396f-161">대부분의 개발자 문에 붙이는 정적 및 전역 상태의 위험이 있지만 직접 인스턴스화를 통해 특정 구현에 코드를 여전히 밀접 하 게 결합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-161">Many developers understand the risks of static cling and global state, but will still tightly couple their code to specific implementations through direct instantiation.</span></span> <span data-ttu-id="c396f-162">"새는 글 루" 결합이 미리 알림 및 new 키워드의 사용의 일반적인 condemnation 하지 알 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-162">"New is glue" is meant to be a reminder of this coupling, and not a general condemnation of the use of the new keyword.</span></span> <span data-ttu-id="c396f-163">과 마찬가지로 정적 메서드 호출 일반적으로 외부 종속성이 없는 형식의 새 인스턴스 하지 밀접 하 게 구현 세부 정보를 코드를 결합에 있거나 테스트 더 어렵게 만들 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-163">Just as with static method calls, new instances of types that have no external dependencies typically do not tightly couple code to implementation details or make testing more difficult.</span></span> <span data-ttu-id="c396f-164">그러나는 클래스를 인스턴스화할 때마다 걸릴 잠시 또는 종속성으로 해당 인스턴스를 요청 하려면 더 나은 디자인 하는 의미가 하드 코딩 특정 인스턴스에 해당 특정 위치에 있는지 여부를 고려해 야 할 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-164">But each time a class is instantiated, take just a brief moment to consider whether it makes sense to hard-code that specific instance in that particular location, or if it would be a better design to request that instance as a dependency.</span></span>

### <a name="declare-your-dependencies"></a><span data-ttu-id="c396f-165">종속성을 선언</span><span class="sxs-lookup"><span data-stu-id="c396f-165">Declare Your Dependencies</span></span>

<span data-ttu-id="c396f-166">ASP.NET Core 메서드 것으로 구축 되었습니다 및 클래스를 인수로 요청 하는 해당 종속성을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-166">ASP.NET Core is built around having methods and classes declare their dependencies, requesting them as arguments.</span></span> <span data-ttu-id="c396f-167">ASP.NET 응용 프로그램 시작 클래스에서 설정 일반적으로 하는 시점에 종속성 주입을 지원 하도록 구성 된 논리입니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-167">ASP.NET applications are typically set up in a Startup class, which itself is configured to support dependency injection at several points.</span></span> <span data-ttu-id="c396f-168">생성자를 통해 종속성을 요청할 수 있는 경우 시작 클래스에 생성자 같이:</span><span class="sxs-lookup"><span data-stu-id="c396f-168">If your Startup class has a constructor, it can request dependencies through the constructor, like so:</span></span>

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

<span data-ttu-id="c396f-169">시작 클래스에 대 한 명시적 형식 요구는 흥미로운 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-169">The Startup class is interesting in that there are no explicit type requirements for it.</span></span> <span data-ttu-id="c396f-170">특별 한 시작 기본 클래스에서 상속 하지 않습니다 하거나 특정 인터페이스를 구현지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-170">It doesn't inherit from a special Startup base class, nor does it implement any particular interface.</span></span> <span data-ttu-id="c396f-171">지정할 수 있습니다는 생성자를 한 수의 매개 변수는 생성자에서 원하는 대로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-171">You can give it a constructor, or not, and you can specify as many parameters on the constructor as you want.</span></span> <span data-ttu-id="c396f-172">응용 프로그램에 대해 구성 하는 웹 호스트 시작 시작 클래스를 사용 하도록 지시를 호출 합니다 또는 시작 클래스에 필요한 모든 종속성을 채우는 데 종속성 주입을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-172">When the web host you've configured for your application starts, it will call the Startup class you've told it to use, and will use dependency injection to populate any dependencies the Startup class requires.</span></span> <span data-ttu-id="c396f-173">물론, ASP.NET Core에서 사용 하는 서비스 컨테이너에 구성 되지 않은 매개 변수를 요청 하는 경우 예외를 받습니다 하지만 종속성에 집중으로 컨테이너에 대해 알고를 원하는 대로 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-173">Of course, if you request parameters that aren't configured in the services container used by ASP.NET Core, you'll get an exception, but as long as you stick to dependencies the container knows about, you can request anything you want.</span></span>

<span data-ttu-id="c396f-174">종속성 주입 시작 인스턴스를 만들 때, 처음부터 ASP.NET Core 응용 프로그램에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-174">Dependency injection is built into your ASP.NET Core apps right from the start, when you create the Startup instance.</span></span> <span data-ttu-id="c396f-175">여기서 시작 클래스에 대 한 중지 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-175">It doesn't stop there for the Startup class.</span></span> <span data-ttu-id="c396f-176">Configure 메서드에서 종속성을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-176">You can also request dependencies in the Configure method:</span></span>

```csharp
public void Configure(IApplicationBuilder app,
    IHostingEnvironment env,
    ILoggerFactory loggerFactory)
{

}
```

<span data-ttu-id="c396f-177">ConfigureServices 메서드는이 동작에 대 한 예외 IServiceCollection 형식의 매개 변수 하나에 수행 해야 할 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-177">The ConfigureServices method is the exception to this behavior; it must take just one parameter of type IServiceCollection.</span></span> <span data-ttu-id="c396f-178">가구의 서비스 컨테이너에 개체를 추가 하는 일을 담당 하는 한편 IServiceCollection 매개 변수를 통해 모든 현재 구성 된 서비스를 수행할 액세스 권한이 다른 종속성 주입을 지원 하기 위해 실제로 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-178">It doesn't really need to support dependency injection, since on the one hand it is responsible for adding objects to the services container, and on the other it has access to all currently configured services via the IServiceCollection parameter.</span></span> <span data-ttu-id="c396f-179">따라서 매개 변수로 필요한 서비스를 요청 하거나 IServiceCollection ConfigureServices에서 사용 하 여 시작 클래스의 모든 부분에서 ASP.NET Core 서비스 컬렉션에 정의 된 종속성 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-179">Thus, you can work with dependencies defined in the ASP.NET Core services collection in every part of the Startup class, either by requesting the needed service as a parameter or by working with the IServiceCollection in ConfigureServices.</span></span>

> [!NOTE]
> <span data-ttu-id="c396f-180">특정 서비스를 시작 클래스를 사용할 수 있는지 확인 해야 할 경우 구성할 수 있습니다 WebHostBuilder와 해당 ConfigureServices 메서드를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-180">If you need to ensure certain services are available to your Startup class, you can configure them using WebHostBuilder and its ConfigureServices method.</span></span>

<span data-ttu-id="c396f-181">시작 클래스는 자신의 서비스에 대 한 필터를 미들웨어 컨트롤러에서 ASP.NET Core 응용 프로그램의 다른 부분을 구성 해야 하는 것에 대 한 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-181">The Startup class is a model for how you should structure other parts of your ASP.NET Core application, from Controllers to Middleware to Filters to your own Services.</span></span> <span data-ttu-id="c396f-182">각각의 경우에 따라야는 [명시적 종속성 원칙](http://deviq.com/explicit-dependencies-principle/), 종속성 요청 하지 않고 직접 만들기, 및 응용 프로그램에서 종속성 주입을 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-182">In each case, you should follow the [Explicit Dependencies Principle](http://deviq.com/explicit-dependencies-principle/), requesting your dependencies rather than directly creating them, and leveraging dependency injection throughout your application.</span></span> <span data-ttu-id="c396f-183">구현에서는 특히 서비스 및 인프라를 사용 하거나 의도 하지 않은 개체를 직접 인스턴스화할 위치와 방법을 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-183">Be careful of where and how you directly instantiate implementations, especially services and objects that work with infrastructure or have side effects.</span></span> <span data-ttu-id="c396f-184">추상화 형식 특정 구현에 하드 코딩 참조에 대 한 인수로 전달 하 고 응용 프로그램 코어에 정의 된 사용을 선호 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-184">Prefer working with abstractions defined in your application core and passed in as arguments to hardcoding references to specific implementation types.</span></span>

## <a name="structuring-the-application"></a><span data-ttu-id="c396f-185">응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="c396f-185">Structuring the Application</span></span>

<span data-ttu-id="c396f-186">일반적으로 단일 응용 프로그램의 단일 진입점을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-186">Monolithic applications typically have a single entry point.</span></span> <span data-ttu-id="c396f-187">ASP.NET Core 웹 응용 프로그램의 경우 진입점 ASP.NET Core 웹 프로젝트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-187">In the case of an ASP.NET Core web application, the entry point will be the ASP.NET Core web project.</span></span> <span data-ttu-id="c396f-188">그러나 솔루션이 하나의 프로젝트만 구성 되어야 한다는 의미 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-188">However, that doesn't mean the solution should consist of just a single project.</span></span> <span data-ttu-id="c396f-189">문제의 분리를 수행 하려면 다른 계층으로 응용 프로그램을 중단 하는 것이 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-189">It's useful to break up the application into different layers in order to follow separation of concerns.</span></span> <span data-ttu-id="c396f-190">계층으로 분리 되 면를 별도 프로젝트로 효율적으로 캡슐화를 달성 하는 데 도움이 되는 폴더 외에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-190">Once broken up into layers, it's helpful to go beyond folders to separate projects, which can help achieve better encapsulation.</span></span> <span data-ttu-id="c396f-191">ASP.NET Core 응용 프로그램으로 이러한 목표를 달성 하는 좋은 방법이 5 장에 설명 된 정리 아키텍처의 변형입니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-191">The best approach to achieve these goals with an ASP.NET Core application is a variation of the Clean Architecture discussed in chapter 5.</span></span> <span data-ttu-id="c396f-192">이 방법에서는 다음 인프라 및 ApplicationCore, UI에 대 한 응용 프로그램의 솔루션 별도 라이브러리 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-192">Following this approach, the application's solution will be comprised of separate libraries for the UI, Infrastructure, and ApplicationCore.</span></span>

<span data-ttu-id="c396f-193">이러한 프로젝트 뿐만 아니라 별도 테스트 프로젝트도 포함 (테스트 장 9에 설명 되어 있음).</span><span class="sxs-lookup"><span data-stu-id="c396f-193">In addition to these projects, separate test projects are included as well (Testing is discussed in Chapter 9).</span></span>

<span data-ttu-id="c396f-194">응용 프로그램의 개체 모델 및 인터페이스 ApplicationCore 프로젝트에 배치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-194">The application's object model and interfaces should be placed in the ApplicationCore project.</span></span> <span data-ttu-id="c396f-195">이 프로젝트를 가능한 적은 종속성을 갖습니다 하 고 솔루션의 다른 프로젝트에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-195">This project will have as few dependencies as possible, and the other projects in the solution will reference it.</span></span> <span data-ttu-id="c396f-196">직접 인프라에 종속 되지 않는 서비스는 유지 해야 하는 비즈니스 엔터티 ApplicationCore 프로젝트에서 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-196">Business entities that need to be persisted are defined in the ApplicationCore project, as are services that do not directly depend on infrastructure.</span></span>

<span data-ttu-id="c396f-197">지 속성을 수행 하는 방법 또는 사용자에 게 알림을 전송 될 수 있습니다 어떻게 같은 구현 세부 인프라 프로젝트에 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-197">Implementation details, such as how persistence is performed or how notifications might be sent to a user, are kept in the Infrastructure project.</span></span> <span data-ttu-id="c396f-198">이 프로젝트는 Entity Framework Core와 같은 구현 별 패키지를 참조 하지만 프로젝트 외부에서 이러한 구현에 대 한 세부 정보를 노출 하면 안 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-198">This project will reference implementation-specific packages such as Entity Framework Core, but should not expose details about these implementations outside of the project.</span></span> <span data-ttu-id="c396f-199">인프라 서비스 및 저장소 ApplicationCore 프로젝트에 정의 된 인터페이스를 구현 해야 하 고 지 속성 구현 과정은 검색 하 고 ApplicationCore에 정의 된 엔터티를 저장 하는 일을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-199">Infrastructure services and repositories should implement interfaces that are defined in the ApplicationCore project, and its persistence implementations are responsible for retrieving and storing entities defined in ApplicationCore.</span></span>

<span data-ttu-id="c396f-200">ASP.NET Core 프로젝트 자체는 UI 수준 문제를 담당 하지만 비즈니스 논리 나 인프라 세부 정보를 포함 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-200">The ASP.NET Core project itself is responsible for any UI level concerns, but should not include business logic or infrastructure details.</span></span> <span data-ttu-id="c396f-201">사실, 이상적으로 것도 없어야 종속성 인프라 프로젝트를 구성 하면 두 개의 프로젝트 간의 종속성 없이 실수로 도입 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-201">In fact, ideally it shouldn't even have a dependency on the Infrastructure project, which will help ensure no dependency between the two projects is introduced accidentally.</span></span> <span data-ttu-id="c396f-202">각 프로젝트에 대 한 레지스트리 클래스에서 DI 규칙을 정의할 수 있는 StructureMap 같은 제 3 자 DI 컨테이너 사용 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-202">This can be achieved using a third-party DI container like StructureMap, which allows you to define DI rules in Registry classes in each project.</span></span>

<span data-ttu-id="c396f-203">또 다른 방법은 구현 세부 사항 으로부터 응용 프로그램을 분리 하는 아마도 개별 Docker 컨테이너에 배포 하는 응용 프로그램 호출 microservices을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-203">Another approach to decoupling the application from implementation details is to have the application call microservices, perhaps deployed in individual Docker containers.</span></span> <span data-ttu-id="c396f-204">이 고려 사항 및 분리 DI를 활용 하 여 두 개의 프로젝트 간에 보다 더 높은 분리를 제공 하지만 더 복잡해졌습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-204">This provides even greater separation of concerns and decoupling than leveraging DI between two projects, but has additional complexity.</span></span>

### <a name="feature-organization"></a><span data-ttu-id="c396f-205">기능 조직</span><span class="sxs-lookup"><span data-stu-id="c396f-205">Feature Organization</span></span>

<span data-ttu-id="c396f-206">기본적으로 ASP.NET Core 응용 프로그램 컨트롤러와 뷰 및 자주 Viewmodel 포함 하도록 해당 폴더 구조를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-206">By default, ASP.NET Core applications organize their folder structure to include Controllers and Views, and frequently ViewModels.</span></span> <span data-ttu-id="c396f-207">이러한 서버 쪽 구조를 지원 하기 위해 클라이언트 쪽 코드는 일반적으로 wwwroot 폴더에서 별도로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-207">Client-side code to support these server-side structures is typically stored separately in the wwwroot folder.</span></span> <span data-ttu-id="c396f-208">그러나 대규모 응용 프로그램 필요한 기능에서 작업 하는 종종 이러한 폴더 사이 이동 필요 하므로이 조직에 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-208">However, large applications may encounter problems with this organization, since working on any given feature often requires jumping between these folders.</span></span> <span data-ttu-id="c396f-209">이 더 어려운 늘어나면 각 폴더의 파일과 하위 폴더 수 있는 다양 한 솔루션 탐색기를 통해 스크롤에 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-209">This gets more and more difficult as the number of files and subfolders in each folder grows, resulting in a great deal of scrolling through Solution Explorer.</span></span> <span data-ttu-id="c396f-210">이 문제에 대 한 한 가지 해결 하 여 응용 프로그램 코드를 구성 하는 *기능* 순서가 아니라 파일 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-210">One solution to this problem is to organize application code by *feature* instead of by file type.</span></span> <span data-ttu-id="c396f-211">이 조직 스타일은 일반적으로 기능 폴더 또는 라고 기능 분할 영역 (참고 항목: [수직 분할 영역](http://deviq.com/vertical-slices/)).</span><span class="sxs-lookup"><span data-stu-id="c396f-211">This organizational style is typically referred to as feature folders or feature slices (see also: [Vertical Slices](http://deviq.com/vertical-slices/)).</span></span>

<span data-ttu-id="c396f-212">ASP.NET Core MVC이이 용도 대 한 영역을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-212">ASP.NET Core MVC supports Areas for this purpose.</span></span> <span data-ttu-id="c396f-213">영역을 사용 하 여 별도의 컨트롤러 및 보기 폴더 (으로 모든 관련된 모델)에서 각 영역 폴더 집합을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-213">Using areas, you can create separate sets of Controllers and Views folders (as well as any associated models) in each Area folder.</span></span> <span data-ttu-id="c396f-214">그림 7-1 영역을 사용 하는 예제 폴더 구조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-214">Figure 7-1 shows an example folder structure, using Areas.</span></span>

![](./media/image7-1.png)

<span data-ttu-id="c396f-215">그림 7-1 샘플 영역 조직</span><span class="sxs-lookup"><span data-stu-id="c396f-215">Figure 7-1 Sample Area Organization</span></span>

<span data-ttu-id="c396f-216">영역을 사용 하는 경우를 위해 컨트롤러 소속 된 영역의 이름을를 데코레이팅하 특성을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-216">When using Areas, you must use attributes to decorate your controllers with the name of the area to which they belong:</span></span>

```csharp
[Area("Catalog")]
public class HomeController
{}
```

<span data-ttu-id="c396f-217">또한 해야 사용자 경로에 영역 지원을 추가 하려면:</span><span class="sxs-lookup"><span data-stu-id="c396f-217">You also need to add area support to your routes:</span></span>

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

<span data-ttu-id="c396f-218">영역에 대 한 기본 제공 지원을 외에도 고유한 폴더 구조 및 대신 특성 및 사용자 지정 경로 규칙을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-218">In addition to the built-in support for Areas, you can also use your own folder structure, and conventions in place of attributes and custom routes.</span></span> <span data-ttu-id="c396f-219">그러면 뷰, 컨트롤러, 계층 구조를 일반적인 방법으로 유지 하 고 모든 관련 파일을 한 곳에서 각 기능에 대 한 참조를 더욱 쉽게 등에 대 한 별도 폴더를 포함 하지 않은 기능 폴더를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-219">This would allow you to have feature folders that didn't include separate folders for Views, Controllers, etc., keeping the hierarchy flatter and making it easier to see all related files in a single place for each feature.</span></span>

<span data-ttu-id="c396f-220">ASP.NET Core 기본 제공 규칙 형식을 사용 하 여 동작을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-220">ASP.NET Core uses built-in convention types to control its behavior.</span></span> <span data-ttu-id="c396f-221">수정 하거나 이러한 규칙을 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-221">You can modify or replace these conventions.</span></span> <span data-ttu-id="c396f-222">예를 들어, 해당 네임 스페이스 (일반적으로 컨트롤러의 위치를 가리키는 폴더와 관련이)에 따라 지정 된 컨트롤러에 대 한 기능 이름을 받습니다 자동으로 포함 하는 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-222">For example, you can create a convention that will automatically get the feature name for a given controller based on its namespace (which typically correlates to the folder in which the controller is located):</span></span>

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

<span data-ttu-id="c396f-223">그런 다음 지정할수록이 규칙 옵션으로 ConfigureServices에서 응용 프로그램에 대 한 MVC에 대 한 지원을 추가 하면:</span><span class="sxs-lookup"><span data-stu-id="c396f-223">You then specify this convention as an option when you add support for MVC to your application in ConfigureServices:</span></span>

```csharp
services.AddMvc(o => o.Conventions.Add(new FeatureConvention()));
```

<span data-ttu-id="c396f-224">또한 ASP.NET Core MVC 보기를 찾는 한 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-224">ASP.NET Core MVC also uses a convention to locate views.</span></span> <span data-ttu-id="c396f-225">뷰 (위에 FeatureConvention에서 제공 된 기능 이름 사용) 기능 폴더에 있을 수 있도록 사용자 지정 규칙을 통해 그를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-225">You can override it with a custom convention so that views will be located in your feature folders (using the feature name provided by the FeatureConvention, above).</span></span> <span data-ttu-id="c396f-226">이 방법을 사용 하는 방법에 대 한 자세한 정보 및 MSDN 문서에서 작업 예제를 다운로드할 수 있습니다 [ASP.NET Core MVC에 대 한 기능 슬라이스](https://msdn.microsoft.com/magazine/mt763233.aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-226">You can learn more about this approach and download a working sample from the MSDN article, [Feature Slices for ASP.NET Core MVC](https://msdn.microsoft.com/magazine/mt763233.aspx).</span></span>

### <a name="cross-cutting-concerns"></a><span data-ttu-id="c396f-227">일반적인 문제</span><span class="sxs-lookup"><span data-stu-id="c396f-227">Cross-Cutting Concerns</span></span>

<span data-ttu-id="c396f-228">응용 프로그램 성장 함에 따라 중복 제거 및 일관성을 유지 하는 일반적인 문제를 팩터링 하 점점 더 중요 해 집니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-228">As applications grow, it becomes increasingly important to factor out cross-cutting concerns to eliminate duplication and maintain consistency.</span></span> <span data-ttu-id="c396f-229">몇 가지 ASP.NET Core 응용 프로그램의 일반적인 문제는 인증, 모델 유효성 검사 규칙, 출력 캐싱 및 오류 처리, 경우에 많은 키워드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-229">Some examples of cross-cutting concerns in ASP.NET Core applications are authentication, model validation rules, output caching, and error handling, though there are many others.</span></span> <span data-ttu-id="c396f-230">ASP.NET Core MVC [필터](https://docs.microsoft.com/aspnet/core/mvc/controllers/filters) 전이나 요청 처리 파이프라인의 특정 단계 후 코드를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-230">ASP.NET Core MVC [filters](https://docs.microsoft.com/aspnet/core/mvc/controllers/filters) allow you to run code before or after certain steps in the request processing pipeline.</span></span> <span data-ttu-id="c396f-231">예를 들어, 필터는 모델 바인딩 및 동작을 후 또는 하기 전에 전과 후 작업의 결과 전후 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-231">For instance, a filter can run before and after model binding, before and after an action, or before and after an action's result.</span></span> <span data-ttu-id="c396f-232">또한 파이프라인의 나머지 부분에 대 한 액세스를 제어 하는 권한 부여 필터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-232">You can also use an authorization filter to control access to the rest of the pipeline.</span></span> <span data-ttu-id="c396f-233">그림 7-2 방법을 요청 실행 흐름 필터를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-233">Figures 7-2 shows how request execution flows through filters, if configured.</span></span>

![요청 권한 부여 필터, 리소스 필터, 모델 바인딩, 동작 필터, 액션 실행 및 작업 결과 변환, 예외 필터, 결과 필터 및 결과 실행을 통해 처리 됩니다.](./media/image7-2.png)

<span data-ttu-id="c396f-236">필터 및 요청 파이프라인을 통해 그림 7-2 요청 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-236">Figure 7-2 Request execution through filters and request pipeline.</span></span>

<span data-ttu-id="c396f-237">컨트롤러 또는 동작 적용할 수 있도록에 일반적으로 필터 특성으로 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-237">Filters are usually implemented as attributes, so you can apply them controllers or actions.</span></span> <span data-ttu-id="c396f-238">이 방식으로 동작 수준 재정의 또는 빌드 컨트롤러 수준에서 지정 된 필터에 지정 된 필터에 추가할 때 자체가 전역 필터를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-238">When added in this fashion, filters specified at the action level override or build upon filters specified at the controller level, which themselves override global filters.</span></span> <span data-ttu-id="c396f-239">예를 들어는 \[경로\] 특성 컨트롤러 및 작업 간 경로를 만드는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-239">For example, the \[Route\] attribute can be used to build up routes between controllers and actions.</span></span> <span data-ttu-id="c396f-240">마찬가지로, 권한 부여 컨트롤러 수준에서 구성 및 다음 샘플을 참조 하십시오. 그런 다음 개별 작업에 의해 재정의 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-240">Likewise, authorization can be configured at the controller level, and then overridden by individual actions, as the following sample demonstrates:</span></span>

```csharp
[Authorize]
public class AccountController : Controller

{
    [AllowAnonymous]
    public async Task<IActionResult> Login() {}
    public async Task<IActionResult> ForgotPassword() {}
}
```

<span data-ttu-id="c396f-241">AllowAnonymous 필터 (특성)를 사용 하 여 컨트롤러 수준에서 설정 하는 권한 부여 필터를 재정의 하는 첫 번째 방법은 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-241">The first method, Login, uses the AllowAnonymous filter (attribute) to override the Authorize filter set at the controller level.</span></span> <span data-ttu-id="c396f-242">ForgotPassword 동작 (및 다른 작업에는 AllowAnonymous 특성 없는 클래스에서) 인증 된 요청에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-242">The ForgotPassword action (and any other action in the class that doesn't have an AllowAnonymous attribute) will require an authenticated request.</span></span>

<span data-ttu-id="c396f-243">일반적인 오류 Api에 대 한 정책 처리의 형태로 중복 제거에 필터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-243">Filters can be used to eliminate duplication in the form of common error handling policies for APIs.</span></span> <span data-ttu-id="c396f-244">예를 들어 모델 유효성 검사가 실패할 경우이 존재 하지 않는 키를 참조 하는 요청에 대 한 NotFound 응답 및 잘못 된 요청 응답을 반환 하는 일반적인 API 정책은입니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-244">For example, a typical API policy is to return a NotFound response to requests referencing keys that do not exist, and a BadRequest response if model validation fails.</span></span> <span data-ttu-id="c396f-245">다음 예제에서는 작업에서 이러한 두 정책을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-245">The following example demonstrates these two policies in action:</span></span>

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

<span data-ttu-id="c396f-246">다음과 같은 조건부 코드로 겹쳐 화면이 복잡 해질 하는 작업 메서드를 허용 하지 않음.</span><span class="sxs-lookup"><span data-stu-id="c396f-246">Don't allow your action methods to become cluttered with conditional code like this.</span></span> <span data-ttu-id="c396f-247">대신, 필요할 때에 적용할 수 있는 필터에는 정책을 끌어옵니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-247">Instead, pull the policies into filters that can be applied on an as-needed basis.</span></span> <span data-ttu-id="c396f-248">이 예제에서는 명령이 전송 되는 API에 언제 든 지 발생 해야 하 고 모델 유효성 검사는 다음 특성으로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-248">In this example, the model validation check, which should occur any time a command is sent to the API, can be replaced by the following attribute:</span></span>

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

<span data-ttu-id="c396f-249">마찬가지로, 필터 레코드 존재 동작이 실행 되는 동작의 이러한 검사를 수행 하지 않아도 전에 404를 반환 하는지 확인 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-249">Likewise, a filter can be used to check if a record exists and return a 404 before the action is executed, eliminating the need to perform these checks in the action.</span></span> <span data-ttu-id="c396f-250">공통 규칙 빠져 되었으며 UI에서 인프라 코드 및 비즈니스 논리를 분리 하 여 솔루션을 구성 되 면 MVC 동작 메서드는 매우 간소한 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-250">Once you've pulled out common conventions and organized your solution to separate infrastructure code and business logic from your UI, your MVC action methods should be extremely thin:</span></span>

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

<span data-ttu-id="c396f-251">읽어볼 수 있는 필터를 구현 하 고 MSDN 문서에서 작업 예제를 다운로드에 대 한 [실제 세계 ASP.NET Core MVC 필터](https://msdn.microsoft.com/magazine/mt767699.aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-251">You can read more about implementing filters and download a working sample from the MSDN article, [Real World ASP.NET Core MVC Filters](https://msdn.microsoft.com/magazine/mt767699.aspx).</span></span>

> ### <a name="references--structuring-applications"></a><span data-ttu-id="c396f-252">참조-응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="c396f-252">References – Structuring Applications</span></span>
> - <span data-ttu-id="c396f-253">**영역**</span><span class="sxs-lookup"><span data-stu-id="c396f-253">**Areas**</span></span>  
> <span data-ttu-id="c396f-254"><https://docs.microsoft.com/aspnet/core/mvc/controllers/areas></span><span class="sxs-lookup"><span data-stu-id="c396f-254"><https://docs.microsoft.com/aspnet/core/mvc/controllers/areas></span></span>
> - <span data-ttu-id="c396f-255">**MSDN-MVC ASP.NET Core에 대 한 기능 슬라이스**
>  <https://msdn.microsoft.com/magazine/mt763233.aspx></span><span class="sxs-lookup"><span data-stu-id="c396f-255">**MSDN – Feature Slices for ASP.NET Core MVC**
<https://msdn.microsoft.com/magazine/mt763233.aspx></span></span>
> - <span data-ttu-id="c396f-256">**필터**</span><span class="sxs-lookup"><span data-stu-id="c396f-256">**Filters**</span></span>  
> <span data-ttu-id="c396f-257"><https://docs.microsoft.com/aspnet/core/mvc/controllers/filters></span><span class="sxs-lookup"><span data-stu-id="c396f-257"><https://docs.microsoft.com/aspnet/core/mvc/controllers/filters></span></span>
> - <span data-ttu-id="c396f-258">**MSDN – 실제 코어 ASP.NET MVC 필터**</span><span class="sxs-lookup"><span data-stu-id="c396f-258">**MSDN – Real World ASP.NET Core MVC Filters**</span></span>  
> <span data-ttu-id="c396f-259"><https://msdn.microsoft.com/magazine/mt767699.aspx></span><span class="sxs-lookup"><span data-stu-id="c396f-259"><https://msdn.microsoft.com/magazine/mt767699.aspx></span></span>

## <a name="security"></a><span data-ttu-id="c396f-260">보안</span><span class="sxs-lookup"><span data-stu-id="c396f-260">Security</span></span>

<span data-ttu-id="c396f-261">웹 응용 프로그램 보안은 큰, 많은 고려 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-261">Securing web applications is a large topic, with many considerations.</span></span> <span data-ttu-id="c396f-262">가장 기본적인 수준에서 보안 사용자에 게 지정된 된 요청와 서 다음 해당 요청 해야 하는 리소스에 대 한 액세스를만 있는지를 확인 하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-262">At its most basic level, security involves ensuring you know who a given request is coming from, and then ensuring that that request only has access to resources it should.</span></span> <span data-ttu-id="c396f-263">인증은 요청 알려진된 엔터티에서 오는 것으로 처리 해야 하는지 확인 하려면 요청에 신뢰할 수 있는 데이터 저장소에 제공 된 자격 증명을 비교 하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-263">Authentication is the process of comparing credentials provided with a request to those in a trusted data store, to see if the request should be treated as coming from a known entity.</span></span> <span data-ttu-id="c396f-264">권한 부여는 사용자 id에 따라 특정 리소스에 대 한 액세스를 제한 하는 과정입니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-264">Authorization is the process of restricting access to certain resources based on user identity.</span></span> <span data-ttu-id="c396f-265">세 번째 보안 문제가 발생 요청을 수행 해야 이상 제 3 자가 도청에서 보호 [SSL 응용 프로그램에서 사용 되도록](https://docs.microsoft.com/aspnet/core/security/enforcing-ssl)합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-265">A third security concern is protecting requests from eavesdropping by third parties, for which you should at least [ensure that SSL is used by your application](https://docs.microsoft.com/aspnet/core/security/enforcing-ssl).</span></span>

### <a name="authentication"></a><span data-ttu-id="c396f-266">인증</span><span class="sxs-lookup"><span data-stu-id="c396f-266">Authentication</span></span>

<span data-ttu-id="c396f-267">ASP.NET Core Identity는 멤버 자격 시스템으로 응용 프로그램에 대 한 로그인 기능을 지 원하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-267">ASP.NET Core Identity is a membership system you can use to support login functionality for your application.</span></span> <span data-ttu-id="c396f-268">로컬 사용자 계정에 대 한 지원을 지원 뿐 아니라 외부 로그인 공급자 Microsoft 계정, Twitter, Facebook, Google, 등 같은 공급자 로부터 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-268">It has support for local user accounts as well as external login provider support from providers like Microsoft Account, Twitter, Facebook, Google, and more.</span></span> <span data-ttu-id="c396f-269">ASP.NET Core Id 외에도 응용 프로그램이 windows 인증을 사용할 수 또는 타사 id 공급자와 같은 [Identityserver](https://github.com/IdentityServer/IdentityServer4)합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-269">In addition to ASP.NET Core Identity, your application can use windows authentication, or a third-party identity provider like [Identity Server](https://github.com/IdentityServer/IdentityServer4).</span></span>

<span data-ttu-id="c396f-270">ASP.NET Core Id는 개별 사용자 계정 옵션을 선택 하는 경우에 새 프로젝트 템플릿이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-270">ASP.NET Core Identity is included in new project templates if the Individual User Accounts option is selected.</span></span> <span data-ttu-id="c396f-271">이 서식 파일에 등록, 로그인, 외부 로그인, 암호를 잊어버리거나 및 추가 기능에 대 한 지원이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-271">This template includes support for registration, login, external logins, forgotten passwords, and additional functionality.</span></span>

![](./media/image7-3.png)

<span data-ttu-id="c396f-272">그림 7-3 선택 개별 사용자 계정에 미리 구성 된 Id가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-272">Figure 7-3 Select Individual User Accounts to have Identity preconfigured.</span></span>

<span data-ttu-id="c396f-273">Id가 지원 시작 시 ConfigureServices 및 구성 모두에서 구성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-273">Identity support is configured in Startup, both in ConfigureServices and Configure:</span></span>

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

<span data-ttu-id="c396f-274">Configure 메서드에 UseMvc 앞에 UseIdentity가 나타나는지 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-274">It's important that UseIdentity appear before UseMvc in the Configure method.</span></span> <span data-ttu-id="c396f-275">ConfigureServices에 Id를 구성 하는 경우에 AddDefaultTokenProviders에 대 한 호출을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-275">When configuring Identity in ConfigureServices, you'll notice a call to AddDefaultTokenProviders.</span></span> <span data-ttu-id="c396f-276">이 웹 통신 보안을 사용할 수 있지만 만들 SMS 또는 메일에 대 한 신원을 확인을 통해 사용자에 게 보낼 수 있는 메시지를 표시 하는 공급자를 대신 참조 하는 토큰으로 수행할 작업을 전혀 관계가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-276">This has nothing to do with tokens that may be used to secure web communications, but instead refers to providers that create prompts that can be sent to users via SMS or email in order for them to confirm their identity.</span></span>

<span data-ttu-id="c396f-277">에 대 한 자세한 내용은 [다단계 인증 구성](https://docs.microsoft.com/aspnet/core/security/authentication/2fa) 및 [외부 로그인 공급자를 사용 하도록 설정](https://docs.microsoft.com/aspnet/core/security/authentication/social/) 공식 ASP.NET Core docs에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-277">You can learn more about [configuring two-factor authentication](https://docs.microsoft.com/aspnet/core/security/authentication/2fa) and [enabling external login providers](https://docs.microsoft.com/aspnet/core/security/authentication/social/) from the official ASP.NET Core docs.</span></span>

### <a name="authorization"></a><span data-ttu-id="c396f-278">권한 부여</span><span class="sxs-lookup"><span data-stu-id="c396f-278">Authorization</span></span>

<span data-ttu-id="c396f-279">권한 부여의 가장 간단한 형태는 익명 사용자에 대 한 액세스를 제한 하는 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-279">The simplest form of authorization involves restricting access to anonymous users.</span></span> <span data-ttu-id="c396f-280">단순히 적용 하 여 수행할 수 있습니다는 \[Authorize\] 특성 특정 컨트롤러 또는 동작을 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-280">This can be achieved by simply applying the \[Authorize\] attribute to certain controllers or actions.</span></span> <span data-ttu-id="c396f-281">역할을 사용 하는 경우와 같이 특정 역할에 속한 사용자에 게 액세스를 제한 하는 특성을 추가로 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-281">If roles are being used, the attribute can be further extended to restrict access to users who belong to certain roles, as shown:</span></span>

```csharp
[Authorize(Roles = "HRManager,Finance")]
public class SalaryController : Controller
{

}
```

<span data-ttu-id="c396f-282">이 경우에 HRManager 또는 재무 역할 (또는 둘 다)에 속하는 사용자는 SalaryController에 대 한 액세스 권한을 갖기 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-282">In this case, users belonging to either the HRManager or Finance roles (or both) would have access to the SalaryController.</span></span> <span data-ttu-id="c396f-283">사용자 (뿐 아니라 여러 가지 방법 중 하나)는 여러 역할에 속해 있는지를 요구 하려면 있습니다 특성을 적용할 수를 여러 번 때마다 필요한 역할을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-283">To require that a user belong to multiple roles (not just one of several), you can apply the attribute multiple times, specifying a required role each time.</span></span>

<span data-ttu-id="c396f-284">여러 다른 컨트롤러 및 작업에 대 한 문자열 바람직하지 않은 반복 발생할 수 있습니다 역할의 특정 집합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-284">Specifying certain sets of roles as strings in many different controllers and actions can lead to undesirable repetition.</span></span> <span data-ttu-id="c396f-285">권한 부여 규칙을 캡슐화 하는 권한 부여 정책을 구성 하 고 적용할 때 다음 개별 역할 대신 정책을 지정할 수는 \[Authorize\] 특성:</span><span class="sxs-lookup"><span data-stu-id="c396f-285">You can configure authorization policies, which encapsulate authorization rules, and then specify the policy instead of individual roles when applying the \[Authorize\] attribute:</span></span>

```csharp
[Authorize(Policy = "CanViewPrivateReport")]
public IActionResult ExecutiveSalaryReport()
{
    return View();
}
```

<span data-ttu-id="c396f-286">이러한 방식으로 정책을 사용 하 여, 특정 역할이 나에 적용 되는 규칙에서 제한 되는 작업의 종류를 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-286">Using policies in this way, you can separate the kinds of actions being restricted from the specific roles or rules that apply to it.</span></span> <span data-ttu-id="c396f-287">나중에, 특정 리소스에 액세스 하는 새 역할을 만들 경우 업데이트할 수 있습니다 방금는 정책에서 모든 역할 목록을 업데이트 하는 대신 모든 \[Authorize\] 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-287">Later, if you create a new role that needs to have access to certain resources, you can just update a policy, rather than updating every list of roles on every \[Authorize\] attribute.</span></span>

#### <a name="claims"></a><span data-ttu-id="c396f-288">클레임</span><span class="sxs-lookup"><span data-stu-id="c396f-288">Claims</span></span>

<span data-ttu-id="c396f-289">클레임은 인증된 된 사용자의 속성을 나타내는 이름/값 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-289">Claims are name value pairs that represent properties of an authenticated user.</span></span> <span data-ttu-id="c396f-290">예를 들어 사용자의 직원을 클레임으로 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-290">For example, you might store users' employee number as a claim.</span></span> <span data-ttu-id="c396f-291">클레임 권한 부여 정책의 일부로 다음 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-291">Claims can then be used as part of authorization policies.</span></span> <span data-ttu-id="c396f-292">"EmployeeOnly" 이라는 정책을 만들 수 있습니다이 예제에 표시 된 대로 "이"를 호출 하는 클레임의 존재를 필요로 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-292">You could create a policy called "EmployeeOnly" that requires the existence of a claim called "EmployeeNumber", as shown in this example:</span></span>

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

<span data-ttu-id="c396f-293">이 정책은 함께 사용 될 수도 \[Authorize\] 위에서 설명한 것 처럼 모든 컨트롤러 및/또는 동작을 보호 하는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-293">This policy could then be used with the \[Authorize\] attribute to protect any controller and/or action, as described above.</span></span>

#### <a name="securing-web-apis"></a><span data-ttu-id="c396f-294">웹 Api 보안 설정</span><span class="sxs-lookup"><span data-stu-id="c396f-294">Securing Web APIs</span></span>

<span data-ttu-id="c396f-295">대부분의 웹 Api 토큰 기반 인증 시스템을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-295">Most web APIs should implement a token-based authentication system.</span></span> <span data-ttu-id="c396f-296">토큰 인증을 상태 비저장 및 확장 가능 하도록 설계 된 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-296">Token authentication is stateless and designed to be scalable.</span></span> <span data-ttu-id="c396f-297">토큰 기반 인증 시스템에서는 클라이언트 인증 공급자와 함께 먼저 인증 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-297">In a token-based authentication system, the client must first authenticate with the authentication provider.</span></span> <span data-ttu-id="c396f-298">성공 하면 클라이언트는 문자의 암호화 방식으로 의미 있는 문자열에 토큰을 발급 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-298">If successful, the client is issued a token, which is simply a cryptographically meaningful string of characters.</span></span> <span data-ttu-id="c396f-299">클라이언트는 다음 API에 요청을 발급 하도록 설정 해야,이 토큰 요청에 헤더를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-299">When the client then needs to issue a request to an API, it adds this token as a header on the request.</span></span> <span data-ttu-id="c396f-300">서버에는 다음 요청을 완료 하기 전에 요청 헤더에 위치한 토큰 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-300">The server then validates the token found in the request header before completing the request.</span></span> <span data-ttu-id="c396f-301">그림 7-4이이 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-301">Figure 7-4 demonstrates this process.</span></span>

![TokenAuth](./media/image7-4.png)

<span data-ttu-id="c396f-303">**그림 7-4입니다.**</span><span class="sxs-lookup"><span data-stu-id="c396f-303">**Figure 7-4.**</span></span> <span data-ttu-id="c396f-304">웹 Api에 대 한 토큰 기반 인증</span><span class="sxs-lookup"><span data-stu-id="c396f-304">Token-based authentication for Web APIs.</span></span>

> ### <a name="references--security"></a><span data-ttu-id="c396f-305">참조-보안</span><span class="sxs-lookup"><span data-stu-id="c396f-305">References – Security</span></span>
> - <span data-ttu-id="c396f-306">**보안 문서 개요**</span><span class="sxs-lookup"><span data-stu-id="c396f-306">**Security Docs Overview**</span></span>  
> <span data-ttu-id="c396f-307">https://docs.microsoft.com/aspnet/core/security/</span><span class="sxs-lookup"><span data-stu-id="c396f-307">https://docs.microsoft.com/aspnet/core/security/</span></span>
> - <span data-ttu-id="c396f-308">**ASP.NET Core 응용 프로그램에서 SSL을 강제 적용**</span><span class="sxs-lookup"><span data-stu-id="c396f-308">**Enforcing SSL in an ASP.NET Core App**</span></span>  
> <span data-ttu-id="c396f-309"><https://docs.microsoft.com/aspnet/core/security/enforcing-ssl></span><span class="sxs-lookup"><span data-stu-id="c396f-309"><https://docs.microsoft.com/aspnet/core/security/enforcing-ssl></span></span>
> - <span data-ttu-id="c396f-310">**ID 소개**</span><span class="sxs-lookup"><span data-stu-id="c396f-310">**Introduction to Identity**</span></span>  
> <span data-ttu-id="c396f-311"><https://docs.microsoft.com/aspnet/core/security/authentication/identity></span><span class="sxs-lookup"><span data-stu-id="c396f-311"><https://docs.microsoft.com/aspnet/core/security/authentication/identity></span></span>
> - <span data-ttu-id="c396f-312">**권한 부여 소개**</span><span class="sxs-lookup"><span data-stu-id="c396f-312">**Introduction to Authorization**</span></span>  
> <span data-ttu-id="c396f-313"><https://docs.microsoft.com/aspnet/core/security/authorization/introduction></span><span class="sxs-lookup"><span data-stu-id="c396f-313"><https://docs.microsoft.com/aspnet/core/security/authorization/introduction></span></span>
> - <span data-ttu-id="c396f-314">**인증 및 Azure 앱 서비스에서 API 앱에 대 한 권한 부여**</span><span class="sxs-lookup"><span data-stu-id="c396f-314">**Authentication and Authorization for API Apps in Azure App Service**</span></span>  
> <span data-ttu-id="c396f-315"><https://docs.microsoft.com/azure/app-service-api/app-service-api-authentication></span><span class="sxs-lookup"><span data-stu-id="c396f-315"><https://docs.microsoft.com/azure/app-service-api/app-service-api-authentication></span></span>

## <a name="client-communication"></a><span data-ttu-id="c396f-316">클라이언트 통신</span><span class="sxs-lookup"><span data-stu-id="c396f-316">Client Communication</span></span>

<span data-ttu-id="c396f-317">페이지를 처리 하 고 웹 Api 통해 데이터에 대 한 요청에 응답 하는 것 외에도 ASP.NET Core 응용 프로그램은 연결 된 클라이언트와 직접 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-317">In addition to serving pages and responding to requests for data via web APIs, ASP.NET Core apps can communicate directly with connected clients.</span></span> <span data-ttu-id="c396f-318">이 아웃 바운드 통신 전송 기술의 다양 가장 일반적인 되 고 Websocket 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-318">This outbound communication can use a variety of transport technologies, the most common being WebSockets.</span></span> <span data-ttu-id="c396f-319">ASP.NET Core SignalR는 종류의 응용 프로그램에 대 한 실시간 서버와 클라이언트 간 통신 기능에 간단한 수행 하는 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-319">ASP.NET Core SignalR is a library that makes it simple to kind of real-time server-to-client communication functionality to your applications.</span></span> <span data-ttu-id="c396f-320">SignalR 다양 한 기술 전송 Websocket을 지원 하 고 트래버스하여 다 개발자의 구현 세부 사항을 추상화 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-320">SignalR supports a variety of transport technologies, including WebSockets, and abstracts away many of the implementation details from the developer.</span></span>

<span data-ttu-id="c396f-321">ASP.NET Core SignalR은 개발, 현재 및 ASP.NET 코어의 다음 릴리스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-321">ASP.NET Core SignalR is currently under development, and will be available in the next release of ASP.NET Core.</span></span> <span data-ttu-id="c396f-322">그러나 다른 [소스 Websocket 라이브러리를 열고](https://github.com/radu-matei/websocket-manager) 현재 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-322">However, other [open source WebSockets libraries](https://github.com/radu-matei/websocket-manager) are currently available.</span></span>

<span data-ttu-id="c396f-323">실시간 클라이언트 통신을 WebSockets 직접 또는 기타 기술을 사용 하 여 다양 한 응용 프로그램 시나리오에서에서 유용 지 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-323">Real-time client communication, whether using WebSockets directly or other techniques, are useful in a variety of application scenarios.</span></span> <span data-ttu-id="c396f-324">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-324">Some examples include:</span></span>

-   <span data-ttu-id="c396f-325">라이브 대화방 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="c396f-325">Live chat room applications</span></span>

-   <span data-ttu-id="c396f-326">응용 프로그램 모니터링</span><span class="sxs-lookup"><span data-stu-id="c396f-326">Monitoring applications</span></span>

-   <span data-ttu-id="c396f-327">작업 진행 상황 업데이트</span><span class="sxs-lookup"><span data-stu-id="c396f-327">Job progress updates</span></span>

-   <span data-ttu-id="c396f-328">알림</span><span class="sxs-lookup"><span data-stu-id="c396f-328">Notifications</span></span>

-   <span data-ttu-id="c396f-329">대화형 forms 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="c396f-329">Interactive forms applications</span></span>

<span data-ttu-id="c396f-330">응용 프로그램에 대 한 클라이언트 통신을 빌드하는 경우 일반적으로 두 구성 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-330">When building client communication into your applications, there are typically two components:</span></span>

-   <span data-ttu-id="c396f-331">서버 쪽 연결 관리자 (SignalR 허브, WebSocketManager WebSocketHandler)</span><span class="sxs-lookup"><span data-stu-id="c396f-331">Server-side connection manager (SignalR Hub, WebSocketManager WebSocketHandler)</span></span>

-   <span data-ttu-id="c396f-332">클라이언트 쪽 라이브러리</span><span class="sxs-lookup"><span data-stu-id="c396f-332">Client-side library</span></span>

<span data-ttu-id="c396f-333">클라이언트 브라우저 – 모바일 응용 프로그램, 콘솔 응용 프로그램으로 제한 되지 않으며 다른 네이티브 앱 SignalR/Websocket을 사용 하 여도 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-333">Clients are not limited to browsers – mobile apps, console apps, and other native apps can also communicate using SignalR/WebSockets.</span></span> <span data-ttu-id="c396f-334">다음 간단한 프로그램 에코 WebSocketManager 샘플 응용 프로그램의 일부분으로 콘솔에 채팅 응용 프로그램에 전달 된 모든 콘텐츠:</span><span class="sxs-lookup"><span data-stu-id="c396f-334">The following simple program echoes all content sent to a chat application to the console, as part of a WebSocketManager sample application:</span></span>

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

<span data-ttu-id="c396f-335">발생 하는 방법으로 응용 프로그램 클라이언트 응용 프로그램과 직접 통신 및 실시간 통신 응용 프로그램의 사용자를 향상 시킬 수 있는지 여부를 고려 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-335">Consider ways in which your applications communicate directly with client applications, and consider whether real-time communication would improve your app's user experience.</span></span>

> ### <a name="references--client-communication"></a><span data-ttu-id="c396f-336">참조-클라이언트 통신</span><span class="sxs-lookup"><span data-stu-id="c396f-336">References – Client Communication</span></span>
> - <span data-ttu-id="c396f-337">**ASP.NET Core SignalR**</span><span class="sxs-lookup"><span data-stu-id="c396f-337">**ASP.NET Core SignalR**</span></span>  
> <span data-ttu-id="c396f-338"><https://github.com/aspnet/SignalR></span><span class="sxs-lookup"><span data-stu-id="c396f-338"><https://github.com/aspnet/SignalR></span></span>
> - <span data-ttu-id="c396f-339">**WebSocket 관리자**</span><span class="sxs-lookup"><span data-stu-id="c396f-339">**WebSocket Manager**</span></span>  
> <span data-ttu-id="c396f-340">https://github.com/radu-matei/websocket-manager</span><span class="sxs-lookup"><span data-stu-id="c396f-340">https://github.com/radu-matei/websocket-manager</span></span>

## <a name="domain-driven-design--should-you-apply-it"></a><span data-ttu-id="c396f-341">도메인 기반 디자인 – 적용 해야 할 것?</span><span class="sxs-lookup"><span data-stu-id="c396f-341">Domain-Driven Design – Should You Apply It?</span></span>

<span data-ttu-id="c396f-342">도메인 기반 디자인 (DDD)는에 초점을 강조 하는 소프트웨어를 작성 하는 민첩 한 방식에서 *비즈니스 도메인*합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-342">Domain-Driven Design (DDD) is an agile approach to building software that emphasizes focusing on the *business domain*.</span></span> <span data-ttu-id="c396f-343">통신 및 실제 시스템 작동 하는 방법을 개발자에 게 연결할 수 있는 비즈니스 도메인 expert(s)와의 상호 작용을 크게 강조를 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-343">It places a heavy emphasis on communication and interaction with business domain expert(s) who can relate to the developers how the real-world system works.</span></span> <span data-ttu-id="c396f-344">예를 들어 주식 거래를 처리 하는 시스템을 작성 하는 경우 도메인 전문가 숙련 된 스톡 브로커 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-344">For example, if you're building a system that handles stock trades, your domain expert might be an experienced stock broker.</span></span> <span data-ttu-id="c396f-345">DDD 대규모의 복잡 한 비즈니스 문제를 해결 하도록 설계 되었습니다과 종종 하지 않습니다를 작고 간단한 응용 프로그램에 대 한 적절 한 이해 하 고 도메인 모델링에 대 한 투자 도움이 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-345">DDD is designed to address large, complex business problems, and is often not appropriate for smaller, simpler applications, as the investment in understanding and modeling the domain is not worth it.</span></span>

<span data-ttu-id="c396f-346">기술 이외의 기타 관련자와 참가자 등 팀 개발 해야 DDD 접근 방식에 따라 소프트웨어를 빌드하는 경우는 *유비쿼터스 언어* 꼽자면 문제에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-346">When building software following a DDD approach, your team (including non-technical stakeholders and contributors) should develop a *ubiquitous language* for the problem space.</span></span> <span data-ttu-id="c396f-347">즉, 동일한 용어가 모델링 되는 실제 개념, 소프트웨어를 해당 하는 및 개념 (데이터베이스 테이블 등)를 지 속하는 존재할 수 있는 모든 구조에 사용할 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-347">That is, the same terminology should be used for the real-world concept being modeled, the software equivalent, and any structures that might exist to persist the concept (for example, database tables).</span></span> <span data-ttu-id="c396f-348">유비쿼터스 언어에 설명 된 개념에 대 한 기초를 형성 해야 따라서 프로그램 *도메인 모델*합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-348">Thus, the concepts described in the ubiquitous language should form the basis for your *domain model*.</span></span>

<span data-ttu-id="c396f-349">시스템의 동작을 나타내는 데 서로 상호 작용 하는 개체의 도메인 모델 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-349">Your domain model is comprised of objects that interact with one another to represent the behavior of the system.</span></span> <span data-ttu-id="c396f-350">이러한 개체는 다음 범주에 해당 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-350">These objects may fall into the following categories:</span></span>

-   <span data-ttu-id="c396f-351">[엔터티](http://deviq.com/entity/), 있으며 id의 스레드를 사용 하 여 개체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-351">[Entities](http://deviq.com/entity/), which represent objects with a thread of identity.</span></span> <span data-ttu-id="c396f-352">엔터티는 일반적으로 기준인 나중에 검색할 수 있는 키와 지 속성에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-352">Entities are typically stored in persistence with a key by which they can later be retrieved.</span></span>

-   <span data-ttu-id="c396f-353">[집계](http://deviq.com/aggregate-pattern/), 있으며 하나의 단위로 유지 해야 하는 개체의 그룹을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-353">[Aggregates](http://deviq.com/aggregate-pattern/), which represent groups of objects that should be persisted as a unit.</span></span>

-   <span data-ttu-id="c396f-354">[값 개체](http://deviq.com/value-object/), 있으며 속성 값의 합계를 기반으로 비교할 수 있는 개념을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-354">[Value objects](http://deviq.com/value-object/), which represent concepts that can be compared on the basis of the sum of their property values.</span></span> <span data-ttu-id="c396f-355">예를 들어, 시작 및 종료 날짜의 구성 된 DateRange 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-355">For example, DateRange consisting of a start and end date.</span></span>

-   <span data-ttu-id="c396f-356">[도메인 이벤트](https://martinfowler.com/eaaDev/DomainEvent.html), 있으며이 시스템의 다른 부분에 관심 있는 시스템 내에서 발생 하는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-356">[Domain events](https://martinfowler.com/eaaDev/DomainEvent.html), which represent things happening within the system that are of interest to other parts of the system.</span></span>

<span data-ttu-id="c396f-357">참고 DDD 도메인 모델에 있는 모델 내에서 복잡 한 동작을 캡슐화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-357">Note that a DDD domain model should encapsulate complex behavior within the model.</span></span> <span data-ttu-id="c396f-358">엔터티, 특히 단순히 안 속성 모음 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-358">Entities, in particular, should not merely be collections of properties.</span></span> <span data-ttu-id="c396f-359">라고 도메인 모델 동작에 게 없는 경우 단순히 시스템의 상태를 나타내는 경우는 [anemic 모델](http://deviq.com/anemic-model/), ddd에서 바람직하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-359">When the domain model lacks behavior and merely represents the state of the system, it is said to be an [anemic model](http://deviq.com/anemic-model/), which is undesirable in DDD.</span></span>

<span data-ttu-id="c396f-360">DDD에 이러한 모델 형식 외에도 일반적으로 다양 한 패턴에서 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-360">In addition to these model types, DDD typically employs a variety of patterns:</span></span>

-   <span data-ttu-id="c396f-361">[리포지토리](http://deviq.com/repository-pattern/), 지 속성 세부 정보를 추상화에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-361">[Repository](http://deviq.com/repository-pattern/), for abstracting persistence details.</span></span>

-   <span data-ttu-id="c396f-362">[공장](https://en.wikipedia.org/wiki/Factory_method_pattern), 복잡 한 개체 생성을 캡슐화 하는 데 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-362">[Factory](https://en.wikipedia.org/wiki/Factory_method_pattern), for encapsulating complex object creation.</span></span>

-   <span data-ttu-id="c396f-363">분리 트리거되는 동작 종속 동작에 대 한 도메인 이벤트</span><span class="sxs-lookup"><span data-stu-id="c396f-363">Domain events, for decoupling dependent behavior from triggering behavior.</span></span>

-   <span data-ttu-id="c396f-364">[서비스](http://gorodinski.com/blog/2012/04/14/services-in-domain-driven-design-ddd/), 캡슐화 복잡 한 동작 및/또는 인프라 구현 세부 정보에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-364">[Services](http://gorodinski.com/blog/2012/04/14/services-in-domain-driven-design-ddd/), for encapsulating complex behavior and/or infrastructure implementation details.</span></span>

-   <span data-ttu-id="c396f-365">[명령](https://en.wikipedia.org/wiki/Command_pattern), 분리에 대 한 명령을 실행 하 고 자체 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-365">[Command](https://en.wikipedia.org/wiki/Command_pattern), for decoupling issuing commands and executing the command itself.</span></span>

-   <span data-ttu-id="c396f-366">[사양](http://deviq.com/specification-pattern/), 쿼리 세부 정보를 캡슐화 하는 데 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-366">[Specification](http://deviq.com/specification-pattern/), for encapsulating query details.</span></span>

<span data-ttu-id="c396f-367">또한 DDD 앞에서 설명한 정리 아키텍처를 사용 하는 권장 느슨한 결합, 간략화 및 단위 테스트를 사용 하 여 쉽게 확인할 수 있는 코드에 대 한 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-367">DDD also recommends the use of the Clean Architecture discussed previously, allowing for loose coupling, encapsulation, and code that can easily be verified using unit tests.</span></span>

### <a name="when-should-you-apply-ddd"></a><span data-ttu-id="c396f-368">DDD 적용할 때</span><span class="sxs-lookup"><span data-stu-id="c396f-368">When Should You Apply DDD</span></span>

<span data-ttu-id="c396f-369">DDD는 중요 한 비즈니스 (되지 기술적인) 복잡성 함께 큰 응용 프로그램에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-369">DDD is well-suited to large applications with significant business (not just technical) complexity.</span></span> <span data-ttu-id="c396f-370">응용 프로그램 도메인 전문가의 기술을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-370">The application should require the knowledge of domain experts.</span></span> <span data-ttu-id="c396f-371">비즈니스 규칙 및 단순히 저장 하 고 데이터 저장소에서 다양 한 레코드의 현재 상태를 검색 하는 다음 상호 작용을 나타내는 도메인 모델 자체에 중요 한 동작이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-371">There should be significant behavior in the domain model itself, representing business rules and interactions beyond simply storing and retrieving the current state of various records from data stores.</span></span>

### <a name="when-shouldnt-you-apply-ddd"></a><span data-ttu-id="c396f-372">서는 안 적용 하는 경우 DDD</span><span class="sxs-lookup"><span data-stu-id="c396f-372">When Shouldn't You Apply DDD</span></span>

<span data-ttu-id="c396f-373">DDD는 모델링, 아키텍처 및 더 작은 응용 프로그램 또는 방금 CRUD (만들기/읽기/업데이트/삭제)는 기본적으로 응용 프로그램에 대해 만들 수 있습니다 하는 통신에 대 한 투자를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-373">DDD involves investments in modeling, architecture, and communication that may not be warranted for smaller applications or applications that are essentially just CRUD (create/read/update/delete).</span></span> <span data-ttu-id="c396f-374">DDD, 다음 응용 프로그램에 가깝지만 도메인 없는 동작으로는 anemic 모델을 알게 하려는 경우 접근 방식을 재구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-374">If you choose to approach your application following DDD, but find that your domain has an anemic model with no behavior, you may need to rethink your approach.</span></span> <span data-ttu-id="c396f-375">응용 프로그램 DDD, 필요 하지 않을 또는 데이터베이스 또는 사용자 인터페이스에서 하지 않고 도메인 모델에서 비즈니스 논리를 캡슐화 하는 응용 프로그램을 리팩터링 도움이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-375">Either your application may not need DDD, or you may need assistance refactoring your application to encapsulate business logic in the domain model, rather than in your database or user interface.</span></span>

<span data-ttu-id="c396f-376">혼합 접근 방식을 DDD는 응용 프로그램의 트랜잭션 또는 더 복잡 한 영역에 대 한 아니라 사용 응용 프로그램의 읽기 전용 부분 또는 간단한 CRUD 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-376">A hybrid approach would be to only use DDD for the transactional or more complex areas of the application, but not for simpler CRUD or read-only portions of the application.</span></span> <span data-ttu-id="c396f-377">예를 들어, 데이터를 보고서를 표시 하거나 대시보드에 대 한 데이터 시각화를 쿼리 하는 경우 집계의 제약 조건이 있는 채울 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-377">For instance, you needn't have the constraints of an Aggregate if you're querying data to display a report or to visualize data for a dashboard.</span></span> <span data-ttu-id="c396f-378">완벽 하 게 이러한 요구 사항에 대 한 별도, 더 간단한 읽기 모델을 가져야 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-378">It's perfectly acceptable to have a separate, simpler read model for such requirements.</span></span>

> ### <a name="references--domain-driven-design"></a><span data-ttu-id="c396f-379">참조 – 도메인 기반 디자인</span><span class="sxs-lookup"><span data-stu-id="c396f-379">References – Domain-Driven Design</span></span>
> - <span data-ttu-id="c396f-380">**DDD 내용만 (StackOverflow 응답)**</span><span class="sxs-lookup"><span data-stu-id="c396f-380">**DDD in Plain English (StackOverflow Answer)**</span></span>  
> <span data-ttu-id="c396f-381"><https://stackoverflow.com/questions/1222392/can-someone-explain-domain-driven-design-ddd-in-plain-english-please/1222488#1222488></span><span class="sxs-lookup"><span data-stu-id="c396f-381"><https://stackoverflow.com/questions/1222392/can-someone-explain-domain-driven-design-ddd-in-plain-english-please/1222488#1222488></span></span>

## <a name="deployment"></a><span data-ttu-id="c396f-382">배포</span><span class="sxs-lookup"><span data-stu-id="c396f-382">Deployment</span></span>

<span data-ttu-id="c396f-383">ASP.NET Core 응용 프로그램 호스트 위치에 관계 없이 배포 프로세스와 관련 된 몇 가지 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-383">There are a few steps involved in the process of deploying your ASP.NET Core application, regardless of where it will be hosted.</span></span> <span data-ttu-id="c396f-384">첫 번째 단계는 변환을 수행할 수 있는 응용 프로그램을 게시 하는 CLI 명령을 게시는 dotnet를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-384">The first step is to publish the application, which can be done using the dotnet publish CLI command.</span></span> <span data-ttu-id="c396f-385">응용 프로그램을 컴파일하 되 고 모든 지정 된 폴더에 응용 프로그램을 실행 하는 데 필요한 파일을 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-385">This will compile the application and place all of the files needed to run the application into a designated folder.</span></span> <span data-ttu-id="c396f-386">Visual Studio에서 배포할 때이 단계를 자동으로 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-386">When you deploy from Visual Studio, this step is performed for you automatically.</span></span> <span data-ttu-id="c396f-387">게시 폴더에는 응용 프로그램 및 해당 종속성에 대 한.exe 및.dll 파일 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-387">The publish folder contains .exe and .dll files for the application and its dependencies.</span></span> <span data-ttu-id="c396f-388">자체 포함 된 응용 프로그램에는.NET 런타임 버전도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-388">A self-contained application will also include a version of the .NET runtime.</span></span> <span data-ttu-id="c396f-389">ASP.NET Core 응용 프로그램 구성 파일, 정적 클라이언트 자산, 및 MVC 뷰도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-389">ASP.NET Core applications will also include configuration files, static client assets, and MVC views.</span></span>

<span data-ttu-id="c396f-390">ASP.NET Core 응용 프로그램은 서버를 부팅 하 고 응용 프로그램 (또는 서버)가 충돌 하는 경우 다시 시작 하는 경우 시작 되어야 하는 콘솔 응용 프로그램.</span><span class="sxs-lookup"><span data-stu-id="c396f-390">ASP.NET Core applications are console applications that must be started when the server boots and restarted if the application (or server) crashes.</span></span> <span data-ttu-id="c396f-391">이 프로세스를 자동화 프로세스 관리자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-391">A process manager can be used to automate this process.</span></span> <span data-ttu-id="c396f-392">ASP.NET Core에 대 한 가장 일반적인 프로세스 관리자는 Nginx 및 Linux 및 IIS에서 Apache 또는 Windows에서 Windows 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-392">The most common process managers for ASP.NET Core are Nginx and Apache on Linux and IIS or Windows Service on Windows.</span></span>

<span data-ttu-id="c396f-393">프로세스 관리자 외에도 Kestrel 웹 서버에서 호스팅되는 ASP.NET Core 응용 프로그램에는 역방향 프록시 서버를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-393">In addition to a process manager, ASP.NET Core applications hosted in the Kestrel web server must use a reverse proxy server.</span></span> <span data-ttu-id="c396f-394">역방향 프록시 서버는 인터넷에서 HTTP 요청을 받고를 몇 가지 예비 처리 후 Kestrel에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-394">A reverse proxy server receives HTTP requests from the internet and forwards them to Kestrel after some preliminary handling.</span></span> <span data-ttu-id="c396f-395">역방향 프록시 서버는 응용 프로그램에 대 한 보안 계층을 제공 하 고 (인터넷에서 트래픽에 노출) 하는 가장자리 배포에 필요한 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-395">Reverse proxy servers provide a layer of security for the application, and are required for edge deployments (exposed to traffic from the Internet).</span></span> <span data-ttu-id="c396f-396">Kestrel 비교적 새로운 기능이 며 특정 공격에 대 한 방어를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-396">Kestrel is relatively new and does not yet offer defenses against certain attacks.</span></span> <span data-ttu-id="c396f-397">또한 kestrel 호스트 헤더와 같은 기법 동일한 포트 및 IP 주소에서 여러 응용 프로그램을 사용 하도록 설정 하려면 함께 사용할 수 없도록 같은 포트에서 여러 응용 프로그램을 호스팅 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-397">Kestrel also doesn't support hosting multiple applications on the same port, so techniques like host headers cannot be used with it to enable hosting multiple applications on the same port and IP address.</span></span>

![인터넷에 kestrel](./media/image7-5.png)

<span data-ttu-id="c396f-399">그림 7-역방향 프록시 서버 뒤 Kestrel에서 호스팅되는 ASP.NET 5</span><span class="sxs-lookup"><span data-stu-id="c396f-399">Figure 7-5 ASP.NET hosted in Kestrel behind a reverse proxy server</span></span>

<span data-ttu-id="c396f-400">SSL/HTTPS를 사용 하 여 여러 응용 프로그램을 보호 하는 역방향 프록시 도움이 될 수 있는 다른 시나리오가입니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-400">Another scenario in which a reverse proxy can be helpful is to secure multiple applications using SSL/HTTPS.</span></span> <span data-ttu-id="c396f-401">이 경우 역방향 프록시만 ssl이 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-401">In this case, only the reverse proxy would need to have SSL configured.</span></span> <span data-ttu-id="c396f-402">그림 7-6에 나와 있는 것 처럼 역방향 프록시 서버와 Kestrel 간의 통신 HTTP를 통한 위치를 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-402">Communication between the reverse proxy server and Kestrel could take place over HTTP, as shown in Figure 7-6.</span></span>

![](./media/image7-6.png)

<span data-ttu-id="c396f-403">그림 7-6 HTTPS 보안 역방향 프록시 서버 뒤에 호스팅되는 ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c396f-403">Figure 7-6 ASP.NET hosted behind an HTTPS-secured reverse proxy server</span></span>

<span data-ttu-id="c396f-404">점차 인기를 더해가는 되는 방법은 다음 하거나 될 수 있는 로컬로 호스팅되고 호스팅용 클라우드 기반 Azure에 배포 된 Docker 컨테이너에서 ASP.NET Core 응용 프로그램을 호스트 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-404">An increasingly popular approach is to host your ASP.NET Core application in a Docker container, which then can be hosted locally or deployed to Azure for cloud-based hosting.</span></span> <span data-ttu-id="c396f-405">Docker 컨테이너 Kestrel에서 실행 중인 응용 프로그램 코드를 포함 될 수 하 고 위와 같이 역방향 프록시 서버 뒤 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-405">The Docker container could contain your application code, running on Kestrel, and would be deployed behind a reverse proxy server, as shown above.</span></span>

<span data-ttu-id="c396f-406">Azure에서 응용 프로그램을 호스팅 중인 경우 몇 가지 서비스를 제공 하는 전용된 가상 어플라이언스로 Microsoft Azure 응용 프로그램 게이트웨이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-406">If you're hosting your application on Azure, you can use Microsoft Azure Application Gateway as a dedicated virtual appliance to provide several services.</span></span> <span data-ttu-id="c396f-407">개별 응용 프로그램에 대 한 역방향 프록시 역할을 하는 것 외에도 응용 프로그램 게이트웨이 다음과 같은 기능이 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c396f-407">In addition to acting as a reverse proxy for individual applications, Application Gateway can also offer the following features:</span></span>

-   <span data-ttu-id="c396f-408">HTTP 부하 분산</span><span class="sxs-lookup"><span data-stu-id="c396f-408">HTTP load balancing</span></span>

-   <span data-ttu-id="c396f-409">SSL 오프 로드 (인터넷에만 SSL)</span><span class="sxs-lookup"><span data-stu-id="c396f-409">SSL offload (SSL only to Internet)</span></span>

-   <span data-ttu-id="c396f-410">End-to-end SSL</span><span class="sxs-lookup"><span data-stu-id="c396f-410">End to End SSL</span></span>

-   <span data-ttu-id="c396f-411">다중 사이트 라우팅 (단일 응용 프로그램 게이트웨이에 최대 20 개의 사이트 통합)</span><span class="sxs-lookup"><span data-stu-id="c396f-411">Multi-site routing (consolidate up to 20 sites on a single Application Gateway)</span></span>

-   <span data-ttu-id="c396f-412">웹 응용 프로그램 방화벽</span><span class="sxs-lookup"><span data-stu-id="c396f-412">Web application firewall</span></span>

-   <span data-ttu-id="c396f-413">Websocket 지원</span><span class="sxs-lookup"><span data-stu-id="c396f-413">Websocket support</span></span>

-   <span data-ttu-id="c396f-414">고급 진단</span><span class="sxs-lookup"><span data-stu-id="c396f-414">Advanced diagnostics</span></span>

<span data-ttu-id="c396f-415">*장 10의 Azure 배포 옵션에 대해 자세히 알아보기*</span><span class="sxs-lookup"><span data-stu-id="c396f-415">*Learn more about Azure deployment options in Chapter 10.*</span></span>

> ### <a name="references--deployment"></a><span data-ttu-id="c396f-416">참조 – 배포</span><span class="sxs-lookup"><span data-stu-id="c396f-416">References – Deployment</span></span>
> - <span data-ttu-id="c396f-417">**호스팅 및 배포 개요**</span><span class="sxs-lookup"><span data-stu-id="c396f-417">**Hosting and Deployment Overview**</span></span>  
> <span data-ttu-id="c396f-418"><https://docs.microsoft.com/aspnet/core/publishing/></span><span class="sxs-lookup"><span data-stu-id="c396f-418"><https://docs.microsoft.com/aspnet/core/publishing/></span></span>
> - <span data-ttu-id="c396f-419">**Kestrel 역방향 프록시를 사용 하는 경우**</span><span class="sxs-lookup"><span data-stu-id="c396f-419">**When to use Kestrel with a reverse proxy**</span></span>  
> <span data-ttu-id="c396f-420"><https://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel#when-to-use-kestrel-with-a-reverse-proxy></span><span class="sxs-lookup"><span data-stu-id="c396f-420"><https://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel#when-to-use-kestrel-with-a-reverse-proxy></span></span>
> - <span data-ttu-id="c396f-421">**Docker에서 ASP.NET Core 앱 호스트**</span><span class="sxs-lookup"><span data-stu-id="c396f-421">**Host ASP.NET Core apps in Docker**</span></span>  
> <span data-ttu-id="c396f-422"><https://docs.microsoft.com/aspnet/core/publishing/docker></span><span class="sxs-lookup"><span data-stu-id="c396f-422"><https://docs.microsoft.com/aspnet/core/publishing/docker></span></span>
> - <span data-ttu-id="c396f-423">**Azure 응용 프로그램 게이트웨이 소개합니다.**</span><span class="sxs-lookup"><span data-stu-id="c396f-423">**Introducing Azure Application Gateway**</span></span>  
> <span data-ttu-id="c396f-424"><https://docs.microsoft.com/azure/application-gateway/application-gateway-introduction></span><span class="sxs-lookup"><span data-stu-id="c396f-424"><https://docs.microsoft.com/azure/application-gateway/application-gateway-introduction></span></span>

>[!div class="step-by-step"]
<span data-ttu-id="c396f-425">[이전] (공통-클라이언트-쪽-웹-technologies.md) [다음] (work-with-data-in-asp-net-core-apps.md)</span><span class="sxs-lookup"><span data-stu-id="c396f-425">[Previous] (common-client-side-web-technologies.md) [Next] (work-with-data-in-asp-net-core-apps.md)</span></span>
