---
title: Linux에서 .NET Core의 필수 구성 요소
description: Linux 컴퓨터에서 .NET Core 응용 프로그램을 개발, 배포 및 실행하기 위해 지원되는 Linux 버전 및 .NET Core 종속성입니다.
author: jralexander
ms.author: johalex
ms.date: 04/19/2018
ms.topic: conceptual
ms.prod: dotnet-core
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: 9d986ed56bbc6f803988fde4b5500cd5d5364050
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="prerequisites-for-net-core-on-linux"></a><span data-ttu-id="0fdf8-103">Linux에서 .NET Core의 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="0fdf8-103">Prerequisites for .NET Core on Linux</span></span>

<span data-ttu-id="0fdf8-104">이 문서에서는 Linux에서 .NET Core 응용 프로그램을 개발하는 데 필요한 종속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-104">This article shows the dependencies needed to develop .NET Core applications on Linux.</span></span> <span data-ttu-id="0fdf8-105">다음에 나오는 지원되는 Linux 배포/버전 및 종속성은 Linux에서 .NET Core 앱을 개발하기 위한 두 가지 방법에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-105">The supported Linux distributions/versions, and dependencies that follow apply to the two ways of developing .NET Core apps on Linux:</span></span>

* [<span data-ttu-id="0fdf8-106">즐겨 찾는 편집기를 사용하는 명령줄</span><span class="sxs-lookup"><span data-stu-id="0fdf8-106">Command-line with your favorite editor</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="0fdf8-107">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="0fdf8-107">Visual Studio Code</span></span>](https://code.visualstudio.com/)

> [!NOTE]
> <span data-ttu-id="0fdf8-108">.NET Core SDK 패키지는 프로덕션 서버/환경에서 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-108">The .NET Core SDK package is not required for production servers/environments.</span></span> <span data-ttu-id="0fdf8-109">.NET Core 런타임 패키지만 프로덕션 환경에 배포된 앱에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-109">Only the .NET Core runtime package is needed for apps deployed to production environments.</span></span> <span data-ttu-id="0fdf8-110">NET Core 런타임은 자체 포함된 배포의 일부로 앱으로 배포되지만 프레임워크 종속 배포된 앱에 대해 별도로 배포되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-110">The .NET Core runtime is deployed with apps as part of a self-contained deployment, however, it must be deployed for Framework-dependent deployed apps separately.</span></span> <span data-ttu-id="0fdf8-111">프레임워크 종속 및 자체 포함된 배포 형식에 대한 자세한 내용은 [.NET Core 응용 프로그램 배포](./deploying/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-111">For more information about framework-dependent and self-contained deployment types, see [.NET Core application deployment](./deploying/index.md).</span></span> <span data-ttu-id="0fdf8-112">또한 특정 지침은 [자체 포함된 Linux 응용 프로그램](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-112">Also see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) for specific guidelines.</span></span>

## <a name="supported-linux-versions"></a><span data-ttu-id="0fdf8-113">지원되는 Linux 버전</span><span class="sxs-lookup"><span data-stu-id="0fdf8-113">Supported Linux versions</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="0fdf8-114">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="0fdf8-114">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="0fdf8-115">.NET Core 2.x는 단일 운영 체제로 Linux를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-115">.NET Core 2.x treats Linux as a single operating system.</span></span> <span data-ttu-id="0fdf8-116">지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처당)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-116">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="0fdf8-117">.NET Core 2.x는 다음 Linux 64비트(`x86_64` 또는 `amd64`) 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-117">NET Core 2.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

* <span data-ttu-id="0fdf8-118">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="0fdf8-118">Red Hat Enterprise Linux 7</span></span>
* <span data-ttu-id="0fdf8-119">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="0fdf8-119">CentOS 7</span></span>
* <span data-ttu-id="0fdf8-120">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="0fdf8-120">Oracle Linux 7</span></span>
* <span data-ttu-id="0fdf8-121">Fedora 27, 26</span><span class="sxs-lookup"><span data-stu-id="0fdf8-121">Fedora 27, 26</span></span>
* <span data-ttu-id="0fdf8-122">Debian 9, 8.7 이상 버전</span><span class="sxs-lookup"><span data-stu-id="0fdf8-122">Debian 9, 8.7 or later versions</span></span>
* <span data-ttu-id="0fdf8-123">Ubuntu 17.10, 16.04, 14.04</span><span class="sxs-lookup"><span data-stu-id="0fdf8-123">Ubuntu 17.10, 16.04, 14.04</span></span>
* <span data-ttu-id="0fdf8-124">Linux Mint 18, 17</span><span class="sxs-lookup"><span data-stu-id="0fdf8-124">Linux Mint 18, 17</span></span>
* <span data-ttu-id="0fdf8-125">openSUSE 42.3 이상 버전</span><span class="sxs-lookup"><span data-stu-id="0fdf8-125">openSUSE 42.3 or later versions</span></span>
* <span data-ttu-id="0fdf8-126">SUSE Enterprise Linux(SLES) 12 서비스 팩 2 이상</span><span class="sxs-lookup"><span data-stu-id="0fdf8-126">SUSE Enterprise Linux (SLES) 12 Service Pack 2 or later</span></span>

<span data-ttu-id="0fdf8-127">지원 OS 버전 중 .NET Core 2.x가 지원되는 운영 체제, 배포 및 버전, 수명 주기 정책 링크의 전체 목록은 [.NET Core 2.x가 지원되는 OS 버전](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-127">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0fdf8-128">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0fdf8-128">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="0fdf8-129">.NET Core 1.x는 다음 Linux 64비트(`x86_64` 또는 `amd64`) 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-129">.NET Core 1.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

* <span data-ttu-id="0fdf8-130">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="0fdf8-130">Red Hat Enterprise Linux 7</span></span>
* <span data-ttu-id="0fdf8-131">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="0fdf8-131">CentOS 7</span></span>
* <span data-ttu-id="0fdf8-132">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="0fdf8-132">Oracle Linux 7</span></span>
* <span data-ttu-id="0fdf8-133">Fedora 26</span><span class="sxs-lookup"><span data-stu-id="0fdf8-133">Fedora 26</span></span>
* <span data-ttu-id="0fdf8-134">Debian 8.2 이상 버전</span><span class="sxs-lookup"><span data-stu-id="0fdf8-134">Debian 8.2 or later versions</span></span>
* <span data-ttu-id="0fdf8-135">Ubuntu 16.04, 14.04</span><span class="sxs-lookup"><span data-stu-id="0fdf8-135">Ubuntu 16.04, 14.04</span></span>
* <span data-ttu-id="0fdf8-136">Linux Mint 18, 17</span><span class="sxs-lookup"><span data-stu-id="0fdf8-136">Linux Mint 18, 17</span></span>
* <span data-ttu-id="0fdf8-137">openSUSE 42.3 이상 버전(.NET Core 1.1)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-137">openSUSE 42.3 or later versions (.NET Core 1.1)</span></span>

<span data-ttu-id="0fdf8-138">지원 OS 버전 중 .NET Core 1.x를 지원하는 운영 체제 및 수명 주기 정책 링크는 [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)(.NET Core 1.x가 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-138">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="0fdf8-139">Linux 배포 종속성</span><span class="sxs-lookup"><span data-stu-id="0fdf8-139">Linux distribution dependencies</span></span>

<span data-ttu-id="0fdf8-140">다음은 예제로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-140">The following are intended to be examples.</span></span> <span data-ttu-id="0fdf8-141">정확한 버전 및 이름은 선택한 Linux 배포에 따라 약간 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-141">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="0fdf8-142">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="0fdf8-142">Ubuntu</span></span>

<span data-ttu-id="0fdf8-143">Ubuntu 배포에는 다음과 같은 라이브러리 설치가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-143">Ubuntu distributions require the following libraries installed:</span></span>

* <span data-ttu-id="0fdf8-144">libunwind8</span><span class="sxs-lookup"><span data-stu-id="0fdf8-144">libunwind8</span></span>
* <span data-ttu-id="0fdf8-145">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="0fdf8-145">liblttng-ust0</span></span>
* <span data-ttu-id="0fdf8-146">libcurl3</span><span class="sxs-lookup"><span data-stu-id="0fdf8-146">libcurl3</span></span>
* <span data-ttu-id="0fdf8-147">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="0fdf8-147">libssl1.0.0</span></span>
* <span data-ttu-id="0fdf8-148">libuuid1</span><span class="sxs-lookup"><span data-stu-id="0fdf8-148">libuuid1</span></span>
* <span data-ttu-id="0fdf8-149">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="0fdf8-149">libkrb5-3</span></span>
* <span data-ttu-id="0fdf8-150">zlib1g</span><span class="sxs-lookup"><span data-stu-id="0fdf8-150">zlib1g</span></span>
* <span data-ttu-id="0fdf8-151">libicu52(14.x용)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-151">libicu52 (for 14.x)</span></span>
* <span data-ttu-id="0fdf8-152">libicu55(16.x용)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-152">libicu55 (for 16.x)</span></span>
* <span data-ttu-id="0fdf8-153">libicu57(17.x용)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-153">libicu57 (for 17.x)</span></span>

### <a name="centos"></a><span data-ttu-id="0fdf8-154">CentOS</span><span class="sxs-lookup"><span data-stu-id="0fdf8-154">CentOS</span></span>

<span data-ttu-id="0fdf8-155">CentOS 배포에는 다음과 같은 라이브러리 설치가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-155">CentOS distributions require the following libraries installed:</span></span>

* <span data-ttu-id="0fdf8-156">libunwind</span><span class="sxs-lookup"><span data-stu-id="0fdf8-156">libunwind</span></span>
* <span data-ttu-id="0fdf8-157">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="0fdf8-157">lttng-ust</span></span>
* <span data-ttu-id="0fdf8-158">libcurl</span><span class="sxs-lookup"><span data-stu-id="0fdf8-158">libcurl</span></span>
* <span data-ttu-id="0fdf8-159">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="0fdf8-159">openssl-libs</span></span>
* <span data-ttu-id="0fdf8-160">libuuid</span><span class="sxs-lookup"><span data-stu-id="0fdf8-160">libuuid</span></span>
* <span data-ttu-id="0fdf8-161">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="0fdf8-161">krb5-libs</span></span>
* <span data-ttu-id="0fdf8-162">libicu</span><span class="sxs-lookup"><span data-stu-id="0fdf8-162">libicu</span></span>
* <span data-ttu-id="0fdf8-163">zlib</span><span class="sxs-lookup"><span data-stu-id="0fdf8-163">zlib</span></span>

<span data-ttu-id="0fdf8-164">종속성에 대한 자세한 내용은 [자체 포함 Linux 응용 프로그램](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-164">For more information about the dependencies, see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

## <a name="installing-net-core-dependencies-with-the-native-installers"></a><span data-ttu-id="0fdf8-165">기본 설치 관리자를 사용하여 .NET Core 종속성 설치</span><span class="sxs-lookup"><span data-stu-id="0fdf8-165">Installing .NET Core dependencies with the native installers</span></span>

<span data-ttu-id="0fdf8-166">.NET Core 기본 설치 관리자는 지원되는 Linux 배포/버전에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-166">.NET Core native installers are available for supported Linux distributions/versions.</span></span> <span data-ttu-id="0fdf8-167">기본 설치 관리자를 사용하려면 서버에 대한 관리자(sudo) 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-167">The native installers require admin (sudo) access to the server.</span></span> <span data-ttu-id="0fdf8-168">기본 설치 관리자를 사용하는 장점은 모든 .NET Core 기본 종속성을 설치한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-168">The advantage of using a native installer is that all of the .NET Core native dependencies are installed.</span></span> <span data-ttu-id="0fdf8-169">기본 설치 관리자는 .NET Core SDK 시스템 차원을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-169">Native installers also install the .NET Core SDK system-wide.</span></span>

<span data-ttu-id="0fdf8-170">Linux에는 두 가지 패키지 선택 항목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-170">On Linux, there are two installer package choices:</span></span>

* <span data-ttu-id="0fdf8-171">피드 기반 패키지 관리자 사용(예: Ubuntu의 경우 apt-get, CentOS/RHEL의 경우 yum).</span><span class="sxs-lookup"><span data-stu-id="0fdf8-171">Using a feed-based package manager, such as apt-get for Ubuntu, or yum for CentOS/RHEL.</span></span>
* <span data-ttu-id="0fdf8-172">패키지 자체 사용(DEB 또는 RPM).</span><span class="sxs-lookup"><span data-stu-id="0fdf8-172">Using the packages themselves, DEB or RPM.</span></span>

### <a name="scripting-installs-with-the-net-core-installer-script"></a><span data-ttu-id="0fdf8-173">.NET Core 설치 관리자 스크립트를 사용하여 설치 스크립팅</span><span class="sxs-lookup"><span data-stu-id="0fdf8-173">Scripting Installs with the .NET Core installer script</span></span>

<span data-ttu-id="0fdf8-174">[dotnet-install 스크립트](./tools/dotnet-install-script.md)는 CLI 도구 체인 및 공유 런타임의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-174">The [dotnet-install scripts](./tools/dotnet-install-script.md) are used to perform a non-admin install of the CLI toolchain and the shared runtime.</span></span> <span data-ttu-id="0fdf8-175">[https://dot.net/v1/dotnet-install.sh](https://dot.net/v1/dotnet-install.sh)에서 스크립트를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-175">You can download the script from [https://dot.net/v1/dotnet-install.sh](https://dot.net/v1/dotnet-install.sh).</span></span>

<span data-ttu-id="0fdf8-176">설치 관리자 bash 스크립트는 자동화 시나리오 및 비관리자 설치에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-176">The installer bash script is used in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="0fdf8-177">또한 이 스크립트는 PowerShell 스위치를 읽으므로 Linux/OS X 시스템에서 스크립트와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-177">This script also reads PowerShell switches, so they can be used with the script on Linux/OS X systems.</span></span>

## <a name="install-net-core-for-supported-red-hat-enterprise-linux-rhel-versions"></a><span data-ttu-id="0fdf8-178">지원되는 RHEL(Red Hat Enterprise Linux) 버전에 대한 .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="0fdf8-178">Install .NET Core for supported Red Hat Enterprise Linux (RHEL) versions</span></span>

<span data-ttu-id="0fdf8-179">지원되는 RHEL 버전에 .NET Core를 설치하려면:</span><span class="sxs-lookup"><span data-stu-id="0fdf8-179">To install .NET Core on supported RHEL versions:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="0fdf8-180">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="0fdf8-180">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="0fdf8-181">최신 설치 정보를 포함하는지 확인하려면 지원되는 RHEL 버전에 대한 [.NET Core 2.x SDK 및 런타임 설치 관리자 지침](https://www.microsoft.com/net/download/linux-package-manager/rhel/sdk-current)을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-181">To ensure you have the latest installation information, follow the [.NET Core 2.x SDK and Runtime Installer instructions](https://www.microsoft.com/net/download/linux-package-manager/rhel/sdk-current) for supported RHEL versions.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0fdf8-182">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0fdf8-182">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="0fdf8-183">**.NET Core 1.1**</span><span class="sxs-lookup"><span data-stu-id="0fdf8-183">**.NET Core 1.1**</span></span>

1. <span data-ttu-id="0fdf8-184">시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-184">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2.  <span data-ttu-id="0fdf8-185">Red Hat Enterprise Linux 설치 정보에서 최신 .NET Core 1.1은 [.NET Core 1.1 시작 가이드](https://access.redhat.com/documentation/en-us/net_core/1.1/html/getting_started_guide/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-185">For the latest .NET Core 1.1 on Red Hat Enterprise Linux installation information, see [the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en-us/net_core/1.1/html/getting_started_guide/)</span></span>
     
<span data-ttu-id="0fdf8-186">**.NET Core 1.0**</span><span class="sxs-lookup"><span data-stu-id="0fdf8-186">**.NET Core 1.0**</span></span>

1. <span data-ttu-id="0fdf8-187">시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-187">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2.  <span data-ttu-id="0fdf8-188">Red Hat Enterprise Linux 설치 정보에서 최신 .NET Core 1.0은 [.NET Core 1.0 시작 가이드](https://access.redhat.com/documentation/en-us/net_core/1.0/html/getting_started_guide/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-188">For the latest .NET Core 1.0 on Red Hat Enterprise Linux installation information, see [the .NET Core 1.0 Getting Started Guide](https://access.redhat.com/documentation/en-us/net_core/1.0/html/getting_started_guide/)</span></span>

<span data-ttu-id="0fdf8-189">Red Hat .NET 채널 액세스 등록 도움말은 Red Hat에서 [Chapter 1 of the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/)(.NET Core 1.1 1장 시작 가이드)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-189">For Red Hat .NET channel access registration help, see [Chapter 1 of the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) at Red Hat.</span></span>

---

## <a name="install-net-core-for-supported-ubuntu-and-linux-mint-distributionsversions-64-bit"></a><span data-ttu-id="0fdf8-190">지원되는 Ubuntu 및 Linux Mint 배포/버전(64비트)에 대한 .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="0fdf8-190">Install .NET Core for supported Ubuntu and Linux Mint distributions/versions (64 bit)</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="0fdf8-191">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="0fdf8-191">.NET Core 2.x</span></span>](#tab/netcore2x)

1. <span data-ttu-id="0fdf8-192">시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-192">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="0fdf8-193">지원되는 Ubuntu 및 Linux Mint 배포/버전(64비트)에 대한 .NET Core 2.x 설치:</span><span class="sxs-lookup"><span data-stu-id="0fdf8-193">Install .NET Core 2.x on supported Ubuntu and Linux Mint distributions/versions (64 bit):</span></span>

<span data-ttu-id="0fdf8-194">**.NET Core 2.0**</span><span class="sxs-lookup"><span data-stu-id="0fdf8-194">**.NET Core 2.0**</span></span>

|<span data-ttu-id="0fdf8-195">런타임/SDK</span><span class="sxs-lookup"><span data-stu-id="0fdf8-195">Runtimes / SDKs</span></span>          |<span data-ttu-id="0fdf8-196">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="0fdf8-196">Ubuntu 17.10</span></span>  |<span data-ttu-id="0fdf8-197">Ubuntu 16.04/Linux Mint 18</span><span class="sxs-lookup"><span data-stu-id="0fdf8-197">Ubuntu 16.04 / Linux Mint 18</span></span>|<span data-ttu-id="0fdf8-198">Ubuntu 14.04/Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="0fdf8-198">Ubuntu 14.04 / Linux Mint 17</span></span>|
|-------------------------|--------------|----------------------------|----------------------------|
|<span data-ttu-id="0fdf8-199">.NET Core 런타임 2.0.6</span><span class="sxs-lookup"><span data-stu-id="0fdf8-199">.NET Core Runtime 2.0.6</span></span>  |[<span data-ttu-id="0fdf8-200">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-200">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.6)|[<span data-ttu-id="0fdf8-201">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-201">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.6)          |[<span data-ttu-id="0fdf8-202">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-202">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.6)            |
|<span data-ttu-id="0fdf8-203">.NET Core 런타임 2.0.5</span><span class="sxs-lookup"><span data-stu-id="0fdf8-203">.NET Core Runtime 2.0.5</span></span>  |[<span data-ttu-id="0fdf8-204">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-204">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.5)|[<span data-ttu-id="0fdf8-205">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-205">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.5)          |[<span data-ttu-id="0fdf8-206">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-206">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.5)            |
|<span data-ttu-id="0fdf8-207">.NET Core SDK 2.1.103</span><span class="sxs-lookup"><span data-stu-id="0fdf8-207">.NET Core SDK 2.1.103</span></span>    |[<span data-ttu-id="0fdf8-208">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-208">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.103)|[<span data-ttu-id="0fdf8-209">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-209">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.103)            |[<span data-ttu-id="0fdf8-210">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-210">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.103)            |
|<span data-ttu-id="0fdf8-211">.NET Core SDK 2.0.3</span><span class="sxs-lookup"><span data-stu-id="0fdf8-211">.NET Core SDK 2.0.3</span></span>      |[<span data-ttu-id="0fdf8-212">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-212">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.0.3)|[<span data-ttu-id="0fdf8-213">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-213">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.0.3)          |[<span data-ttu-id="0fdf8-214">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-214">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.0.3)            |

<span data-ttu-id="0fdf8-215">**.NET Core 2.1**</span><span class="sxs-lookup"><span data-stu-id="0fdf8-215">**.NET Core 2.1**</span></span>

>[!IMPORTANT]
> <span data-ttu-id="0fdf8-216">Visual Studio와 함께 .NET Core 2.1을 사용하려면 [Visual Studio 2017 15.7 미리 보기 1 이상을 설치](https://www.visualstudio.com/vs/preview)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-216">To use .NET Core 2.1 with Visual Studio, you need to [install Visual Studio 2017 15.7 Preview 1 or newer](https://www.visualstudio.com/vs/preview).</span></span>

|<span data-ttu-id="0fdf8-217">런타임/SDK</span><span class="sxs-lookup"><span data-stu-id="0fdf8-217">Runtimes / SDKs</span></span>                  |<span data-ttu-id="0fdf8-218">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="0fdf8-218">Ubuntu 17.10</span></span>    |<span data-ttu-id="0fdf8-219">Ubuntu 16.04/Linux Mint 18</span><span class="sxs-lookup"><span data-stu-id="0fdf8-219">Ubuntu 16.04 / Linux Mint 18</span></span>|<span data-ttu-id="0fdf8-220">Ubuntu 14.04/Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="0fdf8-220">Ubuntu 14.04 / Linux Mint 17</span></span>|
|---------------------------------|----------------|----------------------------|----------------------------|
|<span data-ttu-id="0fdf8-221">.NET Core 런타임 2.1.0-미리 보기2</span><span class="sxs-lookup"><span data-stu-id="0fdf8-221">.NET Core Runtime 2.1.0-preview2</span></span> |[<span data-ttu-id="0fdf8-222">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-222">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.1.0-preview2)|[<span data-ttu-id="0fdf8-223">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-223">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.1.0-preview2)            |[<span data-ttu-id="0fdf8-224">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-224">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.1.0-preview2)            |
|<span data-ttu-id="0fdf8-225">.NET Core 런타임 2.1.0-미리 보기1</span><span class="sxs-lookup"><span data-stu-id="0fdf8-225">.NET Core Runtime 2.1.0-preview1</span></span> |[<span data-ttu-id="0fdf8-226">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-226">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.1.0-preview1)|[<span data-ttu-id="0fdf8-227">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-227">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.1.0-preview1)            |[<span data-ttu-id="0fdf8-228">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-228">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.1.0-preview1)            |
|<span data-ttu-id="0fdf8-229">.NET Core SDK 2.1.300-미리 보기2</span><span class="sxs-lookup"><span data-stu-id="0fdf8-229">.NET Core SDK 2.1.300-preview2</span></span>   |[<span data-ttu-id="0fdf8-230">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-230">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.300-preview2)|[<span data-ttu-id="0fdf8-231">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-231">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.300-preview2)            |[<span data-ttu-id="0fdf8-232">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-232">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.300-preview2)
|<span data-ttu-id="0fdf8-233">.NET Core SDK 2.1.300-미리 보기1</span><span class="sxs-lookup"><span data-stu-id="0fdf8-233">.NET Core SDK 2.1.300-preview1</span></span>   |[<span data-ttu-id="0fdf8-234">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-234">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.300-preview1)|[<span data-ttu-id="0fdf8-235">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-235">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.300-preview1)            |[<span data-ttu-id="0fdf8-236">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-236">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.300-preview1)            |


# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0fdf8-237">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0fdf8-237">.NET Core 1.x</span></span>](#tab/netcore1x)

1. <span data-ttu-id="0fdf8-238">시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-238">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="0fdf8-239">지원되는 Ubuntu 및 Linux Mint 배포/버전(64비트)에 대한 .NET Core 1.x 설치:</span><span class="sxs-lookup"><span data-stu-id="0fdf8-239">Install .NET Core 1.x on supported Ubuntu and Linux Mint distributions/versions (64 bit):</span></span>

| <span data-ttu-id="0fdf8-240">런타임/SDK</span><span class="sxs-lookup"><span data-stu-id="0fdf8-240">Runtimes / SDKs</span></span>         |<span data-ttu-id="0fdf8-241">Ubuntu 16.04/Linux Mint 18</span><span class="sxs-lookup"><span data-stu-id="0fdf8-241">Ubuntu 16.04 / Linux Mint 18</span></span>|<span data-ttu-id="0fdf8-242">Ubuntu 14.04/Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="0fdf8-242">Ubuntu 14.04 / Linux Mint 17</span></span>|
|-------------------------|----------------------------|----------------------------|
|<span data-ttu-id="0fdf8-243">.NET Core 런타임 1.1.7</span><span class="sxs-lookup"><span data-stu-id="0fdf8-243">.NET Core Runtime 1.1.7</span></span>  |[<span data-ttu-id="0fdf8-244">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-244">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-ubuntu-16.04-x64-binaries)            |[<span data-ttu-id="0fdf8-245">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-245">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-ubuntu-14.04-x64-binaries)            |
|<span data-ttu-id="0fdf8-246">.NET Core 런타임 1.1.6</span><span class="sxs-lookup"><span data-stu-id="0fdf8-246">.NET Core Runtime 1.1.6</span></span>  |[<span data-ttu-id="0fdf8-247">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-247">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-ubuntu-16.04-x64-binaries)            |[<span data-ttu-id="0fdf8-248">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-248">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-ubuntu-14.04-x64-binaries)            |
|<span data-ttu-id="0fdf8-249">.NET Core 런타임 1.0.10</span><span class="sxs-lookup"><span data-stu-id="0fdf8-249">.NET Core Runtime 1.0.10</span></span> |[<span data-ttu-id="0fdf8-250">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-250">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-ubuntu-16.04-x64-binaries)            |[<span data-ttu-id="0fdf8-251">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-251">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-ubuntu-14.04-x64-binaries)            |
|<span data-ttu-id="0fdf8-252">.NET Core 런타임 1.0.9</span><span class="sxs-lookup"><span data-stu-id="0fdf8-252">.NET Core Runtime 1.0.9</span></span>  |[<span data-ttu-id="0fdf8-253">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-253">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-ubuntu-16.04-x64-binaries)            |[<span data-ttu-id="0fdf8-254">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-254">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-ubuntu-14.04-x64-binaries)            |
|<span data-ttu-id="0fdf8-255">.NET Core SDK 1.1.8</span><span class="sxs-lookup"><span data-stu-id="0fdf8-255">.NET Core SDK 1.1.8</span></span>      |[<span data-ttu-id="0fdf8-256">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-256">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-ubuntu-16.04-x64-binaries)            |[<span data-ttu-id="0fdf8-257">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-257">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-ubuntu-14.04-x64-binaries)            |
|<span data-ttu-id="0fdf8-258">.NET Core SDK 1.1.7</span><span class="sxs-lookup"><span data-stu-id="0fdf8-258">.NET Core SDK 1.1.7</span></span>      |[<span data-ttu-id="0fdf8-259">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-259">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-ubuntu-16.04-x64-binaries)            |[<span data-ttu-id="0fdf8-260">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-260">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-ubuntu-14.04-x64-binaries)            |
|<span data-ttu-id="0fdf8-261">.NET Core SDK 1.0.4</span><span class="sxs-lookup"><span data-stu-id="0fdf8-261">.NET Core SDK 1.0.4</span></span>      |[<span data-ttu-id="0fdf8-262">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-262">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-ubuntu-16.04-x64-binaries)            |[<span data-ttu-id="0fdf8-263">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-263">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-ubuntu-14.04-x64-binaries)            |
|<span data-ttu-id="0fdf8-264">.NET Core SDK 1.0.1</span><span class="sxs-lookup"><span data-stu-id="0fdf8-264">.NET Core SDK 1.0.1</span></span>      |[<span data-ttu-id="0fdf8-265">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-265">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-ubuntu-16.04-x64-binaries)            |[<span data-ttu-id="0fdf8-266">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-266">Install link</span></span>](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-ubuntu-14.04-x64-binaries)            |

---

## <a name="install-net-core-for-supported-debian-versions-64-bit"></a><span data-ttu-id="0fdf8-267">지원되는 Debian 버전(64비트)에 대한 .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="0fdf8-267">Install .NET Core for supported Debian versions (64 bit)</span></span>

<span data-ttu-id="0fdf8-268">지원되는 Debian 버전(64비트)에 .NET Core를 설치하려면:</span><span class="sxs-lookup"><span data-stu-id="0fdf8-268">To install .NET Core on supported Debian versions (64 bit):</span></span>

> [!NOTE]
> <span data-ttu-id="0fdf8-269">tar.gz에서 Linux 시스템을 설치하는 데 사용자 제어 디렉터리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-269">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="0fdf8-270">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="0fdf8-270">.NET Core 2.x</span></span>](#tab/netcore2x)

1. <span data-ttu-id="0fdf8-271">시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-271">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="0fdf8-272">지원되는 Debian 버전(64비트)에 .NET Core 2.x를 설치하려면:</span><span class="sxs-lookup"><span data-stu-id="0fdf8-272">Install .NET Core 2.x on supported Debian versions (64 bit):</span></span>

<span data-ttu-id="0fdf8-273">**.NET Core 2.0**</span><span class="sxs-lookup"><span data-stu-id="0fdf8-273">**.NET Core 2.0**</span></span>

|<span data-ttu-id="0fdf8-274">런타임/SDK</span><span class="sxs-lookup"><span data-stu-id="0fdf8-274">Runtimes / SDKs</span></span>          |<span data-ttu-id="0fdf8-275">Debian 9</span><span class="sxs-lookup"><span data-stu-id="0fdf8-275">Debian 9</span></span>       |<span data-ttu-id="0fdf8-276">Debian 8</span><span class="sxs-lookup"><span data-stu-id="0fdf8-276">Debian 8</span></span>       |
|-------------------------|---------------|---------------|
|<span data-ttu-id="0fdf8-277">.NET Core 런타임 2.0.6</span><span class="sxs-lookup"><span data-stu-id="0fdf8-277">.NET Core Runtime 2.0.6</span></span>  |[<span data-ttu-id="0fdf8-278">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-278">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.6)   |[<span data-ttu-id="0fdf8-279">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-279">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.6)   |
|<span data-ttu-id="0fdf8-280">.NET Core 런타임 2.0.5</span><span class="sxs-lookup"><span data-stu-id="0fdf8-280">.NET Core Runtime 2.0.5</span></span>  |[<span data-ttu-id="0fdf8-281">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-281">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.5)   |[<span data-ttu-id="0fdf8-282">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-282">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.5)   |
|<span data-ttu-id="0fdf8-283">.NET Core SDK 2.1.103</span><span class="sxs-lookup"><span data-stu-id="0fdf8-283">.NET Core SDK 2.1.103</span></span>    |[<span data-ttu-id="0fdf8-284">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-284">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.103)   |[<span data-ttu-id="0fdf8-285">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-285">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.103)   |
|<span data-ttu-id="0fdf8-286">.NET Core SDK 2.0.3</span><span class="sxs-lookup"><span data-stu-id="0fdf8-286">.NET Core SDK 2.0.3</span></span>      |[<span data-ttu-id="0fdf8-287">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-287">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.0.3)   |[<span data-ttu-id="0fdf8-288">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-288">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.0.3)   |

<span data-ttu-id="0fdf8-289">**.NET Core 2.1**</span><span class="sxs-lookup"><span data-stu-id="0fdf8-289">**.NET Core 2.1**</span></span>

>[!IMPORTANT]
> <span data-ttu-id="0fdf8-290">Visual Studio와 함께 .NET Core 2.1을 사용하려면 [Visual Studio 2017 15.7 미리 보기 1 이상을 설치](https://www.visualstudio.com/vs/preview)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-290">To use .NET Core 2.1 with Visual Studio, you need to [install Visual Studio 2017 15.7 Preview 1 or newer](https://www.visualstudio.com/vs/preview).</span></span>

|<span data-ttu-id="0fdf8-291">런타임/SDK</span><span class="sxs-lookup"><span data-stu-id="0fdf8-291">Runtimes / SDKs</span></span>                  |<span data-ttu-id="0fdf8-292">Debian 9</span><span class="sxs-lookup"><span data-stu-id="0fdf8-292">Debian 9</span></span>       |<span data-ttu-id="0fdf8-293">Debian 8</span><span class="sxs-lookup"><span data-stu-id="0fdf8-293">Debian 8</span></span>       |
|---------------------------------|---------------|---------------|
|<span data-ttu-id="0fdf8-294">.NET Core 런타임 2.1.0-미리 보기2</span><span class="sxs-lookup"><span data-stu-id="0fdf8-294">.NET Core Runtime 2.1.0-preview2</span></span> |[<span data-ttu-id="0fdf8-295">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-295">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.1.0-preview2)   |[<span data-ttu-id="0fdf8-296">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-296">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.1.0-preview2)   |
|<span data-ttu-id="0fdf8-297">.NET Core 런타임 2.1.0-미리 보기1</span><span class="sxs-lookup"><span data-stu-id="0fdf8-297">.NET Core Runtime 2.1.0-preview1</span></span> |[<span data-ttu-id="0fdf8-298">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-298">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.1.0-preview1)   |[<span data-ttu-id="0fdf8-299">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-299">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.1.0-preview1)   |
|<span data-ttu-id="0fdf8-300">.NET Core SDK 2.1.300-미리 보기2</span><span class="sxs-lookup"><span data-stu-id="0fdf8-300">.NET Core SDK 2.1.300-preview2</span></span>   |[<span data-ttu-id="0fdf8-301">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-301">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.300-preview2)   |[<span data-ttu-id="0fdf8-302">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-302">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.300-preview2)   |
|<span data-ttu-id="0fdf8-303">.NET Core SDK 2.1.300-미리 보기1</span><span class="sxs-lookup"><span data-stu-id="0fdf8-303">.NET Core SDK 2.1.300-preview1</span></span>   |[<span data-ttu-id="0fdf8-304">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-304">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.300-preview1)   |[<span data-ttu-id="0fdf8-305">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-305">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.300-preview1)   |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0fdf8-306">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0fdf8-306">.NET Core 1.x</span></span>](#tab/netcore1x)

1. <span data-ttu-id="0fdf8-307">시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-307">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="0fdf8-308">Debian 9 또는 Debian 8에 .NET Core 1.x 설치:</span><span class="sxs-lookup"><span data-stu-id="0fdf8-308">Install .NET Core 1.x on Debian 9 or Debian 8:</span></span>

* <span data-ttu-id="0fdf8-309">.NET Core 런타임 1.1.7 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-debian-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-309">.NET Core Runtime 1.1.7 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-debian-x64-binaries)</span></span>
* <span data-ttu-id="0fdf8-310">.NET Core 런타임 1.1.6 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-debian-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-310">.NET Core Runtime 1.1.6 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-debian-x64-binaries)</span></span>
* <span data-ttu-id="0fdf8-311">.NET Core 런타임 1.0.10 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-debian-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-311">.NET Core Runtime 1.0.10 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-debian-x64-binaries)</span></span>
* <span data-ttu-id="0fdf8-312">.NET Core 런타임 1.0.9 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-debian-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-312">.NET Core Runtime 1.0.9 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-debian-x64-binaries)</span></span>
* <span data-ttu-id="0fdf8-313">.NET Core SDK 1.1.8 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-debian-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-313">.NET Core SDK 1.1.8 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-debian-x64-binaries)</span></span>
* <span data-ttu-id="0fdf8-314">.NET Core SDK 1.1.7 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-debian-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-314">.NET Core SDK 1.1.7 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-debian-x64-binaries)</span></span>
* <span data-ttu-id="0fdf8-315">.NET Core SDK 1.0.4 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-debian-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-315">.NET Core SDK 1.0.4 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-debian-x64-binaries)</span></span>
* <span data-ttu-id="0fdf8-316">.NET Core SDK 1.0.1 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-debian-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-316">.NET Core SDK 1.0.1 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-debian-x64-binaries)</span></span>

---

## <a name="install-net-core-for-supported-fedora-versions-64-bit"></a><span data-ttu-id="0fdf8-317">지원되는 Fedora 버전(64비트)에 대한 .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="0fdf8-317">Install .NET Core for supported Fedora versions (64 bit)</span></span>

<span data-ttu-id="0fdf8-318">지원되는 Fedora 버전에 .NET Core를 설치하려면:</span><span class="sxs-lookup"><span data-stu-id="0fdf8-318">To install .NET Core on supported Fedora versions:</span></span>

> [!NOTE]
> <span data-ttu-id="0fdf8-319">tar.gz에서 Linux 시스템을 설치하는 데 사용자 제어 디렉터리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-319">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="0fdf8-320">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="0fdf8-320">.NET Core 2.x</span></span>](#tab/netcore2x)

1. <span data-ttu-id="0fdf8-321">시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-321">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="0fdf8-322">지원되는 Fedora 버전(64비트)에 대한 .NET Core 2.x 설치:</span><span class="sxs-lookup"><span data-stu-id="0fdf8-322">Install .NET Core 2.x on supported Fedora versions (64 bit):</span></span>

<span data-ttu-id="0fdf8-323">**.NET Core 2.0**</span><span class="sxs-lookup"><span data-stu-id="0fdf8-323">**.NET Core 2.0**</span></span>

|<span data-ttu-id="0fdf8-324">런타임/SDK</span><span class="sxs-lookup"><span data-stu-id="0fdf8-324">Runtimes / SDKs</span></span>          |<span data-ttu-id="0fdf8-325">Fedora 26 이상</span><span class="sxs-lookup"><span data-stu-id="0fdf8-325">Fedora 26 or later</span></span> |<span data-ttu-id="0fdf8-326">Fedora 25 이전</span><span class="sxs-lookup"><span data-stu-id="0fdf8-326">Fedora 25 or previous</span></span> |
|-------------------------|-------------------|----------------------|
|<span data-ttu-id="0fdf8-327">.NET Core 런타임 2.0.6</span><span class="sxs-lookup"><span data-stu-id="0fdf8-327">.NET Core Runtime 2.0.6</span></span>  |[<span data-ttu-id="0fdf8-328">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-328">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.6)       |[<span data-ttu-id="0fdf8-329">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-329">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.6)           |
|<span data-ttu-id="0fdf8-330">.NET Core 런타임 2.0.5</span><span class="sxs-lookup"><span data-stu-id="0fdf8-330">.NET Core Runtime 2.0.5</span></span>  |[<span data-ttu-id="0fdf8-331">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-331">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.5)       |[<span data-ttu-id="0fdf8-332">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-332">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.5)           |
|<span data-ttu-id="0fdf8-333">.NET Core SDK 2.1.103</span><span class="sxs-lookup"><span data-stu-id="0fdf8-333">.NET Core SDK 2.1.103</span></span>    |[<span data-ttu-id="0fdf8-334">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-334">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.103)       |[<span data-ttu-id="0fdf8-335">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-335">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.1.103)           |
|<span data-ttu-id="0fdf8-336">.NET Core SDK 2.0.3</span><span class="sxs-lookup"><span data-stu-id="0fdf8-336">.NET Core SDK 2.0.3</span></span>      |[<span data-ttu-id="0fdf8-337">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-337">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.0.3)       |[<span data-ttu-id="0fdf8-338">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-338">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.0.3)           |

<span data-ttu-id="0fdf8-339">**.NET Core 2.1**</span><span class="sxs-lookup"><span data-stu-id="0fdf8-339">**.NET Core 2.1**</span></span>

>[!IMPORTANT]
> <span data-ttu-id="0fdf8-340">Visual Studio와 함께 .NET Core 2.1을 사용하려면 [Visual Studio 2017 15.7 미리 보기 1 이상을 설치](https://www.visualstudio.com/vs/preview)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-340">To use .NET Core 2.1 with Visual Studio, you need to [install Visual Studio 2017 15.7 Preview 1 or newer](https://www.visualstudio.com/vs/preview).</span></span>

|<span data-ttu-id="0fdf8-341">런타임/SDK</span><span class="sxs-lookup"><span data-stu-id="0fdf8-341">Runtimes / SDKs</span></span>                  |<span data-ttu-id="0fdf8-342">Fedora 26 이상</span><span class="sxs-lookup"><span data-stu-id="0fdf8-342">Fedora 26 or later</span></span> |<span data-ttu-id="0fdf8-343">Fedora 25 이전</span><span class="sxs-lookup"><span data-stu-id="0fdf8-343">Fedora 25 or previous</span></span> |
|---------------------------------|-------------------|----------------------|
|<span data-ttu-id="0fdf8-344">.NET Core 런타임 2.1.0-미리 보기2</span><span class="sxs-lookup"><span data-stu-id="0fdf8-344">.NET Core Runtime 2.1.0-preview2</span></span> |[<span data-ttu-id="0fdf8-345">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-345">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.1.0-preview2)       |[<span data-ttu-id="0fdf8-346">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-346">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.1.0-preview2)           |
|<span data-ttu-id="0fdf8-347">.NET Core 런타임 2.1.0-미리 보기1</span><span class="sxs-lookup"><span data-stu-id="0fdf8-347">.NET Core Runtime 2.1.0-preview1</span></span> |[<span data-ttu-id="0fdf8-348">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-348">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.1.0-preview1)       |[<span data-ttu-id="0fdf8-349">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-349">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.1.0-preview1)           |
|<span data-ttu-id="0fdf8-350">.NET Core SDK 2.1.300-미리 보기2</span><span class="sxs-lookup"><span data-stu-id="0fdf8-350">.NET Core SDK 2.1.300-preview2</span></span>   |[<span data-ttu-id="0fdf8-351">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-351">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.300-preview2)       |[<span data-ttu-id="0fdf8-352">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-352">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.1.300-preview2)           |
|<span data-ttu-id="0fdf8-353">.NET Core SDK 2.1.300-미리 보기1</span><span class="sxs-lookup"><span data-stu-id="0fdf8-353">.NET Core SDK 2.1.300-preview1</span></span>   |[<span data-ttu-id="0fdf8-354">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-354">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.300-preview1)       |[<span data-ttu-id="0fdf8-355">설치 링크</span><span class="sxs-lookup"><span data-stu-id="0fdf8-355">Install link</span></span>](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.1.300-preview1)           |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0fdf8-356">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0fdf8-356">.NET Core 1.x</span></span>](#tab/netcore1x)

1. <span data-ttu-id="0fdf8-357">시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-357">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="0fdf8-358">지원되는 Fedora 버전(64비트)에 .NET Core 1.x 설치:</span><span class="sxs-lookup"><span data-stu-id="0fdf8-358">Install .NET Core 1.x supported Fedora versions (64 bit):</span></span>

<span data-ttu-id="0fdf8-359">**Fedora 24**</span><span class="sxs-lookup"><span data-stu-id="0fdf8-359">**Fedora 24**</span></span>

* <span data-ttu-id="0fdf8-360">.NET Core 런타임 1.1.7 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-fedora-24-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-360">.NET Core Runtime 1.1.7 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-fedora-24-x64-binaries)</span></span>
* <span data-ttu-id="0fdf8-361">.NET Core 런타임 1.1.6 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-fedora-24-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-361">.NET Core Runtime 1.1.6 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-fedora-24-x64-binaries)</span></span>
* <span data-ttu-id="0fdf8-362">.NET Core SDK 1.1.8 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-fedora-24-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-362">.NET Core SDK 1.1.8 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-fedora-24-x64-binaries)</span></span>
* <span data-ttu-id="0fdf8-363">.NET Core SDK 1.1.7 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-fedora-24-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-363">.NET Core SDK 1.1.7 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-fedora-24-x64-binaries)</span></span>
* <span data-ttu-id="0fdf8-364">.NET Core SDK 1.0.1 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-debian-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-364">.NET Core SDK 1.0.1 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-debian-x64-binaries)</span></span>

<span data-ttu-id="0fdf8-365">**Fedora 23**</span><span class="sxs-lookup"><span data-stu-id="0fdf8-365">**Fedora 23**</span></span>

* <span data-ttu-id="0fdf8-366">.NET Core 런타임 1.0.9 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-fedora-23-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-366">.NET Core Runtime 1.0.9 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-fedora-23-x64-binaries)</span></span>
* <span data-ttu-id="0fdf8-367">.NET Core SDK 1.0.4 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-fedora-23-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-367">.NET Core SDK 1.0.4 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-fedora-23-x64-binaries)</span></span>
* <span data-ttu-id="0fdf8-368">.NET Core SDK 1.0.1 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-fedora-23-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-368">.NET Core SDK 1.0.1 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-fedora-23-x64-binaries)</span></span>

---

## <a name="install-net-core-for-supported-centos-and-oracle-linux-distributionsversions-64-bit"></a><span data-ttu-id="0fdf8-369">지원되는 CentOS 및 Oracle Linux 배포/버전(64비트)에 대한 .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="0fdf8-369">Install .NET Core for supported CentOS and Oracle Linux distributions/versions (64 bit)</span></span>

<span data-ttu-id="0fdf8-370">지원되는 CentOS 및 Oracle Linux 배포/버전(64비트)에 .NET Core를 설치하려면:</span><span class="sxs-lookup"><span data-stu-id="0fdf8-370">To install .NET Core for supported CentOS and Oracle Linux distributions/versions (64 bit):</span></span>

> [!NOTE]
> <span data-ttu-id="0fdf8-371">tar.gz에서 Linux 시스템을 설치하는 데 사용자 제어 디렉터리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-371">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="0fdf8-372">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="0fdf8-372">.NET Core 2.x</span></span>](#tab/netcore2x)

1. <span data-ttu-id="0fdf8-373">시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-373">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="0fdf8-374">지원되는 CentOS 및 Oracle Linux 배포/버전(64비트)에 .NET Core 2.x 설치:</span><span class="sxs-lookup"><span data-stu-id="0fdf8-374">Install .NET Core 2.x on supported CentOS and Oracle Linux distributions/versions (64 bit):</span></span>

<span data-ttu-id="0fdf8-375">**.NET Core 2.0**</span><span class="sxs-lookup"><span data-stu-id="0fdf8-375">**.NET Core 2.0**</span></span>

* <span data-ttu-id="0fdf8-376">.NET Core 런타임 2.0.6 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.6)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-376">.NET Core Runtime 2.0.6 [install link](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.6)</span></span>
* <span data-ttu-id="0fdf8-377">.NET Core 런타임 2.0.5 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.5)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-377">.NET Core Runtime 2.0.5 [install link](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.5)</span></span>
* <span data-ttu-id="0fdf8-378">.NET Core SDK 2.1.103 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.103)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-378">.NET Core SDK 2.1.103 [install link](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.103)</span></span>
* <span data-ttu-id="0fdf8-379">.NET Core SDK 2.0.3 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.0.3)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-379">.NET Core SDK 2.0.3 [install link](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.0.3)</span></span>
 
<span data-ttu-id="0fdf8-380">**.NET Core 2.1**</span><span class="sxs-lookup"><span data-stu-id="0fdf8-380">**.NET Core 2.1**</span></span>

>[!IMPORTANT]
> <span data-ttu-id="0fdf8-381">Visual Studio와 함께 .NET Core 2.1을 사용하려면 [Visual Studio 2017 15.7 미리 보기 1 이상을 설치](https://www.visualstudio.com/vs/preview/)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-381">To use .NET Core 2.1 with Visual Studio, you need to [install Visual Studio 2017 15.7 Preview 1 or newer](https://www.visualstudio.com/vs/preview/).</span></span>

* <span data-ttu-id="0fdf8-382">.NET Core 런타임 2.1.0-미리 보기2 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.0-preview2)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-382">.NET Core Runtime 2.1.0-preview2 [install link](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.0-preview2)</span></span>
* <span data-ttu-id="0fdf8-383">.NET Core 런타임 2.1.0-미리 보기1 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.0-preview1)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-383">.NET Core Runtime 2.1.0-preview1 [install link](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.0-preview1)</span></span>
* <span data-ttu-id="0fdf8-384">.NET Core SDK 2.1.300-미리 보기2 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.300-preview2)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-384">.NET Core SDK 2.1.300-preview2 [install link](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.300-preview2)</span></span>
* <span data-ttu-id="0fdf8-385">.NET Core SDK 2.1.300-미리 보기1 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.300-preview1)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-385">.NET Core SDK 2.1.300-preview1 [install link](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.300-preview1)</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0fdf8-386">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0fdf8-386">.NET Core 1.x</span></span>](#tab/netcore1x)

1. <span data-ttu-id="0fdf8-387">시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-387">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="0fdf8-388">지원되는 CentOS 및 Oracle Linux 배포/버전(64비트)에 .NET Core 1.x 설치:</span><span class="sxs-lookup"><span data-stu-id="0fdf8-388">Install .NET Core 1.x on supported CentOS and Oracle Linux distributions/versions (64 bit):</span></span>

* <span data-ttu-id="0fdf8-389">.NET Core 런타임 1.1.7 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-centos-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-389">.NET Core Runtime 1.1.7 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-centos-x64-binaries)</span></span>
* <span data-ttu-id="0fdf8-390">.NET Core 런타임 1.1.6 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-centos-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-390">.NET Core Runtime 1.1.6 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-centos-x64-binaries)</span></span>
* <span data-ttu-id="0fdf8-391">.NET Core 런타임 1.0.10 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-centos-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-391">.NET Core Runtime 1.0.10 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-centos-x64-binaries)</span></span>
* <span data-ttu-id="0fdf8-392">.NET Core 런타임 1.0.9 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-centos-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-392">.NET Core Runtime 1.0.9 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-centos-x64-binaries)</span></span>
* <span data-ttu-id="0fdf8-393">.NET Core SDK 1.1.8 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-centos-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-393">.NET Core SDK 1.1.8 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-centos-x64-binaries)</span></span>
* <span data-ttu-id="0fdf8-394">.NET Core SDK 1.1.7 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-centos-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-394">.NET Core SDK 1.1.7 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-centos-x64-binaries)</span></span>
* <span data-ttu-id="0fdf8-395">.NET Core SDK 1.0.4 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-centos-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-395">.NET Core SDK 1.0.4 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-centos-x64-binaries)</span></span>
* <span data-ttu-id="0fdf8-396">.NET Core SDK 1.0.1 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-centos-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-396">.NET Core SDK 1.0.1 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-centos-x64-binaries)</span></span>

---

## <a name="install-net-core-for-supported-suse-linux-enterprise-server-and-opensuse-distributionsversions-64-bit"></a><span data-ttu-id="0fdf8-397">지원되는 SUSE Linux Enterprise Server 및 OpenSUSE 배포/버전(64비트)에 .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="0fdf8-397">Install .NET Core for supported SUSE Linux Enterprise Server and OpenSUSE distributions/versions (64 bit)</span></span>

<span data-ttu-id="0fdf8-398">지원되는 SUSE Linux Enterprise Server 및 OpenSUSE 배포/버전(64비트)에 .NET Core 2.x를 설치하려면:</span><span class="sxs-lookup"><span data-stu-id="0fdf8-398">To install .NET Core 2.x for supported SUSE Linux Enterprise Server and OpenSUSE distributions/versions (64 bit):</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="0fdf8-399">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="0fdf8-399">.NET Core 2.x</span></span>](#tab/netcore2x)

1. <span data-ttu-id="0fdf8-400">시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-400">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="0fdf8-401">지원되는 SUSE Linux Enterprise Server 및 OpenSUSE 배포/버전(64비트)에 .NET Core 2.x 설치:</span><span class="sxs-lookup"><span data-stu-id="0fdf8-401">Install .NET Core 2.x on supported SUSE Linux Enterprise Server and OpenSUSE distributions/versions (64 bit):</span></span>

<span data-ttu-id="0fdf8-402">**.NET Core 2.0**</span><span class="sxs-lookup"><span data-stu-id="0fdf8-402">**.NET Core 2.0**</span></span>

* <span data-ttu-id="0fdf8-403">.NET Core 런타임 2.0.6 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.6)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-403">.NET Core Runtime 2.0.6 [install link](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.6)</span></span>
* <span data-ttu-id="0fdf8-404">.NET Core 런타임 2.0.5 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.5)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-404">.NET Core Runtime 2.0.5 [install link](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.5)</span></span>
* <span data-ttu-id="0fdf8-405">.NET Core SDK 2.1.103 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.103)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-405">.NET Core SDK 2.1.103 [install link](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.103)</span></span>
* <span data-ttu-id="0fdf8-406">.NET Core SDK 2.0.3 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.0.3)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-406">.NET Core SDK 2.0.3 [install link](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.0.3)</span></span>
 
<span data-ttu-id="0fdf8-407">**.NET Core 2.1**</span><span class="sxs-lookup"><span data-stu-id="0fdf8-407">**.NET Core 2.1**</span></span>

>[!IMPORTANT]
> <span data-ttu-id="0fdf8-408">Visual Studio와 함께 .NET Core 2.1을 사용하려면 [Visual Studio 2017 15.7 미리 보기 1 이상을 설치](https://www.visualstudio.com/vs/preview)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-408">To use .NET Core 2.1 with Visual Studio, you need to [install Visual Studio 2017 15.7 Preview 1 or newer](https://www.visualstudio.com/vs/preview).</span></span>

* <span data-ttu-id="0fdf8-409">.NET Core 런타임 2.1.0-미리 보기2 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.0-preview2)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-409">.NET Core Runtime 2.1.0-preview2 [install link](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.0-preview2)</span></span>
* <span data-ttu-id="0fdf8-410">.NET Core 런타임 2.1.0-미리 보기1 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.0-preview1)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-410">.NET Core Runtime 2.1.0-preview1  [install link](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.0-preview1)</span></span>
* <span data-ttu-id="0fdf8-411">.NET Core SDK 2.1.300-미리 보기2 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.300-preview2)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-411">.NET Core SDK 2.1.300-preview2 [install link](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.300-preview2)</span></span>
* <span data-ttu-id="0fdf8-412">.NET Core SDK 2.1.300-미리 보기1 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.300-preview1)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-412">.NET Core SDK 2.1.300-preview1 [install link](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.300-preview1)</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0fdf8-413">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0fdf8-413">.NET Core 1.x</span></span>](#tab/netcore1x)

1. <span data-ttu-id="0fdf8-414">시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-414">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="0fdf8-415">지원되는 SUSE Linux Enterprise Server 및 OpenSUSE 배포/버전(64비트)에 .NET Core 1.x 설치:</span><span class="sxs-lookup"><span data-stu-id="0fdf8-415">Install .NET Core 1.x on supported SUSE Linux Enterprise Server and OpenSUSE distributions/versions (64 bit):</span></span>

<span data-ttu-id="0fdf8-416">**SUSE Linux Enterprise Server 13.2**</span><span class="sxs-lookup"><span data-stu-id="0fdf8-416">**SUSE Linux Enterprise Server 13.2**</span></span>

* <span data-ttu-id="0fdf8-417">.NET Core 런타임 1.1.7 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-opensuse-13.2-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-417">.NET Core Runtime 1.1.7 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-opensuse-13.2-x64-binaries)</span></span>
* <span data-ttu-id="0fdf8-418">.NET Core 런타임 1.1.6 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-opensuse-13.2-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-418">.NET Core Runtime 1.1.6 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-opensuse-13.2-x64-binaries)</span></span>
* <span data-ttu-id="0fdf8-419">.NET Core SDK 1.1.7 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-opensuse-13.2-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-419">.NET Core SDK 1.1.7 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-opensuse-13.2-x64-binaries)</span></span>

<span data-ttu-id="0fdf8-420">**openSUSE 24**</span><span class="sxs-lookup"><span data-stu-id="0fdf8-420">**openSUSE 24**</span></span>

* <span data-ttu-id="0fdf8-421">.NET Core SDK 1.0.4 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-opensuse-24-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-421">.NET Core SDK 1.0.4 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-opensuse-24-x64-binaries)</span></span>
* <span data-ttu-id="0fdf8-422">.NET Core SDK 1.0.1 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-opensuse-24-x64-binaries)</span><span class="sxs-lookup"><span data-stu-id="0fdf8-422">.NET Core SDK 1.0.1 [install link](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-opensuse-24-x64-binaries)</span></span>

---

> [!IMPORTANT]
> <span data-ttu-id="0fdf8-423">지원되는 Linux 배포/버전에 .NET Core 설치에 문제가 있는 경우 설치된 배포/버전에 대한 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0fdf8-423">If you have problems with a .NET Core installation on a supported Linux distribution/version, consult the following topics for your installed distributions/versions:</span></span>
> * [<span data-ttu-id="0fdf8-424">.NET Core 2.1 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="0fdf8-424">.NET Core 2.1 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/2.1)
> * [<span data-ttu-id="0fdf8-425">.NET Core 2.0 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="0fdf8-425">.NET Core 2.0 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/2.0)
> * [<span data-ttu-id="0fdf8-426">.NET Core 1.1 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="0fdf8-426">.NET Core 1.1 known issues</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.1)
> * [<span data-ttu-id="0fdf8-427">.NET Core 1.0 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="0fdf8-427">.NET Core 1.0 known issues</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.0)