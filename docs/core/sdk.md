---
title: .NET Core SDK 개요
description: .NET Core 프로젝트를 만드는 데 사용되는 라이브러리 및 도구 집합인 .NET Core SDK에 관해 알아보세요.
author: blackdwarf
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: e75774f24b18796a618264eb7cca64d3aa243e5e
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="net-core-sdk-overview"></a><span data-ttu-id="101ad-103">.NET Core SDK 개요</span><span class="sxs-lookup"><span data-stu-id="101ad-103">.NET Core SDK Overview</span></span> 

## <a name="introduction"></a><span data-ttu-id="101ad-104">소개</span><span class="sxs-lookup"><span data-stu-id="101ad-104">Introduction</span></span>
<span data-ttu-id="101ad-105">.NET Core SDK(소프트웨어 개발 키트)는 개발자들이 .NET Core 응용 프로그램과 라이브러리를 만드는 데 사용할 수 있는 라이브러리 및 도구 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="101ad-105">.NET Core Software Development Kit (SDK) is a set of libraries and tools that allow developers to create .NET Core applications and libraries.</span></span> <span data-ttu-id="101ad-106">이 SDK는 개발자들이 가장 많이 사용할만한 패키지로서</span><span class="sxs-lookup"><span data-stu-id="101ad-106">This is the package that developers will most likely acquire.</span></span> 

<span data-ttu-id="101ad-107">다음 구성 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="101ad-107">It contains the following components:</span></span>

1. <span data-ttu-id="101ad-108">응용 프로그램을 빌드하는 데 사용되는 .NET Core 명령줄 도구</span><span class="sxs-lookup"><span data-stu-id="101ad-108">The .NET Core Command Line Tools that are used to build applications</span></span>
2. <span data-ttu-id="101ad-109">응용 프로그램을 빌드 및 실행할 수 있는 .NET Core(라이브러리 및 런타임)</span><span class="sxs-lookup"><span data-stu-id="101ad-109">.NET Core (libraries and runtime) that allow applications to both be built and run</span></span>
3. <span data-ttu-id="101ad-110">응용 프로그램은 물론 [CLI 명령](tools/index.md)도 실행하기 위한 `dotnet` 드라이버</span><span class="sxs-lookup"><span data-stu-id="101ad-110">The `dotnet` driver for running the [CLI commands](tools/index.md) as well as running applications</span></span>


## <a name="acquiring-the-net-core-sdk"></a><span data-ttu-id="101ad-111">.NET Core SDK 가져오기</span><span class="sxs-lookup"><span data-stu-id="101ad-111">Acquiring the .NET Core SDK</span></span>
<span data-ttu-id="101ad-112">모든 도구와 마찬가지로 먼저 컴퓨터에 도구를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="101ad-112">As with any tooling, the first thing is to get the tools to your machine.</span></span> <span data-ttu-id="101ad-113">시나리오에 따라, 기본 설치 관리자를 사용하여 SDK를 설치할 수도 있고 설치 셸 스크립트를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="101ad-113">Depending on your scenario, you can either use the native installers to install the SDK or use the installation shell script.</span></span>

<span data-ttu-id="101ad-114">기본 설치 관리자는 주로 개발자의 컴퓨터를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="101ad-114">The native installers are primarily meant for developer's machines.</span></span> <span data-ttu-id="101ad-115">Ubuntu의 DEB 패키지 또는 Windows MSI 번들처럼 SDK는 지원되는 플랫폼의 기본 설치 메커니즘을 사용하여 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="101ad-115">The SDK is distributed using each supported platform's native install mechanism, for instance DEB packages on Ubuntu or MSI bundles on Windows.</span></span> <span data-ttu-id="101ad-116">이러한 설치 관리자는 설치 후 SDK를 즉시 사용하려는 사용자에게 필요한 환경을 설치 및 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="101ad-116">These installers will install and set up the environment as needed for the user to use the SDK immediately after the install.</span></span> <span data-ttu-id="101ad-117">그러나 이러한 사용자는 컴퓨터에 대한 관리자 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="101ad-117">However, they also require administrative privileges on the machine.</span></span> <span data-ttu-id="101ad-118">[.NET Core 설치 가이드](https://aka.ms/dotnetcoregs)에서 설치 지침을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="101ad-118">You can view the installation instructions on the [.NET Core installation guide](https://aka.ms/dotnetcoregs).</span></span>

<span data-ttu-id="101ad-119">반면 설치 스크립트를 사용할 경우에는 관리 권한이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="101ad-119">Install scripts, on the other hand, do not require administrative privileges.</span></span> <span data-ttu-id="101ad-120">그러나 컴퓨터에 필수 구성 요소도 설치되지 않습니다. 모든 필수 구성 요소를 수동으로 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="101ad-120">However, they will also not install any prerequisites on the machine; you need to install all of the prerequisites manually.</span></span> <span data-ttu-id="101ad-121">스크립트는 대개 빌드 서버를 설정하거나 관리자 권한 없이 도구를 설치할 경우 사용됩니다(위의 필수 구성 요소 주의 사항 참조).</span><span class="sxs-lookup"><span data-stu-id="101ad-121">The scripts are meant mostly for setting up build servers or when you wish to install the tools without admin privileges (do note the prerequisites caveat above).</span></span> <span data-ttu-id="101ad-122">자세한 내용은 [스크립트 참조 설치 항목](tools/dotnet-install-script.md)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="101ad-122">You can find more information on the [install script reference topic](tools/dotnet-install-script.md).</span></span> <span data-ttu-id="101ad-123">CI 빌드 서버에 SDK를 설치하는 방법에 관심이 있는 경우 [CI 서버와 SDK](tools/using-ci-with-cli.md) 문서를 살펴볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="101ad-123">If you are interested in how to set up SDK on your CI build server you can take a look at the [SDK with CI servers](tools/using-ci-with-cli.md) document.</span></span> 

<span data-ttu-id="101ad-124">기본적으로 SDK는 "SxS”(병렬) 방식으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="101ad-124">By default, the SDK will install in a "side-by-side" (SxS) manner.</span></span> <span data-ttu-id="101ad-125">즉, 특정 시간에 CLI 도구의 여러 버전이 단일 컴퓨터에 공존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="101ad-125">This means that multiple versions of the CLI tools can coexist at any given time on a single machine.</span></span> <span data-ttu-id="101ad-126">그러나 사용되는 올바른 버전에 대해서는 .NET Core 명령줄 도구 항목의 [드라이버 섹션](tools/index.md#driver)에 자세히 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="101ad-126">How the correct version gets used is explained in more detail in the [driver section](tools/index.md#driver) of .NET Core Command Line Tools topic.</span></span>
