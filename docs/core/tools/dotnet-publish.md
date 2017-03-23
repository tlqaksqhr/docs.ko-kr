---
title: "dotnet-publish 명령 | Microsoft 문서"
description: "dotnet-publish 명령은 .NET Core 프로젝트를 디렉터리에 게시합니다."
keywords: "dotnet-publish, CLI, CLI 명령, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/07/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: f2ef275a-7c5e-430a-8c30-65f52af62771
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 78487673d8fa07286605fb806f30083747b17386
ms.lasthandoff: 03/07/2017

---
#<a name="dotnet-publish"></a>dotnet-publish

## <a name="name"></a>이름

`dotnet-publish` - 응용 프로그램 및 모든 종속성을 폴더로 압축하여 게시할 준비를 합니다.

## <a name="synopsis"></a>개요

```
dotnet publish [project] [-f|--framework] [-r|--runtime] [-o|--output] [-c|--configuration] [--version-suffix] [-v|--verbosity]
dotnet publish [-h|--help]
```

## <a name="description"></a>설명

`dotnet publish`는 응용 프로그램을 컴파일하고 프로젝트 파일에 지정된 종속성을 읽은 다음 결과 파일 집합을 디렉터리에 게시합니다. 출력에는 다음이 포함됩니다.

1. `*.dll` 확장과 함께 어셈블리의 IL(중간 언어) 코드
2. 프로젝트의 종속성이 모두 포함된 *deps.json* 파일 
3. 런타임에 대한 기타 구성 옵션(예: 가비지 수집 유형)뿐만 아니라 응용 프로그램에서 예상하는 공유 런타임을 지정하는 *Runtime.config.json* 파일
4. 모든 응용 프로그램의 종속성. 이러한 종속성은 NuGet 캐시에서 출력 폴더로 복사됩니다. 

`dotnet publish` 명령의 출력은 원격 컴퓨터에 배포하여 실행할 수 있으며, 응용 프로그램을 다른 컴퓨터(예: 서버)에 배포하여 실행할 수 있는 공식적인 방법으로 유일하게 지원됩니다. 프로젝트에서 지정하는 배포 유형에 따라 원격 컴퓨터에 .NET Core 공유 런타임을 설치해야 합니다. 자세한 내용은 [.NET Core 응용 프로그램 배포](../deploying/index.md) 항목을 참조하세요.

## <a name="arguments"></a>인수

`project` 

게시할 프로젝트이며, `project`를 지정하지 않을 경우 현재 디렉터리로 기본 설정됩니다. 

## <a name="options"></a>옵션

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.  

`-f|--framework <FRAMEWORK>`

지정한 대상 프레임워크에 대한 응용 프로그램을 게시합니다. 대상 프레임워크는 프로젝트 파일에 지정되어야 합니다.

`-r|--runtime <RUNTIME_IDENTIFIER>`

지정된 런타임에 대한 응용 프로그램을 게시합니다. [자체 포함 배포](../deploying/index.md#self-contained-deployments-scd)를 만들 때 사용됩니다. 사용할 수 있는 RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요. 기본값은 [프레임워크 종속 앱](../deploying/index.md#framework-dependent-deployments-fdd)을 게시하는 것입니다.

`-o|--output <OUTPUT_PATH>`

디렉터리를 배치할 경로를 지정합니다. 지정하지 않으면 이식 가능한 응용 프로그램의 경우 *_./bin/[configuration]/[framework]/_*로, 자체 포함 배포의 경우 *_./bin/[configuration]/[framework]/[runtime]_*으로 기본 설정됩니다.

`-c|--configuration {Debug|Release}`

프로젝트를 빌드할 때 사용할 구성입니다. 기본값은 `Debug`입니다.

`--version-suffix <VERSION_SUFFIX>`

프로젝트 파일의 버전 필드에서 `*`를 대체할 항목을 정의합니다.

`-v|--verbosity <LEVEL>`

명령의 세부 정보 표시 수준을 설정합니다. 허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.

## <a name="examples"></a>예제

현재 디렉터리에 있는 프로젝트를 게시합니다.

`dotnet publish`

지정된 프로젝트 파일을 사용하여 응용 프로그램을 게시합니다.

`dotnet publish ~/projects/app1/app1.csproj`
    
`netcoreapp1.1` 프레임워크를 사용하여 현재 디렉터리에 있는 프로젝트를 게시합니다.

`dotnet publish --framework netcoreapp1.1`
    
`netcoreapp1.1` 프레임워크 및 `OS X 10.10`에 대한 런타임을 사용하여 현재 응용 프로그램을 게시합니다. 이 RID는 프로젝트 파일에 있어야 합니다.

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

## <a name="see-also"></a>참고 항목
* [프레임워크](../../standard/frameworks.md)
* [RID(런타임 식별자) 카탈로그](../rid-catalog.md)
