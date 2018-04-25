---
title: Mac에서 .NET Core의 필수 구성 요소
description: macOS 컴퓨터에서.NET Core 응용 프로그램을 개발, 배포 및 실행하기 위해 지원되는 macOS 버전 및 .NET Core 종속성입니다.
keywords: .NET, .NET Core, macOS, Mac
author: guardrex
ms.author: mairaw
ms.date: 09/27/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.workload:
- dotnetcore
ms.openlocfilehash: 4bad51e7d0d705ea730382edf80850bca15c5e7a
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="prerequisites-for-net-core-on-macos"></a><span data-ttu-id="6e9c6-104">macOS에서 .NET Core의 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="6e9c6-104">Prerequisites for .NET Core on macOS</span></span>

<span data-ttu-id="6e9c6-105">이 문서에서는 macOS 컴퓨터에서.NET Core 응용 프로그램을 개발, 배포 및 실행하기 위해 필요한 지원되는 macOS 버전 및 .NET Core 종속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6e9c6-105">This article shows you the supported macOS versions and .NET Core dependencies that you need to develop, deploy, and run .NET Core applications on macOS machines.</span></span> <span data-ttu-id="6e9c6-106">다음에 나오는 지원되는 OS 버전 및 종속성은 Mac에서 .NET Core 앱을 개발하기 위한 세 가지 방법, 즉 [즐겨 사용하는 편집기를 통한 명령줄](tutorials/using-with-xplat-cli.md), [Visual Studio Code](https://code.visualstudio.com/) 및 [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/)에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e9c6-106">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on a Mac: via the [command-line with your favorite editor](tutorials/using-with-xplat-cli.md), [Visual Studio Code](https://code.visualstudio.com/), and [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span></span>

## <a name="supported-macos-versions"></a><span data-ttu-id="6e9c6-107">지원되는 macOS 버전</span><span class="sxs-lookup"><span data-stu-id="6e9c6-107">Supported macOS versions</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="6e9c6-108">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="6e9c6-108">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="6e9c6-109">.NET Core 2.x는 다음 macOS 버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e9c6-109">.NET Core 2.x is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="6e9c6-110">macOS 10.12 "Sierra" 이상 버전</span><span class="sxs-lookup"><span data-stu-id="6e9c6-110">macOS 10.12 "Sierra" and later versions</span></span>

<span data-ttu-id="6e9c6-111">지원 OS 버전 중 .NET Core 2.x를 지원하는 운영 체제 및 수명 주기 정책 링크는 [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)(.NET Core 2.x가 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6e9c6-111">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6e9c6-112">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6e9c6-112">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="6e9c6-113">.NET Core 1.x는 다음 macOS 버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e9c6-113">.NET Core 1.x is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="6e9c6-114">macOS 10.12 "Sierra"</span><span class="sxs-lookup"><span data-stu-id="6e9c6-114">macOS 10.12 "Sierra"</span></span>
* <span data-ttu-id="6e9c6-115">macOS 10.11 "El Capitan"</span><span class="sxs-lookup"><span data-stu-id="6e9c6-115">macOS 10.11 "El Capitan"</span></span>

<span data-ttu-id="6e9c6-116">지원 OS 버전 중 .NET Core 1.x를 지원하는 운영 체제 및 수명 주기 정책 링크는 [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)(.NET Core 1.x가 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6e9c6-116">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

---

## <a name="net-core-dependencies"></a><span data-ttu-id="6e9c6-117">.NET Core 종속성</span><span class="sxs-lookup"><span data-stu-id="6e9c6-117">.NET Core dependencies</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="6e9c6-118">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="6e9c6-118">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="6e9c6-119">[.NET 다운로드](https://www.microsoft.com/net/download/core)에서 .NET Core SDK를 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6e9c6-119">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="6e9c6-120">macOS에 설치하는 데 문제가 있는 경우 설치된 버전에 해당하는 [알려진 문제](https://github.com/dotnet/core/tree/master/release-notes/2.0) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6e9c6-120">If you have problems with the installation on macOS, consult the [Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) topic for the version you have installed.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6e9c6-121">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6e9c6-121">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="6e9c6-122">**.NET Core 1.x**</span><span class="sxs-lookup"><span data-stu-id="6e9c6-122">**.NET Core 1.x**</span></span>

<span data-ttu-id="6e9c6-123">.NET Core 1.x를 macOS에서 실행할 때는 OpenSSL이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6e9c6-123">.NET Core 1.x requires OpenSSL when running on macOS.</span></span> <span data-ttu-id="6e9c6-124">OpenSSL을 획득하는 쉬운 방법은 macOS용 [Homebrew("brew")](https://brew.sh/) 패키지 관리자를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6e9c6-124">An easy way to obtain OpenSSL is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="6e9c6-125">*brew*를 설치한 후 터미널(명령) 프롬프트에서 다음 명령을 실행하여 OpenSSL을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6e9c6-125">After installing *brew*, install OpenSSL by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

<span data-ttu-id="6e9c6-126">[.NET 다운로드](https://www.microsoft.com/net/download/core)에서 .NET Core SDK를 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6e9c6-126">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="6e9c6-127">macOS에 설치하는 데 문제가 있는 경우 [1.0.0 알려진 문제](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) 및 [1.0.1 알려진 문제](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6e9c6-127">If you have problems with the installation on macOS, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics.</span></span>

---

## <a name="increase-the-maximum-open-file-limit-net-core-versions-before-net-core-sdk-202"></a><span data-ttu-id="6e9c6-128">열려 있는 최대 파일 제한 늘리기(.NET Core SDK 2.0.2 이전 .NET Core 버전)</span><span class="sxs-lookup"><span data-stu-id="6e9c6-128">Increase the maximum open file limit (.NET Core versions before .NET Core SDK 2.0.2)</span></span> 

<span data-ttu-id="6e9c6-129">.NET Core 버전(.NET Core SDK 2.0.2 이전)에서 macOS에서 열려 있는 기본 파일 제한은 프로젝트를 복원하거나 단위 테스트를 실행하는 등 일부 .NET Core 작업에 충분하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e9c6-129">In older .NET Core versions (before .NET Core SDK 2.0.2), the default open file limit on macOS may not be sufficient for some .NET Core workloads, such as restoring projects or running unit tests.</span></span>

<span data-ttu-id="6e9c6-130">다음 단계를 수행하여 이 제한을 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e9c6-130">You can increase this limit by following these steps:</span></span>

1. <span data-ttu-id="6e9c6-131">텍스트 편집기를 사용하여 새 파일 _/Library/LaunchDaemons/limit.maxfiles.plist_를 만들고 이 콘텐츠로 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="6e9c6-131">Using a text editor, create a new file _/Library/LaunchDaemons/limit.maxfiles.plist_, and save the file with this content:</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN"
        "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
  <dict>
    <key>Label</key>
    <string>limit.maxfiles</string>
    <key>ProgramArguments</key>
    <array>
      <string>launchctl</string>
      <string>limit</string>
      <string>maxfiles</string>
      <string>2048</string>
      <string>4096</string>
    </array>
    <key>RunAtLoad</key>
    <true/>
    <key>ServiceIPC</key>
    <false/>
  </dict>
</plist>
```

2. <span data-ttu-id="6e9c6-132">터미널 창에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6e9c6-132">In a terminal window, run the following command:</span></span>

```console
echo 'ulimit -n 2048' | sudo tee -a /etc/profile
```

3. <span data-ttu-id="6e9c6-133">Mac을 다시 부팅하여 이 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="6e9c6-133">Reboot your Mac to apply these settings.</span></span>

## <a name="visual-studio-for-mac"></a><span data-ttu-id="6e9c6-134">Visual Studio for Mac</span><span class="sxs-lookup"><span data-stu-id="6e9c6-134">Visual Studio for Mac</span></span>

<span data-ttu-id="6e9c6-135">.NET Core SDK를 사용하여 .NET Core 응용 프로그램을 개발하기 위해 원하는 편집기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e9c6-135">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="6e9c6-136">그러나 통합 개발 환경의 Mac에서 .NET Core 응용 프로그램을 개발하려는 경우 [Mac용 Visual Studio](https://www.visualstudio.com/vs/visual-studio-mac/)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e9c6-136">However, if you want to develop .NET Core applications on a Mac in an integrated development environment, you can use [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span></span> 

<span data-ttu-id="6e9c6-137">Visual Studio for Mac을 사용하여 macOS에서 .NET Core로 개발하려면 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6e9c6-137">.NET Core development on macOS with Visual Studio for Mac requires:</span></span>

* <span data-ttu-id="6e9c6-138">지원되는 macOS 운영 체제 버전</span><span class="sxs-lookup"><span data-stu-id="6e9c6-138">A supported version of the macOS operating system</span></span>
* <span data-ttu-id="6e9c6-139">OpenSSL(.NET Core 1.x 전용, .NET Core 2.x는 macOS에서 기본적으로 제공되는 보안 서비스를 사용함)</span><span class="sxs-lookup"><span data-stu-id="6e9c6-139">OpenSSL (.NET Core 1.x only; .NET Core 2.x uses security services available natively in macOS)</span></span>
* <span data-ttu-id="6e9c6-140">.NET Core SDK for Mac</span><span class="sxs-lookup"><span data-stu-id="6e9c6-140">.NET Core SDK for Mac</span></span>
* [<span data-ttu-id="6e9c6-141">Visual Studio for Mac</span><span class="sxs-lookup"><span data-stu-id="6e9c6-141">Visual Studio for Mac</span></span>](https://www.visualstudio.com/vs/visual-studio-mac/)
