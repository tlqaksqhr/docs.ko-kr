---
title: "Mac에서 .NET Core의 필수 구성 요소"
description: "macOS 컴퓨터에서.NET Core 응용 프로그램을 개발, 배포 및 실행하기 위해 지원되는 macOS 버전 및 .NET Core 종속성입니다."
keywords: .NET, .NET Core, macOS, Mac
author: guardrex
ms.author: mairaw
ms.date: 09/27/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.openlocfilehash: 16f3cfd482bddfff1b9ad56e7ffe58ae2aed4980
ms.sourcegitcommit: 62d3e3e74c1b7ffa927590012c0b9f87de1b0848
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="prerequisites-for-net-core-on-macos"></a><span data-ttu-id="af239-104">MacOS에서.NET Core에 대 한 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="af239-104">Prerequisites for .NET Core on macOS</span></span>

<span data-ttu-id="af239-105">이 문서에서는 macOS 컴퓨터에서.NET Core 응용 프로그램을 개발, 배포 및 실행하기 위해 필요한 지원되는 macOS 버전 및 .NET Core 종속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="af239-105">This article shows you the supported macOS versions and .NET Core dependencies that you need to develop, deploy, and run .NET Core applications on macOS machines.</span></span> <span data-ttu-id="af239-106">다음에 나오는 지원되는 OS 버전 및 종속성은 Mac에서 .NET Core 앱을 개발하기 위한 세 가지 방법, 즉 [즐겨 사용하는 편집기를 통한 명령줄](tutorials/using-with-xplat-cli.md), [Visual Studio Code](https://code.visualstudio.com/) 및 [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/)에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="af239-106">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on a Mac: via the [command-line with your favorite editor](tutorials/using-with-xplat-cli.md), [Visual Studio Code](https://code.visualstudio.com/), and [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span></span>

## <a name="supported-macos-versions"></a><span data-ttu-id="af239-107">지원되는 macOS 버전</span><span class="sxs-lookup"><span data-stu-id="af239-107">Supported macOS versions</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="af239-108">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="af239-108">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="af239-109">.NET core 2.x macOS의 다음 버전에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af239-109">.NET Core 2.x is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="af239-110">macOS 10.12 "시에라" 및 이상 버전</span><span class="sxs-lookup"><span data-stu-id="af239-110">macOS 10.12 "Sierra" and later versions</span></span>

<span data-ttu-id="af239-111">지원 OS 버전 중 .NET Core 2.x를 지원하는 운영 체제 및 수명 주기 정책 링크는 [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)(.NET Core 2.x가 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af239-111">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="af239-112">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="af239-112">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="af239-113">.NET core 1.x macOS의 다음 버전에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af239-113">.NET Core 1.x is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="af239-114">macOS 10.12 "Sierra"</span><span class="sxs-lookup"><span data-stu-id="af239-114">macOS 10.12 "Sierra"</span></span>
* <span data-ttu-id="af239-115">macOS 10.11 "El Capitan"</span><span class="sxs-lookup"><span data-stu-id="af239-115">macOS 10.11 "El Capitan"</span></span>

<span data-ttu-id="af239-116">지원 OS 버전 중 .NET Core 1.x를 지원하는 운영 체제 및 수명 주기 정책 링크는 [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)(.NET Core 1.x가 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af239-116">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

---

## <a name="net-core-dependencies"></a><span data-ttu-id="af239-117">.NET Core 종속성</span><span class="sxs-lookup"><span data-stu-id="af239-117">.NET Core dependencies</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="af239-118">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="af239-118">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="af239-119">[.NET 다운로드](https://www.microsoft.com/net/download/core)에서 .NET Core SDK를 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="af239-119">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="af239-120">macOS에 설치하는 데 문제가 있는 경우 설치된 버전에 해당하는 [알려진 문제](https://github.com/dotnet/core/tree/master/release-notes/2.0) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af239-120">If you have problems with the installation on macOS, consult the [Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) topic for the version you have installed.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="af239-121">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="af239-121">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="af239-122">**.NET Core 1.x**</span><span class="sxs-lookup"><span data-stu-id="af239-122">**.NET Core 1.x**</span></span>

<span data-ttu-id="af239-123">.NET Core 1.x를 macOS에서 실행할 때는 OpenSSL이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="af239-123">.NET Core 1.x requires OpenSSL when running on macOS.</span></span> <span data-ttu-id="af239-124">OpenSSL을 획득하는 쉬운 방법은 macOS용 [Homebrew("brew")](https://brew.sh/) 패키지 관리자를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="af239-124">An easy way to obtain OpenSSL is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="af239-125">*brew*를 설치한 후 터미널(명령) 프롬프트에서 다음 명령을 실행하여 OpenSSL을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="af239-125">After installing *brew*, install OpenSSL by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

<span data-ttu-id="af239-126">[.NET 다운로드](https://www.microsoft.com/net/download/core)에서 .NET Core SDK를 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="af239-126">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="af239-127">macOS에 설치하는 데 문제가 있는 경우 [1.0.0 알려진 문제](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) 및 [1.0.1 알려진 문제](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af239-127">If you have problems with the installation on macOS, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics.</span></span>

---

## <a name="increase-the-maximum-open-file-limit"></a><span data-ttu-id="af239-128">열려 있는 최대 파일 제한 증가</span><span class="sxs-lookup"><span data-stu-id="af239-128">Increase the maximum open file limit</span></span>

<span data-ttu-id="af239-129">기본 파일 열기 제한 macOS에 프로젝트를 복원 하거나 단위 테스트를 실행 하는 등 일부.NET Core 작업에 대 한 충분 한 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af239-129">The default open file limit on macOS may not be sufficient for some .NET Core workloads, such as restoring projects or running unit tests.</span></span>

<span data-ttu-id="af239-130">다음이 단계를 수행 하 여이 제한을 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af239-130">You can increase this limit by following these steps:</span></span>

1. <span data-ttu-id="af239-131">텍스트 편집기를 사용 하 여 새 파일을 만듭니다 _/Library/LaunchDaemons/limit.maxfiles.plist_, 해당 콘텐츠 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="af239-131">Using a text editor, create a new file _/Library/LaunchDaemons/limit.maxfiles.plist_, and save the file with this content:</span></span>

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

2. <span data-ttu-id="af239-132">터미널 창에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="af239-132">In a terminal window, run the following command:</span></span>

```console
echo 'ulimit -n 2048' | sudo tee -a /etc/profile
```

3. <span data-ttu-id="af239-133">Mac이이 설정을 적용 하려면 다시 부팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="af239-133">Reboot your Mac to apply these settings.</span></span>

## <a name="visual-studio-for-mac"></a><span data-ttu-id="af239-134">Visual Studio for Mac</span><span class="sxs-lookup"><span data-stu-id="af239-134">Visual Studio for Mac</span></span>

<span data-ttu-id="af239-135">.NET Core SDK를 사용하여 .NET Core 응용 프로그램을 개발하기 위해 원하는 편집기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af239-135">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="af239-136">그러나 통합 개발 환경의 Mac에서 .NET Core 응용 프로그램을 개발하려는 경우 [Mac용 Visual Studio](https://www.visualstudio.com/vs/visual-studio-mac/)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af239-136">However, if you want to develop .NET Core applications on a Mac in an integrated development environment, you can use [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span></span> 

<span data-ttu-id="af239-137">Visual Studio for Mac을 사용하여 macOS에서 .NET Core로 개발하려면 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="af239-137">.NET Core development on macOS with Visual Studio for Mac requires:</span></span>

* <span data-ttu-id="af239-138">지원되는 macOS 운영 체제 버전</span><span class="sxs-lookup"><span data-stu-id="af239-138">A supported version of the macOS operating system</span></span>
* <span data-ttu-id="af239-139">OpenSSL(.NET Core 1.x 전용, .NET Core 2.x는 macOS에서 기본적으로 제공되는 보안 서비스를 사용함)</span><span class="sxs-lookup"><span data-stu-id="af239-139">OpenSSL (.NET Core 1.x only; .NET Core 2.x uses security services available natively in macOS)</span></span>
* <span data-ttu-id="af239-140">.NET Core SDK for Mac</span><span class="sxs-lookup"><span data-stu-id="af239-140">.NET Core SDK for Mac</span></span>
* [<span data-ttu-id="af239-141">Visual Studio for Mac</span><span class="sxs-lookup"><span data-stu-id="af239-141">Visual Studio for Mac</span></span>](https://www.visualstudio.com/vs/visual-studio-mac/)
