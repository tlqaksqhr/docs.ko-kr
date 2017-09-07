---
title: "dotnet clean 명령 - .NET Core CLI"
description: "dotnet clean 명령은 현재 디렉터리를 정리합니다."
author: mairaw
ms.author: mairaw
ms.date: 08/13/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: 4836f07ec1a8b59c343b4d0181587e602f61d45e
ms.contentlocale: ko-kr
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-clean"></a>dotnet-clean

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>이름

`dotnet clean` - 프로젝트의 출력을 정리합니다.

## <a name="synopsis"></a>개요

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)
```
dotnet clean [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)
```
dotnet clean [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-v|--verbosity]
dotnet clean [-h|--help]
```
---

## <a name="description"></a>설명

`dotnet clean` 명령은 이전 빌드의 출력을 정리합니다. 이 명령은 [MSBuild 대상](/visualstudio/msbuild/msbuild-targets)으로 구현되므로 명령이 실행될 때 프로젝트가 평가됩니다. 빌드 중 생성된 출력만 정리됩니다. 중간(*obj*) 및 최종 출력(*bin*) 폴더가 모두 정리됩니다.

## <a name="arguments"></a>인수

`PROJECT`

정리할 MSBuild 프로젝트입니다. 프로젝트 파일을 지정하지 않으면 MSBuild는 현재 작업 디렉터리에서 *proj*로 끝나는 파일 확장명이 있는 파일을 검색하고 해당 파일을 사용합니다.

## <a name="options"></a>옵션

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

빌드 구성을 정의합니다. 기본값은 `Debug`입니다. 이 옵션은 빌드 시에 지정한 경우에만 정리 시에도 필요합니다.

`-f|--framework <FRAMEWORK>`

빌드 시 지정한 [프레임워크](../../standard/frameworks.md)입니다. 프레임워크는 [프로젝트 파일](csproj.md)에 정의해야 합니다. 빌드 시에 프레임워크를 지정한 경우 정리할 때도 프레임워크를 지정해야 합니다.

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.

`-o|--output <OUTPUT_DIRECTORY>`

빌드 출력이 배치된 디렉터리입니다. 프로젝트를 빌드할 때 프레임워크를 지정한 경우 `-f|--framework <FRAMEWORK>` 스위치와 출력 디렉터리 스위치를 함께 지정합니다.

`-r|--runtime <RUNTIME_IDENTIFIER>`

지정된 런타임의 출력 폴더를 정리합니다. [자체 포함된 배포](../deploying/index.md#self-contained-deployments-scd)가 만들어진 경우 사용됩니다.

`-v|--verbosity <LEVEL>`

명령의 세부 정보 표시 수준을 설정합니다. 허용되는 수준은 q[uiet], m[inimal], n[ormal], d[etailed] 및 diag[nostic]입니다.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

빌드 구성을 정의합니다. 기본값은 `Debug`입니다. 이 옵션은 빌드 시에 지정한 경우에만 정리 시에도 필요합니다.

`-f|--framework <FRAMEWORK>`

빌드 시 지정한 [프레임워크](../../standard/frameworks.md)입니다. 프레임워크는 [프로젝트 파일](csproj.md)에 정의해야 합니다. 빌드 시에 프레임워크를 지정한 경우 정리할 때도 프레임워크를 지정해야 합니다.

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.

`-o|--output <OUTPUT_DIRECTORY>`

빌드 출력이 배치된 디렉터리입니다. 프로젝트를 빌드할 때 프레임워크를 지정한 경우 `-f|--framework <FRAMEWORK>` 스위치와 출력 디렉터리 스위치를 함께 지정합니다.

`-v|--verbosity <LEVEL>`

명령의 세부 정보 표시 수준을 설정합니다. 허용되는 수준은 q[uiet], m[inimal], n[ormal], d[etailed] 및 diag[nostic]입니다.

---

## <a name="examples"></a>예제

프로젝트의 기본 빌드 정리:

`dotnet clean`

릴리스 구성을 사용하여 빌드한 프로젝트 정리:

`dotnet clean --configuration Release`

