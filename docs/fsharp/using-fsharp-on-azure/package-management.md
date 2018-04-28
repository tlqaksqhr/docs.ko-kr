---
title: 'F #을 사용한 패키지 관리를 사용 하 여 Azure에 대 한'
description: 'F # Azure 종속성을 관리 하려면 Paket 또는 Nuget 사용'
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: conceptual
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: da6938c6ee29292571f4269c68a9148c13738422
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="package-management-for-f-azure-dependencies"></a><span data-ttu-id="90005-103">F# Azure 종속성에 대한 패키지 관리</span><span class="sxs-lookup"><span data-stu-id="90005-103">Package Management for F# Azure Dependencies</span></span>

<span data-ttu-id="90005-104">Azure 개발에 대 한 패키지를 가져오는 패키지 관리자를 사용 하는 경우 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="90005-104">Obtaining packages for Azure development is easy when you use a package manager.</span></span> <span data-ttu-id="90005-105">두 옵션은 [Paket](https://fsprojects.github.io/Paket/) 및 [NuGet](https://www.nuget.org/)합니다.</span><span class="sxs-lookup"><span data-stu-id="90005-105">The two options are [Paket](https://fsprojects.github.io/Paket/) and [NuGet](https://www.nuget.org/).</span></span>

## <a name="using-paket"></a><span data-ttu-id="90005-106">Paket를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="90005-106">Using Paket</span></span>

<span data-ttu-id="90005-107">사용 중인 경우 [Paket](https://fsprojects.github.io/Paket/) 종속성 관리자를 사용 하 여는 `paket.exe` Azure 종속성을 추가 하는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="90005-107">If you're using [Paket](https://fsprojects.github.io/Paket/) as your dependency manager, you can use the `paket.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="90005-108">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="90005-108">For example:</span></span>

    > paket add nuget WindowsAzure.Storage

<span data-ttu-id="90005-109">사용 중인 경우 또는 [모노](https://www.mono-project.com/) 플랫폼 간.NET 개발을 위한:</span><span class="sxs-lookup"><span data-stu-id="90005-109">Or, if you're using [Mono](https://www.mono-project.com/) for cross-platform .NET development:</span></span>

    > mono paket.exe add nuget WindowsAzure.Storage

<span data-ttu-id="90005-110">이렇게 하면 추가 됩니다 `WindowsAzure.Storage` 수정 하면 현재 디렉터리에 프로젝트에 대 한 패키지 종속성 집합에는 `paket.dependencies` 파일을 선택한 패키지를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="90005-110">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, modify the `paket.dependencies` file, and download the package.</span></span> <span data-ttu-id="90005-111">이전에 종속성을 설정 하거나 사용 하는 프로젝트에 종속성 설치를 다른 개발자가 경우 해결 하 고 다음과 같은 로컬 종속성을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90005-111">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

    > paket install

<span data-ttu-id="90005-112">또는 모노 개발:</span><span class="sxs-lookup"><span data-stu-id="90005-112">Or, for Mono development:</span></span>

    > mono paket.exe install

<span data-ttu-id="90005-113">다음과 같은 최신 버전으로 모든 패키지 종속 파일을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90005-113">You can update all your package dependencies to the latest version like this:</span></span>

    > paket update

<span data-ttu-id="90005-114">또는 모노 개발:</span><span class="sxs-lookup"><span data-stu-id="90005-114">Or, for Mono development:</span></span>

    > mono paket.exe update

## <a name="using-nuget"></a><span data-ttu-id="90005-115">Nuget을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="90005-115">Using Nuget</span></span>

<span data-ttu-id="90005-116">사용 중인 경우 [NuGet](https://www.nuget.org/) 종속성 관리자를 사용 하 여는 `nuget.exe` Azure 종속성을 추가 하는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="90005-116">If you're using [NuGet](https://www.nuget.org/) as your dependency manager, you can use the `nuget.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="90005-117">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="90005-117">For example:</span></span>

    > nuget install WindowsAzure.Storage -ExcludeVersion

<span data-ttu-id="90005-118">또는 모노 개발:</span><span class="sxs-lookup"><span data-stu-id="90005-118">Or, for Mono development:</span></span>

    > mono nuget.exe install WindowsAzure.Storage -ExcludeVersion

<span data-ttu-id="90005-119">이렇게 하면 추가 됩니다 `WindowsAzure.Storage` 를 현재 디렉터리 및 다운로드 패키지에 프로젝트에 대 한 패키지 종속 파일의 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="90005-119">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, and download the package.</span></span> <span data-ttu-id="90005-120">이전에 종속성을 설정 하거나 사용 하는 프로젝트에 종속성 설치를 다른 개발자가 경우 해결 하 고 다음과 같은 로컬 종속성을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90005-120">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

    > nuget restore 

<span data-ttu-id="90005-121">또는 모노 개발:</span><span class="sxs-lookup"><span data-stu-id="90005-121">Or, for Mono development:</span></span>

    > mono nuget.exe restore

<span data-ttu-id="90005-122">다음과 같은 최신 버전으로 모든 패키지 종속 파일을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90005-122">You can update all your package dependencies to the latest version like this:</span></span>

    > nuget update

<span data-ttu-id="90005-123">또는 모노 개발:</span><span class="sxs-lookup"><span data-stu-id="90005-123">Or, for Mono development:</span></span>

    > mono nuget.exe update

## <a name="referencing-assemblies"></a><span data-ttu-id="90005-124">어셈블리 참조</span><span class="sxs-lookup"><span data-stu-id="90005-124">Referencing Assemblies</span></span>

<span data-ttu-id="90005-125">F # 스크립트에 패키지를 사용 하기 위해 사용 하 여 패키지에 포함 된 어셈블리를 참조 해야는 `#r` 지시문입니다.</span><span class="sxs-lookup"><span data-stu-id="90005-125">In order to use your packages in your F# script, you need to reference the assemblies included in the packages using a `#r` directive.</span></span> <span data-ttu-id="90005-126">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="90005-126">For example:</span></span>

    > #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"

<span data-ttu-id="90005-127">볼 수 있듯이 DLL과 하지 않을 수 있는 정확 하 게 패키지 이름과 전체 DLL 이름에 상대 경로를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90005-127">As you can see, you'll need to specify the relative path to the DLL and the full DLL name, which may not be exactly the same as the package name.</span></span> <span data-ttu-id="90005-128">경로 프레임 워크 버전 및 패키지 버전 번호가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90005-128">The path will include a framework version and possibly a package version number.</span></span> <span data-ttu-id="90005-129">설치 된 모든 어셈블리를 찾으려면 Windows 명령줄에서 다음과 같이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90005-129">To find all the installed assemblies, you can use something like this on a Windows command line:</span></span>

    > cd packages/WindowsAzure.Storage
    > dir /s/b *.dll

<span data-ttu-id="90005-130">또는 Unix 셸에서 다음과 같은이:</span><span class="sxs-lookup"><span data-stu-id="90005-130">Or in a Unix shell, something like this:</span></span>

    > find packages/WindowsAzure.Storage -name "*.dll"

<span data-ttu-id="90005-131">이렇게 하면 경로는 설치 된 어셈블리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90005-131">This will give you the paths to the installed assemblies.</span></span> <span data-ttu-id="90005-132">여기에서 프레임 워크 버전에 대 한 올바른 경로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90005-132">From there, you can select the correct path for your framework version.</span></span>
