---
title: "Mac에서 .NET Core의 필수 구성 요소"
description: "macOS 컴퓨터에서.NET Core 응용 프로그램을 개발, 배포 및 실행하기 위해 지원되는 macOS 버전 및 .NET Core 종속성입니다."
keywords: .NET, .NET Core, macOS, Mac
author: guardrex
ms.author: mairaw
ms.date: 07/07/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8feaee2cbfa55e23bd49c0ab76d995f15be343b4
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---

# <a name="prerequisites-for-net-core-on-mac"></a><span data-ttu-id="f69e0-104">Mac에서 .NET Core의 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="f69e0-104">Prerequisites for .NET Core on Mac</span></span>

<span data-ttu-id="f69e0-105">이 문서에서는 macOS 컴퓨터에서.NET Core 응용 프로그램을 개발, 배포 및 실행하기 위해 필요한 지원되는 macOS 버전 및 .NET Core 종속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f69e0-105">This article shows you the supported macOS versions and .NET Core dependencies that you need to develop, deploy, and run .NET Core applications on macOS machines.</span></span> <span data-ttu-id="f69e0-106">다음에 나오는 지원되는 OS 버전 및 종속성은 Mac에서 .NET Core 앱을 개발하기 위한 세 가지 방법, 즉 [즐겨 사용하는 편집기를 통한 명령줄](tutorials/using-with-xplat-cli.md), [Visual Studio Code](https://code.visualstudio.com/) 및 [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/)에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f69e0-106">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on a Mac: via the [command-line with your favorite editor](tutorials/using-with-xplat-cli.md), [Visual Studio Code](https://code.visualstudio.com/), and [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span></span>

## <a name="supported-macos-versions"></a><span data-ttu-id="f69e0-107">지원되는 macOS 버전</span><span class="sxs-lookup"><span data-stu-id="f69e0-107">Supported macOS versions</span></span>

<span data-ttu-id="f69e0-108">.NET Core는 다음 macOS 버전에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f69e0-108">.NET Core is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="f69e0-109">macOS 10.12 "Sierra"</span><span class="sxs-lookup"><span data-stu-id="f69e0-109">macOS 10.12 "Sierra"</span></span>
* <span data-ttu-id="f69e0-110">macOS 10.11 "El Capitan"(.NET Core 1.x만)</span><span class="sxs-lookup"><span data-stu-id="f69e0-110">macOS 10.11 "El Capitan" (.NET Core 1.x only)</span></span>

<span data-ttu-id="f69e0-111">[지원되는 OS 버전](https://github.com/dotnet/core/blob/master/roadmap.md#supported-os-versions)에서 지원되는 운영 체제의 전체 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f69e0-111">See [Supported OS Versions](https://github.com/dotnet/core/blob/master/roadmap.md#supported-os-versions) for the complete list of supported operating systems.</span></span>

## <a name="net-core-dependencies"></a><span data-ttu-id="f69e0-112">.NET Core 종속성</span><span class="sxs-lookup"><span data-stu-id="f69e0-112">.NET Core dependencies</span></span>

<span data-ttu-id="f69e0-113">**.NET Core 1.x**</span><span class="sxs-lookup"><span data-stu-id="f69e0-113">**.NET Core 1.x**</span></span>

<span data-ttu-id="f69e0-114">.NET Core 1.x를 macOS에서 실행할 때는 OpenSSL이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f69e0-114">.NET Core 1.x requires OpenSSL when running on macOS.</span></span> <span data-ttu-id="f69e0-115">OpenSSL을 획득하는 쉬운 방법은 macOS용 [Homebrew("brew")](https://brew.sh/) 패키지 관리자를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f69e0-115">An easy way to obtain OpenSSL is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="f69e0-116">*brew*를 설치한 후 터미널(명령) 프롬프트에서 다음 명령을 실행하여 OpenSSL을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f69e0-116">After installing *brew*, install OpenSSL by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

<span data-ttu-id="f69e0-117">[.NET 다운로드](https://www.microsoft.com/net/download/core)에서 .NET Core SDK를 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f69e0-117">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="f69e0-118">macOS에 설치하는 데 문제가 있는 경우 [1.0.0 알려진 문제](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) 및 [1.0.1 알려진 문제](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f69e0-118">If you have problems with the installation on macOS, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics.</span></span>

<span data-ttu-id="f69e0-119">**.NET Core 2.x**</span><span class="sxs-lookup"><span data-stu-id="f69e0-119">**.NET Core 2.x**</span></span>

<span data-ttu-id="f69e0-120">[.NET 다운로드](https://www.microsoft.com/net/download/core)에서 .NET Core SDK를 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f69e0-120">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="f69e0-121">macOS에 설치하는 데 문제가 있는 경우 설치된 버전에 해당하는 [알려진 문제](https://github.com/dotnet/core/tree/master/release-notes/2.0) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f69e0-121">If you have problems with the installation on macOS, consult the [Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) topic for the version you have installed.</span></span>

## <a name="visual-studio-for-mac"></a><span data-ttu-id="f69e0-122">Visual Studio for Mac</span><span class="sxs-lookup"><span data-stu-id="f69e0-122">Visual Studio for Mac</span></span>

<span data-ttu-id="f69e0-123">.NET Core SDK를 사용하여 .NET Core 응용 프로그램을 개발하기 위해 원하는 편집기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f69e0-123">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="f69e0-124">그러나 통합 개발 환경의 Mac에서 .NET Core 응용 프로그램을 개발하려는 경우 [Mac용 Visual Studio](https://www.visualstudio.com/vs/visual-studio-mac/)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f69e0-124">However, if you want to develop .NET Core applications on a Mac in an integrated development environment, you can use [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span></span> 

<span data-ttu-id="f69e0-125">Visual Studio for Mac을 사용하여 macOS에서 .NET Core로 개발하려면 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f69e0-125">.NET Core development on macOS with Visual Studio for Mac requires:</span></span>

* <span data-ttu-id="f69e0-126">지원되는 macOS 운영 체제 버전</span><span class="sxs-lookup"><span data-stu-id="f69e0-126">A supported version of the macOS operating system</span></span>
* <span data-ttu-id="f69e0-127">OpenSSL(.NET Core 1.x 전용, .NET Core 2.x는 macOS에서 기본적으로 제공되는 보안 서비스를 사용함)</span><span class="sxs-lookup"><span data-stu-id="f69e0-127">OpenSSL (.NET Core 1.x only; .NET Core 2.x uses security services available natively in macOS)</span></span>
* <span data-ttu-id="f69e0-128">.NET Core SDK for Mac</span><span class="sxs-lookup"><span data-stu-id="f69e0-128">.NET Core SDK for Mac</span></span>
* [<span data-ttu-id="f69e0-129">Visual Studio for Mac</span><span class="sxs-lookup"><span data-stu-id="f69e0-129">Visual Studio for Mac</span></span>](https://www.visualstudio.com/vs/visual-studio-mac/)

