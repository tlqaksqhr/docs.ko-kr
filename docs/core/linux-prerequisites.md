---
title: "Linux에서 .NET Core의 필수 구성 요소"
description: "Linux 컴퓨터에서 .NET Core 응용 프로그램을 개발, 배포 및 실행하기 위해 지원되는 Linux 버전 및 .NET Core 종속성입니다."
keywords: .NET, .NET Core, Linux, debian, ubuntu, RHEL, centOS,
author: jralexander
ms.author: johalex
ms.date: 12/06/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.workload:
- dotnetcore
ms.openlocfilehash: 913d3869559b10af508e695a06d06021f8f90175
ms.sourcegitcommit: adcf9bdafeaa6bc243af7bf70b45f3df954f256a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2018
---
# <a name="prerequisites-for-net-core-on-linux"></a><span data-ttu-id="d60f1-104">Linux에서 .NET Core의 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="d60f1-104">Prerequisites for .NET Core on Linux</span></span>

<span data-ttu-id="d60f1-105">이 문서에서는 Linux에서 .NET Core 응용 프로그램을 개발하는 데 필요한 종속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-105">This article shows the dependencies needed to develop .NET Core applications on Linux.</span></span> <span data-ttu-id="d60f1-106">다음에 나오는 지원되는 Linux 배포/버전 및 종속성은 Linux에서 .NET Core 앱을 개발하기 위한 두 가지 방법에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-106">The supported Linux distributions/versions, and dependencies that follow apply to the two ways of developing .NET Core apps on Linux:</span></span>

* [<span data-ttu-id="d60f1-107">즐겨 찾는 편집기를 사용하는 명령줄</span><span class="sxs-lookup"><span data-stu-id="d60f1-107">Command-line with your favorite editor</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="d60f1-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d60f1-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

## <a name="supported-linux-versions"></a><span data-ttu-id="d60f1-109">지원되는 Linux 버전</span><span class="sxs-lookup"><span data-stu-id="d60f1-109">Supported Linux versions</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d60f1-110">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d60f1-110">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="d60f1-111">.NET Core 2.0은 단일 운영 체제로 Linux를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-111">.NET Core 2.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="d60f1-112">지원되는 Linux 배포판에 대한 단일 Linux 빌드(칩 아키텍처 당)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-112">There is a single Linux build (per chip architecture) for supported Linux distros.</span></span>

<span data-ttu-id="d60f1-113">.NET Core 2.x는 다음 Linux 64비트(`x86_64` 또는 `amd64`) 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-113">NET Core 2.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

 * <span data-ttu-id="d60f1-114">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="d60f1-114">Red Hat Enterprise Linux 7</span></span>
 * <span data-ttu-id="d60f1-115">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="d60f1-115">CentOS 7</span></span>
 * <span data-ttu-id="d60f1-116">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="d60f1-116">Oracle Linux 7</span></span>
 * <span data-ttu-id="d60f1-117">Fedora 25, Fedora 26</span><span class="sxs-lookup"><span data-stu-id="d60f1-117">Fedora 25, Fedora 26</span></span>
 * <span data-ttu-id="d60f1-118">Debian 8.7 이상 버전</span><span class="sxs-lookup"><span data-stu-id="d60f1-118">Debian 8.7 or later versions</span></span> 
 * <span data-ttu-id="d60f1-119">Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="d60f1-119">Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04</span></span>
 * <span data-ttu-id="d60f1-120">Linux Mint 18, Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="d60f1-120">Linux Mint 18, Linux Mint 17</span></span>
 * <span data-ttu-id="d60f1-121">openSUSE 42.2 이상 버전</span><span class="sxs-lookup"><span data-stu-id="d60f1-121">openSUSE 42.2 or later versions</span></span>
 * <span data-ttu-id="d60f1-122">SLES(SUSE Enterprise Linux) 12 SP2 이상 버전</span><span class="sxs-lookup"><span data-stu-id="d60f1-122">SUSE Enterprise Linux (SLES) 12 SP2 or later versions</span></span>

<span data-ttu-id="d60f1-123">지원 OS 버전 중 .NET Core 2.x를 지원하는 운영 체제 및 수명 주기 정책 링크는 [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)(.NET Core 2.x가 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d60f1-123">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d60f1-124">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d60f1-124">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="d60f1-125">.NET Core 1.x는 다음 Linux 64비트(`x86_64` 또는 `amd64`) 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-125">.NET Core 1.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

* <span data-ttu-id="d60f1-126">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="d60f1-126">Red Hat Enterprise Linux 7</span></span>
* <span data-ttu-id="d60f1-127">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="d60f1-127">CentOS 7</span></span>
* <span data-ttu-id="d60f1-128">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="d60f1-128">Oracle Linux 7</span></span>
* <span data-ttu-id="d60f1-129">Fedora 24</span><span class="sxs-lookup"><span data-stu-id="d60f1-129">Fedora 24</span></span>
* <span data-ttu-id="d60f1-130">Debian 8.2 이상 버전</span><span class="sxs-lookup"><span data-stu-id="d60f1-130">Debian 8.2 or later versions</span></span>
* <span data-ttu-id="d60f1-131">Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*</span><span class="sxs-lookup"><span data-stu-id="d60f1-131">Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*</span></span>
 * <span data-ttu-id="d60f1-132">Ubuntu 16.10은 .NET Core 1.1의 최신 패치 릴리스에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-132">Ubuntu 16.10 is supported by the latest patch release of .NET Core 1.1</span></span>
* <span data-ttu-id="d60f1-133">Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="d60f1-133">Linux Mint 17</span></span>
* <span data-ttu-id="d60f1-134">openSUSE 42.1 이상 버전(.NET Core 1.1)</span><span class="sxs-lookup"><span data-stu-id="d60f1-134">openSUSE 42.1 or later versions (.NET Core 1.1)</span></span>

<span data-ttu-id="d60f1-135">지원 OS 버전 중 .NET Core 1.x를 지원하는 운영 체제 및 수명 주기 정책 링크는 [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)(.NET Core 1.x가 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d60f1-135">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="d60f1-136">Linux 배포 종속성</span><span class="sxs-lookup"><span data-stu-id="d60f1-136">Linux distribution dependencies</span></span>

<span data-ttu-id="d60f1-137">다음은 예제로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-137">The following are intended to be examples.</span></span> <span data-ttu-id="d60f1-138">정확한 버전 및 이름은 선택한 Linux 배포에 따라 약간 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-138">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="d60f1-139">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="d60f1-139">Ubuntu</span></span>

<span data-ttu-id="d60f1-140">Ubuntu 배포에는 다음과 같은 라이브러리 설치가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-140">Ubuntu distributions require the following libraries installed:</span></span>

* <span data-ttu-id="d60f1-141">libunwind8</span><span class="sxs-lookup"><span data-stu-id="d60f1-141">libunwind8</span></span>
* <span data-ttu-id="d60f1-142">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="d60f1-142">liblttng-ust0</span></span>
* <span data-ttu-id="d60f1-143">libcurl3</span><span class="sxs-lookup"><span data-stu-id="d60f1-143">libcurl3</span></span>
* <span data-ttu-id="d60f1-144">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="d60f1-144">libssl1.0.0</span></span>
* <span data-ttu-id="d60f1-145">libuuid1</span><span class="sxs-lookup"><span data-stu-id="d60f1-145">libuuid1</span></span>
* <span data-ttu-id="d60f1-146">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="d60f1-146">libkrb5-3</span></span>
* <span data-ttu-id="d60f1-147">zlib1g</span><span class="sxs-lookup"><span data-stu-id="d60f1-147">zlib1g</span></span>
* <span data-ttu-id="d60f1-148">libicu52(14.X용)</span><span class="sxs-lookup"><span data-stu-id="d60f1-148">libicu52 (for 14.X)</span></span>
* <span data-ttu-id="d60f1-149">libicu55(16.X용)</span><span class="sxs-lookup"><span data-stu-id="d60f1-149">libicu55 (for 16.X)</span></span>
* <span data-ttu-id="d60f1-150">libicu57(17.X용)</span><span class="sxs-lookup"><span data-stu-id="d60f1-150">libicu57 (for 17.X)</span></span>

### <a name="centos"></a><span data-ttu-id="d60f1-151">CentOS</span><span class="sxs-lookup"><span data-stu-id="d60f1-151">CentOS</span></span>

<span data-ttu-id="d60f1-152">CentOS 배포에는 다음과 같은 라이브러리 설치가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-152">CentOS distributions require the following libraries installed:</span></span>

* <span data-ttu-id="d60f1-153">libunwind</span><span class="sxs-lookup"><span data-stu-id="d60f1-153">libunwind</span></span>
* <span data-ttu-id="d60f1-154">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="d60f1-154">lttng-ust</span></span>
* <span data-ttu-id="d60f1-155">libcurl</span><span class="sxs-lookup"><span data-stu-id="d60f1-155">libcurl</span></span>
* <span data-ttu-id="d60f1-156">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="d60f1-156">openssl-libs</span></span>
* <span data-ttu-id="d60f1-157">libuuid</span><span class="sxs-lookup"><span data-stu-id="d60f1-157">libuuid</span></span>
* <span data-ttu-id="d60f1-158">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="d60f1-158">krb5-libs</span></span>
* <span data-ttu-id="d60f1-159">libicu</span><span class="sxs-lookup"><span data-stu-id="d60f1-159">libicu</span></span>
* <span data-ttu-id="d60f1-160">zlib</span><span class="sxs-lookup"><span data-stu-id="d60f1-160">zlib</span></span>

<span data-ttu-id="d60f1-161">종속성에 대한 자세한 내용은 [자체 포함 Linux 응용 프로그램](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d60f1-161">For more information about the dependencies, see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

## <a name="installing-net-core-dependencies-with-the-native-installers"></a><span data-ttu-id="d60f1-162">기본 설치 관리자를 사용하여 .NET Core 종속성 설치</span><span class="sxs-lookup"><span data-stu-id="d60f1-162">Installing .NET Core dependencies with the native installers</span></span>

<span data-ttu-id="d60f1-163">.NET Core 기본 설치 관리자는 지원되는 Linux 배포/버전에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-163">.NET Core native installers are available for supported Linux distributions/versions.</span></span> <span data-ttu-id="d60f1-164">기본 설치 관리자를 사용하려면 서버에 대한 관리자(sudo) 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-164">The native installers require admin (sudo) access to the server.</span></span> <span data-ttu-id="d60f1-165">기본 설치 관리자를 사용하는 장점은 모든 .NET Core 기본 종속성을 설치한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-165">The advantage of using a native installer is that all of the .NET Core native dependencies are installed.</span></span> <span data-ttu-id="d60f1-166">기본 설치 관리자는 .NET Core SDK 시스템 차원을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-166">Native installers also install the .NET Core SDK system-wide.</span></span>

<span data-ttu-id="d60f1-167">Linux에는 두 가지 패키지 선택 항목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-167">On Linux, there are two installer package choices:</span></span>

* <span data-ttu-id="d60f1-168">피드 기반 패키지 관리자 사용(예: Ubuntu의 경우 apt-get, CentOS/RHEL의 경우 yum).</span><span class="sxs-lookup"><span data-stu-id="d60f1-168">Using a feed-based package manager, such as apt-get for Ubuntu, or yum for CentOS/RHEL.</span></span>
* <span data-ttu-id="d60f1-169">패키지 자체 사용(DEB 또는 RPM).</span><span class="sxs-lookup"><span data-stu-id="d60f1-169">Using the packages themselves, DEB or RPM.</span></span>

### <a name="scripting-installs-with-the-net-core-installer-script"></a><span data-ttu-id="d60f1-170">.NET Core 설치 관리자 스크립트를 사용하여 설치 스크립팅</span><span class="sxs-lookup"><span data-stu-id="d60f1-170">Scripting Installs with the .NET Core installer script</span></span>

<span data-ttu-id="d60f1-171">`dotnet-install` 스크립트는 CLI 도구 체인 및 공유 런타임의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-171">The `dotnet-install` scripts are used to perform a non-admin install of the CLI toolchain and the shared runtime.</span></span> <span data-ttu-id="d60f1-172">https://dot.net/v1/dotnet-install.sh에서 스크립트를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-172">You can download the script from: https://dot.net/v1/dotnet-install.sh</span></span>

<span data-ttu-id="d60f1-173">설치 관리자 bash 스크립트는 자동화 시나리오 및 비관리자 설치에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-173">The installer bash script is used in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="d60f1-174">또한 이 스크립트는 PowerShell 스위치를 읽으므로 Linux/OS X 시스템에서 스크립트와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-174">This script also reads PowerShell switches, so they can be used with the script on Linux/OS X systems.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d60f1-175">스크립트를 실행하기 전에 필요한 모든 [종속성](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md)을 설치하세요.</span><span class="sxs-lookup"><span data-stu-id="d60f1-175">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

## <a name="install-net-core-for-red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="d60f1-176">RHEL(Red Hat Enterprise Linux) 7에 대한 .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="d60f1-176">Install .NET Core for Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="d60f1-177">RHEL 7에 .NET Core를 설치하려면 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-177">To install .NET Core on RHEL 7:</span></span>

1. <span data-ttu-id="d60f1-178">RHEL 7 구독에 따라 사용할 수 있는 Red Hat .NET 채널을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-178">Enable the Red Hat .NET channel, available under your RHEL 7 subscription.</span></span>
    * <span data-ttu-id="d60f1-179">Red Hat Enterprise 7 Server의 경우 다음을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-179">For Red Hat Enterprise 7 Server, use:</span></span>
    
         ```bash
         subscription-manager repos --enable=rhel-7-server-dotnet-rpms
         ```
    
    * <span data-ttu-id="d60f1-180">Red Hat Enterprise 7 Workstation의 경우 다음을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-180">For Red Hat Enterprise 7 Workstation, use:</span></span>
    
        ```bash
        subscription-manager repos --enable=rhel-7-workstation-dotnet-rpms
         ```
    
    * <span data-ttu-id="d60f1-181">Red Hat Enterprise 7 HPC Compute Node의 경우 다음을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-181">For Red Hat Enterprise 7 HPC Compute Node, use:</span></span>
    
        ```bash
        subscription-manager repos --enable=rhel-7-hpc-node-dotnet-rpms
        ```

2. <span data-ttu-id="d60f1-182">scl 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-182">Install the scl tool.</span></span>

    ```bash
    yum install scl-utils
    ```
    
3. <span data-ttu-id="d60f1-183">.NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="d60f1-183">Install .NET Core</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d60f1-184">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d60f1-184">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="d60f1-185">.NET Core 2.0 SDK 및 런타임 설치:</span><span class="sxs-lookup"><span data-stu-id="d60f1-185">Install .NET Core 2.0 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnet20
   ```

<span data-ttu-id="d60f1-186">사용자 환경에 대해 .NET Core 2.0 SDK/런타임을 사용하도록 설정:</span><span class="sxs-lookup"><span data-stu-id="d60f1-186">Enable .NET Core 2.0 SDK/Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnet20 bash
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d60f1-187">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d60f1-187">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="d60f1-188">**.NET Core 1.1**</span><span class="sxs-lookup"><span data-stu-id="d60f1-188">**.NET Core 1.1**</span></span>

<span data-ttu-id="d60f1-189">.NET Core 1.1 SDK 및 런타임 설치:</span><span class="sxs-lookup"><span data-stu-id="d60f1-189">Install .NET Core 1.1 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnetcore11
   ```

<span data-ttu-id="d60f1-190">사용자 환경에 대해 .NET Core 1.1 SDK 및 런타임을 사용하도록 설정:</span><span class="sxs-lookup"><span data-stu-id="d60f1-190">Enable .NET Core 1.1 SDK and Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnetcore11 bash
   ```

<span data-ttu-id="d60f1-191">**.NET Core 1.0**</span><span class="sxs-lookup"><span data-stu-id="d60f1-191">**.NET Core 1.0**</span></span>

<span data-ttu-id="d60f1-192">.NET Core 1.0 SDK 및 런타임 설치:</span><span class="sxs-lookup"><span data-stu-id="d60f1-192">Install .NET Core 1.0 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnetcore10
   ```

<span data-ttu-id="d60f1-193">사용자 환경에 대해 .NET Core 1.0 SDK 및 런타임을 사용하도록 설정:</span><span class="sxs-lookup"><span data-stu-id="d60f1-193">Enable .NET Core 1.0 SDK and Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnetcore10 bash
   ```

---
4. <span data-ttu-id="d60f1-194">`dotnet --version` 명령을 실행하여 설치 성공을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-194">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

     ```bash
     dotnet --version
     ```

<span data-ttu-id="d60f1-195">Red Hat .NET 채널 액세스 등록 도움말은 Red Hat에서 [Chapter 1 of the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/)(.NET Core 1.1 1장 시작 가이드)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d60f1-195">For Red Hat .NET channel access registration help, see [Chapter 1 of the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) at Red Hat.</span></span>

## <a name="install-net-core-for-ubuntu-1404-ubuntu-1604-ubuntu-1610--linux-mint-17-linux-mint-18-64-bit"></a><span data-ttu-id="d60f1-196">Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10 & Linux Mint 17, Linux Mint 18(64 비트)에 대한 .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="d60f1-196">Install .NET Core for Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10 & Linux Mint 17, Linux Mint 18 (64 bit)</span></span>

1. <span data-ttu-id="d60f1-197">시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.</span><span class="sxs-lookup"><span data-stu-id="d60f1-197">Remove any **previous preview** versions of .NET Core from your system.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d60f1-198">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d60f1-198">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="d60f1-199">신뢰할 수 있는 것으로 Microsoft 제품 키를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-199">Register the Microsoft Product key as trusted.</span></span>

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```

3. <span data-ttu-id="d60f1-200">원하는 버전의 호스트 패키지 피드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-200">Set up the desired version host package feed.</span></span>

   <span data-ttu-id="d60f1-201">**Ubuntu 17.10**</span><span class="sxs-lookup"><span data-stu-id="d60f1-201">**Ubuntu 17.10**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-artful-prod artful main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```
   <span data-ttu-id="d60f1-202">**Ubuntu 17.04**</span><span class="sxs-lookup"><span data-stu-id="d60f1-202">**Ubuntu 17.04**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-zesty-prod zesty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   <span data-ttu-id="d60f1-203">**Ubuntu 16.04/Linux Mint 18**</span><span class="sxs-lookup"><span data-stu-id="d60f1-203">**Ubuntu 16.04 / Linux Mint 18**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-xenial-prod xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   <span data-ttu-id="d60f1-204">**Ubuntu 14.04/Linux Mint 17**</span><span class="sxs-lookup"><span data-stu-id="d60f1-204">**Ubuntu 14.04 / Linux Mint 17**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-trusty-prod trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

4. <span data-ttu-id="d60f1-205">.NET Core를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-205">Install .NET Core.</span></span>

   ```bash
   sudo apt-get install dotnet-sdk-2.1.4
   ```

4. <span data-ttu-id="d60f1-206">`dotnet --version` 명령을 실행하여 설치 성공을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-206">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d60f1-207">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d60f1-207">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="d60f1-208">원하는 버전의 호스트 패키지 피드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-208">Set up the desired version host package feed.</span></span>

   <span data-ttu-id="d60f1-209">**Ubuntu 16.10**</span><span class="sxs-lookup"><span data-stu-id="d60f1-209">**Ubuntu 16.10**</span></span>
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ yakkety main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

  <span data-ttu-id="d60f1-210">**Ubuntu 16.04/Linux Mint 18**</span><span class="sxs-lookup"><span data-stu-id="d60f1-210">**Ubuntu 16.04 / Linux Mint 18**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```
    
   <span data-ttu-id="d60f1-211">**Ubuntu 14.04/Linux Mint 17**</span><span class="sxs-lookup"><span data-stu-id="d60f1-211">**Ubuntu 14.04 / Linux Mint 17**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

3. <span data-ttu-id="d60f1-212">Ubuntu 또는 Linux Mint에 .NET Core 1.x를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-212">Install .NET Core 1.x on Ubuntu or Linux Mint:</span></span>

   ```bash
   sudo apt-get install dotnet-dev-1.0.4
   ```

4. <span data-ttu-id="d60f1-213">`dotnet --version` 명령을 실행하여 설치 성공을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-213">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

---

 ## <a name="install-net-core-for-debian-8-or-debian-9-64-bit"></a><span data-ttu-id="d60f1-214">Debian 8 또는 Debian 9(64비트)에 대한 .NET Core를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-214">Install .NET Core for Debian 8 or Debian 9 (64 bit)</span></span>

<span data-ttu-id="d60f1-215">Debian 8 또는 Debian 9(64비트)에 .NET Core를 설치하려면:</span><span class="sxs-lookup"><span data-stu-id="d60f1-215">To install .NET Core on Debian 8 or Debian 9 (64 bit):</span></span>

1. <span data-ttu-id="d60f1-216">시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.</span><span class="sxs-lookup"><span data-stu-id="d60f1-216">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="d60f1-217">tar.gz에서 Linux 시스템을 설치하는 데 사용자 제어 디렉터리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-217">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d60f1-218">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d60f1-218">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="d60f1-219">시스템 구성 요소를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-219">Install system components.</span></span>

   ```bash
   sudo apt-get update
   sudo apt-get install curl libunwind8 gettext apt-transport-https
   ```
   
3. <span data-ttu-id="d60f1-220">신뢰할 수 있는 Microsoft 제품 키를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-220">Register the trusted Microsoft Product key.</span></span>

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```
   
4. <span data-ttu-id="d60f1-221">Microsoft 제품 피드를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-221">Register the Microsoft Product feed.</span></span>

   <span data-ttu-id="d60f1-222">**Debian 9(Stretch)**</span><span class="sxs-lookup"><span data-stu-id="d60f1-222">**Debian 9 (Stretch)**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-stretch-prod stretch main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
   <span data-ttu-id="d60f1-223">**Debian 8(Jessie)**</span><span class="sxs-lookup"><span data-stu-id="d60f1-223">**Debian 8 (Jessie)**</span></span>
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-jessie-prod jessie main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
5. <span data-ttu-id="d60f1-224">.NET Core SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-224">Install .NET Core SDK.</span></span>

   ```bash
   sudo apt-get update
   sudo apt-get install dotnet-sdk-2.0.0
   ```

6. <span data-ttu-id="d60f1-225">PATH에 dotnet을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-225">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```
   
7. <span data-ttu-id="d60f1-226">`dotnet --version` 명령을 실행하여 설치 성공을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-226">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```   
  

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d60f1-227">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d60f1-227">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="d60f1-228">필수 구성 요소를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-228">Get the prerequisites.</span></span>

   ```bash
   sudo apt-get install curl libunwind8 gettext
   ```

3. <span data-ttu-id="d60f1-229">.NET Core SDK 이진 파일(tarball)을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-229">Download the .NET Core SDK binaries (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848826
   ```

4. <span data-ttu-id="d60f1-230">.NET Core SDK 이전 파일을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-230">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="d60f1-231">PATH에 dotnet을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-231">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

6. <span data-ttu-id="d60f1-232">`dotnet --version` 명령을 실행하여 설치 성공을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-232">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

---

## <a name="install-net-core-for-fedora-24-fedora-25-or-fedora-26-64-bit"></a><span data-ttu-id="d60f1-233">Fedora 24, Fedora 25 또는 Fedora 26(64비트)에 대한 .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="d60f1-233">Install .NET Core for Fedora 24, Fedora 25, or Fedora 26 (64 bit)</span></span>

<span data-ttu-id="d60f1-234">Fedora 26 또는 Fedora 25에 .NET Core 2.x를 설치하거나 Fedora 24에 .NET Core 1.x를 설치하려면:</span><span class="sxs-lookup"><span data-stu-id="d60f1-234">To install .NET Core 2.x on Fedora 26 or Fedora 25, or .NET Core 1.x on Fedora 24:</span></span>

1. <span data-ttu-id="d60f1-235">시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.</span><span class="sxs-lookup"><span data-stu-id="d60f1-235">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="d60f1-236">tar.gz에서 Linux 시스템을 설치하는 데 사용자 제어 디렉터리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-236">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d60f1-237">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d60f1-237">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="d60f1-238">**Fedora 26 또는 Fedora 25**</span><span class="sxs-lookup"><span data-stu-id="d60f1-238">**Fedora 26 or Fedora 25**</span></span>

2. <span data-ttu-id="d60f1-239">Microsoft 서명 키를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-239">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="d60f1-240">dotnet 제품 피드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-240">Add the dotnet product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. <span data-ttu-id="d60f1-241">.NET Core SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-241">Install the .NET Core SDK.</span></span>

   ```bash
   sudo dnf update
   sudo dnf install libunwind libicu
   sudo dnf install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="d60f1-242">PATH에 dotnet을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-242">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d60f1-243">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d60f1-243">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="d60f1-244">**Fedora 24**</span><span class="sxs-lookup"><span data-stu-id="d60f1-244">**Fedora 24**</span></span>

2. <span data-ttu-id="d60f1-245">필수 구성 요소를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-245">Get the prerequisites.</span></span>

   ```bash
   sudo dnf install libunwind libicu
   ```

3. <span data-ttu-id="d60f1-246">.NET Core SDK 이진 파일(tarball)을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-246">Download the .NET Core SDK binary  (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848833
   ```

4. <span data-ttu-id="d60f1-247">.NET Core SDK 이전 파일을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-247">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="d60f1-248">PATH에 dotnet을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-248">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. <span data-ttu-id="d60f1-249">`dotnet --version` 명령을 실행하여 설치 성공을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-249">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-centos-71-64-bit--oracle-linux-71-64-bit"></a><span data-ttu-id="d60f1-250">CentOS 7.1(64비트) 및 Oracle Linux 7.1(64비트)에 대한 .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="d60f1-250">Install .NET Core for CentOS 7.1 (64 bit) & Oracle Linux 7.1 (64 bit)</span></span>

<span data-ttu-id="d60f1-251">CentOS 7.1(64비트) 및 Oracle Linux 7.1(64비트)용 .NET Core를 설치하려면:</span><span class="sxs-lookup"><span data-stu-id="d60f1-251">To install .NET Core for CentOS 7.1 (64 bit) & Oracle Linux 7.1 (64 bit):</span></span>

1. <span data-ttu-id="d60f1-252">시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.</span><span class="sxs-lookup"><span data-stu-id="d60f1-252">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="d60f1-253">tar.gz에서 Linux 시스템을 설치하는 데 사용자 제어 디렉터리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-253">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d60f1-254">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d60f1-254">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="d60f1-255">Microsoft 서명 키를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-255">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="d60f1-256">Microsoft 제품 피드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-256">Add the Microsoft Product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. <span data-ttu-id="d60f1-257">.NET Core SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-257">Install the .NET Core SDK.</span></span>

   ```bash
   sudo yum update
   sudo yum install libunwind libicu
   sudo yum install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="d60f1-258">PATH에 dotnet 추가</span><span class="sxs-lookup"><span data-stu-id="d60f1-258">Add dotnet to your PATH</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d60f1-259">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d60f1-259">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="d60f1-260">필수 구성 요소를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-260">Get the prerequisites.</span></span>

   ```bash
   sudo yum install libunwind libicu
   ```
   
3. <span data-ttu-id="d60f1-261">.NET Core SDK 이진 파일(tarball)을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-261">Download the .NET Core SDK binary (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848821
   ```

4. <span data-ttu-id="d60f1-262">.NET Core SDK 이전 파일을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-262">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="d60f1-263">PATH에 dotnet을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-263">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

---

6. <span data-ttu-id="d60f1-264">`dotnet --version` 명령을 실행하여 설치 성공을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-264">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-suse-linux-enterprise-server-64-bit"></a><span data-ttu-id="d60f1-265">SUSE Linux Enterprise Server(64비트)에 대한 .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="d60f1-265">Install .NET Core for SUSE Linux Enterprise Server (64 bit)</span></span>

<span data-ttu-id="d60f1-266">SLES(SUSE Linux Enterprise Server) 12 SP2(64비트)용 .NET Core 2.x을 설치하려면:</span><span class="sxs-lookup"><span data-stu-id="d60f1-266">To install .NET Core 2.x for SUSE Linux Enterprise Server (SLES) 12 SP2 (64 bit):</span></span>

1. <span data-ttu-id="d60f1-267">시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.</span><span class="sxs-lookup"><span data-stu-id="d60f1-267">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="d60f1-268">dotnet 제품 피드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-268">Add the dotnet product feed.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ```

3. <span data-ttu-id="d60f1-269">.NET Core SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-269">Install the .NET Core SDK.</span></span>

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

4. <span data-ttu-id="d60f1-270">PATH에 dotnet을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-270">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

5. <span data-ttu-id="d60f1-271">`dotnet --version` 명령을 실행하여 설치 성공을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-271">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```
   
## <a name="install-net-core-for-opensuse-64-bit"></a><span data-ttu-id="d60f1-272">openSUSE(64비트)용 .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="d60f1-272">Install .NET Core for openSUSE (64 bit)</span></span>

<span data-ttu-id="d60f1-273">openSUSE용 .NET Core 2.x 또는 openSUSE(64비트)용 .NET Core 1.x를 설치하려면:</span><span class="sxs-lookup"><span data-stu-id="d60f1-273">To install .NET Core 2.x for openSUSE or .NET Core 1.x for openSUSE (64 bit):</span></span>

1. <span data-ttu-id="d60f1-274">시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.</span><span class="sxs-lookup"><span data-stu-id="d60f1-274">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="d60f1-275">tar.gz에서 Linux 시스템을 설치하는 데 사용자 제어 디렉터리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-275">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d60f1-276">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d60f1-276">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="d60f1-277">Microsoft 서명 키를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-277">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="d60f1-278">dotnet 제품 피드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-278">Add the dotnet product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ``` 

4. <span data-ttu-id="d60f1-279">.NET Core SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-279">Install the .NET Core SDK.</span></span>

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="d60f1-280">PATH에 dotnet을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-280">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d60f1-281">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d60f1-281">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="d60f1-282">필수 구성 요소를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-282">Get the prerequisites.</span></span>

   ```bash
   sudo zypper install libunwind libicu
   ```

3. <span data-ttu-id="d60f1-283">.NET Core SDK 이진 파일(tarball)을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-283">Download the .NET Core SDK binary (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848824
   ```

4. <span data-ttu-id="d60f1-284">.NET Core SDK 이전 파일을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-284">Extract the .NET Core SDK binaries.</span></span>
   
   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="d60f1-285">PATH에 dotnet을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-285">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. <span data-ttu-id="d60f1-286">`dotnet --version` 명령을 실행하여 설치 성공을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="d60f1-286">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

> [!IMPORTANT]
> <span data-ttu-id="d60f1-287">지원되는 Linux 배포/버전의 .NET Core 2.x 설치에 문제가 있는 경우 설치된 배포/버전은 [2.0 Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0)(2.0 알려진 문제) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d60f1-287">If you have problems with the .NET Core 2.x installation on a supported Linux distribution/version, consult the [2.0 Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) topic for your installed distributions/versions.</span></span> 
>
> <span data-ttu-id="d60f1-288">지원되는 Linux 배포/버전의 .NET Core 1.x 설치에 문제가 있는 경우 설치된 배포/버전은 [1.0.0 Known issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md)(1.0.0 알려진 문제) 및 [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md)(1.0.1 알려진 문제) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d60f1-288">If you have problems with the .NET Core 1.x installation on a supported Linux distribution/version, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics for your installed distributions/versions.</span></span>
