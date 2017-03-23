---
title: "dotnet-list reference 명령 | Microsoft 문서"
description: "dotnet-list reference 명령은 프로젝트 간 참조를 나열하는 편리한 옵션을 제공합니다."
keywords: "dotnet-list, CLI, CLI 명령, .NET Core"
author: spboyer
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8f954a0c-03f8-4fbc-a529-b313ab12c623
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: e95aa43bfed78d72ef1ea5f3883ae64e06ffaa99
ms.lasthandoff: 03/07/2017

---
# <a name="dotnet-list-reference"></a>dotnet-list reference

## <a name="name"></a>이름

`dotnet-list reference` - 프로젝트 간 참조를 나열합니다.

## <a name="synopsis"></a>개요

```
dotnet list [project] reference
dotnet list reference [-h|--help]
```

## <a name="description"></a>설명

`dotnet list reference` 명령은 지정한 프로젝트에 대해 프로젝트 참조를 나열하는 편리한 옵션을 제공합니다.

## <a name="arguments"></a>인수

`project`

참조를 나열할 프로젝트 파일입니다. 지정하지 않으면 이 명령은 현재 디렉터리에서 솔루션 파일을 하나 검색합니다.

## <a name="options"></a>옵션

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.

## <a name="examples"></a>예제

지정된 프로젝트에 대한 프로젝트 참조를 나열합니다.

`dotnet list app/app.csproj reference`

현재 디렉터리에 있는 프로젝트에 대한 프로젝트 참조를 나열합니다.

`dotnet list reference`

