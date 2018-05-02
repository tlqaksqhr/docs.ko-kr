---
title: .NET Core 명령줄 도구 아키텍처
description: .NET Core 도구 레이어 및 최신 버전의 변경 내용에 대해 알아봅니다.
author: blackdwarf
ms.date: 03/06/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: 909e3ba088a3eabededf008fa07a51ac7d677fa2
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="high-level-overview-of-changes-in-the-net-core-tools"></a><span data-ttu-id="cb4f8-103">.NET Core 도구의 변경 내용에 대한 대략적인 개요</span><span class="sxs-lookup"><span data-stu-id="cb4f8-103">High-level overview of changes in the .NET Core tools</span></span>

<span data-ttu-id="cb4f8-104">이 문서에서는 .NET Core 도구의 계층화 및 CLI 명령의 구현에 대한 변경 사항 정보와 함께 *project.json*에서 MSBuild 및 *csproj* 프로젝트 시스템으로 이전하는 것과 관련된 변경 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-104">This document describes the changes associated with moving from *project.json* to MSBuild and the *csproj* project system with information on the changes to the layering of the .NET Core tooling and the implementation of the CLI commands.</span></span> <span data-ttu-id="cb4f8-105">이러한 변화는 2017년 3월 7일에 발표된 .NET Core SDK 1.0과 Visual Studio 2017에서 나타났지만([알림](https://blogs.msdn.microsoft.com/dotnet/2017/03/07/announcing-net-core-tools-1-0/) 참조), 처음에는 .NET Core SDK Preview 3 릴리스와 함께 구현되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-105">These changes occurred with the release of .NET Core SDK 1.0 and Visual Studio 2017 on March 7, 2017 (see the [announcement](https://blogs.msdn.microsoft.com/dotnet/2017/03/07/announcing-net-core-tools-1-0/)) but were initially implemented with the release of the .NET Core SDK Preview 3.</span></span>

## <a name="moving-away-from-projectjson"></a><span data-ttu-id="cb4f8-106">project.json로부터의 이동</span><span class="sxs-lookup"><span data-stu-id="cb4f8-106">Moving away from project.json</span></span>
<span data-ttu-id="cb4f8-107">.NET Core용 도구의 가장 큰 변화는 프로젝트 시스템이 [project.json에서 csproj로 전환](https://blogs.msdn.microsoft.com/dotnet/2016/05/23/changes-to-project-json/)되었다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-107">The biggest change in the tooling for .NET Core is certainly the [move away from project.json to csproj](https://blogs.msdn.microsoft.com/dotnet/2016/05/23/changes-to-project-json/) as the project system.</span></span> <span data-ttu-id="cb4f8-108">최신 버전의 명령줄 도구는 *project.json* 파일을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-108">The latest versions of the command-line tools don't support *project.json* files.</span></span> <span data-ttu-id="cb4f8-109">즉, project.json 기반 응용 프로그램 및 라이브러리를 빌드, 실행 또는 게시하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-109">That means that it cannot be used to build, run or publish project.json based applications and libraries.</span></span> <span data-ttu-id="cb4f8-110">이 버전의 도구를 사용하려면 기존 프로젝트를 마이그레이션하거나 새 프로젝트를 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-110">In order to use this version of the tools, you will need to migrate your existing projects or start new ones.</span></span> 

<span data-ttu-id="cb4f8-111">이러한 흐름에 포함되어 project.json 프로젝트를 빌드하기 위해 개발된 사용자 지정 빌드 엔진이 전문적이고 완전한 기능의 빌드 엔진인 [MSBuild](https://github.com/Microsoft/msbuild)로 바뀌었습니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-111">As part of this move, the custom build engine that was developed to build project.json projects was replaced with a mature and fully capable build engine called [MSBuild](https://github.com/Microsoft/msbuild).</span></span> <span data-ttu-id="cb4f8-112">MSBuild는.NET 커뮤니티에서 잘 알려진 엔진으로 플랫폼의 첫 번째 릴리스 이후 핵심 기술로 부상하였습니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-112">MSBuild is a well-known engine in the .NET community, since it has been a key technology since the platform's first release.</span></span> <span data-ttu-id="cb4f8-113">물론 .NET Core 응용 프로그램을 구축해야 하므로 MSBuild는 .NET Core로 이식되었으며, .NET Core에서 실행하는 모든 플랫폼에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-113">Of course, because it needs to build .NET Core applications, MSBuild has been ported to .NET Core and can be used on any platform that .NET Core runs on.</span></span> <span data-ttu-id="cb4f8-114">.NET Core의 주요 기능 중 하나는 플랫폼 간 개발 스택에 대한 것으로 이 이동으로 인해 이 기능이 없어지진 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-114">One of the main promises of .NET Core is that of a cross-platform development stack, and we have made sure that this move does not break that promise.</span></span>

> [!NOTE]
> <span data-ttu-id="cb4f8-115">처음 MSBuild를 사용하는 경우 자세한 내용을 보려면 [MSBuild 개념](/visualstudio/msbuild/msbuild-concepts) 문서를 읽어 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-115">If you are new to MSBuild and would like to learn more about it, you can start by reading the [MSBuild Concepts](/visualstudio/msbuild/msbuild-concepts) article.</span></span> 

## <a name="the-tooling-layers"></a><span data-ttu-id="cb4f8-116">도구 레이어</span><span class="sxs-lookup"><span data-stu-id="cb4f8-116">The tooling layers</span></span>
<span data-ttu-id="cb4f8-117">기존 프로젝트 시스템으로부터의 이동과 빌드 엔진 전환에 따라 이러한 변화로 인해 전체 .NET Core 도구 에코 시스템의 전반적인 "계층"에도 변화가 있는지 자연스럽게 질문이 나오게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-117">With the move away from the existing project system as well as with building engine switches, the question that naturally follows is do any of these changes change the overall "layering" of the whole .NET Core tooling ecosystem?</span></span> <span data-ttu-id="cb4f8-118">새로운 비트 및 구성 요소가 있을까요?</span><span class="sxs-lookup"><span data-stu-id="cb4f8-118">Are there new bits and components?</span></span>

<span data-ttu-id="cb4f8-119">다음 그림에 나와 있는 것처럼 이전에 알고 있는 Preview 2 계층을 빠르게 환기시켜보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-119">Let's start with a quick refresher on Preview 2 layering as shown in the following picture:</span></span>

![Preview 2 도구에 대한 상위 수준 아키텍처](media/cli-msbuild-architecture/p2-arch.png)

<span data-ttu-id="cb4f8-121">도구 계층은 매우 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-121">The layering of the tools is quite simple.</span></span> <span data-ttu-id="cb4f8-122">맨 아래 기본으로 .NET Core 명령줄 도구가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-122">At the bottom we have the .NET Core Command Line tools as a foundation.</span></span> <span data-ttu-id="cb4f8-123">Visual Studio 또는 Visual Studio Code와 같은 높은 수준의 다른 도구는 모두 프로젝트 빌드와 종속성 복원을 위해 CLI를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-123">All other, higher-level tools such as Visual Studio or Visual Studio Code, depend and rely on the CLI to build projects, restore dependencies and so on.</span></span> <span data-ttu-id="cb4f8-124">다시 말하면 예를 들어 Visual Studio에서 복원 작업을 수행하려면 CLI에서 `dotnet restore`([참고 참조](#dotnet-restore-note)) 명령을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-124">This meant that, for example, if Visual Studio wanted to perform a restore operation, it would call into `dotnet restore` ([see note](#dotnet-restore-note)) command in the CLI.</span></span> 

<span data-ttu-id="cb4f8-125">새 프로젝트 시스템으로의 이전으로 이전 다이어그램이 다음과 같이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-125">With the move to the new project system, the previous diagram changes:</span></span> 

![.NET Core SDK 1.0.0 상위 아키텍처](media/cli-msbuild-architecture/p3-arch.png)

<span data-ttu-id="cb4f8-127">주요 차이점은 CLI가 더 이상 기본 계층이 아니라는 점입니다. 이 역할은 이제 "공유된 SDK 구성 요소"에 의해 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-127">The main difference is that the CLI is not the foundational layer anymore; this role is now filled by the "shared SDK component".</span></span> <span data-ttu-id="cb4f8-128">이 공유된 SDK 구성 요소는 코드 컴파일, 게시, NuGet 패키지 압축 등을 담당하는 대상 및 관련 작업 집합입니다. SDK 자체는 오픈 소스이며 [SDK 리포지토리](https://github.com/dotnet/sdk)의 GitHub에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-128">This shared SDK component is a set of targets and associated tasks that are responsible for compiling your code, publishing it, packing NuGet packages etc. The SDK itself is open-source and is available on GitHub on the [SDK repo](https://github.com/dotnet/sdk).</span></span> 

> [!NOTE]
> <span data-ttu-id="cb4f8-129">"대상"은 MSBuild에서 호출할 수 있는 명명된 작업을 나타내는 MSBuild 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-129">A "target" is a MSBuild term that indicates a named operation that MSBuild can invoke.</span></span> <span data-ttu-id="cb4f8-130">일반적으로 대상에서 구현되는 로직을 실행하는 하나 이상의 작업과 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-130">It is usually coupled with one or more tasks that execute some logic that the target is supposed to do.</span></span> <span data-ttu-id="cb4f8-131">MSBuild는 `Copy` 또는 `Execute`와 같이 바로 사용할 수 있는 많은 대상을 지원합니다. 또한 이를 통해 사용자는 관리되는 코드를 사용하여 고유한 작업을 기록하고 대상을 정의하여 이러한 작업을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-131">MSBuild supports many ready-made targets such as `Copy` or `Execute`; it also allows users to write their own tasks using managed code and define targets to execute those tasks.</span></span> <span data-ttu-id="cb4f8-132">자세한 내용은 [MSBuild 작업](/visualstudio/msbuild/msbuild-tasks)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-132">For more information, see [MSBuild tasks](/visualstudio/msbuild/msbuild-tasks).</span></span> 

<span data-ttu-id="cb4f8-133">이제 모든 도구 집합은 CLI를 비롯하여 공유된 SDK 구성 요소와 대상을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-133">All the toolsets now consume the shared SDK component and its targets, CLI included.</span></span> <span data-ttu-id="cb4f8-134">예를 들어 Visual Studio의 다음 버전에서 .NET Core 프로젝트용 종속성 복원을 위해 `dotnet restore`([참고 참조](#dotnet-restore-note)) 명령을 호출하지 않는다면, 직접 “복원” 대상을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-134">For example, the next version of Visual Studio will not call into `dotnet restore` ([see note](#dotnet-restore-note)) command to restore dependencies for .NET Core projects, it will use the "Restore" target directly.</span></span> <span data-ttu-id="cb4f8-135">이는 MSBuild 대상이므로, 원시 MSBuild를 사용하여 [dotnet msbuild](dotnet-msbuild.md) 명령을 통해 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-135">Since these are MSBuild targets, you can also use raw MSBuild to execute them using the [dotnet msbuild](dotnet-msbuild.md) command.</span></span> 

### <a name="cli-commands"></a><span data-ttu-id="cb4f8-136">CLI 명령</span><span class="sxs-lookup"><span data-stu-id="cb4f8-136">CLI commands</span></span>
<span data-ttu-id="cb4f8-137">공유된 SDK 구성 요소는 대부분의 기존 CLI 명령들이 MSBuild 작업 및 대상으로 다시 구현되었음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-137">The shared SDK component means that the majority of existing CLI commands have been re-implemented as MSBuild tasks and targets.</span></span> <span data-ttu-id="cb4f8-138">CLI 명령 및 도구 집합의 경우 어떤 의미가 있을까요?</span><span class="sxs-lookup"><span data-stu-id="cb4f8-138">What does this mean for the CLI commands and your usage of the toolset?</span></span> 

<span data-ttu-id="cb4f8-139">사용 관점으로 보면 CLI를 사용하는 방식은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-139">From an usage perspective, it doesn't change the way you use the CLI.</span></span> <span data-ttu-id="cb4f8-140">CLI에는 Preview 2 릴리스에 있는 핵심 명령이 아직 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-140">The CLI still has the core commands that exist in Preview 2 release:</span></span>

* `new`
* `restore`
* `run` 
* `build`
* `publish`
* `test`
* `pack` 

<span data-ttu-id="cb4f8-141">이러한 명령은 여전히 사용자가 예상하는 대로 수행됩니다(프로젝트 새로 구동, 빌드, 게시, 압축 등).</span><span class="sxs-lookup"><span data-stu-id="cb4f8-141">These commands still do what you expect them to do (new up a project, build it, publish it, pack it and so on).</span></span> <span data-ttu-id="cb4f8-142">대부분의 옵션은 변경되지 않고 그대로 있습니다. 이 사이트의 설명서 또는 명령의 도움말 화면(`dotnet <command> --help` 사용)을 참조하여 변경 내용을 살펴볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-142">Majority of the options are not changed, and are still there, and you can consult either the commands' help screens (using `dotnet <command> --help`) or documentation on this site to get familiar with any changes.</span></span> 

<span data-ttu-id="cb4f8-143">실행 관점에서 CLI 명령은 매개 변수를 사용하고 "원시" MSBuild에 대한 호출을 생성하여 필요한 속성을 설정하고 원하는 대상을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-143">From an execution perspective, the CLI commands will take their parameters and construct a call to "raw" MSBuild that will set the needed properties and run the desired target.</span></span> <span data-ttu-id="cb4f8-144">이해를 돕기 위해 다음 명령을 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-144">To better illustrate this, consider the following command:</span></span> 

   `dotnet publish -o pub -c Release`
    
<span data-ttu-id="cb4f8-145">이 명령은 "릴리스" 구성을 사용하여 응용 프로그램을 `pub` 폴더에 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-145">This command is publishing an application into a `pub` folder using the "Release" configuration.</span></span> <span data-ttu-id="cb4f8-146">내부적으로 이 명령은 다음과 같은 MSBuild 호출로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-146">Internally, this command gets translated into the following MSBuild invocation:</span></span> 

   `dotnet msbuild /t:Publish /p:OutputPath=pub /p:Configuration=Release`

<span data-ttu-id="cb4f8-147">이 규칙에서 주목할 만한 예외는 `new` 및 `run` 명령으로 MSBuild 대상으로 구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="cb4f8-147">The notable exception to this rule are `new` and `run` commands, as they have not been implemented as MSBuild targets.</span></span>

<a name="dotnet-restore-note"></a> <span data-ttu-id="cb4f8-148">[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]</span><span class="sxs-lookup"><span data-stu-id="cb4f8-148">[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]</span></span>