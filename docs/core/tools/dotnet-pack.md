---
title: "dotnet-pack 명령 - .NET Core CLI | Microsoft Docs"
description: "dotnet-pack 명령은 .NET Core 프로젝트에 대한 NuGet 패키지를 만듭니다."
keywords: "dotnet-pack, CLI, CLI 명령, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8dbbb3f7-b817-4161-a6c8-a3489d05e051
ms.translationtype: Human Translation
ms.sourcegitcommit: 14c2e01ab0c30c9f1cbfdcc53ea85fe51a4d8c2e
ms.openlocfilehash: 5a2ea69825fa336b1d8ce2283e214d02c16347e3
ms.contentlocale: ko-kr
ms.lasthandoff: 05/01/2017

---

# <a name="dotnet-pack"></a>dotnet-pack

## <a name="name"></a>이름

`dotnet-pack` - 코드를 NuGet 패키지로 압축합니다.

## <a name="synopsis"></a>개요

`dotnet pack [<PROJECT>] [-o|--output] [--no-build] [--include-symbols] [--include-source] [-c|--configuration] [--version-suffix <VERSION_SUFFIX>] [-s|--serviceable] [-v|--verbosity] [-h|--help]`

## <a name="description"></a>설명

`dotnet pack` 명령은 프로젝트를 빌드하고 NuGet 패키지를 만듭니다. 이 명령의 결과가 NuGet 패키지입니다. `--include-symbols` 옵션이 있는 경우 디버그 기호를 포함하는 다른 패키지가 생성됩니다. 

압축된 프로젝트의 NuGet 종속성은 *.nuspec* 파일에 추가되므로 패키지를 설치할 때 적절히 확인됩니다. 프로젝트 간 참조는 프로젝트 내에서 패키지되지 않습니다. 현재 프로젝트 간 종속성이 있는 경우 프로젝트당 패키지가 있어야 합니다.

`dotnet pack`은 기본적으로 프로젝트를 먼저 빌드합니다. 이렇게 하지 않으려면 `--no-build` 옵션을 전달합니다. 이 옵션은 코드가 이미 빌드된 CI(연속 통합) 빌드 시나리오에서 유용합니다.

압축 프로세스에 대한 `dotnet pack` 명령에 MSBuild 속성을 제공할 수 있습니다. 자세한 내용은 [NuGet 메타데이터 속성](csproj.md#nuget-metadata-properties) 및 [MSBuild 명령줄 참조](/visualstudio/msbuild/msbuild-command-line-reference)를 참조하세요.

## <a name="arguments"></a>인수

`PROJECT` 
    
압축할 프로젝트입니다. [csproj file](csproj.md) 파일 또는 디렉터리에 대한 경로입니다. 생략하면 현재 디렉터리로 기본 설정됩니다. 

## <a name="options"></a>옵션

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.  

`-o|--output <OUTPUT_DIRECTORY>`

지정된 디렉터리에 빌드된 패키지를 배치합니다. 

`--no-build`

압축하기 전에 프로젝트를 빌드하지 않습니다. 

`--include-symbols`

기호 `nupkg`를 생성합니다. 

`--include-source`

NuGet 패키지에 소스 파일을 포함합니다. 소스 파일은 `nupkg`의 `src` 폴더에 있습니다. 

`-c|--configuration <CONFIGURATION>`

프로젝트를 빌드할 때 사용할 구성입니다. 지정하지 않으면 구성 기본값은 `Debug`입니다.

`--version-suffix <VERSION_SUFFIX>`

프로젝트에서 `$(VersionSuffix)` MSBuild 속성에 대한 값을 정의합니다.

`-s|--serviceable`

패키지에 서비스 가능 플래그를 설정합니다. 자세한 내용은 [.NET 블로그: .NET 4.5.1에서 .NET NuGet 라이브러리에 대한 Microsoft 보안 업데이트를 지원함](https://aka.ms/nupkgservicing)을 참조하세요.

`--verbosity <LEVEL>`

명령의 세부 정보 표시 수준을 설정합니다. 허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.

## <a name="examples"></a>예제

현재 디렉터리에 있는 프로젝트를 압축합니다.

`dotnet pack`

`app1` 프로젝트를 압축합니다.

`dotnet pack ~/projects/app1/project.csproj`
    
현재 디렉터리에 있는 프로젝트를 압축하고 결과 패키지를 `nupkgs` 폴더에 배치합니다.

`dotnet pack --output nupkgs`

현재 디렉터리에 있는 프로젝트를 `nupkgs` 폴더로 압축하고 빌드 단계를 건너뜁니다.

`dotnet pack --no-build --output nupkgs`

*.csproj* 파일에서 프로젝트의 버전 접미사를 `<VersionSuffix>$(VersionSuffix)</VersionSuffix>`로 구성한 상태로 현재 프로젝트를 압축하고 결과 패키지 버전을 지정된 접미사로 업데이트합니다.

`dotnet pack --version-suffix "ci-1234"`

`PackageVersion` MSBuild 속성을 사용하여 패키지 버전을 `2.1.0`으로 설정합니다.

`dotnet pack /p:PackageVersion=2.1.0`

