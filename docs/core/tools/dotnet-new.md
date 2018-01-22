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
ms.openlocfilehash: cf65dc80f135badcb1580726a12a9ae9d94ae3d7
ms.sourcegitcommit: 8bde7a3432f30fc771079744955c75c58c4eb393
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2018
---
# <a name="dotnet-new"></a><span data-ttu-id="04f99-104">dotnet new</span><span class="sxs-lookup"><span data-stu-id="04f99-104">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="04f99-105">name</span><span class="sxs-lookup"><span data-stu-id="04f99-105">Name</span></span>

<span data-ttu-id="04f99-106">`dotnet new` - 지정된 템플릿을 기반으로 새 프로젝트, 구성 파일 또는 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="04f99-107">개요</span><span class="sxs-lookup"><span data-stu-id="04f99-107">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="04f99-108">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="04f99-108">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="04f99-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="04f99-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="04f99-110">설명</span><span class="sxs-lookup"><span data-stu-id="04f99-110">Description</span></span>

<span data-ttu-id="04f99-111">`dotnet new` 명령은 유효한 .NET Core 프로젝트를 초기화하는 편리한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span> 

<span data-ttu-id="04f99-112">이 명령은 [템플릿 엔진](https://github.com/dotnet/templating)을 호출하여 지정된 템플릿 및 옵션을 기반으로 디스크에 아티팩트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="04f99-113">인수</span><span class="sxs-lookup"><span data-stu-id="04f99-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="04f99-114">명령이 호출될 때 인스턴스화할 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="04f99-115">각 템플릿에는 전달할 수 있는 특정 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="04f99-116">자세한 내용은 [템플릿 옵션](#template-options)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="04f99-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="04f99-117">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="04f99-117">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="04f99-118">명령에는 템플릿의 기본 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-118">The command contains a default list of templates.</span></span> <span data-ttu-id="04f99-119">`dotnet new -l`을 사용하여 사용 가능한 템플릿 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="04f99-120">다음 표에는 .NET Core 2.0 SDK와 함께 사전 설치된 템플릿이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-120">The following table shows the templates that come pre-installed with the .NET Core 2.0 SDK.</span></span> <span data-ttu-id="04f99-121">템플릿의 기본 언어는 대괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="04f99-122">템플릿 설명</span><span class="sxs-lookup"><span data-stu-id="04f99-122">Template description</span></span>                          | <span data-ttu-id="04f99-123">템플릿 이름</span><span class="sxs-lookup"><span data-stu-id="04f99-123">Template name</span></span> | <span data-ttu-id="04f99-124">언어</span><span class="sxs-lookup"><span data-stu-id="04f99-124">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="04f99-125">콘솔 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="04f99-125">Console application</span></span>                          | `console`     | <span data-ttu-id="04f99-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="04f99-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="04f99-127">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="04f99-127">Class library</span></span>                                | `classlib`    | <span data-ttu-id="04f99-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="04f99-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="04f99-129">단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="04f99-129">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="04f99-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="04f99-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="04f99-131">xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="04f99-131">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="04f99-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="04f99-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="04f99-133">ASP.NET Core 비어 있음</span><span class="sxs-lookup"><span data-stu-id="04f99-133">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="04f99-134">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="04f99-134">[C#], F#</span></span>      |
| <span data-ttu-id="04f99-135">ASP.NET Core 웹앱(모델-뷰-컨트롤러)</span><span class="sxs-lookup"><span data-stu-id="04f99-135">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="04f99-136">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="04f99-136">[C#], F#</span></span>      |
| <span data-ttu-id="04f99-137">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="04f99-137">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="04f99-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="04f99-138">[C#]</span></span>          |
| <span data-ttu-id="04f99-139">ASP.NET Core(Angular 사용)</span><span class="sxs-lookup"><span data-stu-id="04f99-139">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="04f99-140">[C#]</span><span class="sxs-lookup"><span data-stu-id="04f99-140">[C#]</span></span>          |
| <span data-ttu-id="04f99-141">ASP.NET Core(React.js 사용)</span><span class="sxs-lookup"><span data-stu-id="04f99-141">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="04f99-142">[C#]</span><span class="sxs-lookup"><span data-stu-id="04f99-142">[C#]</span></span>          |
| <span data-ttu-id="04f99-143">ASP.NET Core(React.js 및 Redux 사용)</span><span class="sxs-lookup"><span data-stu-id="04f99-143">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="04f99-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="04f99-144">[C#]</span></span>          |
| <span data-ttu-id="04f99-145">ASP.NET Core 웹 API</span><span class="sxs-lookup"><span data-stu-id="04f99-145">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="04f99-146">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="04f99-146">[C#], F#</span></span>      |
| <span data-ttu-id="04f99-147">global.json 파일</span><span class="sxs-lookup"><span data-stu-id="04f99-147">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="04f99-148">Nuget 구성</span><span class="sxs-lookup"><span data-stu-id="04f99-148">Nuget config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="04f99-149">웹 구성</span><span class="sxs-lookup"><span data-stu-id="04f99-149">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="04f99-150">솔루션 파일</span><span class="sxs-lookup"><span data-stu-id="04f99-150">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="04f99-151">Razor 페이지</span><span class="sxs-lookup"><span data-stu-id="04f99-151">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="04f99-152">MVC/ViewImports</span><span class="sxs-lookup"><span data-stu-id="04f99-152">MVC/ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="04f99-153">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="04f99-153">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="04f99-154">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="04f99-154">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="04f99-155">명령에는 템플릿의 기본 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-155">The command contains a default list of templates.</span></span> <span data-ttu-id="04f99-156">`dotnet new -all`을 사용하여 사용 가능한 템플릿 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-156">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="04f99-157">다음 표에는 .NET Core 1.x SDK와 함께 사전 설치된 템플릿이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-157">The following table shows the templates that come pre-installed with the .NET Core 1.x SDK.</span></span> <span data-ttu-id="04f99-158">템플릿의 기본 언어는 대괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-158">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="04f99-159">템플릿 설명</span><span class="sxs-lookup"><span data-stu-id="04f99-159">Template description</span></span>  | <span data-ttu-id="04f99-160">템플릿 이름</span><span class="sxs-lookup"><span data-stu-id="04f99-160">Template name</span></span> | <span data-ttu-id="04f99-161">언어</span><span class="sxs-lookup"><span data-stu-id="04f99-161">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="04f99-162">콘솔 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="04f99-162">Console application</span></span>  | `console`     | <span data-ttu-id="04f99-163">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="04f99-163">[C#], F#</span></span>  |
| <span data-ttu-id="04f99-164">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="04f99-164">Class library</span></span>        | `classlib`    | <span data-ttu-id="04f99-165">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="04f99-165">[C#], F#</span></span>  |
| <span data-ttu-id="04f99-166">단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="04f99-166">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="04f99-167">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="04f99-167">[C#], F#</span></span>  |
| <span data-ttu-id="04f99-168">xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="04f99-168">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="04f99-169">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="04f99-169">[C#], F#</span></span>  |
| <span data-ttu-id="04f99-170">ASP.NET Core 비어 있음</span><span class="sxs-lookup"><span data-stu-id="04f99-170">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="04f99-171">[C#]</span><span class="sxs-lookup"><span data-stu-id="04f99-171">[C#]</span></span>      |
| <span data-ttu-id="04f99-172">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="04f99-172">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="04f99-173">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="04f99-173">[C#], F#</span></span>  |
| <span data-ttu-id="04f99-174">ASP.NET Core 웹 API</span><span class="sxs-lookup"><span data-stu-id="04f99-174">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="04f99-175">[C#]</span><span class="sxs-lookup"><span data-stu-id="04f99-175">[C#]</span></span>      |
| <span data-ttu-id="04f99-176">Nuget 구성</span><span class="sxs-lookup"><span data-stu-id="04f99-176">Nuget config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="04f99-177">웹 구성</span><span class="sxs-lookup"><span data-stu-id="04f99-177">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="04f99-178">솔루션 파일</span><span class="sxs-lookup"><span data-stu-id="04f99-178">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="04f99-179">옵션</span><span class="sxs-lookup"><span data-stu-id="04f99-179">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="04f99-180">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="04f99-180">.NET Core 2.x</span></span>](#tab/netcore2x)

`--force`

<span data-ttu-id="04f99-181">기존 파일을 변경할 경우에도 콘텐츠를 강제 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-181">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="04f99-182">출력 디렉터리에 이미 프로젝트가 포함되어 있는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-182">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="04f99-183">명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-183">Prints out help for the command.</span></span> <span data-ttu-id="04f99-184">`dotnet new` 명령 자체 또는 `dotnet new mvc --help` 같은 템플릿에 대해 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-184">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="04f99-185">제공된 `PATH` 또는 `NUGET_ID`에서 소스 또는 템플릿 팩을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-185">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="04f99-186">사용자 지정 템플릿을 만드는 방법에 대한 자세한 내용은 [dotnet new에 대한 사용자 지정 템플릿](custom-templates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="04f99-186">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="04f99-187">지정된 이름을 포함하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-187">Lists templates containing the specified name.</span></span> <span data-ttu-id="04f99-188">`dotnet new` 명령에 대해 호출되는 경우 지정된 디렉터리에서 사용 가능한 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-188">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="04f99-189">예를 들어 디렉터리에 이미 프로젝트가 포함되어 있는 경우 일부 프로젝트 템플릿을 나열하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-189">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="04f99-190">만들 템플릿의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-190">The language of the template to create.</span></span> <span data-ttu-id="04f99-191">허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조).</span><span class="sxs-lookup"><span data-stu-id="04f99-191">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="04f99-192">일부 템플릿의 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-192">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="04f99-193">생성된 출력에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-193">The name for the created output.</span></span> <span data-ttu-id="04f99-194">이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-194">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="04f99-195">생성된 출력을 배치할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-195">Location to place the generated output.</span></span> <span data-ttu-id="04f99-196">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-196">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="04f99-197">사용 가능한 형식에 따라 템플릿을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-197">Filters templates based on available types.</span></span> <span data-ttu-id="04f99-198">미리 정의된 값은 “project”, “item” 또는 “other”입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-198">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="04f99-199">제공된 `PATH` 또는 `NUGET_ID`에서 소스 또는 템플릿 팩을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-199">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="04f99-200">`PATH`를 사용하여 템플릿을 제거하려면 경로를 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-200">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="04f99-201">예를 들어 *C:/Users/\<사용자>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지만 상위 폴더의 *./GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-201">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="04f99-202">마지막의 종료하는 디렉터리 슬래시도 템플릿 경로에 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="04f99-202">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="04f99-203">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="04f99-203">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="04f99-204">`dotnet new` 명령의 컨텍스트에서만 실행되는 경우 특정 유형의 프로젝트에 대한 모든 템플릿을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-204">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="04f99-205">`dotnet new web -all`처럼 특정 템플릿의 컨텍스트에서 실행되는 경우 `-all`은 강제 생성 플래그로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-205">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="04f99-206">출력 디렉터리에 이미 프로젝트가 포함되어 있는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-206">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="04f99-207">명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-207">Prints out help for the command.</span></span> <span data-ttu-id="04f99-208">`dotnet new` 명령 자체 또는 `dotnet new mvc --help` 같은 템플릿에 대해 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-208">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="04f99-209">지정된 이름을 포함하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-209">Lists templates containing the specified name.</span></span> <span data-ttu-id="04f99-210">`dotnet new` 명령에 대해 호출되는 경우 지정된 디렉터리에서 사용 가능한 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-210">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="04f99-211">예를 들어 디렉터리에 이미 프로젝트가 포함되어 있는 경우 일부 프로젝트 템플릿을 나열하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-211">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="04f99-212">만들 템플릿의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-212">The language of the template to create.</span></span> <span data-ttu-id="04f99-213">허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조).</span><span class="sxs-lookup"><span data-stu-id="04f99-213">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="04f99-214">일부 템플릿의 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-214">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="04f99-215">생성된 출력에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-215">The name for the created output.</span></span> <span data-ttu-id="04f99-216">이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-216">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="04f99-217">생성된 출력을 배치할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-217">Location to place the generated output.</span></span> <span data-ttu-id="04f99-218">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-218">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="04f99-219">템플릿 옵션</span><span class="sxs-lookup"><span data-stu-id="04f99-219">Template options</span></span>

<span data-ttu-id="04f99-220">각 프로젝트 템플릿에는 사용할 수 있는 추가 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-220">Each project template may have additional options available.</span></span> <span data-ttu-id="04f99-221">코어 템플릿에는 다음과 같은 추가 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-221">The core templates have the following additional options:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="04f99-222">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="04f99-222">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="04f99-223">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="04f99-223">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="04f99-224">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-224">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="04f99-225">**classlib**</span><span class="sxs-lookup"><span data-stu-id="04f99-225">**classlib**</span></span>

<span data-ttu-id="04f99-226">`-f|--framework <FRAMEWORK>` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-226">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="04f99-227">값: `netcoreapp2.0`(.NET Core 클래스 라이브러리를 만드는 경우) 또는 `netstandard2.0`(.NET Standard 클래스 라이브러리를 만드는 경우).</span><span class="sxs-lookup"><span data-stu-id="04f99-227">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="04f99-228">기본값은 `netstandard2.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-228">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="04f99-229">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-229">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="04f99-230">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="04f99-230">**mstest, xunit**</span></span>

<span data-ttu-id="04f99-231">`-p|--enable-pack` - [dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-231">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="04f99-232">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-232">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="04f99-233">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="04f99-233">**globaljson**</span></span>

<span data-ttu-id="04f99-234">`--sdk-version <VERSION_NUMBER>` - *global.json* 파일에서 사용할 .NET Core SDK 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-234">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="04f99-235">**web**</span><span class="sxs-lookup"><span data-stu-id="04f99-235">**web**</span></span>

<span data-ttu-id="04f99-236">`--use-launch-settings` - 생성된 템플릿 출력에 *launchSettings.json*을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-236">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="04f99-237">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-237">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="04f99-238">**webapi**</span><span class="sxs-lookup"><span data-stu-id="04f99-238">**webapi**</span></span>

<span data-ttu-id="04f99-239">`-au|--auth <AUTHENTICATION_TYPE>` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-239">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="04f99-240">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-240">The possible values are:</span></span>

- <span data-ttu-id="04f99-241">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="04f99-241">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="04f99-242">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-242">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="04f99-243">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-243">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="04f99-244">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-244">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="04f99-245">`--aad-b2c-instance <INSTANCE>` - 연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-245">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="04f99-246">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-246">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="04f99-247">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-247">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="04f99-248">`-ssp|--susi-policy-id <ID>` - 이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-248">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="04f99-249">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-249">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="04f99-250">`--aad-instance <INSTANCE>` - 연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-250">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="04f99-251">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-251">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="04f99-252">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-252">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="04f99-253">`--client-id <ID>` - 이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-253">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="04f99-254">`IndividualB2C` 또는 `SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-254">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="04f99-255">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-255">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="04f99-256">`--domain <DOMAIN>` - 디렉터리 테넌트에 대한 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-256">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="04f99-257">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-257">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="04f99-258">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-258">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="04f99-259">`--tenant-id <ID>` - 연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-259">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="04f99-260">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-260">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="04f99-261">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-261">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="04f99-262">`-r|--org-read-access` - 디렉터리에 대한 이 응용 프로그램 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-262">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="04f99-263">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-263">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="04f99-264">`--use-launch-settings` - 생성된 템플릿 출력에 *launchSettings.json*을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-264">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="04f99-265">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-265">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="04f99-266">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-266">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="04f99-267">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-267">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="04f99-268">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="04f99-268">**mvc, razor**</span></span>

<span data-ttu-id="04f99-269">`-au|--auth <AUTHENTICATION_TYPE>` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-269">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="04f99-270">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-270">The possible values are:</span></span>

- <span data-ttu-id="04f99-271">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="04f99-271">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="04f99-272">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-272">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="04f99-273">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-273">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="04f99-274">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-274">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="04f99-275">`MultiOrg` - 여러 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-275">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="04f99-276">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-276">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="04f99-277">`--aad-b2c-instance <INSTANCE>` - 연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-277">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="04f99-278">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-278">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="04f99-279">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-279">The default value is `https://login.microsoftonline.com/tfp/` .</span></span>

<span data-ttu-id="04f99-280">`-ssp|--susi-policy-id <ID>` - 이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-280">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="04f99-281">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-281">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="04f99-282">`-rp|--reset-password-policy-id <ID>` - 이 프로젝트에 대한 암호 재설정 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-282">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="04f99-283">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-283">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="04f99-284">`-ep|--edit-profile-policy-id <ID>` - 이 프로젝트에 대한 프로필 편집 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-284">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="04f99-285">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-285">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="04f99-286">`--aad-instance <INSTANCE>` - 연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-286">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="04f99-287">`SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-287">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="04f99-288">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-288">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="04f99-289">`--client-id <ID>` - 이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-289">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="04f99-290">`IndividualB2C`, `SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-290">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="04f99-291">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-291">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="04f99-292">`--domain <DOMAIN>` - 디렉터리 테넌트에 대한 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-292">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="04f99-293">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-293">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="04f99-294">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-294">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="04f99-295">`--tenant-id <ID>` - 연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-295">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="04f99-296">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-296">Use with `SingleOrg` authentication..</span></span> <span data-ttu-id="04f99-297">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-297">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="04f99-298">`--callback-path <PATH>` - 리디렉션 URI의 응용 프로그램 기본 경로 내 요청 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-298">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="04f99-299">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-299">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="04f99-300">기본값은 `/signin-oidc`입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-300">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="04f99-301">`-r|--org-read-access` - 디렉터리에 대한 이 응용 프로그램 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-301">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="04f99-302">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-302">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="04f99-303">`--use-launch-settings` - 생성된 템플릿 출력에 *launchSettings.json*을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-303">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="04f99-304">`--use-browserlink` - 프로젝트에 BrowserLink를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-304">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="04f99-305">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-305">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="04f99-306">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-306">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="04f99-307">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-307">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="04f99-308">**page**</span><span class="sxs-lookup"><span data-stu-id="04f99-308">**page**</span></span>

<span data-ttu-id="04f99-309">`-na|--namespace <NAMESPACE_NAME>` - 생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-309">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="04f99-310">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-310">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="04f99-311">`-np|--no-pagemodel` - PageModel 없이 페이지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-311">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="04f99-312">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="04f99-312">**viewimports**</span></span>

<span data-ttu-id="04f99-313">`-na|--namespace <NAMESPACE_NAME>` - 생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-313">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="04f99-314">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-314">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="04f99-315">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="04f99-315">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="04f99-316">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="04f99-316">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="04f99-317">`-f|--framework` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-317">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="04f99-318">값: `netcoreapp1.0` 또는 `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="04f99-318">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="04f99-319">기본값은 `netcoreapp1.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-319">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="04f99-320">**classlib**</span><span class="sxs-lookup"><span data-stu-id="04f99-320">**classlib**</span></span>

<span data-ttu-id="04f99-321">`-f|--framework` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-321">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="04f99-322">값: `netcoreapp1.0`, `netcoreapp1.1` 또는 `netstandard1.0`~`netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="04f99-322">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="04f99-323">기본값은 `netstandard1.4`입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-323">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="04f99-324">**mvc**</span><span class="sxs-lookup"><span data-stu-id="04f99-324">**mvc**</span></span>

<span data-ttu-id="04f99-325">`-f|--framework` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-325">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="04f99-326">값: `netcoreapp1.0` 또는 `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="04f99-326">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="04f99-327">기본값은 `netcoreapp1.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-327">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="04f99-328">`-au|--auth` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-328">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="04f99-329">값: `None` 또는 `Individual`.</span><span class="sxs-lookup"><span data-stu-id="04f99-329">Values: `None` or `Individual`.</span></span> <span data-ttu-id="04f99-330">기본값은 `None`입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-330">The default value is `None`.</span></span>

<span data-ttu-id="04f99-331">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-331">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="04f99-332">값: `true` 또는 `false`.</span><span class="sxs-lookup"><span data-stu-id="04f99-332">Values: `true` or `false`.</span></span> <span data-ttu-id="04f99-333">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-333">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="04f99-334">예제</span><span class="sxs-lookup"><span data-stu-id="04f99-334">Examples</span></span>

<span data-ttu-id="04f99-335">현재 디렉터리에 F# 콘솔 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-335">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang f#`

<span data-ttu-id="04f99-336">지정된 디렉터리에서 .NET Standard 클래스 라이브러리 프로젝트를 만듭니다(.NET Core 2.0 SDK 이상 버전에서만 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="04f99-336">Create a .NET Standard class library project in the specified directory (available only with .NET Core 2.0 SDK or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="04f99-337">.NET Core 2.0을 대상으로 인증 없이 현재 디렉터리에 새 ASP.NET Core C# MVC 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-337">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 2.0:</span></span>

`dotnet new mvc -au None -f netcoreapp2.0`

<span data-ttu-id="04f99-338">.NET Core 2.0을 대상으로 새 xUnit 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-338">Create a new xUnit application targeting .NET Core 2.0:</span></span>

`dotnet new xunit --framework netcoreapp2.0`

<span data-ttu-id="04f99-339">MVC에 대해 사용할 수 있는 모든 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="04f99-339">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

## <a name="see-also"></a><span data-ttu-id="04f99-340">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04f99-340">See also</span></span>

[<span data-ttu-id="04f99-341">dotnet new에 대한 사용자 지정 템플릿</span><span class="sxs-lookup"><span data-stu-id="04f99-341">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="04f99-342">dotnet용 사용자 지정 템플릿 새로 만들기</span><span class="sxs-lookup"><span data-stu-id="04f99-342">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
<span data-ttu-id="04f99-343">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)(dotnet/dotnet-template-samples GitHub 리포지토리)</span><span class="sxs-lookup"><span data-stu-id="04f99-343">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)</span></span>  
<span data-ttu-id="04f99-344">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)(dotnet new에 대한 사용 가능한 템플릿)</span><span class="sxs-lookup"><span data-stu-id="04f99-344">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
