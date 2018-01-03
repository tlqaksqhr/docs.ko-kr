---
title: ".NET Framework에서 .NET Core로 이식"
description: "이식 프로세스를 이해하고 .NET Framework 프로젝트를 .NET Core로 이식할 때 유용한 도구에 관해 알아보세요."
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 00d00d38-99af-44f4-a75f-defcd9729dc5
ms.workload: dotnetcore
ms.openlocfilehash: 3413b73c2a0a3c3ebf49b0b3ec81d00c6558d9a8
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="porting-to-net-core-from-net-framework"></a><span data-ttu-id="24802-104">.NET Framework에서 .NET Core로 이식</span><span class="sxs-lookup"><span data-stu-id="24802-104">Porting to .NET Core from .NET Framework</span></span>

<span data-ttu-id="24802-105">.NET Framework에서 코드를 실행한 적이 있으면 .NET Core 1.0에서 코드를 실행하는 데 관심이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24802-105">If you've got code running on the .NET Framework, you may be interested in running your code on .NET Core 1.0.</span></span>  <span data-ttu-id="24802-106">이 문서에서는 이식 프로세스 및 .NET Core로 이식할 때 유용하게 사용할 수 있는 도구 목록에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="24802-106">This article covers an overview of the porting process and a list of the tools you may find helpful when porting to .NET Core.</span></span>

## <a name="overview-of-the-porting-process"></a><span data-ttu-id="24802-107">이식 프로세스의 개요</span><span class="sxs-lookup"><span data-stu-id="24802-107">Overview of the Porting Process</span></span>

<span data-ttu-id="24802-108">권장되는 이식 프로세스는 다음 단계를 따르는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="24802-108">The recommended process for porting follows the following series of steps.</span></span>  <span data-ttu-id="24802-109">이러한 프로세스의 각 부분은 향후 문서에서 더 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="24802-109">Each of these parts of the process are covered in more detail in further articles.</span></span>

1. <span data-ttu-id="24802-110">타사 종속성을 식별하고 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="24802-110">Identify and account for your third-party dependencies.</span></span>

   <span data-ttu-id="24802-111">여기에서는 타사 종속성의 개념, 종속 방법, .NET Core에서 실행되는지 확인하는 방법 및 실행되지 않을 경우 수행할 수 있는 단계를 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="24802-111">This will involve understanding what your third-party dependencies are, how you depend on them, how to see if they also run on .NET Core, and steps you can take if they don't.</span></span>
   
2. <span data-ttu-id="24802-112">대상 .NET Framework 4.6.2로 이식하려는 모든 프로젝트의 대상을 다시 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="24802-112">Retarget all projects you wish to port to target .NET Framework 4.6.2.</span></span>

   <span data-ttu-id="24802-113">그러면 .NET Core에서 특정 API를 지원할 수 없는 경우 .NET Framework 관련 대상에 API 대안을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24802-113">This ensures that you can use API alternatives for .NET Framework-specific targets in the cases where .NET Core can't support a particular API.</span></span>
   
3. <span data-ttu-id="24802-114">[API Portability Analyzer 도구](https://github.com/Microsoft/dotnet-apiport/)를 사용하여 어셈블리를 분석하고 결과에 따라 이식 계획을 수립합니다.</span><span class="sxs-lookup"><span data-stu-id="24802-114">Use the [API Portability Analyzer tool](https://github.com/Microsoft/dotnet-apiport/) to analyze your assemblies and develop a plan to port based on its results.</span></span>

   <span data-ttu-id="24802-115">API Portability Analyzer 도구는 컴파일된 어셈블리를 분석하고 상위 수준 이식성 요약 및 .NET Core에서 사용할 수 없는 사용 중인 각 API에 대한 분석 결과를 보여 주는 보고서를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="24802-115">The API Portability Analyzer tool will analyze your compiled assemblies and generate a report which shows a high-level portability summary and a breakdown of each API you're using that isn't available on .NET Core.</span></span>  <span data-ttu-id="24802-116">코드베이스에 대한 분석과 함께 이 보고서를 사용하여 코드를 이식할 방법에 대한 계획을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24802-116">You can use this report alongside an analysis of your codebase to develop a plan for how you'll port your code over.</span></span>
   
4. <span data-ttu-id="24802-117">테스트 코드를 이식합니다.</span><span class="sxs-lookup"><span data-stu-id="24802-117">Port your tests code.</span></span>

   <span data-ttu-id="24802-118">.NET Core로 이식하면 코드베이스가 너무 많이 변경되기 때문에 코드를 이식할 때 테스트를 실행할 수 있도록 테스트를 이식하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="24802-118">Because porting to .NET Core is such a big change to your codebase, it's highly recommended to get your tests ported so that you can run tests as you port code over.</span></span>  <span data-ttu-id="24802-119">현재 MSTest, xUnit 및 NUnit 모두 .NET Core 1.0을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="24802-119">MSTest, xUnit, and NUnit all support .NET Core 1.0 today.</span></span>
   
6. <span data-ttu-id="24802-120">이식에 대한 계획을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="24802-120">Execute your plan for porting!</span></span>

## <a name="tools-to-help"></a><span data-ttu-id="24802-121">유용한 도구</span><span class="sxs-lookup"><span data-stu-id="24802-121">Tools to help</span></span>

<span data-ttu-id="24802-122">다음은 유용하게 사용할 수 있는 간단한 도구 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="24802-122">Here's a short list of the tools you'll find helpful:</span></span>

* <span data-ttu-id="24802-123">NuGet - [NuGet 클라이언트](https://dist.nuget.org/index.html) 또는 [NuGet 패키지 탐색기](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer)로, Microsoft의 .NET 구현용 패키지 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="24802-123">NuGet - [Nuget Client](https://dist.nuget.org/index.html) or [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer), Microsoft's package manager for .NET implementations.</span></span>
* <span data-ttu-id="24802-124">Api Portability Analyzer - [명령줄 도구](https://github.com/Microsoft/dotnet-apiport/releases) 또는 [Visual Studio 확장](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b)으로, 문제에 대한 어셈블리 단위 분석 결과를 사용하여 .NET Framework와 .NET Core 간에 코드를 이식할 수 있는 정도에 대한 보고서를 생성할 수 있는 도구 체인입니다.</span><span class="sxs-lookup"><span data-stu-id="24802-124">Api Portability Analyzer - [command line tool](https://github.com/Microsoft/dotnet-apiport/releases) or [Visual Studio Extension](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b), a toolchain that can generate a report of how portable your code is between .NET Framework and .NET Core, with an assembly-by-assembly breakdown of issues.</span></span>  <span data-ttu-id="24802-125">자세한 내용은 [프로세스에 도움이 되는 도구](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24802-125">See [Tooling to help you on the process](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/) for more information.</span></span>
* <span data-ttu-id="24802-126">역방향 패키지 검색 - 형식을 검색하고 해당 형식을 포함하는 패키지를 찾을 수 있는 [유용한 웹 서비스](https://packagesearch.azurewebsites.net)입니다.</span><span class="sxs-lookup"><span data-stu-id="24802-126">Reverse Package Search - A [useful web service](https://packagesearch.azurewebsites.net) that allows you to search for a type and find packages containing that type.</span></span>

## <a name="next-steps"></a><span data-ttu-id="24802-127">다음 단계</span><span class="sxs-lookup"><span data-stu-id="24802-127">Next steps</span></span>

[<span data-ttu-id="24802-128">타사 종속성 분석</span><span class="sxs-lookup"><span data-stu-id="24802-128">Analyzing your third-party dependencies.</span></span>](third-party-deps.md)
   
