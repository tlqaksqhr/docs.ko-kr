---
title: dotnet 명령 - .NET Core CLI
description: dotnet 명령(.NET Core CLI 도구에 대한 일반 드라이버) 및 사용법에 대해 알아봅니다.
author: mairaw
ms.author: mairaw
ms.date: 03/20/2018
ms.openlocfilehash: c56ed032ccef6c6fd19a13214b04b384ffff28d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-command"></a><span data-ttu-id="f8657-103">dotnet 명령</span><span class="sxs-lookup"><span data-stu-id="f8657-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="f8657-104">name</span><span class="sxs-lookup"><span data-stu-id="f8657-104">Name</span></span>

<span data-ttu-id="f8657-105">`dotnet` - 명령줄 명령을 실행하기 위한 일반 드라이버입니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-105">`dotnet` - General driver for running the command-line commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f8657-106">개요</span><span class="sxs-lookup"><span data-stu-id="f8657-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="f8657-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="f8657-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f8657-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f8657-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```
---

## <a name="description"></a><span data-ttu-id="f8657-109">설명</span><span class="sxs-lookup"><span data-stu-id="f8657-109">Description</span></span>

<span data-ttu-id="f8657-110">`dotnet`은 CLI(명령줄 인터페이스) 도구 체인에 대한 일반 드라이버입니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-110">`dotnet` is a generic driver for the Command Line Interface (CLI) toolchain.</span></span> <span data-ttu-id="f8657-111">자체적으로 호출되어 간단한 사용 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-111">Invoked on its own, it provides brief usage instructions.</span></span>

<span data-ttu-id="f8657-112">각 특정 기능은 명령으로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-112">Each specific feature is implemented as a command.</span></span> <span data-ttu-id="f8657-113">기능을 사용하려면 [`dotnet build`](dotnet-build.md)와 같이 `dotnet`뒤에 명령을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-113">In order to use the feature, the command is specified after `dotnet`, such as [`dotnet build`](dotnet-build.md).</span></span> <span data-ttu-id="f8657-114">명령 다음에 오는 모든 인수는 고유한 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-114">All of the arguments following the command are its own arguments.</span></span>

<span data-ttu-id="f8657-115">`dotnet` 자체가 명령으로 사용되는 유일한 경우는 [프레임워크 종속 앱](../deploying/index.md)을 실행하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-115">The only time `dotnet` is used as a command on its own is to run [framework-dependent apps](../deploying/index.md).</span></span> <span data-ttu-id="f8657-116">`dotnet` 동사 뒤에 응용 프로그램 DLL을 지정하여 응용 프로그램을 실행합니다(예: `dotnet myapp.dll`).</span><span class="sxs-lookup"><span data-stu-id="f8657-116">Specify an application DLL after the `dotnet` verb to execute the application (for example, `dotnet myapp.dll`).</span></span>

## <a name="options"></a><span data-ttu-id="f8657-117">옵션</span><span class="sxs-lookup"><span data-stu-id="f8657-117">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="f8657-118">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="f8657-118">.NET Core 2.x</span></span>](#tab/netcore2x)

`--additional-deps <PATH>`

<span data-ttu-id="f8657-119">추가적인 *deps.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-119">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="f8657-120">검색 정책 및 검색할 어셈블리를 포함하는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-120">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="f8657-121">진단 출력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-121">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="f8657-122">응용 프로그램 실행에 사용할 설치된 .NET Core 런타임의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-122">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="f8657-123">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-123">Prints out a short help for the command.</span></span> <span data-ttu-id="f8657-124">`dotnet`과 함께 사용되는 경우 사용 가능한 명령 목록도 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-124">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="f8657-125">현재 운영 체제, 버전에 대한 SHA 커밋 및 기타 정보 등 CLI 도구 및 환경에 대한 자세한 정보를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-125">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="f8657-126">후보 공유 프레임워크에서는 롤포워드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-126">Rolls forward on no candidate shared framework.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="f8657-127">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-127">Sets the verbosity level of the command.</span></span> <span data-ttu-id="f8657-128">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-128">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f8657-129">모든 명령에서 지원되지 않습니다. 이 옵션을 사용할 수 있는지 확인하려면 특정 명령 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8657-129">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="f8657-130">사용 중인 .NET Core SDK 버전을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-130">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f8657-131">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f8657-131">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="f8657-132">검색 정책 및 검색할 어셈블리를 포함하는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-132">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="f8657-133">진단 출력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-133">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="f8657-134">응용 프로그램 실행에 사용할 설치된 .NET Core 런타임의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-134">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="f8657-135">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-135">Prints out a short help for the command.</span></span> <span data-ttu-id="f8657-136">`dotnet`과 함께 사용되는 경우 사용 가능한 명령 목록도 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-136">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="f8657-137">현재 운영 체제, 버전에 대한 SHA 커밋 및 기타 정보 등 CLI 도구 및 환경에 대한 자세한 정보를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-137">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="f8657-138">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-138">Sets the verbosity level of the command.</span></span> <span data-ttu-id="f8657-139">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f8657-140">모든 명령에서 지원되지 않습니다. 이 옵션을 사용할 수 있는지 확인하려면 특정 명령 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8657-140">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="f8657-141">사용 중인 .NET Core SDK 버전을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-141">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="f8657-142">dotnet 명령</span><span class="sxs-lookup"><span data-stu-id="f8657-142">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="f8657-143">일반</span><span class="sxs-lookup"><span data-stu-id="f8657-143">General</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="f8657-144">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="f8657-144">.NET Core 2.x</span></span>](#tab/netcore2x)

| <span data-ttu-id="f8657-145">명령</span><span class="sxs-lookup"><span data-stu-id="f8657-145">Command</span></span>                             | <span data-ttu-id="f8657-146">함수</span><span class="sxs-lookup"><span data-stu-id="f8657-146">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="f8657-147">dotnet build</span><span class="sxs-lookup"><span data-stu-id="f8657-147">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="f8657-148">.NET Core 응용 프로그램을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-148">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="f8657-149">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="f8657-149">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="f8657-150">빌드 출력을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-150">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="f8657-151">dotnet help</span><span class="sxs-lookup"><span data-stu-id="f8657-151">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="f8657-152">명령에 대한 자세한 온라인 설명서를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-152">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="f8657-153">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="f8657-153">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="f8657-154">유효한 Preview 2 프로젝트를 .NET Core SDK 1.0 프로젝트로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-154">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="f8657-155">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="f8657-155">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="f8657-156">MSBuild 명령줄에 대한 액세스 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-156">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="f8657-157">dotnet new</span><span class="sxs-lookup"><span data-stu-id="f8657-157">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="f8657-158">지정한 템플릿에 대해 C# 또는 F# 프로젝트를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-158">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="f8657-159">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="f8657-159">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="f8657-160">코드의 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-160">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="f8657-161">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="f8657-161">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="f8657-162">.NET Framework 종속형 또는 자체 포함 응용 프로그램을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-162">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="f8657-163">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="f8657-163">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="f8657-164">지정된 응용 프로그램에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-164">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="f8657-165">dotnet run</span><span class="sxs-lookup"><span data-stu-id="f8657-165">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="f8657-166">소스에서 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-166">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="f8657-167">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="f8657-167">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="f8657-168">솔루션 파일에 프로젝트를 추가, 제거 및 나열하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-168">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="f8657-169">dotnet store</span><span class="sxs-lookup"><span data-stu-id="f8657-169">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="f8657-170">어셈블리를 런타임 패키지 저장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-170">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="f8657-171">dotnet test</span><span class="sxs-lookup"><span data-stu-id="f8657-171">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="f8657-172">Test Runner를 사용하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-172">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f8657-173">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f8657-173">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="f8657-174">명령</span><span class="sxs-lookup"><span data-stu-id="f8657-174">Command</span></span>                             | <span data-ttu-id="f8657-175">함수</span><span class="sxs-lookup"><span data-stu-id="f8657-175">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="f8657-176">dotnet build</span><span class="sxs-lookup"><span data-stu-id="f8657-176">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="f8657-177">.NET Core 응용 프로그램을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-177">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="f8657-178">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="f8657-178">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="f8657-179">빌드 출력을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-179">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="f8657-180">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="f8657-180">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="f8657-181">유효한 Preview 2 프로젝트를 .NET Core SDK 1.0 프로젝트로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-181">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="f8657-182">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="f8657-182">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="f8657-183">MSBuild 명령줄에 대한 액세스 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-183">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="f8657-184">dotnet new</span><span class="sxs-lookup"><span data-stu-id="f8657-184">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="f8657-185">지정한 템플릿에 대해 C# 또는 F# 프로젝트를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-185">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="f8657-186">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="f8657-186">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="f8657-187">코드의 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-187">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="f8657-188">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="f8657-188">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="f8657-189">.NET Framework 종속형 또는 자체 포함 응용 프로그램을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-189">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="f8657-190">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="f8657-190">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="f8657-191">지정된 응용 프로그램에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-191">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="f8657-192">dotnet run</span><span class="sxs-lookup"><span data-stu-id="f8657-192">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="f8657-193">소스에서 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-193">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="f8657-194">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="f8657-194">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="f8657-195">솔루션 파일에 프로젝트를 추가, 제거 및 나열하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-195">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="f8657-196">dotnet test</span><span class="sxs-lookup"><span data-stu-id="f8657-196">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="f8657-197">Test Runner를 사용하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-197">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="f8657-198">프로젝트 참조</span><span class="sxs-lookup"><span data-stu-id="f8657-198">Project references</span></span>

<span data-ttu-id="f8657-199">명령</span><span class="sxs-lookup"><span data-stu-id="f8657-199">Command</span></span> | <span data-ttu-id="f8657-200">함수</span><span class="sxs-lookup"><span data-stu-id="f8657-200">Function</span></span>
--- | ---
[<span data-ttu-id="f8657-201">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="f8657-201">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="f8657-202">프로젝트 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-202">Add a project reference.</span></span>
[<span data-ttu-id="f8657-203">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="f8657-203">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="f8657-204">프로젝트 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-204">List project references.</span></span>
[<span data-ttu-id="f8657-205">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="f8657-205">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="f8657-206">프로젝트 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-206">Remove a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="f8657-207">NuGet 패키지</span><span class="sxs-lookup"><span data-stu-id="f8657-207">NuGet packages</span></span>

<span data-ttu-id="f8657-208">명령</span><span class="sxs-lookup"><span data-stu-id="f8657-208">Command</span></span> | <span data-ttu-id="f8657-209">함수</span><span class="sxs-lookup"><span data-stu-id="f8657-209">Function</span></span>
--- | ---
[<span data-ttu-id="f8657-210">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="f8657-210">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="f8657-211">NuGet 패키지를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-211">Add a NuGet package.</span></span>
[<span data-ttu-id="f8657-212">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="f8657-212">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="f8657-213">NuGet 패키지를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-213">Remove a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="f8657-214">NuGet 명령</span><span class="sxs-lookup"><span data-stu-id="f8657-214">NuGet commands</span></span>

<span data-ttu-id="f8657-215">명령</span><span class="sxs-lookup"><span data-stu-id="f8657-215">Command</span></span> | <span data-ttu-id="f8657-216">함수</span><span class="sxs-lookup"><span data-stu-id="f8657-216">Function</span></span>
--- | ---
[<span data-ttu-id="f8657-217">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="f8657-217">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="f8657-218">서버에서 패키지를 삭제하거나 목록에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-218">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="f8657-219">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="f8657-219">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="f8657-220">http-request 캐시, 임시 캐시 또는 시스템 전체의 글로벌 패키지 폴더와 같은 로컬 NuGet 리소스를 지우거나 목록에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-220">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="f8657-221">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="f8657-221">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="f8657-222">서버에 패키지를 푸시하고 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-222">Pushes a package to the server and publishes it.</span></span>

## <a name="examples"></a><span data-ttu-id="f8657-223">예제</span><span class="sxs-lookup"><span data-stu-id="f8657-223">Examples</span></span>

<span data-ttu-id="f8657-224">컴파일하고 실행할 수 있는 샘플 .NET Core 콘솔 응용 프로그램을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-224">Initialize a sample .NET Core console application that can be compiled and run:</span></span>

`dotnet new console`

<span data-ttu-id="f8657-225">지정된 응용 프로그램에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-225">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="f8657-226">지정된 디렉터리에서 프로젝트 및 해당 종속성을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-226">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="f8657-227">이름이 `myapp.dll`인 프레임워크 종속형 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-227">Run a framework-dependent app named `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="f8657-228">환경 변수</span><span class="sxs-lookup"><span data-stu-id="f8657-228">Environment variables</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="f8657-229">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="f8657-229">.NET Core 2.x</span></span>](#tab/netcore2x)

`DOTNET_PACKAGES`

<span data-ttu-id="f8657-230">주 패키지 캐시입니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-230">The primary package cache.</span></span> <span data-ttu-id="f8657-231">설정하지 않으면 기본적으로 Unix에서는 `$HOME/.nuget/packages`, Windows에서는 `%HOME%\NuGet\Packages`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-231">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="f8657-232">런타임을 로드할 때 공유 호스트에서 사용할 서비스 인덱스의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-232">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="f8657-233">.NET Core 도구 사용에 대한 데이터를 수집하여 Microsoft에 전송할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-233">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="f8657-234">원격 분석 기능을 옵트아웃하려면 `true`(값 `true`, `1` 또는 `yes` 허용)로 설정하고, 원격 분석 기능을 옵트인하려면 `false`(값 `false`, `0` 또는 `no` 허용)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-234">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted); otherwise, set to `false` to opt-in to the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="f8657-235">설정하지 않으면 기본적으로 `false`이고 원격 분석 기능은 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-235">If not set, the defaults is `false`, and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="f8657-236">전역 위치에서 .NET Core 런타임, 공유 프레임워크 또는 SDK가 확인되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-236">Specifies whether .NET Core runtime, shared framework or SDK are resolved from the global location.</span></span> <span data-ttu-id="f8657-237">설정하지 않은 경우 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-237">If not set, it defaults to `true`.</span></span> <span data-ttu-id="f8657-238">전역 위치에서 확인하지 않고 격리된 .NET Core 설치를 가지려면 `false`로 설정합니다(값 `0` 또는 `false`는 허용됨).</span><span class="sxs-lookup"><span data-stu-id="f8657-238">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="f8657-239">다중 수준의 조회에 대한 자세한 내용은 [다중 수준 SharedFX 조회](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8657-239">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f8657-240">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f8657-240">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="f8657-241">주 패키지 캐시입니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-241">The primary package cache.</span></span> <span data-ttu-id="f8657-242">설정하지 않으면 기본적으로 Unix에서는 `$HOME/.nuget/packages`, Windows에서는 `%HOME%\NuGet\Packages`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-242">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="f8657-243">런타임을 로드할 때 공유 호스트에서 사용할 서비스 인덱스의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-243">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="f8657-244">.NET Core 도구 사용에 대한 데이터를 수집하여 Microsoft에 전송할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-244">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="f8657-245">원격 분석 기능을 옵트아웃하려면 `true`(값 `true`, `1` 또는 `yes` 허용)로 설정하고, 원격 분석 기능을 옵트인하려면 `false`(값 `false`, `0` 또는 `no` 허용)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-245">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted); otherwise, set to `false` to opt-in to the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="f8657-246">설정하지 않으면 기본적으로 `false`이고 원격 분석 기능은 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8657-246">If not set, the defaults is `false`, and the telemetry feature is active.</span></span>

---
