---
title: "dotnet-add reference 명령 | Microsoft 문서"
description: "dotnet-add reference 명령은 프로젝트 간 참조를 추가하는 편리한 옵션을 제공합니다."
keywords: "dotnet-add, CLI, CLI 명령, .NET Core"
author: spboyer
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 5e2a3efd-443c-4f23-a1b1-a662a5387879
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 7d23377244cfe60730b50bd247209de6e90bec70
ms.lasthandoff: 03/07/2017

---
# <a name="dotnet-add-reference"></a>dotnet-add reference

## <a name="name"></a>이름

`dotnet-add reference` - 프로젝트 간 참조를 추가합니다.

## <a name="synopsis"></a>개요

```
dotnet add [project] reference [-f|--framework] <project_references>
dotnet add reference [-h|--help]
```

## <a name="description"></a>설명

`dotnet add reference` 명령은 프로젝트에 프로젝트 참조를 추가하는 편리한 옵션을 제공합니다. 명령을 실행한 후 [ `<ProjectReference>` ](https://docs.microsoft.com/visualstudio/msbuild/common-msbuild-project-items) 조각이 프로젝트 파일에 추가됩니다.

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a>인수

`project`

작동할 프로젝트 파일입니다. 지정하지 않으면 이 명령은 현재 디렉터리에서 솔루션 파일을 하나 검색합니다.

`project_references`

추가할 프로젝트 간 참조입니다. 하나 또는 여러 프로젝트를 지정할 수 있습니다. Unix/Linux 기반 터미널에서는 GLOB 패턴이 지원됩니다.

## <a name="options"></a>옵션

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.

`-f|--framework <FRAMEWORK>`

특정 프레임워크를 대상으로 하는 경우에만 프로젝트 참조를 추가합니다.

## <a name="examples"></a>예제

프로젝트 참조 추가:

`dotnet add app/app.csproj reference lib/lib.csproj`

여러 프로젝트 참조 추가:

`dotnet add reference lib1/lib1.csproj lib2/lib2.csproj`

Linux/Unix에서 와일드카드 사용 패턴을 사용하여 여러 프로젝트 참조 추가:

`dotnet add app/app.csproj reference **/*.csproj`
