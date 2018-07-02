---
title: dotnet new 명령 - .NET Core CLI
description: dotnet new 명령은 지정된 템플릿을 기반으로 새 .NET Core 프로젝트를 만듭니다.
author: mairaw
ms.author: mairaw
ms.date: 06/12/2018
ms.openlocfilehash: f0ef91361dfbc2c2ba5532fbd607786289e98c69
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207784"
---
# <a name="dotnet-new"></a><span data-ttu-id="b90ff-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="b90ff-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="b90ff-104">name</span><span class="sxs-lookup"><span data-stu-id="b90ff-104">Name</span></span>

<span data-ttu-id="b90ff-105">`dotnet new` - 지정된 템플릿을 기반으로 새 프로젝트, 구성 파일 또는 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b90ff-106">개요</span><span class="sxs-lookup"><span data-stu-id="b90ff-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="b90ff-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b90ff-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="b90ff-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="b90ff-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b90ff-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b90ff-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="b90ff-110">설명</span><span class="sxs-lookup"><span data-stu-id="b90ff-110">Description</span></span>

<span data-ttu-id="b90ff-111">`dotnet new` 명령은 유효한 .NET Core 프로젝트를 초기화하는 편리한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="b90ff-112">이 명령은 [템플릿 엔진](https://github.com/dotnet/templating)을 호출하여 지정된 템플릿 및 옵션을 기반으로 디스크에 아티팩트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="b90ff-113">인수</span><span class="sxs-lookup"><span data-stu-id="b90ff-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="b90ff-114">명령이 호출될 때 인스턴스화할 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="b90ff-115">각 템플릿에는 전달할 수 있는 특정 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="b90ff-116">자세한 내용은 [템플릿 옵션](#template-options)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b90ff-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="b90ff-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b90ff-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="b90ff-118">명령에는 템플릿의 기본 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-118">The command contains a default list of templates.</span></span> <span data-ttu-id="b90ff-119">`dotnet new -l`을 사용하여 사용 가능한 템플릿 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="b90ff-120">다음 표에는 .NET Core SDK 2.1.300과 함께 사전 설치된 템플릿이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="b90ff-121">템플릿의 기본 언어는 대괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="b90ff-122">템플릿 설명</span><span class="sxs-lookup"><span data-stu-id="b90ff-122">Template description</span></span>                          | <span data-ttu-id="b90ff-123">템플릿 이름</span><span class="sxs-lookup"><span data-stu-id="b90ff-123">Template name</span></span>   | <span data-ttu-id="b90ff-124">언어</span><span class="sxs-lookup"><span data-stu-id="b90ff-124">Languages</span></span>     |
|----------------------------------------------|-----------------|---------------|
| <span data-ttu-id="b90ff-125">콘솔 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="b90ff-125">Console application</span></span>                          | `console`       | <span data-ttu-id="b90ff-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b90ff-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="b90ff-127">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="b90ff-127">Class library</span></span>                                | `classlib`      | <span data-ttu-id="b90ff-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b90ff-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="b90ff-129">단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="b90ff-129">Unit test project</span></span>                            | `mstest`        | <span data-ttu-id="b90ff-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b90ff-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="b90ff-131">xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="b90ff-131">xUnit test project</span></span>                           | `xunit`         | <span data-ttu-id="b90ff-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b90ff-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="b90ff-133">Razor 페이지</span><span class="sxs-lookup"><span data-stu-id="b90ff-133">Razor page</span></span>                                   | `page`          | <span data-ttu-id="b90ff-134">[C#]</span><span class="sxs-lookup"><span data-stu-id="b90ff-134">[C#]</span></span>          |
| <span data-ttu-id="b90ff-135">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="b90ff-135">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="b90ff-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="b90ff-136">[C#]</span></span>          |
| <span data-ttu-id="b90ff-137">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="b90ff-137">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="b90ff-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="b90ff-138">[C#]</span></span>          |
| <span data-ttu-id="b90ff-139">ASP.NET Core 비어 있음</span><span class="sxs-lookup"><span data-stu-id="b90ff-139">ASP.NET Core empty</span></span>                           | `web`           | <span data-ttu-id="b90ff-140">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b90ff-140">[C#], F#</span></span>      |
| <span data-ttu-id="b90ff-141">ASP.NET Core 웹앱(모델-뷰-컨트롤러)</span><span class="sxs-lookup"><span data-stu-id="b90ff-141">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="b90ff-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b90ff-142">[C#], F#</span></span>      |
| <span data-ttu-id="b90ff-143">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="b90ff-143">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="b90ff-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="b90ff-144">[C#]</span></span>          |
| <span data-ttu-id="b90ff-145">ASP.NET Core(Angular 사용)</span><span class="sxs-lookup"><span data-stu-id="b90ff-145">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="b90ff-146">[C#]</span><span class="sxs-lookup"><span data-stu-id="b90ff-146">[C#]</span></span>          |
| <span data-ttu-id="b90ff-147">ASP.NET Core(React.js 사용)</span><span class="sxs-lookup"><span data-stu-id="b90ff-147">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="b90ff-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="b90ff-148">[C#]</span></span>          |
| <span data-ttu-id="b90ff-149">ASP.NET Core(React.js 및 Redux 사용)</span><span class="sxs-lookup"><span data-stu-id="b90ff-149">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="b90ff-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="b90ff-150">[C#]</span></span>          |
| <span data-ttu-id="b90ff-151">ASP.NET Core 웹 API</span><span class="sxs-lookup"><span data-stu-id="b90ff-151">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="b90ff-152">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b90ff-152">[C#], F#</span></span>      |
| <span data-ttu-id="b90ff-153">Razor 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="b90ff-153">Razor class library</span></span>                          | `razorclasslib` | <span data-ttu-id="b90ff-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="b90ff-154">[C#]</span></span>          |
| <span data-ttu-id="b90ff-155">global.json 파일</span><span class="sxs-lookup"><span data-stu-id="b90ff-155">global.json file</span></span>                             | `globaljson`    |               |
| <span data-ttu-id="b90ff-156">NuGet 구성</span><span class="sxs-lookup"><span data-stu-id="b90ff-156">NuGet config</span></span>                                 | `nugetconfig`   |               |
| <span data-ttu-id="b90ff-157">웹 구성</span><span class="sxs-lookup"><span data-stu-id="b90ff-157">Web config</span></span>                                   | `webconfig`     |               |
| <span data-ttu-id="b90ff-158">솔루션 파일</span><span class="sxs-lookup"><span data-stu-id="b90ff-158">Solution file</span></span>                                | `sln`           |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="b90ff-159">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="b90ff-159">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="b90ff-160">명령에는 템플릿의 기본 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-160">The command contains a default list of templates.</span></span> <span data-ttu-id="b90ff-161">`dotnet new -l`을 사용하여 사용 가능한 템플릿 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-161">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="b90ff-162">다음 표에는 .NET Core SDK 2.0과 함께 사전 설치된 템플릿이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-162">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="b90ff-163">템플릿의 기본 언어는 대괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-163">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="b90ff-164">템플릿 설명</span><span class="sxs-lookup"><span data-stu-id="b90ff-164">Template description</span></span>                          | <span data-ttu-id="b90ff-165">템플릿 이름</span><span class="sxs-lookup"><span data-stu-id="b90ff-165">Template name</span></span> | <span data-ttu-id="b90ff-166">언어</span><span class="sxs-lookup"><span data-stu-id="b90ff-166">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="b90ff-167">콘솔 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="b90ff-167">Console application</span></span>                          | `console`     | <span data-ttu-id="b90ff-168">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b90ff-168">[C#], F#, VB</span></span>  |
| <span data-ttu-id="b90ff-169">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="b90ff-169">Class library</span></span>                                | `classlib`    | <span data-ttu-id="b90ff-170">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b90ff-170">[C#], F#, VB</span></span>  |
| <span data-ttu-id="b90ff-171">단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="b90ff-171">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="b90ff-172">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b90ff-172">[C#], F#, VB</span></span>  |
| <span data-ttu-id="b90ff-173">xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="b90ff-173">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="b90ff-174">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b90ff-174">[C#], F#, VB</span></span>  |
| <span data-ttu-id="b90ff-175">ASP.NET Core 비어 있음</span><span class="sxs-lookup"><span data-stu-id="b90ff-175">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="b90ff-176">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b90ff-176">[C#], F#</span></span>      |
| <span data-ttu-id="b90ff-177">ASP.NET Core 웹앱(모델-뷰-컨트롤러)</span><span class="sxs-lookup"><span data-stu-id="b90ff-177">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="b90ff-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b90ff-178">[C#], F#</span></span>      |
| <span data-ttu-id="b90ff-179">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="b90ff-179">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="b90ff-180">[C#]</span><span class="sxs-lookup"><span data-stu-id="b90ff-180">[C#]</span></span>          |
| <span data-ttu-id="b90ff-181">ASP.NET Core(Angular 사용)</span><span class="sxs-lookup"><span data-stu-id="b90ff-181">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="b90ff-182">[C#]</span><span class="sxs-lookup"><span data-stu-id="b90ff-182">[C#]</span></span>          |
| <span data-ttu-id="b90ff-183">ASP.NET Core(React.js 사용)</span><span class="sxs-lookup"><span data-stu-id="b90ff-183">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="b90ff-184">[C#]</span><span class="sxs-lookup"><span data-stu-id="b90ff-184">[C#]</span></span>          |
| <span data-ttu-id="b90ff-185">ASP.NET Core(React.js 및 Redux 사용)</span><span class="sxs-lookup"><span data-stu-id="b90ff-185">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="b90ff-186">[C#]</span><span class="sxs-lookup"><span data-stu-id="b90ff-186">[C#]</span></span>          |
| <span data-ttu-id="b90ff-187">ASP.NET Core 웹 API</span><span class="sxs-lookup"><span data-stu-id="b90ff-187">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="b90ff-188">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b90ff-188">[C#], F#</span></span>      |
| <span data-ttu-id="b90ff-189">global.json 파일</span><span class="sxs-lookup"><span data-stu-id="b90ff-189">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="b90ff-190">NuGet 구성</span><span class="sxs-lookup"><span data-stu-id="b90ff-190">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="b90ff-191">웹 구성</span><span class="sxs-lookup"><span data-stu-id="b90ff-191">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="b90ff-192">솔루션 파일</span><span class="sxs-lookup"><span data-stu-id="b90ff-192">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="b90ff-193">Razor 페이지</span><span class="sxs-lookup"><span data-stu-id="b90ff-193">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="b90ff-194">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="b90ff-194">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="b90ff-195">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="b90ff-195">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b90ff-196">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b90ff-196">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="b90ff-197">명령에는 템플릿의 기본 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-197">The command contains a default list of templates.</span></span> <span data-ttu-id="b90ff-198">`dotnet new -all`을 사용하여 사용 가능한 템플릿 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-198">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="b90ff-199">다음 표에는 .NET Core SDK 1.x와 함께 사전 설치된 템플릿이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-199">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="b90ff-200">템플릿의 기본 언어는 대괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-200">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="b90ff-201">템플릿 설명</span><span class="sxs-lookup"><span data-stu-id="b90ff-201">Template description</span></span>  | <span data-ttu-id="b90ff-202">템플릿 이름</span><span class="sxs-lookup"><span data-stu-id="b90ff-202">Template name</span></span> | <span data-ttu-id="b90ff-203">언어</span><span class="sxs-lookup"><span data-stu-id="b90ff-203">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="b90ff-204">콘솔 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="b90ff-204">Console application</span></span>  | `console`     | <span data-ttu-id="b90ff-205">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b90ff-205">[C#], F#</span></span>  |
| <span data-ttu-id="b90ff-206">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="b90ff-206">Class library</span></span>        | `classlib`    | <span data-ttu-id="b90ff-207">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b90ff-207">[C#], F#</span></span>  |
| <span data-ttu-id="b90ff-208">단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="b90ff-208">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="b90ff-209">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b90ff-209">[C#], F#</span></span>  |
| <span data-ttu-id="b90ff-210">xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="b90ff-210">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="b90ff-211">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b90ff-211">[C#], F#</span></span>  |
| <span data-ttu-id="b90ff-212">ASP.NET Core 비어 있음</span><span class="sxs-lookup"><span data-stu-id="b90ff-212">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="b90ff-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="b90ff-213">[C#]</span></span>      |
| <span data-ttu-id="b90ff-214">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="b90ff-214">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="b90ff-215">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b90ff-215">[C#], F#</span></span>  |
| <span data-ttu-id="b90ff-216">ASP.NET Core 웹 API</span><span class="sxs-lookup"><span data-stu-id="b90ff-216">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="b90ff-217">[C#]</span><span class="sxs-lookup"><span data-stu-id="b90ff-217">[C#]</span></span>      |
| <span data-ttu-id="b90ff-218">NuGet 구성</span><span class="sxs-lookup"><span data-stu-id="b90ff-218">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="b90ff-219">웹 구성</span><span class="sxs-lookup"><span data-stu-id="b90ff-219">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="b90ff-220">솔루션 파일</span><span class="sxs-lookup"><span data-stu-id="b90ff-220">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="b90ff-221">옵션</span><span class="sxs-lookup"><span data-stu-id="b90ff-221">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="b90ff-222">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b90ff-222">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="b90ff-223">기존 파일을 변경할 경우에도 콘텐츠를 강제 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-223">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="b90ff-224">출력 디렉터리에 이미 프로젝트가 포함되어 있는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-224">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="b90ff-225">명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-225">Prints out help for the command.</span></span> <span data-ttu-id="b90ff-226">`dotnet new` 명령 자체 또는 `dotnet new mvc --help` 같은 템플릿에 대해 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-226">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="b90ff-227">제공된 `PATH` 또는 `NUGET_ID`에서 소스 또는 템플릿 팩을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-227">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="b90ff-228">시험판 버전의 템플릿 패키지를 설치하려면 버전을 `<package-name>::<package-version>` 형식으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-228">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="b90ff-229">기본적으로 `dotnet new`는 마지막 안정 패키지 버전을 나타내는 버전에 대해 \*를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-229">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="b90ff-230">[예제](#examples) 섹션의 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b90ff-230">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="b90ff-231">사용자 지정 템플릿을 만드는 방법에 대한 자세한 내용은 [dotnet new에 대한 사용자 지정 템플릿](custom-templates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b90ff-231">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="b90ff-232">지정된 이름을 포함하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-232">Lists templates containing the specified name.</span></span> <span data-ttu-id="b90ff-233">`dotnet new` 명령에 대해 호출되는 경우 지정된 디렉터리에서 사용 가능한 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-233">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="b90ff-234">예를 들어 디렉터리에 이미 프로젝트가 포함되어 있는 경우 일부 프로젝트 템플릿을 나열하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-234">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="b90ff-235">만들 템플릿의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-235">The language of the template to create.</span></span> <span data-ttu-id="b90ff-236">허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조).</span><span class="sxs-lookup"><span data-stu-id="b90ff-236">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="b90ff-237">일부 템플릿의 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-237">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="b90ff-238">일부 셸은 `#`을 특수 문자로 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-238">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="b90ff-239">이러한 경우 `dotnet new console -lang "F#"`과 같은 언어 매개 변수 값을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-239">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="b90ff-240">생성된 출력에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-240">The name for the created output.</span></span> <span data-ttu-id="b90ff-241">이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-241">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="b90ff-242">설치 중 사용할 NuGet 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-242">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="b90ff-243">생성된 출력을 배치할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-243">Location to place the generated output.</span></span> <span data-ttu-id="b90ff-244">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-244">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="b90ff-245">사용 가능한 형식에 따라 템플릿을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-245">Filters templates based on available types.</span></span> <span data-ttu-id="b90ff-246">미리 정의된 값은 “project”, “item” 또는 “other”입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-246">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="b90ff-247">제공된 `PATH` 또는 `NUGET_ID`에서 소스 또는 템플릿 팩을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-247">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="b90ff-248">`PATH`를 사용하여 템플릿을 제거하려면 경로를 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-248">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="b90ff-249">예를 들어 *C:/Users/\<사용자>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지만 상위 폴더의 *./GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-249">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="b90ff-250">마지막의 종료하는 디렉터리 슬래시도 템플릿 경로에 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="b90ff-250">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="b90ff-251">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="b90ff-251">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="b90ff-252">기존 파일을 변경할 경우에도 콘텐츠를 강제 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-252">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="b90ff-253">출력 디렉터리에 이미 프로젝트가 포함되어 있는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-253">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="b90ff-254">명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-254">Prints out help for the command.</span></span> <span data-ttu-id="b90ff-255">`dotnet new` 명령 자체 또는 `dotnet new mvc --help` 같은 템플릿에 대해 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-255">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="b90ff-256">제공된 `PATH` 또는 `NUGET_ID`에서 소스 또는 템플릿 팩을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-256">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="b90ff-257">시험판 버전의 템플릿 패키지를 설치하려면 버전을 `<package-name>::<package-version>` 형식으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-257">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="b90ff-258">기본적으로 `dotnet new`는 마지막 안정 패키지 버전을 나타내는 버전에 대해 \*를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-258">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="b90ff-259">[예제](#examples) 섹션의 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b90ff-259">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="b90ff-260">사용자 지정 템플릿을 만드는 방법에 대한 자세한 내용은 [dotnet new에 대한 사용자 지정 템플릿](custom-templates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b90ff-260">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="b90ff-261">지정된 이름을 포함하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-261">Lists templates containing the specified name.</span></span> <span data-ttu-id="b90ff-262">`dotnet new` 명령에 대해 호출되는 경우 지정된 디렉터리에서 사용 가능한 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-262">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="b90ff-263">예를 들어 디렉터리에 이미 프로젝트가 포함되어 있는 경우 일부 프로젝트 템플릿을 나열하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-263">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="b90ff-264">만들 템플릿의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-264">The language of the template to create.</span></span> <span data-ttu-id="b90ff-265">허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조).</span><span class="sxs-lookup"><span data-stu-id="b90ff-265">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="b90ff-266">일부 템플릿의 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-266">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="b90ff-267">일부 셸은 `#`을 특수 문자로 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-267">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="b90ff-268">이러한 경우 `dotnet new console -lang "F#"`과 같은 언어 매개 변수 값을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-268">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="b90ff-269">생성된 출력에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-269">The name for the created output.</span></span> <span data-ttu-id="b90ff-270">이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-270">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="b90ff-271">생성된 출력을 배치할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-271">Location to place the generated output.</span></span> <span data-ttu-id="b90ff-272">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-272">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="b90ff-273">사용 가능한 형식에 따라 템플릿을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-273">Filters templates based on available types.</span></span> <span data-ttu-id="b90ff-274">미리 정의된 값은 “project”, “item” 또는 “other”입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-274">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="b90ff-275">제공된 `PATH` 또는 `NUGET_ID`에서 소스 또는 템플릿 팩을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-275">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="b90ff-276">`PATH`를 사용하여 템플릿을 제거하려면 경로를 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-276">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="b90ff-277">예를 들어 *C:/Users/\<사용자>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지만 상위 폴더의 *./GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-277">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="b90ff-278">마지막의 종료하는 디렉터리 슬래시도 템플릿 경로에 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="b90ff-278">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b90ff-279">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b90ff-279">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="b90ff-280">`dotnet new` 명령의 컨텍스트에서만 실행되는 경우 특정 유형의 프로젝트에 대한 모든 템플릿을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-280">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="b90ff-281">`dotnet new web -all`처럼 특정 템플릿의 컨텍스트에서 실행되는 경우 `-all`은 강제 생성 플래그로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-281">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="b90ff-282">출력 디렉터리에 이미 프로젝트가 포함되어 있는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-282">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="b90ff-283">명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-283">Prints out help for the command.</span></span> <span data-ttu-id="b90ff-284">`dotnet new` 명령 자체 또는 `dotnet new mvc --help` 같은 템플릿에 대해 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-284">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="b90ff-285">지정된 이름을 포함하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-285">Lists templates containing the specified name.</span></span> <span data-ttu-id="b90ff-286">`dotnet new` 명령에 대해 호출되는 경우 지정된 디렉터리에서 사용 가능한 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-286">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="b90ff-287">예를 들어 디렉터리에 이미 프로젝트가 포함되어 있는 경우 일부 프로젝트 템플릿을 나열하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-287">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="b90ff-288">만들 템플릿의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-288">The language of the template to create.</span></span> <span data-ttu-id="b90ff-289">허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조).</span><span class="sxs-lookup"><span data-stu-id="b90ff-289">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="b90ff-290">일부 템플릿의 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-290">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="b90ff-291">일부 셸은 `#`을 특수 문자로 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-291">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="b90ff-292">이러한 경우 `dotnet new console -lang "F#"`과 같은 언어 매개 변수 값을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-292">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="b90ff-293">생성된 출력에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-293">The name for the created output.</span></span> <span data-ttu-id="b90ff-294">이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-294">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="b90ff-295">생성된 출력을 배치할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-295">Location to place the generated output.</span></span> <span data-ttu-id="b90ff-296">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-296">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="b90ff-297">템플릿 옵션</span><span class="sxs-lookup"><span data-stu-id="b90ff-297">Template options</span></span>

<span data-ttu-id="b90ff-298">각 프로젝트 템플릿에는 사용할 수 있는 추가 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-298">Each project template may have additional options available.</span></span> <span data-ttu-id="b90ff-299">코어 템플릿에는 다음과 같은 추가 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-299">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="b90ff-300">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b90ff-300">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="b90ff-301">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="b90ff-301">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="b90ff-302">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-302">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b90ff-303">**classlib**</span><span class="sxs-lookup"><span data-stu-id="b90ff-303">**classlib**</span></span>

<span data-ttu-id="b90ff-304">`-f|--framework <FRAMEWORK>` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-304">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b90ff-305">값: `netcoreapp2.0`(.NET Core 클래스 라이브러리를 만드는 경우) 또는 `netstandard2.0`(.NET Standard 클래스 라이브러리를 만드는 경우).</span><span class="sxs-lookup"><span data-stu-id="b90ff-305">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="b90ff-306">기본값은 `netstandard2.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-306">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="b90ff-307">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-307">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b90ff-308">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="b90ff-308">**mstest, xunit**</span></span>

<span data-ttu-id="b90ff-309">`-p|--enable-pack` - [dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-309">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="b90ff-310">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-310">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b90ff-311">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="b90ff-311">**globaljson**</span></span>

<span data-ttu-id="b90ff-312">`--sdk-version <VERSION_NUMBER>` - *global.json* 파일에서 사용할 .NET Core SDK 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-312">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="b90ff-313">**web**</span><span class="sxs-lookup"><span data-stu-id="b90ff-313">**web**</span></span>

<span data-ttu-id="b90ff-314">`--use-launch-settings` - 생성된 템플릿 출력에 *launchSettings.json*을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-314">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="b90ff-315">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-315">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b90ff-316">**webapi**</span><span class="sxs-lookup"><span data-stu-id="b90ff-316">**webapi**</span></span>

<span data-ttu-id="b90ff-317">`-au|--auth <AUTHENTICATION_TYPE>` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-317">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="b90ff-318">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-318">The possible values are:</span></span>

- <span data-ttu-id="b90ff-319">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="b90ff-319">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="b90ff-320">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-320">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="b90ff-321">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-321">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="b90ff-322">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-322">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="b90ff-323">`--aad-b2c-instance <INSTANCE>` - 연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-323">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="b90ff-324">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-324">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="b90ff-325">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-325">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="b90ff-326">`-ssp|--susi-policy-id <ID>` - 이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-326">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="b90ff-327">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-327">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b90ff-328">`--aad-instance <INSTANCE>` - 연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-328">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="b90ff-329">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-329">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b90ff-330">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-330">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="b90ff-331">`--client-id <ID>` - 이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-331">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="b90ff-332">`IndividualB2C` 또는 `SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-332">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="b90ff-333">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-333">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="b90ff-334">`--domain <DOMAIN>` - 디렉터리 테넌트에 대한 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-334">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="b90ff-335">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-335">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b90ff-336">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-336">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="b90ff-337">`--tenant-id <ID>` - 연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-337">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="b90ff-338">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-338">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b90ff-339">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-339">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="b90ff-340">`-r|--org-read-access` - 디렉터리에 대한 이 응용 프로그램 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-340">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="b90ff-341">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-341">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="b90ff-342">`--use-launch-settings` - 생성된 템플릿 출력에 *launchSettings.json*을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-342">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="b90ff-343">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-343">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="b90ff-344">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-344">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b90ff-345">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-345">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b90ff-346">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="b90ff-346">**mvc, razor**</span></span>

<span data-ttu-id="b90ff-347">`-au|--auth <AUTHENTICATION_TYPE>` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-347">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="b90ff-348">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-348">The possible values are:</span></span>

- <span data-ttu-id="b90ff-349">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="b90ff-349">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="b90ff-350">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-350">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="b90ff-351">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-351">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="b90ff-352">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-352">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="b90ff-353">`MultiOrg` - 여러 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-353">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="b90ff-354">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-354">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="b90ff-355">`--aad-b2c-instance <INSTANCE>` - 연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-355">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="b90ff-356">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-356">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="b90ff-357">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-357">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="b90ff-358">`-ssp|--susi-policy-id <ID>` - 이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-358">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="b90ff-359">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-359">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b90ff-360">`-rp|--reset-password-policy-id <ID>` - 이 프로젝트에 대한 암호 재설정 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-360">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="b90ff-361">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-361">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b90ff-362">`-ep|--edit-profile-policy-id <ID>` - 이 프로젝트에 대한 프로필 편집 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-362">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="b90ff-363">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-363">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b90ff-364">`--aad-instance <INSTANCE>` - 연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-364">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="b90ff-365">`SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-365">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="b90ff-366">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-366">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="b90ff-367">`--client-id <ID>` - 이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-367">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="b90ff-368">`IndividualB2C`, `SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-368">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="b90ff-369">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-369">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="b90ff-370">`--domain <DOMAIN>` - 디렉터리 테넌트에 대한 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-370">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="b90ff-371">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-371">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b90ff-372">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-372">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="b90ff-373">`--tenant-id <ID>` - 연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-373">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="b90ff-374">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-374">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b90ff-375">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-375">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="b90ff-376">`--callback-path <PATH>` - 리디렉션 URI의 응용 프로그램 기본 경로 내 요청 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-376">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="b90ff-377">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-377">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b90ff-378">기본값은 `/signin-oidc`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-378">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="b90ff-379">`-r|--org-read-access` - 디렉터리에 대한 이 응용 프로그램 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-379">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="b90ff-380">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-380">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="b90ff-381">`--use-launch-settings` - 생성된 템플릿 출력에 *launchSettings.json*을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-381">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="b90ff-382">`--use-browserlink` - 프로젝트에 BrowserLink를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-382">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="b90ff-383">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-383">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="b90ff-384">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-384">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b90ff-385">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-385">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b90ff-386">**page**</span><span class="sxs-lookup"><span data-stu-id="b90ff-386">**page**</span></span>

<span data-ttu-id="b90ff-387">`-na|--namespace <NAMESPACE_NAME>` - 생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-387">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="b90ff-388">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-388">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="b90ff-389">`-np|--no-pagemodel` - PageModel 없이 페이지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-389">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="b90ff-390">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="b90ff-390">**viewimports**</span></span>

<span data-ttu-id="b90ff-391">`-na|--namespace <NAMESPACE_NAME>` - 생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-391">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="b90ff-392">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-392">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="b90ff-393">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="b90ff-393">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="b90ff-394">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="b90ff-394">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="b90ff-395">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-395">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b90ff-396">**classlib**</span><span class="sxs-lookup"><span data-stu-id="b90ff-396">**classlib**</span></span>

<span data-ttu-id="b90ff-397">`-f|--framework <FRAMEWORK>` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-397">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b90ff-398">값: `netcoreapp2.0`(.NET Core 클래스 라이브러리를 만드는 경우) 또는 `netstandard2.0`(.NET Standard 클래스 라이브러리를 만드는 경우).</span><span class="sxs-lookup"><span data-stu-id="b90ff-398">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="b90ff-399">기본값은 `netstandard2.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-399">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="b90ff-400">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-400">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b90ff-401">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="b90ff-401">**mstest, xunit**</span></span>

<span data-ttu-id="b90ff-402">`-p|--enable-pack` - [dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-402">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="b90ff-403">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-403">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b90ff-404">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="b90ff-404">**globaljson**</span></span>

<span data-ttu-id="b90ff-405">`--sdk-version <VERSION_NUMBER>` - *global.json* 파일에서 사용할 .NET Core SDK 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-405">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="b90ff-406">**web**</span><span class="sxs-lookup"><span data-stu-id="b90ff-406">**web**</span></span>

<span data-ttu-id="b90ff-407">`--use-launch-settings` - 생성된 템플릿 출력에 *launchSettings.json*을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-407">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="b90ff-408">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-408">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b90ff-409">**webapi**</span><span class="sxs-lookup"><span data-stu-id="b90ff-409">**webapi**</span></span>

<span data-ttu-id="b90ff-410">`-au|--auth <AUTHENTICATION_TYPE>` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-410">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="b90ff-411">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-411">The possible values are:</span></span>

- <span data-ttu-id="b90ff-412">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="b90ff-412">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="b90ff-413">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-413">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="b90ff-414">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-414">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="b90ff-415">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-415">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="b90ff-416">`--aad-b2c-instance <INSTANCE>` - 연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-416">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="b90ff-417">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-417">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="b90ff-418">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-418">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="b90ff-419">`-ssp|--susi-policy-id <ID>` - 이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-419">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="b90ff-420">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-420">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b90ff-421">`--aad-instance <INSTANCE>` - 연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-421">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="b90ff-422">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-422">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b90ff-423">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-423">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="b90ff-424">`--client-id <ID>` - 이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-424">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="b90ff-425">`IndividualB2C` 또는 `SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-425">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="b90ff-426">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-426">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="b90ff-427">`--domain <DOMAIN>` - 디렉터리 테넌트에 대한 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-427">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="b90ff-428">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-428">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b90ff-429">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-429">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="b90ff-430">`--tenant-id <ID>` - 연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-430">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="b90ff-431">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-431">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b90ff-432">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-432">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="b90ff-433">`-r|--org-read-access` - 디렉터리에 대한 이 응용 프로그램 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-433">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="b90ff-434">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-434">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="b90ff-435">`--use-launch-settings` - 생성된 템플릿 출력에 *launchSettings.json*을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-435">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="b90ff-436">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-436">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="b90ff-437">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-437">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b90ff-438">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-438">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b90ff-439">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="b90ff-439">**mvc, razor**</span></span>

<span data-ttu-id="b90ff-440">`-au|--auth <AUTHENTICATION_TYPE>` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-440">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="b90ff-441">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-441">The possible values are:</span></span>

- <span data-ttu-id="b90ff-442">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="b90ff-442">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="b90ff-443">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-443">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="b90ff-444">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-444">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="b90ff-445">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-445">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="b90ff-446">`MultiOrg` - 여러 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-446">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="b90ff-447">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-447">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="b90ff-448">`--aad-b2c-instance <INSTANCE>` - 연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-448">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="b90ff-449">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-449">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="b90ff-450">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-450">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="b90ff-451">`-ssp|--susi-policy-id <ID>` - 이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-451">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="b90ff-452">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-452">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b90ff-453">`-rp|--reset-password-policy-id <ID>` - 이 프로젝트에 대한 암호 재설정 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-453">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="b90ff-454">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-454">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b90ff-455">`-ep|--edit-profile-policy-id <ID>` - 이 프로젝트에 대한 프로필 편집 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-455">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="b90ff-456">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-456">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b90ff-457">`--aad-instance <INSTANCE>` - 연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-457">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="b90ff-458">`SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-458">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="b90ff-459">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-459">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="b90ff-460">`--client-id <ID>` - 이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-460">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="b90ff-461">`IndividualB2C`, `SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-461">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="b90ff-462">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-462">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="b90ff-463">`--domain <DOMAIN>` - 디렉터리 테넌트에 대한 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-463">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="b90ff-464">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-464">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b90ff-465">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-465">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="b90ff-466">`--tenant-id <ID>` - 연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-466">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="b90ff-467">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-467">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b90ff-468">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-468">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="b90ff-469">`--callback-path <PATH>` - 리디렉션 URI의 응용 프로그램 기본 경로 내 요청 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-469">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="b90ff-470">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-470">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b90ff-471">기본값은 `/signin-oidc`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-471">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="b90ff-472">`-r|--org-read-access` - 디렉터리에 대한 이 응용 프로그램 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-472">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="b90ff-473">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-473">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="b90ff-474">`--use-launch-settings` - 생성된 템플릿 출력에 *launchSettings.json*을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-474">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="b90ff-475">`--use-browserlink` - 프로젝트에 BrowserLink를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-475">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="b90ff-476">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-476">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="b90ff-477">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-477">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="b90ff-478">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-478">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="b90ff-479">**page**</span><span class="sxs-lookup"><span data-stu-id="b90ff-479">**page**</span></span>

<span data-ttu-id="b90ff-480">`-na|--namespace <NAMESPACE_NAME>` - 생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-480">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="b90ff-481">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-481">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="b90ff-482">`-np|--no-pagemodel` - PageModel 없이 페이지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-482">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="b90ff-483">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="b90ff-483">**viewimports**</span></span>

<span data-ttu-id="b90ff-484">`-na|--namespace <NAMESPACE_NAME>` - 생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-484">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="b90ff-485">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-485">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b90ff-486">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b90ff-486">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="b90ff-487">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="b90ff-487">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="b90ff-488">`-f|--framework` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-488">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b90ff-489">값: `netcoreapp1.0` 또는 `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="b90ff-489">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="b90ff-490">기본값은 `netcoreapp1.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-490">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="b90ff-491">**classlib**</span><span class="sxs-lookup"><span data-stu-id="b90ff-491">**classlib**</span></span>

<span data-ttu-id="b90ff-492">`-f|--framework` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-492">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b90ff-493">값: `netcoreapp1.0`, `netcoreapp1.1` 또는 `netstandard1.0`~`netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="b90ff-493">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="b90ff-494">기본값은 `netstandard1.4`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-494">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="b90ff-495">**mvc**</span><span class="sxs-lookup"><span data-stu-id="b90ff-495">**mvc**</span></span>

<span data-ttu-id="b90ff-496">`-f|--framework` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-496">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b90ff-497">값: `netcoreapp1.0` 또는 `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="b90ff-497">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="b90ff-498">기본값은 `netcoreapp1.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-498">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="b90ff-499">`-au|--auth` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-499">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="b90ff-500">값: `None` 또는 `Individual`.</span><span class="sxs-lookup"><span data-stu-id="b90ff-500">Values: `None` or `Individual`.</span></span> <span data-ttu-id="b90ff-501">기본값은 `None`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-501">The default value is `None`.</span></span>

<span data-ttu-id="b90ff-502">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-502">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="b90ff-503">값: `true` 또는 `false`.</span><span class="sxs-lookup"><span data-stu-id="b90ff-503">Values: `true` or `false`.</span></span> <span data-ttu-id="b90ff-504">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-504">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="b90ff-505">예제</span><span class="sxs-lookup"><span data-stu-id="b90ff-505">Examples</span></span>

<span data-ttu-id="b90ff-506">현재 디렉터리에 F# 콘솔 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-506">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="b90ff-507">지정된 디렉터리에서 .NET Standard 클래스 라이브러리 프로젝트를 만듭니다(.NET Core SDK 2.0 이상 버전에서만 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="b90ff-507">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="b90ff-508">인증 없이 현재 디렉터리에 새 ASP.NET Core C# MVC 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-508">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="b90ff-509">새 xUnit 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-509">Create a new xUnit application:</span></span>

`dotnet new xunit`

<span data-ttu-id="b90ff-510">MVC에 대해 사용할 수 있는 모든 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="b90ff-510">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="b90ff-511">ASP.NET Core용 단일 페이지 응용 프로그램 템플릿 버전 2.0을 설치합니다(.NET Core SDK 1.1 및 이후 버전에서만 사용할 수 있는 명령 옵션).</span><span class="sxs-lookup"><span data-stu-id="b90ff-511">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="b90ff-512">현재 디렉터리에서 SDK 버전을 2.0.0으로 설정하여 *global.json*을 만듭니다(.NET Core SDK 2.0 이상 버전에서만 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="b90ff-512">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="b90ff-513">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b90ff-513">See also</span></span>

[<span data-ttu-id="b90ff-514">dotnet new에 대한 사용자 지정 템플릿</span><span class="sxs-lookup"><span data-stu-id="b90ff-514">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="b90ff-515">dotnet용 사용자 지정 템플릿 새로 만들기</span><span class="sxs-lookup"><span data-stu-id="b90ff-515">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
<span data-ttu-id="b90ff-516">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)(dotnet/dotnet-template-samples GitHub 리포지토리)</span><span class="sxs-lookup"><span data-stu-id="b90ff-516">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)</span></span>  
<span data-ttu-id="b90ff-517">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)(dotnet new에 대한 사용 가능한 템플릿)</span><span class="sxs-lookup"><span data-stu-id="b90ff-517">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
