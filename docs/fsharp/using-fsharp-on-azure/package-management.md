---
title: "F #을 사용한 패키지 관리를 사용 하 여 Azure에 대 한"
description: "F # Azure 종속성을 관리 하려면 Paket 또는 Nuget 사용"
keywords: "visual f #, f #, 기능 프로그래밍,.NET,.NET Core를 Azure"
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: dd32ef9c-5416-467e-9fa3-c9ee3bb08456
ms.openlocfilehash: 22dc94ea69e0dfb95e22da4bc64ce915398190d2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="package-management-for-f-azure-dependencies"></a><span data-ttu-id="fbc08-104">F# Azure 종속성에 대한 패키지 관리</span><span class="sxs-lookup"><span data-stu-id="fbc08-104">Package Management for F# Azure Dependencies</span></span>

<span data-ttu-id="fbc08-105">Azure 개발에 대 한 패키지를 가져오는 패키지 관리자를 사용 하는 경우 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="fbc08-105">Obtaining packages for Azure development is easy when you use a package manager.</span></span> <span data-ttu-id="fbc08-106">두 옵션은 [Paket](https://fsprojects.github.io/Paket/) 및 [NuGet](https://www.nuget.org/)합니다.</span><span class="sxs-lookup"><span data-stu-id="fbc08-106">The two options are [Paket](https://fsprojects.github.io/Paket/) and [NuGet](https://www.nuget.org/).</span></span>

## <a name="using-paket"></a><span data-ttu-id="fbc08-107">Paket를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="fbc08-107">Using Paket</span></span>

<span data-ttu-id="fbc08-108">사용 중인 경우 [Paket](https://fsprojects.github.io/Paket/) 종속성 관리자를 사용 하 여는 `paket.exe` Azure 종속성을 추가 하는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="fbc08-108">If you're using [Paket](https://fsprojects.github.io/Paket/) as your dependency manager, you can use the `paket.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="fbc08-109">예:</span><span class="sxs-lookup"><span data-stu-id="fbc08-109">For example:</span></span>

    > paket add nuget WindowsAzure.Storage

<span data-ttu-id="fbc08-110">사용 중인 경우 또는 [모노](http://www.mono-project.com/) 플랫폼 간.NET 개발을 위한:</span><span class="sxs-lookup"><span data-stu-id="fbc08-110">Or, if you're using [Mono](http://www.mono-project.com/) for cross-platform .NET development:</span></span>

    > mono paket.exe add nuget WindowsAzure.Storage

<span data-ttu-id="fbc08-111">이렇게 하면 추가 됩니다 `WindowsAzure.Storage` 수정 하면 현재 디렉터리에 프로젝트에 대 한 패키지 종속성 집합에는 `paket.dependencies` 파일을 선택한 패키지를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbc08-111">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, modify the `paket.dependencies` file, and download the package.</span></span> <span data-ttu-id="fbc08-112">이전에 종속성을 설정 하거나 사용 하는 프로젝트에 종속성 설치를 다른 개발자가 경우 해결 하 고 다음과 같은 로컬 종속성을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbc08-112">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

    > paket install

<span data-ttu-id="fbc08-113">또는 모노 개발:</span><span class="sxs-lookup"><span data-stu-id="fbc08-113">Or, for Mono development:</span></span>

    > mono paket.exe install

<span data-ttu-id="fbc08-114">다음과 같은 최신 버전으로 모든 패키지 종속 파일을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbc08-114">You can update all your package dependencies to the latest version like this:</span></span>

    > paket update

<span data-ttu-id="fbc08-115">또는 모노 개발:</span><span class="sxs-lookup"><span data-stu-id="fbc08-115">Or, for Mono development:</span></span>

    > mono paket.exe update

## <a name="using-nuget"></a><span data-ttu-id="fbc08-116">Nuget을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="fbc08-116">Using Nuget</span></span>

<span data-ttu-id="fbc08-117">사용 중인 경우 [NuGet](https://www.nuget.org/) 종속성 관리자를 사용 하 여는 `nuget.exe` Azure 종속성을 추가 하는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="fbc08-117">If you're using [NuGet](https://www.nuget.org/) as your dependency manager, you can use the `nuget.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="fbc08-118">예:</span><span class="sxs-lookup"><span data-stu-id="fbc08-118">For example:</span></span>

    > nuget install WindowsAzure.Storage -ExcludeVersion

<span data-ttu-id="fbc08-119">또는 모노 개발:</span><span class="sxs-lookup"><span data-stu-id="fbc08-119">Or, for Mono development:</span></span>

    > mono nuget.exe install WindowsAzure.Storage -ExcludeVersion

<span data-ttu-id="fbc08-120">이렇게 하면 추가 됩니다 `WindowsAzure.Storage` 를 현재 디렉터리 및 다운로드 패키지에 프로젝트에 대 한 패키지 종속 파일의 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="fbc08-120">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, and download the package.</span></span> <span data-ttu-id="fbc08-121">이전에 종속성을 설정 하거나 사용 하는 프로젝트에 종속성 설치를 다른 개발자가 경우 해결 하 고 다음과 같은 로컬 종속성을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbc08-121">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

    > nuget restore 

<span data-ttu-id="fbc08-122">또는 모노 개발:</span><span class="sxs-lookup"><span data-stu-id="fbc08-122">Or, for Mono development:</span></span>

    > mono nuget.exe restore

<span data-ttu-id="fbc08-123">다음과 같은 최신 버전으로 모든 패키지 종속 파일을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbc08-123">You can update all your package dependencies to the latest version like this:</span></span>

    > nuget update

<span data-ttu-id="fbc08-124">또는 모노 개발:</span><span class="sxs-lookup"><span data-stu-id="fbc08-124">Or, for Mono development:</span></span>

    > mono nuget.exe update

## <a name="referencing-assemblies"></a><span data-ttu-id="fbc08-125">어셈블리 참조</span><span class="sxs-lookup"><span data-stu-id="fbc08-125">Referencing Assemblies</span></span>

<span data-ttu-id="fbc08-126">F # 스크립트에 패키지를 사용 하기 위해 사용 하 여 패키지에 포함 된 어셈블리를 참조 해야는 `#r` 지시문입니다.</span><span class="sxs-lookup"><span data-stu-id="fbc08-126">In order to use your packages in your F# script, you need to reference the assemblies included in the packages using a `#r` directive.</span></span> <span data-ttu-id="fbc08-127">예:</span><span class="sxs-lookup"><span data-stu-id="fbc08-127">For example:</span></span>

    > #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"

<span data-ttu-id="fbc08-128">볼 수 있듯이 DLL과 하지 않을 수 있는 정확 하 게 패키지 이름과 전체 DLL 이름에 상대 경로를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbc08-128">As you can see, you'll need to specify the relative path to the DLL and the full DLL name, which may not be exactly the same as the package name.</span></span> <span data-ttu-id="fbc08-129">경로 프레임 워크 버전 및 패키지 버전 번호가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbc08-129">The path will include a framework version and possibly a package version number.</span></span> <span data-ttu-id="fbc08-130">설치 된 모든 어셈블리를 찾으려면 Windows 명령줄에서 다음과 같이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbc08-130">To find all the installed assemblies, you can use something like this on a Windows command line:</span></span>

    > cd packages/WindowsAzure.Storage
    > dir /s/b *.dll

<span data-ttu-id="fbc08-131">또는 Unix 셸에서 다음과 같은이:</span><span class="sxs-lookup"><span data-stu-id="fbc08-131">Or in a Unix shell, something like this:</span></span>

    > find packages/WindowsAzure.Storage -name "*.dll"

<span data-ttu-id="fbc08-132">이렇게 하면 경로는 설치 된 어셈블리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbc08-132">This will give you the paths to the installed assemblies.</span></span> <span data-ttu-id="fbc08-133">여기에서 프레임 워크 버전에 대 한 올바른 경로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbc08-133">From there, you can select the correct path for your framework version.</span></span>
