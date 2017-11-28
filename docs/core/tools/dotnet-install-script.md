---
title: "dotnet 설치 스크립트"
description: ".NET Core CLI 도구 및 공유 런타임을 설치하는 dotnet-install 스크립트에 대해 알아봅니다."
keywords: "dotnet-install, dotnet-install 스크립트, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 09/11/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: b64e7e6f-ffb4-4fc8-b43b-5731c89479c2
ms.openlocfilehash: 2f15f37016fe824d76b501e4793e0b28bbdbe167
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="5f8c0-104">dotnet-install 스크립트 참조</span><span class="sxs-lookup"><span data-stu-id="5f8c0-104">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="5f8c0-105">이름</span><span class="sxs-lookup"><span data-stu-id="5f8c0-105">Name</span></span>

<span data-ttu-id="5f8c0-106">`dotnet-install.ps1` | `dotnet-install.sh` - .NET Core CLI 도구 및 공유 런타임을 설치하는 데 사용되는 스크립트입니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-106">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core CLI tools and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5f8c0-107">개요</span><span class="sxs-lookup"><span data-stu-id="5f8c0-107">Synopsis</span></span>

<span data-ttu-id="5f8c0-108">Windows:</span><span class="sxs-lookup"><span data-stu-id="5f8c0-108">Windows:</span></span>

`dotnet-install.ps1 [-Channel] [-Version] [-InstallDir] [-Architecture] [-SharedRuntime] [-DryRun] [-NoPath] [-AzureFeed] [-ProxyAddress] [--Verbose] [--Help]`

<span data-ttu-id="5f8c0-109">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="5f8c0-109">macOS/Linux:</span></span>

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture] [--shared-runtime] [--dry-run] [--no-path] [--azure-feed] [--verbose] [--help]`

## <a name="description"></a><span data-ttu-id="5f8c0-110">설명</span><span class="sxs-lookup"><span data-stu-id="5f8c0-110">Description</span></span>

<span data-ttu-id="5f8c0-111">`dotnet-install` 스크립트는 .NET Core CLI 도구 및 공유 런타임을 포함하는 .NET Core SDK의 비관리자 설치를 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-111">The `dotnet-install` scripts are used to perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI tools and the shared runtime.</span></span>

<span data-ttu-id="5f8c0-112">[.NET Core 기본 웹 사이트](https://dot.net)에서 호스팅되는 안정적인 버전을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-112">We recommend that you use the stable version that is hosted on [.NET Core main website](https://dot.net).</span></span> <span data-ttu-id="5f8c0-113">스크립트에 대한 직접 경로는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-113">The direct paths to the scripts are:</span></span>

* <span data-ttu-id="5f8c0-114">https://dot.net/v1/dotnet-install.sh(bash, UNIX)</span><span class="sxs-lookup"><span data-stu-id="5f8c0-114">https://dot.net/v1/dotnet-install.sh (bash, UNIX)</span></span>
* <span data-ttu-id="5f8c0-115">https://dot.net/v1/dotnet-install.ps1(Powershell, Windows)</span><span class="sxs-lookup"><span data-stu-id="5f8c0-115">https://dot.net/v1/dotnet-install.ps1 (Powershell, Windows)</span></span>

<span data-ttu-id="5f8c0-116">이러한 스크립트의 주요 유용성은 자동화 시나리오 및 비관리자 설치입니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-116">The main usefulness of these scripts is in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="5f8c0-117">두 가지 스크립트가 있습니다. 하나는 Windows에서 작동하는 PowerShell 스크립트입니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-117">There are two scripts: One is a PowerShell script that works on Windows.</span></span> <span data-ttu-id="5f8c0-118">다른 스크립트는 Linux/macOS에서 작동하는 bash 스크립트입니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-118">The other script is a bash script that works on Linux/macOS.</span></span> <span data-ttu-id="5f8c0-119">두 스크립트의 동작은 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-119">Both scripts have the same behavior.</span></span> <span data-ttu-id="5f8c0-120">또한 bash 스크립트는 PowerShell 스위치를 읽으므로 Linux/macOS 시스템에서 스크립트와 함께 PowerShell 스위치를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-120">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span> 

<span data-ttu-id="5f8c0-121">설치 스크립트는 CLI 빌드 저장 위치에서 ZIP/tarball 파일을 다운로드하여 기본 위치나 `-InstallDir|--install-dir`로 지정한 위치에 설치를 계속 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-121">The installation scripts download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span> <span data-ttu-id="5f8c0-122">기본적으로 설치 스크립트는 SDK를 다운로드하고 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-122">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="5f8c0-123">공유 런타임만 가져오려는 경우 `--shared-runtime` 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-123">If you wish to only obtain the shared runtime, specify the `--shared-runtime` argument.</span></span> 

<span data-ttu-id="5f8c0-124">기본적으로 스크립트는 현재 세션에 대한 $PATH에 설치 위치를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-124">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="5f8c0-125">`--no-path` 인수를 지정하여 이 기본 동작을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-125">Override this default behavior by specifying the `--no-path` argument.</span></span> 

<span data-ttu-id="5f8c0-126">스크립트를 실행하기 전에 필요한 모든 [종속성](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md)을 설치하세요.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-126">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

<span data-ttu-id="5f8c0-127">`--version` 인수를 사용하여 특정 버전을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-127">You can install a specific version using the `--version` argument.</span></span> <span data-ttu-id="5f8c0-128">버전은 세 부분으로 구성된 버전(예: 1.0.0-13232)으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-128">The version must be specified as a 3-part version (for example, 1.0.0-13232).</span></span> <span data-ttu-id="5f8c0-129">생략하면 `latest` 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-129">If omitted, it uses the `latest` version.</span></span>

## <a name="options"></a><span data-ttu-id="5f8c0-130">옵션</span><span class="sxs-lookup"><span data-stu-id="5f8c0-130">Options</span></span>

`-Channel <CHANNEL>`

<span data-ttu-id="5f8c0-131">설치에 대한 소스 채널을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-131">Specifies the source channel for the installation.</span></span> <span data-ttu-id="5f8c0-132">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-132">The possible values are:</span></span>

- <span data-ttu-id="5f8c0-133">`Current` - 현재 릴리스</span><span class="sxs-lookup"><span data-stu-id="5f8c0-133">`Current` - Current release</span></span>
- <span data-ttu-id="5f8c0-134">`LTS` - 장기 지원 채널(현재 지원되는 릴리스)</span><span class="sxs-lookup"><span data-stu-id="5f8c0-134">`LTS` - Long-Term Support channel (current supported release)</span></span>
- <span data-ttu-id="5f8c0-135">특정 릴리스를 나타내는 X.Y 형식의 두 부분으로 된 버전(예: `2.0` 또는 `1.0`)</span><span class="sxs-lookup"><span data-stu-id="5f8c0-135">Two-part version in X.Y format representing a specific release (for example, `2.0` or `1.0`)</span></span>
- <span data-ttu-id="5f8c0-136">분기 이름[예: `master` 분기에서 온 최신 값의 경우 `release/2.0.0`, `release/2.0.0-preview2` 또는 `master`("bleeding edge" 야간 릴리스)]</span><span class="sxs-lookup"><span data-stu-id="5f8c0-136">Branch name [for example, `release/2.0.0`, `release/2.0.0-preview2`, or `master` for the latest from the `master` branch ("bleeding edge" nightly releases)]</span></span>

<span data-ttu-id="5f8c0-137">기본값은 `LTS`입니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-137">The default value is `LTS`.</span></span> <span data-ttu-id="5f8c0-138">.NET 지원 채널에 대한 자세한 내용은 [.NET Core 지원 주기](https://www.microsoft.com/net/core/support) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-138">For more information on .NET support channels, see the [.NET Core Support Lifecycle](https://www.microsoft.com/net/core/support) topic.</span></span>

`-Version <VERSION>`

<span data-ttu-id="5f8c0-139">특정 빌드 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-139">Represents a specific build version.</span></span> <span data-ttu-id="5f8c0-140">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-140">The possible values are:</span></span>

- <span data-ttu-id="5f8c0-141">`latest` - 채널의 최신 빌드(`-Channel` 옵션과 함께 사용됨)</span><span class="sxs-lookup"><span data-stu-id="5f8c0-141">`latest` - Latest build on the channel (used with the `-Channel` option)</span></span>
- <span data-ttu-id="5f8c0-142">`coherent` - 채널의 일관된 최신 빌드, 안정적인 최신 패키지 조합 사용(분기 이름 `-Channel` 옵션과 함께 사용됨)</span><span class="sxs-lookup"><span data-stu-id="5f8c0-142">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options)</span></span>
- <span data-ttu-id="5f8c0-143">특정 빌드 버전을 나타내는 X.Y.Z 형식의 세 부분으로 구성된 버전이며 `-Channel` 옵션을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-143">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="5f8c0-144">예를 들면 `2.0.0-preview2-006120` 같은 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-144">For example: `2.0.0-preview2-006120`</span></span>

<span data-ttu-id="5f8c0-145">생략하면 `-Version`은 `latest`로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-145">If omitted, `-Version` defaults to `latest`.</span></span>

`-InstallDir <DIRECTORY>`

<span data-ttu-id="5f8c0-146">설치 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-146">Specifies the installation path.</span></span> <span data-ttu-id="5f8c0-147">디렉터리가 없을 경우 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-147">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="5f8c0-148">기본값은 *%LocalAppData%\.dotnet*입니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-148">The default value is *%LocalAppData%\.dotnet*.</span></span> <span data-ttu-id="5f8c0-149">이진 파일은 디렉터리에 직접 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-149">Note that binaries are placed directly in the directory.</span></span>

`-Architecture <ARCHITECTURE>`

<span data-ttu-id="5f8c0-150">설치할 .NET Core 바이너리의 아키텍처입니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-150">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="5f8c0-151">가능한 값은 `auto`, `x64` 및 `x86`입니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-151">Possible values are `auto`, `x64`, and `x86`.</span></span> <span data-ttu-id="5f8c0-152">기본값은 현재 실행 중인 OS 아키텍처를 나타내는 `auto`입니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-152">The default value is `auto`, which represents the currently running OS architecture.</span></span>

`-SharedRuntime`

<span data-ttu-id="5f8c0-153">설정되면 이 스위치는 설치를 공유 런타임으로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-153">If set, this switch limits installation to the shared runtime.</span></span> <span data-ttu-id="5f8c0-154">전체 SDK가 설치되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-154">The entire SDK isn't installed.</span></span>

`-DryRun`

<span data-ttu-id="5f8c0-155">설정된 경우 스크립트에서 설치를 수행하지는 않지만 대신 현재 요청된 버전의 .NET Core CLI를 일관되게 설치하기 위해 사용할 명령줄을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-155">If set, the script won't perform the installation; but instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="5f8c0-156">예를 들어 `latest` 버전을 지정하면 빌드 스크립트에서 이 명령을 결정적으로 사용할 수 있도록 특정 버전에 대한 링크를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-156">For example if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="5f8c0-157">또한 직접 설치하거나 다운로드하는 것을 선호하는 경우 이진 파일 위치를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-157">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

`-NoPath`

<span data-ttu-id="5f8c0-158">설정된 경우 현재 세션에 대한 경로로 접두사/installdir을 내보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-158">If set, the prefix/installdir are not exported to the path for the current session.</span></span> <span data-ttu-id="5f8c0-159">기본적으로 스크립트는 경로를 수정하여, 설치 후 CLI 도구를 즉시 사용할 수 있게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-159">By default, the script will modify the PATH, which makes the CLI tools available immediately after install.</span></span>

`-AzureFeed`

<span data-ttu-id="5f8c0-160">설치 관리자에 대한 Azure 피드의 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-160">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="5f8c0-161">이 값은 변경하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-161">It isn't recommended that you change this value.</span></span> <span data-ttu-id="5f8c0-162">기본값은 `https://dotnetcli.azureedge.net/dotnet`입니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-162">The default is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

`-ProxyAddress`

<span data-ttu-id="5f8c0-163">설정된 경우 설치 관리자에서 웹 요청을 만들 때 프록시를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-163">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="5f8c0-164">(Windows에만 유효함)</span><span class="sxs-lookup"><span data-stu-id="5f8c0-164">(Only valid for Windows)</span></span>

`--verbose`

<span data-ttu-id="5f8c0-165">진단 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-165">Display diagnostics information.</span></span>

`--help`

<span data-ttu-id="5f8c0-166">스크립트에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-166">Prints out help for the script.</span></span>

## <a name="examples"></a><span data-ttu-id="5f8c0-167">예제</span><span class="sxs-lookup"><span data-stu-id="5f8c0-167">Examples</span></span>

<span data-ttu-id="5f8c0-168">기본 위치에 최신 LTS(장기 지원) 버전을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-168">Install the latest long-term supported (LTS) version to the default location:</span></span>

<span data-ttu-id="5f8c0-169">Windows:</span><span class="sxs-lookup"><span data-stu-id="5f8c0-169">Windows:</span></span>

`./dotnet-install.ps1 -Channel LTS`

<span data-ttu-id="5f8c0-170">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="5f8c0-170">macOS/Linux:</span></span>

`./dotnet-install.sh --channel LTS`

<span data-ttu-id="5f8c0-171">지정된 위치에 2.0 채널의 최신 버전을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-171">Install the latest version from 2.0 channel to the specified location:</span></span>

<span data-ttu-id="5f8c0-172">Windows:</span><span class="sxs-lookup"><span data-stu-id="5f8c0-172">Windows:</span></span>

`./dotnet-install.ps1 -Channel 2.0 -InstallDir C:\cli`

<span data-ttu-id="5f8c0-173">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="5f8c0-173">macOS/Linux:</span></span>

`./dotnet-install.sh --channel 2.0 --install-dir ~/cli`

<span data-ttu-id="5f8c0-174">1.1.0 버전의 공유 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-174">Install the 1.1.0 version of the shared runtime:</span></span>

<span data-ttu-id="5f8c0-175">Windows:</span><span class="sxs-lookup"><span data-stu-id="5f8c0-175">Windows:</span></span>

`./dotnet-install.ps1 -SharedRuntime -Version 1.1.0`

<span data-ttu-id="5f8c0-176">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="5f8c0-176">macOS/Linux:</span></span>

`./dotnet-install.sh --shared-runtime --version 1.1.0`

<span data-ttu-id="5f8c0-177">스크립트 가져와서 .NET Core CLI one-liner 예제를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8c0-177">Obtain script and install .NET Core CLI one-liner examples:</span></span>

<span data-ttu-id="5f8c0-178">Windows:</span><span class="sxs-lookup"><span data-stu-id="5f8c0-178">Windows:</span></span>

`@powershell -NoProfile -ExecutionPolicy unrestricted -Command "&([scriptblock]::Create((Invoke-WebRequest -useb 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"`

<span data-ttu-id="5f8c0-179">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="5f8c0-179">macOS/Linux:</span></span>

`curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>`

## <a name="see-also"></a><span data-ttu-id="5f8c0-180">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5f8c0-180">See also</span></span>

<span data-ttu-id="5f8c0-181">[.NET Core 릴리스](https://github.com/dotnet/core/releases) </span><span class="sxs-lookup"><span data-stu-id="5f8c0-181">[.NET Core releases](https://github.com/dotnet/core/releases) </span></span>  
[<span data-ttu-id="5f8c0-182">.NET Core 런타임 및 SDK 다운로드 아카이브</span><span class="sxs-lookup"><span data-stu-id="5f8c0-182">.NET Core Runtime and SDK download archive</span></span>](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
