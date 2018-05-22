---
title: dotnet new에 대한 사용자 지정 템플릿
description: 모든 형식의 .NET 프로젝트 또는 파일에 대한 사용자 지정 템플릿을 알아봅니다.
author: guardrex
ms.author: mairaw
ms.date: 08/11/2017
ms.openlocfilehash: fe888d0bfeeb51d77b73ec481b93fec9b40aa6ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="custom-templates-for-dotnet-new"></a><span data-ttu-id="69cb5-103">dotnet new에 대한 사용자 지정 템플릿</span><span class="sxs-lookup"><span data-stu-id="69cb5-103">Custom templates for dotnet new</span></span>

<span data-ttu-id="69cb5-104">[.NET Core SDK](https://www.microsoft.com/net/download/core)에는 [`dotnet new` 명령](dotnet-new.md)과 함께 사용할 많은 템플릿이 미리 설치되어 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-104">The [.NET Core SDK](https://www.microsoft.com/net/download/core) comes with many templates pre-installed to use with the [`dotnet new` command](dotnet-new.md).</span></span> <span data-ttu-id="69cb5-105">.NET Core 2.0부터 앱, 서비스, 도구 또는 클래스 라이브러리와 같은 모든 형식의 프로젝트에 대한 사용자 지정 템플릿을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-105">Starting with .NET Core 2.0, you can create your own custom templates for any type of project, such as an app, service, tool, or class library.</span></span> <span data-ttu-id="69cb5-106">구성 파일과 같이 하나 이상의 종속 파일을 출력하는 템플릿도 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-106">You can even create a template that outputs one or more independent files, such as a configuration file.</span></span>

<span data-ttu-id="69cb5-107">NuGet *nupkg* 파일을 직접 참조하거나 템플릿이 포함된 파일 시스템 디렉터리를 지정하여 NuGet 피드의 NuGet 패키지에서 사용자 지정 템플릿을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-107">You can install custom templates from a NuGet package on any NuGet feed, by referencing a NuGet *nupkg* file directly, or by specifying a file system directory that contains the template.</span></span> <span data-ttu-id="69cb5-108">템플릿 엔진은 값을 바꾸고, 파일과 파일 지역을 포함 및 제외하고, 서식이 사용될 때 사용자 지정 처리 작업을 실행할 수 있는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-108">The template engine offers features that allow you to replace values, include and exclude files and regions of files, and execute custom processing operations when your template is used.</span></span>

<span data-ttu-id="69cb5-109">템플릿 엔진은 오픈 소스이며 온라인 코드 리포지토리는 GitHub의 [dotnet/templating](https://github.com/dotnet/templating/)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-109">The template engine is open source, and the online code repository is at [dotnet/templating](https://github.com/dotnet/templating/) on GitHub.</span></span> <span data-ttu-id="69cb5-110">템플릿 샘플을 보려면 [dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples) 리포지토리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69cb5-110">Visit the [dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples) repo for samples of templates.</span></span> <span data-ttu-id="69cb5-111">타사 템플릿을 포함한 추가 템플릿은 GitHub의 [Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)(dotnet new에 대한 사용 가능한 템플릿)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-111">More templates, including templates from third parties, are found at [Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) on GitHub.</span></span> <span data-ttu-id="69cb5-112">사용자 지정 템플릿을 만들고 사용하는 방법에 대한 자세한 내용은 [How to create your own templates for dotnet new](https://blogs.msdn.microsoft.com/dotnet/2017/04/02/how-to-create-your-own-templates-for-dotnet-new/)(dotnet new에 대한 사용자 지정 템플릿을 만드는 방법) 및 [dotnet/templating GitHub repo Wiki](https://github.com/dotnet/templating/wiki)(dotnet/templating GitHub 리포지토리 Wiki)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69cb5-112">For more information about creating and using custom templates, see [How to create your own templates for dotnet new](https://blogs.msdn.microsoft.com/dotnet/2017/04/02/how-to-create-your-own-templates-for-dotnet-new/) and the [dotnet/templating GitHub repo Wiki](https://github.com/dotnet/templating/wiki).</span></span>

<span data-ttu-id="69cb5-113">연습을 수행하고 템플릿을 만들려면 [dotnet new에 대한 사용자 지정 템플릿 만들기](~/docs/core/tutorials/create-custom-template.md) 자습서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69cb5-113">To follow a walkthrough and create a template, see the [Create a custom template for dotnet new](~/docs/core/tutorials/create-custom-template.md) tutorial.</span></span>

## <a name="configuration"></a><span data-ttu-id="69cb5-114">구성</span><span class="sxs-lookup"><span data-stu-id="69cb5-114">Configuration</span></span>

<span data-ttu-id="69cb5-115">템플릿은 다음 구성 요소로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-115">A template is composed of the following components:</span></span>

- <span data-ttu-id="69cb5-116">소스 파일 및 폴더</span><span class="sxs-lookup"><span data-stu-id="69cb5-116">Source files and folders</span></span>
- <span data-ttu-id="69cb5-117">구성 파일(*template.json*)</span><span class="sxs-lookup"><span data-stu-id="69cb5-117">A configuration file (*template.json*)</span></span>

### <a name="source-files-and-folders"></a><span data-ttu-id="69cb5-118">소스 파일 및 폴더</span><span class="sxs-lookup"><span data-stu-id="69cb5-118">Source files and folders</span></span>

<span data-ttu-id="69cb5-119">소스 파일 및 폴더에는 `dotnet new <TEMPLATE>` 명령이 실행될 때 템플릿 엔진에서 사용하려는 모든 파일 및 폴더가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-119">The source files and folders include whatever files and folders you want the template engine to use when the `dotnet new <TEMPLATE>` command is executed.</span></span> <span data-ttu-id="69cb5-120">템플릿 엔진은 프로젝트를 생성하는 데 *실행 가능한 프로젝트*를 소스 코드로 사용하도록 디자인되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-120">The template engine is designed to use *runnable projects* as source code to produce projects.</span></span> <span data-ttu-id="69cb5-121">여기에는 여러 가지 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-121">This has several benefits:</span></span>

- <span data-ttu-id="69cb5-122">템플릿 엔진에서는 특수 토큰을 프로젝트의 소스 코드에 삽입할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-122">The template engine doesn't require you to inject special tokens into your project's source code.</span></span>
- <span data-ttu-id="69cb5-123">코드 파일은 특수 파일이 아니고 템플릿 엔진 작업을 수행하는 방식으로 수정되지도 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-123">The code files aren't special files or modified in any way to work with the template engine.</span></span> <span data-ttu-id="69cb5-124">따라서 일반적으로 프로젝트 작업을 할 때 사용하는 도구로 템플릿 콘텐츠를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-124">So, the tools you normally use when working with projects also work with template content.</span></span>
- <span data-ttu-id="69cb5-125">다른 프로젝트를 처리하는 것처럼 템플릿 프로젝트를 빌드, 실행 및 디버그합니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-125">You build, run, and debug your template projects just like you do for any of your other projects.</span></span>
- <span data-ttu-id="69cb5-126">*template.json* 구성 파일을 프로젝트에 추가하면 기존 프로젝트에서 템플릿을 빠르게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-126">You can quickly create a template from an existing project just by adding a *template.json* configuration file to the project.</span></span>

<span data-ttu-id="69cb5-127">템플릿에 저장되는 파일과 폴더는 .NET Core 또는 .NET Framework 솔루션과 같은 공식 .NET 프로젝트 형식으로 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-127">Files and folders stored in the template aren't limited to formal .NET project types, such as .NET Core or .NET Framework solutions.</span></span> <span data-ttu-id="69cb5-128">템플릿 엔진에서 출력에 대한 파일(예: 구성 파일 또는 솔루션 파일)을 하나만 생성하는 경우에도 소스 파일 및 폴더는 템플릿을 사용할 때 만들려는 콘텐츠로 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-128">Source files and folders may consist of any content that you wish to create when the template is used, even if the template engine produces just one file for its output, such as a configuration file or a solution file.</span></span> <span data-ttu-id="69cb5-129">예를 들어 *web.config* 소스 파일이 포함되고 템플릿을 사용할 때 프로젝트에 대한 수정된 *web.config* 파일을 만드는 템플릿을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-129">For example, you can create a template that contains a *web.config* source file and creates a modified *web.config* file for projects where the template is used.</span></span> <span data-ttu-id="69cb5-130">소스 파일의 수정 사항은 *template.json* 구성 파일에서 제공한 논리와 설정 및 `dotnet new <TEMPLATE>` 명령에 대한 옵션으로 전달된 사용자 제공 값을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-130">The modifications to source files are based on logic and settings you've provided in the *template.json* configuration file along with values provided by the user passed as options to the `dotnet new <TEMPLATE>` command.</span></span>

### <a name="templatejson"></a><span data-ttu-id="69cb5-131">template.json</span><span class="sxs-lookup"><span data-stu-id="69cb5-131">template.json</span></span>

<span data-ttu-id="69cb5-132">*template.json* 파일은 템플릿 루트 디렉터리의 *.template.config* 폴더에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-132">The *template.json* file is placed in a *.template.config* folder in the root directory of the template.</span></span> <span data-ttu-id="69cb5-133">이 파일은 템플릿 엔진에 구성 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-133">The file provides configuration information to the template engine.</span></span> <span data-ttu-id="69cb5-134">기능 템플릿을 충분히 만들 수 있는 최소 구성으로 다음 표에 나와 있는 멤버가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-134">The minimum configuration requires the members shown in the following table, which is sufficient to create a functional template.</span></span>

| <span data-ttu-id="69cb5-135">멤버</span><span class="sxs-lookup"><span data-stu-id="69cb5-135">Member</span></span>            | <span data-ttu-id="69cb5-136">형식</span><span class="sxs-lookup"><span data-stu-id="69cb5-136">Type</span></span>          | <span data-ttu-id="69cb5-137">설명</span><span class="sxs-lookup"><span data-stu-id="69cb5-137">Description</span></span> |
| ----------------- | ------------- | ----------- |
| `$schema`         | <span data-ttu-id="69cb5-138">URI</span><span class="sxs-lookup"><span data-stu-id="69cb5-138">URI</span></span>           | <span data-ttu-id="69cb5-139">*template.json* 파일에 대한 JSON 스키마.</span><span class="sxs-lookup"><span data-stu-id="69cb5-139">The JSON schema for the *template.json* file.</span></span> <span data-ttu-id="69cb5-140">스키마 지정 시 JSON 스키마가 JSON 편집 기능을 구현하도록 지원하는 편집기.</span><span class="sxs-lookup"><span data-stu-id="69cb5-140">Editors that support JSON schemas enable JSON-editing features when the schema is specified.</span></span> <span data-ttu-id="69cb5-141">예를 들어 [Visual Studio Code](https://code.visualstudio.com/)에서는 이 멤버가 IntelliSense를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-141">For example, [Visual Studio Code](https://code.visualstudio.com/) requires this member to enable IntelliSense.</span></span> <span data-ttu-id="69cb5-142">`http://json.schemastore.org/template` 값을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="69cb5-142">Use a value of `http://json.schemastore.org/template`.</span></span> |
| `author`          | <span data-ttu-id="69cb5-143">string</span><span class="sxs-lookup"><span data-stu-id="69cb5-143">string</span></span>        | <span data-ttu-id="69cb5-144">템플릿 작성자.</span><span class="sxs-lookup"><span data-stu-id="69cb5-144">The author of the template.</span></span> |
| `classifications` | <span data-ttu-id="69cb5-145">array(string)</span><span class="sxs-lookup"><span data-stu-id="69cb5-145">array(string)</span></span> | <span data-ttu-id="69cb5-146">사용자가 템플릿 검색 시 템플릿을 찾는 데 사용할 수 있는 0개 이상의 템플릿 특성.</span><span class="sxs-lookup"><span data-stu-id="69cb5-146">Zero or more characteristics of the template that a user might use to find the template when searching for it.</span></span> <span data-ttu-id="69cb5-147"><code>dotnet new -l&#124;--list</code> 명령을 사용하여 생성된 템플릿 목록에 템플릿이 나타날 때 *태그* 열에 분류도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-147">The classifications also appear in the *Tags* column when it appears in a list of templates produced by using the <code>dotnet new -l&#124;--list</code> command.</span></span> |
| `identity`        | <span data-ttu-id="69cb5-148">string</span><span class="sxs-lookup"><span data-stu-id="69cb5-148">string</span></span>        | <span data-ttu-id="69cb5-149">이 템플릿의 공유한 이름.</span><span class="sxs-lookup"><span data-stu-id="69cb5-149">A unique name for this template.</span></span> |
| `name`            | <span data-ttu-id="69cb5-150">string</span><span class="sxs-lookup"><span data-stu-id="69cb5-150">string</span></span>        | <span data-ttu-id="69cb5-151">사용자에게 표시되어야 하는 템플릿의 이름.</span><span class="sxs-lookup"><span data-stu-id="69cb5-151">The name for the template that users should see.</span></span> |
| `shortName`       | <span data-ttu-id="69cb5-152">string</span><span class="sxs-lookup"><span data-stu-id="69cb5-152">string</span></span>        | <span data-ttu-id="69cb5-153">템플릿 이름이 GUI를 통해 선택되는 것이 아니라 사용자에 의해 지정되는 환경에 적용되는 템플릿을 선택하기 위한 기본 약어.</span><span class="sxs-lookup"><span data-stu-id="69cb5-153">A default shorthand for selecting the template that applies to environments where the template name is specified by the user, not selected via a GUI.</span></span> <span data-ttu-id="69cb5-154">예를 들어 명령 프롬프트에서 템플릿과 CLI 명령을 함께 사용할 경우 짧은 이름이 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-154">For example, the short name is useful when using templates from a command prompt with CLI commands.</span></span> |

#### <a name="example"></a><span data-ttu-id="69cb5-155">예제:</span><span class="sxs-lookup"><span data-stu-id="69cb5-155">Example:</span></span>

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Catalina Garcia",
  "classifications": [ "Common", "Console" ],
  "identity": "GarciaSoftware.ConsoleTemplate.CSharp",
  "name": "Garcia Software Console Application",
  "shortName": "garciaconsole"
}
```

<span data-ttu-id="69cb5-156">*template.json* 파일에 대한 전체 스키마는 [JSON Schema Store](http://json.schemastore.org/template)(JSON 스키마 저장소)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-156">The full schema for the *template.json* file is found at the [JSON Schema Store](http://json.schemastore.org/template).</span></span>

## <a name="net-default-templates"></a><span data-ttu-id="69cb5-157">.NET 기본 템플릿</span><span class="sxs-lookup"><span data-stu-id="69cb5-157">.NET default templates</span></span>

<span data-ttu-id="69cb5-158">[.NET Core SDK](https://www.microsoft.com/net/download/core)를 설치할 때 콘솔 앱, 클래스 라이브러리, 단위 테스트 프로젝트, ASP.NET Core 앱([Angular](https://angular.io/) 및 [React](https://facebook.github.io/react/) 프로젝트 포함) 및 구성 파일을 비롯한 프로젝트 및 파일을 만들 수 있는 12개 이상의 기본 제공 템플릿이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-158">When you install the [.NET Core SDK](https://www.microsoft.com/net/download/core), you receive over a dozen built-in templates for creating projects and files, including console apps, class libraries, unit test projects, ASP.NET Core apps (including [Angular](https://angular.io/) and [React](https://facebook.github.io/react/) projects), and configuration files.</span></span> <span data-ttu-id="69cb5-159">기본 제공 템플릿을 나열하려면 `dotnet new` 명령을 `-l|--list` 옵션과 함께 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-159">To list the built-in templates, execute the `dotnet new` command with the `-l|--list` option:</span></span>

```console
dotnet new -l
```

## <a name="packing-a-template-into-a-nuget-package-nupkg-file"></a><span data-ttu-id="69cb5-160">템플릿을 NuGet 패키지(nupkg 파일)로 압축</span><span class="sxs-lookup"><span data-stu-id="69cb5-160">Packing a template into a NuGet package (nupkg file)</span></span>

<span data-ttu-id="69cb5-161">현재 사용자 지정 템플릿은 Windows에서 [nuget.exe](https://dist.nuget.org/win-x86-commandline/latest/nuget.exe)([dotnet pack](dotnet-pack.md)이 아님)를 사용하여 압축됩니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-161">Currently, a custom template is packed on Windows with [nuget.exe](https://dist.nuget.org/win-x86-commandline/latest/nuget.exe) (not [dotnet pack](dotnet-pack.md)).</span></span> <span data-ttu-id="69cb5-162">플랫폼 간 패키징의 경우 [NuGetizer 3000](https://github.com/NuGet/Home/wiki/NuGetizer-3000)을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-162">For cross-platform packaging, consider using [NuGetizer 3000](https://github.com/NuGet/Home/wiki/NuGetizer-3000).</span></span>

<span data-ttu-id="69cb5-163">프로젝트 폴더의 콘텐츠는 *.template.config/template.json* 파일과 함께 *content* 폴더에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-163">The contents of the project folder, together with its *.template.config/template.json* file, are placed into a folder named *content*.</span></span> <span data-ttu-id="69cb5-164">*content* 폴더 옆에 패키지 콘텐츠를 설명하고 NuGet 패키지를 만드는 프로세스를 적용하는 XML 매니페스트 파일인 [*nuspec* 파일](/nuget/create-packages/creating-a-package)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-164">Next to the *content* folder, add a [*nuspec* file](/nuget/create-packages/creating-a-package), which is an XML manifest file that describes a package's contents and drives the process of creating the NuGet package.</span></span> <span data-ttu-id="69cb5-165">*nuspec* 파일의 **\<packageTypes>** 요소 내부에는 **\<packageType>** 요소와 `Template`의 `name` 특성 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-165">Inside of a **\<packageTypes>** element in the *nuspec* file, include a **\<packageType>** element with a `name` attribute value of `Template`.</span></span> <span data-ttu-id="69cb5-166">*content* 폴더와 *nuspec* 파일은 동일한 디렉터리에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-166">Both the *content* folder and the *nuspec* file should reside in the same directory.</span></span> <span data-ttu-id="69cb5-167">표에서는 템플릿을 NuGet 패키지로 생성하는 데 필요한 최소 *nuspec* 파일 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-167">The table shows the minimum *nuspec* file elements required to produce a template as a NuGet package.</span></span>

| <span data-ttu-id="69cb5-168">요소</span><span class="sxs-lookup"><span data-stu-id="69cb5-168">Element</span></span>            | <span data-ttu-id="69cb5-169">형식</span><span class="sxs-lookup"><span data-stu-id="69cb5-169">Type</span></span>   | <span data-ttu-id="69cb5-170">설명</span><span class="sxs-lookup"><span data-stu-id="69cb5-170">Description</span></span> |
| ------------------ | ------ | ----------- |
| <span data-ttu-id="69cb5-171">**\<authors>**</span><span class="sxs-lookup"><span data-stu-id="69cb5-171">**\<authors>**</span></span>     | <span data-ttu-id="69cb5-172">string</span><span class="sxs-lookup"><span data-stu-id="69cb5-172">string</span></span> | <span data-ttu-id="69cb5-173">nuget.org에서 프로필 이름과 일치하는, 쉼표로 구분된 패키지 작성자 목록입니다. 작성자는 nuget.org의 NuGet 갤러리에 표시되고 동일한 작성자가 패키지를 상호 참조하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-173">A comma-separated list of packages authors, matching the profile names on nuget.org. Authors are displayed in the NuGet Gallery on nuget.org and are used to cross-reference packages by the same authors.</span></span> |
| <span data-ttu-id="69cb5-174">**\<description>**</span><span class="sxs-lookup"><span data-stu-id="69cb5-174">**\<description>**</span></span> | <span data-ttu-id="69cb5-175">string</span><span class="sxs-lookup"><span data-stu-id="69cb5-175">string</span></span> | <span data-ttu-id="69cb5-176">UI 표시를 위한 패키지에 대한 자세한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-176">A long description of the package for UI display.</span></span> |
| <span data-ttu-id="69cb5-177">**\<id>**</span><span class="sxs-lookup"><span data-stu-id="69cb5-177">**\<id>**</span></span>          | <span data-ttu-id="69cb5-178">string</span><span class="sxs-lookup"><span data-stu-id="69cb5-178">string</span></span> | <span data-ttu-id="69cb5-179">nuget.org 또는 무엇이든 패키지가 상주하는 갤러리에서 고유해야 하는 대/소문자를 구분하지 않는 패키지 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-179">The case-insensitive package identifier, which must be unique across nuget.org or whatever gallery the package will reside in.</span></span> <span data-ttu-id="69cb5-180">ID는 URL에 유효하지 않은 공백이나 문자를 포함할 수 없고 일반적으로 .NET 네임스페이스 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-180">IDs may not contain spaces or characters that are not valid for a URL and generally follow .NET namespace rules.</span></span> <span data-ttu-id="69cb5-181">자세한 내용은 [고유한 패키지 식별자 선택 및 버전 번호 설정](/nuget/create-packages/creating-a-package#choosing-a-unique-package-identifier-and-setting-the-version-number)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69cb5-181">See [Choosing a unique package identifier and setting the version number](/nuget/create-packages/creating-a-package#choosing-a-unique-package-identifier-and-setting-the-version-number) for guidance.</span></span> |
| <span data-ttu-id="69cb5-182">**\<packageType>**</span><span class="sxs-lookup"><span data-stu-id="69cb5-182">**\<packageType>**</span></span> | <span data-ttu-id="69cb5-183">string</span><span class="sxs-lookup"><span data-stu-id="69cb5-183">string</span></span> | <span data-ttu-id="69cb5-184">**\<metadata>** 요소 중 **\<packageTypes>** 요소 내부에 이 요소를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-184">Place this element inside a **\<packageTypes>** element among the **\<metadata>** elements.</span></span> <span data-ttu-id="69cb5-185">**\<packageType>** 요소의 `name` 특성을 `Template`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-185">Set the `name` attribute of the **\<packageType>** element to `Template`.</span></span> |
| <span data-ttu-id="69cb5-186">**\<version>**</span><span class="sxs-lookup"><span data-stu-id="69cb5-186">**\<version>**</span></span>     | <span data-ttu-id="69cb5-187">string</span><span class="sxs-lookup"><span data-stu-id="69cb5-187">string</span></span> | <span data-ttu-id="69cb5-188">major.minor.patch 패턴을 따르는 패키지 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-188">The version of the package, following the major.minor.patch pattern.</span></span> <span data-ttu-id="69cb5-189">버전 번호는 [시험판 버전](/nuget/create-packages/prerelease-packages#semantic-versioning) 항목의 설명대로 시험판 접미사를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-189">Version numbers may include a pre-release suffix as described in the [Pre-release versions](/nuget/create-packages/prerelease-packages#semantic-versioning) topic.</span></span> |

<span data-ttu-id="69cb5-190">전체 *nuspec* 파일 스키마는 [.nuspec reference](/nuget/schema/nuspec)(.nuspec 참조)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69cb5-190">See the [.nuspec reference](/nuget/schema/nuspec) for the complete *nuspec* file schema.</span></span> <span data-ttu-id="69cb5-191">템플릿에 대한 예제 *nuspec* 파일은 [dotnet new에 대한 사용자 지정 템플릿 만들기](~/docs/core/tutorials/create-custom-template.md) 자습서에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-191">An example *nuspec* file for a template appears in the [Create a custom template for dotnet new](~/docs/core/tutorials/create-custom-template.md) tutorial.</span></span>

<span data-ttu-id="69cb5-192">`nuget pack <PATH_TO_NUSPEC_FILE>` 명령을 사용하여 [패키지를 만듭니다](/nuget/create-packages/creating-a-package#creating-the-package).</span><span class="sxs-lookup"><span data-stu-id="69cb5-192">[Create a package](/nuget/create-packages/creating-a-package#creating-the-package) using the `nuget pack <PATH_TO_NUSPEC_FILE>` command.</span></span>

## <a name="installing-a-template"></a><span data-ttu-id="69cb5-193">템플릿 설치</span><span class="sxs-lookup"><span data-stu-id="69cb5-193">Installing a template</span></span>

<span data-ttu-id="69cb5-194">*nupkg* 파일을 직접 참조하거나 템플릿 구성이 포함된 파일 시스템 디렉터리를 지정하여 NuGet 피드의 NuGet 패키지에서 사용자 지정 템플릿을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-194">Install a custom template from a NuGet package on any NuGet feed by referencing a *nupkg* file directly or by specifying a file system directory that contains a templating configuration.</span></span> <span data-ttu-id="69cb5-195">`-i|--install` 옵션을 [dotnet new](dotnet-new.md) 명령과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-195">Use the `-i|--install` option with the [dotnet new](dotnet-new.md) command.</span></span>

### <a name="to-install-a-template-from-a-nuget-package-stored-at-nugetorg"></a><span data-ttu-id="69cb5-196">nuget.org에 저장된 NuGet 패키지에서 템플릿을 설치하려면</span><span class="sxs-lookup"><span data-stu-id="69cb5-196">To install a template from a NuGet package stored at nuget.org</span></span>

```console
dotnet new -i <NUGET_PACKAGE_ID>
```

### <a name="to-install-a-template-from-a-local-nupkg-file"></a><span data-ttu-id="69cb5-197">로컬 nupkg 파일에서 템플릿을 설치하려면</span><span class="sxs-lookup"><span data-stu-id="69cb5-197">To install a template from a local nupkg file</span></span>

```console
dotnet new -i <PATH_TO_NUPKG_FILE>
```

### <a name="to-install-a-template-from-a-file-system-directory"></a><span data-ttu-id="69cb5-198">파일 시스템 디렉터리에서 템플릿을 설치하려면</span><span class="sxs-lookup"><span data-stu-id="69cb5-198">To install a template from a file system directory</span></span>

<span data-ttu-id="69cb5-199">`FILE_SYSTEM_DIRECTORY`는 프로젝트 및 *.template.config* 폴더가 포함된 프로젝트 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-199">The `FILE_SYSTEM_DIRECTORY` is the project folder containing the project and the *.template.config* folder:</span></span>

```console
dotnet new -i <FILE_SYSTEM_DIRECTORY>
```

## <a name="uninstalling-a-template"></a><span data-ttu-id="69cb5-200">템플릿 제거</span><span class="sxs-lookup"><span data-stu-id="69cb5-200">Uninstalling a template</span></span>

<span data-ttu-id="69cb5-201">`id`를 통해 NuGet 패키지를 참조하거나 템플릿 구성이 포함된 파일 시스템 디렉터리를 지정하여 사용자 지정 템플릿을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-201">Uninstall a custom template by referencing a NuGet package by its `id` or by specifying a file system directory that contains a templating configuration.</span></span> <span data-ttu-id="69cb5-202">`-u|--uninstall` 설치 옵션을 [dotnet new](dotnet-new.md) 명령과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-202">Use the `-u|--uninstall` install option with the [dotnet new](dotnet-new.md) command.</span></span>

### <a name="to-uninstall-a-template-from-a-nuget-package-stored-at-nugetorg"></a><span data-ttu-id="69cb5-203">nuget.org에 저장된 NuGet 패키지에서 템플릿을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="69cb5-203">To uninstall a template from a NuGet package stored at nuget.org</span></span>

```console
dotnet new -u <NUGET_PACKAGE_ID>
```

### <a name="to-uninstall-a-template-from-a-local-nupkg-file"></a><span data-ttu-id="69cb5-204">로컬 nupkg 파일에서 템플릿을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="69cb5-204">To uninstall a template from a local nupkg file</span></span>

<span data-ttu-id="69cb5-205">템플릿을 제거하려는 경우 *nupkg* 파일의 경로를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="69cb5-205">When you wish to uninstall the template, don't attempt to use the path to the *nupkg* file.</span></span> <span data-ttu-id="69cb5-206">*`dotnet new -u <PATH_TO_NUPKG_FILE>`을 사용하여 템플릿을 제거하는 시도가 실패합니다.*</span><span class="sxs-lookup"><span data-stu-id="69cb5-206">*Attempting to uninstall a template using `dotnet new -u <PATH_TO_NUPKG_FILE>` fails.*</span></span> <span data-ttu-id="69cb5-207">`id`를 통해 패키지를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-207">Reference the package by its `id`:</span></span>

```console
dotnet new -u <NUGET_PACKAGE_ID>
```

### <a name="to-uninstall-a-template-from-a-file-system-directory"></a><span data-ttu-id="69cb5-208">파일 시스템 디렉터리에서 템플릿을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="69cb5-208">To uninstall a template from a file system directory</span></span>

<span data-ttu-id="69cb5-209">`FILE_SYSTEM_DIRECTORY`는 프로젝트 및 *.template.config* 폴더가 포함된 프로젝트 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-209">The `FILE_SYSTEM_DIRECTORY` is the project folder containing the project and the *.template.config* folder:</span></span>

```console
dotnet new -u <FILE_SYSTEM_DIRECTORY>
```

## <a name="create-a-project-using-a-custom-template"></a><span data-ttu-id="69cb5-210">사용자 지정 템플릿을 사용하여 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="69cb5-210">Create a project using a custom template</span></span>

<span data-ttu-id="69cb5-211">템플릿이 설치된 후 다른 미리 설치된 템플릿을 사용하는 것처럼 `dotnet new <TEMPLATE>` 명령을 실행하여 템플릿을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-211">After a template is installed, use the template by executing the `dotnet new <TEMPLATE>` command as you would with any other pre-installed template.</span></span> <span data-ttu-id="69cb5-212">템플릿 설정에서 구성한 템플릿 관련 옵션을 포함하여 `dotnet new` 명령에 대한 [옵션](dotnet-new.md#options)을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-212">You can also specify [options](dotnet-new.md#options) to the `dotnet new` command, including template specific options you configured in the template settings.</span></span> <span data-ttu-id="69cb5-213">템플릿의 짧은 이름을 직접 명령에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="69cb5-213">Supply the template's short name directly to the command:</span></span>

```console
dotnet new <TEMPLATE>
```

## <a name="see-also"></a><span data-ttu-id="69cb5-214">참고 항목</span><span class="sxs-lookup"><span data-stu-id="69cb5-214">See also</span></span>

[<span data-ttu-id="69cb5-215">dotnet new에 대한 사용자 지정 템플릿(자습서)</span><span class="sxs-lookup"><span data-stu-id="69cb5-215">Create a custom template for dotnet new (tutorial)</span></span>](../tutorials/create-custom-template.md)  
<span data-ttu-id="69cb5-216">[dotnet/templating GitHub repo Wiki](https://github.com/dotnet/templating/wiki)(dotnet/templating GitHub 리포지토리 Wiki)</span><span class="sxs-lookup"><span data-stu-id="69cb5-216">[dotnet/templating GitHub repo Wiki](https://github.com/dotnet/templating/wiki)</span></span>  
<span data-ttu-id="69cb5-217">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)(dotnet/dotnet-template-samples GitHub 리포지토리)</span><span class="sxs-lookup"><span data-stu-id="69cb5-217">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)</span></span>  
<span data-ttu-id="69cb5-218">[How to create your own templates for dotnet new](https://blogs.msdn.microsoft.com/dotnet/2017/04/02/how-to-create-your-own-templates-for-dotnet-new/)(dotnet new에 대한 사용자 지정 템플릿을 만드는 방법)</span><span class="sxs-lookup"><span data-stu-id="69cb5-218">[How to create your own templates for dotnet new](https://blogs.msdn.microsoft.com/dotnet/2017/04/02/how-to-create-your-own-templates-for-dotnet-new/)</span></span>  
[<span data-ttu-id="69cb5-219">*template.json* JSON 스키마 저장소에 대 한 스키마</span><span class="sxs-lookup"><span data-stu-id="69cb5-219">*template.json* schema at the JSON Schema Store</span></span>](http://json.schemastore.org/template)  
