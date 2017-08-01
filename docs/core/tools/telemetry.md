---
title: ".NET Core 도구 원격 분석"
description: "분석을 위해 사용 정보를 수집하는 .NET Core 도구 원격 분석 기능을 살펴봅니다."
keywords: .NET, .NET Core
author: richlander
ms.author: mairaw
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 480df976-7568-4df4-9d26-9911357b5a31
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1816b9fbad1f671820c9f970674c8af2147a230e
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---

# <a name="net-core-tools-telemetry"></a>.NET Core 도구 원격 분석

.NET Core 도구에는 사용 정보를 수집하는 [원격 분석 기능](https://github.com/dotnet/cli/pull/2145)이 포함되어 있습니다. .NET 팀이 개선을 위해 도구 사용 방법을 이해하는 것이 중요합니다.

수집된 데이터는 비대칭이며, Microsoft 및 커뮤니티 엔지니어가 [Creative Commons Attribution 라이선스](https://creativecommons.org/licenses/by/4.0/)에 따라 사용할 수 있도록 게시됩니다.

## <a name="scope"></a>범위

`dotnet` 명령은 앱과 .NET Core 도구를 실행하는 데 사용됩니다. `dotnet` 명령 자체는 원격 분석을 수집하지 않습니다. 원격 분석을 수집하는 것은 `dotnet` 명령을 통해 실행되는 .NET Core 도구입니다.

.NET Core 명령(원격 분석이 사용되지 않음):

- `dotnet`
- `dotnet [path-to-app]`

.NET Core 도구 [명령](index.md)(원격 분석이 사용됨):

- `dotnet build`
- `dotnet pack`
- `dotnet restore`
- `dotnet run`

## <a name="behavior"></a>동작

.NET Core 도구 원격 분석 기능은 기본적으로 사용됩니다. 환경 변수 DOTNET_CLI_TELEMETRY_OPTOUT(예: macOS/Linux에서는 `export`, Windows에서는 `set`)을 true(예: "true", 1)로 설정하여 원격 분석 기능을 옵트아웃할 수 있습니다.

## <a name="data-points"></a>데이터 요소

이 기능은 다음 데이터를 수집합니다.

- 사용되는 명령(예: "build", "restore")
- 명령의 ExitCode
- 테스트 프로젝트의 경우 사용되는 Test Runner
- 호출의 타임스탬프
- 사용되는 프레임워크
- 런타임 ID가 "런타임" 노드에 있는지 여부
- 사용되는 CLI 버전

이 기능은 사용자 이름이나 전자 메일 등의 개인 데이터를 수집하지 않습니다. 코드를 검사하지 않으며 이름, 리포지토리, 작성자 등 중요하다고 생각될 수 있는 프로젝트 수준의 데이터(project.json에서 설정한 경우)를 추출하지 않습니다. 도구로 무엇을 빌드하느냐가 아니라 도구를 어떻게 사용하느냐를 알고자 합니다. 중요한 데이터가 수집된다면 그것은 버그입니다. 수정할 수 있도록 [문제를 제출](https://github.com/dotnet/cli/issues)하세요.

## <a name="license"></a>라이선스

.NET Core의 Microsoft 배포는 [MICROSOFT.NET 라이브러리 EULA](https://aka.ms/dotnet-core-eula)로 허가됩니다. 여기에는 원격 분석을 사용하도록 설정하는 다음의 "DATA" 섹션이 포함됩니다.

[.NET NuGet 패키지](https://www.nuget.org/profiles/dotnetframework)도 동일한 라이선스를 사용하지만 원격 분석을 사용하도록 설정하지는 않습니다(위의 [범위](#scope) 참조).

> 2. 데이터. 소프트웨어에서 사용자 및 사용자의 소프트웨어 사용에 대한 정보를 수집하고 이 정보를 Microsoft에 보낼 수 있습니다. Microsoft에서는 제품 및 서비스 향상을 위해 이 정보를 사용할 수 있습니다. 데이터 수집 및 사용에 대한 자세한 내용은 도움말 문서 및 개인정보처리방침(http://go.microsoft.com/fwlink/?LinkId=528096)을 참조하세요. 소프트웨어를 사용하려면 이러한 사례에 동의해야 합니다.

## <a name="disclosure"></a>공개

사용자가 명령 중 하나를 처음 실행하면(예: `dotnet restore`) .NET Core 도구에 다음 텍스트가 표시됩니다. 이 "첫 실행" 경험이 Microsoft가 사용자에게 데이터 수집에 대해 알리는 방법입니다. 이와 동일한 경험이 NuGet 캐시를 .NET Core SDK의 라이브러리로 채움으로써, NuGet.org(또는 다른 NuGet 피드)에 그러한 라이브러리를 요청하지 않도록 해줍니다.

```console
Welcome to .NET Core!
---------------------
Learn more about .NET Core @ https://aka.ms/dotnet-docs. Use dotnet --help to see available commands or go to https://aka.ms/dotnet-cli-docs.

Telemetry
--------------
The .NET Core tools collect usage data in order to improve your experience.
The data is anonymous and does not include command-line arguments. The data is collected by Microsoft and shared with the community.
You can opt out of telemetry by setting a DOTNET_CLI_TELEMETRY_OPTOUT environment variable to 1 using your favorite shell.
You can read more about .NET Core tools telemetry @ https://aka.ms/dotnet-cli-telemetry.

Configuring...
-------------------
A command is running to initially populate your local package cache, to improve restore speed and enable offline access. This command will take up to a minute to complete and will only happen once.
```

