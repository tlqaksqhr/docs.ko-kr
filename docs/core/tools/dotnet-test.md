---
title: "dotnet test 명령 - .NET Core CLI"
description: "dotnet test 명령은 지정된 프로젝트에서 단위 테스트를 실행하는 데 사용됩니다."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: 55329bed71be21a787d6e77d8c0ea67d607676b8
ms.contentlocale: ko-kr
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-test"></a><span data-ttu-id="f95c5-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="f95c5-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="f95c5-104">이름</span><span class="sxs-lookup"><span data-stu-id="f95c5-104">Name</span></span>

<span data-ttu-id="f95c5-105">`dotnet test` - 단위 테스트를 실행하는 데 사용하는 .NET 테스트 드라이버입니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f95c5-106">개요</span><span class="sxs-lookup"><span data-stu-id="f95c5-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="f95c5-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="f95c5-107">.NET Core 2.x</span></span>](#tab/netcore2x)


```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f95c5-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f95c5-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="f95c5-109">설명</span><span class="sxs-lookup"><span data-stu-id="f95c5-109">Description</span></span>

<span data-ttu-id="f95c5-110">`dotnet test` 명령은 지정된 프로젝트에서 단위 테스트를 실행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-110">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="f95c5-111">단위 테스트는 단위 테스트 프레임워크(예: MSTest, NUnit 또는 xUnit) 및 단위 테스트 프레임워크에 대한 dotnet Test Runner에 종속되어 있는 콘솔 응용 프로그램 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-111">Unit tests are console application projects that have dependencies on the unit test framework (for example, MSTest, NUnit, or xUnit) and the dotnet test runner for the unit testing framework.</span></span> <span data-ttu-id="f95c5-112">이러한 프로젝트는 NuGet 패키지로 패키지되고 프로젝트에 대한 일반 종속성으로 복원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-112">These are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="f95c5-113">테스트 프로젝트에서는 Test Runner도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-113">Test projects also must specify the test runner.</span></span> <span data-ttu-id="f95c5-114">다음의 예제 프로젝트 파일에서 볼 수 있듯이 일반적인 `<PackageReference>` 요소를 사용하여 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-114">This is specified using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

<span data-ttu-id="f95c5-115">[!code-xml[XUnit 기본 템플릿](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]</span><span class="sxs-lookup"><span data-stu-id="f95c5-115">[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]</span></span>

## <a name="arguments"></a><span data-ttu-id="f95c5-116">인수</span><span class="sxs-lookup"><span data-stu-id="f95c5-116">Arguments</span></span>

`PROJECT`

<span data-ttu-id="f95c5-117">테스트 프로젝트에 대한 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-117">Specifies a path to the test project.</span></span> <span data-ttu-id="f95c5-118">생략하면 현재 디렉터리로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-118">If omitted, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="f95c5-119">옵션</span><span class="sxs-lookup"><span data-stu-id="f95c5-119">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="f95c5-120">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="f95c5-120">.NET Core 2.x</span></span>](#tab/netcore2x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="f95c5-121">테스트 실행에 지정된 경로에서 사용자 지정 테스트 어댑터를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-121">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="f95c5-122">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-122">Defines the build configuration.</span></span> <span data-ttu-id="f95c5-123">기본값은 `Debug`이지만 프로젝트의 구성으로 이 기본 SDK 설정이 재정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-123">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="f95c5-124">테스트 실행에 대한 데이터 수집기를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-124">Enables data collector for the test run.</span></span> <span data-ttu-id="f95c5-125">자세한 내용은 [테스트 실행 모니터링 및 분석](https://aka.ms/vstest-collect)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f95c5-125">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="f95c5-126">테스트 플랫폼에 대한 진단 모드를 사용하도록 설정하고 지정된 파일에 진단 메시지를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-126">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="f95c5-127">특정 [프레임워크](../../standard/frameworks.md)에 대한 테스트 이진 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-127">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="f95c5-128">지정된 식을 사용하여 현재 프로젝트의 테스트를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-128">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="f95c5-129">자세한 내용은 [필터 옵션 세부 정보](#filter-option-details) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f95c5-129">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="f95c5-130">선택적 단위 테스트 필터링을 사용하는 방법에 대한 추가 정보 및 예제는 [선택적 단위 테스트 실행](../testing/selective-unit-tests.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f95c5-130">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="f95c5-131">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-131">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="f95c5-132">테스트 결과에 대해 로거를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-132">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="f95c5-133">텍스트 프로젝트를 실행하기 전에 빌드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-133">Does not build the test project prior to running it.</span></span>

`--no-restore`

<span data-ttu-id="f95c5-134">명령을 실행할 때 암시적 복원을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-134">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="f95c5-135">실행할 이진 파일을 찾을 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-135">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="f95c5-136">테스트 결과가 배치될 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-136">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="f95c5-137">지정된 디렉터리가 없을 경우 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-137">The specified directory will be created if it doesn't exist.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="f95c5-138">테스트를 실행할 때 사용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-138">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="f95c5-139">현재 프로젝트에서 검색된 테스트를 모두 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-139">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="f95c5-140">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-140">Sets the verbosity level of the command.</span></span> <span data-ttu-id="f95c5-141">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-141">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f95c5-142">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f95c5-142">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="f95c5-143">테스트 실행에 지정된 경로에서 사용자 지정 테스트 어댑터를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-143">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="f95c5-144">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-144">Defines the build configuration.</span></span> <span data-ttu-id="f95c5-145">기본값은 `Debug`이지만 프로젝트의 구성으로 이 기본 SDK 설정이 재정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-145">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="f95c5-146">테스트 플랫폼에 대한 진단 모드를 사용하도록 설정하고 지정된 파일에 진단 메시지를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-146">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="f95c5-147">특정 [프레임워크](../../standard/frameworks.md)에 대한 테스트 이진 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-147">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="f95c5-148">지정된 식을 사용하여 현재 프로젝트의 테스트를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-148">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="f95c5-149">자세한 내용은 [필터 옵션 세부 정보](#filter-option-details) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f95c5-149">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="f95c5-150">선택적 단위 테스트 필터링을 사용하는 방법에 대한 추가 정보 및 예제는 [선택적 단위 테스트 실행](../testing/selective-unit-tests.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f95c5-150">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="f95c5-151">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-151">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="f95c5-152">테스트 결과에 대해 로거를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-152">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="f95c5-153">텍스트 프로젝트를 실행하기 전에 빌드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-153">Does not build the test project prior to running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="f95c5-154">실행할 이진 파일을 찾을 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-154">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="f95c5-155">테스트를 실행할 때 사용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-155">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="f95c5-156">현재 프로젝트에서 검색된 테스트를 모두 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-156">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="f95c5-157">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-157">Sets the verbosity level of the command.</span></span> <span data-ttu-id="f95c5-158">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-158">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="f95c5-159">예제</span><span class="sxs-lookup"><span data-stu-id="f95c5-159">Examples</span></span>

<span data-ttu-id="f95c5-160">현재 디렉터리에 있는 프로젝트에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-160">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="f95c5-161">`test1` 프로젝트에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-161">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

## <a name="filter-option-details"></a><span data-ttu-id="f95c5-162">필터 옵션 세부 정보</span><span class="sxs-lookup"><span data-stu-id="f95c5-162">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="f95c5-163">`<Expression>`에 `<property><operator><value>[|&<Expression>]` 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-163">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="f95c5-164">`<property>`은(는) `Test Case`의 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-164">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="f95c5-165">다음은 인기 있는 단위 테스트 프레임 워크에서 지원되는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-165">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="f95c5-166">테스트 프레임워크</span><span class="sxs-lookup"><span data-stu-id="f95c5-166">Test Framework</span></span> | <span data-ttu-id="f95c5-167">지원되는 속성</span><span class="sxs-lookup"><span data-stu-id="f95c5-167">Supported properties</span></span>                                                                                      |
| :------------: | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="f95c5-168">MSTest</span><span class="sxs-lookup"><span data-stu-id="f95c5-168">MSTest</span></span>         | <ul><li><span data-ttu-id="f95c5-169">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="f95c5-169">FullyQualifiedName</span></span></li><li><span data-ttu-id="f95c5-170">이름</span><span class="sxs-lookup"><span data-stu-id="f95c5-170">Name</span></span></li><li><span data-ttu-id="f95c5-171">ClassName</span><span class="sxs-lookup"><span data-stu-id="f95c5-171">ClassName</span></span></li><li><span data-ttu-id="f95c5-172">우선 순위</span><span class="sxs-lookup"><span data-stu-id="f95c5-172">Priority</span></span></li><li><span data-ttu-id="f95c5-173">TestCategory</span><span class="sxs-lookup"><span data-stu-id="f95c5-173">TestCategory</span></span></li></ul> |
| <span data-ttu-id="f95c5-174">Xunit</span><span class="sxs-lookup"><span data-stu-id="f95c5-174">Xunit</span></span>          | <ul><li><span data-ttu-id="f95c5-175">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="f95c5-175">FullyQualifiedName</span></span></li><li><span data-ttu-id="f95c5-176">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f95c5-176">DisplayName</span></span></li><li><span data-ttu-id="f95c5-177">특성</span><span class="sxs-lookup"><span data-stu-id="f95c5-177">Traits</span></span></li></ul>                                   |

<span data-ttu-id="f95c5-178">`<operator>`은(는) 속성과 값 사이의 관계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-178">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="f95c5-179">연산자</span><span class="sxs-lookup"><span data-stu-id="f95c5-179">Operator</span></span> | <span data-ttu-id="f95c5-180">함수</span><span class="sxs-lookup"><span data-stu-id="f95c5-180">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="f95c5-181">정확하게 일치</span><span class="sxs-lookup"><span data-stu-id="f95c5-181">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="f95c5-182">정확하게 일치하지 않음</span><span class="sxs-lookup"><span data-stu-id="f95c5-182">Not exact match</span></span> |
| `~`      | <span data-ttu-id="f95c5-183">포함</span><span class="sxs-lookup"><span data-stu-id="f95c5-183">Contains</span></span>        |

<span data-ttu-id="f95c5-184">`<value>`는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-184">`<value>` is a string.</span></span> <span data-ttu-id="f95c5-185">모든 조회는 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-185">All the lookups are case insensitive.</span></span>

<span data-ttu-id="f95c5-186">`<operator>`이(가) 없는 식은 `FullyQualifiedName` 속성의 `contains`(으)로 자동으로 간주됩니다(예를 들어 `dotnet test --filter xyz`과(와) `dotnet test --filter FullyQualifiedName~xyz`이(가) 동일).</span><span class="sxs-lookup"><span data-stu-id="f95c5-186">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="f95c5-187">식은 조건부 연산자와 조인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f95c5-187">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="f95c5-188">연산자</span><span class="sxs-lookup"><span data-stu-id="f95c5-188">Operator</span></span> | <span data-ttu-id="f95c5-189">함수</span><span class="sxs-lookup"><span data-stu-id="f95c5-189">Function</span></span> |
| :------: | :------: |
| <code>&#124;</code>      | <span data-ttu-id="f95c5-190">또는</span><span class="sxs-lookup"><span data-stu-id="f95c5-190">OR</span></span>       |
| `&`      | <span data-ttu-id="f95c5-191">AND</span><span class="sxs-lookup"><span data-stu-id="f95c5-191">AND</span></span>      |

<span data-ttu-id="f95c5-192">조건부 연산자를 사용 하는 경우 식을 괄호로 묶을 수 있습니다 (예를 들어 `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="f95c5-192">You can enclose expressions in paranthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="f95c5-193">선택적 단위 테스트 필터링을 사용하는 방법에 대한 추가 정보 및 예제는 [선택적 단위 테스트 실행](../testing/selective-unit-tests.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f95c5-193">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f95c5-194">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f95c5-194">See also</span></span>

 <span data-ttu-id="f95c5-195">[프레임워크 및 대상](../../standard/frameworks.md) </span><span class="sxs-lookup"><span data-stu-id="f95c5-195">[Frameworks and Targets](../../standard/frameworks.md) </span></span>  
 [<span data-ttu-id="f95c5-196">.NET Core RID(런타임 식별자) 카탈로그</span><span class="sxs-lookup"><span data-stu-id="f95c5-196">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)

