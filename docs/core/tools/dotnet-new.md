---
title: "dotnet-new 명령 - .NET Core CLI | Microsoft Docs"
description: "dotnet-new 명령은 현재 디렉터리에 새 .NET Core 프로젝트를 만듭니다."
keywords: "dotnet-new, CLI, CLI 명령, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: fcc3ed2e-9265-4d50-b59e-dc2e5c190b34
translationtype: Human Translation
ms.sourcegitcommit: dff752a9d31ec92b113dae9eed20cd72faf57c84
ms.openlocfilehash: 14e6b4a2ffe5145a6d5d856c2149569b9ae39ff9
ms.lasthandoff: 03/22/2017

---

# <a name="dotnet-new"></a>dotnet-new

## <a name="name"></a>이름

`dotnet-new` - 지정된 템플릿을 기반으로 새 프로젝트, 구성 파일 또는 솔루션을 만듭니다.

## <a name="synopsis"></a>개요

```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

## <a name="description"></a>설명

`dotnet new` 명령은 올바른 .NET Core 프로젝트를 초기화하는 편리한 방법을 제공합니다. 

이 명령은 [템플릿 엔진](https://github.com/dotnet/templating)을 호출하여 지정된 템플릿 및 옵션을 기반으로 디스크에 아티팩트를 만듭니다.

## <a name="arguments"></a>인수

`TEMPLATE`

명령이 호출될 때 인스턴스화할 템플릿입니다. 각 템플릿에는 전달할 수 있는 특정 옵션이 있을 수 있습니다. 자세한 내용은 [템플릿 옵션](#template-options)을 참조하세요.

명령에는 템플릿의 기본 목록이 포함되어 있습니다. `dotnet new -all`을 사용하여 사용 가능한 템플릿 목록을 가져옵니다. 다음 표에는 SDK와 함께 사전 설치된 템플릿이 나와 있습니다. 템플릿의 기본 언어는 대괄호 안에 표시됩니다.

|템플릿 설명  | 템플릿 이름  | 언어 |
|----------------------|----------------|-----------|
| 콘솔 응용 프로그램  | 콘솔        | [C#], F#  |
| 클래스 라이브러리        | classlib       | [C#], F#  |
| 단위 테스트 프로젝트    | mstest         | [C#], F#  |
| xUnit 테스트 프로젝트   | xunit          | [C#], F#  |
| ASP.NET Core 비어 있음   | 웹            | [C#]      |
| ASP.NET Core 웹앱 | mvc            | [C#], F#  |
| ASP.NET Core 웹 API | webapi         | [C#]      |
| Nuget 구성         | nugetconfig    |           |
| 웹 구성           | webconfig      |           |
| 솔루션 파일        | sln            |           |

## <a name="options"></a>옵션

`-h|--help`

명령에 대한 도움말을 출력합니다. `dotnet new` 명령 자체 또는 `dotnet new mvc --help` 같은 템플릿에 대해 호출될 수 있습니다.

`-l|--list`

지정된 이름을 포함하는 템플릿을 나열합니다. `dotnet new` 명령에 대해 호출되는 경우 지정된 디렉터리에서 사용 가능한 템플릿을 나열합니다. 예를 들어 디렉터리에 이미 프로젝트가 포함되어 있는 경우 일부 프로젝트 템플릿을 나열하지 않습니다.

`-lang|--language {C#|F#}`

만들 템플릿의 언어입니다. 허용되는 언어는 템플릿에 따라 다릅니다([인수](#arguments) 섹션에서 기본값 참조). 일부 템플릿의 경우 유효하지 않습니다.

`-n|--name <OUTPUT_NAME>`

생성된 출력에 대한 이름입니다. 이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.

`-o|--output <OUTPUT_DIRECTORY>`

생성된 출력을 배치할 위치입니다. 기본값은 현재 디렉터리입니다.

`-all|--show-all`

`dotnet new` 명령의 컨텍스트에서만 실행되는 경우 특정 유형의 프로젝트에 대한 모든 템플릿을 표시합니다. `dotnet new web -all`처럼 특정 템플릿의 컨텍스트에서 실행되는 경우 `-all`은 강제 생성 플래그로 해석됩니다. 출력 디렉터리에 이미 프로젝트가 포함되어 있는 경우 필수입니다.

## <a name="template-options"></a>템플릿 옵션

각 프로젝트 템플릿에는 사용할 수 있는 추가 옵션이 있을 수 있습니다. 코어 템플릿에는 다음 옵션이 있습니다.

**console, xunit, mstest, web, webapi**

`-f|--framework` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다. 값: `netcoreapp1.0` 또는 `netcoreapp1.1`(기본값: `netcoreapp1.0`)

**mvc**

`-f|--framework` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다. 값: `netcoreapp1.0` 또는 `netcoreapp1.1`(`Default: netcoreapp1.0`)

`-au|--authentication` - 사용할 인증 형식입니다. 값: `None` 또는 `Individual`(기본값: `None`)

`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용할지 여부를 지정합니다. 값: `true` 또는 `false`(기본값: `false`)

**classlib**

`-f|--framework` - 대상으로 할 [프레임워크](../../standard/frameworks.md)를 지정합니다. 값: `netcoreapp1.0`, `netcoreapp1.1` 또는 `netstandard1.0` ~ `netstandard1.6`(기본값: `netstandard1.4`)

## <a name="examples"></a>예제

현재 디렉터리에 F# 콘솔 응용 프로그램 프로젝트를 만듭니다.

`dotnet new console -lang f#` 
   
.NET Core 1.0을 대상으로 하는 인증 없이 현재 디렉터리에 새 ASP.NET Core C# MVC 응용 프로그램 프로젝트를 만듭니다.  

`dotnet new mvc -au None -f netcoreapp1.0`
 
.NET Core 1.1을 대상으로 새 xUnit 응용 프로그램을 만듭니다.

`dotnet new xunit --Framework netcoreapp1.1`

MVC에 대해 사용할 수 있는 모든 템플릿을 나열합니다.

`dotnet new mvc -l`

