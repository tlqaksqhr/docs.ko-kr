---
title: "csproj 참조 | Microsoft 문서"
description: "기존 및 .NET Core csproj 파일 간의 차이점에 대해 알아보기"
keywords: "참조, csproj, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 10/12/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: bdc29497-64f2-4d11-a21b-4097e0bdf5c9
translationtype: Human Translation
ms.sourcegitcommit: 2ad428dcda9ef213a8487c35a48b33929259abba
ms.openlocfilehash: dfa7cc0f7005269b4e2560c8bbc8b049ed02cc1a

---

# <a name="additions-to-the-csproj-format-for-net-core"></a>.NET Core용 csproj 형식에 대한 추가 사항

[!INCLUDE[preview-warning](../../../includes/warning.md)]

이 문서는 `project.json`에서 `csproj`, [MSBuild](https://github.com/Microsoft/MSBuild)로의 이동에 포함되어 csproj 파일에 추가된 변경 내용의 개요를 제공합니다. 일반 프로젝트 파일 구문 및 참조에 대한 자세한 내용은 [MSBuild 프로젝트 파일](https://docs.microsoft.com/visualstudio/msbuild/msbuild-project-file-schema-reference) 설명서를 참조하세요.  

## <a name="additions"></a>추가

### <a name="packagereference"></a>PackageReference
프로젝트의 NuGet 종속성을 지정합니다. `Include` 특성은 패키지 ID를 지정합니다. 

```xml
<PackageReference Include="<package-id>">
    <Version></Version>
    <PrivateAssets></PrivateAssets>
    <IncludeAssets></IncludeAssets>
    <ExcludeAssets></ExcludeAssets>
</PackageReference>
```

#### <a name="version"></a>버전
`<Version>`은 복원할 패키지 버전을 지정합니다. 요소는 NuGet 버전 지정 체계의 규칙을 따릅니다.

#### <a name="includeassets"></a>IncludeAssets
`<IncludeAssets>` 자식 요소는 부모 `<PackageReference>`에서 지정한 패키지에 속하여 사용해야 하는 자산을 지정합니다. 

요소는 다음 값 중 하나 이상을 포함할 수 있습니다.

* Compile - lib 폴더의 콘텐츠를 컴파일에 사용할 수 있습니다.
* Runtime - 런타임 폴더의 콘텐츠가 분산됩니다.
* ContentFiles - 콘텐츠 파일 폴더의 콘텐츠가 사용됩니다.
* Build - 빌드 폴더의 속성/대상이 사용됩니다.
* Native - 런타임에 네이티브 자산의 콘텐츠가 출력 폴더에 복사됩니다.
* Analyzers – 분석기가 사용됩니다.

또는 다음 요소가 포함될 수 있습니다.

* None – 자산이 사용되지 않습니다.
* All – 모든 자산이 사용됩니다.

#### <a name="excludeassets"></a>ExcludeAssets
`<ExcludeAssets>` 자식 요소는 부모 `<PackageReference>`에서 지정한 패키지에 속하여 사용하지 말아야 하는 자산을 지정합니다.

요소는 다음 값 중 하나 이상을 포함할 수 있습니다.

* Compile - lib 폴더의 콘텐츠를 컴파일에 사용할 수 있습니다.
* Runtime - 런타임 폴더의 콘텐츠가 분산됩니다.
* ContentFiles - 콘텐츠 파일 폴더의 콘텐츠가 사용됩니다.
* Build - 빌드 폴더의 속성/대상이 사용됩니다.
* Native - 런타임에 네이티브 자산의 콘텐츠가 출력 폴더에 복사됩니다.
* Analyzers – 분석기가 사용됩니다.

또는 다음 요소가 포함될 수 있습니다.

* None – 자산이 사용되지 않습니다.
* All – 모든 자산이 사용됩니다.

#### <a name="privateassets"></a>PrivateAssets
`<PrivateAssets>` 자식 요소는 부모 `<PackageReference>`에서 지정한 패키지에 속하여 사용해야 하지만 다음 프로젝트로 전달하지 말아야 하는 자산을 지정합니다. 

> [!NOTE]
> 이 요소는 project.json/xproj `SuppressParent` 요소에 대한 새 용어입니다. 

요소는 다음 값 중 하나 이상을 포함할 수 있습니다.

* Compile - lib 폴더의 콘텐츠를 컴파일에 사용할 수 있습니다.
* Runtime - 런타임 폴더의 콘텐츠가 분산됩니다.
* ContentFiles - 콘텐츠 파일 폴더의 콘텐츠가 사용됩니다.
* Build - 빌드 폴더의 속성/대상이 사용됩니다.
* Native - 런타임에 네이티브 자산의 콘텐츠가 출력 폴더에 복사됩니다.
* Analyzers – 분석기가 사용됩니다.

또는 다음 요소가 포함될 수 있습니다.

* None – 자산이 사용되지 않습니다.
* All – 모든 자산이 사용됩니다.

### <a name="dotnetclitoolreference"></a>DotnetCliToolReference
`<DotnetCliToolReference>` 요소는 사용자가 프로젝트의 컨텍스트에서 복원할 CLI 도구를 지정합니다. 이 요소는 `project.json`의 `tools` 노드를 대체합니다. 

#### <a name="version"></a>버전
`<Version>`은 복원할 패키지 버전을 지정합니다. 요소는 NuGet 버전 지정 체계의 규칙을 따릅니다.

### <a name="runtimeidentifiers"></a>RuntimeIdentifiers
`<RuntimeIdentifiers>` 요소를 사용하면 프로젝트에 대해 세미콜론으로 구분된 [RID(런타임 식별자)](../../rid-catalog.md) 목록을 지정할 수 있습니다. RID를 통해 자체 포함 배포를 게시할 수 있습니다. 


<!--HONumber=Jan17_HO3-->


