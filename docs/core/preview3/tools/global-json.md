---
title: "global.json 참조 | Microsoft 문서"
description: "global.json 참조"
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 11/02/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 96102f96-d403-4385-8ef6-5d80e406eb0c
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: b814bfc79c2fcd0fd15b9494c18c6d0443a70fb1

---

# <a name="globaljson-reference-net-core-tools-rc4"></a>global.json 참조(.NET Core 도구 RC4)

> [!WARNING]
> 이 항목은 .NET Core 도구 RC4에 적용됩니다. .NET Core Tools Preview 2 버전의 경우 [global.json 참조](../../tools/global-json.md) 항목을 참조하세요.

global.json 파일은 여전히 .NET Core 명령줄 RC4에 있습니다. 그러나 이 파일은 기본적으로 이전 릴리스에서처럼 솔루션의 메타데이터를 정의하는 것이 아니라 `sdk` 속성을 통해 사용되는 CLI 버전 선택을 허용하기 위해 주로 사용됩니다. 

이 참조에서는 위의 사실을 반영합니다. 

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


<!--HONumber=Feb17_HO2-->


