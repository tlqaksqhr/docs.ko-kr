---
title: "ASP.NET Core MVC 응용 프로그램 테스트"
description: "ASP.NET Core와 Azure의 최신 웹 응용 프로그램을 설계 | ASP.NET Core MVC 응용 프로그램 테스트"
author: ardalis
ms.author: wiwagn
ms.date: 10/08/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d23d0accc33fb8335dff602d6e1d6c8689972906
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="test-aspnet-core-mvc-apps"></a><span data-ttu-id="5fd77-103">ASP.NET Core MVC 응용 프로그램 테스트</span><span class="sxs-lookup"><span data-stu-id="5fd77-103">Test ASP.NET Core MVC Apps</span></span>

> <span data-ttu-id="5fd77-104">_"단위 테스트 제품, 마음에 들지 않으면 가능성이 고객 않습니다 하려고 하거나, 테스트 합니다."_</span><span class="sxs-lookup"><span data-stu-id="5fd77-104">_"If you don't like unit testing your product, most likely your customers won't like to test it, either."_</span></span>
> <span data-ttu-id="5fd77-105">_- Anonymous-</span><span class="sxs-lookup"><span data-stu-id="5fd77-105">_- Anonymous-</span></span>

## <a name="summary"></a><span data-ttu-id="5fd77-106">요약</span><span class="sxs-lookup"><span data-stu-id="5fd77-106">Summary</span></span>

<span data-ttu-id="5fd77-107">복잡성에 관계 없이 소프트웨어 변경 사항에 따라 예기치 않은 방법으로 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-107">Software of any complexity can fail in unexpected ways in response to changes.</span></span> <span data-ttu-id="5fd77-108">따라서 변경을 수행한 후 테스트는 가장 간단한 (또는 최소 중요) 응용 프로그램을 제외 반드시 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-108">Thus, testing after making changes is required for all but the most trivial (or least critical) applications.</span></span> <span data-ttu-id="5fd77-109">소프트웨어 테스트 수동 테스트는 가장 느린 이상 안정적이 고 가장 비용이 많이 드는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-109">Manual testing is the slowest, least reliable, most expensive way to test software.</span></span> <span data-ttu-id="5fd77-110">그러나 응용 프로그램 테스트 가능 이어야 하도록 설계 되지 않은, 사용할 수 있는 유일한 수단 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-110">Unfortunately, if applications are not designed to be testable, it can be the only means available.</span></span> <span data-ttu-id="5fd77-111">아키텍처 원칙으로 배치 하는 다음 장에서 X 작성 된 응용 프로그램 단위 테스트를 수행할 수 있어야 합니다. 및 자동화 된 통합 및 기능 테스트 에서도 ASP.NET Core 응용 프로그램을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-111">Applications written following the architectural principles laid out in chapter X should be unit testable, and ASP.NET Core applications support automated integration and functional testing as well.</span></span>

## <a name="kinds-of-automated-tests"></a><span data-ttu-id="5fd77-112">자동화 된 테스트의 종류</span><span class="sxs-lookup"><span data-stu-id="5fd77-112">Kinds of Automated Tests</span></span>

<span data-ttu-id="5fd77-113">소프트웨어 응용 프로그램에 대 한 자동화 된 테스트의 여러 가지 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-113">There are many kinds of automated tests for software applications.</span></span> <span data-ttu-id="5fd77-114">가장 단순한 가장 낮은 수준의 테스트는 단위 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-114">The simplest, lowest level test is the unit test.</span></span> <span data-ttu-id="5fd77-115">약간 더 높은 수준에서은 통합 테스트 및 기능 테스트입니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-115">At a slightly higher level there are integration tests and functional tests.</span></span> <span data-ttu-id="5fd77-116">다른 종류의 UI 테스트, 부하 테스트, 스트레스 테스트 및 스모크 테스트와 테스트,이 문서의 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-116">Other kinds of tests, like UI tests, load tests, stress tests, and smoke tests, are beyond the scope of this document.</span></span>

### <a name="unit-tests"></a><span data-ttu-id="5fd77-117">단위 테스트</span><span class="sxs-lookup"><span data-stu-id="5fd77-117">Unit Tests</span></span>

<span data-ttu-id="5fd77-118">단위 테스트 응용 프로그램 논리의 단일 부분을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-118">A unit test tests a single part of your application's logic.</span></span> <span data-ttu-id="5fd77-119">더 이상 그럴 것 중 일부를 나열 하 여 설명할 수 있습니다 하나.</span><span class="sxs-lookup"><span data-stu-id="5fd77-119">One can further describe it by listing some of the things that it isn't.</span></span> <span data-ttu-id="5fd77-120">단위 테스트에 대 한 종속성 또는 인프라-어떤 통합 테스트를 사용자 코드가 작동 하는 방법을 테스트 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-120">A unit test doesn't test how your code works with dependencies or infrastructure – that's what integration tests are for.</span></span> <span data-ttu-id="5fd77-121">단위 테스트에서 코드가 작성 되는 프레임 워크를 테스트 하지 않는-것 작동 하거나, 하는 경우 하지 않습니다, 버그 및 해결 방법을 코드 가정해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-121">A unit test doesn't test the framework your code is written on – you should assume it works or, if you find it doesn't, file a bug and code a workaround.</span></span> <span data-ttu-id="5fd77-122">단위 테스트 프로세스 및 메모리에 완전히 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-122">A unit test runs completely in memory and in process.</span></span> <span data-ttu-id="5fd77-123">파일 시스템, 네트워크 또는 데이터베이스와 통신 하지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-123">It doesn't communicate with the file system, the network, or a database.</span></span> <span data-ttu-id="5fd77-124">단위 테스트 에서만 코드를 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-124">Unit tests should only test your code.</span></span>

<span data-ttu-id="5fd77-125">단위 테스트 코드, 외부 종속성이 없고 단일 단위만 테스트 사실로 매우 빠르게 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-125">Unit tests, by virtue of the fact that they test only a single unit of your code, with no external dependencies, should execute extremely quickly.</span></span> <span data-ttu-id="5fd77-126">따라서 몇 초 후에 수백 개의 단위 테스트의 테스트 도구 모음을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-126">Thus, you should be able to run test suites of hundreds of unit tests in a few seconds.</span></span> <span data-ttu-id="5fd77-127">자주 이상적으로 모든 자동화 된 빌드 및 확실히 공유 소스 제어 리포지토리에 모든 푸시하기 전에 실행할 빌드 서버에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-127">Run them frequently, ideally before every push to a shared source control repository, and certainly with every automated build on your build server.</span></span>

### <a name="integration-tests"></a><span data-ttu-id="5fd77-128">통합 테스트</span><span class="sxs-lookup"><span data-stu-id="5fd77-128">Integration Tests</span></span>

<span data-ttu-id="5fd77-129">데이터베이스와 파일 시스템 등의 인프라와 상호 작용 하 여 코드를 캡슐화 하는 아니지만 하면는 해당 코드의 일부 및 여전히 테스트 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-129">Although it's a good idea to encapsulate your code that interacts with infrastructure like databases and file systems, you will still have some of that code, and you will probably want to test it.</span></span> <span data-ttu-id="5fd77-130">또한 응용 프로그램의 종속성은 완벽 하 게 해결 하는 경우 예상 대로 코드의 계층 상호 작용 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-130">Additionally, you should verify that your code's layers interact as you expect when your application's dependencies are fully resolved.</span></span> <span data-ttu-id="5fd77-131">통합 테스트의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-131">This is the responsibility of integration tests.</span></span> <span data-ttu-id="5fd77-132">통합 테스트는 종종 외부 종속성 및 인프라에 따라 달라 지므로 느리고 보다 단위 테스트를 설정 하는 것이 어려울 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-132">Integration tests tend to be slower and more difficult to set up than unit tests, because they often depend on external dependencies and infrastructure.</span></span> <span data-ttu-id="5fd77-133">따라서 통합 테스트에서 단위 테스트를 사용 하 여 테스트 될 수 있는 작업을 테스트 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-133">Thus, you should avoid testing things that could be tests with unit tests in integration tests.</span></span> <span data-ttu-id="5fd77-134">단위 테스트와 함께 지정된 된 시나리오를 테스트 하려면 하는 경우 단위 테스트와 함께 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-134">If you can test a given scenario with a unit test, you should test it with a unit test.</span></span> <span data-ttu-id="5fd77-135">수 없는 다음 통합 테스트를 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5fd77-135">If you can't, then consider using an integration test.</span></span>

<span data-ttu-id="5fd77-136">통합 테스트는 더 복잡 한 설치 및 단위 테스트 보다 해체 프로시저 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-136">Integration tests will often have more complex setup and teardown procedures than unit tests.</span></span> <span data-ttu-id="5fd77-137">예를 들어 실제 데이터베이스에 대해 이동 하는 통합 테스트를 각 테스트 실행 하기 전에 알려진된 상태로 데이터베이스를 반환 하는 방법이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-137">For example, an integration test that goes against an actual database will need a way to return the database to a known state before each test run.</span></span> <span data-ttu-id="5fd77-138">새 테스트 추가 되 고 프로덕션 데이터베이스 스키마 진화 함에 따라 이러한 테스트 스크립트의 크기와 복잡성 증가 경향이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-138">As new tests are added and the production database schema evolves, these test scripts will tend to grow in size and complexity.</span></span> <span data-ttu-id="5fd77-139">많은 큰 시스템에서 공유 소스 제어에 대 한 변경 내용 체크 인 하기 전에 개발자 워크스테이션에 통합 테스트의 전체 제품군을 실행 하기에 적합 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-139">In many large systems, it is impractical to run full suites of integration tests on developer workstations before checking in changes to shared source control.</span></span> <span data-ttu-id="5fd77-140">이러한 경우에는 빌드 서버에서 통합 테스트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-140">In these cases, integration tests may be run on a build server.</span></span>

<span data-ttu-id="5fd77-141">LocalFileImageService 구현 클래스 인출 및 id를 지정 하는 특정 폴더에서 이미지 파일의 바이트를 반환 하기 위한 논리를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-141">The LocalFileImageService implementation class implements the logic for fetching and returning the bytes of an image file from a particular folder given an id:</span></span>

```cs
public class LocalFileImageService : IImageService
{
    private readonly IHostingEnvironment _env;
    public LocalFileImageService(IHostingEnvironment env)
    {
        _env = env;
    }
    public byte[] GetImageBytesById(int id)
    {
        try
        {
            var contentRoot = _env.ContentRootPath + "//Pics";
            var path = Path.Combine(contentRoot, id + ".png");
            return File.ReadAllBytes(path);
```

### <a name="functional-tests"></a><span data-ttu-id="5fd77-142">기능 테스트</span><span class="sxs-lookup"><span data-stu-id="5fd77-142">Functional Tests</span></span>

<span data-ttu-id="5fd77-143">통합 테스트 시스템의 일부 구성 요소가 올바르게 작동 하는지 함께 확인 하는 개발자의 관점에서 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-143">Integration tests are written from the perspective of the developer, to verify that some components of the system work correctly together.</span></span> <span data-ttu-id="5fd77-144">기능 테스트는 사용자의 관점에서 작성 하 고 해당 요구 사항에 따라 시스템의 정확성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-144">Functional tests are written from the perspective of the user, and verify the correctness of the system based on its requirements.</span></span> <span data-ttu-id="5fd77-145">다음 발췌 구문에서는 단위 테스트에 비해 기능 테스트에 대해 생각 하는 방법에 대 한 유용한 예를 들어를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-145">The following excerpt offers a useful analogy for how to think about functional tests, compared to unit tests:</span></span>

> <span data-ttu-id="5fd77-146">"개발 시스템을 여러 번 건물 집에 비유할 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-146">"Many times the development of a system is likened to the building of a house.</span></span> <span data-ttu-id="5fd77-147">이 비유 매우 올바르지 않으면 하는 동안 그에 따라 확장할 수 단위 테스트 및 테스트 기능 간의 차이점을 이해할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-147">While this analogy isn't quite correct, we can extend it for the purposes of understanding the difference between unit and functional tests.</span></span> <span data-ttu-id="5fd77-148">단위 테스트는 주택 생성 사이트를 방문 하는 빌딩 검사기과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-148">Unit testing is analogous to a building inspector visiting a house's construction site.</span></span> <span data-ttu-id="5fd77-149">그는 집 기반 프레이밍, 전자, 배관, 및 등의 다양 한 내부 시스템 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-149">He is focused on the various internal systems of the house, the foundation, framing, electrical, plumbing, and so on.</span></span> <span data-ttu-id="5fd77-150">그 집의 부분 제대로 작동 되며을 안전 하 게 빌드 코드, 즉 충족 (테스트)를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-150">He ensures (tests) that the parts of the house will work correctly and safely, that is, meet the building code.</span></span> <span data-ttu-id="5fd77-151">이 시나리오에서 기능 테스트는이 동일한 구성 사이트를 방문 주택 소유자와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-151">Functional tests in this scenario are analogous to the homeowner visiting this same construction site.</span></span> <span data-ttu-id="5fd77-152">그 가정 내부 시스템은 적절 하 게 동작, 구성 관리자에서 자신의 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-152">He assumes that the internal systems will behave appropriately, that the building inspector is performing his task.</span></span> <span data-ttu-id="5fd77-153">주택 소유자는 어떤는 것 처럼이 집에서에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-153">The homeowner is focused on what it will be like to live in this house.</span></span> <span data-ttu-id="5fd77-154">그 집을 표시 되는 모양을를 우려, 능숙 크기 대화방에서는 다양 한, 집 가족의 요구에 맞게지 않습니다, 그리고에 적합 한 지점이 아침 sun를 catch 하는 창.</span><span class="sxs-lookup"><span data-stu-id="5fd77-154">He is concerned with how the house looks, are the various rooms a comfortable size, does the house fit the family's needs, are the windows in a good spot to catch the morning sun.</span></span> <span data-ttu-id="5fd77-155">주택 소유자는 실행 하는 기능 테스트 집 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-155">The homeowner is performing functional tests on the house.</span></span> <span data-ttu-id="5fd77-156">그 사용자의 관점을가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-156">He has the user's perspective.</span></span> <span data-ttu-id="5fd77-157">건물 검사기는 집에서 단위 테스트를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-157">The building inspector is performing unit tests on the house.</span></span> <span data-ttu-id="5fd77-158">그에 작성기의 관점입니다. "</span><span class="sxs-lookup"><span data-stu-id="5fd77-158">He has the builder's perspective."</span></span>

<span data-ttu-id="5fd77-159">원본: [단위 기능 테스트 및 테스트](http://www.softwaretestingtricks.com/2007/01/unit-testing-versus-functional-tests.html)</span><span class="sxs-lookup"><span data-stu-id="5fd77-159">Source: [Unit Testing versus Functional Tests](http://www.softwaretestingtricks.com/2007/01/unit-testing-versus-functional-tests.html)</span></span>

<span data-ttu-id="5fd77-160">저는 라는 것을 선호 "개발자 두 가지 방법으로 실패: 잘못 된 작업을 만들었습니다 또는 잘못 된 내용을 빌드합니다."</span><span class="sxs-lookup"><span data-stu-id="5fd77-160">I'm fond of saying "As developers, we fail in two ways: we build the thing wrong, or we build the wrong thing."</span></span> <span data-ttu-id="5fd77-161">단위 테스트 항목 오른쪽을 작성 하는 확인 기능 테스트 올바른 작업을 작성 하는 것을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-161">Unit tests ensure you are building the thing right; functional tests ensure you are building the right thing.</span></span>

<span data-ttu-id="5fd77-162">기능 테스트 시스템 수준에서 작동 하므로 어느 정도의 UI 자동화 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-162">Since functional tests operate at the system level, they may require some degree of UI automation.</span></span> <span data-ttu-id="5fd77-163">일반적으로 통합 테스트와 같은 일부 종류의 테스트 인프라도 함께 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-163">Like integration tests, they usually work with some kind of test infrastructure as well.</span></span> <span data-ttu-id="5fd77-164">따라서 느리고 단위 및 통합 테스트 보다 더욱 불안정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-164">This makes them slower and more brittle than unit and integration tests.</span></span> <span data-ttu-id="5fd77-165">만 있어야 사용자가 예상 대로 작동 하는 시스템 확신 하는 데 필요한 만큼의 기능 테스트.</span><span class="sxs-lookup"><span data-stu-id="5fd77-165">You should have only as many functional tests as you need to be confident the system is behaving as users expect.</span></span>

### <a name="testing-pyramid"></a><span data-ttu-id="5fd77-166">피라미드형 테스트</span><span class="sxs-lookup"><span data-stu-id="5fd77-166">Testing Pyramid</span></span>

<span data-ttu-id="5fd77-167">그림 9-1에는 예가 나와 테스트 피라미드에 대 한 Martin Fowler 썼습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-167">Martin Fowler wrote about the testing pyramid, an example of which is shown in Figure 9-1.</span></span>

![](./media/image9-1.png)

<span data-ttu-id="5fd77-168">그림 9-1이 피라미드를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-168">Figure 9-1 Testing Pyramid</span></span>

<span data-ttu-id="5fd77-169">피라미드형 및 해당 상대 크기의 다른 계층에 다른 종류를의 테스트 및 개수를 작성 해야 응용 프로그램에 대 한 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-169">The different layers of the pyramid, and their relative sizes, represent different kinds of tests and how many you should write for your application.</span></span> <span data-ttu-id="5fd77-170">볼 수 있듯이 기능 테스트는 더 작은 계층으로 통합 테스트의 더 작은 계층에서 지원 되는 단위 테스트의 큰 자료가 있어야 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-170">As you can see, the recommendation is to have a large base of unit tests, supported by a smaller layer of integration tests, with an even smaller layer of functional tests.</span></span> <span data-ttu-id="5fd77-171">각 계층 이상적 있어야 테스트의 하위 계층에 적절 하 게 수행할 수 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-171">Each layer should ideally only have tests in it that cannot be performed adequately at a lower layer.</span></span> <span data-ttu-id="5fd77-172">특정 시나리오에 필요한 테스트의 종류를 결정 하려고 시도할 때 테스트 피라미드형을 염두에 두십시오.</span><span class="sxs-lookup"><span data-stu-id="5fd77-172">Keep the testing pyramid in mind when you are trying to decide which kind of test you need for a particular scenario.</span></span>

### <a name="what-to-test"></a><span data-ttu-id="5fd77-173">테스트 항목</span><span class="sxs-lookup"><span data-stu-id="5fd77-173">What to Test</span></span>

<span data-ttu-id="5fd77-174">자동화 된 테스트를 작성 한 경험이 있는 개발자를 위한 일반적인 문제에 나오는 사용 하 여 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-174">A common problem for developers who are inexperienced with writing automated tests is coming up with what to test.</span></span> <span data-ttu-id="5fd77-175">좋은 출발점 조건부 논리를 테스트 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-175">A good starting point is to test conditional logic.</span></span> <span data-ttu-id="5fd77-176">조건문에 따라 변경 하는 동작을 사용 하 여 메서드 있는 모든 곳 (if else 전환, 등)는 적어도 두 가지 특정 조건에 대 한 올바른 동작을 확인 하는 테스트를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-176">Anywhere you have a method with behavior that changes based on a conditional statement (if-else, switch, etc.), you should be able to come up at least a couple of tests that confirm the correct behavior for certain conditions.</span></span> <span data-ttu-id="5fd77-177">코드 오류 조건에 경우 쓰는 데 오류), (없이 코드를 통해 "정상 경로"에 대 한 테스트를 하나 이상 및 "sad 경로"에 대 한 테스트를 하나 이상 (오류나 불규칙 결과) 응용 프로그램의 오류에 관계 없이 예상 대로 동작을 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-177">If your code has error conditions, it's good to write at least one test for the "happy path" through the code (with no errors), and at least one test for the "sad path" (with errors or atypical results) to confirm your application behaves as expected in the face of errors.</span></span> <span data-ttu-id="5fd77-178">마지막으로, 코드 검사 같은 메트릭이에 집중 하는 것이 아니라 작업이 실패할 수 있는 테스트에 집중 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-178">Finally, try to focus on testing things that can fail, rather than focusing on metrics like code coverage.</span></span> <span data-ttu-id="5fd77-179">더 많은 코드 검사는 일반적으로 보다 적습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-179">More code coverage is better than less, generally.</span></span> <span data-ttu-id="5fd77-180">그러나 매우 복잡 하 고 비즈니스에 중요 한 방법의 몇 가지 더 많은 테스트를 작성 하는 일반적으로 테스트 코드 검사 메트릭을 향상 하기 바로 자동 속성에 대 한 테스트를 작성 하는 보다 잘 활용할 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-180">However, writing a few more tests of a very complex and business-critical method is usually a better use of time than writing tests for auto-properties just to improve test code coverage metrics.</span></span>

## <a name="organizing-test-projects"></a><span data-ttu-id="5fd77-181">테스트 프로젝트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-181">Organizing Test Projects</span></span>

<span data-ttu-id="5fd77-182">하지만 사용자에 대 한 가장 잘 작동 테스트 프로젝트를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-182">Test projects can be organized however works best for you.</span></span> <span data-ttu-id="5fd77-183">테스트 유형 (단위 테스트, 통합 테스트) 및로 (프로젝트, 네임 스페이스)에서 테스트 중인 기능으로 구분 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-183">It's a good idea to separate tests by type (unit test, integration test) and by what they are testing (by project, by namespace).</span></span> <span data-ttu-id="5fd77-184">이러한 분리는 단일 테스트 프로젝트 또는 여러 테스트 프로젝트 내에서 폴더 구성 되는지 여부를 디자인 결정입니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-184">Whether this separation consists of folders within a single test project, or multiple test projects, is a design decision.</span></span> <span data-ttu-id="5fd77-185">한 프로젝트는 가장 간단한 하지만 많은 테스트의 경우 또는 여러 테스트 집합에 더 쉽게 실행 하기 위해 대규모 프로젝트에 대 한 여러 다른 테스트 프로젝트 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-185">One project is simplest, but for large projects with many tests, or in order to more easily run different sets of tests, you might want to have several different test projects.</span></span> <span data-ttu-id="5fd77-186">많은 팀 응용 프로그램의 여러 프로젝트와 함께 테스트 프로젝트의 많은 여전히 분리 하 여 이러한 각 프로젝트에는 어떤 종류의 테스트에 따라 하는 경우에 특히 될 수 있습니다, 테스트 중인 프로젝트를 기반으로 테스트 프로젝트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-186">Many teams organize test projects based on the project they are testing, which for applications with more than a few projects can result in a large number of test projects, especially if you still break these down according to what kind of tests are in each project.</span></span> <span data-ttu-id="5fd77-187">테스트 중인 프로젝트 (및 클래스)을 나타내기 위해 테스트 프로젝트 내에 폴더와 응용 프로그램 별로 테스트 당 프로젝트가 두 개 있는 하 손상 방법이입니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-187">A compromise approach is to have one project per kind of test, per application, with folders inside the test projects to indicate the project (and class) being tested.</span></span>

<span data-ttu-id="5fd77-188">일반적인 방법은 'src' 폴더에서 응용 프로그램 프로젝트 및 병렬 '테스트' 폴더에서 응용 프로그램의 테스트 프로젝트를 구성 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-188">A common approach is to organize the application projects under a ‘src' folder, and the application's test projects under a parallel ‘tests' folder.</span></span> <span data-ttu-id="5fd77-189">이 조직 유용를 찾을 경우 Visual Studio에서 일치 하는 솔루션 폴더를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-189">You can create matching solution folders in Visual Studio, if you find this organization useful.</span></span>

![](./media/image9-2.png)

<span data-ttu-id="5fd77-190">솔루션에 테스트 조직 그림 9-2</span><span class="sxs-lookup"><span data-stu-id="5fd77-190">Figure 9-2 Test organization in your solution</span></span>

<span data-ttu-id="5fd77-191">원하는 어떤 테스트 프레임 워크를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-191">You can use whichever test framework you prefer.</span></span> <span data-ttu-id="5fd77-192">XUnit 프레임 워크는 제대로 작동 하 고는 모든 ASP.NET 코어 및 EF 코어 테스트로 작성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-192">The xUnit framework works well and is what all of the ASP.NET Core and EF Core tests are written in.</span></span> <span data-ttu-id="5fd77-193">그림 9-3에서 나 CLI dotnet 새 xunit를 사용 하 여 표시 된 템플릿을 사용 하 여 Visual Studio에서 xUnit 테스트 프로젝트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-193">You can add an xUnit test project in Visual Studio using the template shown in Figure 9-3, or from the CLI using dotnet new xunit.</span></span>

![](./media/image9-3.png)

<span data-ttu-id="5fd77-194">그림 9-3 Visual Studio에서 테스트 프로젝트는 xUnit 추가</span><span class="sxs-lookup"><span data-stu-id="5fd77-194">Figure 9-3 Add an xUnit Test Project in Visual Studio</span></span>

### <a name="test-naming"></a><span data-ttu-id="5fd77-195">테스트 이름 지정</span><span class="sxs-lookup"><span data-stu-id="5fd77-195">Test Naming</span></span>

<span data-ttu-id="5fd77-196">각 테스트에서 수행 하는 작업을 나타내는 이름으로 테스트를 일관성 있게에서 필드 이름을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-196">You should name your tests in a consistent fashion, with names that indicate what each test does.</span></span> <span data-ttu-id="5fd77-197">유용한 작업을 완료 했습니다 한 가지 방법은 클래스 및 테스트 하는 방법에 따라 테스트 클래스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-197">One approach I've had great success with is to name test classes according to the class and method they are testing.</span></span> <span data-ttu-id="5fd77-198">이 인해 많은 소형 테스트 클래스 되지만 매우 어떤 각 테스트에 대 한 책임이 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-198">This results in many small test classes, but it makes it extremely clear what each test is responsible for.</span></span> <span data-ttu-id="5fd77-199">클래스 및 메서드를 테스트를 식별 하도록 설정 하는 테스트 클래스 이름으로 테스트 메서드 이름은 테스트 중인 동작을 지정 하 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-199">With the test class name set up to identify the class and method to be tested, the test method name can be used to specify the behavior being tested.</span></span> <span data-ttu-id="5fd77-200">여기에 예상 되는 동작 및 입력 또는이 동작을 생성 해야 하는 가정을 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-200">This should include the expected behavior and any inputs or assumptions that should yield this behavior.</span></span> <span data-ttu-id="5fd77-201">일부 예제 테스트 이름:</span><span class="sxs-lookup"><span data-stu-id="5fd77-201">Some example test names:</span></span>

-   <span data-ttu-id="5fd77-202">CatalogControllerGetImage.CallsImageServiceWithId</span><span class="sxs-lookup"><span data-stu-id="5fd77-202">CatalogControllerGetImage.CallsImageServiceWithId</span></span>

-   <span data-ttu-id="5fd77-203">CatalogControllerGetImage.LogsWarningGivenImageMissingException</span><span class="sxs-lookup"><span data-stu-id="5fd77-203">CatalogControllerGetImage.LogsWarningGivenImageMissingException</span></span>

-   <span data-ttu-id="5fd77-204">CatalogControllerGetImage.ReturnsFileResultWithBytesGivenSuccess</span><span class="sxs-lookup"><span data-stu-id="5fd77-204">CatalogControllerGetImage.ReturnsFileResultWithBytesGivenSuccess</span></span>

-   <span data-ttu-id="5fd77-205">CatalogControllerGetImage.ReturnsNotFoundResultGivenImageMissingException</span><span class="sxs-lookup"><span data-stu-id="5fd77-205">CatalogControllerGetImage.ReturnsNotFoundResultGivenImageMissingException</span></span>

<span data-ttu-id="5fd77-206">각 테스트 클래스 이름 "은"를 종료 하 고는 시제를 약간 수정 하는이 방법의 변형:</span><span class="sxs-lookup"><span data-stu-id="5fd77-206">A variation of this approach ends each test class name with "Should" and modifies the tense slightly:</span></span>

-   <span data-ttu-id="5fd77-207">CatalogControllerGetImage**Should**.**Call**ImageServiceWithId</span><span class="sxs-lookup"><span data-stu-id="5fd77-207">CatalogControllerGetImage**Should**.**Call**ImageServiceWithId</span></span>

-   <span data-ttu-id="5fd77-208">CatalogControllerGetImage**Should**.**Log**WarningGivenImageMissingException</span><span class="sxs-lookup"><span data-stu-id="5fd77-208">CatalogControllerGetImage**Should**.**Log**WarningGivenImageMissingException</span></span>

<span data-ttu-id="5fd77-209">일부 팀 더 명확 하 게, 두 번째 명명 방식의 찾을 하지만 약간 더 자세한 정보.</span><span class="sxs-lookup"><span data-stu-id="5fd77-209">Some teams find the second naming approach clearer, though slightly more verbose.</span></span> <span data-ttu-id="5fd77-210">어떤 경우 든, 어떤 경우 실패 한 이름이 확실는 하나 이상의 테스트가 실패 하는 테스트 동작에 대 한 정보를 제공 하는 명명 규칙을 사용 하도록 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-210">In any case, try to use a naming convention that provides insight into test behavior, so that when one or more tests fail, it's obvious from their names what cases have failed.</span></span> <span data-ttu-id="5fd77-211">지정 하지 있습니다 테스트 말에 왠지, ControllerTests.Test1, 등으로 테스트 결과에 표시 되 면 값이 없는 제공.</span><span class="sxs-lookup"><span data-stu-id="5fd77-211">Avoid naming you tests vaguely, such as ControllerTests.Test1, as these offer no value when you see them in test results.</span></span>

<span data-ttu-id="5fd77-212">위의 하는 다 수의 작은 테스트 클래스를 생성 합니다. 같은 명명 규칙을 지키는 인지 폴더 및 네임 스페이스를 사용 하 여 테스트를 추가로 구성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-212">If you follow a naming convention like the one above that produces many small test classes, it's a good idea to further organize your tests using folders and namespaces.</span></span> <span data-ttu-id="5fd77-213">그림 9-4를 테스트 하 여 여러 테스트 프로젝트 내에 폴더를 구성 하는 한 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-213">Figure 9-4 shows one approach to organizing tests by folder within several test projects.</span></span>

![](./media/image9-4.png)

<span data-ttu-id="5fd77-214">**그림 9-4입니다.**</span><span class="sxs-lookup"><span data-stu-id="5fd77-214">**Figure 9-4.**</span></span> <span data-ttu-id="5fd77-215">테스트 중인 클래스에 기반 하는 폴더에서 테스트 클래스를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-215">Organizing test classes by folder based on class being tested.</span></span>

<span data-ttu-id="5fd77-216">물론, 특정 응용 프로그램 클래스에는 테스트 중인 많은 메서드 (및 따라서 여러 테스트 클래스) 하는 경우 이러한 응용 프로그램 클래스에 해당 하는 폴더에 배치 하는 의미를 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-216">Of course, if a particular application class has many methods being tested (and thus many test classes), it may make sense to place these in a folder corresponding to the application class.</span></span> <span data-ttu-id="5fd77-217">이 구조는 폴더를 다른 위치에 파일을 구성할 수 차이가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-217">This organization is no different than how you might organize files into folders elsewhere.</span></span> <span data-ttu-id="5fd77-218">최대 3 개까지 또는 다른 많은 파일이 포함 된 폴더의 파일 관련 4 개, 경우에 자신의 하위 폴더로 이동 하는 것이 도움이 대개 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-218">If you have more than three or four related files in a folder containing many other files, it's often helpful to move them into their own subfolder.</span></span>

## <a name="unit-testing-aspnet-core-apps"></a><span data-ttu-id="5fd77-219">단위 테스트 ASP.NET Core 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="5fd77-219">Unit Testing ASP.NET Core Apps</span></span>

<span data-ttu-id="5fd77-220">잘 설계 된 ASP.NET Core 응용 프로그램에서 대부분의 복잡성 및 비즈니스 논리, 비즈니스 엔터티 및 다양 한 서비스에 캡슐화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-220">In a well-designed ASP.NET Core application, most of the complexity and business logic will be encapsulated in business entities and a variety of services.</span></span> <span data-ttu-id="5fd77-221">ASP.NET Core MVC 응용 프로그램 자체, 컨트롤러, 필터, viewmodel, 및 보기와 거의 단위 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-221">The ASP.NET Core MVC app itself, with its controllers, filters, viewmodels, and views, should require very few unit tests.</span></span> <span data-ttu-id="5fd77-222">대부분의 기능에 지정된 된 동작의 작업 메서드 자체 외부에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-222">Much of the functionality of a given action lies outside the action method itself.</span></span> <span data-ttu-id="5fd77-223">라우팅이 올바르게 작동 하는지 여부를 테스트 또는 전역 오류 처리 단위 테스트와 함께 효과적으로 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-223">Testing whether routing works correctly, or global error handling, cannot be done effectively with a unit test.</span></span> <span data-ttu-id="5fd77-224">마찬가지로, 모든 모델 유효성 검사 및 인증을 포함 하 여 필터 및 권한 부여 필터 단위 테스트를 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-224">Likewise, any filters, including model validation and authentication and authorization filters, cannot be unit tested.</span></span> <span data-ttu-id="5fd77-225">대부분의 작업 메서드는 동작의 이러한 소스는 없이 다르거나 일반적으로 작은 자신의 작업을 독립적으로 컨트롤러를 사용 하 여 테스트할 수 있는 서비스의 대부분을 위임 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-225">Without these sources of behavior, most action methods should be trivially small, delegating the bulk of their work to services that can be tested independent of the controller that uses them.</span></span>

<span data-ttu-id="5fd77-226">경우에 따라 리팩터링 코드에 단위 테스트에 정렬 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-226">Sometimes you'll need to refactor your code in order to unit test it.</span></span> <span data-ttu-id="5fd77-227">자주이 추상화를 식별 하며 종속성 주입을 사용 하 여 추상화를 테스트 하려는 코드에 액세스 하는 대신 인프라에 대 한 직접 코딩 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-227">Frequently this involves identifying abstractions and using dependency injection to access the abstraction in the code you'd like to test, rather than coding directly against infrastructure.</span></span> <span data-ttu-id="5fd77-228">예를 들어 이미지를 표시 하기 위한이 간단한 작업 메서드:</span><span class="sxs-lookup"><span data-stu-id="5fd77-228">For example, consider this simple action method for displaying images:</span></span>

```cs
[HttpGet("[controller]/pic/{id}")]
public IActionResult GetImage(int id)
{
    var contentRoot = _env.ContentRootPath + "//Pics";
    var path = Path.Combine(contentRoot, id + ".png");
    Byte[] b = System.IO.File.ReadAllBytes(path);
    return File(b, "image/png");
}
```

<span data-ttu-id="5fd77-229">단위 테스트이 메서드는 사용 하 여 파일 시스템에서 읽을 수 있는 System.IO.File에 종속 되기 직접 어려운 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-229">Unit testing this method is made difficult by its direct dependency on System.IO.File, which it uses to read from the file system.</span></span> <span data-ttu-id="5fd77-230">예상 대로 작동 하지만 실제 파일에 게 그렇게는 통합 테스트를 확인 하도록이 동작을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-230">You can test this behavior to ensure it works as expected, but doing so with real files is an integration test.</span></span> <span data-ttu-id="5fd77-231">이 메서드의 경로 테스트할 수 없습니다-이 기능을 테스트 곧 수행 하는 방법을 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-231">It's worth noting you can't test this method's route – you'll see how to do this with a functional test shortly.</span></span>

<span data-ttu-id="5fd77-232">에 직접 단위 테스트 파일 시스템 동작이 수 없는 경우 경로 테스트할 수 없습니다 이란 있는 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="5fd77-232">If you can't unit test the file system behavior directly, and you can't test the route, what is there to test?</span></span> <span data-ttu-id="5fd77-233">단위 테스트를 가능 하 게 하려면 리팩터링 후 몇 가지 테스트 사례 및 오류 처리 등의 누락 된 동작을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-233">Well, after refactoring to make unit testing possible, you may discover some test cases and missing behavior, such as error handling.</span></span> <span data-ttu-id="5fd77-234">메서드가 수행 하는 파일을 찾을 수 없을 때</span><span class="sxs-lookup"><span data-stu-id="5fd77-234">What does the method do when a file isn't found?</span></span> <span data-ttu-id="5fd77-235">수행 해야 하는 것?</span><span class="sxs-lookup"><span data-stu-id="5fd77-235">What should it do?</span></span> <span data-ttu-id="5fd77-236">이 예제에서는 여 리팩터링된 메서드는 다음과 같이 보입니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-236">In this example, the refactored method looks like this:</span></span>

```cs
[HttpGet("[controller]/pic/{id}")\]
public IActionResult GetImage(int id)
{
    byte[] imageBytes;
    try
    {
        imageBytes = _imageService.GetImageBytesById(id);
    }
    catch (CatalogImageMissingException ex)
    {
        _logger.LogWarning($"No image found for id: {id}");
        return NotFound();
    }
    return File(imageBytes, "image/png");
}
```

<span data-ttu-id="5fd77-237">\_로 거 및 \_imageService은 둘 다 종속성으로 삽입 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-237">The \_logger and \_imageService are both injected as dependencies.</span></span> <span data-ttu-id="5fd77-238">에 전달 된 동작 메서드에 전달 되는 동일한 id를 테스트할 수 이제는 \_imageService, 결과 바이트는 FileResult의 일부로 반환 되는 및입니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-238">Now you can test that the same id that is passed to the action method is passed to the \_imageService, and that the resulting bytes are returned as part of the FileResult.</span></span> <span data-ttu-id="5fd77-239">또한 및 테스트할 수 있습니다 예상 대로 오류 로깅을 수행 중인을 이미지가 누락 되었거나, 경우 NotFound 결과가 반환 됩니다 이것은 중요 한 응용 프로그램 동작 (즉,: 방금 일시적인 코드 문제 진단에 추가 하는 개발자) 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-239">You can also test that error logging is happening as expected, and that a NotFound result is returned if the image is missing, assuming this is important application behavior (that is, not just temporary code the developer added to diagnose an issue).</span></span> <span data-ttu-id="5fd77-240">실제 파일 논리는 별도 구현 서비스 옮겼습니다 및 누락 된 파일의 경우에 대 한 응용 프로그램별 예외를 반환 하도록가 확장 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-240">The actual file logic has moved into a separate implementation service, and has been augmented to return an application-specific exception for the case of a missing file.</span></span> <span data-ttu-id="5fd77-241">있습니다 수이 구현 독립적으로 테스트할 통합 테스트를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-241">You can test this implementation independently, using an integration test.</span></span>

## <a name="integration-testing-aspnet-core-apps"></a><span data-ttu-id="5fd77-242">ASP.NET Core 앱을 테스트 하는 통합</span><span class="sxs-lookup"><span data-stu-id="5fd77-242">Integration Testing ASP.NET Core Apps</span></span>

```cs
    }
        catch (FileNotFoundException ex)
        {
            throw new CatalogImageMissingException(ex);
        }
    }
}
```

<span data-ttu-id="5fd77-243">이 서비스는 별도 서비스로 리팩터링 되기 전의 코드 CatalogController와 마찬가지로 IHostingEnvironment를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-243">This service uses the IHostingEnvironment, just as the CatalogController code did before it was refactored into a separate service.</span></span> <span data-ttu-id="5fd77-244">IHostingEnvironment를 사용 하는 컨트롤러의 유일한 코드가 이것이 이후 해당 종속성 CatalogController의 생성자에서 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-244">Since this was the only code in the controller that used IHostingEnvironment, that dependency was removed from CatalogController's constructor.</span></span>

<span data-ttu-id="5fd77-245">이 서비스가 올바르게 작동을 테스트 하려면 테스트 알려진된 이미지 파일을 만들고 서비스는 특정 입력이 제공 하는 것을 반환 하는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-245">To test that this service works correctly, you need to create a known test image file and verify that the service returns it given a specific input.</span></span> <span data-ttu-id="5fd77-246">실제로에 (이 경우 파일 시스템에서 읽기) 테스트 하려는 동작에 모의 개체를 사용 하지 않는 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-246">You should take care not to use mock objects on the behavior you actually want to test (in this case, reading from the file system).</span></span> <span data-ttu-id="5fd77-247">그러나 모의 개체 여전히 통합 테스트를 설정 하려면 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-247">However, mock objects may still be useful to set up integration tests.</span></span> <span data-ttu-id="5fd77-248">이 경우 테스트 이미지에 대 한 사용 하려는 폴더를 가리키도록 해당 ContentRootPath IHostingEnvironment 모의 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-248">In this case, you can mock IHostingEnvironment so that its ContentRootPath points to the folder you're going to use for your test image.</span></span> <span data-ttu-id="5fd77-249">전체 작업 통합 테스트 클래스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-249">The complete working integration test class is shown here:</span></span>

```cs
public class LocalFileImageServiceGetImageBytesById
{
    private byte[] _testBytes = new byte[] { 0x01, 0x02, 0x03 };
    private readonly Mock<IHostingEnvironment> _mockEnvironment = new Mock<IHostingEnvironment>();
    private int _testImageId = 123;
    private string _testFileName = "123.png";
    public LocalFileImageServiceGetImageBytesById()
    {
        // create folder if necessary
        Directory.CreateDirectory(Path.Combine(GetFileDirectory(), "Pics"));
        string filePath = GetFilePath(_testFileName);
        System.IO.File.WriteAllBytes(filePath, _testBytes);
        _mockEnvironment.SetupGet<string>(m => m.ContentRootPath).Returns(GetFileDirectory());
    }
    private string GetFilePath(string fileName)
    {
        return Path.Combine(GetFileDirectory(), "Pics", fileName);
        }
            private string GetFileDirectory()
        {
            var location = System.Reflection.Assembly.GetEntryAssembly().Location;
            return Path.GetDirectoryName(location);
        }

        [Fact]
        public void ReturnsFileContentResultGivenValidId()
        {
            var fileService = new LocalFileImageService(_mockEnvironment.Object);
            var result = fileService.GetImageBytesById(_testImageId);
            Assert.Equal(_testBytes, result);
        }
    }
```

> [!NOTE]
> <span data-ttu-id="5fd77-250">테스트 자체는 매우 간단한 코드의 대부분 해야 하는 시스템을 구성 하 고이 경우는 실제 파일에 디스크에서 읽어야 하는 테스트 인프라를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-250">that the test itself is very simple – the bulk of the code is necessary to configure the system and create the testing infrastructure (in this case, an actual file to be read from disk).</span></span> <span data-ttu-id="5fd77-251">단위 테스트 보다 더 복잡 한 설치 작업이 필요할 수 있는 통합 테스트에 대 한 일반입니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-251">This is typical for integration tests, which often require more complex setup work than unit tests.</span></span>

## <a name="functional-testing-aspnet-core-apps"></a><span data-ttu-id="5fd77-252">기능 테스트 ASP.NET Core 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="5fd77-252">Functional Testing ASP.NET Core Apps</span></span>

<span data-ttu-id="5fd77-253">ASP.NET Core 응용 프로그램에 대 한 TestServer 클래스를 사용 하면 기능 테스트 상당히 쉽게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-253">For ASP.NET Core applications, the TestServer class makes functional tests fairly easy to write.</span></span> <span data-ttu-id="5fd77-254">와 마찬가지로 일반적으로 응용 프로그램에 대 한 WebHostBuilder를 사용 하 여 TestServer를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-254">You configure a TestServer using a WebHostBuilder, just as you normally do for your application.</span></span> <span data-ttu-id="5fd77-255">이 WebHostBuilder 응용 프로그램의 실제 호스트와 동일 하 게 구성 해야 하지만 더 쉬운 테스트 환경의 모든 측면을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-255">This WebHostBuilder should be configured just like your application's real host, but you can modify any aspects of it that make testing easier.</span></span> <span data-ttu-id="5fd77-256">대부분의 경우 캡슐화 할 수 있습니다 (아마도 기본 클래스)에서 다시 사용할 수 있는 메서드 하므로 많은 테스트 사례에 대 한 동일한 TestServer를 재사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-256">Most of the time, you'll reuse the same TestServer for many test cases, so you can encapsulate it in a reusable method (perhaps in a base class):</span></span>

```cs
public abstract class BaseWebTest
{
    protected readonly HttpClient _client;
    protected string _contentRoot;

    public BaseWebTest()
    {
        _client = GetClient();
    }
    
    protected HttpClient GetClient()
    {
        var startupAssembly = typeof(Startup).GetTypeInfo().Assembly;
        _contentRoot = GetProjectPath("src", startupAssembly);
        var builder = new WebHostBuilder()
        .UseContentRoot(_contentRoot)
        .UseStartup&lt;Startup&gt;();
        var server = new TestServer(builder);
        var client = server.CreateClient();
        return client;
    }
}
```

<span data-ttu-id="5fd77-257">GetProjectPath 메서드는 단순히 웹 프로젝트 (샘플 솔루션 다운로드)에 실제 경로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-257">The GetProjectPath method simply returns the physical path to the web project (download sample solution).</span></span> <span data-ttu-id="5fd77-258">WebHostBuilder이 경우 단순히 지정 위치에서 웹 응용 프로그램에 대 한 콘텐츠 루트 이며, 실제 웹 응용 프로그램에서 동일한 시작 클래스를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-258">The WebHostBuilder in this case simply specifies where the content root for the web application is, and references the same Startup class the real web application uses.</span></span> <span data-ttu-id="5fd77-259">TestServer를 사용 하 여 요청을 만드는 표준 System.Net.HttpClient 유형을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-259">To work with the TestServer, you use the standard System.Net.HttpClient type to make requests to it.</span></span> <span data-ttu-id="5fd77-260">TestServer는 TestServer에서 실행 중인 응용 프로그램에 요청을 준비 하는 미리 구성 된 클라이언트를 제공 하는 것이 도움이 CreateClient 메서드를 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-260">TestServer exposes a helpful CreateClient method that provides a pre-configured client that is ready to make requests to the application running on the TestServer.</span></span> <span data-ttu-id="5fd77-261">이 클라이언트를 사용 하 여 (보호 된 설정 \_위의 기본 테스트에 대 한 클라이언트 멤버가) ASP.NET Core 응용 프로그램에 대 한 기능 테스트를 작성할 때:</span><span class="sxs-lookup"><span data-stu-id="5fd77-261">You use this client (set to the protected \_client member on the base test above) when writing functional tests for your ASP.NET Core application:</span></span>

```cs
public class CatalogControllerGetImage : BaseWebTest
{
    [Fact]
    public async Task ReturnsFileContentResultGivenValidId()
    {
        var testFilePath = Path.Combine(_contentRoot, "pics//1.png");
        var expectedFileBytes = File.ReadAllBytes(testFilePath);
        var response = await _client.GetAsync("/catalog/pic/1");
        response.EnsureSuccessStatusCode();
        var streamResponse = await response.Content.ReadAsStreamAsync();
        byte[] byteResult;
        using (var ms = new MemoryStream())
        {
            streamResponse.CopyTo(ms);
            byteResult = ms.ToArray();
        }
        Assert.Equal(expectedFileBytes, byteResult);
    }
}
```

<span data-ttu-id="5fd77-262">모든 미들웨어, 필터, 바인더, 현재 위치에 있을 수 있는 등을 포함 하 여 전체 ASP.NET Core MVC 응용 프로그램 스택을 실행 하는이 기능을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-262">This functional test exercises the full ASP.NET Core MVC application stack, including all middleware, filters, binders, etc. that may be in place.</span></span> <span data-ttu-id="5fd77-263">인지 확인 한 경로 지정 ("/ 1/pic 카탈로그 /") 알려진된 위치에 파일에 대 한 예상된 바이트 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-263">It verifies that a given route ("/catalog/pic/1") returns the expected byte array for a file in a known location.</span></span> <span data-ttu-id="5fd77-264">실제 웹 서버를 설정 하지 않고이 작업을 수행 하 고 있으므로 대부분의 실제 웹을 사용 하 여 테스트를 위해 서버 (예: 방화벽 설정에 문제가) 발생할 수 있는 오류를 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-264">It does so without setting up a real web server, and so avoids much of the brittleness that using a real web server for testing can experience (for example, problems with firewall settings).</span></span> <span data-ttu-id="5fd77-265">TestServer에 대해 실행 되는 기능 테스트 통합 및 단위 테스트의 경우 보다 일반적으로 느린 있지만 테스트 웹 서버에 네트워크를 통해 실행 되는 테스트 보다 훨씬 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="5fd77-265">Functional tests that run against TestServer are usually slower than integration and unit tests, but are much faster than tests that would run over the network to a test web server.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="5fd77-266">[이전] [다음] (개발-프로세스-에-azure.md) (work-with-data-in-asp-net-core-apps.md)</span><span class="sxs-lookup"><span data-stu-id="5fd77-266">[Previous] (work-with-data-in-asp-net-core-apps.md) [Next] (development-process-for-azure.md)</span></span>
