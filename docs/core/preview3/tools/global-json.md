---
title: "global.json 참고 | .NET Core"
description: "global.json 참조"
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 11/02/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: e1ac9659-425f-4486-a376-c12ca942ead8
translationtype: Human Translation
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: 281f1b717a0e220e533078e973711977617a1401

---

# <a name="globaljson-reference"></a>global.json 참조

global.json 파일은 여전히 .NET Core 명령줄 Preview 3에 있습니다. 그러나 이 파일은 기본적으로 이전 릴리스에서처럼 솔루션의 메타데이터를 정의하는 것이 아니라 `sdk` 속성을 통해 사용되는 CLI 버전 선택을 허용하기 위해 주로 사용됩니다. 

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



<!--HONumber=Nov16_HO3-->


