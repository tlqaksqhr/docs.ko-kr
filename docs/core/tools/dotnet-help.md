---
title: dotnet help 명령 - .NET Core CLI
description: dotnet help 명령은 지정된 명령에 대한 자세한 온라인 설명서를 표시합니다.
author: mairaw
ms.author: mairaw
ms.date: 05/25/2018
ms.openlocfilehash: ed152717e32ffb294f5d5bd8e5eb74d55e33e506
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696600"
---
# <a name="dotnet-help-reference"></a>dotnet help reference

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a>name

`dotnet help` - 지정된 명령에 대한 자세한 온라인 설명서를 표시합니다.

## <a name="synopsis"></a>개요

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a>설명

`dotnet help` 명령은 docs.microsoft.com에서 지정된 명령에 대한 자세한 정보를 제공하는 참조 페이지를 엽니다.

## <a name="arguments"></a>인수

`COMMAND_NAME`

.NET Core CLI 명령의 이름입니다. 유효한 CLI 명령 목록은 [CLI 명령](index.md#cli-commands)을 참조하세요.

## <a name="options"></a>옵션

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.

## <a name="examples"></a>예제

[dotnet new](dotnet-new.md) 명령에 대한 설명서 페이지를 엽니다.

`dotnet help new`
