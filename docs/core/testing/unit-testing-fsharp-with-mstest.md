---
title: dotnet test 및 MSTest를 사용하여 .NET Core에서 F# 라이브러리 유닛 테스트
description: dotnet test 및 MSTest를 사용하여 샘플 솔루션을 단계별로 빌드하는 대화형 환경을 통해 .NET Core의 F#에 대한 단위 테스트 개념을 알아봅니다.
author: billwagner
ms.author: wiwagn
ms.date: 08/30/2017
dev_langs:
- fsharp
ms.openlocfilehash: 14e1ac54cb966e0e38c962e92cceb764fd8e9b42
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33218860"
---
# <a name="unit-testing-f-libraries-in-net-core-using-dotnet-test-and-mstest"></a><span data-ttu-id="1e718-103">dotnet test 및 MSTest를 사용하여 .NET Core에서 F# 라이브러리 유닛 테스트</span><span class="sxs-lookup"><span data-stu-id="1e718-103">Unit testing F# libraries in .NET Core using dotnet test and MSTest</span></span>

<span data-ttu-id="1e718-104">이 자습서에서는 샘플 솔루션을 단계별로 빌드하는 대화형 환경을 통해 단위 테스트 개념을 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="1e718-105">미리 빌드된 솔루션을 사용하여 이 자습서를 진행하려는 경우 시작하기 전에 [샘플 코드를 보거나 다운로드](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp-mstest/).</span><span class="sxs-lookup"><span data-stu-id="1e718-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp-mstest/) before you begin.</span></span> <span data-ttu-id="1e718-106">다운로드 지침은 [샘플 및 자습서](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e718-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="1e718-107">소스 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="1e718-107">Creating the source project</span></span>

<span data-ttu-id="1e718-108">셸 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-108">Open a shell window.</span></span> <span data-ttu-id="1e718-109">솔루션을 저장할 *unit-testing-with-fsharp*라는 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-109">Create a directory called *unit-testing-with-fsharp* to hold the solution.</span></span>
<span data-ttu-id="1e718-110">이 새 디렉터리 내에서 [`dotnet new sln`](../tools/dotnet-new.md)을 실행하여 새 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution.</span></span> <span data-ttu-id="1e718-111">이렇게 하면 클래스 라이브러리와 단위 테스트 프로젝트를 모두 쉽게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-111">This makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="1e718-112">솔루션 디렉터리 내에 *MathService* 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-112">Inside the solution directory, create a *MathService* directory.</span></span> <span data-ttu-id="1e718-113">따라서 지금까지의 디렉터리 및 파일 구조는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-113">The directory and file structure thus far is shown below:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
```

<span data-ttu-id="1e718-114">*MathService*를 현재 디렉터리로 만들고 [`dotnet new classlib -lang F#`](../tools/dotnet-new.md)을 실행하여 소스 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-114">Make *MathService* the current directory and run [`dotnet new classlib -lang F#`](../tools/dotnet-new.md) to create the source project.</span></span>  <span data-ttu-id="1e718-115">TDD(테스트 기반 개발)를 사용하기 위해 수학 서비스의 실패 구현을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-115">To use test-driven development (TDD), you'll create a failing implementation of the math service:</span></span>

```fsharp
module MyMath =
    let squaresOfOdds xs = raise (System.NotImplementedException("You haven't written a test yet!"))
```

<span data-ttu-id="1e718-116">디렉터리를 다시 *unit-testing-with-fsharp* 디렉터리로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-116">Change the directory back to the *unit-testing-with-fsharp* directory.</span></span> <span data-ttu-id="1e718-117">[`dotnet sln add .\MathService\MathService.fsproj`](../tools/dotnet-sln.md)를 실행하여 클래스 라이브러리 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-117">Run [`dotnet sln add .\MathService\MathService.fsproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="creating-the-test-project"></a><span data-ttu-id="1e718-118">테스트 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="1e718-118">Creating the test project</span></span>

<span data-ttu-id="1e718-119">다음으로 *MathService.Tests* 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-119">Next, create the *MathService.Tests* directory.</span></span> <span data-ttu-id="1e718-120">다음 개요에는 디렉터리 구조가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-120">The following outline shows the directory structure:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
```

<span data-ttu-id="1e718-121">*MathService.Tests* 디렉터리를 현재 디렉터리로 만들고 [`dotnet new mstest -lang F#`](../tools/dotnet-new.md)을 사용하여 새 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-121">Make the *MathService.Tests* directory the current directory and create a new project using [`dotnet new mstest -lang F#`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="1e718-122">그러면 MSTest를 테스트 프레임워크로 사용하는 테스트 프로젝트가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-122">This creates a test project that uses MSTest as the test framework.</span></span> <span data-ttu-id="1e718-123">생성된 템플릿은 *MathServiceTests.fsproj*에 Test Runner를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-123">The generated template configures the test runner in the *MathServiceTests.fsproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0-preview-20170628-02" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

<span data-ttu-id="1e718-124">테스트 프로제트는 다른 패키지에 단위 테스트를 만들고 실행하도록 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-124">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="1e718-125">이전 단계의 `dotnet new`는 MSTest 및 MSTest runner를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-125">`dotnet new` in the previous step added MSTest and the MSTest runner.</span></span> <span data-ttu-id="1e718-126">이제 `MathService` 클래스 라이브러리를 프로젝트에 다른 종속성으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-126">Now, add the `MathService` class library as another dependency to the project.</span></span> <span data-ttu-id="1e718-127">[`dotnet add reference`](../tools/dotnet-add-reference.md) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-127">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../MathService/MathService.fsproj
```

<span data-ttu-id="1e718-128">GitHub의 [샘플 리포지토리](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj)에서 전체 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-128">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) on GitHub.</span></span>

<span data-ttu-id="1e718-129">최종 솔루션 레이아웃은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-129">You have the following final solution layout:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
        Test Source Files
        MathServiceTests.fsproj
```

<span data-ttu-id="1e718-130">*unit-testing-with-fsharp* 디렉터리에서 [`dotnet sln add .\MathService.Tests\MathService.Tests.fsproj`](../tools/dotnet-sln.md)를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-130">Execute [`dotnet sln add .\MathService.Tests\MathService.Tests.fsproj`](../tools/dotnet-sln.md) in the *unit-testing-with-fsharp* directory.</span></span>

## <a name="creating-the-first-test"></a><span data-ttu-id="1e718-131">첫 번째 테스트 만들기</span><span class="sxs-lookup"><span data-stu-id="1e718-131">Creating the first test</span></span>

<span data-ttu-id="1e718-132">TDD 접근 방식에서는 하나의 실패 테스트를 작성하고, 통과시키고, 이 프로세스를 반복해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-132">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="1e718-133">*Tests.fs*를 열고 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-133">Open *Tests.fs* and add the following code:</span></span>

```fsharp
namespace MathService.Tests

open System
open Microsoft.VisualStudio.TestTools.UnitTesting
open MathService

[<TestClass>]
type TestClass () =

    [<TestMethod>]
    member this.TestMethodPassing() =
        Assert.IsTrue(true)

    [<TestMethod>]
     member this.FailEveryTime() = Assert.IsTrue(false)
```

<span data-ttu-id="1e718-134">`[<TestClass>]` 특성은 테스트가 포함된 클래스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-134">The `[<TestClass>]` attribute denotes a class that contains tests.</span></span> <span data-ttu-id="1e718-135">`[<TestMethod>]` 특성은 Test Runner에서 실행하는 테스트 메서드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-135">The `[<TestMethod>]` attribute denotes a test method that is run by the test runner.</span></span> <span data-ttu-id="1e718-136">*unit-testing-with-fsharp* 디렉터리에서 [`dotnet test`](../tools/dotnet-test.md)를 실행하여 테스트 및 클래스 라이브러리를 빌드한 다음 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-136">From the *unit-testing-with-fsharp* directory, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="1e718-137">MSTest Test Runner에는 테스트를 실행할 프로그램 진입점이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-137">The MSTest test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="1e718-138">`dotnet test`는 만든 단위 테스트 프로젝트를 사용하여 Test Runner를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-138">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="1e718-139">이러한 두 테스트는 가장 기본적인 통과 및 실패 테스트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-139">These two tests show the most basic passing and failing tests.</span></span> <span data-ttu-id="1e718-140">`My test`는 통과하고 `Fail every time`은 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-140">`My test` passes, and `Fail every time` fails.</span></span> <span data-ttu-id="1e718-141">이제 `squaresOfOdds` 메서드에 대한 테스트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-141">Now, create a test for the `squaresOfOdds` method.</span></span> <span data-ttu-id="1e718-142">`squaresOfOdds` 메서드는 입력 시퀀스에 포함된 모든 홀수 정수 값 제곱의 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-142">The `squaresOfOdds` method returns a list of the squares of all odd integer values that are part of the input sequence.</span></span> <span data-ttu-id="1e718-143">이러한 모든 함수를 한 번에 작성하지 않고 기능의 유효성을 검사하는 테스트를 반복적으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-143">Rather than trying to write all of those functions at once, you can iteratively create tests that validate the functionality.</span></span> <span data-ttu-id="1e718-144">각 테스트 패스를 만들면 메서드에 필요한 기능이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-144">Making each test pass means creating the necessary functionality for the method.</span></span>

<span data-ttu-id="1e718-145">작성할 수 있는 가장 간단한 테스트는 모든 짝수를 사용하여 `squaresOfOdds`를 호출하는 것입니다. 이 경우 결과는 빈 정수 시퀀스여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-145">The simplest test we can write is to call `squaresOfOdds` with all even numbers, where the result should be an empty sequence of integers.</span></span>  <span data-ttu-id="1e718-146">해당 테스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-146">Here's that test:</span></span>

```fsharp
[<TestMethod>]
member this.TestEvenSequence() =
    let expected = Seq.empty<int> |> Seq.toList
    let actual = MyMath.squaresOfOdds [2; 4; 6; 8; 10]
    Assert.AreEqual(expected, actual)
```

<span data-ttu-id="1e718-147">`expected` 시퀀스가 목록으로 변환되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-147">Notice that the `expected` sequence has been converted to a list.</span></span> <span data-ttu-id="1e718-148">MSTest 라이브러리는 많은 표준 .NET 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-148">The MSTest library relies on many standard .NET types.</span></span> <span data-ttu-id="1e718-149">해당 종속성으로 인해 공용 인터페이스 및 예상 결과에서 <xref:System.Collections.IEnumerable> 대신 <xref:System.Collections.ICollection>을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-149">That dependency means that your public interface and expected results support <xref:System.Collections.ICollection> rather than <xref:System.Collections.IEnumerable>.</span></span>

<span data-ttu-id="1e718-150">테스트를 실행하면 테스트가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-150">When you run the test, you see that your test fails.</span></span> <span data-ttu-id="1e718-151">구현은 아직 만들지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-151">You haven't created the implementation yet.</span></span> <span data-ttu-id="1e718-152">`Mathservice` 클래스에서 작동하는 가장 간단한 코드를 작성하여 이 테스트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-152">Make this test by writing the simplest code in the `Mathservice` class that works:</span></span>

```csharp
let squaresOfOdds xs =
    Seq.empty<int> |> Seq.toList
```

<span data-ttu-id="1e718-153">*unit-testing-with-fsharp* 디렉터리에서 `dotnet test`를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-153">In the *unit-testing-with-fsharp* directory, run `dotnet test` again.</span></span> <span data-ttu-id="1e718-154">`dotnet test` 명령은 `MathService` 프로젝트에 대한 빌드를 실행한 다음 `MathService.Tests` 프로젝트에 대한 빌드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-154">The `dotnet test` command runs a build for the `MathService` project and then for the `MathService.Tests` project.</span></span> <span data-ttu-id="1e718-155">두 프로젝트를 모두 빌드한 후 이 단일 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-155">After building both projects, it runs this single test.</span></span> <span data-ttu-id="1e718-156">전달합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-156">It passes.</span></span>

## <a name="completing-the-requirements"></a><span data-ttu-id="1e718-157">요구 사항 완료</span><span class="sxs-lookup"><span data-stu-id="1e718-157">Completing the requirements</span></span>

<span data-ttu-id="1e718-158">이제 하나의 테스트를 통과했으므로 더 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-158">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="1e718-159">다음의 단순한 사례에서는 유일한 홀수가 `1`인 시퀀스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-159">The next simple case works with a sequence whose only odd number is `1`.</span></span> <span data-ttu-id="1e718-160">숫자 1은 제곱이 1이므로 더 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-160">The number 1 is easier because the square of 1 is 1.</span></span> <span data-ttu-id="1e718-161">이 테스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-161">Here's that next test:</span></span>

```fsharp
[<TestMethod>]
member public this.TestOnesAndEvens() =
    let expected = [1; 1; 1; 1]
    let actual = MyMath.squaresOfOdds [2; 1; 4; 1; 6; 1; 8; 1; 10]
    Assert.AreEqual(expected, actual)
```

<span data-ttu-id="1e718-162">`dotnet test`를 실행하면 새 테스트가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-162">Executing `dotnet test` fails the new test.</span></span> <span data-ttu-id="1e718-163">이제 `squaresOfOdds` 메서드를 업데이트하여 이 새 테스트를 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-163">You must update the `squaresOfOdds` method to handle this new test.</span></span> <span data-ttu-id="1e718-164">시퀀스에서 모든 짝수를 필터링하여 이 테스트가 통과하게 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-164">You must filter all the even numbers out of the sequence to make this test pass.</span></span> <span data-ttu-id="1e718-165">이렇게 하려면 작은 필터 함수를 작성하고 `Seq.filter`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-165">You can do that by writing a small filter function and using `Seq.filter`:</span></span>

```fsharp
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd |> Seq.toList
```

<span data-ttu-id="1e718-166">`Seq.toList`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-166">Notice the call to `Seq.toList`.</span></span> <span data-ttu-id="1e718-167">그러면 <xref:System.Collections.ICollection> 인터페이스를 구현하는 목록이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-167">That creates a list, which implements the <xref:System.Collections.ICollection> interface.</span></span>

<span data-ttu-id="1e718-168">한 가지 단계가 남았습니다. 즉, 각 홀수를 제곱합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-168">There's one more step to go: square each of the odd numbers.</span></span> <span data-ttu-id="1e718-169">먼저 새 테스트를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-169">Start by writing a new test:</span></span>

```fsharp
[<TestMethod>]
member public this.TestSquaresOfOdds() =
    let expected = [1; 9; 25; 49; 81]
    let actual = MyMath.squaresOfOdds [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
    Assert.AreEqual(expected, actual)
```

<span data-ttu-id="1e718-170">맵 작업을 통해 필터링된 시퀀스를 파이프하여 각 홀수의 제곱을 계산하는 방법으로 테스트를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-170">You can fix the test by piping the filtered sequence through a map operation to compute the square of each odd number:</span></span>

```fsharp
let private square x = x * x
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd
    |> Seq.map square
    |> Seq.toList
```

<span data-ttu-id="1e718-171">작은 라이브러리 및 이 라이브러리에 대한 단위 테스트 집합을 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-171">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="1e718-172">새 패키지 및 테스트 추가가 정상 워크플로에 포함되도록 솔루션을 구조화했습니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-172">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="1e718-173">응용 프로그램의 목표를 해결하는 데 대부분의 시간과 노력을 들였습니다.</span><span class="sxs-lookup"><span data-stu-id="1e718-173">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
