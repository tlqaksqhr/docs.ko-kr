---
title: .NET Core Global Tool
description: .NET Core Global Tool의 개요와 사용 가능한 .NET Core CLI 명령입니다.
author: KathleenDollard
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 077ffd53f1ba2988c80a637aaa109a66139736b0
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34697094"
---
# <a name="net-core-global-tools-overview"></a><span data-ttu-id="f07ec-103">.NET Core Global Tool 개요</span><span class="sxs-lookup"><span data-stu-id="f07ec-103">.NET Core Global Tools overview</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

<span data-ttu-id="f07ec-104">.NET Core Global Tool은 콘솔 응용 프로그램을 포함하는 특별한 NuGet 패키지입니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-104">A .NET Core Global Tool is a special NuGet package that contains a console application.</span></span> <span data-ttu-id="f07ec-105">Global Tool은 컴퓨터에서 PATH 환경 변수 또는 사용자 지정 위치에 포함된 기본 위치에 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-105">A Global Tool can be installed on your machine on a default location that is included in the PATH environment variable or on a custom location.</span></span>

<span data-ttu-id="f07ec-106">.NET Core Global Tool을 사용하려는 경우:</span><span class="sxs-lookup"><span data-stu-id="f07ec-106">If you want to use a .NET Core Global Tool:</span></span>

* <span data-ttu-id="f07ec-107">도구에 대한 정보를 찾습니다(일반적으로 웹 사이트 또는 GitHub 페이지).</span><span class="sxs-lookup"><span data-stu-id="f07ec-107">Find information about the tool (usually a website or GitHub page).</span></span>
* <span data-ttu-id="f07ec-108">홈에서 피드의 작성자 및 통계를 확인합니다(일반적으로 NuGet.org).</span><span class="sxs-lookup"><span data-stu-id="f07ec-108">Check the author and statistics in the home for the feed (usually NuGet.org).</span></span>
* <span data-ttu-id="f07ec-109">도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-109">Install the tool.</span></span>
* <span data-ttu-id="f07ec-110">도구를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-110">Call the tool.</span></span>
* <span data-ttu-id="f07ec-111">도구를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-111">Update the tool.</span></span>
* <span data-ttu-id="f07ec-112">도구를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-112">Uninstall the tool.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f07ec-113">.NET Core Global Tool이 경로에 나타나고 완전 신뢰 상태로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-113">.NET Core Global Tools appear on your path and run in full trust.</span></span> <span data-ttu-id="f07ec-114">작성자를 신뢰하지 않는 경우 .NET Core Global Tool을 설치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-114">Do not install .NET Core Global Tools unless you trust the author.</span></span>

## <a name="find-a-net-core-global-tool"></a><span data-ttu-id="f07ec-115">.NET Core Global Tool 찾기</span><span class="sxs-lookup"><span data-stu-id="f07ec-115">Find a .NET Core Global Tool</span></span>

<span data-ttu-id="f07ec-116">현재 .NET Core CLI(명령줄 인터페이스)에는 Global Tool 검색 기능이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-116">Currently, there isn't a Global Tool search feature in the .NET Core Command-line Interface (CLI).</span></span>

<span data-ttu-id="f07ec-117">[NuGet](https://www.nuget.org)에서 .NET Core Global Tool을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-117">You can find .NET Core Global Tools on [NuGet](https://www.nuget.org).</span></span> <span data-ttu-id="f07ec-118">그러나 NuGet에서는 아직 .NET Core Global Tool을 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-118">However, NuGet doesn't yet allow you to search specifically for .NET Core Global Tools.</span></span>

<span data-ttu-id="f07ec-119">블로그 게시물 또는 [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools) GitHub 리포지토리에서 도구 권장 사항을 찾을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-119">You may also find tool recommendations in blog posts or in the [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools) GitHub repository.</span></span>

<span data-ttu-id="f07ec-120">[aspnet/DotNetTools](https://github.com/aspnet/DotNetTools/) GitHub 리포지토리에서 ASP.NET 팀이 만든 Global Tool의 소스 코드를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-120">You can also see the source code for the Global Tools created by the ASP.NET team at the [aspnet/DotNetTools](https://github.com/aspnet/DotNetTools/) GitHub repository.</span></span>

## <a name="check-the-author-and-statistics"></a><span data-ttu-id="f07ec-121">작성자 및 통계 확인</span><span class="sxs-lookup"><span data-stu-id="f07ec-121">Check the author and statistics</span></span>

<span data-ttu-id="f07ec-122">.NET Core Global Tool은 완전 신뢰 상태로 실행되며 일반적으로 사용자 경로에 설치되므로 매우 강력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-122">Since .NET Core Global Tools run in full trust and are generally installed on your path, they can be very powerful.</span></span> <span data-ttu-id="f07ec-123">신뢰할 수 없는 사용자의 도구를 다운로드하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="f07ec-123">Don't download tools from people you don't trust.</span></span>

<span data-ttu-id="f07ec-124">도구가 NuGet에서 호스팅되는 경우 도구를 검색하여 작성자 및 통계를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-124">If the tool is hosted on NuGet, you can check the author and statistics by searching for the tool.</span></span>

## <a name="install-a-global-tool"></a><span data-ttu-id="f07ec-125">Global Tool 설치</span><span class="sxs-lookup"><span data-stu-id="f07ec-125">Install a Global Tool</span></span>

<span data-ttu-id="f07ec-126">Global Tool을 설치하려면 [dotnet tool install](dotnet-tool-install.md) .NET Core CLI 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-126">To install a Global Tool, you use the [dotnet tool install](dotnet-tool-install.md) .NET Core CLI command.</span></span> <span data-ttu-id="f07ec-127">다음 예제에서는 기본 위치에 Global Tool을 설치하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-127">The following example shows how to install a Global Tool in the default location:</span></span>

```console
dotnet tool install -g dotnetsay
```

<span data-ttu-id="f07ec-128">도구를 설치할 수 없는 경우 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-128">If the tool can't be installed, error messages are displayed.</span></span> <span data-ttu-id="f07ec-129">예상한 피드가 확인되고 있는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-129">Check that the feeds you expected are being checked.</span></span>

<span data-ttu-id="f07ec-130">이전 릴리스 버전 또는 특정 버전의 도구를 설치하려는 경우 다음 형식을 사용하여 버전 번호를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-130">If you're trying to install a pre-release version or a specific version of the tool, you can specify the version number using the following format:</span></span>

```console
dotnet tool install -g <package-name> --version <version-number>
```

<span data-ttu-id="f07ec-131">설치에 성공하면 다음 예와 같이 도구와 설치된 버전을 호출하는 데 사용되는 명령을 보여 주는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-131">If installation is successful, a message is displayed showing the command used to call the tool and the version installed, similar to the following example:</span></span>

```
You can invoke the tool using the following command: dotnetsay
Tool 'dotnetsay' (version '2.0.0') was successfully installed.
```

<span data-ttu-id="f07ec-132">Global Tool은 기본 디렉터리 또는 특정 위치에 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-132">Global Tools can be installed in the default directory or in a specific location.</span></span> <span data-ttu-id="f07ec-133">기본 디렉터리는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-133">The default directories are:</span></span>

| <span data-ttu-id="f07ec-134">OS</span><span class="sxs-lookup"><span data-stu-id="f07ec-134">OS</span></span>          | <span data-ttu-id="f07ec-135">Path</span><span class="sxs-lookup"><span data-stu-id="f07ec-135">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="f07ec-136">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="f07ec-136">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="f07ec-137">Windows</span><span class="sxs-lookup"><span data-stu-id="f07ec-137">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="f07ec-138">이러한 위치는 SDK를 처음 실행할 때 사용자 경로에 추가되므로 설치된 Global Tool을 직접 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-138">These locations are added to the user's path when the SDK is first run, so Global Tools installed there can be called directly.</span></span>

<span data-ttu-id="f07ec-139">Global Tool은 컴퓨터 전체가 아니라 사용자별 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-139">Note that the Global Tools are user-specific, not machine global.</span></span> <span data-ttu-id="f07ec-140">사용자별 도구라는 것은 컴퓨터의 모든 사용자가 사용할 수 있는 Global Tool을 설치할 수 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-140">Being user-specific means you cannot install a Global Tool that is available to all users of the machine.</span></span> <span data-ttu-id="f07ec-141">이 도구는 도구가 설치된 각 사용자 프로필에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-141">The tool is only available for each user profile where the tool was installed.</span></span>

<span data-ttu-id="f07ec-142">Global Tool을 특정 디렉터리에 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-142">Global Tools can also be installed in a specific directory.</span></span> <span data-ttu-id="f07ec-143">특정 디렉터리에 설치된 경우 사용자는 경로에 해당 디렉터리를 포함하거나, 지정된 디렉터리로 명령을 호출하거나, 지정된 디렉터리 내에서 도구를 호출하여 명령을 사용할 수 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-143">When installed in a specific directory, the user must ensure the command is available, by including that directory in the path, by calling the command with the directory specified, or calling the tool from within the specified directory.</span></span>
<span data-ttu-id="f07ec-144">이 경우 .NET Core CLI는 이 위치를 PATH 환경 변수에 자동으로 추가하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-144">In this case, the .NET Core CLI doesn't add this location automatically to the PATH environment variable.</span></span>

## <a name="use-the-tool"></a><span data-ttu-id="f07ec-145">도구 사용</span><span class="sxs-lookup"><span data-stu-id="f07ec-145">Use the tool</span></span>

<span data-ttu-id="f07ec-146">도구가 설치되면 명령을 사용하여 도구를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-146">Once the tool is installed, you can call it by using its command.</span></span> <span data-ttu-id="f07ec-147">명령이 패키지 이름과 같지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-147">Note that the command may not be the same as the package name.</span></span>

<span data-ttu-id="f07ec-148">명령이 `dotnetsay`인 경우 다음을 사용하여 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-148">If the command is `dotnetsay`, you call it with:</span></span>

```console
dotnetsay
```

<span data-ttu-id="f07ec-149">도구 작성자가 도구를 `dotnet` 프롬프트 컨텍스트에 표시하려면 도구를 다음과 같이 `dotnet <command>`로 호출하는 방식으로 작성했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-149">If the tool author wanted the tool to appear in the context of the `dotnet` prompt, they may have written it in a way that you call it as `dotnet <command>`, such as:</span></span>

```console
dotnet doc
```

<span data-ttu-id="f07ec-150">[dotnet tool list](dotnet-tool-list.md) 명령을 사용하여 설치된 패키지를 나열하면 설치된 Global Tool 패키지에 포함된 도구를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-150">You can find which tools are included in an installed Global Tool package by listing the installed packages using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

<span data-ttu-id="f07ec-151">도구의 웹 사이트에서 사용 지침을 찾거나 다음 명령 중 하나를 입력할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-151">You can also look for usage instructions at the tool's website or by typing one of the following commands:</span></span>

```console
<command> --help
dotnet <command> --help
```

### <a name="what-could-go-wrong"></a><span data-ttu-id="f07ec-152">발생 가능한 문제</span><span class="sxs-lookup"><span data-stu-id="f07ec-152">What could go wrong</span></span>

<span data-ttu-id="f07ec-153">Global Tool은 [프레임워크 종속 응용 프로그램](../deploying/index.md#framework-dependent-deployments-fdd)입니다. 즉, 컴퓨터에 설치된 .NET Core 런타임에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-153">Global Tools are [framework-dependent applications](../deploying/index.md#framework-dependent-deployments-fdd), which means they rely on a .NET Core runtime installed on your machine.</span></span> <span data-ttu-id="f07ec-154">예상된 런타임을 찾을 수 없으면 다음과 같은 일반적인 .NET Core 런타임 롤포워드 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-154">If the expected runtime is not found, they follow normal .NET Core runtime roll-forward rules such as:</span></span>

* <span data-ttu-id="f07ec-155">응용 프로그램은 지정된 주 및 부 버전의 가장 높은 패치 릴리스로 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-155">An application rolls forward to the highest patch release of the specified major and minor version.</span></span>
* <span data-ttu-id="f07ec-156">일치하는 주 및 부 버전 번호와 일치하는 런타임이 없으면 다음으로 높은 부 버전이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-156">If there is no matching runtime with a matching major and minor version number, the next higher minor version is used.</span></span>
* <span data-ttu-id="f07ec-157">런타임의 미리 보기 버전 간 또는 미리 보기 버전과 릴리스 버전 간에는 롤포워드가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-157">Roll forward doesn't occur between preview versions of the runtime or between preview versions and release versions.</span></span> <span data-ttu-id="f07ec-158">따라서 미리 보기 버전을 사용하여 만든 Global Tool은 작성자가 다시 빌드하여 다시 게시하고 다시 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-158">Thus, Global Tools created using preview versions must be rebuilt and republished by the author and reinstalled.</span></span>
* <span data-ttu-id="f07ec-159">.NET Core 2.1 미리 보기 1에서 만든 Global Tool에서 추가 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-159">Additional issues can occur with Global Tools created in .NET Core 2.1 Preview 1.</span></span> <span data-ttu-id="f07ec-160">자세한 내용은 [.NET Core 2.1 미리 보기 2 알려진 문제](https://github.com/dotnet/core/blob/master/release-notes/2.1/Preview/2.1.0-preview2-known-issues.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f07ec-160">For more information, see [.NET Core 2.1 Preview 2 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/2.1/Preview/2.1.0-preview2-known-issues.md).</span></span>

<span data-ttu-id="f07ec-161">응용 프로그램이 적절한 런타임을 찾을 수 없으면 실행에 실패하고 오류를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-161">If an application cannot find an appropriate runtime, it fails to run and reports an error.</span></span>

<span data-ttu-id="f07ec-162">발생할 수 있는 또 다른 문제는 이전 미리 보기에서 만들어진 Global Tool이 현재 설치된 .NET Core 런타임으로 실행되지 않는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-162">Another issue that might happen is that a Global Tool that was created during an earlier preview may not run with your currently installed .NET Core runtimes.</span></span> <span data-ttu-id="f07ec-163">다음 명령을 사용하여 컴퓨터에 설치된 런타임을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-163">You can see which runtimes are installed on your machine using the following command:</span></span>

```console
dotnet --list-runtimes
```

<span data-ttu-id="f07ec-164">Global Tool 작성자에게 문의하여 업데이트된 버전 번호로 NuGet에 해당 도구 패키지를 다시 컴파일하고 다시 게시할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-164">Contact the author of the Global Tool and see if they can recompile and republish their tool package to NuGet with an updated version number.</span></span> <span data-ttu-id="f07ec-165">NuGet에서 패키지를 업데이트하면 복사본을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-165">Once they have updated the package on NuGet, you can update your copy.</span></span>

<span data-ttu-id="f07ec-166">.NET Core CLI는 처음 사용 시 PATH 환경 변수에 기본 위치를 추가하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-166">The .NET Core CLI tries to add the default locations to the PATH environment variable on its first usage.</span></span> <span data-ttu-id="f07ec-167">그러나 다음과 같이 위치가 PATH에 자동으로 추가되지 않는 몇 가지 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-167">However, there are a couple of scenarios where the location might not be added to PATH automatically, such as:</span></span>

* <span data-ttu-id="f07ec-168">`DOTNET_SKIP_FIRST_TIME_EXPERIENCE` 환경 변수를 설정한 경우</span><span class="sxs-lookup"><span data-stu-id="f07ec-168">If you've set the `DOTNET_SKIP_FIRST_TIME_EXPERIENCE` environment variable.</span></span>
* <span data-ttu-id="f07ec-169">macOS에서 *.tar.gz* 파일을 사용하여 NET Core SDK를 설치하고 *.pkg* 파일을 설치하지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="f07ec-169">On macOS, if you've installed the .NET Core SDK using *.tar.gz* files and not *.pkg*.</span></span>
* <span data-ttu-id="f07ec-170">Linux에서는 셸 환경 파일을 편집하여 PATH를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-170">On Linux, you need to edit the shell environment file to configure the PATH.</span></span>

## <a name="other-cli-commands"></a><span data-ttu-id="f07ec-171">기타 CLI 명령</span><span class="sxs-lookup"><span data-stu-id="f07ec-171">Other CLI commands</span></span>

<span data-ttu-id="f07ec-172">.NET Core SDK에는 .NET Core Global Tool을 지원하는 다른 명령이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-172">The .NET Core SDK contains other commands that support .NET Core Global Tools.</span></span> <span data-ttu-id="f07ec-173">다음 옵션 중 하나와 함께 `dotnet tool` 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-173">Use any of the `dotnet tool` commands with one of the following options:</span></span>

* <span data-ttu-id="f07ec-174">`--global` 또는 `-g`는 명령을 사용자 수준의 Global Tool에 적용 가능함을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-174">`--global` or `-g` specifies that the command is applicable to user-wide Global Tools.</span></span>
* <span data-ttu-id="f07ec-175">`--tool-path`는 Global Tool의 사용자 지정 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-175">`--tool-path` specifies a custom location for Global Tools.</span></span>

<span data-ttu-id="f07ec-176">Global Tool에 사용할 수 있는 명령을 확인하려면:</span><span class="sxs-lookup"><span data-stu-id="f07ec-176">To find out which commands are available for Global Tools:</span></span>

```console
dotnet tool --help
```

<span data-ttu-id="f07ec-177">Global Tool을 업데이트하려면 원래 버전을 제거하고 안정적인 최신 버전으로 다시 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-177">Updating a Global Tool involves uninstalling and reinstalling it with the latest stable version.</span></span> <span data-ttu-id="f07ec-178">Global Tool을 업데이트하려면 [dotnet tool update](dotnet-tool-update.md) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-178">To update a Global Tool, use the [dotnet tool update](dotnet-tool-update.md) command:</span></span>

```console
dotnet tool update -g <packagename>
```

<span data-ttu-id="f07ec-179">[dotnet tool uninstall](dotnet-tool-uninstall.md)을 사용하여 Global Tool을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-179">Remove a Global Tool using the [dotnet tool uninstall](dotnet-tool-uninstall.md):</span></span>

```console
dotnet tool uninstall -g <packagename>
```

<span data-ttu-id="f07ec-180">현재 컴퓨터에 설치된 모든 Global Tool과 해당 버전 및 명령을 표시하려면 [dotnet tool list](dotnet-tool-list.md) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f07ec-180">To display all of the Global Tools currently installed on the machine, along with their version and commands, use the [dotnet tool list](dotnet-tool-list.md) command:</span></span>

```console
dotnet tool list -g
```