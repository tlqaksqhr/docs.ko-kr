---
title: "dotnet list reference 명령 - .NET Core CLI"
description: "dotnet list reference 명령은 프로젝트 간 참조를 나열하는 편리한 옵션을 제공합니다."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: b3e903c15a7486faa279d47ad5e2e00c090b19af
ms.contentlocale: ko-kr
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-list-reference"></a>dotnet list reference

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>이름

`dotnet list reference` - 프로젝트 간 참조를 나열합니다.

## <a name="synopsis"></a>개요

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a>설명

`dotnet list reference` 명령은 지정한 프로젝트에 대해 프로젝트 참조를 나열하는 편리한 옵션을 제공합니다.

## <a name="arguments"></a>인수

`PROJECT`

참조를 나열하기 위해 사용할 프로젝트 파일을 지정합니다. 지정하지 않으면 이 명령은 현재 디렉터리에서 프로젝트 파일을 검색합니다.

## <a name="options"></a>옵션

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.

## <a name="examples"></a>예제

지정된 프로젝트에 대한 프로젝트 참조를 나열합니다.

`dotnet list app/app.csproj reference`

현재 디렉터리에 있는 프로젝트에 대한 프로젝트 참조를 나열합니다.

`dotnet list reference`

