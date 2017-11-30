---
title: "ASP.NET Core 서비스 및 웹 응용 프로그램 테스트"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | ASP.NET Core 서비스 및 웹 응용 프로그램 테스트"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f756a679befee676db2bf6d402fd7e34b1621b9d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="testing-aspnet-core-services-and-web-apps"></a><span data-ttu-id="2cc72-104">ASP.NET Core 서비스 및 웹 응용 프로그램 테스트</span><span class="sxs-lookup"><span data-stu-id="2cc72-104">Testing ASP.NET Core services and web apps</span></span>

<span data-ttu-id="2cc72-105">컨트롤러는 ASP.NET MVC 웹 응용 프로그램 및 ASP.NET Core API 서비스의 핵심 요소로입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-105">Controllers are a central part of any ASP.NET Core API service and ASP.NET MVC Web application.</span></span> <span data-ttu-id="2cc72-106">따라서 응용 프로그램에 대 한 의도 한 대로 동작 하므로 신뢰도 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-106">As such, you should have confidence they behave as intended for your application.</span></span> <span data-ttu-id="2cc72-107">자동화 된 테스트가이 신뢰도 제공할 수 있습니다 및 프로덕션에 도달 하기 전에 오류를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-107">Automated tests can provide you with this confidence and can detect errors before they reach production.</span></span>

<span data-ttu-id="2cc72-108">컨트롤러 동작 하는 방식을 잘못 되었거나 잘못 된 입력에 따라 테스트 및 수행 하는 비즈니스 작업의 결과에 따라 컨트롤러 응답을 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-108">You need to test how the controller behaves based on valid or invalid inputs, and test controller responses based on the result of the business operation it performs.</span></span> <span data-ttu-id="2cc72-109">그러나 있어야 이러한 종류의 테스트 프로그램 microservices:</span><span class="sxs-lookup"><span data-stu-id="2cc72-109">However, you should have these types of tests your microservices:</span></span>

-   <span data-ttu-id="2cc72-110">단위 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-110">Unit tests.</span></span> <span data-ttu-id="2cc72-111">이러한 응용 프로그램의 개별 구성 요소가 예상 대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-111">These ensure that individual components of the application work as expected.</span></span> <span data-ttu-id="2cc72-112">어설션 구성 API를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-112">Assertions test the component API.</span></span>

-   <span data-ttu-id="2cc72-113">통합 테스트입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-113">Integration tests.</span></span> <span data-ttu-id="2cc72-114">이러한 구성 요소 상호 작용 데이터베이스와 같은 외부 아티팩트에 대해 예상 대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-114">These ensure that component interactions work as expected against external artifacts like databases.</span></span> <span data-ttu-id="2cc72-115">어설션 구성 API, UI 또는 로깅 등 데이터베이스 I/O와 같은 작업의 부작용은 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-115">Assertions can test component API, UI, or the side effects of actions like database I/O, logging, etc.</span></span>

-   <span data-ttu-id="2cc72-116">각 마이크로 서비스에 대 한 기능 테스트입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-116">Functional tests for each microservice.</span></span> <span data-ttu-id="2cc72-117">이러한 응용 프로그램 사용자의 관점에서 예상 대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-117">These ensure that the application works as expected from the user’s perspective.</span></span>

-   <span data-ttu-id="2cc72-118">서비스를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-118">Service tests.</span></span> <span data-ttu-id="2cc72-119">이 동시에 여러 서비스를 테스트를 포함 하 여 종단 간 서비스 사용 사례를 테스트 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-119">These ensure that end-to-end service use cases, including testing multiple services at the same time, are tested.</span></span> <span data-ttu-id="2cc72-120">이러한 종류의 테스트에 대 한 먼저 환경을 준비 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-120">For this type of testing, you need to prepare the environment first.</span></span> <span data-ttu-id="2cc72-121">이 경우 있음을 의미 하는 서비스 시작 (예를 들어를 사용 하 여 docker-작성 위로).</span><span class="sxs-lookup"><span data-stu-id="2cc72-121">In this case, it means starting the services (for example, by using docker-compose up).</span></span>

### <a name="implementing-unit-tests-for-aspnet-core-web-apis"></a><span data-ttu-id="2cc72-122">ASP.NET Core 웹 Api에 대 한 구현 단위 테스트</span><span class="sxs-lookup"><span data-stu-id="2cc72-122">Implementing unit tests for ASP.NET Core Web APIs</span></span>

<span data-ttu-id="2cc72-123">단위 테스트는 인프라와 종속성에서 격리 된 상태에서 응용 프로그램의 일부를 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-123">Unit testing involves testing a part of an application in isolation from its infrastructure and dependencies.</span></span> <span data-ttu-id="2cc72-124">메서드는 테스트 또는 단위 테스트를 수행할 컨트롤러 논리를 단일 작업의 콘텐츠만 경우, 프레임 워크 자체 또는 해당 종속성의 동작이 아닌 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-124">When you unit test controller logic, only the content of a single action or method is tested, not the behavior of its dependencies or of the framework itself.</span></span> <span data-ttu-id="2cc72-125">단위 테스트의 구성 요소 간의 상호 작용 문제를 탐지 되지 않으면-통합 테스트의 목표입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-125">Unit tests do not detect issues in the interaction between components—that is the purpose of integration testing.</span></span>

<span data-ttu-id="2cc72-126">테스트 컨트롤러 작업 하면 단위로 동작에만 집중 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-126">As you unit test your controller actions, make sure you focus only on their behavior.</span></span> <span data-ttu-id="2cc72-127">컨트롤러 단위 테스트 필터, 라우팅 또는 모델 바인딩 등으로를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-127">A controller unit test avoids things like filters, routing, or model binding.</span></span> <span data-ttu-id="2cc72-128">한 작업에 집중할 것 때문에 단위 테스트는 일반적으로 쓰려고 간단 하 고 신속 하 게 실행.</span><span class="sxs-lookup"><span data-stu-id="2cc72-128">Because they focus on testing just one thing, unit tests are generally simple to write and quick to run.</span></span> <span data-ttu-id="2cc72-129">많은 오버 헤드 없이 자주 잘 작성 된 일련의 단위 테스트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-129">A well-written set of unit tests can be run frequently without much overhead.</span></span>

<span data-ttu-id="2cc72-130">단위 테스트 xUnit.net, MSTest, Moq, NUnit 등 테스트 프레임 워크에 따라 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-130">Unit tests are implemented based on test frameworks like xUnit.net, MSTest, Moq, or NUnit.</span></span> <span data-ttu-id="2cc72-131">EShopOnContainers 샘플 응용 프로그램에 대 한 XUnit 사용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-131">For the eShopOnContainers sample application, we are using XUnit.</span></span>

<span data-ttu-id="2cc72-132">직접 new 키워드를 사용 하 여 C에서 컨트롤러 클래스를 인스턴스화하는 Web API 컨트롤러에 대 한 단위 테스트를 작성 하는 경우\#, 테스트 가능한 한 빠르게 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-132">When you write a unit test for a Web API controller, you instantiate the controller class directly using the new keyword in C\#, so that the test will run as fast as possible.</span></span> <span data-ttu-id="2cc72-133">다음 예제에서는 사용 하는 경우이 작업을 수행 하는 방법을 보여 줍니다. [XUnit](https://xunit.github.io/) 테스트 프레임 워크입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-133">The following example shows how to do this when using [XUnit](https://xunit.github.io/) as the Test framework.</span></span>

```csharp
[Fact]
public void Add_new_Order_raises_new_event()
{
    // Arrange
    var street = " FakeStreet ";
    var city = "FakeCity";
    // Other variables omitted for brevity ...
    // Act
    var fakeOrder = new Order(new Address(street, city, state, country, zipcode),
        cardTypeId, cardNumber,
        cardSecurityNumber, cardHolderName,
        cardExpiration);
    // Assert
    Assert.Equal(fakeOrder.DomainEvents.Count, expectedResult);
}
```

### <a name="implementing-integration-and-functional-tests-for-each-microservice"></a><span data-ttu-id="2cc72-134">통합 및 각 마이크로 서비스에 대 한 기능 테스트를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-134">Implementing integration and functional tests for each microservice</span></span>

<span data-ttu-id="2cc72-135">앞에서 설명한 것 처럼 통합 테스트 및 기능 테스트 목표 및 목적에 따라 가집니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-135">As noted, integration tests and functional tests have different purposes and goals.</span></span> <span data-ttu-id="2cc72-136">그러나 구현 하는 방법은 모두 ASP.NET Core 컨트롤러를 테스트할 때 이므로 마찬가지로이 섹션의 통합 테스트에 집중 하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-136">However, the way you implement both when testing ASP.NET Core controllers is similar, so in this section we concentrate on integration tests.</span></span>

<span data-ttu-id="2cc72-137">통합 테스트 조합 하는 경우 응용 프로그램의 구성 요소가 제대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-137">Integration testing ensures that an application's components function correctly when assembled.</span></span> <span data-ttu-id="2cc72-138">ASP.NET Core 지원 통합 단위 테스트 프레임 워크 및 네트워크 오버 헤드 없이 요청을 처리 하는 데 사용할 수 있는 기본 제공 테스트 웹 호스트를 사용 하 여 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-138">ASP.NET Core supports integration testing using unit test frameworks and a built-in test web host that can be used to handle requests without network overhead.</span></span>

<span data-ttu-id="2cc72-139">통합 테스트에는 단위 테스트의 경우와 달리 데이터베이스, 파일 시스템, 네트워크 리소스 또는 웹 요청 및 응답 예: 응용 프로그램 인프라 문제가 자주 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-139">Unlike unit testing, integration tests frequently involve application infrastructure concerns, such as a database, file system, network resources, or web requests and responses.</span></span> <span data-ttu-id="2cc72-140">단위 테스트 fakes를 사용 하거나 대신 이러한 문제는 개체의 모의 알림.</span><span class="sxs-lookup"><span data-stu-id="2cc72-140">Unit tests use fakes or mock objects in place of these concerns.</span></span> <span data-ttu-id="2cc72-141">하지만 통합 테스트의 목적은 시스템 통합 테스트에 대 한 하거나 하지 않으면 fakes를 사용 하 여 개체의 모의 알림 하므로 이러한 시스템에 예상 대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-141">But the purpose of integration tests is to confirm that the system works as expected with these systems, so for integration testing you do not use fakes or mock objects.</span></span> <span data-ttu-id="2cc72-142">대신, 데이터베이스 액세스 또는 서비스 호출에서 다른 서비스와 같은 인프라를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-142">Instead, you include the infrastructure, like database access or service invocation from other services.</span></span>

<span data-ttu-id="2cc72-143">단위 테스트 보다 더 큰 세그먼트의 코드를 실행 하는 통합 테스트 및 통합 테스트 인프라 요소에 의존 하기 때문에 예제 규모도 더 훨씬 크기 단위 테스트 보다 느립니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-143">Because integration tests exercise larger segments of code than unit tests, and because integration tests rely on infrastructure elements, they tend to be orders of magnitude slower than unit tests.</span></span> <span data-ttu-id="2cc72-144">따라서 것이 작성 하 고 실행할 통합 테스트의 수를 제한 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-144">Thus, it is a good idea to limit how many integration tests you write and run.</span></span>

<span data-ttu-id="2cc72-145">ASP.NET Core를 실행할 수 있는지 테스트 더 빠르게 실제 웹 호스트를 사용 하는 경우를 의미 하는 기본 제공 테스트 웹 호스트 네트워크 오버 헤드 없이 HTTP 요청을 처리 하는 데 사용할 수 있는 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-145">ASP.NET Core includes a built-in test web host that can be used to handle HTTP requests without network overhead, meaning that you can run those tests faster when using a real web host.</span></span> <span data-ttu-id="2cc72-146">테스트 웹 호스트 Microsoft.AspNetCore.TestHost으로 NuGet 구성 요소에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-146">The test web host is available in a NuGet component as Microsoft.AspNetCore.TestHost.</span></span> <span data-ttu-id="2cc72-147">통합 테스트 프로젝트에 추가할 수 있으며, 응용 프로그램의 ASP.NET Core를 호스트 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-147">It can be added to integration test projects and used to host ASP.NET Core applications.</span></span>

<span data-ttu-id="2cc72-148">통합 테스트에 대 한 만들면 ASP.NET Core 컨트롤러는 다음 코드에서 볼 수 있듯이 테스트 호스트를 통해 컨트롤러를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-148">As you can see in the following code, when you create integration tests for ASP.NET Core controllers, you instantiate the controllers through the test host.</span></span> <span data-ttu-id="2cc72-149">이 HTTP 요청에 비교할 수 있지만 보다 빠르게 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-149">This is comparable to an HTTP request, but it runs faster.</span></span>

```csharp
public class PrimeWebDefaultRequestShould
{
    private readonly TestServer _server;
    private readonly HttpClient _client;

    public PrimeWebDefaultRequestShould()
    {
        // Arrange
        _server = new TestServer(new WebHostBuilder()
           .UseStartup<Startup>());
           _client = _server.CreateClient();
    }

    [Fact]
    public async Task ReturnHelloWorld()
    {
        // Act
        var response = await _client.GetAsync("/");
        response.EnsureSuccessStatusCode();
        var responseString = await response.Content.ReadAsStringAsync();
        // Assert
        Assert.Equal("Hello World!", responseString);
    }
}
```

#### <a name="additional-resources"></a><span data-ttu-id="2cc72-150">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="2cc72-150">Additional resources</span></span>

-   <span data-ttu-id="2cc72-151">**Steve Smith 합니다. 테스트 컨트롤러** (ASP.NET Core) [ *https://docs.microsoft.com/aspnet/core/mvc/controllers/testing*](https://docs.microsoft.com/aspnet/core/mvc/controllers/testing)</span><span class="sxs-lookup"><span data-stu-id="2cc72-151">**Steve Smith. Testing controllers** (ASP.NET Core) [*https://docs.microsoft.com/aspnet/core/mvc/controllers/testing*](https://docs.microsoft.com/aspnet/core/mvc/controllers/testing)</span></span>

-   <span data-ttu-id="2cc72-152">**Steve Smith 합니다. 통합 테스트** (ASP.NET Core) [ *https://docs.microsoft.com/aspnet/core/testing/integration-testing*](https://docs.microsoft.com/aspnet/core/testing/integration-testing)</span><span class="sxs-lookup"><span data-stu-id="2cc72-152">**Steve Smith. Integration testing** (ASP.NET Core) [*https://docs.microsoft.com/aspnet/core/testing/integration-testing*](https://docs.microsoft.com/aspnet/core/testing/integration-testing)</span></span>

-   <span data-ttu-id="2cc72-153">**.NET Core dotnet 테스트를 사용 하 여의 단위 테스트를**
    [*https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test*](https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test)</span><span class="sxs-lookup"><span data-stu-id="2cc72-153">**Unit testing in .NET Core using dotnet test**
[*https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test*](https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test)</span></span>

-   <span data-ttu-id="2cc72-154">**xUnit.net**합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-154">**xUnit.net**.</span></span> <span data-ttu-id="2cc72-155">공식 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-155">Official site.</span></span>
    [<span data-ttu-id="2cc72-156">*https://xunit.github.io/*</span><span class="sxs-lookup"><span data-stu-id="2cc72-156">*https://xunit.github.io/*</span></span>](https://xunit.github.io/)

-   <span data-ttu-id="2cc72-157">**단위 테스트 기본 사항입니다. ** 
     [ *https://msdn.microsoft.com/en-us/library/hh694602.aspx*](https://msdn.microsoft.com/en-us/library/hh694602.aspx)</span><span class="sxs-lookup"><span data-stu-id="2cc72-157">**Unit Test Basics.**
[*https://msdn.microsoft.com/en-us/library/hh694602.aspx*](https://msdn.microsoft.com/en-us/library/hh694602.aspx)</span></span>

-   <span data-ttu-id="2cc72-158">**Moq**합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-158">**Moq**.</span></span> <span data-ttu-id="2cc72-159">GitHub 리포지토리 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-159">GitHub repo.</span></span>
    [<span data-ttu-id="2cc72-160">*https://github.com/moq/moq*</span><span class="sxs-lookup"><span data-stu-id="2cc72-160">*https://github.com/moq/moq*</span></span>](https://github.com/moq/moq)

-   <span data-ttu-id="2cc72-161">**NUnit**합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-161">**NUnit**.</span></span> <span data-ttu-id="2cc72-162">공식 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-162">Official site.</span></span>
    [<span data-ttu-id="2cc72-163">*https://www.nunit.org/*</span><span class="sxs-lookup"><span data-stu-id="2cc72-163">*https://www.nunit.org/*</span></span>](https://www.nunit.org/)

### <a name="implementing-service-tests-on-a-multi-container-application"></a><span data-ttu-id="2cc72-164">서비스를 구현 하는 다중 컨테이너 응용 프로그램에서 테스트를</span><span class="sxs-lookup"><span data-stu-id="2cc72-164">Implementing service tests on a multi-container application</span></span> 

<span data-ttu-id="2cc72-165">다중 컨테이너 응용 프로그램을 테스트할 때 앞에서 설명한 것 처럼 모든 microservices Docker 호스트 또는 컨테이너 클러스터 내에서 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-165">As noted earlier, when you test multi-container applications, all the microservices need to be running within the Docker host or container cluster.</span></span> <span data-ttu-id="2cc72-166">여러 microservices 관련 된 여러 작업을 포함 하는 종단 간 서비스 테스트 배포 및 Docker 호스트에서 docker를 실행 하 여 전체 응용 프로그램을 시작 해야 할-구성 작업 (또는 이와 비슷한 메커니즘은 orchestrator를 사용 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="2cc72-166">End-to-end service tests that include multiple operations involving several microservices require you to deploy and start the whole application in the Docker host by running docker-compose up (or a comparable mechanism if you are using an orchestrator).</span></span> <span data-ttu-id="2cc72-167">전체 응용 프로그램 및 서버의 모든 서비스가 실행 되 면, 종단 간 통합 및 기능 테스트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-167">Once the whole application and all its services is running, you can execute end-to-end integration and functional tests.</span></span>

<span data-ttu-id="2cc72-168">몇 가지 방법으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-168">There are a few approaches you can use.</span></span> <span data-ttu-id="2cc72-169">사용 하 여 응용 프로그램 (또는 compose.ci.build.yml docker와 같은 비슷한 루틴)을 배포 하는 docker compose.yml 파일에서 솔루션 수준에서 확장할 수 있습니다 사용할 진입점 [dotnet 테스트](https://docs.microsoft.com/dotnet/core/tools/dotnet-test)합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-169">In the docker-compose.yml file that you use to deploy the application (or similar ones, like docker-compose.ci.build.yml), at the solution level you can expand the entry point to use [dotnet test](https://docs.microsoft.com/dotnet/core/tools/dotnet-test).</span></span> <span data-ttu-id="2cc72-170">또한 대상으로 하는 이미지에서 테스트를 실행 하는 다른 구성 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-170">You can also use another compose file that would run your tests in the image you are targeting.</span></span> <span data-ttu-id="2cc72-171">다른 구성 파일을 사용 하 여 microservices 및 컨테이너에 있는 데이터베이스를 포함 하는 통합 테스트에 대 한, 테스트를 실행 하기 전에 관련된 데이터는 원래 상태로 항상 다시 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-171">By using another compose file for integration tests that includes your microservices and databases on containers, you can make sure that the related data is always reset to its original state before running the tests.</span></span>

<span data-ttu-id="2cc72-172">작성할 응용 프로그램에 실행 되 면 Visual Studio를 실행 하는 경우 중단점 및 예외를 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-172">Once the compose application is up and running, you can take advantage of breakpoints and exceptions if you are running Visual Studio.</span></span> <span data-ttu-id="2cc72-173">또는 Visual Studio Team Services 또는 다른 CI/CD 시스템을 지 원하는 Docker 컨테이너에 CI 파이프라인에서 자동으로 통합 테스트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc72-173">Or you can run the integration tests automatically in your CI pipeline in Visual Studio Team Services or any other CI/CD system that supports Docker containers.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="2cc72-174">[이전] (구독-events.md) [다음] (... /microservice-ddd-cqrs-patterns/index.md)</span><span class="sxs-lookup"><span data-stu-id="2cc72-174">[Previous] (subscribe-events.md) [Next] (../microservice-ddd-cqrs-patterns/index.md)</span></span>
