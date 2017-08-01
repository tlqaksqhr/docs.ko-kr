---
title: "dotnet-remove package 명령 - .NET Core CLI"
description: "dotnet-remove package 명령은 프로젝트에 대한 NuGet 패키지 참조를 제거하는 편리한 옵션을 제공합니다."
keywords: "dotnet-remove, CLI, CLI 명령, .NET Core"
author: spboyer
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 2fcc8d37-16b3-4581-8038-832160e72d36
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a3fef846d5850e2c2a158ccd1f30a84e8f23f793
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-remove-package"></a>dotnet-remove package

## <a name="name"></a>이름

`dotnet-remove package` - 프로젝트 파일에서 패키지 참조를 제거합니다.

## <a name="synopsis"></a>개요

`dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]`

## <a name="description"></a>설명

`dotnet remove package` 명령은 프로젝트에서 NuGet 패키지 참조를 제거하는 편리한 옵션을 제공합니다.

## <a name="arguments"></a>인수

`PROJECT`

프로젝트 파일을 지정합니다. 지정하지 않으면 이 명령은 현재 디렉터리에서 솔루션 파일을 하나 검색합니다.

`PACKAGE_NAME`

제거할 패키지 참조입니다.

## <a name="options"></a>옵션

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.

## <a name="examples"></a>예제

현재 디렉터리의 프로젝트에서 `Newtonsoft.Json` NuGet 패키지를 제거합니다.

`dotnet remove package Newtonsoft.Json`

