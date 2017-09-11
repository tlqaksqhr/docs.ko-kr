---
title: ".NET Core의 단위 테스트"
description: "유닛 테스트가 아주 쉬워졌습니다. .NET Core 프로젝트에서 유닛 테스트를 사용하는 방법을 참조하세요."
keywords: .NET, .NET Core
author: ardalis
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 815ac74c-4bd9-4a94-a87c-78288b27c0e2
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 22647a9ad7723bbfcf0d54530b3c0538198e7c35
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---

# <a name="unit-testing-in-net-core"></a><span data-ttu-id="52af4-105">.NET Core의 단위 테스트</span><span class="sxs-lookup"><span data-stu-id="52af4-105">Unit Testing in .NET Core</span></span>

<span data-ttu-id="52af4-106">.NET Core는 테스트 가능성을 염두에 두고 설계되어 이전보다 더 쉽게 응용 프로그램에 대한 단위 테스트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52af4-106">.NET Core has been designed with testability in mind, so that creating unit tests for your applications is easier than ever before.</span></span> <span data-ttu-id="52af4-107">이 문서에서는 단위 테스트 및 이 테스트가 다른 종류의 테스트와 어떻게 다른지에 대해 간략하게 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="52af4-107">This article briefly introduces unit tests (and how they differ from other kinds of tests).</span></span> <span data-ttu-id="52af4-108">연결된 리소스에서는 테스트 프로젝트를 솔루션에 추가한 다음 명령줄이나 Visual Studio를 사용하여 단위 테스트를 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="52af4-108">Linked resources demonstrates how to add a test project to your solution and then run unit tests using either the command line or Visual Studio.</span></span>

## <a name="getting-started-with-testing"></a><span data-ttu-id="52af4-109">테스트 시작</span><span class="sxs-lookup"><span data-stu-id="52af4-109">Getting Started with Testing</span></span>
 
<span data-ttu-id="52af4-110">자동화된 테스트 모음이 있다면 소프트웨어 응용 프로그램이 작성자가 의도한 대로 수행되는지 확인하는 최선의 방법 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="52af4-110">Having a suite of automated tests is one of the best ways to ensure a software application does what its authors intended it to do.</span></span> <span data-ttu-id="52af4-111">통합 테스트, 웹 테스트, 부하 테스트 등 소프트웨어 응용 프로그램에 대한 다양한 종류의 테스트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52af4-111">There are many different kinds of tests for software applications, including integration tests, web tests, load tests, and many others.</span></span> <span data-ttu-id="52af4-112">최하위 수준에 개별 소프트웨어 구성 요소나 메서드를 테스트하는 단위 테스트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52af4-112">At the lowest level are unit tests, which test individual software components or methods.</span></span> <span data-ttu-id="52af4-113">단위 테스트에서는 개발자의 제어 수준 내에서만 코드를 테스트하며 데이터베이스, 파일 시스템, 네트워크 리소스 등의 인프라 문제는 테스트하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52af4-113">Unit tests should only test code within the developer’s control, and should not test infrastructure concerns, like databases, file systems, or network resources.</span></span> <span data-ttu-id="52af4-114">단위 테스트는 [TDD(테스트 기반 개발)](http://deviq.com/test-driven-development/)를 사용하여 작성하거나, 기존 코드에 추가하여 정확성을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52af4-114">Unit tests may be written using [Test Driven Development (TDD)](http://deviq.com/test-driven-development/), or they can be added to existing code to confirm its correctness.</span></span> <span data-ttu-id="52af4-115">두 경우 모두 변경 내용을 프로젝트의 공유 코드 리포지토리로 푸시하기 전에 수백 개의 테스트를 실행할 수 있어야 하므로 두 경우 모두 작고 신속하며 이름을 잘 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52af4-115">In either case, they should be small, well-named, and fast, since ideally you will want to be able to run hundreds of them before pushing your changes into the project’s shared code repository.</span></span>

> [!NOTE]
> <span data-ttu-id="52af4-116">개발자는 종종 테스트 클래스 및 메서드에 적합한 이름을 찾으려고 노력합니다.</span><span class="sxs-lookup"><span data-stu-id="52af4-116">Developers often struggle with coming up with good names for their test classes and methods.</span></span> <span data-ttu-id="52af4-117">시작점으로 ASP.NET 제품 팀은 [이러한 규칙](https://github.com/aspnet/Home/wiki/Engineering-guidelines#unit-tests-and-functional-tests)을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="52af4-117">As a starting point, the ASP.NET product team follows [these conventions](https://github.com/aspnet/Home/wiki/Engineering-guidelines#unit-tests-and-functional-tests).</span></span>

<span data-ttu-id="52af4-118">단위 테스트를 작성할 때 실수로 인프라에 대한 종속성이 생성되지 않도록 주의하세요.</span><span class="sxs-lookup"><span data-stu-id="52af4-118">When writing unit tests, be careful you don’t accidentally introduce dependencies on infrastructure.</span></span> <span data-ttu-id="52af4-119">이러한 테스트는 속도가 느려지고 불안정해지는 경향이 있으므로 통합 테스트용으로 예약해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52af4-119">These tend to make tests slower and more brittle, and thus should be reserved for integration tests.</span></span> <span data-ttu-id="52af4-120">[명시적 종속성 원칙](http://deviq.com/explicit-dependencies-principle/)을 따르고 [종속성 주입](/aspnet/core/fundamentals/dependency-injection)을 사용하여 프레임워크에서 종속성을 요청하면 응용 프로그램 코드에서 숨겨진 종속성을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52af4-120">You can avoid these hidden dependencies in your application code by following the [Explicit Dependencies Principle](http://deviq.com/explicit-dependencies-principle/) and using [Dependency Injection](/aspnet/core/fundamentals/dependency-injection) to request your dependencies from the framework.</span></span> <span data-ttu-id="52af4-121">또한 단위 테스트를 통합 테스트와 별도의 프로젝트에 유지하고 단위 테스트 프로젝트에 인프라 패키지에 대한 참조나 종속성이 없도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52af4-121">You can also keep your unit tests in a separate project from your integration tests, and ensure your unit test project doesn’t have references to or dependencies on infrastructure packages.</span></span>

<span data-ttu-id="52af4-122">.NET Core 프로젝트의 단위 테스트에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52af4-122">Learn more about unit testing in .NET Core projects:</span></span>

* <span data-ttu-id="52af4-123">[xUnit 및 .NET Core CLI를 사용하여 단위 테스트 만들기 연습](unit-testing-with-dotnet-test.md)을 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="52af4-123">Try this [walkthrough creating unit tests with xUnit and the .NET Core CLI](unit-testing-with-dotnet-test.md).</span></span> 
* <span data-ttu-id="52af4-124">XUnit 팀은 [.NET Core 및 Visual Studio에서 xUnit을 사용하는 방법](http://xunit.github.io/docs/getting-started-dotnet-core.html)을 보여 주는 자습서를 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="52af4-124">The XUnit team has written a tutorial that shows [how to use xUnit with .NET Core and Visual Studio](http://xunit.github.io/docs/getting-started-dotnet-core.html).</span></span>
* <span data-ttu-id="52af4-125">MSTest를 사용하려는 경우 [MSTest 및 .NET Core CLI를 사용하여 단위 테스트 만들기 연습](unit-testing-with-mstest.md)을 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="52af4-125">If you prefer using MSTest, try the [walkthrough creating unit tests with MSTest and the .NET Core CLI](unit-testing-with-mstest.md).</span></span>
* <span data-ttu-id="52af4-126">선택적 단위 테스트 필터링을 사용하는 방법에 대한 추가 정보 및 예제는 [선택적 단위 테스트 실행](../testing/selective-unit-tests.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52af4-126">For a additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

