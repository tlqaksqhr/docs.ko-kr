---
title: "dotnet-msbuild 명령 | Microsoft 문서"
description: "dotnet-msbuild 명령은 MSBuild 명령줄에 대한 액세스 권한을 제공합니다."
keywords: "dotnet-msmsbuild, CLI, CLI 명령, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: ffdc40ba-ef33-463e-aa35-b0af1fe615a2
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: a000e49a8672affe5b3bb9bd8a5f7e8095ab0aa9
ms.lasthandoff: 03/07/2017

---
#<a name="dotnet-msbuild"></a>dotnet-msbuild

## <a name="name"></a>이름

`dotnet-msbuild` - 프로젝트 및 모든 종속성을 빌드합니다.

## <a name="synopsis"></a>개요

```
dotnet msbuild <msbuild_arguments>
dotnet msbuild [-h]
```

## <a name="description"></a>설명

`dotnet msbuild` 명령을 사용하면 모든 기능을 갖춘 MSBuild에 액세스할 수 있습니다. 

이 명령에는 기존 MSBuild 명령줄 클라이언트와 정확히 동일한 기능이 있습니다. 옵션은 모두 동일합니다. [MSBuild 명령줄 참조](https://docs.microsoft.com/visualstudio/msbuild/msbuild-command-line-reference)를 통해 옵션을 익힐 수 있습니다. 

## <a name="examples"></a>예제

프로젝트 및 해당 종속성을 빌드합니다.

`dotnet msbuild`

릴리스 구성을 사용하여 프로젝트 및 해당 종속성을 빌드합니다.

`dotnet msbuild /p:Configuration=Release`

게시 대상을 실행하고 `osx.10.11-x64` RID에 대해 게시합니다.

`dotnet msbuild /t:Publish /p:RuntimeIdentifiers=osx.10.11-x64`
