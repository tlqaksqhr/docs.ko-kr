---
title: "csproj 참조 |.NET Core SDK"
description: "기존 및 .NET Core csproj 파일 간의 차이점에 대해 알아보기"
keywords: "참조, csproj, .NET Core"
author: blackdwarf
ms.author: mairaw
manager: wpickett
ms.date: 10/12/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: bdc29497-64f2-4d11-a21b-4097e0bdf5c9
translationtype: Human Translation
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: af32bc592762d7e8cb4e3b180656d9c3464df4a5

---

<a name="additions-to-csproj-format-for-net-core"></a>.NET Core용 csproj 형식 추가
----------------------------------------

# <a name="overview"></a>개요 
이 문서는 project.json에서 csproj 및 [MSBuild](https://github.com/Microsoft/MSBuild)로 이동에 포함되어 csproj 파일에 추가된 변경 내용에 대해 간략하게 설명합니다. 이 문서에서는 **비핵심 csproj 파일에 대한 델타만** 설명합니다. 일반 프로젝트 파일 구문 및 참조에 대한 자세한 내용은 [MSBuild 프로젝트 파일]() 설명서를 참조하세요. 

> **참고:** 이 문서는 차후에 확장될 예정으로 나중에 다시 방문하여 새 추가 내용을 확인해 보세요. 

# <a name="additions"></a>추가

## <a name="packagereference"></a>PackageReference
프로젝트의 NuGet 종속성을 지정합니다. `Include` 특성은 패키지 ID를 지정합니다. 

```xml
<PackageReference Include="<package-id>">
    <Version></Version>
    <PrivateAssets></PrivateAssets>
    <IncludeAssets></IncludeAssets>
    <ExcludeAssets></ExcludeAssets>
</PackageReference>
```

### <a name="version"></a>버전
`<Version>`은 복원할 패키지 버전을 지정합니다. 요소는 NuGet 버전 지정 체계의 규칙을 따릅니다.

### <a name="includeassets"></a>IncludeAssets
`<IncludeAssets>` 자식 요소는 부모 `<PackageReference>`에서 지정한 패키지에 속하여 사용해야 하는 자산을 지정합니다. 

요소는 다음 값 중 하나 이상을 포함할 수 있습니다.

* Compile � 컴파일에 사용할 수 있는 lib 폴더의 콘텐츠
* Runtime � 분산된 런타임 폴더의 콘텐츠
* ContentFiles � 사용되는 콘텐츠 파일 폴더의 콘텐츠
* Build � 사용되는 빌드 폴더에서 속성/대상 수행
* Native - 런타임에 대한 출력 폴더로 복사된 네이티브 자산 콘텐츠
* Analyzers � 분석기 사용 실행

또는 다음 요소가 포함될 수 있습니다.

* None � 사용되는 작업 없음
* All � 모두 사용됨

### <a name="excludeassets"></a>ExcludeAssets
`<ExcluseAssets>` 자식 요소는 부모 `<PackageReference>`에서 지정한 패키지에 속하여 사용하지 말아야 하는 자산을 지정합니다.

요소는 다음 값 중 하나 이상을 포함할 수 있습니다.

* Compile � 컴파일에 사용할 수 있는 lib 폴더의 콘텐츠
* Runtime � 분산된 런타임 폴더의 콘텐츠
* ContentFiles � 사용되는 콘텐츠 파일 폴더의 콘텐츠
* Build � 사용되는 빌드 폴더에서 속성/대상 수행
* Native - 런타임에 대한 출력 폴더로 복사된 네이티브 자산 콘텐츠
* Analyzers � 분석기 사용 실행

또는 다음 요소가 포함될 수 있습니다.

* None � 사용되는 작업 없음
* All � 모두 사용됨

### <a name="privateassets"></a>PrivateAssets
`<PrivateAssets>` 자식 요소는 부모 `<PackageReference>`에서 지정한 패키지에 속하여 사용해야 하지만 다음 프로젝트로 전달하지 말아야 하는 자산을 지정합니다. 

> **참고:** 이 요소는 project.json/xproj `SupressParent` 요소에 대한 새 용어입니다. 

요소는 다음 값 중 하나 이상을 포함할 수 있습니다.

* Compile � 컴파일에 사용할 수 있는 lib 폴더의 콘텐츠
* Runtime � 분산된 런타임 폴더의 콘텐츠
* ContentFiles � 사용되는 콘텐츠 파일 폴더의 콘텐츠
* Build � 사용되는 빌드 폴더에서 속성/대상 수행
* Native - 런타임에 대한 출력 폴더로 복사된 네이티브 자산 콘텐츠
* Analyzers � 분석기 사용 실행

또는 다음 요소가 포함될 수 있습니다.

* None � 사용되는 작업 없음
* All � 모두 사용됨

## <a name="dotnetclitoolreference"></a>DotnetCliToolReference
`<DotnetCliToolReference>` 요소는 사용자가 프로젝트의 컨텍스트에서 복원할 CLI 도구를 지정합니다. 이 요소는 `project.json`의 `tools` 노드를 대체합니다. 

### <a name="version"></a>버전
`<Version>`은 복원할 패키지 버전을 지정합니다. 요소는 NuGet 버전 지정 체계의 규칙을 따릅니다.

## <a name="runtimeidentifiers"></a>RuntimeIdentifiers
`<RuntimeIdentifiers>` 요소를 사용하면 프로젝트에 대해 [런타임 식별자](../../rid-catalog.md)가 세미콜론으로 구분된 목록을 지정합니다. 자체 포함된 배포를 게시할 수 있습니다. 




<!--HONumber=Nov16_HO3-->


