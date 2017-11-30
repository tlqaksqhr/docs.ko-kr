---
title: "Linux에서 .NET Core의 필수 구성 요소"
description: "Linux 컴퓨터에서 .NET Core 응용 프로그램을 개발, 배포 및 실행하기 위해 지원되는 Linux 버전 및 .NET Core 종속성입니다."
keywords: .NET, .NET Core, Linux, debian, ubuntu, RHEL, centOS,
author: jralexander
ms.author: johalex
ms.date: 09/07/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.openlocfilehash: 04fdf26e150e6d489c0641588563f69f24835615
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="prerequisites-for-net-core-on-linux"></a><span data-ttu-id="f8474-104">Linux에서 .NET Core의 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="f8474-104">Prerequisites for .NET Core on Linux</span></span>

<span data-ttu-id="f8474-105">이 문서에서는 Linux에서 .NET Core 응용 프로그램을 개발하는 데 필요한 종속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-105">This article shows the dependencies needed to develop .NET Core applications on Linux.</span></span> <span data-ttu-id="f8474-106">다음에 나오는 지원되는 Linux 배포/버전 및 종속성은 Linux에서 .NET Core 앱을 개발하기 위한 두 가지 방법에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-106">The supported Linux distributions/versions, and dependencies that follow apply to the two ways of developing .NET Core apps on Linux:</span></span>

* [<span data-ttu-id="f8474-107">즐겨 찾는 편집기를 사용하는 명령줄</span><span class="sxs-lookup"><span data-stu-id="f8474-107">Command-line with your favorite editor</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="f8474-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f8474-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

## <a name="supported-linux-versions"></a><span data-ttu-id="f8474-109">지원되는 Linux 버전</span><span class="sxs-lookup"><span data-stu-id="f8474-109">Supported Linux versions</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="f8474-110">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="f8474-110">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="f8474-111">.NET Core 2.0은 단일 운영 체제로 Linux를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-111">.NET Core 2.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="f8474-112">지원되는 Linux 배포판에 대한 단일 Linux 빌드(칩 아키텍처 당)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-112">There is a single Linux build (per chip architecture) for supported Linux distros.</span></span>

<span data-ttu-id="f8474-113">.NET Core 2.x는 다음 Linux 64비트(`x86_64` 또는 `amd64`) 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-113">NET Core 2.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

 * <span data-ttu-id="f8474-114">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="f8474-114">Red Hat Enterprise Linux 7</span></span>
 * <span data-ttu-id="f8474-115">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="f8474-115">CentOS 7</span></span>
 * <span data-ttu-id="f8474-116">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="f8474-116">Oracle Linux 7</span></span>
 * <span data-ttu-id="f8474-117">Fedora 25, Fedora 26</span><span class="sxs-lookup"><span data-stu-id="f8474-117">Fedora 25, Fedora 26</span></span>
 * <span data-ttu-id="f8474-118">Debian 8.7 이상 버전</span><span class="sxs-lookup"><span data-stu-id="f8474-118">Debian 8.7 or later versions</span></span> 
 * <span data-ttu-id="f8474-119">Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="f8474-119">Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04</span></span>
 * <span data-ttu-id="f8474-120">Linux Mint 18, Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="f8474-120">Linux Mint 18, Linux Mint 17</span></span>
 * <span data-ttu-id="f8474-121">openSUSE 42.2 이상 버전</span><span class="sxs-lookup"><span data-stu-id="f8474-121">openSUSE 42.2 or later versions</span></span>
 * <span data-ttu-id="f8474-122">SLES(SUSE Enterprise Linux) 12 SP2 이상 버전</span><span class="sxs-lookup"><span data-stu-id="f8474-122">SUSE Enterprise Linux (SLES) 12 SP2 or later versions</span></span>

<span data-ttu-id="f8474-123">지원 OS 버전 중 .NET Core 2.x를 지원하는 운영 체제 및 수명 주기 정책 링크는 [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)(.NET Core 2.x가 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8474-123">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f8474-124">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f8474-124">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="f8474-125">.NET Core 1.x는 다음 Linux 64비트(`x86_64` 또는 `amd64`) 배포/버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-125">.NET Core 1.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

* <span data-ttu-id="f8474-126">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="f8474-126">Red Hat Enterprise Linux 7</span></span>
* <span data-ttu-id="f8474-127">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="f8474-127">CentOS 7</span></span>
* <span data-ttu-id="f8474-128">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="f8474-128">Oracle Linux 7</span></span>
* <span data-ttu-id="f8474-129">Fedora 24</span><span class="sxs-lookup"><span data-stu-id="f8474-129">Fedora 24</span></span>
* <span data-ttu-id="f8474-130">Debian 8.2 이상 버전</span><span class="sxs-lookup"><span data-stu-id="f8474-130">Debian 8.2 or later versions</span></span>
* <span data-ttu-id="f8474-131">Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*</span><span class="sxs-lookup"><span data-stu-id="f8474-131">Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*</span></span>
 * <span data-ttu-id="f8474-132">Ubuntu 16.10은 .NET Core 1.1의 최신 패치 릴리스에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-132">Ubuntu 16.10 is supported by the latest patch release of .NET Core 1.1</span></span>
* <span data-ttu-id="f8474-133">Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="f8474-133">Linux Mint 17</span></span>
* <span data-ttu-id="f8474-134">openSUSE 42.1 이상 버전(.NET Core 1.1)</span><span class="sxs-lookup"><span data-stu-id="f8474-134">openSUSE 42.1 or later versions (.NET Core 1.1)</span></span>

<span data-ttu-id="f8474-135">지원 OS 버전 중 .NET Core 1.x를 지원하는 운영 체제 및 수명 주기 정책 링크는 [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)(.NET Core 1.x가 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8474-135">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="f8474-136">Linux 배포 종속성</span><span class="sxs-lookup"><span data-stu-id="f8474-136">Linux distribution dependencies</span></span>

<span data-ttu-id="f8474-137">다음 예제로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-137">The following are intended to be examples.</span></span> <span data-ttu-id="f8474-138">정확한 버전 및 이름 선택한 Linux 분포로 약간 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-138">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="f8474-139">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="f8474-139">Ubuntu</span></span>

<span data-ttu-id="f8474-140">Ubuntu 배포에는 다음과 같은 라이브러리 설치가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-140">Ubuntu distributions require the following libraries installed:</span></span>

* <span data-ttu-id="f8474-141">libunwind8</span><span class="sxs-lookup"><span data-stu-id="f8474-141">libunwind8</span></span>
* <span data-ttu-id="f8474-142">liblttng ust0</span><span class="sxs-lookup"><span data-stu-id="f8474-142">liblttng-ust0</span></span>
* <span data-ttu-id="f8474-143">libcurl3</span><span class="sxs-lookup"><span data-stu-id="f8474-143">libcurl3</span></span>
* <span data-ttu-id="f8474-144">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="f8474-144">libssl1.0.0</span></span>
* <span data-ttu-id="f8474-145">libuuid1</span><span class="sxs-lookup"><span data-stu-id="f8474-145">libuuid1</span></span>
* <span data-ttu-id="f8474-146">libkrb5</span><span class="sxs-lookup"><span data-stu-id="f8474-146">libkrb5</span></span>
* <span data-ttu-id="f8474-147">zlib1g</span><span class="sxs-lookup"><span data-stu-id="f8474-147">zlib1g</span></span>
* <span data-ttu-id="f8474-148">libicu52 (14.X)에 대 한</span><span class="sxs-lookup"><span data-stu-id="f8474-148">libicu52 (for 14.X)</span></span>
* <span data-ttu-id="f8474-149">libicu55 (용 16.X)</span><span class="sxs-lookup"><span data-stu-id="f8474-149">libicu55 (for 16.X)</span></span>
* <span data-ttu-id="f8474-150">libicu57 (용 17.X)</span><span class="sxs-lookup"><span data-stu-id="f8474-150">libicu57 (for 17.X)</span></span>

### <a name="centos"></a><span data-ttu-id="f8474-151">CentOS</span><span class="sxs-lookup"><span data-stu-id="f8474-151">CentOS</span></span>

<span data-ttu-id="f8474-152">CentOS 배포에는 다음과 같은 라이브러리 설치가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-152">CentOS distributions require the following libraries installed:</span></span>

* <span data-ttu-id="f8474-153">libunwind</span><span class="sxs-lookup"><span data-stu-id="f8474-153">libunwind</span></span>
* <span data-ttu-id="f8474-154">lttng ust</span><span class="sxs-lookup"><span data-stu-id="f8474-154">lttng-ust</span></span>
* <span data-ttu-id="f8474-155">libcurl</span><span class="sxs-lookup"><span data-stu-id="f8474-155">libcurl</span></span>
* <span data-ttu-id="f8474-156">openssl 라이브러리</span><span class="sxs-lookup"><span data-stu-id="f8474-156">openssl-libs</span></span>
* <span data-ttu-id="f8474-157">libuuid</span><span class="sxs-lookup"><span data-stu-id="f8474-157">libuuid</span></span>
* <span data-ttu-id="f8474-158">하려면 krb5 라이브러리</span><span class="sxs-lookup"><span data-stu-id="f8474-158">krb5-libs</span></span>
* <span data-ttu-id="f8474-159">libicu</span><span class="sxs-lookup"><span data-stu-id="f8474-159">libicu</span></span>
* <span data-ttu-id="f8474-160">zlib</span><span class="sxs-lookup"><span data-stu-id="f8474-160">zlib</span></span>

<span data-ttu-id="f8474-161">종속성에 대한 자세한 내용은 [자체 포함 Linux 응용 프로그램](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8474-161">For more information about the dependencies, see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

## <a name="installing-net-core-dependencies-with-the-native-installers"></a><span data-ttu-id="f8474-162">기본 설치 관리자를 사용하여 .NET Core 종속성 설치</span><span class="sxs-lookup"><span data-stu-id="f8474-162">Installing .NET Core dependencies with the native installers</span></span>

<span data-ttu-id="f8474-163">.NET Core 기본 설치 관리자는 지원되는 Linux 배포/버전에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-163">.NET Core native installers are available for supported Linux distributions/versions.</span></span> <span data-ttu-id="f8474-164">기본 설치 관리자를 사용하려면 서버에 대한 관리자(sudo) 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-164">The native installers require admin (sudo) access to the server.</span></span> <span data-ttu-id="f8474-165">기본 설치 관리자를 사용하는 장점은 모든 .NET Core 기본 종속성을 설치한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-165">The advantage of using a native installer is that all of the .NET Core native dependencies are installed.</span></span> <span data-ttu-id="f8474-166">기본 설치 관리자는 .NET Core SDK 시스템 차원을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-166">Native installers also install the .NET Core SDK system-wide.</span></span>

<span data-ttu-id="f8474-167">Linux에는 두 가지 패키지 선택 항목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-167">On Linux, there are two installer package choices:</span></span>

* <span data-ttu-id="f8474-168">피드 기반 패키지 관리자 사용(예: Ubuntu의 경우 apt-get, CentOS/RHEL의 경우 yum).</span><span class="sxs-lookup"><span data-stu-id="f8474-168">Using a feed-based package manager, such as apt-get for Ubuntu, or yum for CentOS/RHEL.</span></span>
* <span data-ttu-id="f8474-169">패키지 자체 사용(DEB 또는 RPM).</span><span class="sxs-lookup"><span data-stu-id="f8474-169">Using the packages themselves, DEB or RPM.</span></span>

### <a name="scripting-installs-with-the-net-core-installer-script"></a><span data-ttu-id="f8474-170">.NET Core 설치 관리자 스크립트를 사용하여 설치 스크립팅</span><span class="sxs-lookup"><span data-stu-id="f8474-170">Scripting Installs with the .NET Core installer script</span></span>

<span data-ttu-id="f8474-171">`dotnet-install` 스크립트는 CLI 도구 체인 및 공유 런타임의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-171">The `dotnet-install` scripts are used to perform a non-admin install of the CLI toolchain and the shared runtime.</span></span> <span data-ttu-id="f8474-172">스크립트를 다운로드할 수 있습니다: https://dot.net/v1/dotnet-install.sh</span><span class="sxs-lookup"><span data-stu-id="f8474-172">You can download the script from: https://dot.net/v1/dotnet-install.sh</span></span>

<span data-ttu-id="f8474-173">설치 관리자 bash 스크립트는 자동화 시나리오 및 비관리자 설치에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-173">The installer bash script is used in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="f8474-174">또한 이 스크립트는 PowerShell 스위치를 읽으므로 Linux/OS X 시스템에서 스크립트와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-174">This script also reads PowerShell switches, so they can be used with the script on Linux/OS X systems.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f8474-175">스크립트를 실행하기 전에 필요한 모든 [종속성](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md)을 설치하세요.</span><span class="sxs-lookup"><span data-stu-id="f8474-175">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

## <a name="install-net-core-for-red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="f8474-176">RHEL(Red Hat Enterprise Linux) 7에 대한 .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="f8474-176">Install .NET Core for Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="f8474-177">RHEL 7에 .NET Core를 설치하려면 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-177">To install .NET Core on RHEL 7:</span></span>

1. <span data-ttu-id="f8474-178">RHEL 7 구독에 따라 사용할 수 있는 Red Hat .NET 채널을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-178">Enable the Red Hat .NET channel, available under your RHEL 7 subscription.</span></span>
    * <span data-ttu-id="f8474-179">Red Hat Enterprise 7 Server의 경우 다음을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-179">For Red Hat Enterprise 7 Server, use:</span></span>
    
         ```bash
         subscription-manager repos --enable=rhel-7-server-dotnet-rpms
         ```
    
    * <span data-ttu-id="f8474-180">Red Hat Enterprise 7 Workstation의 경우 다음을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-180">For Red Hat Enterprise 7 Workstation, use:</span></span>
    
        ```bash
        subscription-manager repos --enable=rhel-7-workstation-dotnet-rpms
         ```
    
    * <span data-ttu-id="f8474-181">Red Hat Enterprise 7 HPC Compute Node의 경우 다음을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-181">For Red Hat Enterprise 7 HPC Compute Node, use:</span></span>
    
        ```bash
        subscription-manager repos --enable=rhel-7-hpc-node-dotnet-rpms
        ```

2. <span data-ttu-id="f8474-182">scl 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-182">Install the scl tool.</span></span>

    ```bash
    yum install scl-utils
    ```
    
3. <span data-ttu-id="f8474-183">.NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="f8474-183">Install .NET Core</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="f8474-184">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="f8474-184">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="f8474-185">.NET Core 2.0 SDK 및 런타임 설치:</span><span class="sxs-lookup"><span data-stu-id="f8474-185">Install .NET Core 2.0 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnet20
   ```

<span data-ttu-id="f8474-186">사용자 환경에 대해 .NET Core 2.0 SDK/런타임을 사용하도록 설정:</span><span class="sxs-lookup"><span data-stu-id="f8474-186">Enable .NET Core 2.0 SDK/Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnet20 bash
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f8474-187">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f8474-187">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="f8474-188">**.NET Core 1.1**</span><span class="sxs-lookup"><span data-stu-id="f8474-188">**.NET Core 1.1**</span></span>

<span data-ttu-id="f8474-189">.NET Core 1.1 SDK 및 런타임 설치:</span><span class="sxs-lookup"><span data-stu-id="f8474-189">Install .NET Core 1.1 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnetcore11
   ```

<span data-ttu-id="f8474-190">사용자 환경에 대해 .NET Core 1.1 SDK 및 런타임을 사용하도록 설정:</span><span class="sxs-lookup"><span data-stu-id="f8474-190">Enable .NET Core 1.1 SDK and Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnetcore11 bash
   ```

<span data-ttu-id="f8474-191">**.NET Core 1.0**</span><span class="sxs-lookup"><span data-stu-id="f8474-191">**.NET Core 1.0**</span></span>

<span data-ttu-id="f8474-192">.NET Core 1.0 SDK 및 런타임 설치:</span><span class="sxs-lookup"><span data-stu-id="f8474-192">Install .NET Core 1.0 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnetcore10
   ```

<span data-ttu-id="f8474-193">사용자 환경에 대해 .NET Core 1.0 SDK 및 런타임을 사용하도록 설정:</span><span class="sxs-lookup"><span data-stu-id="f8474-193">Enable .NET Core 1.0 SDK and Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnetcore10 bash
   ```

---
4. <span data-ttu-id="f8474-194">`dotnet --version` 명령을 실행하여 설치 성공을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-194">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

     ```bash
     dotnet --version
     ```

<span data-ttu-id="f8474-195">Red Hat .NET 채널 액세스 등록 도움말은 Red Hat에서 [Chapter 1 of the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/)(.NET Core 1.1 1장 시작 가이드)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8474-195">For Red Hat .NET channel access registration help, see [Chapter 1 of the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) at Red Hat.</span></span>

## <a name="install-net-core-for-ubuntu-1404-ubuntu-1604-ubuntu-1610--linux-mint-17-linux-mint-18-64-bit"></a><span data-ttu-id="f8474-196">Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10 & Linux Mint 17, Linux Mint 18(64 비트)에 대한 .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="f8474-196">Install .NET Core for Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10 & Linux Mint 17, Linux Mint 18 (64 bit)</span></span>

1. <span data-ttu-id="f8474-197">시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.</span><span class="sxs-lookup"><span data-stu-id="f8474-197">Remove any **previous preview** versions of .NET Core from your system.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="f8474-198">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="f8474-198">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="f8474-199">신뢰할 수 있는 것으로 Microsoft 제품 키를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-199">Register the Microsoft Product key as trusted.</span></span>

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```

3. <span data-ttu-id="f8474-200">원하는 버전의 호스트 패키지 피드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-200">Set up the desired version host package feed.</span></span>

   <span data-ttu-id="f8474-201">**Ubuntu 17.04**</span><span class="sxs-lookup"><span data-stu-id="f8474-201">**Ubuntu 17.04**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-zesty-prod zesty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   <span data-ttu-id="f8474-202">**Ubuntu 16.04/Linux Mint 18**</span><span class="sxs-lookup"><span data-stu-id="f8474-202">**Ubuntu 16.04 / Linux Mint 18**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-xenial-prod xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   <span data-ttu-id="f8474-203">**Ubuntu 14.04/Linux Mint 17**</span><span class="sxs-lookup"><span data-stu-id="f8474-203">**Ubuntu 14.04 / Linux Mint 17**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-trusty-prod trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

4. <span data-ttu-id="f8474-204">.NET Core를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-204">Install .NET Core.</span></span>

   ```bash
   sudo apt-get install dotnet-sdk-2.0.0
   ```

4. <span data-ttu-id="f8474-205">`dotnet --version` 명령을 실행하여 설치 성공을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-205">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f8474-206">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f8474-206">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="f8474-207">원하는 버전의 호스트 패키지 피드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-207">Set up the desired version host package feed.</span></span>

   <span data-ttu-id="f8474-208">**Ubuntu 16.10**</span><span class="sxs-lookup"><span data-stu-id="f8474-208">**Ubuntu 16.10**</span></span>
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ yakkety main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

  <span data-ttu-id="f8474-209">**Ubuntu 16.04/Linux Mint 18**</span><span class="sxs-lookup"><span data-stu-id="f8474-209">**Ubuntu 16.04 / Linux Mint 18**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```
    
   <span data-ttu-id="f8474-210">**Ubuntu 14.04/Linux Mint 17**</span><span class="sxs-lookup"><span data-stu-id="f8474-210">**Ubuntu 14.04 / Linux Mint 17**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

3. <span data-ttu-id="f8474-211">Ubuntu 또는 Linux Mint에 .NET Core 1.x를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-211">Install .NET Core 1.x on Ubuntu or Linux Mint:</span></span>

   ```bash
   sudo apt-get install dotnet-dev-1.0.4
   ```

4. <span data-ttu-id="f8474-212">`dotnet --version` 명령을 실행하여 설치 성공을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-212">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

---

 ## <a name="install-net-core-for-debian-8-or-debian-9-64-bit"></a><span data-ttu-id="f8474-213">Debian 8 또는 Debian 9(64비트)에 대한 .NET Core를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-213">Install .NET Core for Debian 8 or Debian 9 (64 bit)</span></span>

<span data-ttu-id="f8474-214">Debian 8 또는 Debian 9(64비트)에 .NET Core를 설치하려면:</span><span class="sxs-lookup"><span data-stu-id="f8474-214">To install .NET Core on Debian 8 or Debian 9 (64 bit):</span></span>

1. <span data-ttu-id="f8474-215">시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.</span><span class="sxs-lookup"><span data-stu-id="f8474-215">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="f8474-216">tar.gz에서 Linux 시스템을 설치하는 데 사용자 제어 디렉터리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-216">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="f8474-217">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="f8474-217">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="f8474-218">시스템 구성 요소를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-218">Install system components.</span></span>

   ```bash
   sudo apt-get update
   sudo apt-get install curl libunwind8 gettext apt-transport-https
   ```
   
3. <span data-ttu-id="f8474-219">신뢰할 수 있는 Microsoft 제품 키를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-219">Register the trusted Microsoft Product key.</span></span>

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```
   
4. <span data-ttu-id="f8474-220">Microsoft 제품 피드를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-220">Register the Microsoft Product feed.</span></span>

   <span data-ttu-id="f8474-221">**Debian 9(Stretch)**</span><span class="sxs-lookup"><span data-stu-id="f8474-221">**Debian 9 (Stretch)**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-stretch-prod stretch main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
   <span data-ttu-id="f8474-222">**Debian 8(Jessie)**</span><span class="sxs-lookup"><span data-stu-id="f8474-222">**Debian 8 (Jessie)**</span></span>
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-jessie-prod jessie main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
5. <span data-ttu-id="f8474-223">.NET Core SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-223">Install .NET Core SDK.</span></span>

   ```bash
   sudo apt-get update
   sudo apt-get install dotnet-sdk-2.0.0
   ```

6. <span data-ttu-id="f8474-224">PATH에 dotnet을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-224">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```
   
7. <span data-ttu-id="f8474-225">`dotnet --version` 명령을 실행하여 설치 성공을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-225">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```   
  

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f8474-226">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f8474-226">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="f8474-227">필수 구성 요소를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-227">Get the prerequisites.</span></span>

   ```bash
   sudo apt-get install curl libunwind8 gettext
   ```

3. <span data-ttu-id="f8474-228">.NET Core SDK 이진 파일(tarball)을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-228">Download the .NET Core SDK binaries (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848826
   ```

4. <span data-ttu-id="f8474-229">.NET Core SDK 이전 파일을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-229">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="f8474-230">PATH에 dotnet을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-230">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

6. <span data-ttu-id="f8474-231">`dotnet --version` 명령을 실행하여 설치 성공을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-231">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

---

## <a name="install-net-core-for-fedora-24-fedora-25-or-fedora-26-64-bit"></a><span data-ttu-id="f8474-232">Fedora 24, Fedora 25 또는 Fedora 26(64비트)에 대한 .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="f8474-232">Install .NET Core for Fedora 24, Fedora 25, or Fedora 26 (64 bit)</span></span>

<span data-ttu-id="f8474-233">Fedora 26 또는 Fedora 25에 .NET Core 2.x를 설치하거나 Fedora 24에 .NET Core 1.x를 설치하려면:</span><span class="sxs-lookup"><span data-stu-id="f8474-233">To install .NET Core 2.x on Fedora 26 or Fedora 25, or .NET Core 1.x on Fedora 24:</span></span>

1. <span data-ttu-id="f8474-234">시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.</span><span class="sxs-lookup"><span data-stu-id="f8474-234">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="f8474-235">tar.gz에서 Linux 시스템을 설치하는 데 사용자 제어 디렉터리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-235">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="f8474-236">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="f8474-236">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="f8474-237">**Fedora 26 또는 Fedora 25**</span><span class="sxs-lookup"><span data-stu-id="f8474-237">**Fedora 26 or Fedora 25**</span></span>

2. <span data-ttu-id="f8474-238">Microsoft 서명 키를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-238">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="f8474-239">dotnet 제품 피드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-239">Add the dotnet product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. <span data-ttu-id="f8474-240">.NET Core SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-240">Install the .NET Core SDK.</span></span>

   ```bash
   sudo dnf update
   sudo dnf install libunwind libicu
   sudo dnf install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="f8474-241">PATH에 dotnet을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-241">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f8474-242">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f8474-242">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="f8474-243">**Fedora 24**</span><span class="sxs-lookup"><span data-stu-id="f8474-243">**Fedora 24**</span></span>

2. <span data-ttu-id="f8474-244">필수 구성 요소를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-244">Get the prerequisites.</span></span>

   ```bash
   sudo dnf install libunwind libicu
   ```

3. <span data-ttu-id="f8474-245">.NET Core SDK 이진 파일(tarball)을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-245">Download the .NET Core SDK binary  (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848833
   ```

4. <span data-ttu-id="f8474-246">.NET Core SDK 이전 파일을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-246">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="f8474-247">PATH에 dotnet을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-247">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. <span data-ttu-id="f8474-248">`dotnet --version` 명령을 실행하여 설치 성공을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-248">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-centos-71-64-bit--oracle-linux-71-64-bit"></a><span data-ttu-id="f8474-249">CentOS 7.1(64비트) 및 Oracle Linux 7.1(64비트)에 대한 .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="f8474-249">Install .NET Core for CentOS 7.1 (64 bit) & Oracle Linux 7.1 (64 bit)</span></span>

<span data-ttu-id="f8474-250">CentOS 7.1(64비트) 및 Oracle Linux 7.1(64비트)용 .NET Core를 설치하려면:</span><span class="sxs-lookup"><span data-stu-id="f8474-250">To install .NET Core for CentOS 7.1 (64 bit) & Oracle Linux 7.1 (64 bit):</span></span>

1. <span data-ttu-id="f8474-251">시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.</span><span class="sxs-lookup"><span data-stu-id="f8474-251">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="f8474-252">tar.gz에서 Linux 시스템을 설치하는 데 사용자 제어 디렉터리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-252">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="f8474-253">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="f8474-253">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="f8474-254">Microsoft 서명 키를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-254">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="f8474-255">Microsoft 제품 피드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-255">Add the Microsoft Product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. <span data-ttu-id="f8474-256">.NET Core SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-256">Install the .NET Core SDK.</span></span>

   ```bash
   sudo yum update
   sudo yum install libunwind libicu
   sudo yum install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="f8474-257">PATH에 dotnet 추가</span><span class="sxs-lookup"><span data-stu-id="f8474-257">Add dotnet to your PATH</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f8474-258">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f8474-258">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="f8474-259">필수 구성 요소를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-259">Get the prerequisites.</span></span>

   ```bash
   sudo yum install libunwind libicu
   ```
   
3. <span data-ttu-id="f8474-260">.NET Core SDK 이진 파일(tarball)을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-260">Download the .NET Core SDK binary (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848821
   ```

4. <span data-ttu-id="f8474-261">.NET Core SDK 이전 파일을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-261">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="f8474-262">PATH에 dotnet을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-262">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

---

6. <span data-ttu-id="f8474-263">`dotnet --version` 명령을 실행하여 설치 성공을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-263">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-suse-linux-enterprise-server-64-bit"></a><span data-ttu-id="f8474-264">SUSE Linux Enterprise Server(64비트)에 대한 .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="f8474-264">Install .NET Core for SUSE Linux Enterprise Server (64 bit)</span></span>

<span data-ttu-id="f8474-265">SLES(SUSE Linux Enterprise Server) 12 SP2(64비트)용 .NET Core 2.x을 설치하려면:</span><span class="sxs-lookup"><span data-stu-id="f8474-265">To install .NET Core 2.x for SUSE Linux Enterprise Server (SLES) 12 SP2 (64 bit):</span></span>

1. <span data-ttu-id="f8474-266">시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.</span><span class="sxs-lookup"><span data-stu-id="f8474-266">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="f8474-267">dotnet 제품 피드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-267">Add the dotnet product feed.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ```

3. <span data-ttu-id="f8474-268">.NET Core SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-268">Install the .NET Core SDK.</span></span>

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

4. <span data-ttu-id="f8474-269">PATH에 dotnet을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-269">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

5. <span data-ttu-id="f8474-270">`dotnet --version` 명령을 실행하여 설치 성공을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-270">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```
   
## <a name="install-net-core-for-opensuse-64-bit"></a><span data-ttu-id="f8474-271">openSUSE(64비트)용 .NET Core 설치</span><span class="sxs-lookup"><span data-stu-id="f8474-271">Install .NET Core for openSUSE (64 bit)</span></span>

<span data-ttu-id="f8474-272">openSUSE용 .NET Core 2.x 또는 openSUSE(64비트)용 .NET Core 1.x를 설치하려면:</span><span class="sxs-lookup"><span data-stu-id="f8474-272">To install .NET Core 2.x for openSUSE or .NET Core 1.x for openSUSE (64 bit):</span></span>

1. <span data-ttu-id="f8474-273">시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.</span><span class="sxs-lookup"><span data-stu-id="f8474-273">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="f8474-274">tar.gz에서 Linux 시스템을 설치하는 데 사용자 제어 디렉터리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-274">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="f8474-275">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="f8474-275">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="f8474-276">Microsoft 서명 키를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-276">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="f8474-277">dotnet 제품 피드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-277">Add the dotnet product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ``` 

4. <span data-ttu-id="f8474-278">.NET Core SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-278">Install the .NET Core SDK.</span></span>

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="f8474-279">PATH에 dotnet을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-279">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f8474-280">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f8474-280">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="f8474-281">필수 구성 요소를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-281">Get the prerequisites.</span></span>

   ```bash
   sudo zypper install libunwind libicu
   ```

3. <span data-ttu-id="f8474-282">.NET Core SDK 이진 파일(tarball)을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-282">Download the .NET Core SDK binary (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848824
   ```

4. <span data-ttu-id="f8474-283">.NET Core SDK 이전 파일을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-283">Extract the .NET Core SDK binaries.</span></span>
   
   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="f8474-284">PATH에 dotnet을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-284">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. <span data-ttu-id="f8474-285">`dotnet --version` 명령을 실행하여 설치 성공을 증명합니다.</span><span class="sxs-lookup"><span data-stu-id="f8474-285">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

> [!IMPORTANT]
> <span data-ttu-id="f8474-286">지원되는 Linux 배포/버전의 .NET Core 2.x 설치에 문제가 있는 경우 설치된 배포/버전은 [2.0 Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0)(2.0 알려진 문제) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8474-286">If you have problems with the .NET Core 2.x installation on a supported Linux distribution/version, consult the [2.0 Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) topic for your installed distributions/versions.</span></span> 
>
> <span data-ttu-id="f8474-287">지원되는 Linux 배포/버전의 .NET Core 1.x 설치에 문제가 있는 경우 설치된 배포/버전은 [1.0.0 Known issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md)(1.0.0 알려진 문제) 및 [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md)(1.0.1 알려진 문제) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8474-287">If you have problems with the .NET Core 1.x installation on a supported Linux distribution/version, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics for your installed distributions/versions.</span></span>
