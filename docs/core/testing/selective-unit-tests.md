---
title: "선택적 단위 테스트 실행"
description: "필터 식을 사용하여 dotnet 명령으로 선택적 단위 테스트를 실행하는 방법을 보여 줍니다."
keywords: ".NET, .NET Core, 단위 테스트, 선택적 테스트"
author: smadala
ms.author: mairaw
ms.date: 03/22/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 13d01272-bbf8-456c-a97a-560001d1a7f2
ms.openlocfilehash: af832d04d2cba530a93710a90701ab119a66deef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="f4be9-104">선택적 단위 테스트 실행</span><span class="sxs-lookup"><span data-stu-id="f4be9-104">Running selective unit tests</span></span>

<span data-ttu-id="f4be9-105">다음 예제에서는 `dotnet test`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f4be9-105">The following examples use `dotnet test`.</span></span> <span data-ttu-id="f4be9-106">`vstest.console.exe`를 사용하는 경우 `--filter `를 `--testcasefilter:`로 바꾸세요.</span><span class="sxs-lookup"><span data-stu-id="f4be9-106">If you're using `vstest.console.exe`, replace `--filter ` with `--testcasefilter:`.</span></span>

## <a name="mstest"></a><span data-ttu-id="f4be9-107">MSTest</span><span class="sxs-lookup"><span data-stu-id="f4be9-107">MSTest</span></span>

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

| <span data-ttu-id="f4be9-108">식</span><span class="sxs-lookup"><span data-stu-id="f4be9-108">Expression</span></span> | <span data-ttu-id="f4be9-109">결과</span><span class="sxs-lookup"><span data-stu-id="f4be9-109">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="f4be9-110">`FullyQualifiedName`에 `Method`가 포함된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f4be9-110">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="f4be9-111">`vstest 15.1+`에서 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="f4be9-111">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="f4be9-112">이름에 `TestMethod1`이 포함된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f4be9-112">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTestClass1` | <span data-ttu-id="f4be9-113">클래스 `MSTestNamespace.UnitTestClass1`에 속하는 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f4be9-113">Runs tests which are in class `MSTestNamespace.UnitTestClass1`.</span></span><br><span data-ttu-id="f4be9-114">**참고:** `ClassName` 값에는 네임스페이스가 있어야 하므로, `ClassName=UnitTestClass1`이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f4be9-114">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTestClass1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTestClass1.TestMethod1` | <span data-ttu-id="f4be9-115">`MSTestNamespace.UnitTestClass1.TestMethod1`을 제외한 모든 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f4be9-115">Runs all tests except `MSTestNamespace.UnitTestClass1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="f4be9-116">`[TestCategory("CategoryA")]`로 주석이 추가된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f4be9-116">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=3` | <span data-ttu-id="f4be9-117">`[Priority(3)]`로 주석이 추가된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f4be9-117">Runs tests which are annotated with `[Priority(3)]`.</span></span><br><span data-ttu-id="f4be9-118">**참고:** `Priority~3`는 문자열이 아니므로 잘못된 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f4be9-118">**Note:** `Priority~3` is an invalid value, as it isn't a string.</span></span> |

<span data-ttu-id="f4be9-119">**조건 연산자 | 및 &amp; 사용**</span><span class="sxs-lookup"><span data-stu-id="f4be9-119">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="f4be9-120">식</span><span class="sxs-lookup"><span data-stu-id="f4be9-120">Expression</span></span> | <span data-ttu-id="f4be9-121">결과</span><span class="sxs-lookup"><span data-stu-id="f4be9-121">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTestClass1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="f4be9-122">`FullyQualifiedName`에 `UnitTestClass1`이 **있거나** `TestCategory`가 `CategoryA`인 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f4be9-122">Runs tests which have `UnitTestClass1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA"` | <span data-ttu-id="f4be9-123">`FullyQualifiedName`에 `UnitTestClass1`**이 있고** `TestCategory`가 `CategoryA`인 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f4be9-123">Runs tests which have `UnitTestClass1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="f4be9-124">`UnitTestClass1`을 포함하는 `FullyQualifiedName`**이 있고**`TestCategory`가 `CategoryA`**이거나** `Priority`가 1인 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f4be9-124">Runs tests which have either `FullyQualifiedName` containing `UnitTestClass1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="f4be9-125">xUnit</span><span class="sxs-lookup"><span data-stu-id="f4be9-125">xUnit</span></span>

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

| <span data-ttu-id="f4be9-126">식</span><span class="sxs-lookup"><span data-stu-id="f4be9-126">Expression</span></span> | <span data-ttu-id="f4be9-127">결과</span><span class="sxs-lookup"><span data-stu-id="f4be9-127">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="f4be9-128">`XUnitNamespace.TestClass1.Test1` 테스트를 하나만 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f4be9-128">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="f4be9-129">`XUnitNamespace.TestClass1.Test1`을 제외한 모든 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f4be9-129">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="f4be9-130">표시 이름에 `TestClass1`이 포함된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f4be9-130">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="f4be9-131">코드 예제에서 `Category` 및 `Priority` 키로 정의된 특성은 필터링에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4be9-131">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="f4be9-132">식</span><span class="sxs-lookup"><span data-stu-id="f4be9-132">Expression</span></span> | <span data-ttu-id="f4be9-133">결과</span><span class="sxs-lookup"><span data-stu-id="f4be9-133">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="f4be9-134">`FullyQualifiedName`에 `XUnit`가 포함된 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f4be9-134">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="f4be9-135">`vstest 15.1+`에서 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="f4be9-135">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=bvt` | <span data-ttu-id="f4be9-136">`[Trait("Category", "bvt")]`가 있는 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f4be9-136">Runs tests which have `[Trait("Category", "bvt")]`.</span></span> |

<span data-ttu-id="f4be9-137">**조건 연산자 | 및 &amp; 사용**</span><span class="sxs-lookup"><span data-stu-id="f4be9-137">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="f4be9-138">식</span><span class="sxs-lookup"><span data-stu-id="f4be9-138">Expression</span></span> | <span data-ttu-id="f4be9-139">결과</span><span class="sxs-lookup"><span data-stu-id="f4be9-139">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=Nightly"</code> | <span data-ttu-id="f4be9-140">`FullyQualifiedName`에 `TestClass1`이 **있거나**`Category`가 `Nightly`인 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f4be9-140">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `Nightly`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=Nightly"` | <span data-ttu-id="f4be9-141">`FullyQualifiedName`에 `TestClass1`**이 있고** `Category`가 `Nightly`인 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f4be9-141">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `Nightly`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=Nightly)&#124;Priority=1"</code> | <span data-ttu-id="f4be9-142">`TestClass1`을 포함하는 `FullyQualifiedName`**이 있고**`Category`가 `CategoryA`**이거나** `Priority`가 1인 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f4be9-142">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |
