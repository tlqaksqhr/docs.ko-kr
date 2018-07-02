---
title: dotnet 명령 - .NET Core CLI
description: dotnet 명령(.NET Core CLI 도구에 대한 일반 드라이버) 및 사용법에 대해 알아봅니다.
author: mairaw
ms.author: mairaw
ms.date: 06/04/2018
ms.openlocfilehash: 788dc746705f9328683019ab3ad9836204a1ea63
ms.sourcegitcommit: fc70fcb9c789b6a4aefcdace46f3643fd076450f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2018
ms.locfileid: "34805661"
---
# <a name="dotnet-command"></a><span data-ttu-id="89799-103">dotnet 명령</span><span class="sxs-lookup"><span data-stu-id="89799-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="89799-104">name</span><span class="sxs-lookup"><span data-stu-id="89799-104">Name</span></span>

<span data-ttu-id="89799-105">`dotnet` - 명령줄 명령을 실행하기 위한 일반 드라이버입니다.</span><span class="sxs-lookup"><span data-stu-id="89799-105">`dotnet` - General driver for running the command-line commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="89799-106">개요</span><span class="sxs-lookup"><span data-stu-id="89799-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="89799-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="89799-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="89799-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="89799-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="89799-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="89799-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```
---

## <a name="description"></a><span data-ttu-id="89799-110">설명</span><span class="sxs-lookup"><span data-stu-id="89799-110">Description</span></span>

<span data-ttu-id="89799-111">`dotnet`은 CLI(명령줄 인터페이스) 도구 체인에 대한 일반 드라이버입니다.</span><span class="sxs-lookup"><span data-stu-id="89799-111">`dotnet` is a generic driver for the Command Line Interface (CLI) toolchain.</span></span> <span data-ttu-id="89799-112">자체적으로 호출되어 간단한 사용 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-112">Invoked on its own, it provides brief usage instructions.</span></span>

<span data-ttu-id="89799-113">각 특정 기능은 명령으로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="89799-113">Each specific feature is implemented as a command.</span></span> <span data-ttu-id="89799-114">기능을 사용하려면 `dotnet` 뒤에 명령을 지정합니다(예: [`dotnet build`](dotnet-build.md)).</span><span class="sxs-lookup"><span data-stu-id="89799-114">To use the feature, the command is specified after `dotnet`, such as [`dotnet build`](dotnet-build.md).</span></span> <span data-ttu-id="89799-115">명령 다음에 오는 모든 인수는 고유한 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="89799-115">All of the arguments following the command are its own arguments.</span></span>

<span data-ttu-id="89799-116">`dotnet` 자체가 명령으로 사용되는 유일한 경우는 [프레임워크 종속 앱](../deploying/index.md)을 실행하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="89799-116">The only time `dotnet` is used as a command on its own is to run [framework-dependent apps](../deploying/index.md).</span></span> <span data-ttu-id="89799-117">`dotnet` 동사 뒤에 응용 프로그램 DLL을 지정하여 응용 프로그램을 실행합니다(예: `dotnet myapp.dll`).</span><span class="sxs-lookup"><span data-stu-id="89799-117">Specify an application DLL after the `dotnet` verb to execute the application (for example, `dotnet myapp.dll`).</span></span>

## <a name="options"></a><span data-ttu-id="89799-118">옵션</span><span class="sxs-lookup"><span data-stu-id="89799-118">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="89799-119">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="89799-119">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="89799-120">추가적인 *deps.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="89799-120">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="89799-121">검색 정책 및 검색할 어셈블리를 포함하는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="89799-121">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="89799-122">진단 출력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-122">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="89799-123">응용 프로그램 실행에 사용할 설치된 .NET Core 런타임의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="89799-123">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="89799-124">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-124">Prints out a short help for the command.</span></span> <span data-ttu-id="89799-125">`dotnet`과 함께 사용되는 경우 사용 가능한 명령 목록도 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-125">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="89799-126">현재 운영 체제, 버전에 대한 SHA 커밋 및 기타 정보 등 CLI 도구 및 환경에 대한 자세한 정보를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-126">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`--list-runtimes`

<span data-ttu-id="89799-127">설치된 .NET Core 런타임을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-127">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="89799-128">설치된 .NET Core SDK를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-128">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="89799-129">후보 공유 프레임워크에서는 롤포워드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89799-129">Rolls forward on no candidate shared framework.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="89799-130">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-130">Sets the verbosity level of the command.</span></span> <span data-ttu-id="89799-131">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="89799-131">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="89799-132">모든 명령에서 지원되지 않습니다. 이 옵션을 사용할 수 있는지 확인하려면 특정 명령 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89799-132">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="89799-133">사용 중인 .NET Core SDK 버전을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-133">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="89799-134">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="89799-134">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="89799-135">추가적인 *deps.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="89799-135">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="89799-136">검색 정책 및 검색할 어셈블리를 포함하는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="89799-136">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="89799-137">진단 출력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-137">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="89799-138">응용 프로그램 실행에 사용할 설치된 .NET Core 런타임의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="89799-138">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="89799-139">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-139">Prints out a short help for the command.</span></span> <span data-ttu-id="89799-140">`dotnet`과 함께 사용되는 경우 사용 가능한 명령 목록도 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-140">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="89799-141">현재 운영 체제, 버전에 대한 SHA 커밋 및 기타 정보 등 CLI 도구 및 환경에 대한 자세한 정보를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-141">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="89799-142">후보 공유 프레임워크에서는 롤포워드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89799-142">Rolls forward on no candidate shared framework.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="89799-143">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-143">Sets the verbosity level of the command.</span></span> <span data-ttu-id="89799-144">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="89799-144">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="89799-145">모든 명령에서 지원되지 않습니다. 이 옵션을 사용할 수 있는지 확인하려면 특정 명령 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89799-145">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="89799-146">사용 중인 .NET Core SDK 버전을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-146">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="89799-147">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="89799-147">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="89799-148">검색 정책 및 검색할 어셈블리를 포함하는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="89799-148">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="89799-149">진단 출력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-149">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="89799-150">응용 프로그램 실행에 사용할 설치된 .NET Core 런타임의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="89799-150">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="89799-151">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-151">Prints out a short help for the command.</span></span> <span data-ttu-id="89799-152">`dotnet`과 함께 사용되는 경우 사용 가능한 명령 목록도 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-152">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="89799-153">현재 운영 체제, 버전에 대한 SHA 커밋 및 기타 정보 등 CLI 도구 및 환경에 대한 자세한 정보를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-153">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="89799-154">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-154">Sets the verbosity level of the command.</span></span> <span data-ttu-id="89799-155">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="89799-155">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="89799-156">모든 명령에서 지원되지 않습니다. 이 옵션을 사용할 수 있는지 확인하려면 특정 명령 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89799-156">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="89799-157">사용 중인 .NET Core SDK 버전을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-157">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="89799-158">dotnet 명령</span><span class="sxs-lookup"><span data-stu-id="89799-158">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="89799-159">일반</span><span class="sxs-lookup"><span data-stu-id="89799-159">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="89799-160">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="89799-160">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="89799-161">명령</span><span class="sxs-lookup"><span data-stu-id="89799-161">Command</span></span>                                       | <span data-ttu-id="89799-162">함수</span><span class="sxs-lookup"><span data-stu-id="89799-162">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="89799-163">dotnet build</span><span class="sxs-lookup"><span data-stu-id="89799-163">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="89799-164">.NET Core 응용 프로그램을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-164">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="89799-165">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="89799-165">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="89799-166">빌드에서 시작된 서버와 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-166">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="89799-167">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="89799-167">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="89799-168">빌드 출력을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-168">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="89799-169">dotnet help</span><span class="sxs-lookup"><span data-stu-id="89799-169">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="89799-170">명령에 대한 자세한 온라인 설명서를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-170">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="89799-171">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="89799-171">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="89799-172">유효한 Preview 2 프로젝트를 .NET Core SDK 1.0 프로젝트로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-172">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="89799-173">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="89799-173">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="89799-174">MSBuild 명령줄에 대한 액세스 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-174">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="89799-175">dotnet new</span><span class="sxs-lookup"><span data-stu-id="89799-175">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="89799-176">지정한 템플릿에 대해 C# 또는 F# 프로젝트를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-176">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="89799-177">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="89799-177">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="89799-178">코드의 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="89799-178">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="89799-179">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="89799-179">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="89799-180">.NET Framework 종속형 또는 자체 포함 응용 프로그램을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-180">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="89799-181">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="89799-181">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="89799-182">지정된 응용 프로그램에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-182">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="89799-183">dotnet run</span><span class="sxs-lookup"><span data-stu-id="89799-183">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="89799-184">소스에서 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-184">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="89799-185">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="89799-185">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="89799-186">솔루션 파일에 프로젝트를 추가, 제거 및 나열하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="89799-186">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="89799-187">dotnet store</span><span class="sxs-lookup"><span data-stu-id="89799-187">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="89799-188">어셈블리를 런타임 패키지 저장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-188">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="89799-189">dotnet test</span><span class="sxs-lookup"><span data-stu-id="89799-189">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="89799-190">Test Runner를 사용하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-190">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="89799-191">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="89799-191">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="89799-192">명령</span><span class="sxs-lookup"><span data-stu-id="89799-192">Command</span></span>                             | <span data-ttu-id="89799-193">함수</span><span class="sxs-lookup"><span data-stu-id="89799-193">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="89799-194">dotnet build</span><span class="sxs-lookup"><span data-stu-id="89799-194">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="89799-195">.NET Core 응용 프로그램을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-195">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="89799-196">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="89799-196">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="89799-197">빌드 출력을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-197">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="89799-198">dotnet help</span><span class="sxs-lookup"><span data-stu-id="89799-198">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="89799-199">명령에 대한 자세한 온라인 설명서를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-199">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="89799-200">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="89799-200">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="89799-201">유효한 Preview 2 프로젝트를 .NET Core SDK 1.0 프로젝트로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-201">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="89799-202">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="89799-202">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="89799-203">MSBuild 명령줄에 대한 액세스 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-203">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="89799-204">dotnet new</span><span class="sxs-lookup"><span data-stu-id="89799-204">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="89799-205">지정한 템플릿에 대해 C# 또는 F# 프로젝트를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-205">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="89799-206">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="89799-206">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="89799-207">코드의 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="89799-207">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="89799-208">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="89799-208">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="89799-209">.NET Framework 종속형 또는 자체 포함 응용 프로그램을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-209">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="89799-210">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="89799-210">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="89799-211">지정된 응용 프로그램에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-211">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="89799-212">dotnet run</span><span class="sxs-lookup"><span data-stu-id="89799-212">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="89799-213">소스에서 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-213">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="89799-214">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="89799-214">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="89799-215">솔루션 파일에 프로젝트를 추가, 제거 및 나열하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="89799-215">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="89799-216">dotnet store</span><span class="sxs-lookup"><span data-stu-id="89799-216">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="89799-217">어셈블리를 런타임 패키지 저장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-217">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="89799-218">dotnet test</span><span class="sxs-lookup"><span data-stu-id="89799-218">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="89799-219">Test Runner를 사용하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-219">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="89799-220">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="89799-220">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="89799-221">명령</span><span class="sxs-lookup"><span data-stu-id="89799-221">Command</span></span>                             | <span data-ttu-id="89799-222">함수</span><span class="sxs-lookup"><span data-stu-id="89799-222">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="89799-223">dotnet build</span><span class="sxs-lookup"><span data-stu-id="89799-223">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="89799-224">.NET Core 응용 프로그램을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-224">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="89799-225">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="89799-225">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="89799-226">빌드 출력을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-226">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="89799-227">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="89799-227">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="89799-228">유효한 Preview 2 프로젝트를 .NET Core SDK 1.0 프로젝트로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-228">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="89799-229">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="89799-229">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="89799-230">MSBuild 명령줄에 대한 액세스 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-230">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="89799-231">dotnet new</span><span class="sxs-lookup"><span data-stu-id="89799-231">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="89799-232">지정한 템플릿에 대해 C# 또는 F# 프로젝트를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-232">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="89799-233">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="89799-233">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="89799-234">코드의 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="89799-234">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="89799-235">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="89799-235">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="89799-236">.NET Framework 종속형 또는 자체 포함 응용 프로그램을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-236">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="89799-237">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="89799-237">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="89799-238">지정된 응용 프로그램에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-238">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="89799-239">dotnet run</span><span class="sxs-lookup"><span data-stu-id="89799-239">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="89799-240">소스에서 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-240">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="89799-241">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="89799-241">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="89799-242">솔루션 파일에 프로젝트를 추가, 제거 및 나열하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="89799-242">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="89799-243">dotnet test</span><span class="sxs-lookup"><span data-stu-id="89799-243">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="89799-244">Test Runner를 사용하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-244">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="89799-245">프로젝트 참조</span><span class="sxs-lookup"><span data-stu-id="89799-245">Project references</span></span>

<span data-ttu-id="89799-246">명령</span><span class="sxs-lookup"><span data-stu-id="89799-246">Command</span></span> | <span data-ttu-id="89799-247">함수</span><span class="sxs-lookup"><span data-stu-id="89799-247">Function</span></span>
--- | ---
[<span data-ttu-id="89799-248">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="89799-248">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="89799-249">프로젝트 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-249">Adds a project reference.</span></span>
[<span data-ttu-id="89799-250">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="89799-250">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="89799-251">프로젝트 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-251">Lists project references.</span></span>
[<span data-ttu-id="89799-252">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="89799-252">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="89799-253">프로젝트 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-253">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="89799-254">NuGet 패키지</span><span class="sxs-lookup"><span data-stu-id="89799-254">NuGet packages</span></span>

<span data-ttu-id="89799-255">명령</span><span class="sxs-lookup"><span data-stu-id="89799-255">Command</span></span> | <span data-ttu-id="89799-256">함수</span><span class="sxs-lookup"><span data-stu-id="89799-256">Function</span></span>
--- | ---
[<span data-ttu-id="89799-257">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="89799-257">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="89799-258">NuGet 패키지를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-258">Adds a NuGet package.</span></span>
[<span data-ttu-id="89799-259">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="89799-259">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="89799-260">NuGet 패키지를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-260">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="89799-261">NuGet 명령</span><span class="sxs-lookup"><span data-stu-id="89799-261">NuGet commands</span></span>

<span data-ttu-id="89799-262">명령</span><span class="sxs-lookup"><span data-stu-id="89799-262">Command</span></span> | <span data-ttu-id="89799-263">함수</span><span class="sxs-lookup"><span data-stu-id="89799-263">Function</span></span>
--- | ---
[<span data-ttu-id="89799-264">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="89799-264">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="89799-265">서버에서 패키지를 삭제하거나 목록에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-265">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="89799-266">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="89799-266">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="89799-267">http-request 캐시, 임시 캐시 또는 시스템 전체의 글로벌 패키지 폴더와 같은 로컬 NuGet 리소스를 지우거나 목록에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-267">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="89799-268">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="89799-268">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="89799-269">서버에 패키지를 푸시하고 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-269">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="89799-270">전역 도구 명령</span><span class="sxs-lookup"><span data-stu-id="89799-270">Global Tools commands</span></span>

<span data-ttu-id="89799-271">[.NET Core 전역 도구](global-tools.md)는 .NET Core SDK 2.1.300부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89799-271">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="89799-272">명령</span><span class="sxs-lookup"><span data-stu-id="89799-272">Command</span></span> | <span data-ttu-id="89799-273">함수</span><span class="sxs-lookup"><span data-stu-id="89799-273">Function</span></span>
--- | ---
[<span data-ttu-id="89799-274">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="89799-274">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="89799-275">컴퓨터에 전역 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-275">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="89799-276">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="89799-276">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="89799-277">컴퓨터의 기본 디렉터리 또는 지정된 경로에 현재 설치된 모든 전역 도구를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-277">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="89799-278">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="89799-278">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="89799-279">컴퓨터에서 전역 도구를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-279">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="89799-280">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="89799-280">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="89799-281">컴퓨터에서 전역 도구를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-281">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="89799-282">추가 도구</span><span class="sxs-lookup"><span data-stu-id="89799-282">Additional tools</span></span>

<span data-ttu-id="89799-283">.NET Core SDK 2.1.300부터는 `DotnetCliToolReference`을 사용하여 프로젝트별로만 사용할 수 있었던 여러 도구를 .NET Core SDK의 일부로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89799-283">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="89799-284">사용 가능한 도구는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="89799-284">These tools include:</span></span>

| <span data-ttu-id="89799-285">도구</span><span class="sxs-lookup"><span data-stu-id="89799-285">Tool</span></span>                                              | <span data-ttu-id="89799-286">함수</span><span class="sxs-lookup"><span data-stu-id="89799-286">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="89799-287">dev-certs</span><span class="sxs-lookup"><span data-stu-id="89799-287">dev-certs</span></span>                                         | <span data-ttu-id="89799-288">개발 인증서를 만들고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-288">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="89799-289">ef</span><span class="sxs-lookup"><span data-stu-id="89799-289">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="89799-290">Entity Framework Core 명령줄 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="89799-290">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="89799-291">sql-cache</span><span class="sxs-lookup"><span data-stu-id="89799-291">sql-cache</span></span>                                         | <span data-ttu-id="89799-292">SQL Server 캐시 명령줄 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="89799-292">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="89799-293">user-secrets</span><span class="sxs-lookup"><span data-stu-id="89799-293">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="89799-294">개발 사용자 비밀을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-294">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="89799-295">watch</span><span class="sxs-lookup"><span data-stu-id="89799-295">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="89799-296">파일이 변경될 때 명령을 실행하는 파일 감시자를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-296">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="89799-297">각 도구에 대한 자세한 내용을 보려면 `dotnet <tool-name> --help`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-297">For more information about each tool, execute `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="89799-298">예제</span><span class="sxs-lookup"><span data-stu-id="89799-298">Examples</span></span>

<span data-ttu-id="89799-299">새 .NET Core 콘솔 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="89799-299">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="89799-300">지정된 응용 프로그램에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-300">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="89799-301">지정된 디렉터리에서 프로젝트 및 해당 종속성을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-301">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="89799-302">이름이 `myapp.dll`인 프레임워크 종속형 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-302">Run a framework-dependent app named `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="89799-303">환경 변수</span><span class="sxs-lookup"><span data-stu-id="89799-303">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="89799-304">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="89799-304">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="89799-305">주 패키지 캐시입니다.</span><span class="sxs-lookup"><span data-stu-id="89799-305">The primary package cache.</span></span> <span data-ttu-id="89799-306">설정하지 않으면 기본적으로 Unix에서는 `$HOME/.nuget/packages`, Windows에서는 `%HOME%\NuGet\Packages`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="89799-306">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="89799-307">런타임을 로드할 때 공유 호스트에서 사용할 서비스 인덱스의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-307">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="89799-308">.NET Core 도구 사용에 대한 데이터를 수집하여 Microsoft에 전송할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-308">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="89799-309">원격 분석 기능을 옵트아웃하려면 `true`로 설정합니다(값 `true`, `1` 또는 `yes`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="89799-309">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="89799-310">이외의 경우 원격 분석 기능을 옵트인하려면 `false`로 설정합니다(`false`, `0` 또는 `no`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="89799-310">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="89799-311">설정하지 않으면 기본적으로 `false`이고 원격 분석 기능은 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="89799-311">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="89799-312">전역 위치에서 .NET Core 런타임, 공유 프레임워크 또는 SDK가 확인되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-312">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="89799-313">설정하지 않은 경우 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="89799-313">If not set, it defaults to `true`.</span></span> <span data-ttu-id="89799-314">전역 위치에서 확인하지 않고 격리된 .NET Core 설치를 가지려면 `false`로 설정합니다(값 `0` 또는 `false`는 허용됨).</span><span class="sxs-lookup"><span data-stu-id="89799-314">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="89799-315">다중 수준의 조회에 대한 자세한 내용은 [다중 수준 SharedFX 조회](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89799-315">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="89799-316">부 버전 롤포워드를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-316">Disables minor version roll forward.</span></span> <span data-ttu-id="89799-317">자세한 내용은 [롤포워드](../whats-new/dotnet-core-2-1.md#roll-forward)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89799-317">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="89799-318">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="89799-318">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="89799-319">주 패키지 캐시입니다.</span><span class="sxs-lookup"><span data-stu-id="89799-319">The primary package cache.</span></span> <span data-ttu-id="89799-320">설정하지 않으면 기본적으로 Unix에서는 `$HOME/.nuget/packages`, Windows에서는 `%HOME%\NuGet\Packages`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="89799-320">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="89799-321">런타임을 로드할 때 공유 호스트에서 사용할 서비스 인덱스의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-321">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="89799-322">.NET Core 도구 사용에 대한 데이터를 수집하여 Microsoft에 전송할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-322">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="89799-323">원격 분석 기능을 옵트아웃하려면 `true`로 설정합니다(값 `true`, `1` 또는 `yes`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="89799-323">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="89799-324">이외의 경우 원격 분석 기능을 옵트인하려면 `false`로 설정합니다(`false`, `0` 또는 `no`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="89799-324">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="89799-325">설정하지 않으면 기본적으로 `false`이고 원격 분석 기능은 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="89799-325">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="89799-326">전역 위치에서 .NET Core 런타임, 공유 프레임워크 또는 SDK가 확인되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-326">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="89799-327">설정하지 않은 경우 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="89799-327">If not set, it defaults to `true`.</span></span> <span data-ttu-id="89799-328">전역 위치에서 확인하지 않고 격리된 .NET Core 설치를 가지려면 `false`로 설정합니다(값 `0` 또는 `false`는 허용됨).</span><span class="sxs-lookup"><span data-stu-id="89799-328">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="89799-329">다중 수준의 조회에 대한 자세한 내용은 [다중 수준 SharedFX 조회](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89799-329">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="89799-330">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="89799-330">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="89799-331">주 패키지 캐시입니다.</span><span class="sxs-lookup"><span data-stu-id="89799-331">The primary package cache.</span></span> <span data-ttu-id="89799-332">설정하지 않으면 기본적으로 Unix에서는 `$HOME/.nuget/packages`, Windows에서는 `%HOME%\NuGet\Packages`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="89799-332">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="89799-333">런타임을 로드할 때 공유 호스트에서 사용할 서비스 인덱스의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-333">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="89799-334">.NET Core 도구 사용에 대한 데이터를 수집하여 Microsoft에 전송할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="89799-334">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="89799-335">원격 분석 기능을 옵트아웃하려면 `true`로 설정합니다(값 `true`, `1` 또는 `yes`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="89799-335">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="89799-336">이외의 경우 원격 분석 기능을 옵트인하려면 `false`로 설정합니다(`false`, `0` 또는 `no`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="89799-336">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="89799-337">설정하지 않으면 기본적으로 `false`이고 원격 분석 기능은 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="89799-337">If not set, the default is `false` and the telemetry feature is active.</span></span>

---
