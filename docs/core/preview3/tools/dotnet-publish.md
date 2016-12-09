---
title: "dotnet-publish 명령 | .NET Core SDK"
description: "dotnet-publish 명령은 .NET Core 프로젝트를 디렉터리에 게시합니다."
keywords: "dotnet-publish, CLI, CLI 명령, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 10/07/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8a7e1c52-5c57-4bf5-abad-727450ebeefd
translationtype: Human Translation
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: e480c32faa22859de74e06f3a199fba1c0720c46

---

#<a name="dotnet-publish"></a>dotnet-publish

## <a name="name"></a>Name

`dotnet-publish` - 응용 프로그램 및 모든 종속성을 폴더로 압축하여 게시할 준비를 합니다.

## <a name="synopsis"></a>개요

`dotnet publish [project] 
    [--help] [--framework]  
    [--runtime] [--output]  
    [--version-suffix] [--configuration]`

## <a name="description"></a>설명

`dotnet publish`는 응용 프로그램을 컴파일하고 프로젝트 파일에 지정된 종속성을 읽은 다음 결과 파일 집합을 디렉터리에 게시합니다. 

이식 가능한 앱의 유형에 따라 결과 디렉터리에 다음 항목이 포함됩니다.

1. *프레임워크 종속 배포* - 응용 프로그램의 IL(중간 언어) 코드 및 응용 프로그램의 모든 관리 종속성입니다.
2. *자체 포함 배포* - 위와 같으며 대상 플랫폼에 대한 전체 런타임을 포함합니다.

자세한 내용은 [.NET Core 응용 프로그램 배포](../deploying/index.md) 항목을 참조하세요.

## <a name="options"></a>옵션

`[project]` 

게시할 프로젝트이며, `[project]`를 지정하지 않을 경우 현재 디렉터리로 기본 설정됩니다. 

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.  

`-f|--framework <FRAMEWORK>`

지정된 FID(프레임워크 식별자)에 대한 응용 프로그램을 게시합니다. 

`-r|--runtime <RUNTIME_IDENTIFIER>`

지정된 런타임에 대한 응용 프로그램을 게시합니다. 사용할 수 있는 RID(런타임 식별자) 목록은 [RID 카탈로그](../../rid-catalog.md)를 참조하세요.

`-o|--output <OUTPUT_PATH>`

디렉터리를 배치할 경로를 지정합니다. 지정하지 않으면 이식 가능한 응용 프로그램의 경우 *_./bin/[configuration]/[framework]/_*로, 자체 포함 배포의 경우 *_./bin/[configuration]/[framework]/[runtime]_*으로 기본 설정됩니다.

`--version-suffix [VERSION_SUFFIX]`

프로젝트 파일의 버전 필드에서 `*`를 대체할 항목을 정의합니다.

`-c|--configuration [Debug|Release]`

게시할 때 사용할 구성입니다. 기본값은 `Debug`입니다.

## <a name="examples"></a>예제

응용 프로그램을 게시합니다.

`dotnet publish`

지정된 프로젝트 파일을 사용하여 응용 프로그램을 게시합니다.

`dotnet publish ~/projects/app1/app1.csproj`
    
`netcoreapp1.0` 프레임워크를 사용하여 현재 응용 프로그램을 게시합니다.

`dotnet publish --framework netcoreapp1.0`
    
`netcoreapp1.0` 프레임워크 및 `OS X 10.10`에 대한 런타임을 사용하여 현재 응용 프로그램을 게시합니다. 이 RID는 프로젝트 파일에 있어야 합니다.

`dotnet publish --framework netcoreapp1.0 --runtime osx.10.11-x64`

## <a name="see-also"></a>참고 항목
* [프레임워크](../../../standard/frameworks.md)
* [RID(런타임 식별자) 카탈로그](../../rid-catalog.md)



<!--HONumber=Nov16_HO3-->


