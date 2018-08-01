---
title: ASP.NET Core MVC 앱 개발
description: ASP.NET Core 및 Azure를 사용하여 최신 웹 응용 프로그램 설계 | ASP.NET Core MVC 앱 개발
author: ardalis
ms.author: wiwagn
ms.date: 06/28/2018
ms.openlocfilehash: 2fd3eb1e123959130884b96ee9d2e59b83c41b0a
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37404647"
---
# <a name="develop-aspnet-core-mvc-apps"></a><span data-ttu-id="42f90-103">ASP.NET Core MVC 앱 개발</span><span class="sxs-lookup"><span data-stu-id="42f90-103">Develop ASP.NET Core MVC apps</span></span>

> <span data-ttu-id="42f90-104">"처음에는 제대로 하는 것이 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-104">"It's not important to get it right the first time.</span></span> <span data-ttu-id="42f90-105">그러나 마지막에 제대로 하는 것은 매우 중요합니다."</span><span class="sxs-lookup"><span data-stu-id="42f90-105">It's vitally important to get it right the last time."</span></span>  
> <span data-ttu-id="42f90-106">_- Andrew Hunt 및 David Thomas_</span><span class="sxs-lookup"><span data-stu-id="42f90-106">_- Andrew Hunt and David Thomas_</span></span>

<span data-ttu-id="42f90-107">ASP.NET Core는 최신 클라우드에 최적화된 웹 응용 프로그램을 빌드하기 위한 플랫폼 간 오픈 소스 프레임워크입니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-107">ASP.NET Core is a cross-platform, open-source framework for building modern cloud-optimized web applications.</span></span> <span data-ttu-id="42f90-108">ASP.NET Core 앱은 간단하고 모듈화되어 있으며, 종속성 주입에 대한 기본 제공 지원을 통해 더 큰 테스트와 유지 관리가 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-108">ASP.NET Core apps are lightweight and modular, with built-in support for dependency injection, enabling greater testability and maintainability.</span></span> <span data-ttu-id="42f90-109">뷰 기반 앱 외에도 최신 웹 API를 작성할 수 있도록 지원하는 MVC와 함께 ASP.NET Core는 엔터프라이즈 웹 응용 프로그램을 빌드할 수 있는 강력한 프레임워크입니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-109">Combined with MVC, which supports building modern web APIs in addition to view-based apps, ASP.NET Core is a powerful framework with which to build enterprise web applications.</span></span>

## <a name="mapping-requests-to-responses"></a><span data-ttu-id="42f90-110">요청을 응답에 매핑</span><span class="sxs-lookup"><span data-stu-id="42f90-110">Mapping requests to responses</span></span>

<span data-ttu-id="42f90-111">ASP.NET Core 앱은 본질적으로 들어오는 요청을 나가는 응답에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-111">At its heart, ASP.NET Core apps map incoming requests to outgoing responses.</span></span> <span data-ttu-id="42f90-112">이 매핑은 낮은 수준에서 미들웨어로 수행되며, 간단한 ASP.NET Core 앱과 마이크로 서비스는 사용자 지정 미들웨어로만 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-112">At a low level, this is done with middleware, and simple ASP.NET Core apps and microservices may be comprised solely of custom middleware.</span></span> <span data-ttu-id="42f90-113">ASP.NET Core MVC를 사용하는 경우 _경로_, _컨트롤러_ 및 _작업_과 관련하여 다소 높은 수준에서 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-113">When using ASP.NET Core MVC, you can work at a somewhat higher level, thinking in terms of _routes_, _controllers_, and _actions_.</span></span> <span data-ttu-id="42f90-114">들어오는 각 요청은 응용 프로그램의 라우팅 테이블과 비교되며, 일치하는 경로가 있으면 연결된 작업 메서드(컨트롤러에 속함)가 호출되어 요청을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-114">Each incoming request is compared with the application's routing table, and if a matching route is found, the associated action method (belonging to a controller) is called to handle the request.</span></span> <span data-ttu-id="42f90-115">일치하는 경로가 없으면 오류 처리기(이 경우 NotFound 결과를 반환)가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-115">If no matching route is found, an error handler (in this case, returning a NotFound result) is called.</span></span>

<span data-ttu-id="42f90-116">ASP.NET Core MVC 앱은 기본 경로, 특성 경로 또는 둘 다를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-116">ASP.NET Core MVC apps can use conventional routes, attribute routes, or both.</span></span> <span data-ttu-id="42f90-117">기본 경로는 코드에 정의되며, 아래 예제와 같은 구문을 사용하여 라우팅 _규칙_을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-117">Conventional routes are defined in code, specifying routing _conventions_ using syntax like in the example below:</span></span>

```csharp
app.UseMvc(routes =>;
{
    routes.MapRoute("default","{controller=Home}/{action=Index}/{id?}");
});
```

<span data-ttu-id="42f90-118">이 예제에서는 "default"라는 경로가 라우팅 테이블에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-118">In this example, a route named "default" has been added to the routing table.</span></span> <span data-ttu-id="42f90-119">_controller_, _action_ 및 _id_에 대한 자리 표시자를 사용하여 경로 템플릿을 정의합니다. controller와 action 자리 표시자에는 기본값(각각 "Home"과 "Index")이 지정되어 있고, id 자리 표시자("?"가 적용됨)는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-119">It defines a route template with placeholders for _controller_, _action_, and _id_. The controller and action placeholders have default specified ("Home" and "Index", respectively), and the id placeholder is optional (by virtue of a "?" applied to it).</span></span> <span data-ttu-id="42f90-120">여기에 정의된 규칙에 따르면 요청의 첫 번째 부분과 두 번째 부분이 각각 컨트롤러의 이름 및 작업과 일치해야 하고, 필요한 경우 세 번째 부분은 id 매개 변수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-120">The convention defined here states that the first part of a request should correspond to the name of the controller, the second part to the action, and then if necessary a third part will represent an id parameter.</span></span> <span data-ttu-id="42f90-121">기본 경로는 일반적으로 Startup 클래스의 Configure 메서드와 같이 응용 프로그램의 한 위치에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-121">Conventional routes are typically defined in one place for the application, such as in the Configure method in the Startup class.</span></span>

<span data-ttu-id="42f90-122">특성 경로는 전역적으로 지정되지 않고 컨트롤러와 작업에 직접 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-122">Attribute routes are applied to controllers and actions directly, rather than specified globally.</span></span> <span data-ttu-id="42f90-123">이렇게 하면 특정 메서드를 볼 때 훨씬 더 쉽게 검색할 수 있다는 이점이 있지만, 라우팅 정보가 응용 프로그램의 한 위치에서 유지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-123">This has the advantage of making them much more discoverable when you're looking at a particular method, but does mean that routing information is not kept in one place in the application.</span></span> <span data-ttu-id="42f90-124">특성 경로를 사용하면 지정된 작업에 대해 여러 경로를 쉽게 지정할 수 있을 뿐만 아니라 컨트롤러와 작업 간의 경로를 결합할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-124">With attribute routes, you can easily specify multiple routes for a given action, as well as combine routes between controllers and actions.</span></span> <span data-ttu-id="42f90-125">예:</span><span class="sxs-lookup"><span data-stu-id="42f90-125">For example:</span></span>

```csharp
[Route("Home")]
public class HomeController : Controller
{
    [Route("")] // Combines to define the route template "Home"
    [Route("Index")] // Combines to define route template "Home/Index"
    [Route("/")] // Does not combine, defines the route template ""
    public IActionResult Index() {}
}
```

<span data-ttu-id="42f90-126">[HttpGet] 및 유사한 특성에서 경로를 지정할 수 있으므로 [Route] 특성을 별도로 추가할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-126">Routes can be specified on [HttpGet] and similar attributes, avoiding the need to add separate [Route] attributes.</span></span> <span data-ttu-id="42f90-127">특성 경로는 토큰을 사용하여 아래 표시된 것처럼 컨트롤러 또는 작업 이름을 반복해야 하는 필요성을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-127">Attribute routes can also use tokens to reduce the need to repeat controller or action names, as shown below:</span></span>

```csharp
[Route("[controller\]")]
public class ProductsController : Controller
{
    [Route("")] // Matches 'Products'
    [Route("Index")] // Matches 'Products/Index'
    public IActionResult Index() {}
}
```

<span data-ttu-id="42f90-128">지정된 요청이 경로와 일치하지만 작업 메서드가 호출되기 전에 ASP.NET Core MVC는 요청에 대한 [모델 바인딩](/aspnet/core/mvc/models/model-binding) 및 [모델 유효성 검사](/aspnet/core/mvc/models/validation)를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-128">Once a given request has been matched to a route, but before the action method is called, ASP.NET Core MVC will perform [model binding](/aspnet/core/mvc/models/model-binding) and [model validation](/aspnet/core/mvc/models/validation) on the request.</span></span> <span data-ttu-id="42f90-129">모델 바인딩은 들어오는 HTTP 데이터를 호출할 작업 메서드의 매개 변수로 지정된 .NET 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-129">Model binding is responsible for converting incoming HTTP data into the .NET types specified as parameters of the action method to be called.</span></span> <span data-ttu-id="42f90-130">예를 들어 작업 메서드에서 정수 ID 매개 변수가 필요한 경우 모델 바인딩은 요청의 일부로 제공된 값에서 이 매개 변수를 제공하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-130">For example, if the action method expects an int id parameter, model binding will attempt to provide this parameter from a value provided as part of the request.</span></span> <span data-ttu-id="42f90-131">이렇게 하기 위해 모델 바인딩은 게시된 양식의 값, 경로 자체의 값 및 쿼리 문자열 값을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-131">To do so, model binding looks for values in a posted form, values in the route itself, and query string values.</span></span> <span data-ttu-id="42f90-132">ID 값을 찾은 것으로 가정하고 이 값이 정수로 변환되어 작업 메서드에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-132">Assuming an id value is found, it will be converted to an integer before being passed into the action method.</span></span>

<span data-ttu-id="42f90-133">모델을 바인딩한 후 작업 메서드를 호출하기 전에 모델 유효성 검사가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-133">After binding the model but before calling the action method, model validation occurs.</span></span> <span data-ttu-id="42f90-134">모델 유효성 검사에서는 모델 유형에 대한 선택적 특성을 사용하며, 제공된 모델 개체가 특정 데이터 요구 사항을 준수하는지 확인하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-134">Model validation uses optional attributes on the model type, and can help ensure that the provided model object conforms to certain data requirements.</span></span> <span data-ttu-id="42f90-135">특정 값은 필요에 따라 지정하거나 특정 길이 또는 숫자 범위로 제한할 수 있습니다. 유효성 검사 특성이 지정되었지만 모델이 요구 사항을 준수하지 않는 경우 ModelState.IsValid 속성이 false가 되며 실패한 유효성 검사 규칙 집합을 요청하는 클라이언트에 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-135">Certain values may be specified as required, or limited to a certain length or numeric range, etc. If validation attributes are specified but the model does not conform to their requirements, the property ModelState.IsValid will be false, and the set of failing validation rules will be available to send to the client making the request.</span></span>

<span data-ttu-id="42f90-136">모델 유효성 검사를 사용하는 경우 항상 상태 변경 명령을 수행하기 전에 모델이 유효한지 확인하여 유효하지 않은 데이터로 인해 앱이 손상되지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-136">If you're using model validation, you should be sure to always check that the model is valid before performing any state-altering commands, to ensure your app is not corrupted by invalid data.</span></span> <span data-ttu-id="42f90-137">[필터](/aspnet/core/mvc/controllers/filters)를 사용하면 모든 작업에서 이에 대한 코드를 추가할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-137">You can use a [filter](/aspnet/core/mvc/controllers/filters) to avoid the need to add code for this in every action.</span></span> <span data-ttu-id="42f90-138">ASP.NET Core MVC 필터는 요청 그룹을 가로채는 방법을 제공하므로 일반적인 정책과 교차 편집 문제를 대상 기준으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-138">ASP.NET Core MVC filters offer a way of intercepting groups of requests, so that common policies and cross-cutting concerns can be applied on a targeted basis.</span></span> <span data-ttu-id="42f90-139">필터는 개별 작업, 전체 컨트롤러 또는 전체 응용 프로그램에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-139">Filters can be applied to individual actions, whole controllers, or globally for an application.</span></span>

<span data-ttu-id="42f90-140">웹 API의 경우 ASP.NET Core MVC는 [_콘텐츠 협상_](/aspnet/core/mvc/models/formatting)을 지원하므로 응답의 형식을 지정하는 방법을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-140">For web APIs, ASP.NET Core MVC supports [_content negotiation_](/aspnet/core/mvc/models/formatting), allowing requests to specify how responses should be formatted.</span></span> <span data-ttu-id="42f90-141">요청에 제공된 헤더에 따라 데이터를 반환하는 작업은 응답을 XML, JSON 또는 지원되는 다른 형식으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-141">Based on headers provided in the request, actions returning data will format the response in XML, JSON, or another supported format.</span></span> <span data-ttu-id="42f90-142">이 기능을 사용하면 데이터 형식 요구 사항이 서로 다른 여러 클라이언트에서 동일한 API를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-142">This feature enables the same API to be used by multiple clients with different data format requirements.</span></span>

> ### <a name="references--mapping-requests-to-responses"></a><span data-ttu-id="42f90-143">참고 자료 - 요청을 응답에 매핑</span><span class="sxs-lookup"><span data-stu-id="42f90-143">References – Mapping Requests to Responses</span></span>
>
> - <span data-ttu-id="42f90-144">**컨트롤러 작업에 라우팅**
> <https://docs.microsoft.com/aspnet/core/mvc/controllers/routing></span><span class="sxs-lookup"><span data-stu-id="42f90-144">**Routing to Controller Actions**
<https://docs.microsoft.com/aspnet/core/mvc/controllers/routing></span></span>
> - <span data-ttu-id="42f90-145">**모델 바인딩**
> <https://docs.microsoft.com/aspnet/core/mvc/models/model-binding></span><span class="sxs-lookup"><span data-stu-id="42f90-145">**Model Binding**
<https://docs.microsoft.com/aspnet/core/mvc/models/model-binding></span></span>
> - <span data-ttu-id="42f90-146">**모델 유효성 검사**
> <https://docs.microsoft.com/aspnet/core/mvc/models/validation></span><span class="sxs-lookup"><span data-stu-id="42f90-146">**Model Validation**
<https://docs.microsoft.com/aspnet/core/mvc/models/validation></span></span>
> - <span data-ttu-id="42f90-147">**필터**
> <https://docs.microsoft.com/aspnet/core/mvc/controllers/filters></span><span class="sxs-lookup"><span data-stu-id="42f90-147">**Filters**
<https://docs.microsoft.com/aspnet/core/mvc/controllers/filters></span></span>

## <a name="working-with-dependencies"></a><span data-ttu-id="42f90-148">종속성 사용</span><span class="sxs-lookup"><span data-stu-id="42f90-148">Working with dependencies</span></span>

<span data-ttu-id="42f90-149">ASP.NET Core에는 [종속성 주입](/aspnet/core/fundamentals/dependency-injection)이라는 기술이 기본적으로 지원되며 내부적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-149">ASP.NET Core has built-in support for and internally makes use of a technique known as [dependency injection](/aspnet/core/fundamentals/dependency-injection).</span></span> <span data-ttu-id="42f90-150">종속성 주입은 응용 프로그램의 여러 부분 간에 느슨한 결합을 사용할 수 있게 하는 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-150">Dependency injection is a technique that enables loose coupling between different parts of an application.</span></span> <span data-ttu-id="42f90-151">느슨한 결합은 응용 프로그램의 일부를 쉽게 격리하여 테스트하거나 대체할 수 있기 때문에 바람직합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-151">Looser coupling is desirable because it makes it easier to isolate parts of the application, allowing for testing or replacement.</span></span> <span data-ttu-id="42f90-152">또한 응용 프로그램의 한 부분을 변경하는 경우 응용 프로그램의 다른 부분에 예기치 않은 영향을 줄 가능성을 낮춥니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-152">It also makes it less likely that a change in one part of the application will have an unexpected impact somewhere else in the application.</span></span> <span data-ttu-id="42f90-153">종속성 주입은 종속성 반전 원칙을 기반으로 하며, 종종 열기/닫기 원칙을 구현하는 데 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-153">Dependency injection is based on the dependency inversion principle, and is often key to achieving the open/closed principle.</span></span> <span data-ttu-id="42f90-154">응용 프로그램에서 종속성을 사용하는 방식을 평가할 때 [static cling](https://deviq.com/static-cling/)(정적 집착) 코드 냄새에 주의하고 "[new is glue](https://ardalis.com/new-is-glue)(접착제로서의 new)"라는 경구를 명심하세요.</span><span class="sxs-lookup"><span data-stu-id="42f90-154">When evaluating how your application works with its dependencies, beware of the [static cling](https://deviq.com/static-cling/) code smell, and remember the aphorism "[new is glue](https://ardalis.com/new-is-glue)."</span></span>

<span data-ttu-id="42f90-155">정적 집착은 클래스에서 정적 메서드를 호출하거나 인프라에 부작용이나 종속성이 있는 정적 속성에 액세스할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-155">Static cling occurs when your classes make calls to static methods, or access static properties, which have side effects or dependencies on infrastructure.</span></span> <span data-ttu-id="42f90-156">예를 들어 정적 메서드를 호출하는 메서드가 있고 이에 따라 데이터베이스에 쓰는 경우 메서드는 데이터베이스와 밀접하게 결합됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-156">For example, if you have a method that calls a static method, which in turn writes to a database, your method is tightly coupled to the database.</span></span> <span data-ttu-id="42f90-157">데이터베이스 호출을 중단하는 모든 것이 메서드를 손상시킵니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-157">Anything that breaks that database call will break your method.</span></span> <span data-ttu-id="42f90-158">이러한 테스트는 상용 모의 라이브러리에서 정적 호출을 모의해야 하거나 표준 테스트 데이터베이스에서만 테스트할 수 있으므로 이러한 메서드를 테스트하기가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-158">Testing such methods is notoriously difficult, since such tests either require commercial mocking libraries to mock the static calls, or can only be tested with a test database in place.</span></span> <span data-ttu-id="42f90-159">인프라에 종속되지 않는 정적 호출, 특히 완전한 상태 비저장인 호출은 호출하기에 괜찮지만, 결합 또는 테스트 용이성(정적 호출 자체에 코드를 결합하는 것 이상)에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-159">Static calls that don't have any dependence on infrastructure, especially those that are completely stateless, are fine to call and have no impact on coupling or testability (beyond coupling code to the static call itself).</span></span>

<span data-ttu-id="42f90-160">많은 개발자가 정적 집착 및 전역 상태의 위험을 이해하고 있지만, 여전히 직접 인스턴스화를 통해 코드를 특정 구현에 밀접하게 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-160">Many developers understand the risks of static cling and global state, but will still tightly couple their code to specific implementations through direct instantiation.</span></span> <span data-ttu-id="42f90-161">"접착제로서의 new"는 new 키워드 사용에 대한 일반적인 비난이 아니라 이 결합을 상기시키기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-161">"New is glue" is meant to be a reminder of this coupling, and not a general condemnation of the use of the new keyword.</span></span> <span data-ttu-id="42f90-162">정적 메서드 호출과 마찬가지로, 외부 종속성이 없는 형식의 새 인스턴스는 일반적으로 코드를 구현 세부 정보와 밀접하게 결합하거나 테스트를 더 어렵게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-162">Just as with static method calls, new instances of types that have no external dependencies typically do not tightly couple code to implementation details or make testing more difficult.</span></span> <span data-ttu-id="42f90-163">그러나 클래스를 인스턴스화할 때마다 해당 특정 위치에 해당 특정 인스턴스를 하드 코딩하는 것이 적절한지, 아니면 해당 인스턴스를 종속성으로 요청하도록 설계하는 것이 더 효율적인지를 잠시 생각해 보세요.</span><span class="sxs-lookup"><span data-stu-id="42f90-163">But each time a class is instantiated, take just a brief moment to consider whether it makes sense to hard-code that specific instance in that particular location, or if it would be a better design to request that instance as a dependency.</span></span>

### <a name="declare-your-dependencies"></a><span data-ttu-id="42f90-164">종속성 선언</span><span class="sxs-lookup"><span data-stu-id="42f90-164">Declare your dependencies</span></span>

<span data-ttu-id="42f90-165">ASP.NET Core는 메서드와 클래스에서 해당 종속성을 선언하고 이 종속성을 인수로 요청하도록 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-165">ASP.NET Core is built around having methods and classes declare their dependencies, requesting them as arguments.</span></span> <span data-ttu-id="42f90-166">ASP.NET 응용 프로그램은 일반적으로 Startup 클래스에 설정되며, 이 클래스 자체는 여러 지점에서 종속성 주입을 지원하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-166">ASP.NET applications are typically set up in a Startup class, which itself is configured to support dependency injection at several points.</span></span> <span data-ttu-id="42f90-167">Startup 클래스에 생성자가 있으면 다음과 같이 생성자를 통해 종속성을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-167">If your Startup class has a constructor, it can request dependencies through the constructor, like so:</span></span>

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

<span data-ttu-id="42f90-168">Startup 클래스는 명시적 형식 요구 사항이 없다는 점에서 흥미롭습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-168">The Startup class is interesting in that there are no explicit type requirements for it.</span></span> <span data-ttu-id="42f90-169">특별한 Startup 기본 클래스에서 상속하지 않으며 특정 인터페이스도 구현하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-169">It doesn't inherit from a special Startup base class, nor does it implement any particular interface.</span></span> <span data-ttu-id="42f90-170">생성자를 부여하거나 부여하지 않을 수 있고, 원하는 만큼 많은 매개 변수를 생성자에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-170">You can give it a constructor, or not, and you can specify as many parameters on the constructor as you want.</span></span> <span data-ttu-id="42f90-171">응용 프로그램에 대해 구성한 웹 호스트가 시작되면, 사용하도록 지정한 Startup 클래스를 호출하고 종속성 주입을 사용하여 Startup 클래스에 필요한 모든 종속성이 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-171">When the web host you've configured for your application starts, it will call the Startup class you've told it to use, and will use dependency injection to populate any dependencies the Startup class requires.</span></span> <span data-ttu-id="42f90-172">물론, ASP.NET Core에서 사용하는 서비스 컨테이너에 구성되지 않은 매개 변수를 요청하면, 예외가 발생하지만 컨테이너에서 인식하고 있는 종속성을 포기하지 않는 한 원하는 것을 모두 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-172">Of course, if you request parameters that aren't configured in the services container used by ASP.NET Core, you'll get an exception, but as long as you stick to dependencies the container knows about, you can request anything you want.</span></span>

<span data-ttu-id="42f90-173">종속성 주입은 Startup 인스턴스를 만들 때 처음부터 ASP.NET Core 응용 프로그램에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-173">Dependency injection is built into your ASP.NET Core apps right from the start, when you create the Startup instance.</span></span> <span data-ttu-id="42f90-174">Startup 클래스에 대해서는 중지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-174">It doesn't stop there for the Startup class.</span></span> <span data-ttu-id="42f90-175">다음과 같이 Configure 메서드에서 종속성을 요청할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-175">You can also request dependencies in the Configure method:</span></span>

```csharp
public void Configure(IApplicationBuilder app,
    IHostingEnvironment env,
    ILoggerFactory loggerFactory)
{

}
```

<span data-ttu-id="42f90-176">ConfigureServices 메서드는 이 동작에 대한 예외이며, IServiceCollection 형식의 매개 변수 하나만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-176">The ConfigureServices method is the exception to this behavior; it must take just one parameter of type IServiceCollection.</span></span> <span data-ttu-id="42f90-177">한편으로는 서비스 컨테이너에 개체를 추가해야 하며, 다른 한편으로는 IServiceCollection 매개 변수를 통해 현재 구성된 모든 서비스에 액세스할 수 있으므로 종속성 주입을 지원할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-177">It doesn't really need to support dependency injection, since on the one hand it is responsible for adding objects to the services container, and on the other it has access to all currently configured services via the IServiceCollection parameter.</span></span> <span data-ttu-id="42f90-178">따라서 필요한 서비스를 매개 변수로 요청하거나 ConfigureServices에서 IServiceCollection을 사용하여 Startup 클래스의 모든 부분에서 ASP.NET Core 서비스 컬렉션에 정의된 종속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-178">Thus, you can work with dependencies defined in the ASP.NET Core services collection in every part of the Startup class, either by requesting the needed service as a parameter or by working with the IServiceCollection in ConfigureServices.</span></span>

> [!NOTE]
> <span data-ttu-id="42f90-179">Startup 클래스에서 특정 서비스를 사용할 수 있는지 확인해야 하는 경우 WebHostBuilder 및 해당 ConfigureServices 메서드를 사용하여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-179">If you need to ensure certain services are available to your Startup class, you can configure them using WebHostBuilder and its ConfigureServices method.</span></span>

<span data-ttu-id="42f90-180">Startup 클래스는 컨트롤러에서 미들웨어, 필터, 자체의 서비스에 이르기까지 ASP.NET Core 응용 프로그램의 다른 부분을 구조화하는 방법에 대한 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-180">The Startup class is a model for how you should structure other parts of your ASP.NET Core application, from Controllers to Middleware to Filters to your own Services.</span></span> <span data-ttu-id="42f90-181">각각의 경우에서 [명시적 종속성 원칙](https://deviq.com/explicit-dependencies-principle/)을 따르고, 종속성을 직접 생성하지 않는 대신 요청하고, 응용 프로그램 전체에서 종속성 주입을 활용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-181">In each case, you should follow the [Explicit Dependencies Principle](https://deviq.com/explicit-dependencies-principle/), requesting your dependencies rather than directly creating them, and leveraging dependency injection throughout your application.</span></span> <span data-ttu-id="42f90-182">구현, 특히 인프라에서 작동하거나 부작용이 있는 서비스와 개체를 직접 인스턴스화하는 위치와 방법에 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-182">Be careful of where and how you directly instantiate implementations, especially services and objects that work with infrastructure or have side effects.</span></span> <span data-ttu-id="42f90-183">응용 프로그램 코어에 정의되고 특정 구현 형식에 대한 하드 코딩 참조에 인수로 전달되는 추상화 작업을 선호합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-183">Prefer working with abstractions defined in your application core and passed in as arguments to hardcoding references to specific implementation types.</span></span>

## <a name="structuring-the-application"></a><span data-ttu-id="42f90-184">응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="42f90-184">Structuring the application</span></span>

<span data-ttu-id="42f90-185">모놀리식 응용 프로그램에는 일반적으로 단일 진입점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-185">Monolithic applications typically have a single entry point.</span></span> <span data-ttu-id="42f90-186">ASP.NET Core 웹 응용 프로그램의 경우 진입점은 ASP.NET Core 웹 프로젝트가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-186">In the case of an ASP.NET Core web application, the entry point will be the ASP.NET Core web project.</span></span> <span data-ttu-id="42f90-187">그러나 솔루션이 단일 프로젝트로만 구성되어야 한다는 것을 의미하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-187">However, that doesn't mean the solution should consist of just a single project.</span></span> <span data-ttu-id="42f90-188">문제를 분리하기 위해 응용 프로그램을 여러 계층으로 분할하는 것이 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-188">It's useful to break up the application into different layers in order to follow separation of concerns.</span></span> <span data-ttu-id="42f90-189">일단 계층으로 분할되면 폴더를 넘어 별도의 프로젝트로 이동하여 캡슐화를 효율적으로 수행하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-189">Once broken up into layers, it's helpful to go beyond folders to separate projects, which can help achieve better encapsulation.</span></span> <span data-ttu-id="42f90-190">ASP.NET Core 응용 프로그램에서 이러한 목표를 달성하는 가장 좋은 방법은 5장에서 설명하는 클린 아키텍처의 변형입니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-190">The best approach to achieve these goals with an ASP.NET Core application is a variation of the Clean Architecture discussed in chapter 5.</span></span> <span data-ttu-id="42f90-191">응용 프로그램의 솔루션은 이 방법에 따라 UI, 인프라 및 ApplicationCore에 대한 별도의 라이브러리로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-191">Following this approach, the application's solution will be comprised of separate libraries for the UI, Infrastructure, and ApplicationCore.</span></span>

<span data-ttu-id="42f90-192">이러한 프로젝트 외에도, 별도의 테스트 프로젝트도 포함됩니다(테스트는 9장에서 설명).</span><span class="sxs-lookup"><span data-stu-id="42f90-192">In addition to these projects, separate test projects are included as well (Testing is discussed in Chapter 9).</span></span>

<span data-ttu-id="42f90-193">응용 프로그램의 개체 모델과 인터페이스는 ApplicationCore 프로젝트에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-193">The application's object model and interfaces should be placed in the ApplicationCore project.</span></span> <span data-ttu-id="42f90-194">이 프로젝트는 가능한 한 적은 종속성을 가지며, 솔루션의 다른 프로젝트에서 이 프로젝트를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-194">This project will have as few dependencies as possible, and the other projects in the solution will reference it.</span></span> <span data-ttu-id="42f90-195">지속되어야 하는 비즈니스 엔터티는 인프라에 직접 종속되지 않는 서비스와 마찬가지로 ApplicationCore 프로젝트에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-195">Business entities that need to be persisted are defined in the ApplicationCore project, as are services that do not directly depend on infrastructure.</span></span>

<span data-ttu-id="42f90-196">지속성을 수행하는 방법 또는 사용자에게 알림을 보내는 방법과 같은 구현 세부 정보는 인프라 프로젝트에 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-196">Implementation details, such as how persistence is performed or how notifications might be sent to a user, are kept in the Infrastructure project.</span></span> <span data-ttu-id="42f90-197">이 프로젝트는 Entity Framework Core와 같은 구현별 패키지를 참조하지만 프로젝트 외부에서 이러한 구현에 대한 세부 정보를 노출하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-197">This project will reference implementation-specific packages such as Entity Framework Core, but should not expose details about these implementations outside of the project.</span></span> <span data-ttu-id="42f90-198">인프라 서비스 및 리포지토리는 ApplicationCore 프로젝트에 정의된 인터페이스를 구현해야 하며, 해당 지속성 구현은 ApplicationCore에 정의된 엔터티를 검색하고 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-198">Infrastructure services and repositories should implement interfaces that are defined in the ApplicationCore project, and its persistence implementations are responsible for retrieving and storing entities defined in ApplicationCore.</span></span>

<span data-ttu-id="42f90-199">ASP.NET Core UI 프로젝트는 모든 UI 수준의 문제를 담당하지만 비즈니스 논리 또는 인프라 세부 정보를 포함하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-199">The ASP.NET Core UI project is responsible for any UI level concerns, but should not include business logic or infrastructure details.</span></span> <span data-ttu-id="42f90-200">실제로 인프라 프로젝트에 대한 종속성이 없어야 하며, 이 경우 두 프로젝트 간의 종속성이 실수로 도입되지 않도록 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-200">In fact, ideally it shouldn't even have a dependency on the Infrastructure project, which will help ensure no dependency between the two projects is introduced accidentally.</span></span> <span data-ttu-id="42f90-201">이는 StructureMap과 같은 타사 DI 컨테이너를 사용하여 수행할 수 있습니다. 이 컨테이너를 사용하면 각 프로젝트의 레지스트리 클래스에서 DI 규칙을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-201">This can be achieved using a third-party DI container like StructureMap, which allows you to define DI rules in Registry classes in each project.</span></span>

<span data-ttu-id="42f90-202">응용 프로그램을 구현 세부 정보와 분리하는 또 다른 방법은 응용 프로그램에서 개별 Docker 컨테이너에 배포된 마이크로 서비스를 호출하게 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-202">Another approach to decoupling the application from implementation details is to have the application call microservices, perhaps deployed in individual Docker containers.</span></span> <span data-ttu-id="42f90-203">이는 두 프로젝트 간에 DI를 활용하는 것보다 훨씬 더 많은 문제와 분리를 제공하지만 추가적인 복잡성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-203">This provides even greater separation of concerns and decoupling than leveraging DI between two projects, but has additional complexity.</span></span>

### <a name="feature-organization"></a><span data-ttu-id="42f90-204">기능 구성</span><span class="sxs-lookup"><span data-stu-id="42f90-204">Feature organization</span></span>

<span data-ttu-id="42f90-205">기본적으로 ASP.NET Core 응용 프로그램은 Controllers 및 Views를 포함하고, ViewModels를 자주 포함하도록 자체의 폴더 구조를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-205">By default, ASP.NET Core applications organize their folder structure to include Controllers and Views, and frequently ViewModels.</span></span> <span data-ttu-id="42f90-206">이러한 서버 쪽 구조를 지원하는 클라이언트 쪽 코드는 일반적으로 wwwroot 폴더에 별도로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-206">Client-side code to support these server-side structures is typically stored separately in the wwwroot folder.</span></span> <span data-ttu-id="42f90-207">그러나 작업 중이거나 지정된 기능이 이러한 폴더 간에 자주 이동해야 하므로 큰 응용 프로그램에서 이 기능으로 인해 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-207">However, large applications may encounter problems with this organization, since working on any given feature often requires jumping between these folders.</span></span> <span data-ttu-id="42f90-208">이 경우 각 폴더의 파일 및 하위 폴더의 수가 증가함에 따라 점점 더 어려워지고, 이로 인해 솔루션 탐색기를 통해 많은 양의 스크롤이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-208">This gets more and more difficult as the number of files and subfolders in each folder grows, resulting in a great deal of scrolling through Solution Explorer.</span></span> <span data-ttu-id="42f90-209">이 문제를 해결하는 한 가지 방법은 응용 프로그램 코드를 파일 형식 대신 _기능_으로 구성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-209">One solution to this problem is to organize application code by _feature_ instead of by file type.</span></span> <span data-ttu-id="42f90-210">이 구성 스타일은 일반적으로 기능 폴더 또는 기능 분할 영역이라고 합니다([수직 분할 영역](https://deviq.com/vertical-slices/) 참조).</span><span class="sxs-lookup"><span data-stu-id="42f90-210">This organizational style is typically referred to as feature folders or feature slices (see also: [Vertical Slices](https://deviq.com/vertical-slices/)).</span></span>

<span data-ttu-id="42f90-211">ASP.NET Core MVC는 이러한 용도를 위해 Areas를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-211">ASP.NET Core MVC supports Areas for this purpose.</span></span> <span data-ttu-id="42f90-212">Areas를 사용하면 각 Area 폴더에 별도의 Controllers 및 Views 폴더 집합(관련된 모델도 포함)을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-212">Using areas, you can create separate sets of Controllers and Views folders (as well as any associated models) in each Area folder.</span></span> <span data-ttu-id="42f90-213">그림 7-1에서는 Areas를 사용하는 폴더 구조의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-213">Figure 7-1 shows an example folder structure, using Areas.</span></span>

![](./media/image7-1.png)

<span data-ttu-id="42f90-214">그림 7-1 샘플 영역 구성</span><span class="sxs-lookup"><span data-stu-id="42f90-214">Figure 7-1 Sample Area Organization</span></span>

<span data-ttu-id="42f90-215">Areas를 사용하는 경우 특성을 사용하여 컨트롤러를 해당 컨트롤러가 속한 영역 이름으로 데코레이팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-215">When using Areas, you must use attributes to decorate your controllers with the name of the area to which they belong:</span></span>

```csharp
[Area("Catalog")]
public class HomeController
{}
```

<span data-ttu-id="42f90-216">또한 경로에도 영역 지원을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-216">You also need to add area support to your routes:</span></span>

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

<span data-ttu-id="42f90-217">Areas에 대한 기본 제공 외에도, 고유한 폴더 구조와 규칙(특성 및 사용자 지정 경로 대신)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-217">In addition to the built-in support for Areas, you can also use your own folder structure, and conventions in place of attributes and custom routes.</span></span> <span data-ttu-id="42f90-218">이렇게 하면 Views, Controllers 등에 대한 별도의 폴더가 포함되지 않은 기능 폴더를 갖출 수 있으며, 이에 따라 계층 구조가 더 균일하게 유지되고 각 기능과 관련된 모든 파일이 한 곳에서 더 쉽게 확인될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-218">This would allow you to have feature folders that didn't include separate folders for Views, Controllers, etc., keeping the hierarchy flatter and making it easier to see all related files in a single place for each feature.</span></span>

<span data-ttu-id="42f90-219">ASP.NET Core는 기본 제공 규칙을 사용하여 동작을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-219">ASP.NET Core uses built-in convention types to control its behavior.</span></span> <span data-ttu-id="42f90-220">이러한 규칙은 수정하거나 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-220">You can modify or replace these conventions.</span></span> <span data-ttu-id="42f90-221">예를 들어 네임스페이스(일반적으로 컨트롤러가 있는 폴더와 상호 관련됨)에 따라 지정된 컨트롤러에 대한 기능 이름을 자동으로 가져오는 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-221">For example, you can create a convention that will automatically get the feature name for a given controller based on its namespace (which typically correlates to the folder in which the controller is located):</span></span>

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

<span data-ttu-id="42f90-222">그런 다음 ConfigureServices에서 MVC에 대한 지원을 응용 프로그램에 추가할 때 이 규칙을 옵션으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-222">You then specify this convention as an option when you add support for MVC to your application in ConfigureServices:</span></span>

```csharp
services.AddMvc(o => o.Conventions.Add(new FeatureConvention()));
```

<span data-ttu-id="42f90-223">또한 ASP.NET Core MVC는 규칙을 사용하여 뷰를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-223">ASP.NET Core MVC also uses a convention to locate views.</span></span> <span data-ttu-id="42f90-224">위의 FeatureConvention에서 제공한 기능 이름을 사용하여 뷰가 사용자의 기능 폴더에 배치되도록 사용자 지정 규칙을 사용하여 이를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-224">You can override it with a custom convention so that views will be located in your feature folders (using the feature name provided by the FeatureConvention, above).</span></span> <span data-ttu-id="42f90-225">[ASP.NET Core MVC용 기능 분할 영역](https://msdn.microsoft.com/magazine/mt763233.aspx) MSDN 문서에서 이 방법에 대해 자세히 알아보고 작업용 샘플을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-225">You can learn more about this approach and download a working sample from the MSDN article, [Feature Slices for ASP.NET Core MVC](https://msdn.microsoft.com/magazine/mt763233.aspx).</span></span>

### <a name="cross-cutting-concerns"></a><span data-ttu-id="42f90-226">교차 편집 문제</span><span class="sxs-lookup"><span data-stu-id="42f90-226">Cross-cutting concerns</span></span>

<span data-ttu-id="42f90-227">응용 프로그램이 확장함에 따라 교차 편집 문제를 해결하여 중복을 제거하고 일관성을 유지하는 것이 점점 더 중요해지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-227">As applications grow, it becomes increasingly important to factor out cross-cutting concerns to eliminate duplication and maintain consistency.</span></span> <span data-ttu-id="42f90-228">ASP.NET Core 응용 프로그램의 교차 편집 문제에 대한 몇 가지 예로 인증, 모델 유효성 검사 규칙, 출력 캐싱 및 오류 처리 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-228">Some examples of cross-cutting concerns in ASP.NET Core applications are authentication, model validation rules, output caching, and error handling, though there are many others.</span></span> <span data-ttu-id="42f90-229">ASP.NET Core MVC [필터](/aspnet/core/mvc/controllers/filters)를 사용하면 요청 처리 파이프라인의 특정 단계 이전 또는 이후에 코드가 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-229">ASP.NET Core MVC [filters](/aspnet/core/mvc/controllers/filters) allow you to run code before or after certain steps in the request processing pipeline.</span></span> <span data-ttu-id="42f90-230">예를 들어 필터는 모델 바인딩 전후, 작업 전후, 작업 결과 전후에 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-230">For instance, a filter can run before and after model binding, before and after an action, or before and after an action's result.</span></span> <span data-ttu-id="42f90-231">또한 권한 필터를 사용하여 나머지 파이프라인에 대한 액세스를 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-231">You can also use an authorization filter to control access to the rest of the pipeline.</span></span> <span data-ttu-id="42f90-232">그림 7-2에서는 요청 실행이 구성된 경우 필터를 통해 진행되는 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-232">Figures 7-2 shows how request execution flows through filters, if configured.</span></span>

![요청은 권한 부여 필터, 리소스 필터, 모델 바인딩, 작업 필터, 작업 실행 및 작업 결과 변환, 예외 필터, 결과 필터 및 결과 실행을 통해 처리됩니다.](./media/image7-2.png)

<span data-ttu-id="42f90-235">그림 7-2 필터 및 요청 파이프라인을 통한 요청 실행</span><span class="sxs-lookup"><span data-stu-id="42f90-235">Figure 7-2 Request execution through filters and request pipeline.</span></span>

<span data-ttu-id="42f90-236">필터는 일반적으로 특성으로 구현되므로 컨트롤러 또는 작업을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-236">Filters are usually implemented as attributes, so you can apply them controllers or actions.</span></span> <span data-ttu-id="42f90-237">이 방식으로 추가되면 작업 수준에서 지정된 필터가 컨트롤러 수준에서 지정된 필터에 따라 재정의되거나 빌드됩니다. 이 필터는 자체적으로 전역 필터를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-237">When added in this fashion, filters specified at the action level override or build upon filters specified at the controller level, which themselves override global filters.</span></span> <span data-ttu-id="42f90-238">예를 들어 \[Route\] 특성을 사용하여 컨트롤러와 작업 사이의 경로를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-238">For example, the \[Route\] attribute can be used to build up routes between controllers and actions.</span></span> <span data-ttu-id="42f90-239">마찬가지로, 권한 부여는 컨트롤러 수준에서 구성한 다음, 다음 샘플과 같이 개별 작업으로 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-239">Likewise, authorization can be configured at the controller level, and then overridden by individual actions, as the following sample demonstrates:</span></span>

```csharp
[Authorize]
public class AccountController : Controller

{
    [AllowAnonymous]
    public async Task<IActionResult> Login() {}
    public async Task<IActionResult> ForgotPassword() {}
}
```

<span data-ttu-id="42f90-240">첫 번째 메서드인 Login은 AllowAnonymous 필터(특성)를 사용하여 컨트롤러 수준에서 설정된 Authorize 필터를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-240">The first method, Login, uses the AllowAnonymous filter (attribute) to override the Authorize filter set at the controller level.</span></span> <span data-ttu-id="42f90-241">ForgotPassword 작업(및 AllowAnonymous 특성이 없는 클래스의 다른 작업)에는 인증된 요청이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-241">The ForgotPassword action (and any other action in the class that doesn't have an AllowAnonymous attribute) will require an authenticated request.</span></span>

<span data-ttu-id="42f90-242">필터는 API에 대한 일반적인 오류 처리 정책의 형태로 중복을 제거하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-242">Filters can be used to eliminate duplication in the form of common error handling policies for APIs.</span></span> <span data-ttu-id="42f90-243">예를 들어 일반적인 API 정책은 존재하지 않는 키를 참조하는 요청에 대해 NotFound 응답을 반환하고, 모델 유효성 검사가 실패하면 BadRequest 응답을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-243">For example, a typical API policy is to return a NotFound response to requests referencing keys that do not exist, and a BadRequest response if model validation fails.</span></span> <span data-ttu-id="42f90-244">다음 예제의 작업에서는 이러한 두 가지 정책을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-244">The following example demonstrates these two policies in action:</span></span>

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

<span data-ttu-id="42f90-245">이러한 방식으로 조건부 코드를 사용하여 작업 메서드가 복잡해지지 않게 합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-245">Don't allow your action methods to become cluttered with conditional code like this.</span></span> <span data-ttu-id="42f90-246">대신 정책을 필요에 따라 적용할 수 있는 필터로 끌어옵니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-246">Instead, pull the policies into filters that can be applied on an as-needed basis.</span></span> <span data-ttu-id="42f90-247">다음 예제에서는 명령을 API로 보낼 때마다 수행되어야 하는 모델 유효성 검사를 다음 특성으로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-247">In this example, the model validation check, which should occur any time a command is sent to the API, can be replaced by the following attribute:</span></span>

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

<span data-ttu-id="42f90-248">마찬가지로, 필터를 사용하여 레코드가 있는지 확인하고, 작업이 실행되기 전에 404를 반환하므로 작업에서 이러한 검사를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-248">Likewise, a filter can be used to check if a record exists and return a 404 before the action is executed, eliminating the need to perform these checks in the action.</span></span> <span data-ttu-id="42f90-249">공통 규칙을 제거하고 UI에서 인프라 코드와 비즈니스 논리를 분리하는 솔루션을 구성한 후에는 MVC 작업 메서드가 매우 간소하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-249">Once you've pulled out common conventions and organized your solution to separate infrastructure code and business logic from your UI, your MVC action methods should be extremely thin:</span></span>

```csharp
[HttpPut("{id}")]
[ValidateAuthorExists]
public async Task<IActionResult> Put(int id, [FromBody]Author author)
{
    await _authorRepository.UpdateAsync(author);
    return Ok();
}
```

<span data-ttu-id="42f90-250">[실제 ASP.NET Core MVC 필터](https://msdn.microsoft.com/magazine/mt767699.aspx) MSDN 문서에서 필터 구현에 대한 자세한 내용을 알아보고 작업용 샘플을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-250">You can read more about implementing filters and download a working sample from the MSDN article, [Real World ASP.NET Core MVC Filters](https://msdn.microsoft.com/magazine/mt767699.aspx).</span></span>

> ### <a name="references--structuring-applications"></a><span data-ttu-id="42f90-251">참조 - 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="42f90-251">References – Structuring applications</span></span>
>
> - <span data-ttu-id="42f90-252">**Areas**</span><span class="sxs-lookup"><span data-stu-id="42f90-252">**Areas**</span></span>  
>   <https://docs.microsoft.com/aspnet/core/mvc/controllers/areas>
> - <span data-ttu-id="42f90-253">**MSDN Magazine – ASP.NET Core MVC용 기능 분할**</span><span class="sxs-lookup"><span data-stu-id="42f90-253">**MSDN Magazine – Feature Slices for ASP.NET Core MVC**</span></span>  
 > <https://msdn.microsoft.com/magazine/mt763233.aspx>
> - <span data-ttu-id="42f90-254">**필터**</span><span class="sxs-lookup"><span data-stu-id="42f90-254">**Filters**</span></span>  
>   <https://docs.microsoft.com/aspnet/core/mvc/controllers/filters>
> - <span data-ttu-id="42f90-255">**MSDN – 실제 ASP.NET Core MVC 필터**</span><span class="sxs-lookup"><span data-stu-id="42f90-255">**MSDN – Real World ASP.NET Core MVC Filters**</span></span>  
>   <https://msdn.microsoft.com/magazine/mt767699.aspx>

## <a name="security"></a><span data-ttu-id="42f90-256">보안</span><span class="sxs-lookup"><span data-stu-id="42f90-256">Security</span></span>

<span data-ttu-id="42f90-257">웹 응용 프로그램 보안은 많은 고려 사항이 있는 큰 주제입니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-257">Securing web applications is a large topic, with many considerations.</span></span> <span data-ttu-id="42f90-258">가장 기본적인 수준에서 보안은 지정된 요청을 발급한 사용자를 확인한 다음, 해당 요청에서 필요한 리소스에만 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-258">At its most basic level, security involves ensuring you know who a given request is coming from, and then ensuring that that request only has access to resources it should.</span></span> <span data-ttu-id="42f90-259">인증은 요청과 함께 제공되는 자격 증명을 신뢰할 수 있는 데이터 저장소의 자격 증명과 비교하여 해당 요청을 알려진 엔터티에서 제공하는 것으로 처리해야 하는지 여부를 확인하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-259">Authentication is the process of comparing credentials provided with a request to those in a trusted data store, to see if the request should be treated as coming from a known entity.</span></span> <span data-ttu-id="42f90-260">권한 부여는 사용자 ID에 따라 특정 리소스에 대한 액세스를 제한하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-260">Authorization is the process of restricting access to certain resources based on user identity.</span></span> <span data-ttu-id="42f90-261">세 번째 보안 문제는 요청을 제3자의 도청으로부터 보호하는 것이며, 이를 위해 적어도 [응용 프로그램에서 SSL을 사용](/aspnet/core/security/enforcing-ssl)하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-261">A third security concern is protecting requests from eavesdropping by third parties, for which you should at least [ensure that SSL is used by your application](/aspnet/core/security/enforcing-ssl).</span></span>

### <a name="authentication"></a><span data-ttu-id="42f90-262">인증</span><span class="sxs-lookup"><span data-stu-id="42f90-262">Authentication</span></span>

<span data-ttu-id="42f90-263">ASP.NET Core Identity는 응용 프로그램에 대한 로그인 기능을 지원하는 데 사용할 수 있는 멤버 자격 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-263">ASP.NET Core Identity is a membership system you can use to support login functionality for your application.</span></span> <span data-ttu-id="42f90-264">로컬 사용자 계정뿐만 아니라 Microsoft 계정, Twitter, Facebook, Google 등과 같은 공급자의 외부 로그인 공급자도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-264">It has support for local user accounts as well as external login provider support from providers like Microsoft Account, Twitter, Facebook, Google, and more.</span></span> <span data-ttu-id="42f90-265">응용 프로그램에서 ASP.NET Core Identity 외에도 Windows 인증 또는 [IdentityServer](https://github.com/IdentityServer/IdentityServer4)와 같은 타사 ID 공급자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-265">In addition to ASP.NET Core Identity, your application can use windows authentication, or a third-party identity provider like [Identity Server](https://github.com/IdentityServer/IdentityServer4).</span></span>

<span data-ttu-id="42f90-266">개별 사용자 계정 옵션이 선택되면 ASP.NET Core Identity가 새 프로젝트 템플릿에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-266">ASP.NET Core Identity is included in new project templates if the Individual User Accounts option is selected.</span></span> <span data-ttu-id="42f90-267">이 템플릿에는 등록, 로그인, 외부 로그인, 잊어버린 암호 및 추가 기능에 대한 지원이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-267">This template includes support for registration, login, external logins, forgotten passwords, and additional functionality.</span></span>

![](./media/image7-3.png)

<span data-ttu-id="42f90-268">그림 7-3 Identity를 미리 구성하기 위한 개별 사용자 계정 선택</span><span class="sxs-lookup"><span data-stu-id="42f90-268">Figure 7-3 Select Individual User Accounts to have Identity preconfigured.</span></span>

<span data-ttu-id="42f90-269">Identity 지원은 ConfigureServices 및 Configure 모두의 Startup에 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-269">Identity support is configured in Startup, both in ConfigureServices and Configure:</span></span>

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

<span data-ttu-id="42f90-270">Configure 메서드에서 UseIdentity는 UseMvc 앞에 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-270">It's important that UseIdentity appear before UseMvc in the Configure method.</span></span> <span data-ttu-id="42f90-271">ConfigureServices에 Identity가 구성되면 AddDefaultTokenProviders에 대한 호출을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-271">When configuring Identity in ConfigureServices, you'll notice a call to AddDefaultTokenProviders.</span></span> <span data-ttu-id="42f90-272">이는 웹 통신을 보호하는 데 사용할 수 있는 토큰과는 관계가 없지만, 대신 SMS 또는 이메일을 통해 사용자에게 보낼 수 있는 메시지를 만드는 공급자를 참조하여 자신의 ID를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-272">This has nothing to do with tokens that may be used to secure web communications, but instead refers to providers that create prompts that can be sent to users via SMS or email in order for them to confirm their identity.</span></span>

<span data-ttu-id="42f90-273">공식 ASP.NET Core 문서에서 [2단계 인증 구성](/aspnet/core/security/authentication/2fa) 및 [외부 로그인 공급자 사용](/aspnet/core/security/authentication/social/)에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-273">You can learn more about [configuring two-factor authentication](/aspnet/core/security/authentication/2fa) and [enabling external login providers](/aspnet/core/security/authentication/social/) from the official ASP.NET Core docs.</span></span>

### <a name="authorization"></a><span data-ttu-id="42f90-274">권한 부여</span><span class="sxs-lookup"><span data-stu-id="42f90-274">Authorization</span></span>

<span data-ttu-id="42f90-275">가장 간단한 형태의 권한 부여는 익명 사용자에 대한 액세스를 제한하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-275">The simplest form of authorization involves restricting access to anonymous users.</span></span> <span data-ttu-id="42f90-276">이 작업은 특정 컨트롤러 또는 작업에 \[Authorize\] 특성을 적용하기만 하면 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-276">This can be achieved by simply applying the \[Authorize\] attribute to certain controllers or actions.</span></span> <span data-ttu-id="42f90-277">역할을 사용하는 경우 다음과 같이 특정 역할에 속한 사용자에 대한 액세스를 제한하도록 특성을 추가로 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-277">If roles are being used, the attribute can be further extended to restrict access to users who belong to certain roles, as shown:</span></span>

```csharp
[Authorize(Roles = "HRManager,Finance")]
public class SalaryController : Controller
{

}
```

<span data-ttu-id="42f90-278">이 경우 HRManager 또는 Finance 역할(또는 둘 다)에 속한 사용자는 SalaryController에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-278">In this case, users belonging to either the HRManager or Finance roles (or both) would have access to the SalaryController.</span></span> <span data-ttu-id="42f90-279">사용자가 여러 역할에 속하도록 하려면(여러 역할 중 하나에만 속하는 것이 아님), 특성을 여러 번 적용하고 매번 필요한 역할을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-279">To require that a user belong to multiple roles (not just one of several), you can apply the attribute multiple times, specifying a required role each time.</span></span>

<span data-ttu-id="42f90-280">여러 다른 컨트롤러와 작업에서 특정 역할 집합을 문자열로 지정하면 바람직하지 않은 반복이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-280">Specifying certain sets of roles as strings in many different controllers and actions can lead to undesirable repetition.</span></span> <span data-ttu-id="42f90-281">권한 부여 규칙을 캡슐화하는 권한 부여 정책을 구성한 다음, \[Authorize\] 특성을 적용할 때 개별 역할 대신 정책을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-281">You can configure authorization policies, which encapsulate authorization rules, and then specify the policy instead of individual roles when applying the \[Authorize\] attribute:</span></span>

```csharp
[Authorize(Policy = "CanViewPrivateReport")]
public IActionResult ExecutiveSalaryReport()
{
    return View();
}
```

<span data-ttu-id="42f90-282">이러한 방식으로 정책을 사용하면 적용되는 특정 역할이나 정책에서 제한되는 작업의 종류를 분리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-282">Using policies in this way, you can separate the kinds of actions being restricted from the specific roles or rules that apply to it.</span></span> <span data-ttu-id="42f90-283">나중에 특정 리소스에 액세스해야 하는 새 역할을 만드는 경우 모든 \[Authorize\] 특성에 대한 모든 역할 목록을 업데이트하는 대신 정책을 업데이트하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-283">Later, if you create a new role that needs to have access to certain resources, you can just update a policy, rather than updating every list of roles on every \[Authorize\] attribute.</span></span>

#### <a name="claims"></a><span data-ttu-id="42f90-284">클레임</span><span class="sxs-lookup"><span data-stu-id="42f90-284">Claims</span></span>

<span data-ttu-id="42f90-285">클레임은 인증된 사용자의 속성을 나타내는 이름 값 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-285">Claims are name value pairs that represent properties of an authenticated user.</span></span> <span data-ttu-id="42f90-286">예를 들어 사용자의 직원 번호를 클레임으로 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-286">For example, you might store users' employee number as a claim.</span></span> <span data-ttu-id="42f90-287">그런 다음, 클레임을 권한 부여 정책의 일부로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-287">Claims can then be used as part of authorization policies.</span></span> <span data-ttu-id="42f90-288">다음 예제와 같이 "EmployeeNumber"라는 클레임이 있어야 하는 "EmployeeOnly"라는 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-288">You could create a policy called "EmployeeOnly" that requires the existence of a claim called "EmployeeNumber", as shown in this example:</span></span>

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

<span data-ttu-id="42f90-289">이 정책은 위에서 설명한 대로 \[Authorize\] 특성과 함께 사용하여 모든 컨트롤러 및/또는 작업을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-289">This policy could then be used with the \[Authorize\] attribute to protect any controller and/or action, as described above.</span></span>

#### <a name="securing-web-apis"></a><span data-ttu-id="42f90-290">웹 API 보안</span><span class="sxs-lookup"><span data-stu-id="42f90-290">Securing web APIs</span></span>

<span data-ttu-id="42f90-291">대부분의 웹 API는 토큰 기반 인증 시스템을 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-291">Most web APIs should implement a token-based authentication system.</span></span> <span data-ttu-id="42f90-292">토큰 인증은 상태 비저장이며 확장 가능하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-292">Token authentication is stateless and designed to be scalable.</span></span> <span data-ttu-id="42f90-293">토큰 기반 인증 시스템에서 클라이언트는 먼저 인증 공급자를 통해 인증받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-293">In a token-based authentication system, the client must first authenticate with the authentication provider.</span></span> <span data-ttu-id="42f90-294">성공하면 클라이언트에서 토큰을 발급합니다. 이 토큰은 단순히 암호화 방식으로 의미 있는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-294">If successful, the client is issued a token, which is simply a cryptographically meaningful string of characters.</span></span> <span data-ttu-id="42f90-295">다음으로, 클라이언트에서 API에 요청을 발급해야 할 때 이 토큰을 헤더로 요청에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-295">When the client then needs to issue a request to an API, it adds this token as a header on the request.</span></span> <span data-ttu-id="42f90-296">그런 다음 요청을 완료하기 전에 서버에서 요청 헤더에 있는 토큰의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-296">The server then validates the token found in the request header before completing the request.</span></span> <span data-ttu-id="42f90-297">그림 7-4에서는 이 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-297">Figure 7-4 demonstrates this process.</span></span>

![TokenAuth](./media/image7-4.png)

<span data-ttu-id="42f90-299">**그림 7-4**</span><span class="sxs-lookup"><span data-stu-id="42f90-299">**Figure 7-4.**</span></span> <span data-ttu-id="42f90-300">웹 API에 대한 토큰 기반 인증</span><span class="sxs-lookup"><span data-stu-id="42f90-300">Token-based authentication for Web APIs.</span></span>

> ### <a name="references--security"></a><span data-ttu-id="42f90-301">참고 자료 - 보안</span><span class="sxs-lookup"><span data-stu-id="42f90-301">References – Security</span></span>
>
> - <span data-ttu-id="42f90-302">**보안 개요 문서**</span><span class="sxs-lookup"><span data-stu-id="42f90-302">**Security Docs Overview**</span></span>  
>   https://docs.microsoft.com/aspnet/core/security/
> - <span data-ttu-id="42f90-303">**ASP.NET Core 앱에 SSL 적용**</span><span class="sxs-lookup"><span data-stu-id="42f90-303">**Enforcing SSL in an ASP.NET Core App**</span></span>  
>   <https://docs.microsoft.com/aspnet/core/security/enforcing-ssl>
> - <span data-ttu-id="42f90-304">**ID 소개**</span><span class="sxs-lookup"><span data-stu-id="42f90-304">**Introduction to Identity**</span></span>  
>   <https://docs.microsoft.com/aspnet/core/security/authentication/identity>
> - <span data-ttu-id="42f90-305">**권한 부여 소개**</span><span class="sxs-lookup"><span data-stu-id="42f90-305">**Introduction to Authorization**</span></span>  
>   <https://docs.microsoft.com/aspnet/core/security/authorization/introduction>
> - <span data-ttu-id="42f90-306">**Azure App Service에서 API Apps에 대한 인증 및 권한 부여**</span><span class="sxs-lookup"><span data-stu-id="42f90-306">**Authentication and Authorization for API Apps in Azure App Service**</span></span>  
>   <https://docs.microsoft.com/azure/app-service-api/app-service-api-authentication>

## <a name="client-communication"></a><span data-ttu-id="42f90-307">클라이언트 통신</span><span class="sxs-lookup"><span data-stu-id="42f90-307">Client communication</span></span>

<span data-ttu-id="42f90-308">ASP.NET Core 앱은 페이지를 제공하고 웹 API를 통해 데이터에 대한 요청에 응답하는 것 외에도, 연결된 클라이언트와 직접 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-308">In addition to serving pages and responding to requests for data via web APIs, ASP.NET Core apps can communicate directly with connected clients.</span></span> <span data-ttu-id="42f90-309">이 아웃바운드 통신에는 다양한 전송 기술이 사용될 수 있으며, WebSockets가 가장 일반적인 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-309">This outbound communication can use a variety of transport technologies, the most common being WebSockets.</span></span> <span data-ttu-id="42f90-310">ASP.NET Core SignalR은 응용 프로그램에 실시간 서버-클라이언트 통신 기능을 간단하게 추가할 수 있게 해 주는 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-310">ASP.NET Core SignalR is a library that makes it simple to add real-time server-to-client communication functionality to your applications.</span></span> <span data-ttu-id="42f90-311">SignalR은 WebSockets를 포함한 다양한 전송 기술을 지원하며 개발자의 다양한 구현 세부 정보를 추상화합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-311">SignalR supports a variety of transport technologies, including WebSockets, and abstracts away many of the implementation details from the developer.</span></span>

<span data-ttu-id="42f90-312">ASP.NET Core SignalR은 ASP.NET Core 2.1과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-312">ASP.NET Core SignalR is available with ASP.NET Core 2.1.</span></span>

<span data-ttu-id="42f90-313">WebSockets를 직접 사용하든 다른 기술을 사용하든 실시간 클라이언트 통신은 다양한 응용 프로그램 시나리오에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-313">Real-time client communication, whether using WebSockets directly or other techniques, are useful in a variety of application scenarios.</span></span> <span data-ttu-id="42f90-314">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-314">Some examples include:</span></span>

- <span data-ttu-id="42f90-315">라이브 대화방 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="42f90-315">Live chat room applications</span></span>

- <span data-ttu-id="42f90-316">응용 프로그램 모니터링</span><span class="sxs-lookup"><span data-stu-id="42f90-316">Monitoring applications</span></span>

- <span data-ttu-id="42f90-317">작업 진행 상황 업데이트</span><span class="sxs-lookup"><span data-stu-id="42f90-317">Job progress updates</span></span>

- <span data-ttu-id="42f90-318">알림</span><span class="sxs-lookup"><span data-stu-id="42f90-318">Notifications</span></span>

- <span data-ttu-id="42f90-319">대화형 Forms 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="42f90-319">Interactive forms applications</span></span>

<span data-ttu-id="42f90-320">응용 프로그램에 클라이언트 통신을 빌드하는 경우 일반적으로 다음 두 가지 구성 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-320">When building client communication into your applications, there are typically two components:</span></span>

- <span data-ttu-id="42f90-321">서버 쪽 연결 관리자(SignalR Hub, WebSocketManager WebSocketHandler)</span><span class="sxs-lookup"><span data-stu-id="42f90-321">Server-side connection manager (SignalR Hub, WebSocketManager WebSocketHandler)</span></span>

- <span data-ttu-id="42f90-322">클라이언트 쪽 라이브러리</span><span class="sxs-lookup"><span data-stu-id="42f90-322">Client-side library</span></span>

<span data-ttu-id="42f90-323">클라이언트는 브라우저에 국한되지 않으며, 모바일 앱, 콘솔 앱 및 다른 네이티브 앱은 SignalR/WebSockets를 사용하여 통신할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-323">Clients aren't limited to browsers – mobile apps, console apps, and other native apps can also communicate using SignalR/WebSockets.</span></span> <span data-ttu-id="42f90-324">간단한 다음 프로그램에서는 WebSocketManager 샘플 응용 프로그램의 일부로 채팅 응용 프로그램에 보내진 모든 콘텐츠를 콘솔에 에코합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-324">The following simple program echoes all content sent to a chat application to the console, as part of a WebSocketManager sample application:</span></span>

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
}
```

<span data-ttu-id="42f90-325">응용 프로그램이 클라이언트 응용 프로그램과 직접 통신하는 방법을 고려하고, 실시간 통신이 앱의 사용자 환경을 향상시키는지 여부를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="42f90-325">Consider ways in which your applications communicate directly with client applications, and consider whether real-time communication would improve your app's user experience.</span></span>

> ### <a name="references--client-communication"></a><span data-ttu-id="42f90-326">참고 자료 - 클라이언트 통신</span><span class="sxs-lookup"><span data-stu-id="42f90-326">References – Client Communication</span></span>
>
> - <span data-ttu-id="42f90-327">**ASP.NET Core SignalR**</span><span class="sxs-lookup"><span data-stu-id="42f90-327">**ASP.NET Core SignalR**</span></span>  
>   <https://github.com/aspnet/SignalR>
> - <span data-ttu-id="42f90-328">**WebSocket 관리자**</span><span class="sxs-lookup"><span data-stu-id="42f90-328">**WebSocket Manager**</span></span>  
>   https://github.com/radu-matei/websocket-manager

## <a name="domain-driven-design--should-you-apply-it"></a><span data-ttu-id="42f90-329">도메인 기반 디자인 - 적용해야 할까요?</span><span class="sxs-lookup"><span data-stu-id="42f90-329">Domain-driven design – Should you apply it?</span></span>

<span data-ttu-id="42f90-330">DDD(도메인 기반 디자인)는 _비즈니스 도메인_에 초점을 맞춘 소프트웨어를 빌드하는 민첩한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-330">Domain-Driven Design (DDD) is an agile approach to building software that emphasizes focusing on the _business domain_.</span></span> <span data-ttu-id="42f90-331">실제 시스템의 작동 방식을 개발자와 관련시킬 수 있는 비즈니스 도메인 전문가와의 의사 소통과 상호 작용에 크게 중점을 둡니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-331">It places a heavy emphasis on communication and interaction with business domain expert(s) who can relate to the developers how the real-world system works.</span></span> <span data-ttu-id="42f90-332">예를 들어 주식 거래를 처리하는 시스템을 구축하는 경우 도메인 전문가는 경험이 많은 주식 중개인일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-332">For example, if you're building a system that handles stock trades, your domain expert might be an experienced stock broker.</span></span> <span data-ttu-id="42f90-333">DDD는 크고 복잡한 비즈니스 문제를 해결하도록 설계되었으며, 도메인을 이해하고 모델링에 대한 투자가 그다지 가치가 없기 때문에 작고 단순한 응용 프로그램에는 적합하지 않은 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-333">DDD is designed to address large, complex business problems, and is often not appropriate for smaller, simpler applications, as the investment in understanding and modeling the domain is not worth it.</span></span>

<span data-ttu-id="42f90-334">DDD 접근 방식에 따라 소프트웨어를 빌드하는 경우 팀(기술 이외의 이해 관계자 및 참가자 포함)은 문제 영역에 대한 _유비쿼터스 언어_를 개발해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-334">When building software following a DDD approach, your team (including non-technical stakeholders and contributors) should develop a _ubiquitous language_ for the problem space.</span></span> <span data-ttu-id="42f90-335">즉, 모델링된 실제 개념, 해당 소프트웨어 및 개념을 유지하기 위해 존재할 수 있는 구조(예: 데이터베이스 테이블)에 대해 동일한 용어가 사용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-335">That is, the same terminology should be used for the real-world concept being modeled, the software equivalent, and any structures that might exist to persist the concept (for example, database tables).</span></span> <span data-ttu-id="42f90-336">따라서 유비쿼터스 언어로 설명된 개념은 _도메인 모델_의 기초를 형성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-336">Thus, the concepts described in the ubiquitous language should form the basis for your _domain model_.</span></span>

<span data-ttu-id="42f90-337">도메인 모델은 시스템의 동작을 나타내기 위해 서로 상호 작용하는 개체로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-337">Your domain model is comprised of objects that interact with one another to represent the behavior of the system.</span></span> <span data-ttu-id="42f90-338">이러한 개체는 다음과 같은 범주로 분류될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-338">These objects may fall into the following categories:</span></span>

- <span data-ttu-id="42f90-339">[엔터티](https://deviq.com/entity/) - ID의 스레드가 있는 개체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-339">[Entities](https://deviq.com/entity/), which represent objects with a thread of identity.</span></span> <span data-ttu-id="42f90-340">엔터티는 일반적으로 나중에 검색할 수 있는 키를 사용하여 지속성에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-340">Entities are typically stored in persistence with a key by which they can later be retrieved.</span></span>

- <span data-ttu-id="42f90-341">[집계](https://deviq.com/aggregate-pattern/) - 하나의 단위로 유지되어야 하는 개체 그룹을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-341">[Aggregates](https://deviq.com/aggregate-pattern/), which represent groups of objects that should be persisted as a unit.</span></span>

- <span data-ttu-id="42f90-342">[값 개체](https://deviq.com/value-object/) - 해당 속성 값의 합계를 기준으로 비교할 수 있는 개념을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-342">[Value objects](https://deviq.com/value-object/), which represent concepts that can be compared on the basis of the sum of their property values.</span></span> <span data-ttu-id="42f90-343">예를 들어 DateRange는 시작 날짜와 종료 날짜로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-343">For example, DateRange consisting of a start and end date.</span></span>

- <span data-ttu-id="42f90-344">[도메인 이벤트](https://martinfowler.com/eaaDev/DomainEvent.html) - 시스템의 다른 부분에 관심 있는 시스템 내에서 발생하는 상황을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-344">[Domain events](https://martinfowler.com/eaaDev/DomainEvent.html), which represent things happening within the system that are of interest to other parts of the system.</span></span>

<span data-ttu-id="42f90-345">DDD 도메인 모델은 모델 내에서 복잡한 동작을 캡슐화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-345">Note that a DDD domain model should encapsulate complex behavior within the model.</span></span> <span data-ttu-id="42f90-346">특히 엔터티는 단순히 속성의 컬렉션이 되어서는 안됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-346">Entities, in particular, should not merely be collections of properties.</span></span> <span data-ttu-id="42f90-347">도메인 모델에 동작이 부족하고 단순히 시스템의 상태만 나타내는 경우 [anemic model(빈혈 모델)](https://deviq.com/anemic-model/)이라고 하며, DDD에서는 바람직하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-347">When the domain model lacks behavior and merely represents the state of the system, it is said to be an [anemic model](https://deviq.com/anemic-model/), which is undesirable in DDD.</span></span>

<span data-ttu-id="42f90-348">이러한 모델 유형 외에도, DDD는 일반적으로 다음과 같은 다양한 패턴을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-348">In addition to these model types, DDD typically employs a variety of patterns:</span></span>

- <span data-ttu-id="42f90-349">[리포지토리](https://deviq.com/repository-pattern/) - 지속성 세부 정보를 추상화합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-349">[Repository](https://deviq.com/repository-pattern/), for abstracting persistence details.</span></span>

- <span data-ttu-id="42f90-350">[팩터리](https://en.wikipedia.org/wiki/Factory_method_pattern) - 지속성 세부 정보를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-350">[Factory](https://en.wikipedia.org/wiki/Factory_method_pattern), for encapsulating complex object creation.</span></span>

- <span data-ttu-id="42f90-351">도메인 이벤트 - 종속 동작과 트리거 동작을 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-351">Domain events, for decoupling dependent behavior from triggering behavior.</span></span>

- <span data-ttu-id="42f90-352">[서비스](http://gorodinski.com/blog/2012/04/14/services-in-domain-driven-design-ddd/) - 복잡한 동작 및/또는 인프라 구현 세부 정보를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-352">[Services](http://gorodinski.com/blog/2012/04/14/services-in-domain-driven-design-ddd/), for encapsulating complex behavior and/or infrastructure implementation details.</span></span>

- <span data-ttu-id="42f90-353">[명령](https://en.wikipedia.org/wiki/Command_pattern) - 명령 실행을 분리하고 명령 자체를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-353">[Command](https://en.wikipedia.org/wiki/Command_pattern), for decoupling issuing commands and executing the command itself.</span></span>

- <span data-ttu-id="42f90-354">[사양](https://deviq.com/specification-pattern/) - 쿼리 세부 정보를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-354">[Specification](https://deviq.com/specification-pattern/), for encapsulating query details.</span></span>

<span data-ttu-id="42f90-355">또한 DDD는 앞에서 설명한 클린 아키텍처의 사용을 권장하여 단위 테스트를 통해 쉽게 확인할 수 있는 느슨한 결합, 캡슐화 및 코드를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-355">DDD also recommends the use of the Clean Architecture discussed previously, allowing for loose coupling, encapsulation, and code that can easily be verified using unit tests.</span></span>

### <a name="when-should-you-apply-ddd"></a><span data-ttu-id="42f90-356">DDD를 적용해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="42f90-356">When should you apply DDD</span></span>

<span data-ttu-id="42f90-357">DDD는 단지 기술적인 측면이 아닌 비즈니스 측면에서 복잡한 큰 응용 프로그램에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-357">DDD is well-suited to large applications with significant business (not just technical) complexity.</span></span> <span data-ttu-id="42f90-358">응용 프로그램에는 도메인 전문가의 지식이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-358">The application should require the knowledge of domain experts.</span></span> <span data-ttu-id="42f90-359">도메인 모델 자체에는 데이터 저장소의 다양한 레코드에 대한 현재 상태를 저장하고 검색하는 것 이상의 비즈니스 규칙과 상호 작용을 나타내는 중요한 동작이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-359">There should be significant behavior in the domain model itself, representing business rules and interactions beyond simply storing and retrieving the current state of various records from data stores.</span></span>

### <a name="when-shouldnt-you-apply-ddd"></a><span data-ttu-id="42f90-360">DDD를 적용하지 않아야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="42f90-360">When shouldn't you apply DDD</span></span>

<span data-ttu-id="42f90-361">DDD는 모델링, 아키텍처 및 통신에 대한 투자를 수반하며, 더 작은 응용 프로그램 또는 기본적으로 CRUD(만들기/읽기/업데이트/삭제)인 응용 프로그램에 대해 보증되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-361">DDD involves investments in modeling, architecture, and communication that may not be warranted for smaller applications or applications that are essentially just CRUD (create/read/update/delete).</span></span> <span data-ttu-id="42f90-362">DDD를 수행하는 응용 프로그램에 접근하도록 선택했지만 동작이 없는 빈혈 모델이 도메인에 있는 경우 이 방법을 다시 생각해 볼 필요가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-362">If you choose to approach your application following DDD, but find that your domain has an anemic model with no behavior, you may need to rethink your approach.</span></span> <span data-ttu-id="42f90-363">응용 프로그램에 DDD가 필요하지 않거나, 데이터베이스 또는 사용자 인터페이스가 아닌 도메인 모델에 비즈니스 논리를 캡슐화하도록 응용 프로그램을 리팩터링하는 데 도움이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-363">Either your application may not need DDD, or you may need assistance refactoring your application to encapsulate business logic in the domain model, rather than in your database or user interface.</span></span>

<span data-ttu-id="42f90-364">하이브리드 방식은 응용 프로그램의 트랜잭션 영역 또는 복잡한 영역에만 DDD를 사용하는 것이지만, 응용 프로그램의 간단한 CRUD 또는 읽기 전용 부분에는 사용하지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-364">A hybrid approach would be to only use DDD for the transactional or more complex areas of the application, but not for simpler CRUD or read-only portions of the application.</span></span> <span data-ttu-id="42f90-365">예를 들어 데이터를 쿼리하여 보고서를 표시하거나 대시보드에 대한 데이터를 시각화하는 경우 집계의 제약 조건이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-365">For instance, you needn't have the constraints of an Aggregate if you're querying data to display a report or to visualize data for a dashboard.</span></span> <span data-ttu-id="42f90-366">이러한 요구 사항에 대해서는 전적으로 별도의 간단한 읽기 모델을 갖출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-366">It's perfectly acceptable to have a separate, simpler read model for such requirements.</span></span>

> ### <a name="references--domain-driven-design"></a><span data-ttu-id="42f90-367">참고 자료 - 도메인 기반 디자인</span><span class="sxs-lookup"><span data-stu-id="42f90-367">References – Domain-Driven Design</span></span>
>
> - <span data-ttu-id="42f90-368">**일반 영어 버전의 DDD(StackOverflow 응답)**</span><span class="sxs-lookup"><span data-stu-id="42f90-368">**DDD in Plain English (StackOverflow Answer)**</span></span>  
>   <https://stackoverflow.com/questions/1222392/can-someone-explain-domain-driven-design-ddd-in-plain-english-please/1222488#1222488>

## <a name="deployment"></a><span data-ttu-id="42f90-369">배포</span><span class="sxs-lookup"><span data-stu-id="42f90-369">Deployment</span></span>

<span data-ttu-id="42f90-370">호스팅되는 위치에 관계없이 ASP.NET Core 응용 프로그램을 배포하는 프로세스에는 몇 가지 단계가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-370">There are a few steps involved in the process of deploying your ASP.NET Core application, regardless of where it will be hosted.</span></span> <span data-ttu-id="42f90-371">첫 번째 단계는 dotnet publish CLI 명령을 사용하여 수행할 수 있는 응용 프로그램을 게시하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-371">The first step is to publish the application, which can be done using the dotnet publish CLI command.</span></span> <span data-ttu-id="42f90-372">이렇게 하면 응용 프로그램이 컴파일되고 응용 프로그램을 실행하는 데 필요한 모든 파일이 지정된 폴더에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-372">This will compile the application and place all of the files needed to run the application into a designated folder.</span></span> <span data-ttu-id="42f90-373">Visual Studio에서 배포하는 경우 이 단계가 자동으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-373">When you deploy from Visual Studio, this step is performed for you automatically.</span></span> <span data-ttu-id="42f90-374">게시 폴더에는 응용 프로그램 및 해당 종속성에 대한 .exe 및 .dll 파일이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-374">The publish folder contains .exe and .dll files for the application and its dependencies.</span></span> <span data-ttu-id="42f90-375">자체 포함된 응용 프로그램에는 .NET 런타임 버전도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-375">A self-contained application will also include a version of the .NET runtime.</span></span> <span data-ttu-id="42f90-376">ASP.NET Core 응용 프로그램에는 구성 파일, 정적 클라이언트 자산 및 MVC 뷰도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-376">ASP.NET Core applications will also include configuration files, static client assets, and MVC views.</span></span>

<span data-ttu-id="42f90-377">ASP.NET Core 응용 프로그램은 응용 프로그램(또는 서버)이 충돌하는 경우 서버를 부팅하고 다시 시작할 때 시작해야 하는 콘솔 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-377">ASP.NET Core applications are console applications that must be started when the server boots and restarted if the application (or server) crashes.</span></span> <span data-ttu-id="42f90-378">프로세스 관리자는 이 프로세스를 자동화하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-378">A process manager can be used to automate this process.</span></span> <span data-ttu-id="42f90-379">ASP.NET Core에 대한 가장 일반적인 프로세스 관리자는 Linux의 Nginx 및 Apache와 Windows의 IIS 또는 Windows 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-379">The most common process managers for ASP.NET Core are Nginx and Apache on Linux and IIS or Windows Service on Windows.</span></span>

<span data-ttu-id="42f90-380">프로세스 관리자 외에도, Kestrel 웹 서버에서 호스팅되는 ASP.NET Core 응용 프로그램은 역방향 프록시 서버를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-380">In addition to a process manager, ASP.NET Core applications hosted in the Kestrel web server must use a reverse proxy server.</span></span> <span data-ttu-id="42f90-381">역방향 프록시 서버는 인터넷에서 HTTP 요청을 받고, 몇 가지 항목을 사전 처리한 후에 Kestrel에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-381">A reverse proxy server receives HTTP requests from the internet and forwards them to Kestrel after some preliminary handling.</span></span> <span data-ttu-id="42f90-382">역방향 프록시 서버는 응용 프로그램에 대한 보안 계층을 제공하며, 에지 배포(인터넷의 트래픽에 노출됨)에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-382">Reverse proxy servers provide a layer of security for the application, and are required for edge deployments (exposed to traffic from the Internet).</span></span> <span data-ttu-id="42f90-383">Kestrel은 비교적 새롭고 특정 공격에 대한 방어 체계를 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-383">Kestrel is relatively new and does not yet offer defenses against certain attacks.</span></span> <span data-ttu-id="42f90-384">또한 Kestrel은 동일한 포트에서 여러 응용 프로그램을 호스팅하도록 지원하지 않으므로, 호스트 헤더와 같은 기술은 동일한 포트 및 IP 주소에서 여러 응용 프로그램을 호스팅하도록 설정하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-384">Kestrel also doesn't support hosting multiple applications on the same port, so techniques like host headers cannot be used with it to enable hosting multiple applications on the same port and IP address.</span></span>

![인터넷에 대한 Kestrel](./media/image7-5.png)

<span data-ttu-id="42f90-386">그림 7-5 역방향 프록시 서버 뒤에서 Kestrel에 호스팅되는 ASP.NET</span><span class="sxs-lookup"><span data-stu-id="42f90-386">Figure 7-5 ASP.NET hosted in Kestrel behind a reverse proxy server</span></span>

<span data-ttu-id="42f90-387">역방향 프록시가 도움이 될 수 있는 또 다른 시나리오는 SSL/HTTPS를 사용하여 여러 응용 프로그램을 보호하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-387">Another scenario in which a reverse proxy can be helpful is to secure multiple applications using SSL/HTTPS.</span></span> <span data-ttu-id="42f90-388">이 경우 역방향 프록시에만 SSL을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-388">In this case, only the reverse proxy would need to have SSL configured.</span></span> <span data-ttu-id="42f90-389">그림 7-6과 같이 역방향 프록시 서버와 Kestrel 간의 통신은 HTTP를 통해 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-389">Communication between the reverse proxy server and Kestrel could take place over HTTP, as shown in Figure 7-6.</span></span>

![](./media/image7-6.png)

<span data-ttu-id="42f90-390">그림 7-6 HTTPS 보안 역방향 프록시 서버 뒤에서 호스팅되는 ASP.NET</span><span class="sxs-lookup"><span data-stu-id="42f90-390">Figure 7-6 ASP.NET hosted behind an HTTPS-secured reverse proxy server</span></span>

<span data-ttu-id="42f90-391">점점 더 인기 있는 방법은 ASP.NET Core 응용 프로그램을 Docker 컨테이너에 호스팅하는 것이며, 이 컨테이너는 클라우드 기반 호스팅을 위해 로컬로 호스팅되거나 Azure에 배포될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-391">An increasingly popular approach is to host your ASP.NET Core application in a Docker container, which then can be hosted locally or deployed to Azure for cloud-based hosting.</span></span> <span data-ttu-id="42f90-392">Docker 컨테이너는 Kestrel에서 실행되는 응용 프로그램 코드를 포함할 수 있으며, 위와 같이 역방향 프록시 서버 뒤에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-392">The Docker container could contain your application code, running on Kestrel, and would be deployed behind a reverse proxy server, as shown above.</span></span>

<span data-ttu-id="42f90-393">Azure에서 응용 프로그램을 호스팅하는 경우 Microsoft Azure Application Gateway를 전용 가상 어플라이언스로 사용하여 여러 서비스를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-393">If you're hosting your application on Azure, you can use Microsoft Azure Application Gateway as a dedicated virtual appliance to provide several services.</span></span> <span data-ttu-id="42f90-394">Application Gateway는 개별 응용 프로그램에 대한 역방향 프록시로 작동하는 것 외에도 다음과 같은 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42f90-394">In addition to acting as a reverse proxy for individual applications, Application Gateway can also offer the following features:</span></span>

- <span data-ttu-id="42f90-395">HTTP 부하 분산</span><span class="sxs-lookup"><span data-stu-id="42f90-395">HTTP load balancing</span></span>

- <span data-ttu-id="42f90-396">SSL 오프로드(인터넷에만 SSL 사용)</span><span class="sxs-lookup"><span data-stu-id="42f90-396">SSL offload (SSL only to Internet)</span></span>

- <span data-ttu-id="42f90-397">종단 간 SSL</span><span class="sxs-lookup"><span data-stu-id="42f90-397">End to End SSL</span></span>

- <span data-ttu-id="42f90-398">다중 사이트 라우팅(단일 Application Gateway에서 최대 20개의 사이트 통합)</span><span class="sxs-lookup"><span data-stu-id="42f90-398">Multi-site routing (consolidate up to 20 sites on a single Application Gateway)</span></span>

- <span data-ttu-id="42f90-399">웹 응용 프로그램 방화벽</span><span class="sxs-lookup"><span data-stu-id="42f90-399">Web application firewall</span></span>

- <span data-ttu-id="42f90-400">Websocket 지원</span><span class="sxs-lookup"><span data-stu-id="42f90-400">Websocket support</span></span>

- <span data-ttu-id="42f90-401">고급 진단</span><span class="sxs-lookup"><span data-stu-id="42f90-401">Advanced diagnostics</span></span>

<span data-ttu-id="42f90-402">_Azure 배포 옵션에 대한 자세한 내용은 [10장](development-process-for-azure.md)을 참조하세요._</span><span class="sxs-lookup"><span data-stu-id="42f90-402">_Learn more about Azure deployment options in [Chapter 10](development-process-for-azure.md)._</span></span>

> ### <a name="references--deployment"></a><span data-ttu-id="42f90-403">참고 자료 - 배포</span><span class="sxs-lookup"><span data-stu-id="42f90-403">References – Deployment</span></span>
>
> - <span data-ttu-id="42f90-404">**호스팅 및 배포 개요**</span><span class="sxs-lookup"><span data-stu-id="42f90-404">**Hosting and Deployment Overview**</span></span>  
>   <https://docs.microsoft.com/aspnet/core/publishing/>
> - <span data-ttu-id="42f90-405">**Kestrel을 역방향 프록시와 함께 사용하는 경우**</span><span class="sxs-lookup"><span data-stu-id="42f90-405">**When to use Kestrel with a reverse proxy**</span></span>  
>   <https://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel#when-to-use-kestrel-with-a-reverse-proxy>
> - <span data-ttu-id="42f90-406">**Docker에서 ASP.NET Core 앱 호스팅**</span><span class="sxs-lookup"><span data-stu-id="42f90-406">**Host ASP.NET Core apps in Docker**</span></span>  
>   <https://docs.microsoft.com/aspnet/core/publishing/docker>
> - <span data-ttu-id="42f90-407">**Azure Application Gateway 소개**</span><span class="sxs-lookup"><span data-stu-id="42f90-407">**Introducing Azure Application Gateway**</span></span>  
>   <https://docs.microsoft.com/azure/application-gateway/application-gateway-introduction>

>[!div class="step-by-step"]
<span data-ttu-id="42f90-408">[이전](common-client-side-web-technologies.md)
[다음](work-with-data-in-asp-net-core-apps.md)</span><span class="sxs-lookup"><span data-stu-id="42f90-408">[Previous](common-client-side-web-technologies.md)
[Next](work-with-data-in-asp-net-core-apps.md)</span></span>
