---
title: "dotnet-publish 명령 - .NET Core CLI | Microsoft Docs"
description: "dotnet-publish 명령은 .NET Core 프로젝트를 디렉터리에 게시합니다."
keywords: "dotnet-publish, CLI, CLI 명령, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: f2ef275a-7c5e-430a-8c30-65f52af62771
translationtype: Human Translation
ms.sourcegitcommit: dff752a9d31ec92b113dae9eed20cd72faf57c84
ms.openlocfilehash: 48bfe6c77ee6c5d905069f47da5512ac63a24b2a
ms.lasthandoff: 03/22/2017

---

# <a name="dotnet-publish"></a>dotnet-publish

## <a name="name"></a>이름

`dotnet-publish` - 호스팅 시스템에 배포하기 위해 응용 프로그램 및 해당 종속성을 폴더에 압축합니다.

## <a name="synopsis"></a>개요

`dotnet publish [<PROJECT>] [-f|--framework] [-r|--runtime] [-o|--output] [-c|--configuration] [--version-suffix] [-v|--verbosity] [-h|--help]`

## <a name="description"></a>설명

`dotnet publish`는 응용 프로그램을 컴파일하고 프로젝트 파일에 지정된 종속성을 읽은 다음 결과 파일 집합을 디렉터리에 게시합니다. 출력에는 다음이 포함됩니다.

* `*.dll` 확장과 함께 어셈블리의 IL(중간 언어) 코드
* 프로젝트의 종속성이 모두 포함된 *\*.deps.json* 파일
* 런타임에 대한 기타 구성 옵션(예: 가비지 수집 유형)뿐만 아니라 응용 프로그램에서 예상하는 공유 런타임을 지정하는 *\*.runtime.config.json* 파일
* 응용 프로그램의 종속성. 이러한 종속성은 NuGet 캐시에서 출력 폴더로 복사됩니다.

`dotnet publish` 명령의 출력은 실행을 위해 호스팅 시스템(예: 서버, PC, Mac, 랩톱)으로 배포할 준비가 되었으며 응용 프로그램의 배포를 준비하는 공식적으로 지원되는 유일한 방법입니다. 프로젝트에서 지정하는 배포 유형에 따라 호스팅 시스템에 .NET Core 공유 런타임이 설치되어 있을 수도 있고 그렇지 않을 수도 있습니다. 자세한 내용은 [.NET Core 응용 프로그램 배포](../deploying/index.md)를 참조하세요. 게시된 응용 프로그램의 디렉터리 구조에 대해서는 [디렉터리 구조](https://docs.microsoft.com/en-us/aspnet/core/hosting/directory-structure)를 참조하세요.

## <a name="arguments"></a>인수

`PROJECT` 

게시할 프로젝트이며, 지정하지 않을 경우 현재 디렉터리로 기본 설정됩니다. 

## <a name="options"></a>옵션

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.  

`-f|--framework <FRAMEWORK>`

지정한 [대상 프레임워크](../../standard/frameworks.md)에 대한 응용 프로그램을 게시합니다. 프로젝트 파일에 대상 프레임워크를 지정해야 합니다.

`-r|--runtime <RUNTIME_IDENTIFIER>`

지정된 런타임에 대한 응용 프로그램을 게시합니다. [SCD(자체 포함 배포_](../deploying/index.md#self-contained-deployments-scd)를 만들 때 사용됩니다. RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요. 기본값은 [FDD(프레임워크 종속 배포)](../deploying/index.md#framework-dependent-deployments-fdd)를 게시하는 것입니다.

`-o|--output <OUTPUT_DIRECTORY>`

출력 디렉터리의 경로를 지정합니다. 지정하지 않으면 프레임워크 종속 배포의 경우 *./bin/[configuration]/[framework]/*로, 자체 포함 배포의 경우 *./bin/[configuration]/[framework]/[runtime]*으로 기본 설정됩니다.

`-c|--configuration <CONFIGURATION>`

프로젝트를 빌드할 때 사용할 구성입니다. 기본값은 `Debug`입니다.

`--version-suffix <VERSION_SUFFIX>`

프로젝트 파일의 버전 필드에서 별표(`*`)를 대신할 버전 접미사를 정의합니다.

`-v|--verbosity <LEVEL>`

명령의 세부 정보 표시 수준을 설정합니다. 허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.

## <a name="examples"></a>예제

현재 디렉터리에 있는 프로젝트를 게시합니다.

`dotnet publish`

지정된 프로젝트 파일을 사용하여 응용 프로그램을 게시합니다.

`dotnet publish ~/projects/app1/app1.csproj`
    
`netcoreapp1.1` 프레임워크를 사용하여 현재 디렉터리에 있는 프로젝트를 게시합니다.

`dotnet publish --framework netcoreapp1.1`
    
`netcoreapp1.1` 프레임워크 및 `OS X 10.10`에 대한 런타임을 사용하여 현재 응용 프로그램을 게시합니다. 프로젝트 파일에서 이 RID를 나열해야 합니다.

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

## <a name="see-also"></a>참고 항목

* [대상 프레임워크](../../standard/frameworks.md)
* [RID(런타임 식별자) 카탈로그](../rid-catalog.md)
