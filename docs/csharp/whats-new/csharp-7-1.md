---
title: C# 7.1의 새로운 기능
description: C# 7.1의 새로운 기능에 대한 개요입니다.
ms.date: 08/16/2017
ms.openlocfilehash: 565db102284424f9d8f6fa04ec9c74b52c9da0e6
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34728656"
---
# <a name="whats-new-in-c-71"></a><span data-ttu-id="fb5c9-103">C# 7.1의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="fb5c9-103">What's new in C# 7.1</span></span>

<span data-ttu-id="fb5c9-104">C# 7.1은 C# 언어에 대한 첫 번째 포인트 릴리스입니다.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-104">C# 7.1 is the first point release to the C# language.</span></span> <span data-ttu-id="fb5c9-105">언어에 대한 증가된 릴리스 일정을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-105">It marks an increased release cadence for the language.</span></span> <span data-ttu-id="fb5c9-106">새로운 각 기능이 준비될 때 이상적으로 새 기능을 빨리 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-106">You can use the new features sooner, ideally when each new feature is ready.</span></span> <span data-ttu-id="fb5c9-107">C# 7.1은 지정된 버전의 언어와 일치하도록 컴파일러를 구성하는 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-107">C# 7.1 adds the ability to configure the compiler to match a specified version of the language.</span></span> <span data-ttu-id="fb5c9-108">이를 통해 도구를 업그레이드하는 결정을 언어 버전을 업그레이드하는 결정에서 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-108">That enables you to separate the decision to upgrade tools from the decision to upgrade language versions.</span></span>

<span data-ttu-id="fb5c9-109">C# 7.1은 [언어 버전 선택](../language-reference/configure-language-version.md) 구성 요소, 세 개의 새로운 언어 기능 및 새로운 컴파일러 동작을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-109">C# 7.1 adds the [language version selection](../language-reference/configure-language-version.md) configuration element, three new language features and new compiler behavior.</span></span>

<span data-ttu-id="fb5c9-110">이 릴리스의 새로운 언어 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-110">The new language features in this release are:</span></span>

* [<span data-ttu-id="fb5c9-111">`async` `Main`메서드</span><span class="sxs-lookup"><span data-stu-id="fb5c9-111">`async` `Main` method</span></span>](#async-main)
  - <span data-ttu-id="fb5c9-112">응용 프로그램에 대한 진입점은 `async` 한정자를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-112">The entry point for an application can have the `async` modifier.</span></span>
* [<span data-ttu-id="fb5c9-113">`default` 리터럴 식</span><span class="sxs-lookup"><span data-stu-id="fb5c9-113">`default` literal expressions</span></span>](#default-literal-expressions)
  - <span data-ttu-id="fb5c9-114">대상 형식을 유추할 수 있는 경우 기본 값 식에서 기본 리터럴 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-114">You can use default literal expressions in default value expressions when the target type can be inferred.</span></span>
* [<span data-ttu-id="fb5c9-115">유추된 튜플 요소 이름</span><span class="sxs-lookup"><span data-stu-id="fb5c9-115">Inferred tuple element names</span></span>](#inferred-tuple-element-names)
  - <span data-ttu-id="fb5c9-116">튜플 요소의 이름은 대부분의 경우에 튜플 초기화에서 유추할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-116">The names of tuple elements can be inferred from tuple initialization in many cases.</span></span>

<span data-ttu-id="fb5c9-117">마지막으로 컴파일러에는 [참조 어셈블리 생성](#reference-assembly-generation)을 제어하는 두 가지 옵션 `/refout` 및 `/refonly`가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-117">Finally, the compiler has two options `/refout` and `/refonly` that control [reference assembly generation](#reference-assembly-generation).</span></span>

<span data-ttu-id="fb5c9-118">포인트 릴리스에서 최신 기능을 사용하려면 [컴파일러 언어 버전을 구성](../language-reference/configure-language-version.md)하고 해당 버전을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-118">To use the latest features in a point release, you need to [configure the compiler language version](../language-reference/configure-language-version.md) and select the version.</span></span>

## <a name="async-main"></a><span data-ttu-id="fb5c9-119">비동기 기본</span><span class="sxs-lookup"><span data-stu-id="fb5c9-119">Async main</span></span>

<span data-ttu-id="fb5c9-120">*비동기 기본* 메서드를 통해 `Main` 메서드에서 `await`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-120">An *async main* method enables you to use `await` in your `Main` method.</span></span>
<span data-ttu-id="fb5c9-121">이전에 다음을 작성해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-121">Previously you would need to write:</span></span>

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

<span data-ttu-id="fb5c9-122">이제 다음을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-122">You can now write:</span></span>

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

<span data-ttu-id="fb5c9-123">프로그램이 종료 코드를 반환하지 않는 경우 <xref:System.Threading.Tasks.Task>를 반환하는 `Main` 메서드를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-123">If your program doesn't return an exit code, you can declare a `Main` method that returns a <xref:System.Threading.Tasks.Task>:</span></span>

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

<span data-ttu-id="fb5c9-124">프로그래밍 가이드의 [비동기 기본](../programming-guide/main-and-command-args/index.md) 항목에서 세부 정보에 대해 자세히 읽어볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-124">You can read more about the details in the [async main](../programming-guide/main-and-command-args/index.md) topic in the programming guide.</span></span>

## <a name="default-literal-expressions"></a><span data-ttu-id="fb5c9-125">기본 리터럴 식</span><span class="sxs-lookup"><span data-stu-id="fb5c9-125">Default literal expressions</span></span>

<span data-ttu-id="fb5c9-126">기본 리터럴 식은 기본값 식에 대한 향상된 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-126">Default literal expressions are an enhancement to default value expressions.</span></span>
<span data-ttu-id="fb5c9-127">이러한 식은 변수를 기본 값으로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-127">These expressions initialize a variable to the default value.</span></span> <span data-ttu-id="fb5c9-128">여기서 이전에 다음을 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-128">Where you previously would write:</span></span>

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

<span data-ttu-id="fb5c9-129">이제 초기화의 오른쪽에서 형식을 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-129">You can now omit the type on the right-hand side of the initialization:</span></span>

```csharp
Func<string, bool> whereClause = default;
```

<span data-ttu-id="fb5c9-130">[기본값 식](../programming-guide/statements-expressions-operators/default-value-expressions.md)의 C# 프로그래밍 가이드 항목에서 이 향상된 기능에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-130">You can learn more about this enhancement in the C# Programming Guide topic on [default value expressions](../programming-guide/statements-expressions-operators/default-value-expressions.md).</span></span>

<span data-ttu-id="fb5c9-131">또한 이 향상된 기능은 [기본값 키워드](../language-reference/keywords/default.md)에 대한 일부 구문 분석 규칙을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-131">This enhancement also changes some of the parsing rules for the [default keyword](../language-reference/keywords/default.md).</span></span>

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="fb5c9-132">유추된 튜플 요소 이름</span><span class="sxs-lookup"><span data-stu-id="fb5c9-132">Inferred tuple element names</span></span>

<span data-ttu-id="fb5c9-133">이 기능은 C# 7.0에 도입된 튜플 기능에 대한 작은 향상된 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-133">This feature is a small enhancement to the tuples feature introduced in C# 7.0.</span></span> <span data-ttu-id="fb5c9-134">여러 번 튜플을 초기화할 때 할당의 오른쪽에 사용되는 변수는 튜플 요소에 대해 원하는 이름과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-134">Many times when you initialize a tuple, the variables used for the right side of the assignment are the same as the names you'd like for the tuple elements:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

<span data-ttu-id="fb5c9-135">튜플 요소의 이름은 C# 7.1에서 튜플을 초기화하는 데 사용되는 변수에서 유추할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-135">The names of tuple elements can be inferred from the variables used to initialize the tuple in C# 7.1:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

<span data-ttu-id="fb5c9-136">[튜플](../tuples.md) 항목에서 이 기능에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-136">You can learn more about this feature in the [Tuples](../tuples.md) topic.</span></span>

## <a name="reference-assembly-generation"></a><span data-ttu-id="fb5c9-137">참조 어셈블리 생성</span><span class="sxs-lookup"><span data-stu-id="fb5c9-137">Reference assembly generation</span></span>

<span data-ttu-id="fb5c9-138">*참조 전용 어셈블리*인 [/refout](../language-reference/compiler-options/refout-compiler-option.md) 및 [/refonly](../language-reference/compiler-options/refonly-compiler-option.md)를 생성하는 두 개의 새로운 컴파일러 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-138">There are two new compiler options that generate *reference-only assemblies*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) and [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span></span>
<span data-ttu-id="fb5c9-139">링크된 항목에서는 이러한 옵션과 참조 어셈블리를 보다 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-139">The linked topics explain these options and reference assemblies in more detail.</span></span>
