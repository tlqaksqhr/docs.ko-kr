---
title: dotnet new 명령 - .NET Core CLI
description: dotnet new 명령은 지정된 템플릿을 기반으로 새 .NET Core 프로젝트를 만듭니다.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: ae24c4145cc67ca863c07e4d22af8a1c2c2dd732
ms.sourcegitcommit: 3540f614fc94f77ca4ab58df66db2d0f4d52dfee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34570465"
---
# <a name="dotnet-new"></a><span data-ttu-id="10d6b-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="10d6b-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="10d6b-104">name</span><span class="sxs-lookup"><span data-stu-id="10d6b-104">Name</span></span>

<span data-ttu-id="10d6b-105">`dotnet new` - 지정된 템플릿을 기반으로 새 프로젝트, 구성 파일 또는 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="10d6b-106">개요</span><span class="sxs-lookup"><span data-stu-id="10d6b-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="10d6b-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="10d6b-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="10d6b-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="10d6b-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="10d6b-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="10d6b-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="10d6b-110">설명</span><span class="sxs-lookup"><span data-stu-id="10d6b-110">Description</span></span>

<span data-ttu-id="10d6b-111">`dotnet new` 명령은 유효한 .NET Core 프로젝트를 초기화하는 편리한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="10d6b-112">이 명령은 [템플릿 엔진](https://github.com/dotnet/templating)을 호출하여 지정된 템플릿 및 옵션을 기반으로 디스크에 아티팩트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="10d6b-113">인수</span><span class="sxs-lookup"><span data-stu-id="10d6b-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="10d6b-114">명령이 호출될 때 인스턴스화할 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="10d6b-115">각 템플릿에는 전달할 수 있는 특정 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="10d6b-116">자세한 내용은 [템플릿 옵션](#template-options)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="10d6b-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="10d6b-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="10d6b-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="10d6b-118">명령에는 템플릿의 기본 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-118">The command contains a default list of templates.</span></span> <span data-ttu-id="10d6b-119">`dotnet new -l`을 사용하여 사용 가능한 템플릿 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="10d6b-120">다음 표에는 .NET Core SDK 2.1.300과 함께 사전 설치된 템플릿이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="10d6b-121">템플릿의 기본 언어는 대괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="10d6b-122">템플릿 설명</span><span class="sxs-lookup"><span data-stu-id="10d6b-122">Template description</span></span>                          | <span data-ttu-id="10d6b-123">템플릿 이름</span><span class="sxs-lookup"><span data-stu-id="10d6b-123">Template name</span></span>   | <span data-ttu-id="10d6b-124">언어</span><span class="sxs-lookup"><span data-stu-id="10d6b-124">Languages</span></span>     |
|----------------------------------------------|-----------------|---------------|
| <span data-ttu-id="10d6b-125">콘솔 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="10d6b-125">Console application</span></span>                          | `console`       | <span data-ttu-id="10d6b-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="10d6b-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="10d6b-127">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="10d6b-127">Class library</span></span>                                | `classlib`      | <span data-ttu-id="10d6b-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="10d6b-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="10d6b-129">단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="10d6b-129">Unit test project</span></span>                            | `mstest`        | <span data-ttu-id="10d6b-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="10d6b-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="10d6b-131">xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="10d6b-131">xUnit test project</span></span>                           | `xunit`         | <span data-ttu-id="10d6b-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="10d6b-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="10d6b-133">Razor 페이지</span><span class="sxs-lookup"><span data-stu-id="10d6b-133">Razor page</span></span>                                   | `page`          | <span data-ttu-id="10d6b-134">[C#]</span><span class="sxs-lookup"><span data-stu-id="10d6b-134">[C#]</span></span>          |
| <span data-ttu-id="10d6b-135">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="10d6b-135">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="10d6b-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="10d6b-136">[C#]</span></span>          |
| <span data-ttu-id="10d6b-137">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="10d6b-137">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="10d6b-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="10d6b-138">[C#]</span></span>          |
| <span data-ttu-id="10d6b-139">ASP.NET Core 비어 있음</span><span class="sxs-lookup"><span data-stu-id="10d6b-139">ASP.NET Core empty</span></span>                           | `web`           | <span data-ttu-id="10d6b-140">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="10d6b-140">[C#], F#</span></span>      |
| <span data-ttu-id="10d6b-141">ASP.NET Core 웹앱(모델-뷰-컨트롤러)</span><span class="sxs-lookup"><span data-stu-id="10d6b-141">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="10d6b-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="10d6b-142">[C#], F#</span></span>      |
| <span data-ttu-id="10d6b-143">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="10d6b-143">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="10d6b-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="10d6b-144">[C#]</span></span>          |
| <span data-ttu-id="10d6b-145">ASP.NET Core(Angular 사용)</span><span class="sxs-lookup"><span data-stu-id="10d6b-145">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="10d6b-146">[C#]</span><span class="sxs-lookup"><span data-stu-id="10d6b-146">[C#]</span></span>          |
| <span data-ttu-id="10d6b-147">ASP.NET Core(React.js 사용)</span><span class="sxs-lookup"><span data-stu-id="10d6b-147">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="10d6b-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="10d6b-148">[C#]</span></span>          |
| <span data-ttu-id="10d6b-149">ASP.NET Core(React.js 및 Redux 사용)</span><span class="sxs-lookup"><span data-stu-id="10d6b-149">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="10d6b-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="10d6b-150">[C#]</span></span>          |
| <span data-ttu-id="10d6b-151">ASP.NET Core 웹 API</span><span class="sxs-lookup"><span data-stu-id="10d6b-151">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="10d6b-152">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="10d6b-152">[C#], F#</span></span>      |
| <span data-ttu-id="10d6b-153">Razor 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="10d6b-153">Razor class library</span></span>                          | `razorclasslib` | <span data-ttu-id="10d6b-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="10d6b-154">[C#]</span></span>          |
| <span data-ttu-id="10d6b-155">global.json 파일</span><span class="sxs-lookup"><span data-stu-id="10d6b-155">global.json file</span></span>                             | `globaljson`    |               |
| <span data-ttu-id="10d6b-156">NuGet 구성</span><span class="sxs-lookup"><span data-stu-id="10d6b-156">NuGet config</span></span>                                 | `nugetconfig`   |               |
| <span data-ttu-id="10d6b-157">웹 구성</span><span class="sxs-lookup"><span data-stu-id="10d6b-157">Web config</span></span>                                   | `webconfig`     |               |
| <span data-ttu-id="10d6b-158">솔루션 파일</span><span class="sxs-lookup"><span data-stu-id="10d6b-158">Solution file</span></span>                                | `sln`           |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="10d6b-159">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="10d6b-159">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="10d6b-160">명령에는 템플릿의 기본 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-160">The command contains a default list of templates.</span></span> <span data-ttu-id="10d6b-161">`dotnet new -l`을 사용하여 사용 가능한 템플릿 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-161">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="10d6b-162">다음 표에는 .NET Core SDK 2.0과 함께 사전 설치된 템플릿이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-162">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="10d6b-163">템플릿의 기본 언어는 대괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-163">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="10d6b-164">템플릿 설명</span><span class="sxs-lookup"><span data-stu-id="10d6b-164">Template description</span></span>                          | <span data-ttu-id="10d6b-165">템플릿 이름</span><span class="sxs-lookup"><span data-stu-id="10d6b-165">Template name</span></span> | <span data-ttu-id="10d6b-166">언어</span><span class="sxs-lookup"><span data-stu-id="10d6b-166">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="10d6b-167">콘솔 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="10d6b-167">Console application</span></span>                          | `console`     | <span data-ttu-id="10d6b-168">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="10d6b-168">[C#], F#, VB</span></span>  |
| <span data-ttu-id="10d6b-169">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="10d6b-169">Class library</span></span>                                | `classlib`    | <span data-ttu-id="10d6b-170">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="10d6b-170">[C#], F#, VB</span></span>  |
| <span data-ttu-id="10d6b-171">단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="10d6b-171">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="10d6b-172">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="10d6b-172">[C#], F#, VB</span></span>  |
| <span data-ttu-id="10d6b-173">xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="10d6b-173">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="10d6b-174">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="10d6b-174">[C#], F#, VB</span></span>  |
| <span data-ttu-id="10d6b-175">ASP.NET Core 비어 있음</span><span class="sxs-lookup"><span data-stu-id="10d6b-175">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="10d6b-176">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="10d6b-176">[C#], F#</span></span>      |
| <span data-ttu-id="10d6b-177">ASP.NET Core 웹앱(모델-뷰-컨트롤러)</span><span class="sxs-lookup"><span data-stu-id="10d6b-177">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="10d6b-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="10d6b-178">[C#], F#</span></span>      |
| <span data-ttu-id="10d6b-179">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="10d6b-179">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="10d6b-180">[C#]</span><span class="sxs-lookup"><span data-stu-id="10d6b-180">[C#]</span></span>          |
| <span data-ttu-id="10d6b-181">ASP.NET Core(Angular 사용)</span><span class="sxs-lookup"><span data-stu-id="10d6b-181">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="10d6b-182">[C#]</span><span class="sxs-lookup"><span data-stu-id="10d6b-182">[C#]</span></span>          |
| <span data-ttu-id="10d6b-183">ASP.NET Core(React.js 사용)</span><span class="sxs-lookup"><span data-stu-id="10d6b-183">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="10d6b-184">[C#]</span><span class="sxs-lookup"><span data-stu-id="10d6b-184">[C#]</span></span>          |
| <span data-ttu-id="10d6b-185">ASP.NET Core(React.js 및 Redux 사용)</span><span class="sxs-lookup"><span data-stu-id="10d6b-185">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="10d6b-186">[C#]</span><span class="sxs-lookup"><span data-stu-id="10d6b-186">[C#]</span></span>          |
| <span data-ttu-id="10d6b-187">ASP.NET Core 웹 API</span><span class="sxs-lookup"><span data-stu-id="10d6b-187">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="10d6b-188">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="10d6b-188">[C#], F#</span></span>      |
| <span data-ttu-id="10d6b-189">global.json 파일</span><span class="sxs-lookup"><span data-stu-id="10d6b-189">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="10d6b-190">NuGet 구성</span><span class="sxs-lookup"><span data-stu-id="10d6b-190">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="10d6b-191">웹 구성</span><span class="sxs-lookup"><span data-stu-id="10d6b-191">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="10d6b-192">솔루션 파일</span><span class="sxs-lookup"><span data-stu-id="10d6b-192">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="10d6b-193">Razor 페이지</span><span class="sxs-lookup"><span data-stu-id="10d6b-193">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="10d6b-194">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="10d6b-194">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="10d6b-195">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="10d6b-195">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="10d6b-196">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="10d6b-196">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="10d6b-197">명령에는 템플릿의 기본 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-197">The command contains a default list of templates.</span></span> <span data-ttu-id="10d6b-198">`dotnet new -all`을 사용하여 사용 가능한 템플릿 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-198">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="10d6b-199">다음 표에는 .NET Core SDK 1.x와 함께 사전 설치된 템플릿이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-199">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="10d6b-200">템플릿의 기본 언어는 대괄호 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-200">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="10d6b-201">템플릿 설명</span><span class="sxs-lookup"><span data-stu-id="10d6b-201">Template description</span></span>  | <span data-ttu-id="10d6b-202">템플릿 이름</span><span class="sxs-lookup"><span data-stu-id="10d6b-202">Template name</span></span> | <span data-ttu-id="10d6b-203">언어</span><span class="sxs-lookup"><span data-stu-id="10d6b-203">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="10d6b-204">콘솔 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="10d6b-204">Console application</span></span>  | `console`     | <span data-ttu-id="10d6b-205">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="10d6b-205">[C#], F#</span></span>  |
| <span data-ttu-id="10d6b-206">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="10d6b-206">Class library</span></span>        | `classlib`    | <span data-ttu-id="10d6b-207">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="10d6b-207">[C#], F#</span></span>  |
| <span data-ttu-id="10d6b-208">단위 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="10d6b-208">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="10d6b-209">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="10d6b-209">[C#], F#</span></span>  |
| <span data-ttu-id="10d6b-210">xUnit 테스트 프로젝트</span><span class="sxs-lookup"><span data-stu-id="10d6b-210">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="10d6b-211">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="10d6b-211">[C#], F#</span></span>  |
| <span data-ttu-id="10d6b-212">ASP.NET Core 비어 있음</span><span class="sxs-lookup"><span data-stu-id="10d6b-212">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="10d6b-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="10d6b-213">[C#]</span></span>      |
| <span data-ttu-id="10d6b-214">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="10d6b-214">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="10d6b-215">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="10d6b-215">[C#], F#</span></span>  |
| <span data-ttu-id="10d6b-216">ASP.NET Core 웹 API</span><span class="sxs-lookup"><span data-stu-id="10d6b-216">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="10d6b-217">[C#]</span><span class="sxs-lookup"><span data-stu-id="10d6b-217">[C#]</span></span>      |
| <span data-ttu-id="10d6b-218">NuGet 구성</span><span class="sxs-lookup"><span data-stu-id="10d6b-218">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="10d6b-219">웹 구성</span><span class="sxs-lookup"><span data-stu-id="10d6b-219">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="10d6b-220">솔루션 파일</span><span class="sxs-lookup"><span data-stu-id="10d6b-220">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="10d6b-221">옵션</span><span class="sxs-lookup"><span data-stu-id="10d6b-221">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="10d6b-222">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="10d6b-222">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="10d6b-223">기존 파일을 변경할 경우에도 콘텐츠를 강제 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-223">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="10d6b-224">출력 디렉터리에 이미 프로젝트가 포함되어 있는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-224">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="10d6b-225">명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-225">Prints out help for the command.</span></span> <span data-ttu-id="10d6b-226">`dotnet new` 명령 자체 또는 `dotnet new mvc --help` 같은 템플릿에 대해 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-226">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="10d6b-227">제공된 `PATH` 또는 `NUGET_ID`에서 소스 또는 템플릿 팩을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-227">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="10d6b-228">시험판 버전의 템플릿 패키지를 설치하려면 버전을 `<package-name>::<package-version>` 형식으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-228">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="10d6b-229">기본적으로 `dotnet new`는 마지막 안정 패키지 버전을 나타내는 버전에 대해 \*를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-229">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="10d6b-230">[예제](#examples) 섹션의 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="10d6b-230">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="10d6b-231">사용자 지정 템플릿을 만드는 방법에 대한 자세한 내용은 [dotnet new에 대한 사용자 지정 템플릿](custom-templates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="10d6b-231">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="10d6b-232">지정된 이름을 포함하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-232">Lists templates containing the specified name.</span></span> <span data-ttu-id="10d6b-233">`dotnet new` 명령에 대해 호출되는 경우 지정된 디렉터리에서 사용 가능한 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-233">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="10d6b-234">예를 들어 디렉터리에 이미 프로젝트가 포함되어 있는 경우 일부 프로젝트 템플릿을 나열하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-234">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="10d6b-235">만들 템플릿의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-235">The language of the template to create.</span></span> <span data-ttu-id="10d6b-236">허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조).</span><span class="sxs-lookup"><span data-stu-id="10d6b-236">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="10d6b-237">일부 템플릿의 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-237">Not valid for some templates.</span></span>

    > [!NOTE]
    > Some shells interpret `#` as a special character. In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="10d6b-238">생성된 출력에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-238">The name for the created output.</span></span> <span data-ttu-id="10d6b-239">이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-239">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="10d6b-240">설치 중 사용할 NuGet 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-240">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="10d6b-241">생성된 출력을 배치할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-241">Location to place the generated output.</span></span> <span data-ttu-id="10d6b-242">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-242">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="10d6b-243">사용 가능한 형식에 따라 템플릿을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-243">Filters templates based on available types.</span></span> <span data-ttu-id="10d6b-244">미리 정의된 값은 “project”, “item” 또는 “other”입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-244">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="10d6b-245">제공된 `PATH` 또는 `NUGET_ID`에서 소스 또는 템플릿 팩을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-245">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="10d6b-246">`PATH`를 사용하여 템플릿을 제거하려면 경로를 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-246">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="10d6b-247">예를 들어 *C:/Users/\<사용자>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지만 상위 폴더의 *./GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-247">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="10d6b-248">마지막의 종료하는 디렉터리 슬래시도 템플릿 경로에 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="10d6b-248">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="10d6b-249">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="10d6b-249">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="10d6b-250">기존 파일을 변경할 경우에도 콘텐츠를 강제 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-250">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="10d6b-251">출력 디렉터리에 이미 프로젝트가 포함되어 있는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-251">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="10d6b-252">명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-252">Prints out help for the command.</span></span> <span data-ttu-id="10d6b-253">`dotnet new` 명령 자체 또는 `dotnet new mvc --help` 같은 템플릿에 대해 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-253">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="10d6b-254">제공된 `PATH` 또는 `NUGET_ID`에서 소스 또는 템플릿 팩을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-254">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="10d6b-255">시험판 버전의 템플릿 패키지를 설치하려면 버전을 `<package-name>::<package-version>` 형식으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-255">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="10d6b-256">기본적으로 `dotnet new`는 마지막 안정 패키지 버전을 나타내는 버전에 대해 \*를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-256">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="10d6b-257">[예제](#examples) 섹션의 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="10d6b-257">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="10d6b-258">사용자 지정 템플릿을 만드는 방법에 대한 자세한 내용은 [dotnet new에 대한 사용자 지정 템플릿](custom-templates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="10d6b-258">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="10d6b-259">지정된 이름을 포함하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-259">Lists templates containing the specified name.</span></span> <span data-ttu-id="10d6b-260">`dotnet new` 명령에 대해 호출되는 경우 지정된 디렉터리에서 사용 가능한 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-260">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="10d6b-261">예를 들어 디렉터리에 이미 프로젝트가 포함되어 있는 경우 일부 프로젝트 템플릿을 나열하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-261">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="10d6b-262">만들 템플릿의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-262">The language of the template to create.</span></span> <span data-ttu-id="10d6b-263">허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조).</span><span class="sxs-lookup"><span data-stu-id="10d6b-263">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="10d6b-264">일부 템플릿의 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-264">Not valid for some templates.</span></span>

    > [!NOTE]
    > Some shells interpret `#` as a special character. In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="10d6b-265">생성된 출력에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-265">The name for the created output.</span></span> <span data-ttu-id="10d6b-266">이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-266">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="10d6b-267">생성된 출력을 배치할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-267">Location to place the generated output.</span></span> <span data-ttu-id="10d6b-268">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-268">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="10d6b-269">사용 가능한 형식에 따라 템플릿을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-269">Filters templates based on available types.</span></span> <span data-ttu-id="10d6b-270">미리 정의된 값은 “project”, “item” 또는 “other”입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-270">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="10d6b-271">제공된 `PATH` 또는 `NUGET_ID`에서 소스 또는 템플릿 팩을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-271">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="10d6b-272">`PATH`를 사용하여 템플릿을 제거하려면 경로를 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-272">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="10d6b-273">예를 들어 *C:/Users/\<사용자>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지만 상위 폴더의 *./GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-273">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="10d6b-274">마지막의 종료하는 디렉터리 슬래시도 템플릿 경로에 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="10d6b-274">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="10d6b-275">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="10d6b-275">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="10d6b-276">`dotnet new` 명령의 컨텍스트에서만 실행되는 경우 특정 유형의 프로젝트에 대한 모든 템플릿을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-276">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="10d6b-277">`dotnet new web -all`처럼 특정 템플릿의 컨텍스트에서 실행되는 경우 `-all`은 강제 생성 플래그로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-277">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="10d6b-278">출력 디렉터리에 이미 프로젝트가 포함되어 있는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-278">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="10d6b-279">명령에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-279">Prints out help for the command.</span></span> <span data-ttu-id="10d6b-280">`dotnet new` 명령 자체 또는 `dotnet new mvc --help` 같은 템플릿에 대해 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-280">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="10d6b-281">지정된 이름을 포함하는 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-281">Lists templates containing the specified name.</span></span> <span data-ttu-id="10d6b-282">`dotnet new` 명령에 대해 호출되는 경우 지정된 디렉터리에서 사용 가능한 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-282">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="10d6b-283">예를 들어 디렉터리에 이미 프로젝트가 포함되어 있는 경우 일부 프로젝트 템플릿을 나열하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-283">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="10d6b-284">만들 템플릿의 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-284">The language of the template to create.</span></span> <span data-ttu-id="10d6b-285">허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조).</span><span class="sxs-lookup"><span data-stu-id="10d6b-285">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="10d6b-286">일부 템플릿의 경우 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-286">Not valid for some templates.</span></span>

    > [!NOTE]
    > Some shells interpret `#` as a special character. In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="10d6b-287">생성된 출력에 대한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-287">The name for the created output.</span></span> <span data-ttu-id="10d6b-288">이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-288">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="10d6b-289">생성된 출력을 배치할 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-289">Location to place the generated output.</span></span> <span data-ttu-id="10d6b-290">기본값은 현재 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-290">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="10d6b-291">템플릿 옵션</span><span class="sxs-lookup"><span data-stu-id="10d6b-291">Template options</span></span>

<span data-ttu-id="10d6b-292">각 프로젝트 템플릿에는 사용할 수 있는 추가 옵션이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-292">Each project template may have additional options available.</span></span> <span data-ttu-id="10d6b-293">코어 템플릿에는 다음과 같은 추가 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-293">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="10d6b-294">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="10d6b-294">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="10d6b-295">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="10d6b-295">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="10d6b-296">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-296">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="10d6b-297">**classlib**</span><span class="sxs-lookup"><span data-stu-id="10d6b-297">**classlib**</span></span>

<span data-ttu-id="10d6b-298">`-f|--framework <FRAMEWORK>` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-298">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="10d6b-299">값: `netcoreapp2.0`(.NET Core 클래스 라이브러리를 만드는 경우) 또는 `netstandard2.0`(.NET Standard 클래스 라이브러리를 만드는 경우).</span><span class="sxs-lookup"><span data-stu-id="10d6b-299">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="10d6b-300">기본값은 `netstandard2.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-300">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="10d6b-301">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-301">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="10d6b-302">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="10d6b-302">**mstest, xunit**</span></span>

<span data-ttu-id="10d6b-303">`-p|--enable-pack` - [dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-303">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="10d6b-304">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-304">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="10d6b-305">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="10d6b-305">**globaljson**</span></span>

<span data-ttu-id="10d6b-306">`--sdk-version <VERSION_NUMBER>` - *global.json* 파일에서 사용할 .NET Core SDK 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-306">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="10d6b-307">**web**</span><span class="sxs-lookup"><span data-stu-id="10d6b-307">**web**</span></span>

<span data-ttu-id="10d6b-308">`--use-launch-settings` - 생성된 템플릿 출력에 *launchSettings.json*을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-308">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="10d6b-309">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-309">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="10d6b-310">**webapi**</span><span class="sxs-lookup"><span data-stu-id="10d6b-310">**webapi**</span></span>

<span data-ttu-id="10d6b-311">`-au|--auth <AUTHENTICATION_TYPE>` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-311">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="10d6b-312">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-312">The possible values are:</span></span>

- <span data-ttu-id="10d6b-313">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="10d6b-313">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="10d6b-314">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-314">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="10d6b-315">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-315">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="10d6b-316">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-316">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="10d6b-317">`--aad-b2c-instance <INSTANCE>` - 연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-317">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="10d6b-318">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-318">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="10d6b-319">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-319">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="10d6b-320">`-ssp|--susi-policy-id <ID>` - 이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-320">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="10d6b-321">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-321">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="10d6b-322">`--aad-instance <INSTANCE>` - 연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-322">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="10d6b-323">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-323">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="10d6b-324">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-324">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="10d6b-325">`--client-id <ID>` - 이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-325">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="10d6b-326">`IndividualB2C` 또는 `SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-326">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="10d6b-327">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-327">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="10d6b-328">`--domain <DOMAIN>` - 디렉터리 테넌트에 대한 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-328">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="10d6b-329">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-329">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="10d6b-330">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-330">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="10d6b-331">`--tenant-id <ID>` - 연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-331">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="10d6b-332">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-332">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="10d6b-333">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-333">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="10d6b-334">`-r|--org-read-access` - 디렉터리에 대한 이 응용 프로그램 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-334">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="10d6b-335">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-335">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="10d6b-336">`--use-launch-settings` - 생성된 템플릿 출력에 *launchSettings.json*을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-336">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="10d6b-337">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-337">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="10d6b-338">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-338">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="10d6b-339">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-339">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="10d6b-340">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="10d6b-340">**mvc, razor**</span></span>

<span data-ttu-id="10d6b-341">`-au|--auth <AUTHENTICATION_TYPE>` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-341">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="10d6b-342">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-342">The possible values are:</span></span>

- <span data-ttu-id="10d6b-343">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="10d6b-343">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="10d6b-344">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-344">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="10d6b-345">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-345">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="10d6b-346">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-346">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="10d6b-347">`MultiOrg` - 여러 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-347">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="10d6b-348">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-348">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="10d6b-349">`--aad-b2c-instance <INSTANCE>` - 연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-349">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="10d6b-350">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-350">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="10d6b-351">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-351">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="10d6b-352">`-ssp|--susi-policy-id <ID>` - 이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-352">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="10d6b-353">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-353">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="10d6b-354">`-rp|--reset-password-policy-id <ID>` - 이 프로젝트에 대한 암호 재설정 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-354">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="10d6b-355">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-355">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="10d6b-356">`-ep|--edit-profile-policy-id <ID>` - 이 프로젝트에 대한 프로필 편집 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-356">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="10d6b-357">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-357">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="10d6b-358">`--aad-instance <INSTANCE>` - 연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-358">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="10d6b-359">`SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-359">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="10d6b-360">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-360">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="10d6b-361">`--client-id <ID>` - 이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-361">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="10d6b-362">`IndividualB2C`, `SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-362">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="10d6b-363">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-363">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="10d6b-364">`--domain <DOMAIN>` - 디렉터리 테넌트에 대한 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-364">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="10d6b-365">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-365">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="10d6b-366">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-366">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="10d6b-367">`--tenant-id <ID>` - 연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-367">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="10d6b-368">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-368">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="10d6b-369">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-369">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="10d6b-370">`--callback-path <PATH>` - 리디렉션 URI의 응용 프로그램 기본 경로 내 요청 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-370">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="10d6b-371">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-371">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="10d6b-372">기본값은 `/signin-oidc`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-372">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="10d6b-373">`-r|--org-read-access` - 디렉터리에 대한 이 응용 프로그램 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-373">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="10d6b-374">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-374">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="10d6b-375">`--use-launch-settings` - 생성된 템플릿 출력에 *launchSettings.json*을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-375">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="10d6b-376">`--use-browserlink` - 프로젝트에 BrowserLink를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-376">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="10d6b-377">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-377">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="10d6b-378">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-378">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="10d6b-379">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-379">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="10d6b-380">**page**</span><span class="sxs-lookup"><span data-stu-id="10d6b-380">**page**</span></span>

<span data-ttu-id="10d6b-381">`-na|--namespace <NAMESPACE_NAME>` - 생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-381">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="10d6b-382">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-382">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="10d6b-383">`-np|--no-pagemodel` - PageModel 없이 페이지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-383">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="10d6b-384">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="10d6b-384">**viewimports**</span></span>

<span data-ttu-id="10d6b-385">`-na|--namespace <NAMESPACE_NAME>` - 생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-385">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="10d6b-386">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-386">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="10d6b-387">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="10d6b-387">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="10d6b-388">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="10d6b-388">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="10d6b-389">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-389">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="10d6b-390">**classlib**</span><span class="sxs-lookup"><span data-stu-id="10d6b-390">**classlib**</span></span>

<span data-ttu-id="10d6b-391">`-f|--framework <FRAMEWORK>` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-391">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="10d6b-392">값: `netcoreapp2.0`(.NET Core 클래스 라이브러리를 만드는 경우) 또는 `netstandard2.0`(.NET Standard 클래스 라이브러리를 만드는 경우).</span><span class="sxs-lookup"><span data-stu-id="10d6b-392">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="10d6b-393">기본값은 `netstandard2.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-393">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="10d6b-394">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-394">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="10d6b-395">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="10d6b-395">**mstest, xunit**</span></span>

<span data-ttu-id="10d6b-396">`-p|--enable-pack` - [dotnet pack](dotnet-pack.md)을 사용하여 프로젝트에 대한 패키징을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-396">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="10d6b-397">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-397">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="10d6b-398">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="10d6b-398">**globaljson**</span></span>

<span data-ttu-id="10d6b-399">`--sdk-version <VERSION_NUMBER>` - *global.json* 파일에서 사용할 .NET Core SDK 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-399">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="10d6b-400">**web**</span><span class="sxs-lookup"><span data-stu-id="10d6b-400">**web**</span></span>

<span data-ttu-id="10d6b-401">`--use-launch-settings` - 생성된 템플릿 출력에 *launchSettings.json*을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-401">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="10d6b-402">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-402">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="10d6b-403">**webapi**</span><span class="sxs-lookup"><span data-stu-id="10d6b-403">**webapi**</span></span>

<span data-ttu-id="10d6b-404">`-au|--auth <AUTHENTICATION_TYPE>` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-404">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="10d6b-405">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-405">The possible values are:</span></span>

- <span data-ttu-id="10d6b-406">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="10d6b-406">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="10d6b-407">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-407">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="10d6b-408">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-408">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="10d6b-409">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-409">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="10d6b-410">`--aad-b2c-instance <INSTANCE>` - 연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-410">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="10d6b-411">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-411">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="10d6b-412">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-412">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="10d6b-413">`-ssp|--susi-policy-id <ID>` - 이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-413">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="10d6b-414">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-414">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="10d6b-415">`--aad-instance <INSTANCE>` - 연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-415">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="10d6b-416">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-416">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="10d6b-417">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-417">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="10d6b-418">`--client-id <ID>` - 이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-418">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="10d6b-419">`IndividualB2C` 또는 `SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-419">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="10d6b-420">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-420">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="10d6b-421">`--domain <DOMAIN>` - 디렉터리 테넌트에 대한 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-421">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="10d6b-422">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-422">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="10d6b-423">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-423">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="10d6b-424">`--tenant-id <ID>` - 연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-424">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="10d6b-425">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-425">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="10d6b-426">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-426">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="10d6b-427">`-r|--org-read-access` - 디렉터리에 대한 이 응용 프로그램 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-427">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="10d6b-428">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-428">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="10d6b-429">`--use-launch-settings` - 생성된 템플릿 출력에 *launchSettings.json*을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-429">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="10d6b-430">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-430">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="10d6b-431">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-431">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="10d6b-432">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-432">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="10d6b-433">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="10d6b-433">**mvc, razor**</span></span>

<span data-ttu-id="10d6b-434">`-au|--auth <AUTHENTICATION_TYPE>` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-434">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="10d6b-435">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-435">The possible values are:</span></span>

- <span data-ttu-id="10d6b-436">`None` - 인증하지 않습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="10d6b-436">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="10d6b-437">`Individual` - 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-437">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="10d6b-438">`IndividualB2C` - Azure AD B2C를 사용한 개별 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-438">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="10d6b-439">`SingleOrg` - 단일 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-439">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="10d6b-440">`MultiOrg` - 여러 테넌트에 대한 조직적 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-440">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="10d6b-441">`Windows` - Windows 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-441">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="10d6b-442">`--aad-b2c-instance <INSTANCE>` - 연결할 Azure Active Directory B2C 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-442">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="10d6b-443">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-443">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="10d6b-444">기본값은 `https://login.microsoftonline.com/tfp/`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-444">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="10d6b-445">`-ssp|--susi-policy-id <ID>` - 이 프로젝트에 대한 로그인 및 등록 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-445">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="10d6b-446">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-446">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="10d6b-447">`-rp|--reset-password-policy-id <ID>` - 이 프로젝트에 대한 암호 재설정 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-447">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="10d6b-448">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-448">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="10d6b-449">`-ep|--edit-profile-policy-id <ID>` - 이 프로젝트에 대한 프로필 편집 정책 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-449">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="10d6b-450">`IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-450">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="10d6b-451">`--aad-instance <INSTANCE>` - 연결할 Azure Active Directory 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-451">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="10d6b-452">`SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-452">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="10d6b-453">기본값은 `https://login.microsoftonline.com/`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-453">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="10d6b-454">`--client-id <ID>` - 이 프로젝트의 클라이언트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-454">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="10d6b-455">`IndividualB2C`, `SingleOrg` 또는 `MultiOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-455">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="10d6b-456">기본값은 `11111111-1111-1111-11111111111111111`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-456">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="10d6b-457">`--domain <DOMAIN>` - 디렉터리 테넌트에 대한 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-457">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="10d6b-458">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-458">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="10d6b-459">기본값은 `qualified.domain.name`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-459">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="10d6b-460">`--tenant-id <ID>` - 연결할 디렉터리의 TenantId ID입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-460">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="10d6b-461">`SingleOrg` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-461">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="10d6b-462">기본값은 `22222222-2222-2222-2222-222222222222`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-462">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="10d6b-463">`--callback-path <PATH>` - 리디렉션 URI의 응용 프로그램 기본 경로 내 요청 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-463">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="10d6b-464">`SingleOrg` 또는 `IndividualB2C` 인증과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-464">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="10d6b-465">기본값은 `/signin-oidc`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-465">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="10d6b-466">`-r|--org-read-access` - 디렉터리에 대한 이 응용 프로그램 읽기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-466">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="10d6b-467">`SingleOrg` 또는 `MultiOrg` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-467">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="10d6b-468">`--use-launch-settings` - 생성된 템플릿 출력에 *launchSettings.json*을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-468">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="10d6b-469">`--use-browserlink` - 프로젝트에 BrowserLink를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-469">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="10d6b-470">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-470">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="10d6b-471">`Individual` 또는 `IndividualB2C` 인증에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-471">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="10d6b-472">`--no-restore` - 프로젝트를 만드는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-472">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="10d6b-473">**page**</span><span class="sxs-lookup"><span data-stu-id="10d6b-473">**page**</span></span>

<span data-ttu-id="10d6b-474">`-na|--namespace <NAMESPACE_NAME>` - 생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-474">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="10d6b-475">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-475">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="10d6b-476">`-np|--no-pagemodel` - PageModel 없이 페이지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-476">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="10d6b-477">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="10d6b-477">**viewimports**</span></span>

<span data-ttu-id="10d6b-478">`-na|--namespace <NAMESPACE_NAME>` - 생성된 코드에 대한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-478">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="10d6b-479">기본값은 `MyApp.Namespace`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-479">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="10d6b-480">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="10d6b-480">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="10d6b-481">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="10d6b-481">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="10d6b-482">`-f|--framework` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-482">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="10d6b-483">값: `netcoreapp1.0` 또는 `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="10d6b-483">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="10d6b-484">기본값은 `netcoreapp1.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-484">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="10d6b-485">**classlib**</span><span class="sxs-lookup"><span data-stu-id="10d6b-485">**classlib**</span></span>

<span data-ttu-id="10d6b-486">`-f|--framework` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-486">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="10d6b-487">값: `netcoreapp1.0`, `netcoreapp1.1` 또는 `netstandard1.0`~`netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="10d6b-487">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="10d6b-488">기본값은 `netstandard1.4`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-488">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="10d6b-489">**mvc**</span><span class="sxs-lookup"><span data-stu-id="10d6b-489">**mvc**</span></span>

<span data-ttu-id="10d6b-490">`-f|--framework` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-490">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="10d6b-491">값: `netcoreapp1.0` 또는 `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="10d6b-491">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="10d6b-492">기본값은 `netcoreapp1.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-492">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="10d6b-493">`-au|--auth` - 사용할 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-493">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="10d6b-494">값: `None` 또는 `Individual`.</span><span class="sxs-lookup"><span data-stu-id="10d6b-494">Values: `None` or `Individual`.</span></span> <span data-ttu-id="10d6b-495">기본값은 `None`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-495">The default value is `None`.</span></span>

<span data-ttu-id="10d6b-496">`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-496">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="10d6b-497">값: `true` 또는 `false`.</span><span class="sxs-lookup"><span data-stu-id="10d6b-497">Values: `true` or `false`.</span></span> <span data-ttu-id="10d6b-498">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-498">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="10d6b-499">예제</span><span class="sxs-lookup"><span data-stu-id="10d6b-499">Examples</span></span>

<span data-ttu-id="10d6b-500">현재 디렉터리에 F# 콘솔 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-500">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="10d6b-501">지정된 디렉터리에서 .NET Standard 클래스 라이브러리 프로젝트를 만듭니다(.NET Core SDK 2.0 이상 버전에서만 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="10d6b-501">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="10d6b-502">.NET Core 2.0을 대상으로 인증 없이 현재 디렉터리에 새 ASP.NET Core C# MVC 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-502">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 2.0:</span></span>

`dotnet new mvc -au None -f netcoreapp2.0`

<span data-ttu-id="10d6b-503">.NET Core 2.0을 대상으로 새 xUnit 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-503">Create a new xUnit application targeting .NET Core 2.0:</span></span>

`dotnet new xunit --framework netcoreapp2.0`

<span data-ttu-id="10d6b-504">MVC에 대해 사용할 수 있는 모든 템플릿을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="10d6b-504">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="10d6b-505">ASP.NET Core용 단일 페이지 응용 프로그램 템플릿 버전 2.0을 설치합니다(.NET Core SDK 1.1 및 이후 버전에서만 사용할 수 있는 명령 옵션).</span><span class="sxs-lookup"><span data-stu-id="10d6b-505">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="10d6b-506">현재 디렉터리에서 SDK 버전을 2.0.0으로 설정하여 *global.json*을 만듭니다(.NET Core SDK 2.0 이상 버전에서만 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="10d6b-506">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="10d6b-507">참고 항목</span><span class="sxs-lookup"><span data-stu-id="10d6b-507">See also</span></span>

[<span data-ttu-id="10d6b-508">dotnet new에 대한 사용자 지정 템플릿</span><span class="sxs-lookup"><span data-stu-id="10d6b-508">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="10d6b-509">dotnet용 사용자 지정 템플릿 새로 만들기</span><span class="sxs-lookup"><span data-stu-id="10d6b-509">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
<span data-ttu-id="10d6b-510">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)(dotnet/dotnet-template-samples GitHub 리포지토리)</span><span class="sxs-lookup"><span data-stu-id="10d6b-510">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)</span></span>  
<span data-ttu-id="10d6b-511">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)(dotnet new에 대한 사용 가능한 템플릿)</span><span class="sxs-lookup"><span data-stu-id="10d6b-511">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>