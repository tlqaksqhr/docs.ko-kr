---
title: ".NET Core Preview 4 도구에서 종속성 관리 | Microsoft 문서"
description: "Preview 4를 통해 종속성을 관리하는 방식에 대한 변경 내용 설명"
keywords: "CLI, 확장성, 사용자 지정 명령, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 11/12/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 74b87cdb-a244-4c13-908c-539118bfeef9
translationtype: Human Translation
ms.sourcegitcommit: 2ad428dcda9ef213a8487c35a48b33929259abba
ms.openlocfilehash: ad36f5ff8c1d74f1dd6b82ff620f85833d4dfb3e

---

# <a name="managing-dependencies-in-net-core-preview-4-tooling"></a>.NET Core Preview 4 도구에서 종속성 관리

[!INCLUDE[preview-warning](../../../includes/warning.md)]

.NET Core 프로젝트가 project.json에서 csproj 및 MSBuild로 이동하면서 상당한 투자가 발생했으며, 그 결과 종속성 추적을 허용하는 프로젝트 파일과 자산 통합이 이루어졌습니다. .NET Core 프로젝트의 경우 project.json의 경우와 비슷합니다. NuGet 종속성을 추적하는 별도 JSON 또는 XML 파일이 없습니다. 이 변경으로 `<PackageReference>`라는 csproj 구문에 대한 다른 *참조* 형식도 소개하였습니다. 

이 문서에서는 새 참조 형식을 설명합니다. 또한 프로젝트에 대한 이 새 참조 형식을 사용하여 패키지 종속성을 추가하는 방법을 보여 줍니다. 

## <a name="the-new-packagereference-element"></a>새 <PackageReference> 요소
`<PackageReference>`의 기본 구조는 다음과 같습니다.

```xml
<PackageReference Include="PACKAGE_ID">
    <Version>PACKAGE_VERSION</Version>
</PackageReference>
```

MSBuild에 익숙한 경우 이미 존재하는 다른 참조 형식에 익숙할 것입니다. 키는 프로젝트에 추가할 패키지 ID를 지정하는 `Include` 문입니다. `<Version>` 자식 요소는 가져올 버전을 지정합니다. 버전은 [NuGet 버전 규칙](https://docs.microsoft.com/nuget/create-packages/dependency-versions#version-ranges)에 따라 지정됩니다.

> [!NOTE]
> 전체 `csproj` 구문에 대해 잘 알고 있지 않은 경우 자세한 내용은[MSBuild 프로젝트 참조](https://docs.microsoft.com/visualstudio/msbuild/msbuild-project-file-schema-reference) 설명서를 참조하세요.  

특정 대상에만 사용할 수 있는 종속성을 추가하려면 다음 예와 같은 조건을 사용하여 수행합니다.

```xml
<PackageReference Include="PACKAGE_ID" Condition="'$(TargetFramework)' == 'netcoreapp1.0'">
    <Version>PACKAGE_VERSION</Version>
</PackageReference>
```

위의 예는 지정된 대상에 대해 빌드가 발생한 경우에만 종속성이 유효하다는 것을 의미합니다. 조건에서 `$(TargetFramework)`는 프로젝트에 설정 되는 MSBuild 속성입니다. 가장 일반적인.NET Core 응용 프로그램의 경우 이 작업을 수행하지 않아도 됩니다. 

## <a name="adding-a-dependency-to-your-project"></a>프로젝트에 종속성 추가
프로젝트에 종속성을 추가하는 작업은 간단합니다. 다음은 Json.NET 버전 `9.0.1`을 프로젝트에 추가하는 방법을 보여 주는 예입니다. 물론, 다른 NuGet 종속성에 적용됩니다. 

프로젝트 파일을 열면 `<ItemGroup>` 노드가 두 개 이상 나타납니다. 노드 중 하나에 이미 `<PackageReference>` 요소가 있다고 표시됩니다. 이 노드에 새 종속성을 추가하거나 새로 만들 수 있습니다. 둘 중 어떤 방법을 사용해도 결과는 동일합니다. 

이 예제에서는 `dotnet new`에서 삭제된 기본 템플릿을 사용해보겠습니다. 이는 간단한 콘솔 응용 프로그램입니다. 프로젝트를 열면 먼저 이미 기존 `<PackageReference>`에 `<ItemGroup>`이 있음을 확인할 수 있습니다. 그리고 다음을 추가합니다.

```xml
<PackageReference Include="Newtonsoft.Json">
    <Version>9.0.1</Version>
</PackageReference>
```
이렇게 되면 프로젝트를 저장하고 `dotnet restore` 명령을 실행하여 종속성을 설치합니다. 

전체 프로젝트는 다음과 같습니다.

```xml
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />
  
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.0</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <Compile Include="**\*.cs" />
    <EmbeddedResource Include="**\*.resx" />
  </ItemGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.NETCore.App">
      <Version>1.0.1</Version>
    </PackageReference>
    <PackageReference Include="Newtonsoft.Json">
        <Version>9.0.1</Version>
    </PackageReference>
    <PackageReference Include="Microsoft.NET.Sdk">
      <Version>1.0.0-alpha-20161104-2</Version>
      <PrivateAssets>All</PrivateAssets>
    </PackageReference>
  </ItemGroup>
  
  <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
</Project>
```

## <a name="removing-a-dependency-from-the-project"></a>프로젝트에서 종속성 제거
프로젝트 파일에서 종속성을 제거하는 작업은 프로젝트 파일에서 `<PackageReference>`를 단순히 제거하는 것입니다.


<!--HONumber=Jan17_HO3-->


