---
title: dotnet sln 명령 - .NET Core CLI
description: dotnet-sln 명령은 솔루션 파일의 프로젝트를 추가, 제거 및 나열하는 간편한 옵션을 제공합니다.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: dd77281b55b3e7fc7c293e402d11de016ef73cf8
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696714"
---
# <a name="dotnet-sln"></a>dotnet sln

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet sln` - .NET Core 솔루션 파일을 수정합니다.

## <a name="synopsis"></a>개요

```
dotnet sln [<SOLUTION_NAME>] add <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] add <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] remove <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] remove <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a>설명

`dotnet sln` 명령은 솔루션 파일의 프로젝트를 추가, 제거 및 나열하는 간편한 옵션을 제공합니다.

## <a name="commands"></a>명령

`add <PROJECT> ...`

`add <GLOBBING_PATTERN>`

솔루션 파일에 하나 이상의 프로젝트를 추가합니다. Unix/Linux 기반 터미널에서는 [와일드카드 사용 패턴](https://en.wikipedia.org/wiki/Glob_(programming))이 지원됩니다.

`remove <PROJECT> ...`

`remove <GLOBBING_PATTERN>`

솔루션 파일에서 하나 이상의 프로젝트를 제거합니다. Unix/Linux 기반 터미널에서는 [와일드카드 사용 패턴](https://en.wikipedia.org/wiki/Glob_(programming))이 지원됩니다.

`list`

솔루션 파일의 모든 프로젝트를 나열합니다.

## <a name="arguments"></a>인수

`SOLUTION_NAME`

사용할 솔루션 파일입니다. 지정하지 않으면 이 명령은 현재 디렉터리에서 검색합니다. 디렉터리에 여러 솔루션 파일이 있으면 하나를 지정해야 합니다.

## <a name="options"></a>옵션

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.

## <a name="examples"></a>예제

솔루션에 C# 프로젝트를 추가합니다.

`dotnet sln todo.sln add todo-app/todo-app.csproj`

솔루션에서 C# 프로젝트를 제거합니다.

`dotnet sln todo.sln remove todo-app/todo-app.csproj`

솔루션에 여러 C# 프로젝트를 추가합니다.

`dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj`

솔루션에서 여러 C# 프로젝트를 제거합니다.

`dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj`

와일드카드 사용 패턴을 사용하여 솔루션에 여러 C# 프로젝트를 추가합니다.

`dotnet sln todo.sln add **/*.csproj`

와일드카드 사용 패턴을 사용하여 솔루션에서 여러 C# 프로젝트를 제거합니다.

`dotnet sln todo.sln remove **/*.csproj`
