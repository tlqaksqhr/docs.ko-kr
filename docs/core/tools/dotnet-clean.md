---
title: "dotnet-clean 명령 | Microsoft 문서"
description: "dotnet-clean 명령은 현재 디렉터리를 정리합니다."
keywords: "dotnet-clean, CLI, CLI 명령, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: eff65fa1-bab4-4421-8260-d0a284b690b2
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 3c00f4616932318b5dc5d77cbdf6c645696a4226
ms.lasthandoff: 03/07/2017

---
#<a name="dotnet-clean"></a>dotnet-clean

## <a name="name"></a>이름

`dotnet-clean` - 프로젝트의 출력을 정리합니다. 

## <a name="synopsis"></a>개요

```
dotnet clean [project] [-o|--output] [-f|--framework] [-c|--configuration] [-v|--verbosity]
dotnet clean [--help] 
```

## <a name="description"></a>설명

`dotnet clean` 명령은 이전 빌드의 출력을 정리합니다. 이 명령은 MSBuild 대상으로 구현되므로 프로젝트가 평가됩니다. 빌드 중 생성된 출력만 정리됩니다. 중간(`obj`) 및 최종 출력(`bin`) 폴더가 모두 정리됩니다. 

## <a name="options"></a>옵션

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.  

`-o|--output <OUTPUT_DIRECTORY>`

빌드된 이진 파일이 배치된 디렉터리입니다. 이 옵션을 지정하는 경우 `--framework`도 정의해야 합니다. 빌드 시간 동안 이 속성을 지정하지 않은 경우 정리를 위해 이 속성을 지정할 필요가 없습니다.

`-f|--framework <FRAMEWORK>`

빌드 시 지정한 프레임워크입니다. 빌드 시간 동안 이 속성을 지정하지 않은 경우 정리를 위해 이 속성을 지정할 필요가 없습니다. 프레임워크는 [프로젝트](csproj.md) 파일에 정의해야 합니다.

`-c|--configuration [Debug|Release]`

빌드가 실행 중인 구성을 정의합니다.  생략하면 `Debug`로 기본 설정됩니다. 빌드 시간 동안 이 속성을 지정하지 않은 경우 정리를 위해 이 속성을 지정할 필요가 없습니다.

`-v|--verbosity <Quiet|Minimal|Normal|Diag>`

`dotnet clean` 명령의 호출에 대해 사용할 세부 정보 표시 수준을 정의합니다. 세부 정보 표시 수준은 표준 [MSBuild 세부 정보 표시 수준](https://docs.microsoft.com/visualstudio/msbuild/msbuild-command-line-reference)입니다. 

## <a name="examples"></a>예제

프로젝트의 기본 빌드 정리:

`dotnet clean`

릴리스 구성을 사용하여 빌드한 프로젝트 정리:

`dotnet clean --configuration Release`

