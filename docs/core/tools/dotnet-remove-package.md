---
title: dotnet remove package 명령 - .NET Core CLI
description: dotnet remove package 명령은 프로젝트에 대한 NuGet 패키지 참조를 제거하는 편리한 옵션을 제공합니다.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: ed6086bfdfadaa06494c857fc74687f1273af971
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696860"
---
# <a name="dotnet-remove-package"></a>dotnet remove package

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet remove package` - 프로젝트 파일에서 패키지 참조를 제거합니다.

## <a name="synopsis"></a>개요

`dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]`

## <a name="description"></a>설명

`dotnet remove package` 명령은 프로젝트에서 NuGet 패키지 참조를 제거하는 편리한 옵션을 제공합니다.

## <a name="arguments"></a>인수

`PROJECT`

프로젝트 파일을 지정합니다. 지정하지 않으면 이 명령은 현재 디렉터리에서 검색합니다.

`PACKAGE_NAME`

제거할 패키지 참조입니다.

## <a name="options"></a>옵션

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.

## <a name="examples"></a>예제

현재 디렉터리의 프로젝트에서 `Newtonsoft.Json` NuGet 패키지를 제거합니다.

`dotnet remove package Newtonsoft.Json`