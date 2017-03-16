---
title: "global.json 참조 | Microsoft 문서"
description: "global.json 참조"
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 96102f96-d403-4385-8ef6-5d80e406eb0c
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 253b8642ae6fc5308d47552e9addfdbed6813ff1
ms.lasthandoff: 03/07/2017

---

# <a name="globaljson-reference"></a>global.json 참조

global.json 파일을 사용하면 `sdk` 속성을 통해 사용 중인 .NET Core 도구 버전을 선택할 수 있습니다. 

## <a name="sdk"></a>sdk
형식: Object

SDK에 대한 정보를 지정합니다.

### <a name="version"></a>version
형식: String

사용할 SDK의 버전입니다.

예를 들면 다음과 같습니다.

```json
{
    "sdk": {
        "version": "1.0.0-preview2-003121"
    }
}
```
