---
title: dotnet test 명령 - .NET Core CLI
description: dotnet test 명령은 지정된 프로젝트에서 단위 테스트를 실행하는 데 사용됩니다.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.openlocfilehash: d85ca0bf75baa94e63358bd66d11bc29e8b9284b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-test"></a><span data-ttu-id="7e493-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="7e493-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="7e493-104">name</span><span class="sxs-lookup"><span data-stu-id="7e493-104">Name</span></span>

<span data-ttu-id="7e493-105">`dotnet test` - 단위 테스트를 실행하는 데 사용하는 .NET 테스트 드라이버입니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="7e493-106">개요</span><span class="sxs-lookup"><span data-stu-id="7e493-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7e493-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7e493-107">.NET Core 2.x</span></span>](#tab/netcore2x)


```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7e493-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7e493-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="7e493-109">설명</span><span class="sxs-lookup"><span data-stu-id="7e493-109">Description</span></span>

<span data-ttu-id="7e493-110">`dotnet test` 명령은 지정된 프로젝트에서 단위 테스트를 실행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-110">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="7e493-111">`dotnet test` 명령은 프로젝트에 대해 지정된 테스트 러너 콘솔 응용 프로그램을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-111">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="7e493-112">테스트 러너는 단위 테스트 프레임워크(예: MSTest, NUnit 또는 xUnit)에 대해 정의된 테스트를 실행하고 각 테스트의 성공 여부를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-112">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="7e493-113">테스트 러너와 단위 테스트 라이브러리는 NuGet 패키지로 패키지되고 프로젝트에 대한 일반적인 종속성으로 복원됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-113">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="7e493-114">테스트 프로젝트는 다음 샘플 프로젝트 파일에서 볼 수 있듯이 일반적인 `<PackageReference>` 요소를 사용하여 테스트 러너를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-114">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="7e493-115">인수</span><span class="sxs-lookup"><span data-stu-id="7e493-115">Arguments</span></span>

`PROJECT`

<span data-ttu-id="7e493-116">테스트 프로젝트에 대한 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-116">Specifies a path to the test project.</span></span> <span data-ttu-id="7e493-117">생략하면 현재 디렉터리로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-117">If omitted, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="7e493-118">옵션</span><span class="sxs-lookup"><span data-stu-id="7e493-118">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7e493-119">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7e493-119">.NET Core 2.x</span></span>](#tab/netcore2x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="7e493-120">테스트 실행에 지정된 경로에서 사용자 지정 테스트 어댑터를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-120">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="7e493-121">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-121">Defines the build configuration.</span></span> <span data-ttu-id="7e493-122">기본값은 `Debug`이지만 프로젝트의 구성으로 이 기본 SDK 설정이 재정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-122">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="7e493-123">테스트 실행에 대한 데이터 수집기를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-123">Enables data collector for the test run.</span></span> <span data-ttu-id="7e493-124">자세한 내용은 [테스트 실행 모니터링 및 분석](https://aka.ms/vstest-collect)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7e493-124">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="7e493-125">테스트 플랫폼에 대한 진단 모드를 사용하도록 설정하고 지정된 파일에 진단 메시지를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-125">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="7e493-126">특정 [프레임워크](../../standard/frameworks.md)에 대한 테스트 이진 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-126">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="7e493-127">지정된 식을 사용하여 현재 프로젝트의 테스트를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-127">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="7e493-128">자세한 내용은 [필터 옵션 세부 정보](#filter-option-details) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7e493-128">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="7e493-129">선택적 단위 테스트 필터링을 사용하는 방법에 대한 추가 정보 및 예제는 [선택적 단위 테스트 실행](../testing/selective-unit-tests.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7e493-129">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="7e493-130">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-130">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="7e493-131">테스트 결과에 대해 로거를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-131">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="7e493-132">텍스트 프로젝트를 실행하기 전에 빌드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-132">Does not build the test project prior to running it.</span></span>

`--no-restore`

<span data-ttu-id="7e493-133">명령을 실행할 때 암시적 복원을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-133">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="7e493-134">실행할 이진 파일을 찾을 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-134">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="7e493-135">테스트 결과가 배치될 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-135">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="7e493-136">지정된 디렉터리가 없을 경우 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-136">The specified directory will be created if it doesn't exist.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="7e493-137">테스트를 실행할 때 사용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-137">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="7e493-138">현재 프로젝트에서 검색된 테스트를 모두 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-138">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="7e493-139">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-139">Sets the verbosity level of the command.</span></span> <span data-ttu-id="7e493-140">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-140">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7e493-141">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7e493-141">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="7e493-142">테스트 실행에 지정된 경로에서 사용자 지정 테스트 어댑터를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-142">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="7e493-143">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-143">Defines the build configuration.</span></span> <span data-ttu-id="7e493-144">기본값은 `Debug`이지만 프로젝트의 구성으로 이 기본 SDK 설정이 재정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-144">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="7e493-145">테스트 플랫폼에 대한 진단 모드를 사용하도록 설정하고 지정된 파일에 진단 메시지를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-145">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="7e493-146">특정 [프레임워크](../../standard/frameworks.md)에 대한 테스트 이진 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-146">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="7e493-147">지정된 식을 사용하여 현재 프로젝트의 테스트를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-147">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="7e493-148">자세한 내용은 [필터 옵션 세부 정보](#filter-option-details) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7e493-148">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="7e493-149">선택적 단위 테스트 필터링을 사용하는 방법에 대한 추가 정보 및 예제는 [선택적 단위 테스트 실행](../testing/selective-unit-tests.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7e493-149">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="7e493-150">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-150">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="7e493-151">테스트 결과에 대해 로거를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-151">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="7e493-152">텍스트 프로젝트를 실행하기 전에 빌드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-152">Does not build the test project prior to running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="7e493-153">실행할 이진 파일을 찾을 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-153">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="7e493-154">테스트를 실행할 때 사용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-154">Settings to use when running tests.</span></span>

`-t|--list-tests`

<span data-ttu-id="7e493-155">현재 프로젝트에서 검색된 테스트를 모두 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-155">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="7e493-156">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-156">Sets the verbosity level of the command.</span></span> <span data-ttu-id="7e493-157">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-157">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="7e493-158">예제</span><span class="sxs-lookup"><span data-stu-id="7e493-158">Examples</span></span>

<span data-ttu-id="7e493-159">현재 디렉터리에 있는 프로젝트에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-159">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="7e493-160">`test1` 프로젝트에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-160">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

## <a name="filter-option-details"></a><span data-ttu-id="7e493-161">필터 옵션 세부 정보</span><span class="sxs-lookup"><span data-stu-id="7e493-161">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="7e493-162">`<Expression>`에 `<property><operator><value>[|&<Expression>]` 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-162">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="7e493-163">`<property>`은(는) `Test Case`의 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-163">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="7e493-164">다음은 인기 있는 단위 테스트 프레임 워크에서 지원되는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-164">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="7e493-165">테스트 프레임워크</span><span class="sxs-lookup"><span data-stu-id="7e493-165">Test Framework</span></span> | <span data-ttu-id="7e493-166">지원되는 속성</span><span class="sxs-lookup"><span data-stu-id="7e493-166">Supported properties</span></span>                                                                                      |
| :------------: | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="7e493-167">MSTest</span><span class="sxs-lookup"><span data-stu-id="7e493-167">MSTest</span></span>         | <ul><li><span data-ttu-id="7e493-168">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="7e493-168">FullyQualifiedName</span></span></li><li><span data-ttu-id="7e493-169">name</span><span class="sxs-lookup"><span data-stu-id="7e493-169">Name</span></span></li><li><span data-ttu-id="7e493-170">ClassName</span><span class="sxs-lookup"><span data-stu-id="7e493-170">ClassName</span></span></li><li><span data-ttu-id="7e493-171">우선 순위</span><span class="sxs-lookup"><span data-stu-id="7e493-171">Priority</span></span></li><li><span data-ttu-id="7e493-172">TestCategory</span><span class="sxs-lookup"><span data-stu-id="7e493-172">TestCategory</span></span></li></ul> |
| <span data-ttu-id="7e493-173">Xunit</span><span class="sxs-lookup"><span data-stu-id="7e493-173">Xunit</span></span>          | <ul><li><span data-ttu-id="7e493-174">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="7e493-174">FullyQualifiedName</span></span></li><li><span data-ttu-id="7e493-175">DisplayName</span><span class="sxs-lookup"><span data-stu-id="7e493-175">DisplayName</span></span></li><li><span data-ttu-id="7e493-176">특성</span><span class="sxs-lookup"><span data-stu-id="7e493-176">Traits</span></span></li></ul>                                   |

<span data-ttu-id="7e493-177">`<operator>`은(는) 속성과 값 사이의 관계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-177">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="7e493-178">연산자</span><span class="sxs-lookup"><span data-stu-id="7e493-178">Operator</span></span> | <span data-ttu-id="7e493-179">함수</span><span class="sxs-lookup"><span data-stu-id="7e493-179">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="7e493-180">정확하게 일치</span><span class="sxs-lookup"><span data-stu-id="7e493-180">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="7e493-181">정확하게 일치하지 않음</span><span class="sxs-lookup"><span data-stu-id="7e493-181">Not exact match</span></span> |
| `~`      | <span data-ttu-id="7e493-182">포함</span><span class="sxs-lookup"><span data-stu-id="7e493-182">Contains</span></span>        |

<span data-ttu-id="7e493-183">`<value>`는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-183">`<value>` is a string.</span></span> <span data-ttu-id="7e493-184">모든 조회는 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-184">All the lookups are case insensitive.</span></span>

<span data-ttu-id="7e493-185">`<operator>`이(가) 없는 식은 `FullyQualifiedName` 속성의 `contains`(으)로 자동으로 간주됩니다(예를 들어 `dotnet test --filter xyz`과(와) `dotnet test --filter FullyQualifiedName~xyz`이(가) 동일).</span><span class="sxs-lookup"><span data-stu-id="7e493-185">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="7e493-186">식은 조건부 연산자와 조인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e493-186">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="7e493-187">연산자</span><span class="sxs-lookup"><span data-stu-id="7e493-187">Operator</span></span> | <span data-ttu-id="7e493-188">함수</span><span class="sxs-lookup"><span data-stu-id="7e493-188">Function</span></span> |
| :------: | :------: |
| <code>&#124;</code>      | <span data-ttu-id="7e493-189">또는</span><span class="sxs-lookup"><span data-stu-id="7e493-189">OR</span></span>       |
| `&`      | <span data-ttu-id="7e493-190">AND</span><span class="sxs-lookup"><span data-stu-id="7e493-190">AND</span></span>      |

<span data-ttu-id="7e493-191">조건부 연산자를 사용 하는 경우 식을 괄호로 묶을 수 있습니다(예: `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="7e493-191">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="7e493-192">선택적 단위 테스트 필터링을 사용하는 방법에 대한 추가 정보 및 예제는 [선택적 단위 테스트 실행](../testing/selective-unit-tests.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7e493-192">For additional information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7e493-193">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e493-193">See also</span></span>

 [<span data-ttu-id="7e493-194">프레임워크 및 대상</span><span class="sxs-lookup"><span data-stu-id="7e493-194">Frameworks and Targets</span></span>](../../standard/frameworks.md)  
 [<span data-ttu-id="7e493-195">.NET Core RID(런타임 식별자) 카탈로그</span><span class="sxs-lookup"><span data-stu-id="7e493-195">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
