---
title: "dotnet-test 명령 - .NET Core CLI | Microsoft Docs"
description: "`dotnet test` 명령은 지정된 프로젝트에서 단위 테스트를 실행하는 데 사용됩니다."
keywords: "dotnet-test, CLI, CLI 명령, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/25/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 4bf0aef4-148a-41c6-bb95-0a9e1af8762e
ms.translationtype: Human Translation
ms.sourcegitcommit: ae036cfcad341ffc859336a7ab2a49feec145715
ms.openlocfilehash: 734cf337fdd0d33f6c2b6d929b795b2307135550
ms.contentlocale: ko-kr
ms.lasthandoff: 05/18/2017

---

#<a name="dotnet-test"></a>dotnet-test

## <a name="name"></a>이름

`dotnet-test` - 단위 테스트를 실행하는 데 사용하는 .NET 테스트 드라이버입니다.

## <a name="synopsis"></a>개요

`dotnet test [<PROJECT>] [-s|--settings] [-t|--list-tests] [--filter] [-a|--test-adapter-path] [-l|--logger] [-c|--configuration] [-f|--framework] [-o|--output] [-d|--diag] [--no-build] [-v|--verbosity] [-h|--help]`

## <a name="description"></a>설명

`dotnet test` 명령은 지정된 프로젝트에서 단위 테스트를 실행하는 데 사용됩니다. 단위 테스트는 단위 테스트 프레임워크(예: MSTest, NUnit 또는 xUnit) 및 단위 테스트 프레임워크에 대한 dotnet Test Runner에 종속되어 있는 콘솔 응용 프로그램 프로젝트입니다. 이러한 프로젝트는 NuGet 패키지로 패키지되고 프로젝트에 대한 일반 종속성으로 복원됩니다.

테스트 프로젝트에서는 Test Runner도 지정해야 합니다. 다음의 예제 프로젝트 파일에서 볼 수 있듯이 일반적인 `<PackageReference>` 요소를 사용하여 지정합니다.

[!code-xml[XUnit 기본 템플릿](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="options"></a>옵션

`PROJECT`
    
테스트 프로젝트에 대한 경로를 지정합니다. 생략하면 현재 디렉터리로 기본 설정됩니다.

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.

`-s|--settings <SETTINGS_FILE>`

테스트를 실행할 때 사용할 설정입니다. 

`-t|--list-tests`

현재 프로젝트에서 검색된 테스트를 모두 나열합니다. 

`--filter <EXPRESSION>`

지정된 식을 사용하여 현재 프로젝트의 테스트를 필터링합니다. 자세한 내용은 [필터 옵션 세부 정보](#filter-option-details) 섹션을 참조하세요. 선택적 단위 테스트 필터링을 사용하는 방법에 대한 추가 정보 및 예제는 [선택적 단위 테스트 실행](../testing/selective-unit-tests.md)을 참조하세요.

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

테스트 실행에 지정된 경로에서 사용자 지정 테스트 어댑터를 사용합니다. 

`-l|--logger <LoggerUri/FriendlyName>`

테스트 결과에 대해 로거를 지정합니다. 

`-c|--configuration <CONFIGURATION>`

빌드할 구성입니다. 기본값은 `Debug`이지만 프로젝트의 구성으로 이 기본 SDK 설정이 재정의될 수 있습니다.

`-f|--framework <FRAMEWORK>`

특정 [프레임워크](../../standard/frameworks.md)에 대한 테스트 이진 파일을 찾습니다.

`-o|--output <OUTPUT_DIRECTORY>`

실행할 이진 파일을 찾을 디렉터리입니다.

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

테스트 플랫폼에 대한 진단 모드를 사용하도록 설정하고 지정된 파일에 진단 메시지를 기록합니다. 

`--no-build` 

텍스트 프로젝트를 실행하기 전에 빌드하지 않습니다.

`-v|--verbosity <LEVEL>`

명령의 세부 정보 표시 수준을 설정합니다. 허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.

## <a name="examples"></a>예제

현재 디렉터리에 있는 프로젝트에서 테스트를 실행합니다.

`dotnet test` 

`test1` 프로젝트에서 테스트를 실행합니다.

`dotnet test ~/projects/test1/test1.csproj`

## <a name="filter-option-details"></a>필터 옵션 세부 정보

`--filter <EXPRESSION>`

`<Expression>`에 `<property><operator><value>[|&<Expression>]` 형식이 있습니다.

`<property>`은(는) `Test Case`의 특성입니다. 다음은 인기 있는 단위 테스트 프레임 워크에서 지원되는 속성입니다.

| 테스트 프레임워크 | 지원되는 속성                                                                                      |
| :------------: | --------------------------------------------------------------------------------------------------------- |
| MSTest         | <ul><li>FullyQualifiedName</li><li>이름</li><li>ClassName</li><li>우선 순위</li><li>TestCategory</li></ul> |
| Xunit          | <ul><li>FullyQualifiedName</li><li>DisplayName</li><li>특성</li></ul>                                   |

`<operator>`은(는) 속성과 값 사이의 관계를 설명합니다.

| 연산자 | 함수        |
| :------: | --------------- |
| `=`      | 정확하게 일치     |
| `!=`     | 정확하게 일치하지 않음 |
| `~`      | 포함        |

`<value>`는 문자열입니다. 모든 조회는 대/소문자를 구분합니다.

`<operator>`이(가) 없는 식은 `FullyQualifiedName` 속성의 `contains`(으)로 자동으로 간주됩니다(예를 들어 `dotnet test --filter xyz`과(와) `dotnet test --filter FullyQualifiedName~xyz`이(가) 동일).

식은 조건부 연산자와 조인할 수 있습니다.

| 연산자 | 함수 |
| :------: | :------: |
| `|`      | 또는       |
| `&`      | AND      |

조건부 연산자를 사용 하는 경우 식을 괄호로 묶을 수 있습니다 (예를 들어 `(Name~TestMethod1) | (Name~TestMethod2)`).

선택적 단위 테스트 필터링을 사용하는 방법에 대한 추가 정보 및 예제는 [선택적 단위 테스트 실행](../testing/selective-unit-tests.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[프레임워크 및 대상](../../standard/frameworks.md)   
[.NET Core RID(런타임 식별자) 카탈로그](../rid-catalog.md)

