---
title: dotnet new에 대한 사용자 지정 템플릿 만들기
description: 이 재미있는 자습서에서 dotnet new 명령에 대한 사용자 지정 템플릿을 만드는 방법을 알아봅니다.
author: guardrex
ms.author: mairaw
ms.date: 08/12/2017
ms.openlocfilehash: fee2709f54395b9926dae904a448cb92aafb5172
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33218084"
---
# <a name="create-a-custom-template-for-dotnet-new"></a><span data-ttu-id="2b442-103">dotnet new에 대한 사용자 지정 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="2b442-103">Create a custom template for dotnet new</span></span>

<span data-ttu-id="2b442-104">이 자습서에서는 다음을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-104">This tutorial shows you how to:</span></span>

- <span data-ttu-id="2b442-105">기존 프로젝트 또는 새 콘솔 앱 프로젝트에서 기본 템플릿을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-105">Create a basic template from an existing project or a new console app project.</span></span>
- <span data-ttu-id="2b442-106">nuget.org 또는 로컬 *nupkg* 파일을 통해 배포하기 위해 템플릿을 압축합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-106">Pack the template for distribution at nuget.org or from a local *nupkg* file.</span></span>
- <span data-ttu-id="2b442-107">nuget.org, 로컬 *nupkg* 파일 또는 로컬 파일 시스템에서 템플릿을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-107">Install the template from nuget.org, a local *nupkg* file, or the local file system.</span></span>
- <span data-ttu-id="2b442-108">템플릿을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-108">Uninstall the template.</span></span>

<span data-ttu-id="2b442-109">전체 샘플에 대한 자습서를 수행하려면 [샘플 프로젝트 템플릿](https://github.com/dotnet/dotnet-template-samples/tree/master/16-nuget-package)을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-109">If you prefer to proceed through the tutorial with a complete sample, download the [sample project template](https://github.com/dotnet/dotnet-template-samples/tree/master/16-nuget-package).</span></span> <span data-ttu-id="2b442-110">샘플 템플릿은 NuGet 배포에 사용되도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-110">The sample template is configured for NuGet distribution.</span></span>

<span data-ttu-id="2b442-111">다운로드된 샘플을 파일 시스템 배포에서 사용하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-111">If you wish to use the downloaded sample with file system distribution, do the following:</span></span>

- <span data-ttu-id="2b442-112">샘플의 *content* 폴더를 한 수준 위의 *GarciaSoftware.ConsoleTemplate.CSharp* 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-112">Move the contents of the *content* folder of the sample up one level into the *GarciaSoftware.ConsoleTemplate.CSharp* folder.</span></span>
- <span data-ttu-id="2b442-113">빈 *content* 폴더를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-113">Delete the empty *content* folder.</span></span>
- <span data-ttu-id="2b442-114">*nuspec* 파일을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-114">Delete the *nuspec* file.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2b442-115">전제 조건</span><span class="sxs-lookup"><span data-stu-id="2b442-115">Prerequisites</span></span>

- <span data-ttu-id="2b442-116">[.NET Core 2.0 SDK](https://www.microsoft.com/net/core) 이상 버전을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-116">Install the [.NET Core 2.0 SDK](https://www.microsoft.com/net/core) or later versions.</span></span>
- <span data-ttu-id="2b442-117">참조 항목 [dotnet new에 대한 사용자 지정 템플릿](../tools/custom-templates.md)을 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="2b442-117">Read the reference topic [Custom templates for dotnet new](../tools/custom-templates.md).</span></span>

## <a name="create-a-template-from-a-project"></a><span data-ttu-id="2b442-118">프로젝트에서 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="2b442-118">Create a template from a project</span></span>

<span data-ttu-id="2b442-119">컴파일 및 실행되는 것으로 확인한 기존 프로젝트를 사용하거나 하드 드라이브의 폴더에서 새 콘솔 앱 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-119">Use an existing project that you've confirmed compiles and runs, or create a new console app project in a folder on your hard drive.</span></span> <span data-ttu-id="2b442-120">이 자습서에서는 프로젝트 폴더 이름은 사용자 프로필의 *Documents\Templates*에 저장된 *GarciaSoftware.ConsoleTemplate.CSharp*입니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-120">This tutorial assumes that the name of the project folder is *GarciaSoftware.ConsoleTemplate.CSharp* stored at *Documents\Templates* in the user's profile.</span></span> <span data-ttu-id="2b442-121">이 자습서의 프로젝트 템플릿 이름은 *\<회사 이름>.\<템플릿 형식>.\<프로그래밍 언어>* 이지만, 프로젝트와 템플릿에 원하는 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-121">The tutorial project template name is in the format *\<Company Name>.\<Template Type>.\<Programming Language>*, but you're free to name your project and template anything you wish.</span></span>

1. <span data-ttu-id="2b442-122">프로젝트의 루트에 *.template.config*라는 폴더를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-122">Add a folder to the root of the project named *.template.config*.</span></span>
1. <span data-ttu-id="2b442-123">*.template.config* 폴더 내부에서 *template.json* 파일을 만들어 템플릿을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-123">Inside the *.template.config* folder, create a *template.json* file to configure your template.</span></span> <span data-ttu-id="2b442-124">에 대 한 자세한 정보와 멤버 정의 대 한는 *template.json* 파일, 참조는 [새 dotnet 용 사용자 지정 템플릿](../tools/custom-templates.md#templatejson) 항목 및 [ *template.json* JSON 스키마 저장소에서 스키마](http://json.schemastore.org/template)합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-124">For more information and member definitions for the *template.json* file, see the [Custom templates for dotnet new](../tools/custom-templates.md#templatejson) topic and the [*template.json* schema at the JSON Schema Store](http://json.schemastore.org/template).</span></span>

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

<span data-ttu-id="2b442-125">템플릿이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-125">The template is finished.</span></span> <span data-ttu-id="2b442-126">현재는 템플릿 배포를 위한 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-126">At this point, you have two options for template distribution.</span></span> <span data-ttu-id="2b442-127">이 자습서를 계속하려면 어느 것이든 경로를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-127">To continue this tutorial, choose one path or the other:</span></span>

1. <span data-ttu-id="2b442-128">[NuGet 배포](#use-nuget-distribution): NuGet 또는 로컬 *nupkg* 파일에서 템플릿을 설치하고 설치된 템플릿을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-128">[NuGet distribution](#use-nuget-distribution): install the template from NuGet or from the local *nupkg* file, and use the installed template.</span></span>
2. <span data-ttu-id="2b442-129">[파일 시스템 배포](#use-file-system-distribution).</span><span class="sxs-lookup"><span data-stu-id="2b442-129">[File system distribution](#use-file-system-distribution).</span></span>

## <a name="use-nuget-distribution"></a><span data-ttu-id="2b442-130">NuGet 배포 사용</span><span class="sxs-lookup"><span data-stu-id="2b442-130">Use NuGet Distribution</span></span>

### <a name="pack-the-template-into-a-nuget-package"></a><span data-ttu-id="2b442-131">템플릿을 NuGet 패키지로 압축</span><span class="sxs-lookup"><span data-stu-id="2b442-131">Pack the template into a NuGet package</span></span>

1. <span data-ttu-id="2b442-132">NuGet 패키지에 대한 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-132">Create a folder for the NuGet package.</span></span> <span data-ttu-id="2b442-133">자습서의 경우 폴더 이름 *GarciaSoftware.ConsoleTemplate.CSharp*가 사용되고 폴더는 사용자 프로필의 *Documents\NuGetTemplates* 폴더 내부에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-133">For the tutorial, the folder name *GarciaSoftware.ConsoleTemplate.CSharp* is used, and the folder is created inside a *Documents\NuGetTemplates* folder in the user's profile.</span></span> <span data-ttu-id="2b442-134">새 템플릿 폴더 내부에 *content*라는 폴더를 만들어 프로젝트 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-134">Create a folder named *content* inside of the new template folder to hold the project files.</span></span>
1. <span data-ttu-id="2b442-135">프로젝트 폴더의 콘텐츠와 함께 *.template.config/template.json* 파일을 직접 만든 *content* 폴더로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-135">Copy the contents of your project folder, together with its *.template.config/template.json* file, into the *content* folder you created.</span></span>
1. <span data-ttu-id="2b442-136">*콘텐츠* 폴더 옆에 [*nuspec* 파일](/nuget/create-packages/creating-a-package)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-136">Next to the *content* folder, add a [*nuspec* file](/nuget/create-packages/creating-a-package).</span></span> <span data-ttu-id="2b442-137">패키지 콘텐츠를 설명하고 NuGet 패키지를 만드는 프로세스를 적용하는 XML 매니페스트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-137">The nuspec file is an XML manifest file that describes a package's contents and drives the process of creating the NuGet package.</span></span>
   
   ![NuGet 패키지의 레이아웃을 보여 주는 디렉터리 구조](./media/create-custom-template/nugetdirectorylayout.png)

1. <span data-ttu-id="2b442-139">*nuspec* 파일의 **\<packageTypes>** 요소 내부에는 **\<packageType>** 요소와 `Template`의 `name` 특성 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-139">Inside of a **\<packageTypes>** element in the *nuspec* file, include a **\<packageType>** element with a `name` attribute value of `Template`.</span></span> <span data-ttu-id="2b442-140">*content* 폴더와 *nuspec* 파일은 동일한 디렉터리에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-140">Both the *content* folder and the *nuspec* file should reside in the same directory.</span></span> <span data-ttu-id="2b442-141">표에서는 템플릿을 NuGet 패키지로 생성하는 데 필요한 최소 *nuspec* 파일 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-141">The table shows the minimum *nuspec* file elements required to produce a template as a NuGet package.</span></span>

   | <span data-ttu-id="2b442-142">요소</span><span class="sxs-lookup"><span data-stu-id="2b442-142">Element</span></span>            | <span data-ttu-id="2b442-143">형식</span><span class="sxs-lookup"><span data-stu-id="2b442-143">Type</span></span>   | <span data-ttu-id="2b442-144">설명</span><span class="sxs-lookup"><span data-stu-id="2b442-144">Description</span></span> |
   | ------------------ | ------ | ----------- |
   | <span data-ttu-id="2b442-145">**\<authors>**</span><span class="sxs-lookup"><span data-stu-id="2b442-145">**\<authors>**</span></span>     | <span data-ttu-id="2b442-146">string</span><span class="sxs-lookup"><span data-stu-id="2b442-146">string</span></span> | <span data-ttu-id="2b442-147">nuget.org에서 프로필 이름과 일치하는, 쉼표로 구분된 패키지 작성자 목록입니다. 작성자는 nuget.org의 NuGet 갤러리에 표시되고 동일한 작성자가 패키지를 상호 참조하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-147">A comma-separated list of packages authors, matching the profile names on nuget.org. Authors are displayed in the NuGet Gallery on nuget.org and are used to cross-reference packages by the same authors.</span></span> |
   | <span data-ttu-id="2b442-148">**\<description>**</span><span class="sxs-lookup"><span data-stu-id="2b442-148">**\<description>**</span></span> | <span data-ttu-id="2b442-149">string</span><span class="sxs-lookup"><span data-stu-id="2b442-149">string</span></span> | <span data-ttu-id="2b442-150">UI 표시를 위한 패키지에 대한 자세한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-150">A long description of the package for UI display.</span></span> |
   | <span data-ttu-id="2b442-151">**\<id>**</span><span class="sxs-lookup"><span data-stu-id="2b442-151">**\<id>**</span></span>          | <span data-ttu-id="2b442-152">string</span><span class="sxs-lookup"><span data-stu-id="2b442-152">string</span></span> | <span data-ttu-id="2b442-153">nuget.org 또는 무엇이든 패키지가 상주하는 갤러리에서 고유해야 하는 대/소문자를 구분하지 않는 패키지 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-153">The case-insensitive package identifier, which must be unique across nuget.org or whatever gallery the package will reside in.</span></span> <span data-ttu-id="2b442-154">ID는 URL에 유효하지 않은 공백이나 문자를 포함할 수 없고 일반적으로 .NET 네임스페이스 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-154">IDs may not contain spaces or characters that are not valid for a URL and generally follow .NET namespace rules.</span></span> <span data-ttu-id="2b442-155">자세한 내용은 [고유한 패키지 식별자 선택 및 버전 번호 설정](/nuget/create-packages/creating-a-package#choosing-a-unique-package-identifier-and-setting-the-version-number)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b442-155">See [Choosing a unique package identifier and setting the version number](/nuget/create-packages/creating-a-package#choosing-a-unique-package-identifier-and-setting-the-version-number) for guidance.</span></span> |
   | <span data-ttu-id="2b442-156">**\<packageType>**</span><span class="sxs-lookup"><span data-stu-id="2b442-156">**\<packageType>**</span></span> | <span data-ttu-id="2b442-157">string</span><span class="sxs-lookup"><span data-stu-id="2b442-157">string</span></span> | <span data-ttu-id="2b442-158">**\<metadata>** 요소 중 **\<packageTypes>** 요소 내부에 이 요소를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-158">Place this element inside a **\<packageTypes>** element among the **\<metadata>** elements.</span></span> <span data-ttu-id="2b442-159">**\<packageType>** 요소의 `name` 특성을 `Template`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-159">Set the `name` attribute of the **\<packageType>** element to `Template`.</span></span> |
   | <span data-ttu-id="2b442-160">**\<version>**</span><span class="sxs-lookup"><span data-stu-id="2b442-160">**\<version>**</span></span>     | <span data-ttu-id="2b442-161">string</span><span class="sxs-lookup"><span data-stu-id="2b442-161">string</span></span> | <span data-ttu-id="2b442-162">major.minor.patch 패턴을 따르는 패키지 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-162">The version of the package, following the major.minor.patch pattern.</span></span> <span data-ttu-id="2b442-163">버전 번호는 [시험판 버전](/nuget/create-packages/prerelease-packages#semantic-versioning)의 설명대로 시험판 접미사를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-163">Version numbers may include a pre-release suffix as described in [Pre-release versions](/nuget/create-packages/prerelease-packages#semantic-versioning).</span></span> |

   <span data-ttu-id="2b442-164">전체 *nuspec* 파일 스키마는 [.nuspec reference](/nuget/schema/nuspec)(.nuspec 참조)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b442-164">See the [.nuspec reference](/nuget/schema/nuspec) for the complete *nuspec* file schema.</span></span>

   <span data-ttu-id="2b442-165">자습서에 사용된 *nuspec* 파일의 이름은 *GarciaSoftware.ConsoleTemplate.CSharp.nuspec*이고 이 파일은 다음 콘텐츠를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-165">The *nuspec* file for the tutorial is named *GarciaSoftware.ConsoleTemplate.CSharp.nuspec* and contains the following content:</span></span>

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <package xmlns="http://schemas.microsoft.com/packaging/2012/06/nuspec.xsd">
     <metadata>
       <id>GarciaSoftware.ConsoleTemplate.CSharp</id>
       <version>1.0.0</version>
       <description>
         Creates the Garcia Software console app.
       </description>
       <authors>Catalina Garcia</authors>
       <packageTypes>
         <packageType name="Template" />
       </packageTypes>
     </metadata>
   </package>
   ```

1. <span data-ttu-id="2b442-166">`nuget pack <PATH_TO_NUSPEC_FILE>` 명령을 사용하여 [패키지를 만듭니다](/nuget/create-packages/creating-a-package#creating-the-package).</span><span class="sxs-lookup"><span data-stu-id="2b442-166">[Create the package](/nuget/create-packages/creating-a-package#creating-the-package) using the `nuget pack <PATH_TO_NUSPEC_FILE>` command.</span></span> <span data-ttu-id="2b442-167">다음 명령은 NuGet 자산을 저장하는 폴더가 *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp*라고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-167">The following command assumes that the folder that holds the NuGet assets is at *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp*.</span></span> <span data-ttu-id="2b442-168">하지만 시스템에서 폴더가 어디에 있든지 `nuget pack` 명령은 *nuspec* 파일의 경로를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-168">But wherever you place the folder on your system, the `nuget pack` command accepts the path to the *nuspec* file:</span></span>

   ```console
   nuget pack C:\Users\<USER>\Documents\NuGetTemplates\GarciaSoftware.ConsoleTemplate.CSharp\GarciaSoftware.ConsoleTemplate.CSharp.nuspec
   ```

### <a name="publishing-the-package-to-nugetorg"></a><span data-ttu-id="2b442-169">nuget.org에 패키지 게시</span><span class="sxs-lookup"><span data-stu-id="2b442-169">Publishing the package to nuget.org</span></span>

<span data-ttu-id="2b442-170">NuGet 패키지를 게시하려면 [패키지 만들기 및 게시](/nuget/quickstart/create-and-publish-a-package#publish-the-package) 항목의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-170">To publish a NuGet package, follow the instructions in the [Create and publish a package](/nuget/quickstart/create-and-publish-a-package#publish-the-package) topic.</span></span> <span data-ttu-id="2b442-171">그러나 게시된 후에는 삭제할 수 없고 목록에서만 제거되므로 자습서 템플릿을 NuGet에 게시하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-171">However, we recommend that you don't publish the tutorial template to NuGet as it can never be deleted once published, only delisted.</span></span> <span data-ttu-id="2b442-172">이제 *nupkg* 파일 형식의 NuGet 패키지가 준비되었으므로 아래 지침에 따라 로컬 *nupkg* 파일에서 직접 템플릿을 설치해 보세요.</span><span class="sxs-lookup"><span data-stu-id="2b442-172">Now that you have the NuGet package in the form of a *nupkg* file, we suggest that you follow the instructions below to install the template directly from the local *nupkg* file.</span></span>

### <a name="install-the-template-from-a-nuget-package"></a><span data-ttu-id="2b442-173">NuGet 패키지에서 템플릿 설치</span><span class="sxs-lookup"><span data-stu-id="2b442-173">Install the template from a NuGet package</span></span>

#### <a name="install-the-template-from-the-local-nupkg-file"></a><span data-ttu-id="2b442-174">로컬 *nupkg* 파일에서 템플릿 설치</span><span class="sxs-lookup"><span data-stu-id="2b442-174">Install the template from the local *nupkg* file</span></span>

<span data-ttu-id="2b442-175">직접 생성한 *nupkg* 파일에서 템플릿을 설치하려면 `dotnet new` 명령과 `-i|--install` 옵션을 함께 사용하고 *nupkg* 파일 경로를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-175">To install the template from the *nupkg* file that you produced, use the `dotnet new` command with the `-i|--install` option and provide the path to the *nupkg* file:</span></span>

```console
dotnet new -i C:\Users\<USER>\GarciaSoftware.ConsoleTemplate.CSharp.1.0.0.nupkg
```

#### <a name="install-the-template-from-a-nuget-package-stored-at-nugetorg"></a><span data-ttu-id="2b442-176">nuget.org에 저장된 NuGet 패키지에서 템플릿 설치</span><span class="sxs-lookup"><span data-stu-id="2b442-176">Install the template from a NuGet package stored at nuget.org</span></span>

<span data-ttu-id="2b442-177">nuget.org에 저장된 NuGet 패키지에서 템플릿을 설치하려면 `dotnet new` 명령을 `-i|--install` 옵션과 함께 사용하고 NuGet 패키지 이름을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-177">If you wish to install a template from a NuGet package stored at nuget.org, use the `dotnet new` command with the `-i|--install` option and supply the name of the NuGet package:</span></span>

```console
dotnet new -i GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> <span data-ttu-id="2b442-178">예제는 데모용으로만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-178">The example is for demonstration purposes only.</span></span> <span data-ttu-id="2b442-179">nuget.org에는 `GarciaSoftware.ConsoleTemplate.CSharp` NuGet 패키지가 없으므로 NuGet에서 테스트 템플릿을 게시 및 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-179">There isn't a `GarciaSoftware.ConsoleTemplate.CSharp` NuGet package at nuget.org, and we don't recommend that you publish and consume test templates from NuGet.</span></span> <span data-ttu-id="2b442-180">명령을 실행해도 템플릿이 설치되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-180">If you run the command, no template is installed.</span></span> <span data-ttu-id="2b442-181">그러나 이전 섹션 [로컬 nupkg 파일에서 템플릿 설치](#install-the-template-from-the-local-nupkg-file)에 설명된 대로 로컬 파일 시스템에서 직접 *nupkg* 파일을 참조하면 nuget.org에 게시되지 않은 템플릿을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-181">However, you can install a template that hasn't been published to nuget.org by referencing the *nupkg* file directly on your local file system as shown in the previous section [Install the template from the local nupkg file](#install-the-template-from-the-local-nupkg-file).</span></span>

<span data-ttu-id="2b442-182">nuget.org의 패키지에서 템플릿을 설치하는 방법의 생생한 예제를 확인하려면 [NUnit 3 template for dotnet-new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/)(dotnet-new에 대한 NUnit 3 템플릿)를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-182">If you'd like a live example of how to install a template from a package at nuget.org, you can use the [NUnit 3 template for dotnet-new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/).</span></span> <span data-ttu-id="2b442-183">이 템플릿은 NUnit 유닛 테스트를 사용하도록 프로젝트를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-183">This template sets up a project to use NUnit unit testing.</span></span> <span data-ttu-id="2b442-184">다음 명령을 사용하여 템플릿을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-184">Use the following command to install it:</span></span>

```console
dotnet new -i NUnit3.DotNetNew.Template
```

<span data-ttu-id="2b442-185">`dotnet new -l`을 사용하여 템플릿을 나열하면 템플릿 목록에서 *nunit*의 짧은 이름을 가진 *NUnit 3 테스트 프로젝트*가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-185">When you list the templates with `dotnet new -l`, you see the *NUnit 3 Test Project* with a short name of *nunit* in the template list.</span></span> <span data-ttu-id="2b442-186">다음 섹션에서 템플릿을 사용할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-186">You're ready to use the template in the next section.</span></span>

![다른 설치된 템플릿과 함께 NUnit 템플릿을 보여 주는 콘솔 창](./media/create-custom-template/nunit1.png)

### <a name="create-a-project-from-the-template"></a><span data-ttu-id="2b442-188">템플릿에서 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="2b442-188">Create a project from the template</span></span>

<span data-ttu-id="2b442-189">NuGet에서 템플릿이 설치된 후 템플릿 엔진의 출력을 배치할 디렉터리에서 `dotnet new <TEMPLATE>` 명령을 실행하여 템플릿을 사용합니다(`-o|--output` 옵션을 사용하여 특정 디렉터리를 지정하는 경우 제외).</span><span class="sxs-lookup"><span data-stu-id="2b442-189">After the template is installed from NuGet, use the template by executing the `dotnet new <TEMPLATE>` command from the directory where you want to the template engine's output placed (unless you're using the `-o|--output` option to specify a specific directory).</span></span> <span data-ttu-id="2b442-190">자세한 내용은 [`dotnet new` 옵션](~/docs/core/tools/dotnet-new.md#options)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b442-190">For more information, see [`dotnet new` Options](~/docs/core/tools/dotnet-new.md#options).</span></span> <span data-ttu-id="2b442-191">템플릿의 짧은 이름을 `dotnet new` 명령에 직접 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-191">Supply the template's short name directly to the `dotnet new` command.</span></span> <span data-ttu-id="2b442-192">NUnit 템플릿에서 프로젝트를 만들려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-192">To create a project from the NUnit template, run the following command:</span></span>

```console
dotnet new nunit
```

<span data-ttu-id="2b442-193">콘솔에서는 프로젝트가 만들어지고 프로젝트의 패키지가 복원되는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-193">The console shows that the project is created and that the project's packages are restored.</span></span> <span data-ttu-id="2b442-194">명령이 실행된 후 프로젝트를 사용할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-194">After the command is run, the project is ready for use.</span></span>

![NUnit 프로젝트를 만들고 프로젝트 종속성을 복원할 때 dotnet new 명령의 출력을 보여 주는 콘솔 창](./media/create-custom-template/nunit2.png)

### <a name="to-uninstall-a-template-from-a-nuget-package-stored-at-nugetorg"></a><span data-ttu-id="2b442-196">nuget.org에 저장된 NuGet 패키지에서 템플릿을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="2b442-196">To uninstall a template from a NuGet package stored at nuget.org</span></span>

```console
dotnet new -u GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> <span data-ttu-id="2b442-197">예제는 데모용으로만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-197">The example is for demonstration purposes only.</span></span> <span data-ttu-id="2b442-198">nuget.org에 저장되거나 .NET Core SDK와 함께 설치되는 `GarciaSoftware.ConsoleTemplate.CSharp` NuGet 패키지는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-198">There isn't a `GarciaSoftware.ConsoleTemplate.CSharp` NuGet package at nuget.org or installed with the .NET Core SDK.</span></span> <span data-ttu-id="2b442-199">명령을 실행하면 패키지/템플릿이 제거되지 않고 다음 예외가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-199">If you run the command, no package/template is uninstalled and you receive the following exception:</span></span>
> 
> > <span data-ttu-id="2b442-200">'GarciaSoftware.ConsoleTemplate.CSharp'라는 제거할 항목을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-200">Could not find something to uninstall called 'GarciaSoftware.ConsoleTemplate.CSharp'.</span></span>

<span data-ttu-id="2b442-201">이미 설치한 [dotnet-new에 대한 NUnit 3 템플릿](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/)을 제거하려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-201">If you installed the [NUnit 3 template for dotnet-new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/) and wish to uninstall it, use the following command:</span></span>

```console
dotnet new -u NUnit3.DotNetNew.Template
```

### <a name="uninstall-the-template-from-a-local-nupkg-file"></a><span data-ttu-id="2b442-202">로컬 nupkg 파일에서 템플릿 제거</span><span class="sxs-lookup"><span data-stu-id="2b442-202">Uninstall the template from a local nupkg file</span></span>

<span data-ttu-id="2b442-203">템플릿을 제거하려는 경우 *nupkg* 파일의 경로를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="2b442-203">When you wish to uninstall the template, don't attempt to use the path to the *nupkg* file.</span></span> <span data-ttu-id="2b442-204">*`dotnet new -u <PATH_TO_NUPKG_FILE>`을 사용하여 템플릿을 제거하는 시도가 실패합니다.*</span><span class="sxs-lookup"><span data-stu-id="2b442-204">*Attempting to uninstall a template using `dotnet new -u <PATH_TO_NUPKG_FILE>` fails.*</span></span> <span data-ttu-id="2b442-205">`id`를 통해 패키지를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-205">Reference the package by its `id`:</span></span>

```console
dotnet new -u GarciaSoftware.ConsoleTemplate.CSharp.1.0.0
```

## <a name="use-file-system-distribution"></a><span data-ttu-id="2b442-206">파일 시스템 배포 사용</span><span class="sxs-lookup"><span data-stu-id="2b442-206">Use file system distribution</span></span>

<span data-ttu-id="2b442-207">템플릿을 배포하려면 프로젝트 템플릿 폴더를 네트워크에서 사용자가 액세스할 수 있는 위치에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-207">To distribute the template, place the project template folder in a location accessible to users on your network.</span></span> <span data-ttu-id="2b442-208">`dotnet new` 명령을 `-i|--install` 옵션과 함께 사용하여 템플릿 폴더(프로젝트 및 *.template.config* 폴더가 포함된 프로젝트 폴더)의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-208">Use the `dotnet new` command with the `-i|--install` option and specify the path to the template folder (the project folder containing the project and the *.template.config* folder).</span></span>

<span data-ttu-id="2b442-209">이 자습서에서는 프로젝트 템플릿이 사용자 프로필의 *Documents/Templates* 폴더에 저장된다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-209">The tutorial assumes the project template is stored in the *Documents/Templates* folder of the user's profile.</span></span> <span data-ttu-id="2b442-210">해당 위치에서 \<USER>를 사용자의 프로필 이름으로 바꾸는 다음 명령을 사용하여 템플릿을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-210">From that location, install the template with the following command replacing \<USER> with the user's profile name:</span></span>

```console
dotnet new -i C:\Users\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp
```

### <a name="create-a-project-from-the-template"></a><span data-ttu-id="2b442-211">템플릿에서 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="2b442-211">Create a project from the template</span></span>

<span data-ttu-id="2b442-212">파일 시스템에서 템플릿이 설치된 후 템플릿 엔진의 출력을 배치할 디렉터리에서 `dotnet new <TEMPLATE>` 명령을 실행하여 템플릿을 사용합니다(`-o|--output` 옵션을 사용하여 특정 디렉터리를 지정하는 경우 제외).</span><span class="sxs-lookup"><span data-stu-id="2b442-212">After the template is installed from the file system, use the template by executing the `dotnet new <TEMPLATE>` command from the directory where you want to the template engine's output placed (unless you're using the `-o|--output` option to specify a specific directory).</span></span> <span data-ttu-id="2b442-213">자세한 내용은 [`dotnet new` 옵션](~/docs/core/tools/dotnet-new.md#options)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b442-213">For more information, see [`dotnet new` Options](~/docs/core/tools/dotnet-new.md#options).</span></span> <span data-ttu-id="2b442-214">템플릿의 짧은 이름을 `dotnet new` 명령에 직접 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-214">Supply the template's short name directly to the `dotnet new` command.</span></span>

<span data-ttu-id="2b442-215">*C:\Users\\\<USER>\Documents\Projects\MyConsoleApp*에 만들어진 새 프로젝트 폴더에서 `garciaconsole` 템플릿을 기반으로 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-215">From a new project folder created at *C:\Users\\\<USER>\Documents\Projects\MyConsoleApp*, create a project from the `garciaconsole` template:</span></span>

```console
dotnet new garciaconsole
```

### <a name="uninstall-the-template"></a><span data-ttu-id="2b442-216">템플릿 제거</span><span class="sxs-lookup"><span data-stu-id="2b442-216">Uninstall the template</span></span>

<span data-ttu-id="2b442-217">로컬 파일 시스템의 *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp*에서 템플릿을 만든 경우 `-u|--uninstall` 스위치와 템플릿 폴더 경로를 사용하여 템플릿을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-217">If you created the template on your local file system at *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp*, uninstall it with the `-u|--uninstall` switch and the path to the template folder:</span></span>

```console
dotnet new -u C:\Users\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> <span data-ttu-id="2b442-218">로컬 파일 시스템에서 템플릿을 제거하려면 경로를 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-218">To uninstall the template from your local file system, you need to fully qualify the path.</span></span> <span data-ttu-id="2b442-219">예를 들어 *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp*는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b442-219">For example, *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="2b442-220">마지막의 종료하는 디렉터리 슬래시도 템플릿 경로에 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="2b442-220">Additionally, do not include a final terminating directory slash on your template path.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b442-221">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b442-221">See also</span></span>

<span data-ttu-id="2b442-222">[dotnet/templating GitHub repo Wiki](https://github.com/dotnet/templating/wiki)(dotnet/templating GitHub 리포지토리 Wiki)</span><span class="sxs-lookup"><span data-stu-id="2b442-222">[dotnet/templating GitHub repo Wiki](https://github.com/dotnet/templating/wiki)</span></span>  
<span data-ttu-id="2b442-223">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)(dotnet/dotnet-template-samples GitHub 리포지토리)</span><span class="sxs-lookup"><span data-stu-id="2b442-223">[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)</span></span>  
<span data-ttu-id="2b442-224">[How to create your own templates for dotnet new](https://blogs.msdn.microsoft.com/dotnet/2017/04/02/how-to-create-your-own-templates-for-dotnet-new/)(dotnet new에 대한 사용자 지정 템플릿을 만드는 방법)</span><span class="sxs-lookup"><span data-stu-id="2b442-224">[How to create your own templates for dotnet new](https://blogs.msdn.microsoft.com/dotnet/2017/04/02/how-to-create-your-own-templates-for-dotnet-new/)</span></span>  
[<span data-ttu-id="2b442-225">*template.json* JSON 스키마 저장소에 대 한 스키마</span><span class="sxs-lookup"><span data-stu-id="2b442-225">*template.json* schema at the JSON Schema Store</span></span>](http://json.schemastore.org/template)  
