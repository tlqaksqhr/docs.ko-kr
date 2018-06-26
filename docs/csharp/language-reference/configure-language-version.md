---
title: C# 언어 버전 선택 - C# 가이드
description: 특정 컴파일러 버전을 사용하여 구문 유효성 검사를 수행하도록 컴파일러 구성
ms.date: 05/24/2018
ms.openlocfilehash: 2056a99544d0cac94bc7cc79e8cd8793b1bcff78
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34566369"
---
# <a name="select-the-c-language-version"></a><span data-ttu-id="a81af-103">C# 언어 버전 선택</span><span class="sxs-lookup"><span data-stu-id="a81af-103">Select the C# language version</span></span>

<span data-ttu-id="a81af-104">C# 컴파일러는 기본적으로 릴리스된 언어의 최신 주 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-104">The C# compiler defaults to the latest major version of the language that has been released.</span></span> <span data-ttu-id="a81af-105">언어의 새 포인트 릴리스를 사용하여 모든 프로젝트를 컴파일하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-105">You may choose to compile any project using a new point release of the language.</span></span> <span data-ttu-id="a81af-106">최신 버전의 언어를 선택하면 프로젝트에서 최신 언어 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-106">Choosing a newer version of the language enables your project to make use of the latest language features.</span></span> <span data-ttu-id="a81af-107">다른 시나리오에서는 이전 버전의 언어를 사용할 때 프로젝트가 깨끗하게 컴파일되는지 확인해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-107">In other scenarios, you may need to validate that a project compiles cleanly when using an older version of the language.</span></span>

<span data-ttu-id="a81af-108">이 기능은 개발 환경에서 SDK 및 도구의 새 버전을 설치하는 결정과 프로젝트의 새 언어 기능을 통합하는 결정을 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-108">This capability decouples the decision to install new versions of the SDK and tools in your development environment from the decision to incorporate new language features in a project.</span></span> <span data-ttu-id="a81af-109">빌드 컴퓨터에 최신 SDK 및 도구를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-109">You can install the latest SDK and tools on your build machine.</span></span> <span data-ttu-id="a81af-110">각 프로젝트는 해당 빌드에 대해 특정 버전의 언어를 사용하도록 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-110">Each project can be configured to use a specific version of the language for its build.</span></span>

<span data-ttu-id="a81af-111">언어 버전을 설정하는 여러 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-111">There are several ways to set the language version:</span></span>

- <span data-ttu-id="a81af-112">[Visual Studio 빠른 작업](#visual-studio-quick-action)에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-112">Rely on a [Visual Studio quick action](#visual-studio-quick-action).</span></span>
- <span data-ttu-id="a81af-113">[Visual Studio UI](#set-the-language-version-in-visual-studio)에서 언어 버전을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-113">Set the language version in the [Visual Studio UI](#set-the-language-version-in-visual-studio).</span></span>
- <span data-ttu-id="a81af-114">[**.csproj** 파일](#edit-the-csproj-file)을 수동으로 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-114">Manually edit your [**.csproj** file](#edit-the-csproj-file).</span></span>
- <span data-ttu-id="a81af-115">[하위 디렉터리에 있는 여러 프로젝트의](#configure-multiple-projects) 언어 버전을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-115">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="a81af-116">[`-langversion` 컴파일러 옵션](#set-the-langversion-compiler-option)을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-116">Configure the [`-langversion` compiler option](#set-the-langversion-compiler-option).</span></span>

## <a name="visual-studio-quick-action"></a><span data-ttu-id="a81af-117">Visual Studio 빠른 작업</span><span class="sxs-lookup"><span data-stu-id="a81af-117">Visual Studio quick action</span></span>

<span data-ttu-id="a81af-118">Visual Studio를 사용하면 필요한 언어 버전을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-118">Visual Studio helps you determine the language version you need.</span></span> <span data-ttu-id="a81af-119">현재 구성된 버전에 사용할 수 없는 언어 기능을 사용하는 경우, Visual Studio는 프로젝트의 언어 버전을 업데이트하는 잠재적 수정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-119">If you use a language feature that is not available for the currently configured version, Visual Studio shows a potential fix to update the language version for the project.</span></span>

## <a name="set-the-language-version-in-visual-studio"></a><span data-ttu-id="a81af-120">Visual Studio에서 언어 버전 설정</span><span class="sxs-lookup"><span data-stu-id="a81af-120">Set the language version in Visual Studio</span></span>

<span data-ttu-id="a81af-121">Visual Studio에서 버전을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-121">You can set the version in Visual Studio.</span></span> <span data-ttu-id="a81af-122">솔루션 탐색기에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-122">Right-click on the project node in Solution Explorer and select **Properties**.</span></span> <span data-ttu-id="a81af-123">**빌드** 탭을 선택하고 **고급** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-123">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="a81af-124">드롭다운에서 버전을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-124">In the dropdown, select the version.</span></span> <span data-ttu-id="a81af-125">다음 이미지는 "최신" 설정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-125">The following image shows the "latest" setting:</span></span>

![언어 버전을 지정할 수 있는 고급 빌드 설정의 스크린샷](./media/configure-language-version/advanced-build-settings.png)

> [!NOTE]
> <span data-ttu-id="a81af-127">Visual Studio IDE를 사용하여 csproj 파일을 업데이트하는 경우 IDE는 각 빌드 구성에 대한 별도 노드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-127">If you use the Visual Studio IDE to update your csproj files, the IDE creates separate nodes for each build configuration.</span></span> <span data-ttu-id="a81af-128">일반적으로 모든 빌드 구성에서 값을 동일하게 설정하지만 각 빌드 구성에 대해 명시적으로 설정하거나 이 설정을 수정하는 경우 "모든 구성"을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-128">You'll typically set the value the same in all build configurations, but you need to set it explicitly for each build configuration, or select "All Configurations" when you modify this setting.</span></span> <span data-ttu-id="a81af-129">csproj 파일에 다음이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-129">You'll see the following in your csproj file:</span></span>
>
>```xml
> <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
>  <LangVersion>latest</LangVersion>
></PropertyGroup>
>
> <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
>  <LangVersion>latest</LangVersion>
> </PropertyGroup>
> ```
>

## <a name="edit-the-csproj-file"></a><span data-ttu-id="a81af-130">csproj 파일 편집</span><span class="sxs-lookup"><span data-stu-id="a81af-130">Edit the csproj file</span></span>

<span data-ttu-id="a81af-131">**.csproj** 파일에서 언어 버전을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-131">You can set the language version in your **.csproj** file.</span></span> <span data-ttu-id="a81af-132">다음과 같은 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-132">Add an element like the following:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="a81af-133">`latest` 값은 C# 언어의 최신 부 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-133">The value `latest` uses the latest minor version of the C# language.</span></span> <span data-ttu-id="a81af-134">올바른 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-134">Valid values are:</span></span>

|<span data-ttu-id="a81af-135">값</span><span class="sxs-lookup"><span data-stu-id="a81af-135">Value</span></span>|<span data-ttu-id="a81af-136">의미</span><span class="sxs-lookup"><span data-stu-id="a81af-136">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="a81af-137">default</span><span class="sxs-lookup"><span data-stu-id="a81af-137">default</span></span>|<span data-ttu-id="a81af-138">컴파일러는 지원할 수 있는 최신 주 버전의 유효한 언어 구문을 모두 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-138">The compiler accepts all valid language syntax from the latest major version that it can support.</span></span>|
|<span data-ttu-id="a81af-139">ISO-1</span><span class="sxs-lookup"><span data-stu-id="a81af-139">ISO-1</span></span>|<span data-ttu-id="a81af-140">컴파일러는 ISO/IEC 23270:2003 C#(1.0/1.2)에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-140">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2)</span></span> |
|<span data-ttu-id="a81af-141">ISO-2</span><span class="sxs-lookup"><span data-stu-id="a81af-141">ISO-2</span></span>|<span data-ttu-id="a81af-142">컴파일러는 ISO/IEC 23270:2006 C#(2.0)에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-142">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0)</span></span> |
|<span data-ttu-id="a81af-143">3</span><span class="sxs-lookup"><span data-stu-id="a81af-143">3</span></span>|<span data-ttu-id="a81af-144">컴파일러는 C# 3.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-144">The compiler accepts only syntax that is included in C# 3.0 or lower.</span></span>|
|<span data-ttu-id="a81af-145">4</span><span class="sxs-lookup"><span data-stu-id="a81af-145">4</span></span>|<span data-ttu-id="a81af-146">컴파일러는 C# 4.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-146">The compiler accepts only syntax that is included in C# 4.0 or lower.</span></span>|
|<span data-ttu-id="a81af-147">5</span><span class="sxs-lookup"><span data-stu-id="a81af-147">5</span></span>|<span data-ttu-id="a81af-148">컴파일러는 C# 5.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-148">The compiler accepts only syntax that is included in C# 5.0 or lower.</span></span>|
|<span data-ttu-id="a81af-149">6</span><span class="sxs-lookup"><span data-stu-id="a81af-149">6</span></span>|<span data-ttu-id="a81af-150">컴파일러는 C# 6.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-150">The compiler accepts only syntax that is included in C# 6.0 or lower.</span></span>|
|<span data-ttu-id="a81af-151">7</span><span class="sxs-lookup"><span data-stu-id="a81af-151">7</span></span>|<span data-ttu-id="a81af-152">컴파일러는 C# 7.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-152">The compiler accepts only syntax that is included in C# 7.0 or lower.</span></span>|
|<span data-ttu-id="a81af-153">7.1</span><span class="sxs-lookup"><span data-stu-id="a81af-153">7.1</span></span>|<span data-ttu-id="a81af-154">컴파일러는 C# 7.1 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-154">The compiler accepts only syntax that is included in C# 7.1 or lower.</span></span>|
|<span data-ttu-id="a81af-155">7.2</span><span class="sxs-lookup"><span data-stu-id="a81af-155">7.2</span></span>|<span data-ttu-id="a81af-156">컴파일러는 C# 7.2 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-156">The compiler accepts only syntax that is included in C# 7.2 or lower.</span></span>|
|<span data-ttu-id="a81af-157">7.3</span><span class="sxs-lookup"><span data-stu-id="a81af-157">7.3</span></span>|<span data-ttu-id="a81af-158">컴파일러는 C# 7.3 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-158">The compiler accepts only syntax that is included in C# 7.3 or lower.</span></span>|
|<span data-ttu-id="a81af-159">latest</span><span class="sxs-lookup"><span data-stu-id="a81af-159">latest</span></span>|<span data-ttu-id="a81af-160">컴파일러가 지원할 수 있는 유효한 언어 구문을 모두 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-160">The compiler accepts all valid language syntax that it can support.</span></span>|

<span data-ttu-id="a81af-161">특수한 문자열 `default` 및 `latest`는 각각 빌드 컴퓨터에 설치된 최신 주(C# 7.0) 및 부(C# 7.3) 언어 버전을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-161">The special strings `default` and `latest` resolve to the latest major (C# 7.0) and minor (C# 7.3) language versions installed on the build machine, respectively.</span></span>

## <a name="configure-multiple-projects"></a><span data-ttu-id="a81af-162">여러 프로젝트 구성</span><span class="sxs-lookup"><span data-stu-id="a81af-162">Configure multiple projects</span></span>

<span data-ttu-id="a81af-163">`<LangVersion>` 요소를 포함하는 **Directory.build.props** 파일을 생성하여 여러 디렉터리를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-163">You can create a **Directory.build.props** file that contains the `<LangVersion>` element to configure multiple directories.</span></span> <span data-ttu-id="a81af-164">일반적으로 솔루션 디렉터리에서 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-164">You typically do that in your solution directory.</span></span> <span data-ttu-id="a81af-165">솔루션 디렉터리의 **Directory.build.props** 파일에 다음을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-165">Add the following to a **Directory.build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>7.3</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="a81af-166">이제 해당 파일을 포함하는 디렉터리의 모든 하위 디렉터리에 있는 빌드는 C# 버전 7.3 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-166">Now, builds in every subdirectory of the directory containing that file will use C# version 7.3 syntax.</span></span> <span data-ttu-id="a81af-167">자세한 내용은 [빌드 사용자 지정](/visualstudio/msbuild/customize-your-build.md)에 대한 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a81af-167">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build.md).</span></span>

## <a name="set-the-langversion-compiler-option"></a><span data-ttu-id="a81af-168">langversion 컴파일러 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="a81af-168">Set the langversion compiler option</span></span>

<span data-ttu-id="a81af-169">`-langversion` 명령줄 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-169">You can use the `-langversion` command-line option.</span></span> <span data-ttu-id="a81af-170">자세한 내용은 [-langversion](../language-reference/compiler-options/langversion-compiler-option.md) 컴파일러 옵션에 대한 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a81af-170">For more information, see the article on the [-langversion](../language-reference/compiler-options/langversion-compiler-option.md) compiler option.</span></span> <span data-ttu-id="a81af-171">`csc -langversion:?`을 입력하면 유효한 값 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a81af-171">You can see a list of the valid values by typing  `csc -langversion:?`.</span></span>
