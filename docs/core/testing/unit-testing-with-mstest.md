---
title: MSTest 및 .NET Core를 사용한 C# 유닛 테스트
description: dotnet test 및 MSTest를 사용하여 샘플 솔루션을 단계별로 빌드하는 대화형 환경을 통해 C# 및 .NET Core의 단위 테스트 개념을 알아봅니다.
keywords: MSTest, .NET, .NET Core
author: ncarandini
ms.author: wiwagn
ms.date: 09/08/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: ed447641-3e85-4e50-b7ed-004630048a3e
ms.workload:
- dotnetcore
ms.openlocfilehash: 742e0f5707580f70ed068fff18faa7b5e2fd8625
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2018
---
# <a name="unit-testing-c-with-mstest-and-net-core"></a><span data-ttu-id="c0183-104">MSTest 및 .NET Core를 사용한 C# 유닛 테스트</span><span class="sxs-lookup"><span data-stu-id="c0183-104">Unit testing C# with MSTest and .NET Core</span></span>

<span data-ttu-id="c0183-105">이 자습서에서는 샘플 솔루션을 단계별로 빌드하는 대화형 환경을 통해 단위 테스트 개념을 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-105">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="c0183-106">미리 빌드된 솔루션을 사용하여 이 자습서를 진행하려는 경우 시작하기 전에 [샘플 코드를 보거나 다운로드](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/).</span><span class="sxs-lookup"><span data-stu-id="c0183-106">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/) before you begin.</span></span> <span data-ttu-id="c0183-107">다운로드 지침은 [샘플 및 자습서](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0183-107">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

### <a name="creating-the-source-project"></a><span data-ttu-id="c0183-108">소스 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="c0183-108">Creating the source project</span></span>

<span data-ttu-id="c0183-109">셸 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-109">Open a shell window.</span></span> <span data-ttu-id="c0183-110">솔루션을 저장하기 위한 *unit-testing-using-dotnet-test*라는 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-110">Create a directory called *unit-testing-using-dotnet-test* to hold the solution.</span></span> <span data-ttu-id="c0183-111">이 새 디렉터리 내에서 [`dotnet new sln`](../tools/dotnet-new.md)을 실행하여 클래스 라이브러리 및 테스트 프로젝트에 대한 새 솔루션 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-111">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution file for the class library and the test project.</span></span> <span data-ttu-id="c0183-112">다음으로 *PrimeService* 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-112">Next, create a *PrimeService* directory.</span></span> <span data-ttu-id="c0183-113">다음 개요에는 지금까지의 디렉터리 및 파일 구조가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-113">The following outline shows the directory and file structure thus far:</span></span>

```
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
```

<span data-ttu-id="c0183-114">*PrimeService*를 현재 디렉터리로 만들고 [`dotnet new classlib`](../tools/dotnet-new.md)를 실행하여 소스 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-114">Make *PrimeService* the current directory and run [`dotnet new classlib`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="c0183-115">*Class1.cs*의 이름을 *PrimeService.cs*로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-115">Rename *Class1.cs* to *PrimeService.cs*.</span></span> <span data-ttu-id="c0183-116">TDD(테스트 기반 개발)를 사용하기 위해 `PrimeService` 클래스의 실패 구현을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-116">To use test-driven development (TDD), you create a failing implementation of the `PrimeService` class:</span></span>

```csharp
using System;

namespace Prime.Services
{
    public class PrimeService
    {
        public bool IsPrime(int candidate) 
        {
            throw new NotImplementedException("Please create a test first");
        } 
    }
}
```

<span data-ttu-id="c0183-117">디렉터리를 다시 *unit-testing-using-mstest* 디렉터리로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-117">Change the directory back to the *unit-testing-using-mstest* directory.</span></span> <span data-ttu-id="c0183-118">[`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md)를 실행하여 클래스 라이브러리 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-118">Run [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span> 

### <a name="creating-the-test-project"></a><span data-ttu-id="c0183-119">테스트 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="c0183-119">Creating the test project</span></span>

<span data-ttu-id="c0183-120">다음으로 *PrimeService.Tests* 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-120">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="c0183-121">다음 개요에는 디렉터리 구조가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-121">The following outline shows the directory structure:</span></span>

```
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

<span data-ttu-id="c0183-122">*PrimeService.Tests* 디렉터리를 현재 디렉터리로 만들고 [`dotnet new mstest`](../tools/dotnet-new.md)를 사용하여 새 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-122">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new mstest`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="c0183-123">dotnet new 명령은 MStest를 테스트 라이브러리로 사용하는 테스트 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-123">The dotnet new command creates a test project that uses MStest as the test library.</span></span> <span data-ttu-id="c0183-124">생성된 템플릿이 *PrimeServiceTests.csproj* 파일에 Test Runner를 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-124">The generated template configures the test runner in the *PrimeServiceTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

<span data-ttu-id="c0183-125">테스트 프로제트는 다른 패키지에 단위 테스트를 만들고 실행하도록 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-125">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="c0183-126">이전 단계의 `dotnet new`는 MSTest SDK, MSTest 테스트 프레임워크 및 MSTest Runner를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-126">`dotnet new` in the previous step added the MSTest SDK, the MSTest test framework, and the MSTest runner.</span></span> <span data-ttu-id="c0183-127">이제 `PrimeService` 클래스 라이브러리를 프로젝트에 다른 종속성으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-127">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="c0183-128">[`dotnet add reference`](../tools/dotnet-add-reference.md) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-128">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

<span data-ttu-id="c0183-129">GitHub의 [샘플 리포지토리](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj)에서 전체 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-129">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) on GitHub.</span></span>

<span data-ttu-id="c0183-130">다음 개요에는 최종 솔루션 레이아웃이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-130">The following outline shows the final solution layout:</span></span>

```
/unit-testing-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

<span data-ttu-id="c0183-131">*unit-testing-using-dotnet-test* 디렉터리에서 [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md)를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-131">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md) in the *unit-testing-using-dotnet-test* directory.</span></span> 

## <a name="creating-the-first-test"></a><span data-ttu-id="c0183-132">첫 번째 테스트 만들기</span><span class="sxs-lookup"><span data-stu-id="c0183-132">Creating the first test</span></span>

<span data-ttu-id="c0183-133">TDD 접근 방식에서는 하나의 실패 테스트를 작성하고, 통과시키고, 이 프로세스를 반복해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-133">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="c0183-134">*PrimeService.Tests* 디렉터리에서 *UnitTest1.cs*를 제거하고 다음과 같은 내용으로 새 C# 파일 *PrimeService_IsPrimeShould.cs*를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-134">Remove *UnitTest1.cs* from the *PrimeService.Tests* directory and create a new C# file named *PrimeService_IsPrimeShould.cs* with the following content:</span></span>

```csharp
using Microsoft.VisualStudio.TestTools.UnitTesting;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    [TestClass]
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [TestMethod]
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.IsFalse(result, "1 should not be prime");
        }
    }
}
```

<span data-ttu-id="c0183-135">`[TestClass]` 특성은 단위 테스트가 포함된 클래스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-135">The `[TestClass]` attribute denotes a class that contains unit tests.</span></span> <span data-ttu-id="c0183-136">`[TestMethod]` 특성은 메서드가 테스트 메서드임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-136">The `[TestMethod]` attribute indicates a method is a test method.</span></span> 

<span data-ttu-id="c0183-137">이 파일을 저장하고 [`dotnet test`](../tools/dotnet-test.md)를 실행하여 테스트 및 클래스 라이브러리를 빌드한 다음 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-137">Save this file and execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="c0183-138">MSTest Test Runner에는 테스트를 실행할 프로그램 진입점이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-138">The MSTest test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="c0183-139">`dotnet test`는 만든 단위 테스트 프로젝트를 사용하여 Test Runner를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-139">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="c0183-140">테스트가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-140">Your test fails.</span></span> <span data-ttu-id="c0183-141">구현은 아직 만들지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-141">You haven't created the implementation yet.</span></span> <span data-ttu-id="c0183-142">`PrimeService` 클래스에서 작동하는 가장 간단한 코드를 작성하여 이 테스트를 통과시킵니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-142">Make this test pass by writing the simplest code in the `PrimeService` class that works:</span></span>

```csharp
public bool IsPrime(int candidate)
{
    if (candidate == 1)
    {
        return false;
    }
    throw new NotImplementedException("Please create a test first");
}
```

<span data-ttu-id="c0183-143">*unit-testing-using-mstest* 디렉터리에서 `dotnet test`를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-143">In the *unit-testing-using-mstest* directory, run `dotnet test` again.</span></span> <span data-ttu-id="c0183-144">`dotnet test` 명령은 `PrimeService` 프로젝트에 대한 빌드를 실행한 다음 `PrimeService.Tests` 프로젝트에 대한 빌드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-144">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="c0183-145">두 프로젝트를 모두 빌드한 후 이 단일 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-145">After building both projects, it runs this single test.</span></span> <span data-ttu-id="c0183-146">전달합니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-146">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="c0183-147">더 많은 기능 추가</span><span class="sxs-lookup"><span data-stu-id="c0183-147">Adding more features</span></span>

<span data-ttu-id="c0183-148">이제 하나의 테스트를 통과했으므로 더 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-148">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="c0183-149">소수에 대한 몇 가지 다른 간단한 사례가 있습니다(0, -1).</span><span class="sxs-lookup"><span data-stu-id="c0183-149">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="c0183-150">새 테스트를 `[TestMethod]` 특성과 함께 추가할 수도 있지만, 이렇게 하면 금방 지루해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-150">You could add new tests with the `[TestMethod]` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="c0183-151">비슷한 테스트 모음을 작성하는 데 사용할 수 있는 다른 MSTest 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-151">There are other MSTest attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="c0183-152">`[DataTestMethod]` 특성은 같은 코드를 실행하는 테스트 모음을 나타내지만, 서로 다른 입력 인수를 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-152">A `[DataTestMethod]`attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="c0183-153">`[DataRow]` 특성을 사용하여 그러한 입력의 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-153">You can use the `[DataRow]` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="c0183-154">새 테스트를 만드는 대신 이러한 두 특성을 적용하여 단일 데이터 기반 테스트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-154">Instead of creating new tests, apply these two attributes to create a single data driven test.</span></span> <span data-ttu-id="c0183-155">이 데이터 기반 테스트는 가장 작은 소수인 2보다 작은 몇 가지 값을 테스트하는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-155">The data driven test is a method that tests several values less than two, which is the lowest prime number: :</span></span>

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

<span data-ttu-id="c0183-156">`dotnet test`를 실행합니다. 그러면 이러한 테스트 중 2개가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-156">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="c0183-157">모든 테스트가 통과하도록 하려면 메서드의 시작 부분에서 `if` 절을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-157">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```csharp
if (candidate < 2)
```

<span data-ttu-id="c0183-158">기본 라이브러리에서 더 많은 테스트, 더 많은 이론, 더 많은 코드를 추가하여 계속 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-158">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="c0183-159">[테스트의 완료된 버전](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) 및 [라이브러리의 완전한 구현](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs)을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-159">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).</span></span>

<span data-ttu-id="c0183-160">작은 라이브러리 및 이 라이브러리에 대한 단위 테스트 집합을 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-160">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="c0183-161">새 패키지 및 테스트 추가가 정상 워크플로에 포함되도록 솔루션을 구조화했습니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-161">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="c0183-162">응용 프로그램의 목표를 해결하는 데 대부분의 시간과 노력을 들였습니다.</span><span class="sxs-lookup"><span data-stu-id="c0183-162">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
