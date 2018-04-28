---
title: dotnet new 명령 - .NET Core CLI
description: dotnet new 명령은 지정된 템플릿을 기반으로 새 .NET Core 프로젝트를 만듭니다.
author: mairaw
ms.author: mairaw
ms.date: 03/26/2018
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: ab8d6f779a428aab7bd2739105dcf08b51d14ab9
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-new"></a><span data-ttu-id="08130-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="08130-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="08130-104">name</span><span class="sxs-lookup"><span data-stu-id="08130-104">Name</span></span>

<span data-ttu-id="08130-105">`dotnet new` - 지정된 템플릿을 기반으로 새 프로젝트, 구성 파일 또는 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="08130-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="08130-106">개요</span><span class="sxs-lookup"><span data-stu-id="08130-106">Synopsis</span></span>

# <a name="net-core-20tabnetcore2x"></a>[<span data-ttu-id="08130-107">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="08130-107">.NET Core 2.0</span></span>](#tab/netcore2x)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="08130-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="08130-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="08130-109">설명</span><span class="sxs-lookup"><span data-stu-id="08130-109">Description</span></span>

<span data-ttu-id="08130-110">`dotnet new` 명령은 유효한 .NET Core 프로젝트를 초기화하는 편리한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-110">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="08130-111">이 명령은 [템플릿 엔진](https://github.com/dotnet/templating)을 호출하여 지정된 템플릿 및 옵션을 기반으로 디스크에 아티팩트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="08130-111">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="08130-112">인수</span><span class="sxs-lookup"><span data-stu-id="08130-112">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="08130-113">명령이 호출될 때 인스턴스화할 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="08130-114">각 템플릿에는 전달할 수 있는 특정 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08130-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="08130-115">자세한 내용은 [템플릿 옵션](#template-options)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08130-115">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-20tabnetcore2x"></a>[<span data-ttu-id="08130-116">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="08130-116">.NET Core 2.0</span></span>](#tab/netcore2x)

<span data-ttu-id="08130-117">명령에는 템플릿의 기본 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08130-117">The command contains a default list of templates.</span></span> <span data-ttu-id="08130-118">`dotnet new -l`을 사용하여 사용 가능한 템플릿 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="08130-118">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="08130-119">다음 표에는 .NET Core 2.0 SDK와 함께 사전 설치된 템플릿이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08130-119">The following table shows the templates that come pre-installed with the .NET Core 2.0 SDK.</span></span> <span data-ttu-id="08130-120">템플릿의 기본 언어는 대괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="08130-120">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="08130-121">템플릿 설명</span><span class="sxs-lookup"><span data-stu-id="08130-121">Template description</span></span>                          | <span data-ttu-id="08130-122">템플릿 이름</span><span class="sxs-lookup"><span data-stu-id="08130-122">Template name</span></span> | <span data-ttu-id="08130-123">언어</span><span class="sxs-lookup"><span data-stu-id="08130-123">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="08130-124">콘솔 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="08130-124">Console application</span></span>                          | `console`     | <span data-ttu-id="08130-125">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="08130-125">[C#], F#, VB</span></span>  |
| <span data-ttu-id="08130-126">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="08130-126">Class library</span></span>                                | `classlib`    | <span data-ttu-id="08130-127">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="08130-127">[C#], F#, VB</span></span>  |
| <span data-ttu-id="08130-128">단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="08130-128">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="08130-129">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="08130-129">[C#], F#, VB</span></span>  |
| <span data-ttu-id="08130-130">xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="08130-130">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="08130-131">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="08130-131">[C#], F#, VB</span></span>  |
| <span data-ttu-id="08130-132">ASP.NET Core 비어 있음</span><span class="sxs-lookup"><span data-stu-id="08130-132">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="08130-133">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="08130-133">[C#], F#</span></span>      |
| <span data-ttu-id="08130-134">ASP.NET Core 웹앱(모델-뷰-컨트롤러)</span><span class="sxs-lookup"><span data-stu-id="08130-134">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="08130-135">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="08130-135">[C#], F#</span></span>      |
| <span data-ttu-id="08130-136">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="08130-136">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="08130-137">[C#]</span><span class="sxs-lookup"><span data-stu-id="08130-137">[C#]</span></span>          |
| <span data-ttu-id="08130-138">ASP.NET Core(Angular 사용)</span><span class="sxs-lookup"><span data-stu-id="08130-138">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="08130-139">[C#]</span><span class="sxs-lookup"><span data-stu-id="08130-139">[C#]</span></span>          |
| <span data-ttu-id="08130-140">ASP.NET Core(React.js 사용)</span><span class="sxs-lookup"><span data-stu-id="08130-140">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="08130-141">[C#]</span><span class="sxs-lookup"><span data-stu-id="08130-141">[C#]</span></span>          |
| <span data-ttu-id="08130-142">ASP.NET Core(React.js 및 Redux 사용)</span><span class="sxs-lookup"><span data-stu-id="08130-142">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="08130-143">[C#]</span><span class="sxs-lookup"><span data-stu-id="08130-143">[C#]</span></span>          |
| <span data-ttu-id="08130-144">ASP.NET Core 웹 API</span><span class="sxs-lookup"><span data-stu-id="08130-144">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="08130-145">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="08130-145">[C#], F#</span></span>      |
| <span data-ttu-id="08130-146">global.json 파일</span><span class="sxs-lookup"><span data-stu-id="08130-146">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="08130-147">Nuget 구성</span><span class="sxs-lookup"><span data-stu-id="08130-147">Nuget config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="08130-148">웹 구성</span><span class="sxs-lookup"><span data-stu-id="08130-148">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="08130-149">솔루션 파일</span><span class="sxs-lookup"><span data-stu-id="08130-149">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="08130-150">Razor 페이지</span><span class="sxs-lookup"><span data-stu-id="08130-150">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="08130-151">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="08130-151">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="08130-152">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="08130-152">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="08130-153">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="08130-153">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="08130-154">명령에는 템플릿의 기본 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08130-154">The command contains a default list of templates.</span></span> <span data-ttu-id="08130-155">`dotnet new -all`을 사용하여 사용 가능한 템플릿 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="08130-155">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="08130-156">다음 표에는 .NET Core 1.x SDK와 함께 사전 설치된 템플릿이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08130-156">The following table shows the templates that come pre-installed with the .NET Core 1.x SDK.</span></span> <span data-ttu-id="08130-157">템플릿의 기본 언어는 대괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="08130-157">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="08130-158">템플릿 설명</span><span class="sxs-lookup"><span data-stu-id="08130-158">Template description</span></span>  | <span data-ttu-id="08130-159">템플릿 이름</span><span class="sxs-lookup"><span data-stu-id="08130-159">Template name</span></span> | <span data-ttu-id="08130-160">언어</span><span class="sxs-lookup"><span data-stu-id="08130-160">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="08130-161">콘솔 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="08130-161">Console application</span></span>  | `console`     | <span data-ttu-id="08130-162">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="08130-162">[C#], F#</span></span>  |
| <span data-ttu-id="08130-163">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="08130-163">Class library</span></span>        | `classlib`    | <span data-ttu-id="08130-164">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="08130-164">[C#], F#</span></span>  |
| <span data-ttu-id="08130-165">단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="08130-165">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="08130-166">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="08130-166">[C#], F#</span></span>  |
| <span data-ttu-id="08130-167">xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="08130-167">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="08130-168">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="08130-168">[C#], F#</span></span>  |
| <span data-ttu-id="08130-169">ASP.NET Core 비어 있음</span><span class="sxs-lookup"><span data-stu-id="08130-169">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="08130-170">[C#]</span><span class="sxs-lookup"><span data-stu-id="08130-170">[C#]</span></span>      |
| <span data-ttu-id="08130-171">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="08130-171">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="08130-172">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="08130-172">[C#], F#</span></span>  |
| <span data-ttu-id="08130-173">ASP.NET Core 웹 API</span><span class="sxs-lookup"><span data-stu-id="08130-173">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="08130-174">[C#]</span><span class="sxs-lookup"><span data-stu-id="08130-174">[C#]</span></span>      |
| <span data-ttu-id="08130-175">Nuget 구성</span><span class="sxs-lookup"><span data-stu-id="08130-175">Nuget config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="08130-176">웹 구성</span><span class="sxs-lookup"><span data-stu-id="08130-176">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="08130-177">솔루션 파일</span><span class="sxs-lookup"><span data-stu-id="08130-177">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="08130-178">옵션</span><span class="sxs-lookup"><span data-stu-id="08130-178">Options</span></span>

# <a name="net-core-20tabnetcore2x"></a>[<span data-ttu-id="08130-179">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="08130-179">.NET Core 2.0</span></span>](#tab/netcore2x)

`--force`

<span data-ttu-id="08130-180">기존 파일을 변경할 경우에도 콘텐츠를 강제 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-180">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="08130-181">출력 디렉터리에 이미 프로젝트가 포함되어 있는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-181">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="08130-182">명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-182">Prints out help for the command.</span></span> <span data-ttu-id="08130-183">`dotnet new` 명령 자체 또는 `dotnet new mvc --help` 같은 템플릿에 대해 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08130-183">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="08130-184">제공된 `PATH` 또는 `NUGET_ID`에서 소스 또는 템플릿 팩을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-184">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="08130-185">시험판 버전의 템플릿 패키지를 설치하려면 버전을 `<package-name>::<package-version>` 형식으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-185">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="08130-186">기본적으로 `dotnet new`는 마지막 안정 패키지 버전을 나타내는 버전에 대해 \*를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-186">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="08130-187">[예제](#examples) 섹션의 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08130-187">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="08130-188">사용자 지정 템플릿을 만드는 방법에 대한 자세한 내용은 [dotnet new에 대한 사용자 지정 템플릿](custom-templates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08130-188">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="08130-189">지정된 이름을 포함하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-189">Lists templates containing the specified name.</span></span> <span data-ttu-id="08130-190">`dotnet new` 명령에 대해 호출되는 경우 지정된 디렉터리에서 사용 가능한 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-190">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="08130-191">예를 들어 디렉터리에 이미 프로젝트가 포함되어 있는 경우 일부 프로젝트 템플릿을 나열하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08130-191">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="08130-192">만들 템플릿의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-192">The language of the template to create.</span></span> <span data-ttu-id="08130-193">허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조).</span><span class="sxs-lookup"><span data-stu-id="08130-193">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="08130-194">일부 템플릿의 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08130-194">Not valid for some templates.</span></span>

    > [!NOTE]
    > Some shells interpret `#` as a special character. In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="08130-195">생성된 출력에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-195">The name for the created output.</span></span> <span data-ttu-id="08130-196">이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="08130-196">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="08130-197">생성된 출력을 배치할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-197">Location to place the generated output.</span></span> <span data-ttu-id="08130-198">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-198">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="08130-199">사용 가능한 형식에 따라 템플릿을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-199">Filters templates based on available types.</span></span> <span data-ttu-id="08130-200">미리 정의된 값은 “project”, “item” 또는 “other”입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-200">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="08130-201">제공된 `PATH` 또는 `NUGET_ID`에서 소스 또는 템플릿 팩을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-201">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="08130-202">`PATH`를 사용하여 템플릿을 제거하려면 경로를 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-202">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="08130-203">예를 들어 *C:/Users/\<사용자>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지만 상위 폴더의 *./GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08130-203">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="08130-204">마지막의 종료하는 디렉터리 슬래시도 템플릿 경로에 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="08130-204">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="08130-205">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="08130-205">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="08130-206">`dotnet new` 명령의 컨텍스트에서만 실행되는 경우 특정 유형의 프로젝트에 대한 모든 템플릿을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-206">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="08130-207">`dotnet new web -all`처럼 특정 템플릿의 컨텍스트에서 실행되는 경우 `-all`은 강제 생성 플래그로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="08130-207">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="08130-208">출력 디렉터리에 이미 프로젝트가 포함되어 있는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-208">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="08130-209">명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-209">Prints out help for the command.</span></span> <span data-ttu-id="08130-210">`dotnet new` 명령 자체 또는 `dotnet new mvc --help` 같은 템플릿에 대해 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08130-210">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="08130-211">지정된 이름을 포함하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-211">Lists templates containing the specified name.</span></span> <span data-ttu-id="08130-212">`dotnet new` 명령에 대해 호출되는 경우 지정된 디렉터리에서 사용 가능한 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-212">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="08130-213">예를 들어 디렉터리에 이미 프로젝트가 포함되어 있는 경우 일부 프로젝트 템플릿을 나열하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08130-213">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="08130-214">만들 템플릿의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-214">The language of the template to create.</span></span> <span data-ttu-id="08130-215">허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조).</span><span class="sxs-lookup"><span data-stu-id="08130-215">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="08130-216">일부 템플릿의 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08130-216">Not valid for some templates.</span></span>

    > [!NOTE]
    > Some shells interpret `#` as a special character. In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="08130-217">생성된 출력에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-217">The name for the created output.</span></span> <span data-ttu-id="08130-218">이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="08130-218">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="08130-219">생성된 출력을 배치할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-219">Location to place the generated output.</span></span> <span data-ttu-id="08130-220">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-220">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="08130-221">템플릿 옵션</span><span class="sxs-lookup"><span data-stu-id="08130-221">Template options</span></span>

<span data-ttu-id="08130-222">각 프로젝트 템플릿에는 사용할 수 있는 추가 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08130-222">Each project template may have additional options available.</span></span> <span data-ttu-id="08130-223">코어 템플릿에는 다음과 같은 추가 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08130-223">The core templates have the following additional options:</span></span>

# <a name="net-core-20tabnetcore2x"></a>[<span data-ttu-id="08130-224">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="08130-224">.NET Core 2.0</span></span>](#tab/netcore2x)

<span data-ttu-id="08130-225">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="08130-225">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="08130-226">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08130-226">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="08130-227">**classlib**</span><span class="sxs-lookup"><span data-stu-id="08130-227">**classlib**</span></span>

<span data-ttu-id="08130-228">`-f|--framework <FRAMEWORK>` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-228">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="08130-229">값: `netcoreapp2.0`(.NET Core 클래스 라이브러리를 만드는 경우) 또는 `netstandard2.0`(.NET Standard 클래스 라이브러리를 만드는 경우).</span><span class="sxs-lookup"><span data-stu-id="08130-229">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="08130-230">기본값은 `netstandard2.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-230">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="08130-231">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08130-231">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="08130-232">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="08130-232">**mstest, xunit**</span></span>

<span data-ttu-id="08130-233">`-p|--enable-pack` - [dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-233">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="08130-234">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08130-234">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="08130-235">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="08130-235">**globaljson**</span></span>

<span data-ttu-id="08130-236">`--sdk-version <VERSION_NUMBER>` - *global.json* 파일에서 사용할 .NET Core SDK 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-236">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="08130-237">**web**</span><span class="sxs-lookup"><span data-stu-id="08130-237">**web**</span></span>

<span data-ttu-id="08130-238">`--use-launch-settings` - 생성된 템플릿 출력에 *launchSettings.json*을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-238">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="08130-239">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08130-239">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="08130-240">**webapi**</span><span class="sxs-lookup"><span data-stu-id="08130-240">**webapi**</span></span>

<span data-ttu-id="08130-241">`-au|--auth <AUTHENTICATION_TYPE>` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-241">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="08130-242">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="08130-242">The possible values are:</span></span>

- <span data-ttu-id="08130-243">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="08130-243">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="08130-244">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-244">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="08130-245">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-245">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="08130-246">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-246">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="08130-247">`--aad-b2c-instance <INSTANCE>` - 연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-247">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="08130-248">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-248">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="08130-249">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-249">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="08130-250">`-ssp|--susi-policy-id <ID>` - 이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-250">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="08130-251">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-251">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="08130-252">`--aad-instance <INSTANCE>` - 연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-252">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="08130-253">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-253">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="08130-254">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-254">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="08130-255">`--client-id <ID>` - 이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-255">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="08130-256">`IndividualB2C` 또는 `SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-256">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="08130-257">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-257">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="08130-258">`--domain <DOMAIN>` - 디렉터리 테넌트에 대한 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-258">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="08130-259">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-259">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="08130-260">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-260">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="08130-261">`--tenant-id <ID>` - 연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-261">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="08130-262">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-262">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="08130-263">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-263">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="08130-264">`-r|--org-read-access` - 디렉터리에 대한 이 응용 프로그램 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-264">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="08130-265">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="08130-265">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="08130-266">`--use-launch-settings` - 생성된 템플릿 출력에 *launchSettings.json*을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-266">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="08130-267">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-267">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="08130-268">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="08130-268">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="08130-269">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08130-269">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="08130-270">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="08130-270">**mvc, razor**</span></span>

<span data-ttu-id="08130-271">`-au|--auth <AUTHENTICATION_TYPE>` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-271">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="08130-272">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="08130-272">The possible values are:</span></span>

- <span data-ttu-id="08130-273">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="08130-273">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="08130-274">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-274">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="08130-275">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-275">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="08130-276">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-276">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="08130-277">`MultiOrg` - 여러 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-277">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="08130-278">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-278">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="08130-279">`--aad-b2c-instance <INSTANCE>` - 연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-279">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="08130-280">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-280">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="08130-281">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-281">The default value is `https://login.microsoftonline.com/tfp/` .</span></span>

<span data-ttu-id="08130-282">`-ssp|--susi-policy-id <ID>` - 이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-282">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="08130-283">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-283">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="08130-284">`-rp|--reset-password-policy-id <ID>` - 이 프로젝트에 대한 암호 재설정 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-284">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="08130-285">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-285">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="08130-286">`-ep|--edit-profile-policy-id <ID>` - 이 프로젝트에 대한 프로필 편집 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-286">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="08130-287">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-287">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="08130-288">`--aad-instance <INSTANCE>` - 연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-288">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="08130-289">`SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-289">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="08130-290">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-290">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="08130-291">`--client-id <ID>` - 이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-291">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="08130-292">`IndividualB2C`, `SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-292">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="08130-293">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-293">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="08130-294">`--domain <DOMAIN>` - 디렉터리 테넌트에 대한 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-294">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="08130-295">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-295">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="08130-296">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-296">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="08130-297">`--tenant-id <ID>` - 연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-297">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="08130-298">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-298">Use with `SingleOrg` authentication..</span></span> <span data-ttu-id="08130-299">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-299">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="08130-300">`--callback-path <PATH>` - 리디렉션 URI의 응용 프로그램 기본 경로 내 요청 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-300">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="08130-301">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-301">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="08130-302">기본값은 `/signin-oidc`입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-302">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="08130-303">`-r|--org-read-access` - 디렉터리에 대한 이 응용 프로그램 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-303">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="08130-304">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="08130-304">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="08130-305">`--use-launch-settings` - 생성된 템플릿 출력에 *launchSettings.json*을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-305">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="08130-306">`--use-browserlink` - 프로젝트에 BrowserLink를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-306">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="08130-307">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-307">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="08130-308">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="08130-308">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="08130-309">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08130-309">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="08130-310">**page**</span><span class="sxs-lookup"><span data-stu-id="08130-310">**page**</span></span>

<span data-ttu-id="08130-311">`-na|--namespace <NAMESPACE_NAME>` - 생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-311">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="08130-312">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-312">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="08130-313">`-np|--no-pagemodel` - PageModel 없이 페이지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="08130-313">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="08130-314">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="08130-314">**viewimports**</span></span>

<span data-ttu-id="08130-315">`-na|--namespace <NAMESPACE_NAME>` - 생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-315">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="08130-316">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-316">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="08130-317">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="08130-317">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="08130-318">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="08130-318">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="08130-319">`-f|--framework` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-319">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="08130-320">값: `netcoreapp1.0` 또는 `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="08130-320">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="08130-321">기본값은 `netcoreapp1.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-321">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="08130-322">**classlib**</span><span class="sxs-lookup"><span data-stu-id="08130-322">**classlib**</span></span>

<span data-ttu-id="08130-323">`-f|--framework` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-323">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="08130-324">값: `netcoreapp1.0`, `netcoreapp1.1` 또는 `netstandard1.0`~`netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="08130-324">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="08130-325">기본값은 `netstandard1.4`입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-325">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="08130-326">**mvc**</span><span class="sxs-lookup"><span data-stu-id="08130-326">**mvc**</span></span>

<span data-ttu-id="08130-327">`-f|--framework` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-327">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="08130-328">값: `netcoreapp1.0` 또는 `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="08130-328">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="08130-329">기본값은 `netcoreapp1.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-329">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="08130-330">`-au|--auth` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-330">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="08130-331">값: `None` 또는 `Individual`.</span><span class="sxs-lookup"><span data-stu-id="08130-331">Values: `None` or `Individual`.</span></span> <span data-ttu-id="08130-332">기본값은 `None`입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-332">The default value is `None`.</span></span>

<span data-ttu-id="08130-333">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-333">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="08130-334">값: `true` 또는 `false`.</span><span class="sxs-lookup"><span data-stu-id="08130-334">Values: `true` or `false`.</span></span> <span data-ttu-id="08130-335">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="08130-335">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="08130-336">예제</span><span class="sxs-lookup"><span data-stu-id="08130-336">Examples</span></span>

<span data-ttu-id="08130-337">현재 디렉터리에 F# 콘솔 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="08130-337">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="08130-338">지정된 디렉터리에서 .NET Standard 클래스 라이브러리 프로젝트를 만듭니다(.NET Core 2.0 SDK 이상 버전에서만 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="08130-338">Create a .NET Standard class library project in the specified directory (available only with .NET Core 2.0 SDK or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="08130-339">.NET Core 2.0을 대상으로 인증 없이 현재 디렉터리에 새 ASP.NET Core C# MVC 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="08130-339">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 2.0:</span></span>

`dotnet new mvc -au None -f netcoreapp2.0`

<span data-ttu-id="08130-340">.NET Core 2.0을 대상으로 새 xUnit 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="08130-340">Create a new xUnit application targeting .NET Core 2.0:</span></span>

`dotnet new xunit --framework netcoreapp2.0`

<span data-ttu-id="08130-341">MVC에 대해 사용할 수 있는 모든 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="08130-341">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="08130-342">ASP.NET Core용 단일 페이지 응용 프로그램 템플릿 버전 2.0을 설치합니다(.NET Core SDK 1.1 및 이후 버전에서만 사용할 수 있는 명령 옵션).</span><span class="sxs-lookup"><span data-stu-id="08130-342">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

## <a name="see-also"></a><span data-ttu-id="08130-343">참고 항목</span><span class="sxs-lookup"><span data-stu-id="08130-343">See also</span></span>

[<span data-ttu-id="08130-344">dotnet new에 대한 사용자 지정 템플릿</span><span class="sxs-lookup"><span data-stu-id="08130-344">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="08130-345">dotnet용 사용자 지정 템플릿 새로 만들기</span><span class="sxs-lookup"><span data-stu-id="08130-345">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
<span data-ttu-id="08130-346">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)(dotnet/dotnet-template-samples GitHub 리포지토리)</span><span class="sxs-lookup"><span data-stu-id="08130-346">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)</span></span>  
<span data-ttu-id="08130-347">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)(dotnet new에 대한 사용 가능한 템플릿)</span><span class="sxs-lookup"><span data-stu-id="08130-347">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
