---
title: dotnet build-server 명령 - .NET Core CLI
description: dotnet build-server 명령은 빌드에서 시작된 서버와 상호 작용합니다.
author: mairaw
ms.author: mairaw
ms.date: 07/02/2018
ms.openlocfilehash: 1c59c85f246b79c7e2552f704db5b4f076f9b502
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37404335"
---
# <a name="dotnet-build-server"></a>dotnet build-server

[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a>name

`dotnet build-server` - 빌드에서 시작된 서버와 상호 작용합니다.

## <a name="synopsis"></a>개요

```
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a>명령

`shutdown`

Dotnet에서 시작된 빌드 서버를 종료합니다. 기본적으로 모든 서버가 종료됩니다.

## <a name="options"></a>옵션

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.

`--msbuild`

MSBuild 빌드 서버를 종료합니다.

`--razor`

Razor 빌드 서버를 종료합니다.

`--vbcscompiler`

VB/C# 컴파일러 빌드 서버를 종료합니다.
