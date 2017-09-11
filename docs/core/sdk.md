---
title: ".NET Core SDK 개요"
description: ".NET Core 프로젝트를 만드는 데 사용되는 라이브러리 및 도구 집합인 .NET Core SDK에 관해 알아보세요."
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 26bc9822-e42b-48ec-b0d6-499dc604add7
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8f3d0f5b3bccdd1ca25fa1202c2c727e402fe668
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---

# <a name="net-core-sdk-overview"></a><span data-ttu-id="5f6e4-104">.NET Core SDK 개요</span><span class="sxs-lookup"><span data-stu-id="5f6e4-104">.NET Core SDK Overview</span></span> 

## <a name="introduction"></a><span data-ttu-id="5f6e4-105">소개</span><span class="sxs-lookup"><span data-stu-id="5f6e4-105">Introduction</span></span>
<span data-ttu-id="5f6e4-106">.NET Core SDK(소프트웨어 개발 키트)는 개발자들이 .NET Core 응용 프로그램과 라이브러리를 만드는 데 사용할 수 있는 라이브러리 및 도구 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e4-106">.NET Core Software Development Kit (SDK) is a set of libraries and tools that allow developers to create .NET Core applications and libraries.</span></span> <span data-ttu-id="5f6e4-107">이 SDK는 개발자들이 가장 많이 사용할만한 패키지로서</span><span class="sxs-lookup"><span data-stu-id="5f6e4-107">This is the package that developers will most likely acquire.</span></span> 

<span data-ttu-id="5f6e4-108">다음 구성 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e4-108">It contains the following components:</span></span>

1. <span data-ttu-id="5f6e4-109">응용 프로그램을 빌드하는 데 사용되는 .NET Core 명령줄 도구</span><span class="sxs-lookup"><span data-stu-id="5f6e4-109">The .NET Core Command Line Tools that are used to build applications</span></span>
2. <span data-ttu-id="5f6e4-110">응용 프로그램을 빌드 및 실행할 수 있는 .NET Core(라이브러리 및 런타임)</span><span class="sxs-lookup"><span data-stu-id="5f6e4-110">.NET Core (libraries and runtime) that allow applications to both be built and run</span></span>
3. <span data-ttu-id="5f6e4-111">응용 프로그램은 물론 [CLI 명령](tools/index.md)도 실행하기 위한 `dotnet` 드라이버</span><span class="sxs-lookup"><span data-stu-id="5f6e4-111">The `dotnet` driver for running the [CLI commands](tools/index.md) as well as running applications</span></span>


## <a name="acquiring-the-net-core-sdk"></a><span data-ttu-id="5f6e4-112">.NET Core SDK 가져오기</span><span class="sxs-lookup"><span data-stu-id="5f6e4-112">Acquiring the .NET Core SDK</span></span>
<span data-ttu-id="5f6e4-113">모든 도구와 마찬가지로 먼저 컴퓨터에 도구를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e4-113">As with any tooling, the first thing is to get the tools to your machine.</span></span> <span data-ttu-id="5f6e4-114">시나리오에 따라, 기본 설치 관리자를 사용하여 SDK를 설치할 수도 있고 설치 셸 스크립트를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e4-114">Depending on your scenario, you can either use the native installers to install the SDK or use the installation shell script.</span></span>

<span data-ttu-id="5f6e4-115">기본 설치 관리자는 주로 개발자의 컴퓨터를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e4-115">The native installers are primarily meant for developer's machines.</span></span> <span data-ttu-id="5f6e4-116">Ubuntu의 DEB 패키지 또는 Windows MSI 번들처럼 SDK는 지원되는 플랫폼의 기본 설치 메커니즘을 사용하여 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e4-116">The SDK is distributed using each supported platform's native install mechanism, for instance DEB packages on Ubuntu or MSI bundles on Windows.</span></span> <span data-ttu-id="5f6e4-117">이러한 설치 관리자는 설치 후 SDK를 즉시 사용하려는 사용자에게 필요한 환경을 설치 및 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e4-117">These installers will install and set up the environment as needed for the user to use the SDK immediately after the install.</span></span> <span data-ttu-id="5f6e4-118">그러나 이러한 사용자는 컴퓨터에 대한 관리자 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e4-118">However, they also require administrative privileges on the machine.</span></span> <span data-ttu-id="5f6e4-119">[.NET Core 설치 가이드](https://aka.ms/dotnetcoregs)에서 설치 지침을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e4-119">You can view the installation instructions on the [.NET Core installation guide](https://aka.ms/dotnetcoregs).</span></span>

<span data-ttu-id="5f6e4-120">반면 설치 스크립트를 사용할 경우에는 관리 권한이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e4-120">Install scripts, on the other hand, do not require administrative privileges.</span></span> <span data-ttu-id="5f6e4-121">그러나 컴퓨터에 필수 구성 요소도 설치되지 않습니다. 모든 필수 구성 요소를 수동으로 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e4-121">However, they will also not install any prerequisites on the machine; you need to install all of the prerequisites manually.</span></span> <span data-ttu-id="5f6e4-122">스크립트는 대개 빌드 서버를 설정하거나 관리자 권한 없이 도구를 설치할 경우 사용됩니다(위의 필수 구성 요소 주의 사항 참조).</span><span class="sxs-lookup"><span data-stu-id="5f6e4-122">The scripts are meant mostly for setting up build servers or when you wish to install the tools without admin privileges (do note the prerequisites caveat above).</span></span> <span data-ttu-id="5f6e4-123">자세한 내용은 [스크립트 참조 설치 항목](tools/dotnet-install-script.md)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e4-123">You can find more information on the [install script reference topic](tools/dotnet-install-script.md).</span></span> <span data-ttu-id="5f6e4-124">CI 빌드 서버에 SDK를 설치하는 방법에 관심이 있는 경우 [CI 서버와 SDK](tools/using-ci-with-cli.md) 문서를 살펴볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e4-124">If you are interested in how to set up SDK on your CI build server you can take a look at the [SDK with CI servers](tools/using-ci-with-cli.md) document.</span></span> 

<span data-ttu-id="5f6e4-125">기본적으로 SDK는 "SxS”(병렬) 방식으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e4-125">By default, the SDK will install in a "side-by-side" (SxS) manner.</span></span> <span data-ttu-id="5f6e4-126">즉, 특정 시간에 CLI 도구의 여러 버전이 단일 컴퓨터에 공존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e4-126">This means that multiple versions of the CLI tools can coexist at any given time on a single machine.</span></span> <span data-ttu-id="5f6e4-127">그러나 사용되는 올바른 버전에 대해서는 .NET Core 명령줄 도구 항목의 [드라이버 섹션](tools/index.md#driver)에 자세히 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e4-127">How the correct version gets used is explained in more detail in the [driver section](tools/index.md#driver) of .NET Core Command Line Tools topic.</span></span>

