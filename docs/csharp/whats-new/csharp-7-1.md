---
title: C# 7.1의 새로운 기능
description: C# 7.1의 새로운 기능에 대한 개요입니다.
ms.date: 08/16/2017
ms.openlocfilehash: 00baec45d7582d3ac12c7b0865241f5cd8159246
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="whats-new-in-c-71"></a><span data-ttu-id="d2762-103">C# 7.1의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="d2762-103">What's new in C# 7.1</span></span>

<span data-ttu-id="d2762-104">C# 7.1은 C# 언어에 대한 첫 번째 포인트 릴리스입니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-104">C# 7.1 is the first point release to the C# language.</span></span> <span data-ttu-id="d2762-105">언어에 대한 증가된 릴리스 일정을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-105">It marks an increased release cadence for the language.</span></span> <span data-ttu-id="d2762-106">새로운 각 기능이 준비될 때 이상적으로 새 기능을 빨리 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-106">You can use the new features sooner, ideally when each new feature is ready.</span></span> <span data-ttu-id="d2762-107">C# 7.1은 지정된 버전의 언어와 일치하도록 컴파일러를 구성하는 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-107">C# 7.1 adds the ability to configure the compiler to match a specified version of the language.</span></span> <span data-ttu-id="d2762-108">이를 통해 도구를 업그레이드하는 결정을 언어 버전을 업그레이드하는 결정에서 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-108">That enables you to separate the decision to upgrade tools from the decision to upgrade language versions.</span></span>

<span data-ttu-id="d2762-109">C# 7.1은 [언어 버전 선택](#language-version-selection) 구성 요소, 세 개의 새로운 언어 기능 및 새로운 컴파일러 동작을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-109">C# 7.1 adds the [language version selection](#language-version-selection) configuration element, three new language features and new compiler behavior.</span></span>

<span data-ttu-id="d2762-110">이 릴리스의 새로운 언어 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-110">The new language features in this release are:</span></span>

* [<span data-ttu-id="d2762-111">`async` `Main`메서드</span><span class="sxs-lookup"><span data-stu-id="d2762-111">`async` `Main` method</span></span>](#async-main)
  - <span data-ttu-id="d2762-112">응용 프로그램에 대한 진입점은 `async` 한정자를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-112">The entry point for an application can have the `async` modifier.</span></span>
* [<span data-ttu-id="d2762-113">`default` 리터럴 식</span><span class="sxs-lookup"><span data-stu-id="d2762-113">`default` literal expressions</span></span>](#default-literal-expressions)
  - <span data-ttu-id="d2762-114">대상 형식을 유추할 수 있는 경우 기본 값 식에서 기본 리터럴 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-114">You can use default literal expressions in default value expressions when the target type can be inferred.</span></span>
* [<span data-ttu-id="d2762-115">유추된 튜플 요소 이름</span><span class="sxs-lookup"><span data-stu-id="d2762-115">Inferred tuple element names</span></span>](#inferred-tuple-element-names)
  - <span data-ttu-id="d2762-116">튜플 요소의 이름은 대부분의 경우에 튜플 초기화에서 유추할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-116">The names of tuple elements can be inferred from tuple initialization in many cases.</span></span>

<span data-ttu-id="d2762-117">마지막으로 컴파일러에는 [참조 어셈블리 생성](#reference-assembly-generation)을 제어하는 두 가지 옵션 `/refout` 및 `/refonly`가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-117">Finally, the compiler has two options `/refout` and `/refonly` that control [reference assembly generation](#reference-assembly-generation).</span></span>

## <a name="language-version-selection"></a><span data-ttu-id="d2762-118">언어 버전 선택</span><span class="sxs-lookup"><span data-stu-id="d2762-118">Language version selection</span></span>

<span data-ttu-id="d2762-119">C# 컴파일러는 Visual Studio 2017 버전 15.3 또는 .NET Core SDK 2.0부터 C# 7.1을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-119">The C# compiler supports C# 7.1 starting with Visual Studio 2017 version 15.3, or the .NET Core SDK 2.0.</span></span> <span data-ttu-id="d2762-120">그러나 7.1 기능은 기본적으로 꺼져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-120">However, the 7.1 features are turned off by default.</span></span> <span data-ttu-id="d2762-121">7.1 기능을 활성화하려면 프로젝트에 대한 언어 버전 설정을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-121">To enable the 7.1 features, you need to change the language version setting for your project.</span></span>

<span data-ttu-id="d2762-122">Visual Studio의 솔루션 탐색기에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-122">In Visual Studio, right-click on the project node in Solution Explorer and select **Properties**.</span></span> <span data-ttu-id="d2762-123">**빌드** 탭을 선택하고 **고급** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-123">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="d2762-124">드롭다운 목록에서 **C# 최신 부 버전(최신 버전)** 또는 다음 그림과 같이 특정 버전 **C# 7.1**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-124">In the dropdown, select **C# latest minor version (latest)**, or the specific version **C# 7.1** as shown in the image following.</span></span> <span data-ttu-id="d2762-125">`latest` 값은 현재 컴퓨터에 최신 부 버전을 사용하려는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-125">The `latest` value means you want to use the latest minor version on the current machine.</span></span> <span data-ttu-id="d2762-126">`C# 7.1`은 최신 부 버전이 출시된 후에도 C# 7.1을 사용하려는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-126">The `C# 7.1` means that you want to use C# 7.1, even after newer minor versions are released.</span></span>

![언어 버전 설정](./media/csharp-7-1/advanced-build-settings.png)

<span data-ttu-id="d2762-128">또는 "csproj" 파일을 편집하고 다음 줄을 추가하거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-128">Alternatively, you can edit the "csproj" file and add or modify the following lines:</span></span>

```xml
<PropertyGroup>
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

> [!NOTE]
> <span data-ttu-id="d2762-129">Visual Studio IDE를 사용하여 csproj 파일을 업데이트하는 경우 IDE는 각 빌드 구성에 대한 별도 노드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-129">If you use the Visual Studio IDE to update your csproj files, the IDE creates separate nodes for each build configuration.</span></span> <span data-ttu-id="d2762-130">일반적으로 모든 빌드 구성에서 값을 동일하게 설정하지만 각 빌드 구성에 대해 명시적으로 설정하거나 이 설정을 수정하는 경우 "모든 구성"을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-130">You'll typically set the value the same in all build configurations, but you need to set it explicitly for each build configuration, or select "All Configurations" when you modify this setting.</span></span> <span data-ttu-id="d2762-131">csproj 파일에 다음이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-131">You'll see the following in your csproj file:</span></span>

```xml
<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>

<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="d2762-132">`LangVersion` 요소에 대한 올바른 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-132">Valid settings for the `LangVersion` element are:</span></span>

* `ISO-1`
* `ISO-2`
* `3`
* `4`
* `5`
* `6`
* `7`
* `7.1`
* `default`
* `latest`

<span data-ttu-id="d2762-133">특수한 문자열 `default` 및 `latest`는 각각 빌드 컴퓨터에 설치된 최신 주 및 부 언어 버전을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-133">The special strings `default` and `latest` resolve to the latest major and minor language versions installed on the build machine, respectively.</span></span>

<span data-ttu-id="d2762-134">이 설정은 개발 환경에서 SDK 및 도구의 새 버전 설치를 프로젝트의 새 언어 기능을 통합하는 선택에서 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-134">This setting decouples installing new versions of the SDK and tools in your development environment from choosing to incorporate new language features in a project.</span></span> <span data-ttu-id="d2762-135">빌드 컴퓨터에 최신 SDK 및 도구를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-135">You can install the latest SDK and tools on your build machine.</span></span> <span data-ttu-id="d2762-136">각 프로젝트는 해당 빌드에 대해 특정 버전의 언어를 사용하도록 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-136">Each project can be configured to use a specific version of the language for its build.</span></span>

## <a name="async-main"></a><span data-ttu-id="d2762-137">비동기 기본</span><span class="sxs-lookup"><span data-stu-id="d2762-137">Async main</span></span>

<span data-ttu-id="d2762-138">*비동기 기본* 메서드를 통해 `Main` 메서드에서 `await`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-138">An *async main* method enables you to use `await` in your `Main` method.</span></span>
<span data-ttu-id="d2762-139">이전에 다음을 작성해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-139">Previously you would need to write:</span></span>

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

<span data-ttu-id="d2762-140">이제 다음을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-140">You can now write:</span></span>

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

<span data-ttu-id="d2762-141">프로그램이 종료 코드를 반환하지 않는 경우 <xref:System.Threading.Tasks.Task>를 반환하는 `Main` 메서드를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-141">If your program doesn't return an exit code, you can declare a `Main` method that returns a <xref:System.Threading.Tasks.Task>:</span></span>

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

<span data-ttu-id="d2762-142">프로그래밍 가이드의 [비동기 기본](../programming-guide/main-and-command-args/index.md) 항목에서 세부 정보에 대해 자세히 읽어볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-142">You can read more about the details in the [async main](../programming-guide/main-and-command-args/index.md) topic in the programming guide.</span></span>

## <a name="default-literal-expressions"></a><span data-ttu-id="d2762-143">기본 리터럴 식</span><span class="sxs-lookup"><span data-stu-id="d2762-143">Default literal expressions</span></span>

<span data-ttu-id="d2762-144">기본 리터럴 식은 기본값 식에 대한 향상된 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-144">Default literal expressions are an enhancement to default value expressions.</span></span>
<span data-ttu-id="d2762-145">이러한 식은 변수를 기본 값으로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-145">These expressions initialize a variable to the default value.</span></span> <span data-ttu-id="d2762-146">여기서 이전에 다음을 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-146">Where you previously would write:</span></span>

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

<span data-ttu-id="d2762-147">이제 초기화의 오른쪽에서 형식을 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-147">You can now omit the type on the right-hand side of the initialization:</span></span>

```csharp
Func<string, bool> whereClause = default;
```

<span data-ttu-id="d2762-148">[기본값 식](../programming-guide/statements-expressions-operators/default-value-expressions.md)의 C# 프로그래밍 가이드 항목에서 이 향상된 기능에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-148">You can learn more about this enhancement in the C# Programming Guide topic on [default value expressions](../programming-guide/statements-expressions-operators/default-value-expressions.md).</span></span>

<span data-ttu-id="d2762-149">또한 이 향상된 기능은 [기본값 키워드](../language-reference/keywords/default.md)에 대한 일부 구문 분석 규칙을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-149">This enhancement also changes some of the parsing rules for the [default keyword](../language-reference/keywords/default.md).</span></span>

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="d2762-150">유추된 튜플 요소 이름</span><span class="sxs-lookup"><span data-stu-id="d2762-150">Inferred tuple element names</span></span>

<span data-ttu-id="d2762-151">이 기능은 C# 7.0에 도입된 튜플 기능에 대한 작은 향상된 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-151">This feature is a small enhancement to the tuples feature introduced in C# 7.0.</span></span> <span data-ttu-id="d2762-152">여러 번 튜플을 초기화할 때 할당의 오른쪽에 사용되는 변수는 튜플 요소에 대해 원하는 이름과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-152">Many times when you initialize a tuple, the variables used for the right side of the assignment are the same as the names you'd like for the tuple elements:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

<span data-ttu-id="d2762-153">튜플 요소의 이름은 C# 7.1에서 튜플을 초기화하는 데 사용되는 변수에서 유추할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-153">The names of tuple elements can be inferred from the variables used to initialize the tuple in C# 7.1:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

<span data-ttu-id="d2762-154">[튜플](../tuples.md) 항목에서 이 기능에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-154">You can learn more about this feature in the [Tuples](../tuples.md) topic.</span></span>

## <a name="reference-assembly-generation"></a><span data-ttu-id="d2762-155">참조 어셈블리 생성</span><span class="sxs-lookup"><span data-stu-id="d2762-155">Reference assembly generation</span></span>

<span data-ttu-id="d2762-156">*참조 전용 어셈블리*인 [/refout](../language-reference/compiler-options/refout-compiler-option.md) 및 [/refonly](../language-reference/compiler-options/refonly-compiler-option.md)를 생성하는 두 개의 새로운 컴파일러 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-156">There are two new compiler options that generate *reference-only assemblies*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) and [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span></span>
<span data-ttu-id="d2762-157">링크된 항목에서는 이러한 옵션과 참조 어셈블리를 보다 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d2762-157">The linked topics explain these options and reference assemblies in more detail.</span></span>
