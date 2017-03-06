---
title: "csproj 참조 | Microsoft 문서"
description: "기존 및 .NET Core csproj 파일 간의 차이점에 대해 알아보기"
keywords: "참조, csproj, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 07/02/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: bdc29497-64f2-4d11-a21b-4097e0bdf5c9
translationtype: Human Translation
ms.sourcegitcommit: 0402707f98af8b716b041ba1260162cd227918cc
ms.openlocfilehash: 98f6ced2a199bdbe2f91f46e48ffd3ac52438cf8

---

# <a name="additions-to-the-csproj-format-for-net-core"></a>.NET Core용 csproj 형식에 대한 추가 사항

[!INCLUDE[preview-warning](../../../includes/warning.md)]

이 문서는 `project.json`에서 `csproj`, [MSBuild](https://github.com/Microsoft/MSBuild)로의 이동에 포함되어 csproj 파일에 추가된 변경 내용의 개요를 제공합니다. 일반 프로젝트 파일 구문 및 참조에 대한 자세한 내용은 [MSBuild 프로젝트 파일](https://docs.microsoft.com/visualstudio/msbuild/msbuild-project-file-schema-reference) 설명서를 참조하세요.  

## <a name="additions"></a>추가

* 프로젝트의 NuGet 종속성을 지정하는 PackageReference 항목입니다. `Include` 특성은 패키지 ID를 지정합니다. 

```xml
<PackageReference Include="<package-id>" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

## <a name="version"></a>버전
`Version`은 복원할 패키지 버전을 지정합니다. 요소는 NuGet 버전 지정 체계의 규칙을 따릅니다.

## <a name="includeassets"></a>IncludeAssets
`IncludeAssets` 특성은 `<PackageReference>`에서 지정한 패키지에 속하여 사용해야 하는 자산을 지정합니다. 

이 특성은 다음 값 중 하나 이상을 포함할 수 있습니다.

* `Compile` - lib 폴더의 콘텐츠를 컴파일에 사용할 수 있습니다.
* `Runtime` - 런타임 폴더의 콘텐츠가 분산됩니다.
* `ContentFiles` - 콘텐츠 파일 폴더의 콘텐츠가 사용됩니다.
* `Build` - 빌드 폴더의 속성/대상이 사용됩니다.
* `Native` - 런타임에 네이티브 자산의 콘텐츠가 출력 폴더에 복사됩니다.
* `Analyzers` – 분석기가 사용됩니다.

또는 다음 특성이 포함될 수 있습니다.

* `None` – 자산이 사용되지 않습니다.
* `All` – 모든 자산이 사용됩니다.

## <a name="excludeassets"></a>ExcludeAssets
`ExcludeAssets` 특성은 `<PackageReference>`에서 지정한 패키지에 속하여 사용하지 말아야 하는 자산을 지정합니다.

이 특성은 다음 값 중 하나 이상을 포함할 수 있습니다.

* `Compile` - lib 폴더의 콘텐츠를 컴파일에 사용할 수 있습니다.
* `Runtime` - 런타임 폴더의 콘텐츠가 분산됩니다.
* `ContentFiles` - 콘텐츠 파일 폴더의 콘텐츠가 사용됩니다.
* `Build` - 빌드 폴더의 속성/대상이 사용됩니다.
* `Native` - 런타임에 네이티브 자산의 콘텐츠가 출력 폴더에 복사됩니다.
* `Analyzers` – 분석기가 사용됩니다.

또는 다음 요소가 포함될 수 있습니다.

* `None` – 자산이 사용되지 않습니다.
* `All` – 모든 자산이 사용됩니다.

## <a name="privateassets"></a>PrivateAssets
`PrivateAssets` 특성은 `<PackageReference>`에서 지정한 패키지에 속하여 사용해야 하지만 다음 프로젝트로 전달하지 말아야 하는 자산을 지정합니다. 

> [!NOTE]
> 이 요소는 project.json/xproj `SuppressParent` 요소에 대한 새 용어입니다. 

이 특성은 다음 값 중 하나 이상을 포함할 수 있습니다.

* `Compile` - lib 폴더의 콘텐츠를 컴파일에 사용할 수 있습니다.
* `Runtime` - 런타임 폴더의 콘텐츠가 분산됩니다.
* `ContentFiles` - 콘텐츠 파일 폴더의 콘텐츠가 사용됩니다.
* `Build` - 빌드 폴더의 속성/대상이 사용됩니다.
* `Native` - 런타임에 네이티브 자산의 콘텐츠가 출력 폴더에 복사됩니다.
* `Analyzers` – 분석기가 사용됩니다.

또는 다음 특성이 포함될 수 있습니다.

* `None` – 자산이 사용되지 않습니다.
* `All` – 모든 자산이 사용됩니다.

* DotnetCliToolReference `<DotnetCliToolReference>` 항목 요소는 사용자가 프로젝트의 컨텍스트에서 복원할 CLI 도구를 지정합니다. 이 요소는 `project.json`의 `tools` 노드를 대체합니다. 

```xml
<DotnetCliToolReference Include="<package-id>" Version="" />
```

## <a name="version"></a>버전
`Version`은 복원할 패키지 버전을 지정합니다. 이 특성은 NuGet 버전 지정 체계의 규칙을 따릅니다.

* RuntimeIdentifiers - `<RuntimeIdentifiers>` 요소를 사용하면 프로젝트에 대해 세미콜론으로 구분된 [RID(런타임 식별자)](../../rid-catalog.md) 목록을 지정할 수 있습니다. RID를 통해 자체 포함 배포를 게시할 수 있습니다. 

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```


* RuntimeIdentifier - `<RuntieIdentifier>` 요소를 사용하면 프로젝트의 [RID(런타임 식별자)](../../rid-catalog.md)를 하나만 지정할 수 있습니다. RID를 통해 자체 포함 배포를 게시할 수 있습니다. 

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```


* PackageTargetFallback - `<PackageTargetFallback>` 요소를 사용하면 패키지를 복원할 때 사용할 호환 가능한 대상 집합을 지정할 수 있습니다. 이는 dotnet TxM을 사용하는 패키지가 dotnet TxM를 선언하지 않은 패키지와 작동하도록 하기 위한 것입니다. 프로젝트에서 dotnet TxM을 사용하는 경우 dotnet이 아닌 플랫폼이 dotnet과 호환되도록 하기 위해 프로젝트에 `<PackageTargetFallback>`을 추가하지 않는 경우 사용하는 모든 프로젝트에도 dotnet TxM이 있어야 합니다. 

다음 예제에서는 프로젝트의 모든 대상에 대한 대체를 제공합니다. 

```xml
<PackageTargetFallback>
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

다음 예제에서는 `netcoreapp1.0` 대상에 대해서만 대체를 지정합니다.

```xml
<PackageTargetFallback Condition="'$(TargetFramework)'=='netcoreapp1.0'">
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

## <a name="nuget-metadata-properties"></a>NuGet 메타데이터 속성
MSbuild로 전환하면서 NuGet 패키지를 압축할 때 사용되는 입력 메타데이터를 project.json에서 csproj 파일로 전환했습니다. 이 입력은 MSBuild 속성입니다. 다음은 `dotnet pack` 명령 또는 SDK의 일부인 `Pack` MSBuild 대상을 사용할 때 압축 프로세스의 입력으로 사용되는 속성 목록입니다. 

* IsPackable
* PackageVersion
* PackageId
* 제목
* 만든 이
* 설명
* Copyright
* PackageRequireLicenseAcceptance
* PackageLicenseUrl
* PackageProjectUrl
* PackageIconUrl
* PackageReleaseNotes
* PackageTags
* PackageOutputPath
* IncludeSymbols
* IncludeSource
* PackageTypes
* IsTool
* RepositoryUrl
* RepositoryType
* NoPackageAnalysis
* MinClientVersion
* IncludeBuildOutput
* IncludeContentInPack
* BuildOutputTargetFolder
* ContentTargetFolders
* NuspecFile
* NuspecBasePath
* NuspecProperties


<!--HONumber=Feb17_HO2-->


