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
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: 335902f26148d8201b7311b57370fd37280c68dd
ms.contentlocale: ko-kr
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-new"></a><span data-ttu-id="81b1e-104">dotnet new</span><span class="sxs-lookup"><span data-stu-id="81b1e-104">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="81b1e-105">이름</span><span class="sxs-lookup"><span data-stu-id="81b1e-105">Name</span></span>

<span data-ttu-id="81b1e-106">`dotnet new` - 지정된 템플릿을 기반으로 새 프로젝트, 구성 파일 또는 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="81b1e-107">개요</span><span class="sxs-lookup"><span data-stu-id="81b1e-107">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="81b1e-108">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="81b1e-108">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="81b1e-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="81b1e-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="81b1e-110">설명</span><span class="sxs-lookup"><span data-stu-id="81b1e-110">Description</span></span>

<span data-ttu-id="81b1e-111">`dotnet new` 명령은 유효한 .NET Core 프로젝트를 초기화하는 편리한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span> 

<span data-ttu-id="81b1e-112">이 명령은 [템플릿 엔진](https://github.com/dotnet/templating)을 호출하여 지정된 템플릿 및 옵션을 기반으로 디스크에 아티팩트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="81b1e-113">인수</span><span class="sxs-lookup"><span data-stu-id="81b1e-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="81b1e-114">명령이 호출될 때 인스턴스화할 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="81b1e-115">각 템플릿에는 전달할 수 있는 특정 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="81b1e-116">자세한 내용은 [템플릿 옵션](#template-options)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81b1e-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="81b1e-117">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="81b1e-117">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="81b1e-118">명령에는 템플릿의 기본 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-118">The command contains a default list of templates.</span></span> <span data-ttu-id="81b1e-119">`dotnet new -l`을 사용하여 사용 가능한 템플릿 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="81b1e-120">다음 표에는 .NET Core 2.0 SDK와 함께 사전 설치된 템플릿이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-120">The following table shows the templates that come pre-installed with the .NET Core 2.0 SDK.</span></span> <span data-ttu-id="81b1e-121">템플릿의 기본 언어는 대괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="81b1e-122">템플릿 설명</span><span class="sxs-lookup"><span data-stu-id="81b1e-122">Template description</span></span>                          | <span data-ttu-id="81b1e-123">템플릿 이름</span><span class="sxs-lookup"><span data-stu-id="81b1e-123">Template name</span></span>  | <span data-ttu-id="81b1e-124">언어</span><span class="sxs-lookup"><span data-stu-id="81b1e-124">Languages</span></span>     |
|----------------------------------------------|----------------|---------------|
| <span data-ttu-id="81b1e-125">콘솔 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="81b1e-125">Console application</span></span>                          | <span data-ttu-id="81b1e-126">콘솔</span><span class="sxs-lookup"><span data-stu-id="81b1e-126">console</span></span>        | <span data-ttu-id="81b1e-127">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="81b1e-127">[C#], F#, VB</span></span>  |
| <span data-ttu-id="81b1e-128">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="81b1e-128">Class library</span></span>                                | <span data-ttu-id="81b1e-129">classlib</span><span class="sxs-lookup"><span data-stu-id="81b1e-129">classlib</span></span>       | <span data-ttu-id="81b1e-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="81b1e-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="81b1e-131">단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="81b1e-131">Unit test project</span></span>                            | <span data-ttu-id="81b1e-132">mstest</span><span class="sxs-lookup"><span data-stu-id="81b1e-132">mstest</span></span>         | <span data-ttu-id="81b1e-133">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="81b1e-133">[C#], F#, VB</span></span>  |
| <span data-ttu-id="81b1e-134">xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="81b1e-134">xUnit test project</span></span>                           | <span data-ttu-id="81b1e-135">xunit</span><span class="sxs-lookup"><span data-stu-id="81b1e-135">xunit</span></span>          | <span data-ttu-id="81b1e-136">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="81b1e-136">[C#], F#, VB</span></span>  |
| <span data-ttu-id="81b1e-137">ASP.NET Core 비어 있음</span><span class="sxs-lookup"><span data-stu-id="81b1e-137">ASP.NET Core empty</span></span>                           | <span data-ttu-id="81b1e-138">웹</span><span class="sxs-lookup"><span data-stu-id="81b1e-138">web</span></span>            | <span data-ttu-id="81b1e-139">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="81b1e-139">[C#], F#</span></span>      |
| <span data-ttu-id="81b1e-140">ASP.NET Core 웹앱(모델-뷰-컨트롤러)</span><span class="sxs-lookup"><span data-stu-id="81b1e-140">ASP.NET Core Web App (Model-View-Controller)</span></span> | <span data-ttu-id="81b1e-141">mvc</span><span class="sxs-lookup"><span data-stu-id="81b1e-141">mvc</span></span>            | <span data-ttu-id="81b1e-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="81b1e-142">[C#], F#</span></span>      |
| <span data-ttu-id="81b1e-143">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="81b1e-143">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="81b1e-144">razor</span><span class="sxs-lookup"><span data-stu-id="81b1e-144">razor</span></span>          | <span data-ttu-id="81b1e-145">[C#]</span><span class="sxs-lookup"><span data-stu-id="81b1e-145">[C#]</span></span>          |
| <span data-ttu-id="81b1e-146">ASP.NET Core(Angular 사용)</span><span class="sxs-lookup"><span data-stu-id="81b1e-146">ASP.NET Core with Angular</span></span>                    | <span data-ttu-id="81b1e-147">angular</span><span class="sxs-lookup"><span data-stu-id="81b1e-147">angular</span></span>        | <span data-ttu-id="81b1e-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="81b1e-148">[C#]</span></span>          |
| <span data-ttu-id="81b1e-149">ASP.NET Core(React.js 사용)</span><span class="sxs-lookup"><span data-stu-id="81b1e-149">ASP.NET Core with React.js</span></span>                   | <span data-ttu-id="81b1e-150">react</span><span class="sxs-lookup"><span data-stu-id="81b1e-150">react</span></span>          | <span data-ttu-id="81b1e-151">[C#]</span><span class="sxs-lookup"><span data-stu-id="81b1e-151">[C#]</span></span>          |
| <span data-ttu-id="81b1e-152">ASP.NET Core(React.js 및 Redux 사용)</span><span class="sxs-lookup"><span data-stu-id="81b1e-152">ASP.NET Core with React.js and Redux</span></span>         | <span data-ttu-id="81b1e-153">reactredux</span><span class="sxs-lookup"><span data-stu-id="81b1e-153">reactredux</span></span>     | <span data-ttu-id="81b1e-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="81b1e-154">[C#]</span></span>          |
| <span data-ttu-id="81b1e-155">ASP.NET Core 웹 API</span><span class="sxs-lookup"><span data-stu-id="81b1e-155">ASP.NET Core Web API</span></span>                         | <span data-ttu-id="81b1e-156">webapi</span><span class="sxs-lookup"><span data-stu-id="81b1e-156">webapi</span></span>         | <span data-ttu-id="81b1e-157">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="81b1e-157">[C#], F#</span></span>      |
| <span data-ttu-id="81b1e-158">global.json 파일</span><span class="sxs-lookup"><span data-stu-id="81b1e-158">global.json file</span></span>                             | <span data-ttu-id="81b1e-159">globaljson</span><span class="sxs-lookup"><span data-stu-id="81b1e-159">globaljson</span></span>     |               |
| <span data-ttu-id="81b1e-160">Nuget 구성</span><span class="sxs-lookup"><span data-stu-id="81b1e-160">Nuget config</span></span>                                 | <span data-ttu-id="81b1e-161">nugetconfig</span><span class="sxs-lookup"><span data-stu-id="81b1e-161">nugetconfig</span></span>    |               |
| <span data-ttu-id="81b1e-162">웹 구성</span><span class="sxs-lookup"><span data-stu-id="81b1e-162">Web config</span></span>                                   | <span data-ttu-id="81b1e-163">webconfig</span><span class="sxs-lookup"><span data-stu-id="81b1e-163">webconfig</span></span>      |               |
| <span data-ttu-id="81b1e-164">솔루션 파일</span><span class="sxs-lookup"><span data-stu-id="81b1e-164">Solution file</span></span>                                | <span data-ttu-id="81b1e-165">sln</span><span class="sxs-lookup"><span data-stu-id="81b1e-165">sln</span></span>            |               |
| <span data-ttu-id="81b1e-166">Razor 페이지</span><span class="sxs-lookup"><span data-stu-id="81b1e-166">Razor page</span></span>                                   | <span data-ttu-id="81b1e-167">페이지</span><span class="sxs-lookup"><span data-stu-id="81b1e-167">page</span></span>           |               |
| <span data-ttu-id="81b1e-168">MVC/ViewImports</span><span class="sxs-lookup"><span data-stu-id="81b1e-168">MVC/ViewImports</span></span>                              | <span data-ttu-id="81b1e-169">viewimports</span><span class="sxs-lookup"><span data-stu-id="81b1e-169">viewimports</span></span>    |               |
| <span data-ttu-id="81b1e-170">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="81b1e-170">MVC ViewStart</span></span>                                | <span data-ttu-id="81b1e-171">viewstart</span><span class="sxs-lookup"><span data-stu-id="81b1e-171">viewstart</span></span>      |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="81b1e-172">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="81b1e-172">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="81b1e-173">명령에는 템플릿의 기본 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-173">The command contains a default list of templates.</span></span> <span data-ttu-id="81b1e-174">`dotnet new -all`을 사용하여 사용 가능한 템플릿 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-174">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="81b1e-175">다음 표에는 .NET Core 1.x SDK와 함께 사전 설치된 템플릿이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-175">The following table shows the templates that come pre-installed with the .NET Core 1.x SDK.</span></span> <span data-ttu-id="81b1e-176">템플릿의 기본 언어는 대괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-176">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="81b1e-177">템플릿 설명</span><span class="sxs-lookup"><span data-stu-id="81b1e-177">Template description</span></span>  | <span data-ttu-id="81b1e-178">템플릿 이름</span><span class="sxs-lookup"><span data-stu-id="81b1e-178">Template name</span></span>  | <span data-ttu-id="81b1e-179">언어</span><span class="sxs-lookup"><span data-stu-id="81b1e-179">Languages</span></span> |
|----------------------|----------------|-----------|
| <span data-ttu-id="81b1e-180">콘솔 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="81b1e-180">Console application</span></span>  | <span data-ttu-id="81b1e-181">콘솔</span><span class="sxs-lookup"><span data-stu-id="81b1e-181">console</span></span>        | <span data-ttu-id="81b1e-182">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="81b1e-182">[C#], F#</span></span>  |
| <span data-ttu-id="81b1e-183">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="81b1e-183">Class library</span></span>        | <span data-ttu-id="81b1e-184">classlib</span><span class="sxs-lookup"><span data-stu-id="81b1e-184">classlib</span></span>       | <span data-ttu-id="81b1e-185">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="81b1e-185">[C#], F#</span></span>  |
| <span data-ttu-id="81b1e-186">단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="81b1e-186">Unit test project</span></span>    | <span data-ttu-id="81b1e-187">mstest</span><span class="sxs-lookup"><span data-stu-id="81b1e-187">mstest</span></span>         | <span data-ttu-id="81b1e-188">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="81b1e-188">[C#], F#</span></span>  |
| <span data-ttu-id="81b1e-189">xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="81b1e-189">xUnit test project</span></span>   | <span data-ttu-id="81b1e-190">xunit</span><span class="sxs-lookup"><span data-stu-id="81b1e-190">xunit</span></span>          | <span data-ttu-id="81b1e-191">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="81b1e-191">[C#], F#</span></span>  |
| <span data-ttu-id="81b1e-192">ASP.NET Core 비어 있음</span><span class="sxs-lookup"><span data-stu-id="81b1e-192">ASP.NET Core empty</span></span>   | <span data-ttu-id="81b1e-193">웹</span><span class="sxs-lookup"><span data-stu-id="81b1e-193">web</span></span>            | <span data-ttu-id="81b1e-194">[C#]</span><span class="sxs-lookup"><span data-stu-id="81b1e-194">[C#]</span></span>      |
| <span data-ttu-id="81b1e-195">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="81b1e-195">ASP.NET Core Web App</span></span> | <span data-ttu-id="81b1e-196">mvc</span><span class="sxs-lookup"><span data-stu-id="81b1e-196">mvc</span></span>            | <span data-ttu-id="81b1e-197">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="81b1e-197">[C#], F#</span></span>  |
| <span data-ttu-id="81b1e-198">ASP.NET Core 웹 API</span><span class="sxs-lookup"><span data-stu-id="81b1e-198">ASP.NET Core Web API</span></span> | <span data-ttu-id="81b1e-199">webapi</span><span class="sxs-lookup"><span data-stu-id="81b1e-199">webapi</span></span>         | <span data-ttu-id="81b1e-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="81b1e-200">[C#]</span></span>      |
| <span data-ttu-id="81b1e-201">Nuget 구성</span><span class="sxs-lookup"><span data-stu-id="81b1e-201">Nuget config</span></span>         | <span data-ttu-id="81b1e-202">nugetconfig</span><span class="sxs-lookup"><span data-stu-id="81b1e-202">nugetconfig</span></span>    |           |
| <span data-ttu-id="81b1e-203">웹 구성</span><span class="sxs-lookup"><span data-stu-id="81b1e-203">Web config</span></span>           | <span data-ttu-id="81b1e-204">webconfig</span><span class="sxs-lookup"><span data-stu-id="81b1e-204">webconfig</span></span>      |           |
| <span data-ttu-id="81b1e-205">솔루션 파일</span><span class="sxs-lookup"><span data-stu-id="81b1e-205">Solution file</span></span>        | <span data-ttu-id="81b1e-206">sln</span><span class="sxs-lookup"><span data-stu-id="81b1e-206">sln</span></span>            |           |

---

## <a name="options"></a><span data-ttu-id="81b1e-207">옵션</span><span class="sxs-lookup"><span data-stu-id="81b1e-207">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="81b1e-208">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="81b1e-208">.NET Core 2.x</span></span>](#tab/netcore2x)

`--force`

<span data-ttu-id="81b1e-209">기존 파일을 변경할 경우에도 콘텐츠를 강제 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-209">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="81b1e-210">출력 디렉터리에 이미 프로젝트가 포함되어 있는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-210">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="81b1e-211">명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-211">Prints out help for the command.</span></span> <span data-ttu-id="81b1e-212">`dotnet new` 명령 자체 또는 `dotnet new mvc --help` 같은 템플릿에 대해 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-212">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="81b1e-213">제공된 `PATH` 또는 `NUGET_ID`에서 소스 또는 템플릿 팩을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-213">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="81b1e-214">사용자 지정 템플릿을 만드는 방법에 대한 자세한 내용은 [dotnet new에 대한 사용자 지정 템플릿](custom-templates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81b1e-214">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="81b1e-215">지정된 이름을 포함하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-215">Lists templates containing the specified name.</span></span> <span data-ttu-id="81b1e-216">`dotnet new` 명령에 대해 호출되는 경우 지정된 디렉터리에서 사용 가능한 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-216">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="81b1e-217">예를 들어 디렉터리에 이미 프로젝트가 포함되어 있는 경우 일부 프로젝트 템플릿을 나열하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-217">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="81b1e-218">만들 템플릿의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-218">The language of the template to create.</span></span> <span data-ttu-id="81b1e-219">허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조).</span><span class="sxs-lookup"><span data-stu-id="81b1e-219">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="81b1e-220">일부 템플릿의 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-220">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="81b1e-221">생성된 출력에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-221">The name for the created output.</span></span> <span data-ttu-id="81b1e-222">이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-222">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="81b1e-223">생성된 출력을 배치할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-223">Location to place the generated output.</span></span> <span data-ttu-id="81b1e-224">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-224">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="81b1e-225">사용 가능한 형식에 따라 템플릿을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-225">Filters templates based on available types.</span></span> <span data-ttu-id="81b1e-226">미리 정의된 값은 “project”, “item” 또는 “other”입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-226">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="81b1e-227">제공된 `PATH` 또는 `NUGET_ID`에서 소스 또는 템플릿 팩을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-227">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="81b1e-228">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="81b1e-228">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="81b1e-229">`dotnet new` 명령의 컨텍스트에서만 실행되는 경우 특정 유형의 프로젝트에 대한 모든 템플릿을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-229">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="81b1e-230">`dotnet new web -all`처럼 특정 템플릿의 컨텍스트에서 실행되는 경우 `-all`은 강제 생성 플래그로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-230">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="81b1e-231">출력 디렉터리에 이미 프로젝트가 포함되어 있는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-231">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="81b1e-232">명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-232">Prints out help for the command.</span></span> <span data-ttu-id="81b1e-233">`dotnet new` 명령 자체 또는 `dotnet new mvc --help` 같은 템플릿에 대해 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-233">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="81b1e-234">지정된 이름을 포함하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-234">Lists templates containing the specified name.</span></span> <span data-ttu-id="81b1e-235">`dotnet new` 명령에 대해 호출되는 경우 지정된 디렉터리에서 사용 가능한 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-235">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="81b1e-236">예를 들어 디렉터리에 이미 프로젝트가 포함되어 있는 경우 일부 프로젝트 템플릿을 나열하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-236">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="81b1e-237">만들 템플릿의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-237">The language of the template to create.</span></span> <span data-ttu-id="81b1e-238">허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조).</span><span class="sxs-lookup"><span data-stu-id="81b1e-238">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="81b1e-239">일부 템플릿의 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-239">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="81b1e-240">생성된 출력에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-240">The name for the created output.</span></span> <span data-ttu-id="81b1e-241">이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-241">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="81b1e-242">생성된 출력을 배치할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-242">Location to place the generated output.</span></span> <span data-ttu-id="81b1e-243">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-243">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="81b1e-244">템플릿 옵션</span><span class="sxs-lookup"><span data-stu-id="81b1e-244">Template options</span></span>

<span data-ttu-id="81b1e-245">각 프로젝트 템플릿에는 사용할 수 있는 추가 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-245">Each project template may have additional options available.</span></span> <span data-ttu-id="81b1e-246">코어 템플릿에는 다음과 같은 추가 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-246">The core templates have the following additional options:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="81b1e-247">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="81b1e-247">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="81b1e-248">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="81b1e-248">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="81b1e-249">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-249">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="81b1e-250">**classlib**</span><span class="sxs-lookup"><span data-stu-id="81b1e-250">**classlib**</span></span>

<span data-ttu-id="81b1e-251">`-f|--framework <FRAMEWORK>` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-251">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="81b1e-252">값: `netcoreapp2.0`(.NET Core 클래스 라이브러리를 만드는 경우) 또는 `netstandard2.0`(.NET Standard 클래스 라이브러리를 만드는 경우).</span><span class="sxs-lookup"><span data-stu-id="81b1e-252">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="81b1e-253">기본값은 `netstandard2.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-253">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="81b1e-254">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-254">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="81b1e-255">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="81b1e-255">**mstest, xunit**</span></span>

<span data-ttu-id="81b1e-256">`-p|--enable-pack` - [dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-256">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="81b1e-257">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-257">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="81b1e-258">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="81b1e-258">**globaljson**</span></span>

<span data-ttu-id="81b1e-259">`--sdk-version <VERSION_NUMBER>` - *global.json* 파일에서 사용할 .NET Core SDK 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-259">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="81b1e-260">**web**</span><span class="sxs-lookup"><span data-stu-id="81b1e-260">**web**</span></span>

<span data-ttu-id="81b1e-261">`--use-launch-settings` - 생성된 템플릿 출력에 *launchSettings.json*을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-261">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="81b1e-262">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-262">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="81b1e-263">**webapi**</span><span class="sxs-lookup"><span data-stu-id="81b1e-263">**webapi**</span></span>

<span data-ttu-id="81b1e-264">`-au|--auth <AUTHENTICATION_TYPE>` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-264">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="81b1e-265">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-265">The possible values are:</span></span>

- <span data-ttu-id="81b1e-266">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="81b1e-266">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="81b1e-267">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-267">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="81b1e-268">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-268">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="81b1e-269">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-269">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="81b1e-270">`--aad-b2c-instance <INSTANCE>` - 연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-270">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="81b1e-271">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-271">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="81b1e-272">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-272">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="81b1e-273">`-ssp|--susi-policy-id <ID>` - 이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-273">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="81b1e-274">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-274">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="81b1e-275">`--aad-instance <INSTANCE>` - 연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-275">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="81b1e-276">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-276">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="81b1e-277">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-277">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="81b1e-278">`--client-id <ID>` - 이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-278">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="81b1e-279">`IndividualB2C` 또는 `SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-279">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="81b1e-280">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-280">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="81b1e-281">`--domain <DOMAIN>` - 디렉터리 테넌트에 대한 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-281">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="81b1e-282">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-282">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="81b1e-283">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-283">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="81b1e-284">`--tenant-id <ID>` - 연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-284">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="81b1e-285">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-285">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="81b1e-286">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-286">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="81b1e-287">`-r|--org-read-access` - 디렉터리에 대한 이 응용 프로그램 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-287">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="81b1e-288">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-288">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="81b1e-289">`--use-launch-settings` - 생성된 템플릿 출력에 *launchSettings.json*을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-289">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="81b1e-290">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-290">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="81b1e-291">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-291">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="81b1e-292">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-292">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="81b1e-293">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="81b1e-293">**mvc, razor**</span></span>

<span data-ttu-id="81b1e-294">`-au|--auth <AUTHENTICATION_TYPE>` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-294">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="81b1e-295">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-295">The possible values are:</span></span>

- <span data-ttu-id="81b1e-296">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="81b1e-296">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="81b1e-297">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-297">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="81b1e-298">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-298">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="81b1e-299">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-299">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="81b1e-300">`MultiOrg` - 여러 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-300">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="81b1e-301">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-301">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="81b1e-302">`--aad-b2c-instance <INSTANCE>` - 연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-302">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="81b1e-303">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-303">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="81b1e-304">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-304">The default value is `https://login.microsoftonline.com/tfp/` .</span></span>

<span data-ttu-id="81b1e-305">`-ssp|--susi-policy-id <ID>` - 이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-305">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="81b1e-306">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-306">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="81b1e-307">`-rp|--reset-password-policy-id <ID>` - 이 프로젝트에 대한 암호 재설정 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-307">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="81b1e-308">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-308">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="81b1e-309">`-ep|--edit-profile-policy-id <ID>` - 이 프로젝트에 대한 프로필 편집 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-309">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="81b1e-310">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-310">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="81b1e-311">`--aad-instance <INSTANCE>` - 연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-311">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="81b1e-312">`SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-312">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="81b1e-313">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-313">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="81b1e-314">`--client-id <ID>` - 이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-314">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="81b1e-315">`IndividualB2C`, `SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-315">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="81b1e-316">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-316">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="81b1e-317">`--domain <DOMAIN>` - 디렉터리 테넌트에 대한 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-317">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="81b1e-318">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-318">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="81b1e-319">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-319">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="81b1e-320">`--tenant-id <ID>` - 연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-320">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="81b1e-321">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-321">Use with `SingleOrg` authentication..</span></span> <span data-ttu-id="81b1e-322">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-322">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="81b1e-323">`--callback-path <PATH>` - 리디렉션 URI의 응용 프로그램 기본 경로 내 요청 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-323">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="81b1e-324">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-324">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="81b1e-325">기본값은 `/signin-oidc`입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-325">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="81b1e-326">`-r|--org-read-access` - 디렉터리에 대한 이 응용 프로그램 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-326">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="81b1e-327">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-327">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="81b1e-328">`--use-launch-settings` - 생성된 템플릿 출력에 *launchSettings.json*을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-328">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="81b1e-329">`--use-browserlink` - 프로젝트에 BrowserLink를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-329">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="81b1e-330">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-330">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="81b1e-331">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-331">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="81b1e-332">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-332">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="81b1e-333">**page**</span><span class="sxs-lookup"><span data-stu-id="81b1e-333">**page**</span></span>

<span data-ttu-id="81b1e-334">`-na|--namespace <NAMESPACE_NAME>` - 생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-334">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="81b1e-335">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-335">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="81b1e-336">`-np|--no-pagemodel` - PageModel 없이 페이지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-336">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="81b1e-337">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="81b1e-337">**viewimports**</span></span>

<span data-ttu-id="81b1e-338">`-na|--namespace <NAMESPACE_NAME>` - 생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-338">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="81b1e-339">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-339">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="81b1e-340">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="81b1e-340">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="81b1e-341">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="81b1e-341">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="81b1e-342">`-f|--framework` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-342">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="81b1e-343">값: `netcoreapp1.0` 또는 `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="81b1e-343">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="81b1e-344">기본값은 `netcoreapp1.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-344">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="81b1e-345">**classlib**</span><span class="sxs-lookup"><span data-stu-id="81b1e-345">**classlib**</span></span>

<span data-ttu-id="81b1e-346">`-f|--framework` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-346">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="81b1e-347">값: `netcoreapp1.0`, `netcoreapp1.1` 또는 `netstandard1.0`~`netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="81b1e-347">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="81b1e-348">기본값은 `netstandard1.4`입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-348">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="81b1e-349">**mvc**</span><span class="sxs-lookup"><span data-stu-id="81b1e-349">**mvc**</span></span>

<span data-ttu-id="81b1e-350">`-f|--framework` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-350">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="81b1e-351">값: `netcoreapp1.0` 또는 `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="81b1e-351">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="81b1e-352">기본값은 `netcoreapp1.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-352">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="81b1e-353">`-au|--auth` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-353">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="81b1e-354">값: `None` 또는 `Individual`.</span><span class="sxs-lookup"><span data-stu-id="81b1e-354">Values: `None` or `Individual`.</span></span> <span data-ttu-id="81b1e-355">기본값은 `None`입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-355">The default value is `None`.</span></span>

<span data-ttu-id="81b1e-356">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-356">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="81b1e-357">값: `true` 또는 `false`.</span><span class="sxs-lookup"><span data-stu-id="81b1e-357">Values: `true` or `false`.</span></span> <span data-ttu-id="81b1e-358">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-358">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="81b1e-359">예제</span><span class="sxs-lookup"><span data-stu-id="81b1e-359">Examples</span></span>

<span data-ttu-id="81b1e-360">현재 디렉터리에 F# 콘솔 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-360">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang f#`

<span data-ttu-id="81b1e-361">지정된 디렉터리에서 .NET Standard 클래스 라이브러리 프로젝트를 만듭니다(.NET Core 2.0 SDK 이상 버전에서만 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="81b1e-361">Create a .NET Standard class library project in the specified directory (available only with .NET Core 2.0 SDK or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="81b1e-362">.NET Core 2.0을 대상으로 인증 없이 현재 디렉터리에 새 ASP.NET Core C# MVC 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-362">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 2.0:</span></span>

`dotnet new mvc -au None -f netcoreapp2.0`

<span data-ttu-id="81b1e-363">.NET Core 2.0을 대상으로 새 xUnit 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-363">Create a new xUnit application targeting .NET Core 2.0:</span></span>

`dotnet new xunit --framework netcoreapp2.0`

<span data-ttu-id="81b1e-364">MVC에 대해 사용할 수 있는 모든 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="81b1e-364">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

## <a name="see-also"></a><span data-ttu-id="81b1e-365">참고 항목</span><span class="sxs-lookup"><span data-stu-id="81b1e-365">See also</span></span>

[<span data-ttu-id="81b1e-366">dotnet new에 대한 사용자 지정 템플릿</span><span class="sxs-lookup"><span data-stu-id="81b1e-366">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="81b1e-367">dotnet용 사용자 지정 템플릿 새로 만들기</span><span class="sxs-lookup"><span data-stu-id="81b1e-367">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
<span data-ttu-id="81b1e-368">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)(dotnet/dotnet-template-samples GitHub 리포지토리)</span><span class="sxs-lookup"><span data-stu-id="81b1e-368">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)</span></span>  
<span data-ttu-id="81b1e-369">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)(dotnet new에 대한 사용 가능한 템플릿)</span><span class="sxs-lookup"><span data-stu-id="81b1e-369">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>

