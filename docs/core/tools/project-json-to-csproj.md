---
title: project.json 및 csproj 비교 - .NET Core
description: project.json 및 csproj e요소 간 매핑을 참조하세요.
author: natemcmaster
ms.author: mairaw
ms.date: 03/13/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: c5753d73f062aa107d7afbec6146ea3452901fb1
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="a-mapping-between-projectjson-and-csproj-properties"></a><span data-ttu-id="4c370-103">project.json 및 csproj 속성 간 매핑</span><span class="sxs-lookup"><span data-stu-id="4c370-103">A mapping between project.json and csproj properties</span></span>

<span data-ttu-id="4c370-104">[Nate McMaster](https://github.com/natemcmaster)</span><span class="sxs-lookup"><span data-stu-id="4c370-104">By [Nate McMaster](https://github.com/natemcmaster)</span></span>

<span data-ttu-id="4c370-105">.NET Core 도구 개발 중 중요한 디자인 변경으로 인해 *project.json* 파일이 더 이상 지원되지 않으며 대신 .NET Core 프로젝트를 MSBuild/csproj 형식으로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-105">During the development of the .NET Core tooling, an important design change was made to no longer support *project.json* files and instead move the .NET Core projects to the MSBuild/csproj format.</span></span>

<span data-ttu-id="4c370-106">이 문서에서는 프로젝트를 최신 버전의 도구로 업그레이드할 때, 새 형식을 사용하는 방법을 배우고 마이그레이션 도구에서 수행한 변경 내용을 이해할 수 있도록 *project.json*의 설정이 MSBuild/csproj 형식으로 표시되는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-106">This article shows how the settings in *project.json* are represented in the MSBuild/csproj format so you can learn how to use the new format and understand the changes made by the migration tools when you're upgrading your project to the latest version of the tooling.</span></span> 
 
## <a name="the-csproj-format"></a><span data-ttu-id="4c370-107">csproj 형식</span><span class="sxs-lookup"><span data-stu-id="4c370-107">The csproj format</span></span>

<span data-ttu-id="4c370-108">새 형식인 \*.csproj는 XML 기반 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-108">The new format, \*.csproj, is an XML-based format.</span></span> <span data-ttu-id="4c370-109">다음 예제에서는 `Microsoft.NET.Sdk`를 사용하는 .NET Core 프로젝트의 루트 노드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-109">The following example shows the root node of a .NET Core project using the `Microsoft.NET.Sdk`.</span></span> <span data-ttu-id="4c370-110">웹 프로젝트의 경우 사용되는 SDK는 `Microsoft.NET.Sdk.Web`입니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-110">For web projects, the SDK used is `Microsoft.NET.Sdk.Web`.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
...
</Project>
```

## <a name="common-top-level-properties"></a><span data-ttu-id="4c370-111">일반적인 최상위 속성</span><span class="sxs-lookup"><span data-stu-id="4c370-111">Common top-level properties</span></span>

### <a name="name"></a><span data-ttu-id="4c370-112">name</span><span class="sxs-lookup"><span data-stu-id="4c370-112">name</span></span>
```json
{
  "name": "MyProjectName"
}
```

<span data-ttu-id="4c370-113">더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-113">No longer supported.</span></span> <span data-ttu-id="4c370-114">csproj에서는 디렉터리 이름으로 정의되는 프로젝트 파일 이름으로 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-114">In csproj, this is determined by the project filename, which is defined by the directory name.</span></span> <span data-ttu-id="4c370-115">예를 들어, `MyProjectName.csproj`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-115">For example, `MyProjectName.csproj`.</span></span>

<span data-ttu-id="4c370-116">기본적으로 프로젝트 파일 이름은 `<AssemblyName>` 및 `<PackageId>` 속성의 값도 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-116">By default, the project filename also specifies the value of the `<AssemblyName>` and `<PackageId>` properties.</span></span> 

```xml
<PropertyGroup>
  <AssemblyName>MyProjectName</AssemblyName>
  <PackageId>MyProjectName</PackageId>
</PropertyGroup>
```

<span data-ttu-id="4c370-117">`buildOptions\outputName` 속성이 project.json에서 정의된 경우 `<AssemblyName>`에는 `<PackageId>`와 다른 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-117">The `<AssemblyName>` will have a different value than `<PackageId>` if `buildOptions\outputName` property was defined in project.json.</span></span> <span data-ttu-id="4c370-118">자세한 내용은 [기타 일반적인 빌드 옵션](#other-common-build-options)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4c370-118">For more information, see [Other common build options](#other-common-build-options).</span></span>

### <a name="version"></a><span data-ttu-id="4c370-119">버전</span><span class="sxs-lookup"><span data-stu-id="4c370-119">version</span></span>

```json
{
  "version": "1.0.0-alpha-*"
}
```
<span data-ttu-id="4c370-120">`VersionPrefix` 및 `VersionSuffix` 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-120">Use the `VersionPrefix` and `VersionSuffix` properties:</span></span>

```xml
<PropertyGroup>
  <VersionPrefix>1.0.0</VersionPrefix>
  <VersionSuffix>alpha</VersionSuffix>
</PropertyGroup>
```

<span data-ttu-id="4c370-121">`Version` 속성을 사용할 수도 있지만, 패키징 중 버전 설정이 재정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-121">You can also use the `Version` property, but this may override version settings during packaging:</span></span>

```xml
<PropertyGroup>
  <Version>1.0.0-alpha</Version>
</PropertyGroup>
```

### <a name="other-common-root-level-options"></a><span data-ttu-id="4c370-122">기타 일반적인 루트 수준 옵션</span><span class="sxs-lookup"><span data-stu-id="4c370-122">Other common root-level options</span></span>

```json
{
  "authors": [ "Anne", "Bob" ],
  "company": "Contoso",
  "language": "en-US",
  "title": "My library",
  "description": "This is my library.\r\nAnd it's really great!",
  "copyright": "Nugetizer 3000",
  "userSecretsId": "xyz123"
}
```

```xml
<PropertyGroup>
  <Authors>Anne;Bob</Authors>
  <Company>Contoso</Company>
  <NeutralLanguage>en-US</NeutralLanguage>
  <AssemblyTitle>My library</AssemblyTitle>
  <Description>This is my library.
And it's really great!</Description>
  <Copyright>Nugetizer 3000</Copyright>
  <UserSecretsId>xyz123</UserSecretsId>
</PropertyGroup>
```

## <a name="frameworks"></a><span data-ttu-id="4c370-123">frameworks</span><span class="sxs-lookup"><span data-stu-id="4c370-123">frameworks</span></span>

### <a name="one-target-framework"></a><span data-ttu-id="4c370-124">단일 대상 프레임워크</span><span class="sxs-lookup"><span data-stu-id="4c370-124">One target framework</span></span>
```json
{
  "frameworks": {
    "netcoreapp1.0": {}
  }
}
```

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp1.0</TargetFramework>
</PropertyGroup>
```

### <a name="multiple-target-frameworks"></a><span data-ttu-id="4c370-125">여러 대상 프레임워크</span><span class="sxs-lookup"><span data-stu-id="4c370-125">Multiple target frameworks</span></span>

```json
{
  "frameworks": {
    "netcoreapp1.0": {},
    "net451": {}
  }
}
```

<span data-ttu-id="4c370-126">`TargetFrameworks` 속성을 사용하여 대상 프레임워크의 목록을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-126">Use the `TargetFrameworks` property to define your list of target frameworks.</span></span> <span data-ttu-id="4c370-127">세미콜론을 사용하여 여러 프레임워크 값을 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-127">Use semi-colon to separate multiple framework values.</span></span> 

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp1.0;net451</TargetFrameworks>
</PropertyGroup>
```

## <a name="dependencies"></a><span data-ttu-id="4c370-128">종속성</span><span class="sxs-lookup"><span data-stu-id="4c370-128">dependencies</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4c370-129">종속성이 **프로젝트**이고 패키지가 아닌 경우 형식이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-129">If the dependency is a **project** and not a package, the format is different.</span></span> <span data-ttu-id="4c370-130">자세한 내용은 [종속성 유형](#dependency-type) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4c370-130">For more information, see the [dependency type](#dependency-type) section.</span></span>

### <a name="netstandardlibrary-metapackage"></a><span data-ttu-id="4c370-131">NETStandard.Library metapackage</span><span class="sxs-lookup"><span data-stu-id="4c370-131">NETStandard.Library metapackage</span></span>

```json
{
  "dependencies": {
    "NETStandard.Library": "1.6.0"
  }
}
```

```xml
<PropertyGroup>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

### <a name="microsoftnetcoreapp-metapackage"></a><span data-ttu-id="4c370-132">Microsoft.NETCore.App metapackage</span><span class="sxs-lookup"><span data-stu-id="4c370-132">Microsoft.NETCore.App metapackage</span></span>

```json
{
  "dependencies": {
    "Microsoft.NETCore.App": "1.0.0"
  }
}
```

```xml
<PropertyGroup>
  <RuntimeFrameworkVersion>1.0.3</RuntimeFrameworkVersion>
</PropertyGroup>
```

<span data-ttu-id="4c370-133">마이그레이션된 프로젝트에서 `<RuntimeFrameworkVersion>` 값은 설치한 SDK의 버전에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-133">Note that the `<RuntimeFrameworkVersion>` value in the migrated project is determined by the version of the SDK you have installed.</span></span>

### <a name="top-level-dependencies"></a><span data-ttu-id="4c370-134">최상위 종속성</span><span class="sxs-lookup"><span data-stu-id="4c370-134">Top-level dependencies</span></span>
```json
{
  "dependencies": {
    "Microsoft.AspNetCore": "1.1.0"
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.AspNetCore" Version="1.1.0" />
</ItemGroup>
```

### <a name="per-framework-dependencies"></a><span data-ttu-id="4c370-135">프레임워크별 종속성</span><span class="sxs-lookup"><span data-stu-id="4c370-135">Per-framework dependencies</span></span>
```json
{
  "framework": {
    "net451": {
      "dependencies": {
        "System.Collections.Immutable": "1.3.1"
      }
    },
    "netstandard1.5": {
      "dependencies": {
        "Newtonsoft.Json": "9.0.1"
      }
    }
  }
}
```

```xml
<ItemGroup Condition="'$(TargetFramework)'=='net451'">
  <PackageReference Include="System.Collections.Immutable" Version="1.3.1" />
</ItemGroup>

<ItemGroup Condition="'$(TargetFramework)'=='netstandard1.5'">
  <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
</ItemGroup>
```

### <a name="imports"></a><span data-ttu-id="4c370-136">가져오기</span><span class="sxs-lookup"><span data-stu-id="4c370-136">imports</span></span>

```json
{
  "dependencies": {
    "YamlDotNet": "4.0.1-pre309"
  },
  "frameworks": {
    "netcoreapp1.0": {
      "imports": [
        "dnxcore50",
        "dotnet"
      ]
    }
  }
}
```

```xml
<PropertyGroup>
  <PackageTargetFallback>dnxcore50;dotnet</PackageTargetFallback>
</PropertyGroup>
<ItemGroup>
  <PackageReference Include="YamlDotNet" Version="4.0.1-pre309" />
</ItemGroup>
```

### <a name="dependency-type"></a><span data-ttu-id="4c370-137">종속성 유형</span><span class="sxs-lookup"><span data-stu-id="4c370-137">dependency type</span></span>

#### <a name="type-project"></a><span data-ttu-id="4c370-138">type: project</span><span class="sxs-lookup"><span data-stu-id="4c370-138">type: project</span></span>
```json
{
  "dependencies": {
    "MyOtherProject": "1.0.0-*",
    "AnotherProject": {
      "type": "project"
    }
  }
}
```

```xml
<ItemGroup>
  <ProjectReference Include="..\MyOtherProject\MyOtherProject.csproj" />
  <ProjectReference Include="..\AnotherProject\AnotherProject.csproj" />
</ItemGroup>
```

> [!NOTE]
> <span data-ttu-id="4c370-139">`dotnet pack --version-suffix $suffix`가 프로젝트 참조의 종속성 버전을 결정하는 방법이 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-139">This will break the way that `dotnet pack --version-suffix $suffix` determines the dependency version of a project reference.</span></span>


#### <a name="type-build"></a><span data-ttu-id="4c370-140">type: build</span><span class="sxs-lookup"><span data-stu-id="4c370-140">type: build</span></span>
```json
{
  "dependencies": {
    "Microsoft.EntityFrameworkCore.Design": {
      "version": "1.1.0",
      "type": "build"
    }
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.EntityFrameworkCore.Design" Version="1.1.0" PrivateAssets="All" />
</ItemGroup>
```

#### <a name="type-platform"></a><span data-ttu-id="4c370-141">type: platform</span><span class="sxs-lookup"><span data-stu-id="4c370-141">type: platform</span></span>
```json
{
  "dependencies": {
    "Microsoft.NETCore.App": {
      "version": "1.1.0",
      "type": "platform"
    }
  }
}
```

<span data-ttu-id="4c370-142">csproj에는 동일한 항목이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-142">There is no equivalent in csproj.</span></span> 

## <a name="runtimes"></a><span data-ttu-id="4c370-143">runtimes</span><span class="sxs-lookup"><span data-stu-id="4c370-143">runtimes</span></span>
```json
{
  "runtimes": {
    "win7-x64": {},
    "osx.10.11-x64": {},
    "ubuntu.16.04-x64": {}
  }
}
```

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win7-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="standalone-apps-self-contained-deployment"></a><span data-ttu-id="4c370-144">독립 실행형 앱(자체 포함 배포)</span><span class="sxs-lookup"><span data-stu-id="4c370-144">Standalone apps (self-contained deployment)</span></span>
<span data-ttu-id="4c370-145">project.json에서 `runtimes` 섹션 정의는 앱이 빌드 및 게시 중 독립 실행형이었음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-145">In project.json, defining a `runtimes` section means the app was standalone during build and publish.</span></span>
<span data-ttu-id="4c370-146">MSBuild에서 모든 프로젝트는 빌드 중 *이식 가능*하지만 독립 실행형으로 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-146">In MSBuild, all projects are *portable* during build, but can be published as standalone.</span></span>

`dotnet publish --framework netcoreapp1.0 --runtime osx.10.11-x64`

<span data-ttu-id="4c370-147">자세한 내용은 [SCD(자체 포함 배포)](../deploying/index.md#self-contained-deployments-scd)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4c370-147">For more information, see [Self-contained deployments (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span>

## <a name="tools"></a><span data-ttu-id="4c370-148">도구</span><span class="sxs-lookup"><span data-stu-id="4c370-148">tools</span></span>
```json
{
  "tools": {
    "Microsoft.EntityFrameworkCore.Tools.DotNet": "1.0.0-*"
  }
}
```

```xml
<ItemGroup>
  <DotNetCliToolReference Include="Microsoft.EntityFrameworkCore.Tools.DotNet" Version="1.0.0" />
</ItemGroup>
```

> [!NOTE]
> <span data-ttu-id="4c370-149">도구의 `imports`는 csproj에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-149">`imports` on tools are not supported in csproj.</span></span> <span data-ttu-id="4c370-150">imports가 필요한 도구는 새 `Microsoft.NET.Sdk`와 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-150">Tools that need imports will not work with the new `Microsoft.NET.Sdk`.</span></span>

## <a name="buildoptions"></a><span data-ttu-id="4c370-151">buildOptions</span><span class="sxs-lookup"><span data-stu-id="4c370-151">buildOptions</span></span>

<span data-ttu-id="4c370-152">[파일](#files)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4c370-152">See also [Files](#files).</span></span>

### <a name="emitentrypoint"></a><span data-ttu-id="4c370-153">emitEntryPoint</span><span class="sxs-lookup"><span data-stu-id="4c370-153">emitEntryPoint</span></span>

```json
{
  "buildOptions": {
    "emitEntryPoint": true
  }
}
```

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="4c370-154">`emitEntryPoint`가 `false`인 경우 `OutputType` 값은 기본값인 `Library`로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-154">If `emitEntryPoint` was `false`, the value of `OutputType` is converted to `Library`, which is the default value:</span></span>

```json
{
  "buildOptions": {
    "emitEntryPoint": false
  }
}
```

```xml
<PropertyGroup>
  <OutputType>Library</OutputType>
  <!-- or, omit altogether. It defaults to 'Library' -->
</PropertyGroup>
```

### <a name="keyfile"></a><span data-ttu-id="4c370-155">keyFile</span><span class="sxs-lookup"><span data-stu-id="4c370-155">keyFile</span></span>

```json
{
  "buildOptions": {
    "keyFile": "MyKey.snk"
  }
}
```

<span data-ttu-id="4c370-156">`keyFile` 요소는 MSBuild의 세 가지 속성으로 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-156">The `keyFile` element expands to three properties in MSBuild:</span></span>

```xml
<PropertyGroup>
  <AssemblyOriginatorKeyFile>MyKey.snk</AssemblyOriginatorKeyFile>
  <SignAssembly>true</SignAssembly>
  <PublicSign Condition="'$(OS)' != 'Windows_NT'">true</PublicSign>
</PropertyGroup>
```

### <a name="other-common-build-options"></a><span data-ttu-id="4c370-157">기타 일반적인 빌드 옵션</span><span class="sxs-lookup"><span data-stu-id="4c370-157">Other common build options</span></span>

```json
{
  "buildOptions": {
    "warningsAsErrors": true,
    "nowarn": ["CS0168", "CS0219"],
    "xmlDoc": true,
    "preserveCompilationContext": true,
    "outputName": "Different.AssemblyName",
    "debugType": "portable",
    "allowUnsafe": true,
    "define": ["TEST", "OTHERCONDITION"]
  }
}
```

```xml
<PropertyGroup>
  <TreatWarningsAsErrors>true</TreatWarningsAsErrors>
  <NoWarn>$(NoWarn);CS0168;CS0219</NoWarn>
  <GenerateDocumentationFile>true</GenerateDocumentationFile>
  <PreserveCompilationContext>true</PreserveCompilationContext>
  <AssemblyName>Different.AssemblyName</AssemblyName>
  <DebugType>portable</DebugType>
  <AllowUnsafeBlocks>true</AllowUnsafeBlocks>
  <DefineConstants>$(DefineConstants);TEST;OTHERCONDITION</DefineConstants>
</PropertyGroup>
```

## <a name="packoptions"></a><span data-ttu-id="4c370-158">packOptions</span><span class="sxs-lookup"><span data-stu-id="4c370-158">packOptions</span></span>

<span data-ttu-id="4c370-159">[파일](#files)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4c370-159">See also [Files](#files).</span></span>

### <a name="common-pack-options"></a><span data-ttu-id="4c370-160">일반적인 팩 옵션</span><span class="sxs-lookup"><span data-stu-id="4c370-160">Common pack options</span></span>

```json
{
  "packOptions": {    
    "summary": "numl is a machine learning library intended to ease the use of using standard modeling techniques for both prediction and clustering.",
    "tags": ["machine learning", "framework"],
    "releaseNotes": "Version 0.9.12-beta",
    "iconUrl": "http://numl.net/images/ico.png",
    "projectUrl": "http://numl.net",
    "licenseUrl": "https://raw.githubusercontent.com/sethjuarez/numl/master/LICENSE.md",
    "requireLicenseAcceptance": false,
    "repository": {
      "type": "git",
      "url": "https://raw.githubusercontent.com/sethjuarez/numl"
    },
    "owners": ["Seth Juarez"]
  }
}
```

```xml
<PropertyGroup>
  <!-- summary is not migrated from project.json, but you can use the <Description> property for that if needed. -->
  <PackageTags>machine learning;framework</PackageTags>
  <PackageReleaseNotes>Version 0.9.12-beta</PackageReleaseNotes>
  <PackageIconUrl>http://numl.net/images/ico.png</PackageIconUrl>
  <PackageProjectUrl>http://numl.net</PackageProjectUrl>
  <PackageLicenseUrl>https://raw.githubusercontent.com/sethjuarez/numl/master/LICENSE.md</PackageLicenseUrl>
  <PackageRequireLicenseAcceptance>false</PackageRequireLicenseAcceptance>
  <RepositoryType>git</RepositoryType>
  <RepositoryUrl>https://raw.githubusercontent.com/sethjuarez/numl</RepositoryUrl>
  <!-- owners is not supported in MSBuild -->
</PropertyGroup>
```

<span data-ttu-id="4c370-161">MSBuild에는 `owners` 요소에 대해 동일한 요소가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-161">There is no equivalent for the `owners` element in MSBuild.</span></span> <span data-ttu-id="4c370-162">`summary`의 경우, `summary` 값이 자동으로 해당 속성에 마이그레이션되지 않은 경우에도 속성이 [ `description` ](#-other-common-root-level-options) 요소로 매핑되므로 MSBuild `<Description>` 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-162">For `summary`, you can use the MSBuild `<Description>` property, even though the value of `summary` is not migrated automatically to that property, since that property is mapped to the [`description`](#-other-common-root-level-options) element.</span></span>

## <a name="scripts"></a><span data-ttu-id="4c370-163">스크립트</span><span class="sxs-lookup"><span data-stu-id="4c370-163">scripts</span></span>

```json
{
  "scripts": {
    "precompile": "generateCode.cmd",
    "postpublish": [ "obfuscate.cmd", "removeTempFiles.cmd" ]
  }
}
```

<span data-ttu-id="4c370-164">MSBuild에서 해당하는 요소는 [targets](/visualstudio/msbuild/msbuild-targets)입니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-164">Their equivalent in MSBuild are [targets](/visualstudio/msbuild/msbuild-targets):</span></span>

```xml
<Target Name="MyPreCompileTarget" BeforeTargets="Build">
  <Exec Command="generateCode.cmd" />
</Target>

<Target Name="MyPostCompileTarget" AfterTargets="Publish">
  <Exec Command="obfuscate.cmd" />
  <Exec Command="removeTempFiles.cmd" />
</Target>
```


## <a name="runtimeoptions"></a><span data-ttu-id="4c370-165">runtimeOptions</span><span class="sxs-lookup"><span data-stu-id="4c370-165">runtimeOptions</span></span>

```json
{
  "runtimeOptions": {
    "configProperties": {
      "System.GC.Server": true,
      "System.GC.Concurrent": true,
      "System.GC.RetainVM": true,
      "System.Threading.ThreadPool.MinThreads": 4,
      "System.Threading.ThreadPool.MaxThreads": 25
    }
  }
}
```

<span data-ttu-id="4c370-166">"System.GC.Server" 속성을 제외하고, 이 그룹의 모든 설정은 마이그레이션 프로세스 중 루트 개체에 적용된 옵션과 함께 프로젝트 폴더에서 *runtimeconfig.template.json*이라는 파일에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-166">All settings in this group, except for the "System.GC.Server" property, are placed into a file called *runtimeconfig.template.json* in the project folder, with options lifted to the root object during the migration process:</span></span>

```json
{
  "configProperties": {
    "System.GC.Concurrent": true,
    "System.GC.RetainVM": true,
    "System.Threading.ThreadPool.MinThreads": 4,
    "System.Threading.ThreadPool.MaxThreads": 25
  }
}
```

<span data-ttu-id="4c370-167">"System.GC.Server" 속성은 csproj 파일로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-167">The "System.GC.Server" property is migrated into the csproj file:</span></span>
```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

<span data-ttu-id="4c370-168">그러나 MSBuild 속성뿐만 아니라 csproj에서 모든 해당 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-168">However, you can set all those values in the csproj as well as MSBuild properties:</span></span>
```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
  <ConcurrentGarbageCollection>true</ConcurrentGarbageCollection>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  <ThreadPoolMaxThreads>25</ThreadPoolMaxThreads>
</PropertyGroup>
```

## <a name="shared"></a><span data-ttu-id="4c370-169">공유</span><span class="sxs-lookup"><span data-stu-id="4c370-169">shared</span></span>
```json
{
  "shared": "shared/**/*.cs"
}
```

<span data-ttu-id="4c370-170">csproj에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-170">Not supported in csproj.</span></span> <span data-ttu-id="4c370-171">대신 *.nuspec* 파일에 콘텐츠 파일을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-171">You must instead create include content files in your *.nuspec* file.</span></span> <span data-ttu-id="4c370-172">자세한 내용은 [콘텐츠 파일 포함](/nuget/schema/nuspec#including-content-files)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4c370-172">For more information, see [Including content files](/nuget/schema/nuspec#including-content-files).</span></span>

## <a name="files"></a><span data-ttu-id="4c370-173">파일</span><span class="sxs-lookup"><span data-stu-id="4c370-173">files</span></span>

<span data-ttu-id="4c370-174">*project.json*에서 빌드 및 팩을 확장하여 컴파일하고 다른 폴더에서 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-174">In *project.json*, build and pack could be extended to compile and embed from different folders.</span></span>
<span data-ttu-id="4c370-175">MSBuild에서는 [항목](/visualstudio/msbuild/common-msbuild-project-items)을 사용하여 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-175">In MSBuild, this is done using [items](/visualstudio/msbuild/common-msbuild-project-items).</span></span> <span data-ttu-id="4c370-176">다음 예제는 일반적인 변환입니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-176">The following example is a common conversion:</span></span>

```json
{
  "buildOptions": {
    "compile": {
      "copyToOutput": "notes.txt",
      "include": "../Shared/*.cs",
      "exclude": "../Shared/Not/*.cs"
    },
    "embed": {
      "include": "../Shared/*.resx"
    }
  },
  "packOptions": {
    "include": "Views/",
    "mappings": {
      "some/path/in/project.txt": "in/package.txt"
    }
  },
  "publishOptions": {
    "include": [
      "files/",
      "publishnotes.txt"
    ]
  }
}
```

```xml
<ItemGroup>
  <Compile Include="..\Shared\*.cs" Exclude="..\Shared\Not\*.cs" />
  <EmbeddedResource Include="..\Shared\*.resx" />
  <Content Include="Views\**\*" PackagePath="%(Identity)" />
  <None Include="some/path/in/project.txt" Pack="true" PackagePath="in/package.txt" />
  
  <None Include="notes.txt" CopyToOutputDirectory="Always" />
  <!-- CopyToOutputDirectory = { Always, PreserveNewest, Never } -->

  <Content Include="files\**\*" CopyToPublishDirectory="PreserveNewest" />
  <None Include="publishnotes.txt" CopyToPublishDirectory="Always" />
  <!-- CopyToPublishDirectory = { Always, PreserveNewest, Never } -->
</ItemGroup>
```

> [!NOTE]
> <span data-ttu-id="4c370-177">많은 기본 [와일드카드 사용 패턴](https://en.wikipedia.org/wiki/Glob_(programming))이 .NET Core SDK에 의해 자동으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-177">Many of the default [globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are added automatically by the .NET Core SDK.</span></span>
> <span data-ttu-id="4c370-178">자세한 내용은 [기본 컴파일 항목 값](https://aka.ms/sdkimplicititems)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4c370-178">For more information, see [Default Compile Item Values](https://aka.ms/sdkimplicititems).</span></span>

<span data-ttu-id="4c370-179">모든 MSBuild `ItemGroup` 요소는 `Include`, `Exclude` 및 `Remove`를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-179">All MSBuild `ItemGroup` elements support `Include`, `Exclude`, and `Remove`.</span></span>

<span data-ttu-id="4c370-180">.nupkg 내의 패키지 레이아웃은 `PackagePath="path"`를 사용하여 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-180">Package layout inside the .nupkg can be modified with `PackagePath="path"`.</span></span>

<span data-ttu-id="4c370-181">`Content`를 제외하고, 대부분의 항목 그룹은 패키지에 포함되도록 `Pack="true"`를 명시적으로 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-181">Except for `Content`, most item groups require explicitly adding `Pack="true"` to be included in the package.</span></span> <span data-ttu-id="4c370-182">MSBuild `<IncludeContentInPack>` 속성이 기본적으로 `true`로 설정되어 있기 때문에 `Content`는 패키지의 *content* 폴더에 놓입니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-182">`Content` will be put in the *content* folder in a package since the MSBuild `<IncludeContentInPack>` property is set to `true` by default.</span></span> <span data-ttu-id="4c370-183">자세한 내용은 [패키지에 콘텐츠 포함](/nuget/schema/msbuild-targets#including-content-in-a-package)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4c370-183">For more information, see [Including content in a package](/nuget/schema/msbuild-targets#including-content-in-a-package).</span></span>

<span data-ttu-id="4c370-184">`PackagePath="%(Identity)"`는 패키지 경로를 프로젝트 상대 파일 경로에 설정하는 간단한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="4c370-184">`PackagePath="%(Identity)"` is a short way of setting package path to the project-relative file path.</span></span>

## <a name="testrunner"></a><span data-ttu-id="4c370-185">testRunner</span><span class="sxs-lookup"><span data-stu-id="4c370-185">testRunner</span></span>

### <a name="xunit"></a><span data-ttu-id="4c370-186">xUnit</span><span class="sxs-lookup"><span data-stu-id="4c370-186">xUnit</span></span>

```json
{
  "testRunner": "xunit",
  "dependencies": {
    "dotnet-test-xunit": "<any>"
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0-*" />
  <PackageReference Include="xunit" Version="2.2.0-*" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0-*" />
</ItemGroup>
```

### <a name="mstest"></a><span data-ttu-id="4c370-187">MSTest</span><span class="sxs-lookup"><span data-stu-id="4c370-187">MSTest</span></span>

```json
{
  "testRunner": "mstest",
  "dependencies": {
    "dotnet-test-mstest": "<any>"
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0-*" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.12-*" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.11-*" />
</ItemGroup>
```

## <a name="see-also"></a><span data-ttu-id="4c370-188">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4c370-188">See Also</span></span>

[<span data-ttu-id="4c370-189">CLI의 변경 내용에 대한 대략적인 개요</span><span class="sxs-lookup"><span data-stu-id="4c370-189">High-level overview of changes in CLI</span></span>](../tools/cli-msbuild-architecture.md)
