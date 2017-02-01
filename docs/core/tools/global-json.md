---
title: "global.json 참조 | Microsoft 문서"
description: "global.json 참조"
keywords: .NET, .NET Core
author: aL3891
ms.author: mairaw
ms.date: 11/02/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: e1ac9659-425f-4486-a376-c12ca942ead8
translationtype: Human Translation
ms.sourcegitcommit: 2ad428dcda9ef213a8487c35a48b33929259abba
ms.openlocfilehash: e8c8123f2c46e506990375172d1be642653d4996

---

# <a name="globaljson-reference"></a>global.json 참조

> [!WARNING]
> 이 항목은 .NET Core Tools Preview 2에 적용됩니다. Visual Studio 2017 RC - .NET Core Tools Preview 4 버전의 경우 [global.json 참조(Tooling Preview 4)](../preview3/tools/global-json.md) 항목을 참조하세요.

global.json 파일은 .NET Core 프로젝트에서 솔루션 메타데이터를 정의하는 데 사용됩니다. 이 파일은 [dotnet-restore](dotnet-restore.md) 명령을 호출하여 .NET Core 프로젝트의 종속성을 복원할 때 사용됩니다.
이 참조 항목에는 global.json 파일에서 정의할 수 있는 속성의 목록이 표시됩니다.

## <a name="projects"></a>프로젝트
형식: String[]

빌드 시스템에서 종속성을 확인할 때 프로젝트를 검색할 폴더를 지정합니다. 빌드 시스템은 최상위 수준 자식 폴더만 검색합니다.

예를 들면 다음과 같습니다.

```json
{
    "projects": [ "src", "test" ]
}
```

## <a name="packages"></a>패키지
형식: String

패키지를 저장할 위치입니다.

예를 들면 다음과 같습니다.
```json
{
    "packages": "packages-dir"
}
```

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



<!--HONumber=Jan17_HO3-->


