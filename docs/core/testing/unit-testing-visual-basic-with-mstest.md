---
title: dotnet test 및 MSTest를 사용하여 .NET Core에서 Visual Basic 유닛 테스트
description: MSTest를 사용하여 샘플 Visual Basic 솔루션을 단계별로 빌드하는 대화형 환경을 통해 .NET Core의 단위 테스트 개념을 알아봅니다.
author: billwagner
ms.author: wiwagn
ms.date: 09/01/2017
ms.topic: conceptual
dev_langs:
- vb
ms.prod: dotnet-core
ms.workload:
- dotnetcore
ms.openlocfilehash: c573d0a4eae38a15f22730748022effdc00ff0a6
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-mstest"></a><span data-ttu-id="724d8-103">dotnet test 및 MSTest를 사용하여 Visual Basic .NET Core 라이브러리 유닛 테스트</span><span class="sxs-lookup"><span data-stu-id="724d8-103">Unit testing Visual Basic .NET Core libraries using dotnet test and MStest</span></span>

<span data-ttu-id="724d8-104">이 자습서에서는 샘플 솔루션을 단계별로 빌드하는 대화형 환경을 통해 단위 테스트 개념을 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="724d8-105">미리 빌드된 솔루션을 사용하여 이 자습서를 진행하려는 경우 시작하기 전에 [샘플 코드를 보거나 다운로드](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-vb-mstest/).</span><span class="sxs-lookup"><span data-stu-id="724d8-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-vb-mstest/) before you begin.</span></span> <span data-ttu-id="724d8-106">다운로드 지침은 [샘플 및 자습서](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="724d8-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="724d8-107">소스 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="724d8-107">Creating the source project</span></span>

<span data-ttu-id="724d8-108">셸 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-108">Open a shell window.</span></span> <span data-ttu-id="724d8-109">솔루션을 저장할 *unit-testing-vb-mstest*라는 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-109">Create a directory called *unit-testing-vb-mstest* to hold the solution.</span></span>
<span data-ttu-id="724d8-110">이 새 디렉터리 내에서 [`dotnet new sln`](../tools/dotnet-new.md)을 실행하여 새 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution.</span></span> <span data-ttu-id="724d8-111">이 방법을 사용하면 클래스 라이브러리와 단위 테스트 프로젝트를 모두 쉽게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-111">This practice makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="724d8-112">솔루션 디렉터리 내에 *PrimeService* 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-112">Inside the solution directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="724d8-113">지금까지의 디렉터리 및 파일 구조는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-113">You have the following directory and file structure thus far:</span></span>

```
/unit-testing-vb-mstest
    unit-testing-vb-mstest.sln
    /PrimeService
```

<span data-ttu-id="724d8-114">*PrimeService*를 현재 디렉터리로 만들고 [`dotnet new classlib -lang VB`](../tools/dotnet-new.md)를 실행하여 소스 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-114">Make *PrimeService* the current directory and run [`dotnet new classlib -lang VB`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="724d8-115">*Class1.VB*의 이름을 *PrimeService.VB*로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-115">Rename *Class1.VB* to *PrimeService.VB*.</span></span> <span data-ttu-id="724d8-116">TDD(테스트 기반 개발)를 사용하기 위해 `PrimeService` 클래스의 실패 구현을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-116">To use test-driven development (TDD), you create a failing implementation of the `PrimeService` class:</span></span>

```vb
Imports System

Namespace Prime.Services
    Public Class PrimeService
        Public Function IsPrime(candidate As Integer) As Boolean
            Throw New NotImplementedException("Please create a test first")
        End Function
    End Class
End Namespace
```

<span data-ttu-id="724d8-117">디렉터리를 다시 *unit-testing-vb-using-stest* 디렉터리로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-117">Change the directory back to the *unit-testing-vb-using-stest* directory.</span></span> <span data-ttu-id="724d8-118">[`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md)를 실행하여 클래스 라이브러리 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-118">Run [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="creating-the-test-project"></a><span data-ttu-id="724d8-119">테스트 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="724d8-119">Creating the test project</span></span>

<span data-ttu-id="724d8-120">다음으로 *PrimeService.Tests* 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-120">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="724d8-121">다음 개요에는 디렉터리 구조가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-121">The following outline shows the directory structure:</span></span>

```
/unit-testing-vb-mstest
    unit-testing-vb-mstest.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
```

<span data-ttu-id="724d8-122">*PrimeService.Tests* 디렉터리를 현재 디렉터리로 만들고 [`dotnet new mstest -lang VB`](../tools/dotnet-new.md)를 사용하여 새 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-122">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new mstest -lang VB`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="724d8-123">이 명령은 MSTest를 테스트 라이브러리로 사용하는 테스트 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-123">This command creates a test project that uses MSTest as the test library.</span></span> <span data-ttu-id="724d8-124">생성된 템플릿은 *PrimeServiceTests.vbproj*에 Test Runner를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-124">The generated template configures the test runner in the *PrimeServiceTests.vbproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.5.0" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

<span data-ttu-id="724d8-125">테스트 프로제트는 다른 패키지에 단위 테스트를 만들고 실행하도록 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-125">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="724d8-126">이전 단계의 `dotnet new`는 MSTest 및 MSTest runner를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-126">`dotnet new` in the previous step added MSTest and the MSTest runner.</span></span> <span data-ttu-id="724d8-127">이제 `PrimeService` 클래스 라이브러리를 프로젝트에 다른 종속성으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-127">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="724d8-128">[`dotnet add reference`](../tools/dotnet-add-reference.md) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-128">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.vbproj
```

<span data-ttu-id="724d8-129">GitHub의 [샘플 리포지토리](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-mstest/PrimeService.Tests/PrimeService.Tests.vbproj)에서 전체 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-129">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-mstest/PrimeService.Tests/PrimeService.Tests.vbproj) on GitHub.</span></span>

<span data-ttu-id="724d8-130">최종 솔루션 레이아웃은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-130">You have the following final solution layout:</span></span>

```
/unit-testing-vb-mstest
    unit-testing-vb-mstest.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.vbproj
```

<span data-ttu-id="724d8-131">*unit-testing-vb-mstest* 디렉터리에서 [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md)를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-131">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md) in the *unit-testing-vb-mstest* directory.</span></span>

## <a name="creating-the-first-test"></a><span data-ttu-id="724d8-132">첫 번째 테스트 만들기</span><span class="sxs-lookup"><span data-stu-id="724d8-132">Creating the first test</span></span>

<span data-ttu-id="724d8-133">TDD 접근 방식에서는 하나의 실패 테스트를 작성하고, 통과시키고, 이 프로세스를 반복해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-133">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="724d8-134">*PrimeService.Tests* 디렉터리에서 *UnitTest1.vb*를 제거하고 새 Visual Basic 파일 *PrimeService_IsPrimeShould.VB*를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-134">Remove *UnitTest1.vb* from the *PrimeService.Tests* directory and create a new Visual Basic file named *PrimeService_IsPrimeShould.VB*.</span></span> <span data-ttu-id="724d8-135">다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-135">Add the following code:</span></span>

```vb
Imports Microsoft.VisualStudio.TestTools.UnitTesting

Namespace PrimeService.Tests
    <TestClass>
    Public Class PrimeService_IsPrimeShould
        Private _primeService As Prime.Services.PrimeService = New Prime.Services.PrimeService()

        <TestMethod>
        Sub ReturnFalseGivenValueOf1()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.False(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

<span data-ttu-id="724d8-136">`<TestClass>` 특성은 테스트가 포함된 클래스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-136">The `<TestClass>` attribute indicates a class that contains tests.</span></span> <span data-ttu-id="724d8-137">`<TestMethod>` 특성은 Test Runner에서 실행하는 메서드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-137">The `<TestMethod>` attribute denotes a method that is run by the test runner.</span></span> <span data-ttu-id="724d8-138">*unit-testing-vb-mstest*에서 [`dotnet test`](../tools/dotnet-test.md)를 실행하여 테스트 및 클래스 라이브러리를 빌드한 다음 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-138">From the *unit-testing-vb-mstest*, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="724d8-139">MSTest Test Runner에는 테스트를 실행할 프로그램 진입점이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-139">The MSTest test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="724d8-140">`dotnet test`는 만든 단위 테스트 프로젝트를 사용하여 Test Runner를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-140">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="724d8-141">테스트가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-141">Your test fails.</span></span> <span data-ttu-id="724d8-142">구현은 아직 만들지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-142">You haven't created the implementation yet.</span></span> <span data-ttu-id="724d8-143">`PrimeService` 클래스에서 작동하는 가장 간단한 코드를 작성하여 이 테스트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-143">Make this test by writing the simplest code in the `PrimeService` class that works:</span></span>

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Please create a test first")
End Function
```

<span data-ttu-id="724d8-144">*unit-testing-vb-mstest* 디렉터리에서 `dotnet test`를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-144">In the *unit-testing-vb-mstest* directory, run `dotnet test` again.</span></span> <span data-ttu-id="724d8-145">`dotnet test` 명령은 `PrimeService` 프로젝트에 대한 빌드를 실행한 다음 `PrimeService.Tests` 프로젝트에 대한 빌드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-145">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="724d8-146">두 프로젝트를 모두 빌드한 후 이 단일 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-146">After building both projects, it runs this single test.</span></span> <span data-ttu-id="724d8-147">전달합니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-147">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="724d8-148">더 많은 기능 추가</span><span class="sxs-lookup"><span data-stu-id="724d8-148">Adding more features</span></span>

<span data-ttu-id="724d8-149">이제 하나의 테스트를 통과했으므로 더 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-149">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="724d8-150">소수에 대한 몇 가지 다른 간단한 사례가 있습니다(0, -1).</span><span class="sxs-lookup"><span data-stu-id="724d8-150">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="724d8-151">이러한 사례를 `<TestMethod>` 특성과 함께 새 테스트로 추가할 수도 있지만, 이렇게 하면 금방 지루해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-151">You could add those cases as new tests with the `<TestMethod>` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="724d8-152">비슷한 테스트 모음을 작성하는 데 사용할 수 있는 다른 MSTest 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-152">There are other MSTest attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="724d8-153">`<DataTestMethod>` 특성은 같은 코드를 실행하는 테스트 모음을 나타내지만, 서로 다른 입력 인수를 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-153">A `<DataTestMethod>` attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="724d8-154">`<DataRow>` 특성을 사용하여 그러한 입력의 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-154">You can use the `<DataRow>` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="724d8-155">새 테스트를 만드는 대신 이러한 두 특성을 적용하여 단일 이론을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-155">Instead of creating new tests, apply these two attributes to create a single theory.</span></span> <span data-ttu-id="724d8-156">이 이론은 가장 작은 소수인 2보다 작은 몇 가지 값을 테스트하는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-156">The theory is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-vb[Sample_TestCode](../../../samples/core/getting-started/unit-testing-vb-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.vb?name=Sample_TestCode)]

<span data-ttu-id="724d8-157">`dotnet test`를 실행합니다. 그러면 이러한 테스트 중 2개가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-157">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="724d8-158">모든 테스트가 통과하도록 하려면 메서드의 시작 부분에서 `if` 절을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-158">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```vb
if candidate < 2
```

<span data-ttu-id="724d8-159">기본 라이브러리에서 더 많은 테스트, 더 많은 이론, 더 많은 코드를 추가하여 계속 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-159">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="724d8-160">[테스트의 완료된 버전](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.vb) 및 [라이브러리의 완전한 구현](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-mstest/PrimeService/PrimeService.vb)을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-160">You have the [finished version of the tests](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.vb) and the [complete implementation of the library](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-vb-mstest/PrimeService/PrimeService.vb).</span></span>

<span data-ttu-id="724d8-161">작은 라이브러리 및 이 라이브러리에 대한 단위 테스트 집합을 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-161">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="724d8-162">새 패키지 및 테스트 추가가 정상 워크플로에 포함되도록 솔루션을 구조화했습니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-162">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="724d8-163">응용 프로그램의 목표를 해결하는 데 대부분의 시간과 노력을 들였습니다.</span><span class="sxs-lookup"><span data-stu-id="724d8-163">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
