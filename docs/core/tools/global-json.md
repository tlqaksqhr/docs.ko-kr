---
title: "global.json 참조"
description: ".NET Core 도구 버전 설정을 허용하는 global.json 파일의 스키마를 참조하세요."
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 04/05/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 96102f96-d403-4385-8ef6-5d80e406eb0c
ms.openlocfilehash: ffa97164736fc7f3edc450682d23bdf499b6eb34
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="globaljson-reference"></a>global.json 참조

*global.json* 파일을 사용하면 `sdk` 속성을 통해 사용 중인 .NET Core 도구 버전을 선택할 수 있습니다.

.NET Core CLI 도구는 현재 작업 디렉터리(프로젝트 디렉터리와 다를 수 있음) 또는 해당 부모 디렉터리 중 하나에서 이 파일을 찾습니다.

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
