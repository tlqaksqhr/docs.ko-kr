---
title: "dotnet-new 명령 | Microsoft 문서"
description: "dotnet-new 명령은 현재 디렉터리에 새 .NET Core 프로젝트를 만듭니다."
keywords: "dotnet-new, CLI, CLI 명령, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 02/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: fcc3ed2e-9265-4d50-b59e-dc2e5c190b34
translationtype: Human Translation
ms.sourcegitcommit: 96fd8ea3e55ea33e0bdd0bf3c50a10d0de6db1a1
ms.openlocfilehash: f0c62647c5817db2057c60a7a95a62f08f7889a5

---
#<a name="dotnet-new-net-core-tools-rc4"></a>dotnet-new(.NET Core 도구 RC4)

> [!WARNING]
> 이 항목은 .NET Core 도구 RC4에 적용됩니다. .NET Core Tools Preview 2 버전의 경우 [dotnet-new](../../tools/dotnet-new.md) 항목을 참조하세요.

## <a name="name"></a>이름
dotnet-new - 현재 디렉터리에 새 .NET Core 프로젝트를 만듭니다.

## <a name="synopsis"></a>개요
```
dotnet new [template] [-lang|--language] [-n|--name] [-o|--output] [-h|--help]
dotnet new [template] [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

## <a name="description"></a>설명
`dotnet new` 명령은 CLI(명령줄 인터페이스) 도구 집합을 사용해 보기 위해 유효한 .NET Core 프로젝트 및 샘플 소스 코드를 초기화하는 편리한 방법을 제공합니다. 

이 명령은 디렉터리의 컨텍스트에서 호출됩니다. 호출되면 이 명령은 전달받은 옵션 및 템플릿에 따라 리소스 및 파일을 스캐폴딩합니다. 

그런 다음 프로젝트를 추가로 컴파일하거나 편집할 수 있습니다. 

## <a name="arguments"></a>인수
템플릿 - 명령이 호출될 때 인스턴스화할 템플릿입니다.

명령에는 템플릿의 기본 목록이 포함되어 있습니다. `dotnet new --help`를 사용하세요. 

## <a name="options"></a>옵션

`-l|--list`         

지정된 이름을 포함하는 템플릿을 나열합니다.

`-lang|--language`  

만들 템플릿의 언어를 지정합니다.

`-n|--name`         

생성되는 출력의 이름입니다. 이름을 지정하지 않으면 현재 디렉터리의 이름이 사용됩니다.

`-o|--output`       

생성된 출력을 배치할 위치입니다.

`-all|--show-all`   

특정 프로젝트 형식에 대한 템플릿을 모두 표시합니다.

`-h|--help`

명령에 대한 도움말을 출력합니다.

## <a name="template-options"></a>템플릿 옵션
각 프로젝트 템플릿에는 사용할 수 있는 추가 옵션이 있을 수 있습니다. 예를 들어 코어 템플릿에는 다음이 있습니다.

**console, xunit, mstest**

`-f|--framework` - 대상으로 할 프레임워크를 지정합니다. 값: netcoreapp1.0 또는 netcoreapp1.1(기본값: netcoreapp1.0)

**web, webapi**

`-f|--framework` - 대상으로 할 프레임워크를 지정합니다. 값: netcoreapp1.0 또는 netcoreapp1.1(기본값: netcoreapp1.0)
 
**mvc**

`-f|--framework` - 대상으로 할 프레임워크를 지정합니다. 값: netcoreapp1.0 또는 netcoreapp1.1(기본값: netcoreapp1.0)

`-au|--authentication` - 사용할 인증 형식입니다. 값: None 또는 Individual(기본값: None)

`-uld|--use-local-db` - SQLite 대신 LocalDB를 사용할지 여부입니다. 값: true 또는 false(기본값: false)

**classlib**

`-f|--framework` - 대상으로 할 프레임워크를 지정합니다. 값: netcoreapp1.0, netcoreapp1.1 및 netstandard1.0 - 1.6(기본값: netstandard1.4)

## <a name="examples"></a>예제

현재 디렉터리에 F# 콘솔 응용 프로그램 프로젝트를 만듭니다.

`dotnet new console -lang f#` 
   
.NET Core 1.0을 대상으로 하는 인증 없이 현재 디렉터리에 새 ASP.NET Core C# MVC 응용 프로그램 프로젝트를 만듭니다.  

`dotnet new mvc -au None -f netcoreapp1.0`
 
.NET Core 1.1을 대상으로 새 XUnit 응용 프로그램을 만듭니다.

`dotnet new xunit --Framework netcoreapp1.1`

MVC에 대해 사용할 수 있는 모든 템플릿을 나열합니다.

`dotnet new mvc -l`


<!--HONumber=Feb17_HO3-->


