---
title: "dotnet msbuild 명령 - .NET Core CLI"
description: "dotnet msbuild 명령은 MSBuild 명령줄에 대한 액세스 권한을 제공합니다."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: 96e4eac528abad2b336a979a98c9be2bee5d17ee
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-msbuild"></a>dotnet msbuild

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>이름

`dotnet msbuild` - 프로젝트 및 모든 종속성을 빌드합니다.

## <a name="synopsis"></a>개요

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a>설명

`dotnet msbuild` 명령을 사용하면 모든 기능을 갖춘 MSBuild에 액세스할 수 있습니다.

이 명령에는 기존 MSBuild 명령줄 클라이언트와 정확히 동일한 기능이 있습니다. 옵션은 모두 동일합니다. [MSBuild 명령줄 참조](/visualstudio/msbuild/msbuild-command-line-reference)를 사용하여 사용 가능한 옵션에 대한 정보를 얻을 수 있습니다. 

## <a name="examples"></a>예제

프로젝트 및 해당 종속성을 빌드합니다.

`dotnet msbuild`

릴리스 구성을 사용하여 프로젝트 및 해당 종속성을 빌드합니다.

`dotnet msbuild /p:Configuration=Release`

게시 대상을 실행하고 `osx.10.11-x64` RID에 대해 게시합니다.

`dotnet msbuild /t:Publish /p:RuntimeIdentifiers=osx.10.11-x64`

SDK를 통해 포함된 모든 대상이 있는 전체 프로젝트를 확인합니다.

`dotnet msbuild /pp`
