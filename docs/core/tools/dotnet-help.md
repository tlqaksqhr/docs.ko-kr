---
title: "dotnet help 명령 - .NET Core CLI"
description: "dotnet help 명령은 지정된 명령에 대한 자세한 온라인 설명서를 표시합니다."
author: mairaw
ms.author: mairaw
ms.date: 08/17/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: ca7c88675d54d99fdb3526244daaeffe32f32d45
ms.openlocfilehash: 0d43db0bb0a62bb598f7db50c3b8e37936451550
ms.contentlocale: ko-kr
ms.lasthandoff: 08/17/2017

---
# <a name="dotnet-help-reference"></a>dotnet help reference

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a>이름

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

