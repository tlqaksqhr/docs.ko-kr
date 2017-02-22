---
title: "dotnet-sln 명령 | Microsoft 문서"
description: "dotnet-sln 명령은 솔루션 파일의 프로젝트를 추가, 제거 및 나열하는 간편한 옵션을 제공합니다."
keywords: "dotnet-run, CLI, CLI 명령, .NET Core"
author: spboyer
ms.author: mairaw
ms.date: 02/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: e5a72d3e-c14b-4b0a-a978-c5e54a0988c6
translationtype: Human Translation
ms.sourcegitcommit: 6c0474e2964043b6c090ecb4e68b46ff42ca670c
ms.openlocfilehash: c5ed2482222b02b8b50599b48a28afa5922e0135

---
# <a name="dotnet-sln"></a>dotnet-sln

[!INCLUDE[preview-warning](../../../includes/warning.md)]

## <a name="name"></a>이름

`dotnet-sln` - .NET Core 솔루션 파일을 수정합니다.

## <a name="synopsis"></a>개요

```
dotnet sln [<SLN_NAME>] add <project> <project>
dotnet sln [<SLN_NAME>] add **/**
dotnet sln [<SLN_NAME>] remove <project> <project>
dotnet sln [<SLN_NAME>] remove **/**
dotnet sln [<SLN_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a>설명

`dotnet sln` 명령은 솔루션 파일의 프로젝트를 추가, 제거 및 나열하는 간편한 옵션을 제공합니다.

## <a name="commands"></a>명령

`add <project>`

`add **/*`

솔루션 파일에 하나 이상의 프로젝트를 추가합니다. Unix/Linux 기반 터미널에서는 GLOB 패턴이 지원됩니다.

`remove <project>`

`remove **/*`

솔루션 파일에서 하나 이상의 프로젝트를 제거합니다. Unix/Linux 기반 터미널에서는 GLOB 패턴이 지원됩니다.

`list`

솔루션 파일의 모든 프로젝트를 나열합니다.

## <a name="arguments"></a>인수

`SLN_NAME`

사용할 솔루션 파일입니다. 지정하지 않으면 이 명령은 현재 디렉터리에서 솔루션 파일을 하나 검색합니다. 디렉터리에 여러 솔루션 파일이 있으면 하나를 지정해야 합니다.

## <a name="options"></a>옵션

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.

## <a name="examples"></a>예제

솔루션에 프로젝트 추가:

`dotnet sln todo.sln add todo-app/todo-app.csproj`

현재 디렉터리의 솔루션에 프로젝트 추가:

`dotnet sln add todo-app.csproj`

솔루션에서 프로젝트 제거:

`dotnet sln todo.sln remove todo-app/todo-app.csproj`

와일드 카드 사용 패턴을 사용하여 솔루션에 여러 프로젝트 추가:

`dotnet sln add **/**/*.fsproj`



<!--HONumber=Feb17_HO2-->


