---
title: "dotnet-build 명령 | Microsoft 문서"
description: "dotnet-build 명령은 프로젝트와 모든 종속성을 빌드합니다."
keywords: "dotnet-build, CLI, CLI 명령, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 5e1a2bc4-a919-4a86-8f33-a9b218b1fcb3
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 17c2db54f871795c370a6475c21e36736a6b46c3
ms.lasthandoff: 03/07/2017

---
#<a name="dotnet-build"></a>dotnet-build

## <a name="name"></a>이름

`dotnet-build` - 프로젝트 및 모든 종속성을 빌드합니다.

## <a name="synopsis"></a>개요

```
dotnet build [project] [-o|--output] [-f|--framework] [-c|--configuration] [-r|--runtime] [--version-suffix] [--no-incremental] [--no-dependencies] [-v|--verbosity]
dotnet build [--help]
```

## <a name="description"></a>설명
`dotnet build` 명령은 이진 파일 집합으로 프로젝트와 해당 종속성을 빌드합니다. 이진 파일은 `*.dll` 확장을 사용하는 IL(중간 언어)의 프로젝트 코드뿐만 아니라 디버깅에 사용되는 기호 파일(`*.pdb` 확장 포함)입니다. 또한 `*.deps.json` 확장을 사용하는 응용 프로그램의 종속성을 나열하는 JSON 파일이 생성됩니다. 마지막으로 `runtime.config.json` 파일도 생성됩니다. 이 파일은 빌드된 코드가 실행하는 공유 런타임 및 버전을 지정합니다. 

프로젝트에 NuGet의 라이브러리와 같은 타사 종속성이 있는 경우, 이러한 종속성은 NuGet 캐시에서 확인되고 프로젝트의 빌드 출력으로 사용할 수 없습니다. 따라서 `dotnet build`의 제품을 실행하기 위해 다른 컴퓨터로 전송할 준비가 되지 않았습니다. 이는 실행 가능한 프로젝트(응용 프로그램) 빌드로 .NET Framework가 설치된 컴퓨터에서 실행할 수 있는 출력을 생성하는 .NET Framework의 동작과는 대조적입니다. .NET Core에서 비슷한 환경을 가져오려면 [dotnet publish](dotnet-publish.md) 명령을 사용해야 합니다. 이에 대한 자세한 내용은 [.NET Core 응용 프로그램 배포](../deploying/index.md) 문서에서 확인할 수 있습니다. 

빌드하려면 *assets.json* 파일(응용 프로그램의 종속성을 모두 나열하는 파일)의 확장이 있어야 합니다. 즉, 프로젝트를 빌드하기 전에 [`dotnet restore`](dotnet-restore.md)를 실행해야 합니다. 자산 파일이 부족하면 참조 어셈블리를 확인하는 도구를 사용할 수 없으므로 오류가 발생합니다. 

`dotnet build`는 MSBuild를 사용하여 프로젝트를 빌드하므로 병렬 빌드와 증분 빌드를 모두 지원합니다. 해당 항목에 대한 자세한 내용은 [MSBuild 설명서](https://docs.microsoft.com/visualstudio/msbuild/msbuild)를 참조하세요. 

해당 옵션 외에도, `dotnet build` 명령은 속성 설정에 대한 `/p` 또는 로거를 정의하는 `/l`처럼 MSBuild 옵션도 수락합니다. [ `dotnet msbuild` ](dotnet-msbuild.md) 명령 설명서에서 이러한 옵션에 대한 자세한 내용을 확인할 수 있습니다. 시기를 알고 싶은 경우 

프로젝트가 실행 가능한지 아닌지 여부는 프로젝트 파일의 `<OutputType>` 속성으로 확인할 수 있습니다. 다음 예제에서는 실행 코드를 생성하는 프로젝트를 보여 줍니다. 


```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

라이브러리를 생성하려면 해당 속성을 생략하면 됩니다. 출력의 주요 차이점은 라이브러리에 대한 IL DLL에 진입점이 포함되지 않고 실행할 수 없다는 점입니다. 

## <a name="arguments"></a>인수

`project`

빌드할 프로젝트 파일입니다.
프로젝트 파일을 지정하지 않으면 MSBuild는 현재 작업 디렉터리에서 `proj`로 끝나는 파일 확장명이 있는 파일을 검색하고 해당 파일을 사용합니다.

## <a name="options"></a>옵션

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.

`-o|--output <OUTPUT_DIRECTORY>`

빌드된 이진 파일을 배치할 디렉터리입니다. 이 옵션을 지정하는 경우 `--framework`도 정의해야 합니다.

`-f|--framework <FRAMEWORK>`

특정 프레임워크에 대해 컴파일합니다. 프레임워크는 [프로젝트](csproj.md) 파일에 정의해야 합니다.

`-c|--configuration [Debug|Release]`

빌드할 구성을 정의합니다. 생략하면 `Debug`로 기본 설정됩니다.

`-r|--runtime [RUNTIME_IDENTIFIER]`

빌드할 대상 런타임입니다. 사용할 수 있는 RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요.

`--version-suffix [VERSION_SUFFIX]`

프로젝트 파일의 버전 필드에서 `*`를 대체할 항목을 정의합니다. 형식은 NuGet의 버전 지침을 따릅니다.

`--no-incremental`

빌드를 증분 빌드에 안전하지 않은 것으로 표시합니다. 따라서 증분 컴파일이 해제되고 프로젝트 종속성 그래프를 강제로 완전히 다시 빌드합니다.

`--no-dependencies`

프로젝트 간 참조를 무시하고 빌드하도록 지정된 루트 프로젝트만 빌드합니다.

`-v|--verbosity`

명령의 세부 정보 표시 수준을 설정합니다. 허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.

## <a name="examples"></a>예제

프로젝트 및 해당 종속성을 빌드합니다.

`dotnet build`

릴리스 구성을 사용하여 프로젝트 및 해당 종속성을 빌드합니다.

`dotnet build --configuration Release`

특정 런타임(이 예제의 경우 Ubuntu 16.04)에 대한 프로젝트 및 해당 종속성을 빌드합니다.

`dotnet build --runtime ubuntu.16.04-x64`
