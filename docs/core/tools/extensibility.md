---
title: ".NET Core CLI 확장성 모델"
description: "CLI(명령줄 인터페이스) 도구를 확장할 수 있는 방법을 알아봅니다."
keywords: "CLI, 확장성, 사용자 지정 명령, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 04/12/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: fffc3400-aeb9-4c07-9fea-83bc8dbdcbf3
ms.openlocfilehash: a8f70505d1bb043ab21f87edbb5aa2d9f18a7071
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="net-core-cli-tools-extensibility-model"></a><span data-ttu-id="a530a-104">.NET Core CLI 도구 확장성 모델</span><span class="sxs-lookup"><span data-stu-id="a530a-104">.NET Core CLI tools extensibility model</span></span>

<span data-ttu-id="a530a-105">이 문서에서는 .NET Core CLI(명령줄 인터페이스) 도구를 확장할 수 있는 다양한 방법 및 각 방법을 구동하는 시나리오를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-105">This document covers the different ways you can extend the .NET Core Command-line Interface (CLI) tools and explain the scenarios that drive each one of them.</span></span>
<span data-ttu-id="a530a-106">도구를 사용하는 방법과 여러 유형의 도구를 빌드하는 방법을 알아보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-106">You'll see how to consume the tools as well as how to build the different types of tools.</span></span>

## <a name="how-to-extend-cli-tools"></a><span data-ttu-id="a530a-107">CLI 도구를 확장하는 방법</span><span class="sxs-lookup"><span data-stu-id="a530a-107">How to extend CLI tools</span></span>
<span data-ttu-id="a530a-108">CLI 도구는 세 가지 주요 방법으로 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-108">The CLI tools can be extended in three main ways:</span></span>

1. [<span data-ttu-id="a530a-109">프로젝트 단위로 NuGet 패키지 사용</span><span class="sxs-lookup"><span data-stu-id="a530a-109">Via NuGet packages on a per-project basis</span></span>](#per-project-based-extensibility)

  <span data-ttu-id="a530a-110">프로젝트 단위 도구는 프로젝트의 컨텍스트 내에 포함되지만 복원을 통해 간편한 설치를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-110">Per-project tools are contained within the project's context, but they allow easy installation through restoration.</span></span>

2. [<span data-ttu-id="a530a-111">사용자 지정 대상을 사용하여 NuGet 패키지 사용</span><span class="sxs-lookup"><span data-stu-id="a530a-111">Via NuGet packages with custom targets</span></span>](#custom-targets)

  <span data-ttu-id="a530a-112">사용자 지정 대상을 사용하면 사용자 지정 작업을 사용하여 빌드 프로세스를 쉽게 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-112">Custom targets allow you to easily extend the build process with custom tasks.</span></span>

3. [<span data-ttu-id="a530a-113">시스템의 PATH 사용</span><span class="sxs-lookup"><span data-stu-id="a530a-113">Via the system's PATH</span></span>](#path-based-extensibility)

  <span data-ttu-id="a530a-114">PATH 기반 도구는 단일 컴퓨터에서 사용할 수 있는 일반적인 프로젝트 간 도구에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-114">PATH-based tools are good for general, cross-project tools that are usable on a single machine.</span></span>

<span data-ttu-id="a530a-115">위에서 간략하게 설명한 세 가지 확장성 메커니즘은 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-115">The three extensibility mechanisms outlined above are not exclusive.</span></span> <span data-ttu-id="a530a-116">하나 또는 모두 사용하거나 임의로 조합해서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-116">You can use one, or all, or a combination of them.</span></span> <span data-ttu-id="a530a-117">선택하는 방법은 확장을 통해 달성하려는 목표에 따라 크게 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-117">Which one to pick depends largely on the goal you are trying to achieve with your extension.</span></span>

## <a name="per-project-based-extensibility"></a><span data-ttu-id="a530a-118">프로젝트 단위 기반 확장성</span><span class="sxs-lookup"><span data-stu-id="a530a-118">Per-project based extensibility</span></span>
<span data-ttu-id="a530a-119">프로젝트 단위 도구는 NuGet 패키지로 배포되는 [프레임워크 종속 배포](../deploying/index.md#framework-dependent-deployments-fdd)입니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-119">Per-project tools are [framework-dependent deployments](../deploying/index.md#framework-dependent-deployments-fdd) that are distributed as NuGet packages.</span></span> <span data-ttu-id="a530a-120">도구는 도구를 참조하는 프로젝트의 컨텍스트에서 복원된 프로젝트에 대해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-120">Tools are only available in the context of the project that references them and for which they are restored.</span></span> <span data-ttu-id="a530a-121">프로젝트의 컨텍스트 외부(예: 프로젝트가 포함된 디렉터리 외부)에서 호출하면 명령을 찾을 수 없기 때문에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-121">Invocation outside of the context of the project (for example, outside of the directory that contains the project) will fail because the command cannot be found.</span></span>

<span data-ttu-id="a530a-122">이러한 도구는 빌드 서버에도 완벽한데, 프로젝트 파일 외부의 항목이 필요하지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-122">These tools are perfect for build servers, since nothing outside of the project file is needed.</span></span> <span data-ttu-id="a530a-123">빌드 프로세스에서는 빌드하는 프로젝트에 대해 복원을 실행하므로 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-123">The build process runs restore for the project it builds and tools will be available.</span></span> <span data-ttu-id="a530a-124">각 프로젝트가 하나의 특정 언어로만 작성될 수 있기 때문에 F#과 같은 언어 프로젝트도 이 범주에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-124">Language projects, such as F#, are also in this category since each project can only be written in one specific language.</span></span>

<span data-ttu-id="a530a-125">마지막으로 이 확장성 모델에서는 프로젝트의 빌드된 출력에 액세스해야 하는 도구를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-125">Finally, this extensibility model provides support for creation of tools that need access to the built output of the project.</span></span> <span data-ttu-id="a530a-126">예를 들어 [ASP.NET](https://www.asp.net/) MVC 응용 프로그램의 다양한 Razor 보기 도구는 이 범주에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-126">For instance, various Razor view tools in [ASP.NET](https://www.asp.net/) MVC applications fall into this category.</span></span>

### <a name="consuming-per-project-tools"></a><span data-ttu-id="a530a-127">프로젝트 단위 도구 사용</span><span class="sxs-lookup"><span data-stu-id="a530a-127">Consuming per-project tools</span></span>
<span data-ttu-id="a530a-128">이러한 도구를 사용하려면 사용할 각 도구에 대한 `<DotNetCliToolReference>` 요소를 프로젝트 파일에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-128">Consuming these tools requires you to add a `<DotNetCliToolReference>` element to your project file for each tool you want to use.</span></span> <span data-ttu-id="a530a-129">`<DotNetCliToolReference>` 요소 내에서 도구가 상주하는 패키지를 참조하고 필요한 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-129">Inside the `<DotNetCliToolReference>` element, you reference the package in which the tool resides and specify the version you need.</span></span> <span data-ttu-id="a530a-130">[`dotnet restore`](dotnet-restore.md)를 실행하면 도구 및 해당 종속성이 복원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-130">After running [`dotnet restore`](dotnet-restore.md), the tool and its dependencies are restored.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="a530a-131">프로젝트의 빌드 출력을 로드하여 실행해야 하는 도구의 경우 일반적으로 프로젝트 파일의 일반 종속성 아래에 나열되는 다른 종속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-131">For tools that need to load the build output of the project for execution, there is usually another dependency which is listed under the regular dependencies in the project file.</span></span> <span data-ttu-id="a530a-132">CLI에서는 빌드 엔진으로 MSBuild를 사용하기 때문에 전반적인 빌드 프로세스에 포함될 수 있는 방식으로 이러한 도구 부분을 사용자 지정 MSBuild [대상](/visualstudio/msbuild/msbuild-targets) 및 [작업](/visualstudio/msbuild/msbuild-tasks)으로 작성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-132">Since CLI uses MSBuild as its build engine, we recommend that these parts of the tool be written as custom MSBuild [targets](/visualstudio/msbuild/msbuild-targets) and [tasks](/visualstudio/msbuild/msbuild-tasks), since they can then take part in the overall build process.</span></span> <span data-ttu-id="a530a-133">또한 출력 파일 위치, 빌드 중인 현재 구성 등 빌드를 통해 생성된 모든 데이터를 쉽게 가져올 수 있습니다. 이 정보는 모두 임의 대상에서 읽을 수 있는 MSBuild 속성 집합이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-133">Also, they can get any and all data easily that is produced via the build, such as the location of the output files, the current configuration being built, etc. All this information becomes a set of MSBuild properties that can be read from any target.</span></span> <span data-ttu-id="a530a-134">이 문서의 뒷부분에 있는 NuGet을 사용하여 사용자 지정 대상을 추가하는 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-134">You can see how to add a custom target using NuGet later in this document.</span></span>

<span data-ttu-id="a530a-135">간단한 도구를 추가하는 예제를 검토해 보겠습니다. 간단한 프로젝트에 도구만 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-135">Let's review an example of adding a simple tools-only tool to a simple project.</span></span> <span data-ttu-id="a530a-136">다음은 NuGet 패키지에서 지정된 API를 검색할 수 있는 `dotnet-api-search`라는 예제 명령이 지정된 경우 해당 도구를 사용하는 콘솔 응용 프로그램의 프로젝트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-136">Given an example command called `dotnet-api-search` that allows you to search through the NuGet packages for the specified API, here is a console application's project file that uses that tool:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.1</TargetFramework>
  </PropertyGroup>

  <!-- The tools reference -->
  <ItemGroup>
    <DotNetCliToolReference Include="dotnet-api-search" Version="1.0.0" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="a530a-137">`<DotNetCliToolReference>` 요소는 `<PackageReference>` 요소와 비슷한 방식으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-137">The `<DotNetCliToolReference>` element is structured in a similar way as the `<PackageReference>` element.</span></span> <span data-ttu-id="a530a-138">이 노드에는 도구와 복원할 수 있는 도구 버전을 포함하는 패키지의 패키지 ID가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-138">It needs the package ID of the package containing the tool and its version to be able to restore.</span></span>

### <a name="building-tools"></a><span data-ttu-id="a530a-139">도구 빌드</span><span class="sxs-lookup"><span data-stu-id="a530a-139">Building tools</span></span>
<span data-ttu-id="a530a-140">앞에서 설명한 대로 도구는 단순히 이식 가능한 콘솔 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-140">As mentioned, tools are just portable console applications.</span></span> <span data-ttu-id="a530a-141">다른 콘솔 응용 프로그램을 빌드함에 따라 도구를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-141">You build tools as you would build any other console application.</span></span>
<span data-ttu-id="a530a-142">도구를 빌드한 후에는 [`dotnet pack`](dotnet-pack.md) 명령을 사용하여 코드, 종속성에 대한 정보 등을 포함하는 NuGet 패키지(.nupkg 파일)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-142">After you build it, you use the [`dotnet pack`](dotnet-pack.md) command to create a NuGet package (.nupkg file) that contains your code, information about its dependencies, and so on.</span></span> <span data-ttu-id="a530a-143">패키지 이름을 원하는 대로 지정할 수 있지만 응용 프로그램 내부 실제 도구 이진이 `dotnet-<command>`의 규칙을 준수해야 `dotnet`에서 패키지를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-143">You can give any name to the package, but the application inside, the actual tool binary, has to conform to the convention of `dotnet-<command>` in order for `dotnet` to be able to invoke it.</span></span>

> [!NOTE]
> <span data-ttu-id="a530a-144">.NET Core 명령줄 도구의 RC3 이전 버전에서는 `dotnet pack` 명령에 버그가 있어서 `runtime.config.json`이 도구로 압축되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-144">In pre-RC3 versions of the .NET Core command-line tools, the `dotnet pack` command had a bug that caused the `runtime.config.json` to not be packed with the tool.</span></span> <span data-ttu-id="a530a-145">해당 파일이 없으면 런타임 시 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-145">Lacking that file results in errors at runtime.</span></span> <span data-ttu-id="a530a-146">이 문제가 발생하는 경우 최신 도구로 업데이트하고 `dotnet pack`을 다시 시도하세요.</span><span class="sxs-lookup"><span data-stu-id="a530a-146">If you encounter this behavior, be sure to update to the latest tooling and try the `dotnet pack` again.</span></span>

<span data-ttu-id="a530a-147">도구는 이식 가능한 응용 프로그램이므로 도구 사용자가 도구를 실행하려면 도구가 빌드된 버전의 .NET Core 라이브러리가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-147">Since tools are portable applications, the user consuming the tool must have the version of the .NET Core libraries that the tool was built against in order to run the tool.</span></span> <span data-ttu-id="a530a-148">도구에서 사용하고 .NET Core 라이브러리 내에서 포함되지 않은 다른 모든 종속성은 NuGet 캐시에서 복원되고 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-148">Any other dependency that the tool uses and that is not contained within the .NET Core libraries is restored and placed in the NuGet cache.</span></span> <span data-ttu-id="a530a-149">따라서 전체 도구는 .NET Core 라이브러리의 어셈블리뿐만 아니라 NuGet 캐시의 어셈블리를 사용하여 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-149">The entire tool is, therefore, run using the assemblies from the .NET Core libraries as well as assemblies from the NuGet cache.</span></span>

<span data-ttu-id="a530a-150">이러한 종류의 도구에는 해당 도구를 사용하는 프로젝트의 종속성 그래프와 완전히 구분되는 종속성 그래프가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-150">These kinds of tools have a dependency graph that is completely separate from the dependency graph of the project that uses them.</span></span> <span data-ttu-id="a530a-151">복원 프로세스에서는 먼저 프로젝트의 종속성을 복원한 다음 각 도구 및 해당 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-151">The restore process first restores the project's dependencies and then restores each of the tools and their dependencies.</span></span>

<span data-ttu-id="a530a-152">보다 풍부한 예제 및 다양한 조합은 [.NET Core CLI 리포지토리](https://github.com/dotnet/cli/tree/rel/1.0.1/TestAssets/TestProjects)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-152">You can find richer examples and different combinations of this in the [.NET Core CLI repo](https://github.com/dotnet/cli/tree/rel/1.0.1/TestAssets/TestProjects).</span></span>
<span data-ttu-id="a530a-153">동일한 리포지토리에서 [사용된 도구의 구현](https://github.com/dotnet/cli/tree/rel/1.0.1/TestAssets/TestPackages)도 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-153">You can also see the [implementation of tools used](https://github.com/dotnet/cli/tree/rel/1.0.1/TestAssets/TestPackages) in the same repo.</span></span>

### <a name="custom-targets"></a><span data-ttu-id="a530a-154">사용자 지정 대상</span><span class="sxs-lookup"><span data-stu-id="a530a-154">Custom targets</span></span>
<span data-ttu-id="a530a-155">NuGet에는 [사용자 지정 MSBuild 대상 및 props 파일을 패키지](/nuget/create-packages/creating-a-package#including-msbuild-props-and-targets-in-a-package)하는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-155">NuGet has the capability to [package custom MSBuild targets and props files](/nuget/create-packages/creating-a-package#including-msbuild-props-and-targets-in-a-package).</span></span> <span data-ttu-id="a530a-156">.NET Core CLI 도구가 MSBuild를 사용하도록 이동하면서 이제 동일한 확장성 메커니즘이 .NET Core 프로젝트에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-156">With the move of the .NET Core CLI tools to use MSBuild, the same mechanism of extensibility now applies to .NET Core projects.</span></span> <span data-ttu-id="a530a-157">빌드 프로세스를 확장하거나 빌드 프로세스에서 생성된 파일과 같은 아티팩트에 액세스하거나 빌드 호출 시 구성을 검사하려는 경우 이 유형의 확장성을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-157">You would use this type of extensibility when you want to extend the build process, or when you want to access any of the artifacts in the build process, such as generated files, or you want to inspect the configuration under which the build is invoked, etc.</span></span>

<span data-ttu-id="a530a-158">다음 예제에서는 `csproj` 구문을 사용하여 대상의 프로젝트 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-158">In the following example, you can see the target's project file using the `csproj` syntax.</span></span> <span data-ttu-id="a530a-159">이렇게 하면 [`dotnet pack`](dotnet-pack.md) 명령에 대상 파일 및 어셈블리를 패키지 내의 *빌드* 폴더에 배치하여 패키지할 항목이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-159">This instructs the [`dotnet pack`](dotnet-pack.md) command what to package, placing the targets files as well as the assemblies into the *build* folder inside the package.</span></span> <span data-ttu-id="a530a-160">`Label` 속성이 `dotnet pack instructions`로 설정된 `<ItemGroup>` 요소 및 그 아래에 정의된 Target을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-160">Notice the `<ItemGroup>` element that has the `Label` property set to `dotnet pack instructions`, and the Target defined beneath it.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <Description>Sample Packer</Description>
    <VersionPrefix>0.1.0-preview</VersionPrefix>
    <TargetFramework>netstandard1.3</TargetFramework>
    <DebugType>portable</DebugType>
    <AssemblyName>SampleTargets.PackerTarget</AssemblyName>
  </PropertyGroup>
  <ItemGroup>
    <EmbeddedResource Include="Resources\Pkg\dist-template.xml;compiler\resources\**\*" Exclude="bin\**;obj\**;**\*.xproj;packages\**" />
    <None Include="build\SampleTargets.PackerTarget.targets" />
  </ItemGroup>
  <ItemGroup Label="dotnet pack instructions">
    <Content Include="build\*.targets">
      <Pack>true</Pack>
      <PackagePath>build\</PackagePath>
    </Content>
  </ItemGroup>
  <Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">
    <!-- Collect these items inside a target that runs after build but before packaging. -->
    <ItemGroup>
      <Content Include="$(OutputPath)\*.dll;$(OutputPath)\*.json">
        <Pack>true</Pack>
        <PackagePath>build\</PackagePath>
      </Content>
    </ItemGroup>
  </Target>
  <ItemGroup>
    <PackageReference Include="Microsoft.Extensions.DependencyModel" Version="1.0.1-beta-000933"/>
    <PackageReference Include="Microsoft.Build.Framework" Version="0.1.0-preview-00028-160627" />
    <PackageReference Include="Microsoft.Build.Utilities.Core" Version="0.1.0-preview-00028-160627" />
    <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
  </ItemGroup>
  <ItemGroup />
  <PropertyGroup Label="Globals">
    <ProjectGuid>463c66f0-921d-4d34-8bde-7c9d0bffaf7b</ProjectGuid>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(TargetFramework)' == 'netstandard1.3' ">
    <DefineConstants>$(DefineConstants);NETSTANDARD1_3</DefineConstants>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(Configuration)' == 'Release' ">
    <DefineConstants>$(DefineConstants);RELEASE</DefineConstants>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="a530a-161">사용자 지정 대상을 사용하는 작업은 확장되고 있는 프로젝트 내부 버전과 패키지를 가리키는 `<PackageReference>`를 제공함으로써 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-161">Consuming custom targets is done by providing a `<PackageReference>` that points to the package and its version inside the project that is being extended.</span></span> <span data-ttu-id="a530a-162">도구와 달리 사용자 지정 대상 패키지는 사용하는 프로젝트의 종속성 종료 항목에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-162">Unlike the tools, the custom targets package does get included into the consuming project's dependency closure.</span></span>

<span data-ttu-id="a530a-163">사용자 지정 대상을 사용하는 작업은 구성하는 방법에 따라 전적으로 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-163">Using the custom target depends solely on how you configure it.</span></span> <span data-ttu-id="a530a-164">MSBuild 대상이므로 지정된 대상에 따라 달라지고 다른 대상 이후에 실행될 수 있으며, `dotnet msbuild /t:<target-name>` 명령을 사용하여 수동으로 호출할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-164">Since it's an MSBuild target, it can depend on a given target, run after another target and can also be manually invoked using the `dotnet msbuild /t:<target-name>` command.</span></span>

<span data-ttu-id="a530a-165">그러나 사용자에게 더 나은 사용자 환경을 제공하려는 경우 프로젝트별 도구 및 사용자 지정 대상을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-165">However, if you want to provide a better user experience to your users, you can combine per-project tools and custom targets.</span></span> <span data-ttu-id="a530a-166">이 시나리오에서 프로젝트별 도구는 기본적으로 매개 변수가 필요한 항목은 허용하고, 대상을 실행할 필수 [`dotnet msbuild`](dotnet-msbuild.md) 호출로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-166">In this scenario, the per-project tool would essentially just accept whatever needed parameters and would translate that into the required [`dotnet msbuild`](dotnet-msbuild.md) invocation that would execute the target.</span></span> <span data-ttu-id="a530a-167">이러한 종류의 시너지 효과는 [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer) 프로젝트의 [MVP Summit 2016 Hackathon 샘플](https://github.com/dotnet/MVPSummitHackathon2016) 리포지토리에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-167">You can see a sample of this kind of synergy on the [MVP Summit 2016 Hackathon samples](https://github.com/dotnet/MVPSummitHackathon2016) repo in the [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer) project.</span></span>

### <a name="path-based-extensibility"></a><span data-ttu-id="a530a-168">PATH 기반 확장성</span><span class="sxs-lookup"><span data-stu-id="a530a-168">PATH-based extensibility</span></span>
<span data-ttu-id="a530a-169">일반적으로 PATH 기반 확장성은 개념적으로 둘 이상의 프로젝트를 포함하는 도구가 필요한 개발 컴퓨터에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-169">PATH-based extensibility is usually used for development machines where you need a tool that conceptually covers more than a single project.</span></span> <span data-ttu-id="a530a-170">이 확장 메커니즘의 주요 단점은 도구가 있는 컴퓨터에 연결된다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-170">The main drawback of this extension mechanism is that it's tied to the machine where the tool exists.</span></span> <span data-ttu-id="a530a-171">따라서 다른 컴퓨터에서 필요한 경우에는 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-171">If you need it on another machine, you would have to deploy it.</span></span>

<span data-ttu-id="a530a-172">CLI 도구 집합 확장성의 이 패턴은 매우 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-172">This pattern of CLI toolset extensibility is very simple.</span></span> <span data-ttu-id="a530a-173">[.NET Core CLI 개요](index.md)에서 설명한 대로 `dotnet` 드라이버는 `dotnet-<command>` 규칙에 따라 명명된 모든 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-173">As covered in the [.NET Core CLI overview](index.md), `dotnet` driver can run any command that is named after the `dotnet-<command>` convention.</span></span> <span data-ttu-id="a530a-174">기본 해결 논리에서는 여러 위치를 먼저 검색하고 마지막으로 시스템 PATH를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-174">The default resolution logic first probes several locations and finally falls back to the system PATH.</span></span> <span data-ttu-id="a530a-175">요청한 명령이 시스템 PATH에 있고 호출할 수 있는 이진인 경우 `dotnet` 드라이버에서 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-175">If the requested command exists in the system PATH and is a binary that can be invoked, `dotnet` driver will invoke it.</span></span>

<span data-ttu-id="a530a-176">파일은 실행 파일이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-176">The file must be executable.</span></span> <span data-ttu-id="a530a-177">Unix 시스템에서는 `chmod +x`를 통해 실행 비트를 설정하는 모든 항목을 의미하고,</span><span class="sxs-lookup"><span data-stu-id="a530a-177">On Unix systems, this means anything that has the execute bit set via `chmod +x`.</span></span> <span data-ttu-id="a530a-178">Windows에서는 *cmd* 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-178">On Windows, you can use *cmd* files.</span></span>

<span data-ttu-id="a530a-179">"Hello World" 도구의 매우 간단한 구현을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-179">Let's take a look at the very simple implementation of a "Hello World" tool.</span></span> <span data-ttu-id="a530a-180">Windows에서는 `bash` 및 `cmd`를 둘 다 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-180">We will use both `bash` and `cmd` on Windows.</span></span>
<span data-ttu-id="a530a-181">다음 명령은 단순히 "Hello World"를 콘솔에 에코합니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-181">The following command will simply echo "Hello World" to the console.</span></span>

```bash
#!/bin/bash

echo "Hello World!"
```

```cmd
echo "Hello World"
```

<span data-ttu-id="a530a-182">MacOS에서는 이 스크립트를 `dotnet-hello`으로 저장하고 `chmod +x dotnet-hello`을 사용하여 실행 파일 비트를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-182">On macOS, we can save this script as `dotnet-hello` and set its executable bit with `chmod +x dotnet-hello`.</span></span> <span data-ttu-id="a530a-183">그런 다음 `ln -s <full_path>/dotnet-hello /usr/local/bin/` 명령을 사용하여 `/usr/local/bin`에 바로 가기 링크를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-183">We can then create a symbolic link to it in `/usr/local/bin` using the command `ln -s <full_path>/dotnet-hello /usr/local/bin/`.</span></span> <span data-ttu-id="a530a-184">그러면 `dotnet hello` 구문을 사용하여 명령을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-184">This will make it possible to invoke the command using the `dotnet hello` syntax.</span></span>

<span data-ttu-id="a530a-185">Windows에서는 이 스크립트를 `dotnet-hello.cmd`로 저장하고 시스템 경로에 있는 위치에 보관하거나 경로에 이미 있는 폴더에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-185">On Windows, we can save this script as `dotnet-hello.cmd` and put it in a location that is in a system path (or you can add it to a folder that is already in the path).</span></span> <span data-ttu-id="a530a-186">그런 다음 `dotnet hello`를 사용하여 이 예제를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a530a-186">After this, you can just use `dotnet hello` to run this example.</span></span>
