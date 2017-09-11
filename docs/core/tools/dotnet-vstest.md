---
title: "dotnet vstest 명령 - .NET Core CLI"
description: "dotnet vtest 명령은 프로젝트와 모든 종속성을 빌드합니다."
author: guardrex
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: c5a7ee0ba306cea641b0ff34f0b521c92bd03719
ms.contentlocale: ko-kr
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-vstest"></a><span data-ttu-id="6fe79-103">dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="6fe79-103">dotnet vstest</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="6fe79-104">이름</span><span class="sxs-lookup"><span data-stu-id="6fe79-104">Name</span></span>

<span data-ttu-id="6fe79-105">`dotnet-vstest` - 지정한 파일에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-105">`dotnet-vstest` - Runs tests from the specified files.</span></span>

## <a name="synopsis"></a><span data-ttu-id="6fe79-106">개요</span><span class="sxs-lookup"><span data-stu-id="6fe79-106">Synopsis</span></span>

`dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath] [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger] [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]`

## <a name="description"></a><span data-ttu-id="6fe79-107">설명</span><span class="sxs-lookup"><span data-stu-id="6fe79-107">Description</span></span>

<span data-ttu-id="6fe79-108">`dotnet-vstest` 명령은 `VSTest.Console` 명령줄 응용 프로그램을 실행하여 자동화된 단위 및 코딩된 UI 응용 프로그램 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-108">The `dotnet-vstest` command runs the `VSTest.Console` command-line application to run automated unit and coded UI application tests.</span></span>

## <a name="arguments"></a><span data-ttu-id="6fe79-109">인수</span><span class="sxs-lookup"><span data-stu-id="6fe79-109">Arguments</span></span>

`TEST_FILE_NAMES`

<span data-ttu-id="6fe79-110">지정한 어셈블리에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-110">Run tests from the specified assemblies.</span></span> <span data-ttu-id="6fe79-111">여러 테스트 어셈블리 이름을 공백으로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-111">Separate multiple test assembly names with spaces.</span></span>

## <a name="options"></a><span data-ttu-id="6fe79-112">옵션</span><span class="sxs-lookup"><span data-stu-id="6fe79-112">Options</span></span>

`--Settings|/Settings:<Settings File>`

<span data-ttu-id="6fe79-113">테스트를 실행할 때 사용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-113">Settings to use when running tests.</span></span>

`--Tests|/Tests:<Test Names>`

<span data-ttu-id="6fe79-114">제공된 값과 같은 이름의 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-114">Run tests with names that match the provided values.</span></span> <span data-ttu-id="6fe79-115">여러 값을 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-115">Separate multiple values with commas.</span></span>

`--TestAdapterPath|/TestAdapterPath`

<span data-ttu-id="6fe79-116">테스트 실행에서 지정된 경로(있는 경우)의 사용자 지정 테스트 어댑터를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-116">Use custom test adapters from a given path (if any) in the test run.</span></span>

`--Platform|/Platform:<Platform type>`

<span data-ttu-id="6fe79-117">테스트를 실행하는 데 사용되는 대상 플랫폼 아키텍처입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-117">Target platform architecture used for test execution.</span></span> <span data-ttu-id="6fe79-118">유효한 값은 `x86`, `x64` 및 `ARM`입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-118">Valid values are `x86`, `x64`, and `ARM`.</span></span>

`--Framework|/Framework:<Framework Version>`

<span data-ttu-id="6fe79-119">테스트 실행에 사용되는 대상 .NET Framework 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-119">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="6fe79-120">유효한 값의 예로 `.NETFramework,Version=v4.6`, `.NETCoreApp,Version=v1.0` 등이 있습니다. 지원되는 기타 값에는 `Framework35`, `Framework40`, `Framework45` 및 `FrameworkCore10`이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-120">Examples of valid values are `.NETFramework,Version=v4.6`, `.NETCoreApp,Version=v1.0`, etc. Other supported values are `Framework35`, `Framework40`, `Framework45`, and `FrameworkCore10`.</span></span>

`--Parallel|/Parallel`

<span data-ttu-id="6fe79-121">테스트를 병렬로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-121">Execute tests in parallel.</span></span> <span data-ttu-id="6fe79-122">기본적으로 컴퓨터의 사용 가능한 모든 코어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-122">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="6fe79-123">설정 파일을 사용하여 명시적인 코어 수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-123">Set an explicit number of cores with a settings file.</span></span>

`--TestCaseFilter|/TestCaseFilter:<Expression>`

<span data-ttu-id="6fe79-124">지정된 식과 일치하는 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-124">Run tests that match the given expression.</span></span> <span data-ttu-id="6fe79-125">`<Expression>`은 `<property>Operator<value>[|&<Expression>]` 형식입니다. 여기서 Operator는 `=`, `!=` 또는 `~` 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-125">`<Expression>` is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span>  <span data-ttu-id="6fe79-126">연산자 `~`는 '포함' 의미 체계를 가지며 `DisplayName`과 같은 문자열 속성에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-126">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="6fe79-127">하위 식을 그룹으로 묶는 데 괄호 `()`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-127">Parenthesis `()` are used to group sub-expressions.</span></span>

`-?|--Help|/?|/Help`

<span data-ttu-id="6fe79-128">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-128">Prints out a short help for the command.</span></span>

`--logger|/logger:<Logger Uri/FriendlyName>`

<span data-ttu-id="6fe79-129">테스트 결과에 대해 로거를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-129">Specify a logger for test results.</span></span>  

* <span data-ttu-id="6fe79-130">Team Foundation Server에 테스트 결과를 게시하려면 `TfsPublisher` 로거 공급자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-130">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

  ```
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* <span data-ttu-id="6fe79-131">Visual Studio 테스트 결과 파일(TRX)에 결과를 기록하려면 `trx` 로거 공급자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-131">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="6fe79-132">이 스위치는 지정된 로그 파일 이름을 사용하여 테스트 결과 디렉터리에 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-132">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="6fe79-133">`LogFileName`이 제공되지 않으면 테스트 결과를 포함할 고유한 파일 이름이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-133">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

  ```
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

<span data-ttu-id="6fe79-134">지정된 테스트 컨테이너에서 검색된 테스트를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-134">Lists discovered tests from the given test container.</span></span>

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

<span data-ttu-id="6fe79-135">현재 프로세스를 시작하는 일을 담당하는 부모 프로세스의 프로세스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-135">Process Id of the parent process responsible for launching the current process.</span></span>

`--Port|/Port:<Port>`

<span data-ttu-id="6fe79-136">소켓 연결 및 이벤트 메시지를 받기 위한 포트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-136">Specifies the port for the socket connection and receiving the event messages.</span></span>

`--Diag|/Diag:<Path to log file>`

<span data-ttu-id="6fe79-137">테스트 플랫폼에 대한 자세한 정보 로그를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-137">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="6fe79-138">로그는 제공된 파일에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-138">Logs are written to the provided file.</span></span>

`args`

<span data-ttu-id="6fe79-139">어댑터에 전달될 추가 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-139">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="6fe79-140">인수는 `<n>=<v>` 형식의 이름-값 쌍으로 지정됩니다. 여기서 `<n>`은 인수 이름이고 `<v>`는 인수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-140">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="6fe79-141">여러 개의 인수를 구분하려면 공백을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-141">Use a space to separate multiple arguments.</span></span>

## <a name="examples"></a><span data-ttu-id="6fe79-142">예제</span><span class="sxs-lookup"><span data-stu-id="6fe79-142">Examples</span></span>

<span data-ttu-id="6fe79-143">`mytestproject.dll`에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-143">Run tests in `mytestproject.dll`:</span></span>

`dotnet vstest mytestproject.dll`

<span data-ttu-id="6fe79-144">`mytestproject.dll` 및 `myothertestproject.exe`에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-144">Run tests in `mytestproject.dll` and `myothertestproject.exe`:</span></span>

`dotnet vstest mytestproject.dll myothertestproject.exe`

<span data-ttu-id="6fe79-145">`TestMethod1` 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-145">Run `TestMethod1` tests:</span></span>

`dotnet vstest /Tests:TestMethod1`

<span data-ttu-id="6fe79-146">`TestMethod1` 및 `TestMethod2` 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6fe79-146">Run `TestMethod1` and `TestMethod2` tests:</span></span>

`dotnet vstest /Tests:TestMethod1,TestMethod2`

