---
title: 선택적 단위 테스트 실행
description: 필터 식을 사용하여 dotnet 명령으로 선택적 단위 테스트를 실행하는 방법을 보여 줍니다.
author: smadala
ms.author: mairaw
ms.date: 03/22/2017
ms.openlocfilehash: caea91e9884dba6bc07a7ef6a99699e43d23399c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="a3617-103">선택적 단위 테스트 실행</span><span class="sxs-lookup"><span data-stu-id="a3617-103">Running selective unit tests</span></span>

<span data-ttu-id="a3617-104">다음 예제에서는 `dotnet test`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a3617-104">The following examples use `dotnet test`.</span></span> <span data-ttu-id="a3617-105">`vstest.console.exe`를 사용하는 경우 `--filter `를 `--testcasefilter:`로 바꾸세요.</span><span class="sxs-lookup"><span data-stu-id="a3617-105">If you're using `vstest.console.exe`, replace `--filter ` with `--testcasefilter:`.</span></span>

## <a name="mstest"></a><span data-ttu-id="a3617-106">MSTest</span><span class="sxs-lookup"><span data-stu-id="a3617-106">MSTest</span></span>

```csharp
namespace MSTestNamespace
{
    using Microsoft.VisualStudio.TestTools.UnitTesting;

    [TestClass]
    public class UnitTestClass1
    {
        [Priority(2)]
        [TestMethod]
        public void TestMethod1()
        {
        }

        [TestCategory("CategoryA")]
        [Priority(3)]
        [TestMethod]
        public void TestMethod2()
        {
        }
    }
}
```

| <span data-ttu-id="a3617-107">식</span><span class="sxs-lookup"><span data-stu-id="a3617-107">Expression</span></span> | <span data-ttu-id="a3617-108">결과</span><span class="sxs-lookup"><span data-stu-id="a3617-108">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="a3617-109">`FullyQualifiedName`에 `Method`가 포함된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a3617-109">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="a3617-110">`vstest 15.1+`에서 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="a3617-110">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="a3617-111">이름에 `TestMethod1`이 포함된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a3617-111">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTestClass1` | <span data-ttu-id="a3617-112">클래스 `MSTestNamespace.UnitTestClass1`에 속하는 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a3617-112">Runs tests which are in class `MSTestNamespace.UnitTestClass1`.</span></span><br><span data-ttu-id="a3617-113">**참고:** `ClassName` 값에는 네임스페이스가 있어야 하므로, `ClassName=UnitTestClass1`이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3617-113">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTestClass1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTestClass1.TestMethod1` | <span data-ttu-id="a3617-114">`MSTestNamespace.UnitTestClass1.TestMethod1`을 제외한 모든 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a3617-114">Runs all tests except `MSTestNamespace.UnitTestClass1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="a3617-115">`[TestCategory("CategoryA")]`로 주석이 추가된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a3617-115">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=3` | <span data-ttu-id="a3617-116">`[Priority(3)]`로 주석이 추가된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a3617-116">Runs tests which are annotated with `[Priority(3)]`.</span></span><br><span data-ttu-id="a3617-117">**참고:** `Priority~3`는 문자열이 아니므로 잘못된 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a3617-117">**Note:** `Priority~3` is an invalid value, as it isn't a string.</span></span> |

<span data-ttu-id="a3617-118">**조건 연산자 | 및 &amp; 사용**</span><span class="sxs-lookup"><span data-stu-id="a3617-118">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="a3617-119">식</span><span class="sxs-lookup"><span data-stu-id="a3617-119">Expression</span></span> | <span data-ttu-id="a3617-120">결과</span><span class="sxs-lookup"><span data-stu-id="a3617-120">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTestClass1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="a3617-121">`FullyQualifiedName`에 `UnitTestClass1`**이** 있거나 `TestCategory`가 `CategoryA`인 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a3617-121">Runs tests which have `UnitTestClass1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA"` | <span data-ttu-id="a3617-122">`FullyQualifiedName`에 `UnitTestClass1`**이 있고** `TestCategory`가 `CategoryA`인 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a3617-122">Runs tests which have `UnitTestClass1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="a3617-123">`UnitTestClass1`을 포함하는 `FullyQualifiedName`**이** 있고 `TestCategory`가 `CategoryA`**이거나** `Priority`가 1인 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a3617-123">Runs tests which have either `FullyQualifiedName` containing `UnitTestClass1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="a3617-124">xUnit</span><span class="sxs-lookup"><span data-stu-id="a3617-124">xUnit</span></span>

```csharp
namespace XUnitNamespace
{
    public class TestClass1
    {
        [Trait("Category", "bvt")]
        [Trait("Priority", "1")]
        [Fact]
        public void foo()
        {
        }

        [Trait("Category", "Nightly")]
        [Trait("Priority", "2")]
        [Fact]
        public void bar()
        {
        }
    }
}
```

| <span data-ttu-id="a3617-125">식</span><span class="sxs-lookup"><span data-stu-id="a3617-125">Expression</span></span> | <span data-ttu-id="a3617-126">결과</span><span class="sxs-lookup"><span data-stu-id="a3617-126">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="a3617-127">`XUnitNamespace.TestClass1.Test1` 테스트를 하나만 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a3617-127">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="a3617-128">`XUnitNamespace.TestClass1.Test1`을 제외한 모든 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a3617-128">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="a3617-129">표시 이름에 `TestClass1`이 포함된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a3617-129">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="a3617-130">코드 예제에서 `Category` 및 `Priority` 키로 정의된 특성은 필터링에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3617-130">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="a3617-131">식</span><span class="sxs-lookup"><span data-stu-id="a3617-131">Expression</span></span> | <span data-ttu-id="a3617-132">결과</span><span class="sxs-lookup"><span data-stu-id="a3617-132">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="a3617-133">`FullyQualifiedName`에 `XUnit`가 포함된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a3617-133">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="a3617-134">`vstest 15.1+`에서 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="a3617-134">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=bvt` | <span data-ttu-id="a3617-135">`[Trait("Category", "bvt")]`가 있는 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a3617-135">Runs tests which have `[Trait("Category", "bvt")]`.</span></span> |

<span data-ttu-id="a3617-136">**조건 연산자 | 및 &amp; 사용**</span><span class="sxs-lookup"><span data-stu-id="a3617-136">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="a3617-137">식</span><span class="sxs-lookup"><span data-stu-id="a3617-137">Expression</span></span> | <span data-ttu-id="a3617-138">결과</span><span class="sxs-lookup"><span data-stu-id="a3617-138">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=Nightly"</code> | <span data-ttu-id="a3617-139">`FullyQualifiedName`에 `TestClass1`이 **있거나**`Category`가 `Nightly`인 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a3617-139">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `Nightly`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=Nightly"` | <span data-ttu-id="a3617-140">`FullyQualifiedName`에 `TestClass1`**이 있고** `Category`가 `Nightly`인 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a3617-140">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `Nightly`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=Nightly)&#124;Priority=1"</code> | <span data-ttu-id="a3617-141">`TestClass1`을 포함하는 `FullyQualifiedName`**이** 있고 `Category`가 `CategoryA`**이거나** `Priority`가 1인 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a3617-141">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |
