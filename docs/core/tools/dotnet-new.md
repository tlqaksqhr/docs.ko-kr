---
title: "dotnet new 명령 - .NET Core CLI"
description: "dotnet new 명령은 지정된 템플릿을 기반으로 새 .NET Core 프로젝트를 만듭니다."
keywords: "dotnet-new, CLI, CLI 명령, .NET Core"
author: mairaw
ms.author: mairaw
ms.date: 08/13/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: fcc3ed2e-9265-4d50-b59e-dc2e5c190b34
ms.workload: dotnetcore
ms.openlocfilehash: f5815e1ad2a36a8ef3279f6ff83465dba9ec5d50
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-new"></a><span data-ttu-id="909c1-104">dotnet new</span><span class="sxs-lookup"><span data-stu-id="909c1-104">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="909c1-105">name</span><span class="sxs-lookup"><span data-stu-id="909c1-105">Name</span></span>

<span data-ttu-id="909c1-106">`dotnet new` - 지정된 템플릿을 기반으로 새 프로젝트, 구성 파일 또는 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="909c1-107">개요</span><span class="sxs-lookup"><span data-stu-id="909c1-107">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="909c1-108">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="909c1-108">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="909c1-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="909c1-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="909c1-110">설명</span><span class="sxs-lookup"><span data-stu-id="909c1-110">Description</span></span>

<span data-ttu-id="909c1-111">`dotnet new` 명령은 유효한 .NET Core 프로젝트를 초기화하는 편리한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span> 

<span data-ttu-id="909c1-112">이 명령은 [템플릿 엔진](https://github.com/dotnet/templating)을 호출하여 지정된 템플릿 및 옵션을 기반으로 디스크에 아티팩트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="909c1-113">인수</span><span class="sxs-lookup"><span data-stu-id="909c1-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="909c1-114">명령이 호출될 때 인스턴스화할 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="909c1-115">각 템플릿에는 전달할 수 있는 특정 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="909c1-116">자세한 내용은 [템플릿 옵션](#template-options)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="909c1-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="909c1-117">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="909c1-117">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="909c1-118">명령에는 템플릿의 기본 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-118">The command contains a default list of templates.</span></span> <span data-ttu-id="909c1-119">`dotnet new -l`을 사용하여 사용 가능한 템플릿 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="909c1-120">다음 표에는 .NET Core 2.0 SDK와 함께 사전 설치된 템플릿이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-120">The following table shows the templates that come pre-installed with the .NET Core 2.0 SDK.</span></span> <span data-ttu-id="909c1-121">템플릿의 기본 언어는 대괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="909c1-122">템플릿 설명</span><span class="sxs-lookup"><span data-stu-id="909c1-122">Template description</span></span>                          | <span data-ttu-id="909c1-123">템플릿 이름</span><span class="sxs-lookup"><span data-stu-id="909c1-123">Template name</span></span>  | <span data-ttu-id="909c1-124">언어</span><span class="sxs-lookup"><span data-stu-id="909c1-124">Languages</span></span>     |
|----------------------------------------------|----------------|---------------|
| <span data-ttu-id="909c1-125">콘솔 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="909c1-125">Console application</span></span>                          | <span data-ttu-id="909c1-126">콘솔</span><span class="sxs-lookup"><span data-stu-id="909c1-126">console</span></span>        | <span data-ttu-id="909c1-127">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="909c1-127">[C#], F#, VB</span></span>  |
| <span data-ttu-id="909c1-128">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="909c1-128">Class library</span></span>                                | <span data-ttu-id="909c1-129">classlib</span><span class="sxs-lookup"><span data-stu-id="909c1-129">classlib</span></span>       | <span data-ttu-id="909c1-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="909c1-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="909c1-131">단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="909c1-131">Unit test project</span></span>                            | <span data-ttu-id="909c1-132">mstest</span><span class="sxs-lookup"><span data-stu-id="909c1-132">mstest</span></span>         | <span data-ttu-id="909c1-133">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="909c1-133">[C#], F#, VB</span></span>  |
| <span data-ttu-id="909c1-134">xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="909c1-134">xUnit test project</span></span>                           | <span data-ttu-id="909c1-135">xunit</span><span class="sxs-lookup"><span data-stu-id="909c1-135">xunit</span></span>          | <span data-ttu-id="909c1-136">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="909c1-136">[C#], F#, VB</span></span>  |
| <span data-ttu-id="909c1-137">ASP.NET Core 비어 있음</span><span class="sxs-lookup"><span data-stu-id="909c1-137">ASP.NET Core empty</span></span>                           | <span data-ttu-id="909c1-138">웹</span><span class="sxs-lookup"><span data-stu-id="909c1-138">web</span></span>            | <span data-ttu-id="909c1-139">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="909c1-139">[C#], F#</span></span>      |
| <span data-ttu-id="909c1-140">ASP.NET Core 웹앱(모델-뷰-컨트롤러)</span><span class="sxs-lookup"><span data-stu-id="909c1-140">ASP.NET Core Web App (Model-View-Controller)</span></span> | <span data-ttu-id="909c1-141">mvc</span><span class="sxs-lookup"><span data-stu-id="909c1-141">mvc</span></span>            | <span data-ttu-id="909c1-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="909c1-142">[C#], F#</span></span>      |
| <span data-ttu-id="909c1-143">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="909c1-143">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="909c1-144">razor</span><span class="sxs-lookup"><span data-stu-id="909c1-144">razor</span></span>          | <span data-ttu-id="909c1-145">[C#]</span><span class="sxs-lookup"><span data-stu-id="909c1-145">[C#]</span></span>          |
| <span data-ttu-id="909c1-146">ASP.NET Core(Angular 사용)</span><span class="sxs-lookup"><span data-stu-id="909c1-146">ASP.NET Core with Angular</span></span>                    | <span data-ttu-id="909c1-147">angular</span><span class="sxs-lookup"><span data-stu-id="909c1-147">angular</span></span>        | <span data-ttu-id="909c1-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="909c1-148">[C#]</span></span>          |
| <span data-ttu-id="909c1-149">ASP.NET Core(React.js 사용)</span><span class="sxs-lookup"><span data-stu-id="909c1-149">ASP.NET Core with React.js</span></span>                   | <span data-ttu-id="909c1-150">react</span><span class="sxs-lookup"><span data-stu-id="909c1-150">react</span></span>          | <span data-ttu-id="909c1-151">[C#]</span><span class="sxs-lookup"><span data-stu-id="909c1-151">[C#]</span></span>          |
| <span data-ttu-id="909c1-152">ASP.NET Core(React.js 및 Redux 사용)</span><span class="sxs-lookup"><span data-stu-id="909c1-152">ASP.NET Core with React.js and Redux</span></span>         | <span data-ttu-id="909c1-153">reactredux</span><span class="sxs-lookup"><span data-stu-id="909c1-153">reactredux</span></span>     | <span data-ttu-id="909c1-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="909c1-154">[C#]</span></span>          |
| <span data-ttu-id="909c1-155">ASP.NET Core 웹 API</span><span class="sxs-lookup"><span data-stu-id="909c1-155">ASP.NET Core Web API</span></span>                         | <span data-ttu-id="909c1-156">webapi</span><span class="sxs-lookup"><span data-stu-id="909c1-156">webapi</span></span>         | <span data-ttu-id="909c1-157">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="909c1-157">[C#], F#</span></span>      |
| <span data-ttu-id="909c1-158">global.json 파일</span><span class="sxs-lookup"><span data-stu-id="909c1-158">global.json file</span></span>                             | <span data-ttu-id="909c1-159">globaljson</span><span class="sxs-lookup"><span data-stu-id="909c1-159">globaljson</span></span>     |               |
| <span data-ttu-id="909c1-160">Nuget 구성</span><span class="sxs-lookup"><span data-stu-id="909c1-160">Nuget config</span></span>                                 | <span data-ttu-id="909c1-161">nugetconfig</span><span class="sxs-lookup"><span data-stu-id="909c1-161">nugetconfig</span></span>    |               |
| <span data-ttu-id="909c1-162">웹 구성</span><span class="sxs-lookup"><span data-stu-id="909c1-162">Web config</span></span>                                   | <span data-ttu-id="909c1-163">webconfig</span><span class="sxs-lookup"><span data-stu-id="909c1-163">webconfig</span></span>      |               |
| <span data-ttu-id="909c1-164">솔루션 파일</span><span class="sxs-lookup"><span data-stu-id="909c1-164">Solution file</span></span>                                | <span data-ttu-id="909c1-165">sln</span><span class="sxs-lookup"><span data-stu-id="909c1-165">sln</span></span>            |               |
| <span data-ttu-id="909c1-166">Razor 페이지</span><span class="sxs-lookup"><span data-stu-id="909c1-166">Razor page</span></span>                                   | <span data-ttu-id="909c1-167">페이지</span><span class="sxs-lookup"><span data-stu-id="909c1-167">page</span></span>           |               |
| <span data-ttu-id="909c1-168">MVC/ViewImports</span><span class="sxs-lookup"><span data-stu-id="909c1-168">MVC/ViewImports</span></span>                              | <span data-ttu-id="909c1-169">viewimports</span><span class="sxs-lookup"><span data-stu-id="909c1-169">viewimports</span></span>    |               |
| <span data-ttu-id="909c1-170">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="909c1-170">MVC ViewStart</span></span>                                | <span data-ttu-id="909c1-171">viewstart</span><span class="sxs-lookup"><span data-stu-id="909c1-171">viewstart</span></span>      |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="909c1-172">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="909c1-172">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="909c1-173">명령에는 템플릿의 기본 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-173">The command contains a default list of templates.</span></span> <span data-ttu-id="909c1-174">`dotnet new -all`을 사용하여 사용 가능한 템플릿 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-174">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="909c1-175">다음 표에는 .NET Core 1.x SDK와 함께 사전 설치된 템플릿이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-175">The following table shows the templates that come pre-installed with the .NET Core 1.x SDK.</span></span> <span data-ttu-id="909c1-176">템플릿의 기본 언어는 대괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-176">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="909c1-177">템플릿 설명</span><span class="sxs-lookup"><span data-stu-id="909c1-177">Template description</span></span>  | <span data-ttu-id="909c1-178">템플릿 이름</span><span class="sxs-lookup"><span data-stu-id="909c1-178">Template name</span></span>  | <span data-ttu-id="909c1-179">언어</span><span class="sxs-lookup"><span data-stu-id="909c1-179">Languages</span></span> |
|----------------------|----------------|-----------|
| <span data-ttu-id="909c1-180">콘솔 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="909c1-180">Console application</span></span>  | <span data-ttu-id="909c1-181">콘솔</span><span class="sxs-lookup"><span data-stu-id="909c1-181">console</span></span>        | <span data-ttu-id="909c1-182">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="909c1-182">[C#], F#</span></span>  |
| <span data-ttu-id="909c1-183">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="909c1-183">Class library</span></span>        | <span data-ttu-id="909c1-184">classlib</span><span class="sxs-lookup"><span data-stu-id="909c1-184">classlib</span></span>       | <span data-ttu-id="909c1-185">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="909c1-185">[C#], F#</span></span>  |
| <span data-ttu-id="909c1-186">단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="909c1-186">Unit test project</span></span>    | <span data-ttu-id="909c1-187">mstest</span><span class="sxs-lookup"><span data-stu-id="909c1-187">mstest</span></span>         | <span data-ttu-id="909c1-188">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="909c1-188">[C#], F#</span></span>  |
| <span data-ttu-id="909c1-189">xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="909c1-189">xUnit test project</span></span>   | <span data-ttu-id="909c1-190">xunit</span><span class="sxs-lookup"><span data-stu-id="909c1-190">xunit</span></span>          | <span data-ttu-id="909c1-191">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="909c1-191">[C#], F#</span></span>  |
| <span data-ttu-id="909c1-192">ASP.NET Core 비어 있음</span><span class="sxs-lookup"><span data-stu-id="909c1-192">ASP.NET Core empty</span></span>   | <span data-ttu-id="909c1-193">웹</span><span class="sxs-lookup"><span data-stu-id="909c1-193">web</span></span>            | <span data-ttu-id="909c1-194">[C#]</span><span class="sxs-lookup"><span data-stu-id="909c1-194">[C#]</span></span>      |
| <span data-ttu-id="909c1-195">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="909c1-195">ASP.NET Core Web App</span></span> | <span data-ttu-id="909c1-196">mvc</span><span class="sxs-lookup"><span data-stu-id="909c1-196">mvc</span></span>            | <span data-ttu-id="909c1-197">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="909c1-197">[C#], F#</span></span>  |
| <span data-ttu-id="909c1-198">ASP.NET Core 웹 API</span><span class="sxs-lookup"><span data-stu-id="909c1-198">ASP.NET Core Web API</span></span> | <span data-ttu-id="909c1-199">webapi</span><span class="sxs-lookup"><span data-stu-id="909c1-199">webapi</span></span>         | <span data-ttu-id="909c1-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="909c1-200">[C#]</span></span>      |
| <span data-ttu-id="909c1-201">Nuget 구성</span><span class="sxs-lookup"><span data-stu-id="909c1-201">Nuget config</span></span>         | <span data-ttu-id="909c1-202">nugetconfig</span><span class="sxs-lookup"><span data-stu-id="909c1-202">nugetconfig</span></span>    |           |
| <span data-ttu-id="909c1-203">웹 구성</span><span class="sxs-lookup"><span data-stu-id="909c1-203">Web config</span></span>           | <span data-ttu-id="909c1-204">webconfig</span><span class="sxs-lookup"><span data-stu-id="909c1-204">webconfig</span></span>      |           |
| <span data-ttu-id="909c1-205">솔루션 파일</span><span class="sxs-lookup"><span data-stu-id="909c1-205">Solution file</span></span>        | <span data-ttu-id="909c1-206">sln</span><span class="sxs-lookup"><span data-stu-id="909c1-206">sln</span></span>            |           |

---

## <a name="options"></a><span data-ttu-id="909c1-207">옵션</span><span class="sxs-lookup"><span data-stu-id="909c1-207">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="909c1-208">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="909c1-208">.NET Core 2.x</span></span>](#tab/netcore2x)

`--force`

<span data-ttu-id="909c1-209">기존 파일을 변경할 경우에도 콘텐츠를 강제 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-209">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="909c1-210">출력 디렉터리에 이미 프로젝트가 포함되어 있는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-210">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="909c1-211">명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-211">Prints out help for the command.</span></span> <span data-ttu-id="909c1-212">`dotnet new` 명령 자체 또는 `dotnet new mvc --help` 같은 템플릿에 대해 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-212">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="909c1-213">제공된 `PATH` 또는 `NUGET_ID`에서 소스 또는 템플릿 팩을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-213">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="909c1-214">사용자 지정 템플릿을 만드는 방법에 대한 자세한 내용은 [dotnet new에 대한 사용자 지정 템플릿](custom-templates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="909c1-214">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="909c1-215">지정된 이름을 포함하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-215">Lists templates containing the specified name.</span></span> <span data-ttu-id="909c1-216">`dotnet new` 명령에 대해 호출되는 경우 지정된 디렉터리에서 사용 가능한 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-216">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="909c1-217">예를 들어 디렉터리에 이미 프로젝트가 포함되어 있는 경우 일부 프로젝트 템플릿을 나열하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-217">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="909c1-218">만들 템플릿의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-218">The language of the template to create.</span></span> <span data-ttu-id="909c1-219">허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조).</span><span class="sxs-lookup"><span data-stu-id="909c1-219">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="909c1-220">일부 템플릿의 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-220">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="909c1-221">생성된 출력에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-221">The name for the created output.</span></span> <span data-ttu-id="909c1-222">이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-222">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="909c1-223">생성된 출력을 배치할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-223">Location to place the generated output.</span></span> <span data-ttu-id="909c1-224">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-224">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="909c1-225">사용 가능한 형식에 따라 템플릿을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-225">Filters templates based on available types.</span></span> <span data-ttu-id="909c1-226">미리 정의된 값은 “project”, “item” 또는 “other”입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-226">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="909c1-227">제공된 `PATH` 또는 `NUGET_ID`에서 소스 또는 템플릿 팩을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-227">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="909c1-228">`PATH`를 사용하여 템플릿을 제거하려면 경로를 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-228">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="909c1-229">예를 들어 *C:/Users/\<사용자>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지만 상위 폴더의 *./GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-229">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="909c1-230">마지막의 종료하는 디렉터리 슬래시도 템플릿 경로에 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="909c1-230">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="909c1-231">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="909c1-231">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="909c1-232">`dotnet new` 명령의 컨텍스트에서만 실행되는 경우 특정 유형의 프로젝트에 대한 모든 템플릿을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-232">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="909c1-233">`dotnet new web -all`처럼 특정 템플릿의 컨텍스트에서 실행되는 경우 `-all`은 강제 생성 플래그로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-233">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="909c1-234">출력 디렉터리에 이미 프로젝트가 포함되어 있는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-234">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="909c1-235">명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-235">Prints out help for the command.</span></span> <span data-ttu-id="909c1-236">`dotnet new` 명령 자체 또는 `dotnet new mvc --help` 같은 템플릿에 대해 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-236">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="909c1-237">지정된 이름을 포함하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-237">Lists templates containing the specified name.</span></span> <span data-ttu-id="909c1-238">`dotnet new` 명령에 대해 호출되는 경우 지정된 디렉터리에서 사용 가능한 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-238">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="909c1-239">예를 들어 디렉터리에 이미 프로젝트가 포함되어 있는 경우 일부 프로젝트 템플릿을 나열하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-239">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="909c1-240">만들 템플릿의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-240">The language of the template to create.</span></span> <span data-ttu-id="909c1-241">허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조).</span><span class="sxs-lookup"><span data-stu-id="909c1-241">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="909c1-242">일부 템플릿의 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-242">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="909c1-243">생성된 출력에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-243">The name for the created output.</span></span> <span data-ttu-id="909c1-244">이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-244">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="909c1-245">생성된 출력을 배치할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-245">Location to place the generated output.</span></span> <span data-ttu-id="909c1-246">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-246">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="909c1-247">템플릿 옵션</span><span class="sxs-lookup"><span data-stu-id="909c1-247">Template options</span></span>

<span data-ttu-id="909c1-248">각 프로젝트 템플릿에는 사용할 수 있는 추가 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-248">Each project template may have additional options available.</span></span> <span data-ttu-id="909c1-249">코어 템플릿에는 다음과 같은 추가 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-249">The core templates have the following additional options:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="909c1-250">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="909c1-250">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="909c1-251">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="909c1-251">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="909c1-252">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-252">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="909c1-253">**classlib**</span><span class="sxs-lookup"><span data-stu-id="909c1-253">**classlib**</span></span>

<span data-ttu-id="909c1-254">`-f|--framework <FRAMEWORK>` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-254">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="909c1-255">값: `netcoreapp2.0`(.NET Core 클래스 라이브러리를 만드는 경우) 또는 `netstandard2.0`(.NET Standard 클래스 라이브러리를 만드는 경우).</span><span class="sxs-lookup"><span data-stu-id="909c1-255">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="909c1-256">기본값은 `netstandard2.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-256">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="909c1-257">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-257">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="909c1-258">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="909c1-258">**mstest, xunit**</span></span>

<span data-ttu-id="909c1-259">`-p|--enable-pack` - [dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-259">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="909c1-260">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-260">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="909c1-261">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="909c1-261">**globaljson**</span></span>

<span data-ttu-id="909c1-262">`--sdk-version <VERSION_NUMBER>` - *global.json* 파일에서 사용할 .NET Core SDK 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-262">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="909c1-263">**web**</span><span class="sxs-lookup"><span data-stu-id="909c1-263">**web**</span></span>

<span data-ttu-id="909c1-264">`--use-launch-settings` - 생성된 템플릿 출력에 *launchSettings.json*을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-264">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="909c1-265">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-265">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="909c1-266">**webapi**</span><span class="sxs-lookup"><span data-stu-id="909c1-266">**webapi**</span></span>

<span data-ttu-id="909c1-267">`-au|--auth <AUTHENTICATION_TYPE>` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-267">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="909c1-268">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-268">The possible values are:</span></span>

- <span data-ttu-id="909c1-269">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="909c1-269">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="909c1-270">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-270">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="909c1-271">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-271">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="909c1-272">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-272">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="909c1-273">`--aad-b2c-instance <INSTANCE>` - 연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-273">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="909c1-274">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-274">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="909c1-275">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-275">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="909c1-276">`-ssp|--susi-policy-id <ID>` - 이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-276">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="909c1-277">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-277">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="909c1-278">`--aad-instance <INSTANCE>` - 연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-278">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="909c1-279">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-279">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="909c1-280">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-280">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="909c1-281">`--client-id <ID>` - 이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-281">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="909c1-282">`IndividualB2C` 또는 `SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-282">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="909c1-283">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-283">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="909c1-284">`--domain <DOMAIN>` - 디렉터리 테넌트에 대한 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-284">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="909c1-285">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-285">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="909c1-286">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-286">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="909c1-287">`--tenant-id <ID>` - 연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-287">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="909c1-288">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-288">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="909c1-289">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-289">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="909c1-290">`-r|--org-read-access` - 디렉터리에 대한 이 응용 프로그램 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-290">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="909c1-291">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-291">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="909c1-292">`--use-launch-settings` - 생성된 템플릿 출력에 *launchSettings.json*을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-292">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="909c1-293">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-293">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="909c1-294">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-294">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="909c1-295">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-295">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="909c1-296">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="909c1-296">**mvc, razor**</span></span>

<span data-ttu-id="909c1-297">`-au|--auth <AUTHENTICATION_TYPE>` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-297">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="909c1-298">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-298">The possible values are:</span></span>

- <span data-ttu-id="909c1-299">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="909c1-299">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="909c1-300">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-300">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="909c1-301">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-301">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="909c1-302">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-302">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="909c1-303">`MultiOrg` - 여러 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-303">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="909c1-304">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-304">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="909c1-305">`--aad-b2c-instance <INSTANCE>` - 연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-305">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="909c1-306">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-306">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="909c1-307">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-307">The default value is `https://login.microsoftonline.com/tfp/` .</span></span>

<span data-ttu-id="909c1-308">`-ssp|--susi-policy-id <ID>` - 이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-308">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="909c1-309">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-309">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="909c1-310">`-rp|--reset-password-policy-id <ID>` - 이 프로젝트에 대한 암호 재설정 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-310">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="909c1-311">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-311">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="909c1-312">`-ep|--edit-profile-policy-id <ID>` - 이 프로젝트에 대한 프로필 편집 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-312">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="909c1-313">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-313">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="909c1-314">`--aad-instance <INSTANCE>` - 연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-314">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="909c1-315">`SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-315">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="909c1-316">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-316">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="909c1-317">`--client-id <ID>` - 이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-317">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="909c1-318">`IndividualB2C`, `SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-318">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="909c1-319">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-319">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="909c1-320">`--domain <DOMAIN>` - 디렉터리 테넌트에 대한 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-320">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="909c1-321">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-321">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="909c1-322">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-322">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="909c1-323">`--tenant-id <ID>` - 연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-323">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="909c1-324">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-324">Use with `SingleOrg` authentication..</span></span> <span data-ttu-id="909c1-325">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-325">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="909c1-326">`--callback-path <PATH>` - 리디렉션 URI의 응용 프로그램 기본 경로 내 요청 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-326">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="909c1-327">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-327">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="909c1-328">기본값은 `/signin-oidc`입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-328">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="909c1-329">`-r|--org-read-access` - 디렉터리에 대한 이 응용 프로그램 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-329">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="909c1-330">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-330">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="909c1-331">`--use-launch-settings` - 생성된 템플릿 출력에 *launchSettings.json*을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-331">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="909c1-332">`--use-browserlink` - 프로젝트에 BrowserLink를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-332">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="909c1-333">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-333">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="909c1-334">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-334">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="909c1-335">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-335">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="909c1-336">**page**</span><span class="sxs-lookup"><span data-stu-id="909c1-336">**page**</span></span>

<span data-ttu-id="909c1-337">`-na|--namespace <NAMESPACE_NAME>` - 생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-337">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="909c1-338">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-338">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="909c1-339">`-np|--no-pagemodel` - PageModel 없이 페이지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-339">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="909c1-340">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="909c1-340">**viewimports**</span></span>

<span data-ttu-id="909c1-341">`-na|--namespace <NAMESPACE_NAME>` - 생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-341">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="909c1-342">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-342">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="909c1-343">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="909c1-343">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="909c1-344">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="909c1-344">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="909c1-345">`-f|--framework` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-345">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="909c1-346">값: `netcoreapp1.0` 또는 `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="909c1-346">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="909c1-347">기본값은 `netcoreapp1.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-347">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="909c1-348">**classlib**</span><span class="sxs-lookup"><span data-stu-id="909c1-348">**classlib**</span></span>

<span data-ttu-id="909c1-349">`-f|--framework` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-349">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="909c1-350">값: `netcoreapp1.0`, `netcoreapp1.1` 또는 `netstandard1.0`~`netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="909c1-350">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="909c1-351">기본값은 `netstandard1.4`입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-351">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="909c1-352">**mvc**</span><span class="sxs-lookup"><span data-stu-id="909c1-352">**mvc**</span></span>

<span data-ttu-id="909c1-353">`-f|--framework` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-353">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="909c1-354">값: `netcoreapp1.0` 또는 `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="909c1-354">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="909c1-355">기본값은 `netcoreapp1.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-355">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="909c1-356">`-au|--auth` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-356">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="909c1-357">값: `None` 또는 `Individual`.</span><span class="sxs-lookup"><span data-stu-id="909c1-357">Values: `None` or `Individual`.</span></span> <span data-ttu-id="909c1-358">기본값은 `None`입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-358">The default value is `None`.</span></span>

<span data-ttu-id="909c1-359">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-359">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="909c1-360">값: `true` 또는 `false`.</span><span class="sxs-lookup"><span data-stu-id="909c1-360">Values: `true` or `false`.</span></span> <span data-ttu-id="909c1-361">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-361">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="909c1-362">예제</span><span class="sxs-lookup"><span data-stu-id="909c1-362">Examples</span></span>

<span data-ttu-id="909c1-363">현재 디렉터리에 F# 콘솔 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-363">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang f#`

<span data-ttu-id="909c1-364">지정된 디렉터리에서 .NET Standard 클래스 라이브러리 프로젝트를 만듭니다(.NET Core 2.0 SDK 이상 버전에서만 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="909c1-364">Create a .NET Standard class library project in the specified directory (available only with .NET Core 2.0 SDK or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="909c1-365">.NET Core 2.0을 대상으로 인증 없이 현재 디렉터리에 새 ASP.NET Core C# MVC 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-365">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 2.0:</span></span>

`dotnet new mvc -au None -f netcoreapp2.0`

<span data-ttu-id="909c1-366">.NET Core 2.0을 대상으로 새 xUnit 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-366">Create a new xUnit application targeting .NET Core 2.0:</span></span>

`dotnet new xunit --framework netcoreapp2.0`

<span data-ttu-id="909c1-367">MVC에 대해 사용할 수 있는 모든 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="909c1-367">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

## <a name="see-also"></a><span data-ttu-id="909c1-368">참고 항목</span><span class="sxs-lookup"><span data-stu-id="909c1-368">See also</span></span>

[<span data-ttu-id="909c1-369">dotnet new에 대한 사용자 지정 템플릿</span><span class="sxs-lookup"><span data-stu-id="909c1-369">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="909c1-370">dotnet용 사용자 지정 템플릿 새로 만들기</span><span class="sxs-lookup"><span data-stu-id="909c1-370">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
<span data-ttu-id="909c1-371">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)(dotnet/dotnet-template-samples GitHub 리포지토리)</span><span class="sxs-lookup"><span data-stu-id="909c1-371">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)</span></span>  
<span data-ttu-id="909c1-372">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)(dotnet new에 대한 사용 가능한 템플릿)</span><span class="sxs-lookup"><span data-stu-id="909c1-372">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
