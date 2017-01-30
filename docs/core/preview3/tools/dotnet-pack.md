---
title: "dotnet-pack 명령 | .NET Core SDK"
description: "dotnet-pack 명령은 .NET Core 프로젝트에 대한 NuGet 패키지를 만듭니다."
keywords: "dotnet-pack, CLI, CLI 명령, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 10/12/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8b4b8cef-f56c-4a10-aa01-fde8bfaae53e
translationtype: Human Translation
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: 5aca8db50bf80606ff94562a6014c396b0ef770e

---

#<a name="dotnet-pack"></a>dotnet-pack

## <a name="name"></a>Name

`dotnet-pack` - 코드를 NuGet 패키지로 압축합니다.

## <a name="synopsis"></a>개요

`dotnet pack [--help] [--output]  
    [--no-build] [--include-symbols]
    [--include-source] [--servicable]
    [--configuration]  [--version-suffix]
    [project]`  

## <a name="description"></a>설명

`dotnet pack` 명령은 프로젝트를 빌드하고 NuGet 패키지를 만듭니다. 이 명령의 결과가 nuget 패키지가 발생합니다. `--include-symbols` 옵션이 있는 경우 디버그 기호를 포함하는 다른 패키지가 생성됩니다. 

압축할 프로젝트의 NuGet 종속성은 nuspec 파일에 추가되므로 패키지를 설치할 때 확인할 수 있습니다. 프로젝트 간 참조는 프로젝트 내에서 패키지되지 않습니다. 현재 프로젝트 간 종속성이 있는 경우 프로젝트당 패키지가 있어야 합니다.

`dotnet pack`은 기본적으로 프로젝트를 먼저 빌드합니다. 이렇게 하지 않으려면 `--no-build` 옵션을 전달합니다. 예를 들어 이 옵션은 코드가 이미 빌드된 CI(연속 통합) 빌드 시나리오에서 유용할 수 있습니다. 

## <a name="options"></a>옵션

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.  

`[project]` 
    
압축할 프로젝트입니다. [csproj file](csproj.md) 파일 또는 디렉터리에 대한 경로일 수 있습니다. 생략하면 현재 디렉터리로 기본 설정됩니다. 

`-o|--output <OUTPUT_DIRECTORY>`

지정된 디렉터리에 빌드된 패키지를 배치합니다. 

`--no-build`

압축하기 전에 프로젝트를 빌드하지 않습니다. 

`--include-source`

nuget 패키지에 소스 파일을 포함합니다. 소스 파일은 nupkg의 `src` 폴더에 있습니다. 

`--include-symbols`

기호 nupkg를 생성합니다. 

`-c|--configuration <Debug|Release>`

프로젝트를 빌드할 때 사용할 구성입니다. 지정하지 않으면 `Debug`로 기본 설정됩니다.

`--version-suffix`

`-*` 패키지 버전 접미사의 별표를 지정된 문자열로 업데이트합니다.

## <a name="examples"></a>예제

현재 디렉터리에 있는 프로젝트를 압축합니다.

`dotnet pack`

app1 프로젝트를 압축합니다.

`dotnet pack ~/projects/app1/project.csproj`
    
현재 디렉터리에 있는 프로젝트를 압축하고 결과 패키지를 지정된 폴더에 배치합니다.

`dotnet pack --output nupkgs`

현재 디렉터리에 있는 프로젝트를 지정된 폴더로 압축하고 빌드 단계를 건너뜁니다.

`dotnet pack --no-build --output nupkgs`

현재 프로젝트를 압축하고 결과 패키지 버전을 지정된 접미사로 업데이트합니다. 예를 들어 `1.0.0-*` 버전은 `1.0.0-ci-1234`로 업데이트됩니다.

`dotnet pack --version-suffix "ci-1234"`



<!--HONumber=Nov16_HO3-->


