---
title: Roslyn 기반 분석기 - .NET
description: 문제를 찾고 해당 문제에 대한 수정 사항을 제안하는 Roslyn 기반 분석기에 대해 알아봅니다.
author: billwagner
ms.author: billwagner
ms.date: 01/24/2018
ms.technology: dotnet-standard
ms.openlocfilehash: ec153b8fed08ef245a3a0f58970b4e3955dfacb5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="the-roslyn-based-analyzers"></a><span data-ttu-id="95dd4-103">Roslyn 기반 분석기</span><span class="sxs-lookup"><span data-stu-id="95dd4-103">The Roslyn based Analyzers</span></span>

<span data-ttu-id="95dd4-104">Roslyn 기반 분석기는 .NET Compiler SDK(Roslyn API)를 사용해 프로젝트의 소스 코드를 분석하여 문제를 찾고 수정을 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="95dd4-104">Roslyn-based analyzers use the .NET Compiler SDK (Roslyn APIs) to analyze your project's source code to find issues and suggest corrections.</span></span> <span data-ttu-id="95dd4-105">분석기에 따라 버그를 일으킬 수 있는 사례에서 보안 문제, API 호환성 등에 이르는 다양한 종류의 문제를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="95dd4-105">Different analyzers look for different classes of issues, ranging from practices that are likely to cause bugs to security concerns to API compatibility.</span></span>

<span data-ttu-id="95dd4-106">Roslyn 기반 분석기는 대화식으로도 사용할 수 있고 빌드 중에도 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="95dd4-106">Roslyn-based analyzers work both interactively and during builds.</span></span> <span data-ttu-id="95dd4-107">Visual Studio를 사용할 때나 명령줄 빌드 중에 서로 다른 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="95dd4-107">The analyzer provides different guidance when in Visual Studio or in command-line builds.</span></span>

<span data-ttu-id="95dd4-108">Visual Studio에서 코드를 편집하는 동안에는 변경 작업을 하면 분석기가 실행되어 문제를 트리거하는 코드를 작성하는 즉시 발생할 수 있는 문제를 포착합니다.</span><span class="sxs-lookup"><span data-stu-id="95dd4-108">While you edit code in Visual Studio, the analyzers run as you make changes, catching possible issues as soon as you create code that trigger concerns.</span></span> <span data-ttu-id="95dd4-109">모든 문제는 아래에 물결선을 사용하여 강조 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="95dd4-109">Any issues are highlighted with squiggles under any issue.</span></span> <span data-ttu-id="95dd4-110">Visual Studio에서는 전구를 표시하고 이 전구를 클릭하면 분석기에서 해당 문제에 대한 가능한 수정을 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="95dd4-110">Visual Studio displays a light bulb, and when you click on it the analyzer will suggest possible fixes for that issue.</span></span> <span data-ttu-id="95dd4-111">Visual Studio 또는 명령줄에서 프로젝트를 빌드할 때는 모든 소스 코드가 분석되며 분석기는 잠재적 문제의 전체 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="95dd4-111">When you build the project, either in Visual Studio or from the command line, all the source code is analyzed and the analyzer provides a full list of potential issues.</span></span> <span data-ttu-id="95dd4-112">다음 그림에서는 한 가지 예를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="95dd4-112">The following figure shows one example.</span></span>

![프레임워크 분석기에서 보고한 문제](./media/framework-analyzers-2.png)

<span data-ttu-id="95dd4-114">Roslyn 기반 분석기에서는 잠재적 문제를 문제의 심각도에 따라 오류, 경고 또는 정보로 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="95dd4-114">Roslyn-based analyzers report potential issues as errors, warnings, or information based on the severity of the issue.</span></span>

<span data-ttu-id="95dd4-115">Roslyn 기반 분석기는 프로젝트에서 NuGet 패키지로 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="95dd4-115">You install Roslyn-based analyzers as NuGet packages in your project.</span></span> <span data-ttu-id="95dd4-116">구성된 분석기와 각 분석기의 설정은 모든 개발자의 컴퓨터에서 해당 프로젝트에 대해 복원되고 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="95dd4-116">The configured analyzers and any settings for each analyzer are restored and run on any developer's machine for that project.</span></span>

> [!NOTE]
> <span data-ttu-id="95dd4-117">Roslyn 기반 분석기의 사용자 환경은 이전 버전의 FxCop 및 보안 분석 도구와 같은 코드 분석 라이브러리와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="95dd4-117">The user experience for Roslyn-based analyzers is different than that of the Code Analysis libraries like the older versions of FxCop and the security analysis tools.</span></span>  <span data-ttu-id="95dd4-118">Roslyn 기반 분석기는 명시적으로 실행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95dd4-118">You don't need to explicitly run the Roslyn-based analyzers.</span></span> <span data-ttu-id="95dd4-119">Visual Studio의 “분석” 메뉴에서 “코드 분석 실행” 메뉴 항목을 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95dd4-119">There's no need to use the "Run Code Analysis" menu items on the "Analyze" menu in Visual Studio.</span></span> <span data-ttu-id="95dd4-120">Roslyn 기반 분석기는 작업하는 과정에 비동기적으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="95dd4-120">Roslyn-based analyzers run asychronously as you work.</span></span> 

## <a name="more-information-on-specific-analyzers"></a><span data-ttu-id="95dd4-121">특정 분석기에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="95dd4-121">More information on specific analyzers</span></span>

<span data-ttu-id="95dd4-122">이 섹션에서는 다음과 같은 분석기를 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="95dd4-122">The following analyzers are covered in this section:</span></span>

<span data-ttu-id="95dd4-123">[API 분석기](api-analyzer.md): 이 분석기는 코드에서 잠재적인 호환성 위험이나 더 이상 사용되지 않는 API의 사용이 있는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="95dd4-123">[API Analyzer](api-analyzer.md): This analyzer examines your code for potential compatibility risks or uses of deprecated APIs.</span></span>    
<span data-ttu-id="95dd4-124">[프레임워크 분석기](framework-analyzer.md): 이 분석기는 코드가 .NET Framework 응용 프로그램에 대한 지침을 따르는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="95dd4-124">[Framework Analyzer](framework-analyzer.md): This analyzer examines your code to ensure it follows the guidelines for .NET Framework applications.</span></span> <span data-ttu-id="95dd4-125">이러한 규칙에는 여러 보안 기반 권장 사항이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="95dd4-125">These rules include several security-based recommendations.</span></span>
