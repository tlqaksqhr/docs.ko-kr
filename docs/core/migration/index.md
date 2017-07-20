---
title: "csproj 형식으로 .NET Core 마이그레이션 | Microsoft 문서"
description: ".NET Core project.json을 csproj로 마이그레이션"
keywords: ".NET, .NET Core, .NET Core 마이그레이션"
author: blackdwarf
ms.author: mairaw
ms.date: 03/13/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 1feadf3d-3cfc-41dd-abb5-a4fc303a7b53
ms.translationtype: Human Translation
ms.sourcegitcommit: b64eb0d8f1778a4834ecce5d2ced71e0741dbff3
ms.openlocfilehash: ac870aa302c3e56b59cbfdfd0fc88e06bbaad5fb
ms.contentlocale: ko-kr
ms.lasthandoff: 05/27/2017

---

<a id="migrating-net-core-projects-to-the-csproj-format" class="xliff"></a>

# .csproj 형식으로 .NET Core 프로젝트 마이그레이션

이 문서에서는 .NET Core 프로젝트에 대한 마이그레이션 시나리오를 설명하고 다음 세 가지 마이그레이션 시나리오를 살펴봅니다.

1. [*project.json*의 유효한 스키마에서 *csproj*로 마이그레이션](#migration-from-projectjson-to-csproj)
2. [DNX에서 csproj로 마이그레이션](#migration-from-dnx-to-csproj)
3. [RC3 및 이전 .NET Core csproj 프로젝트에서 최종 형식으로 마이그레이션](#migration-from-earlier-net-core-csproj-formats-to-rtm-csproj)

<a id="migration-from-projectjson-to-csproj" class="xliff"></a>

## project.json에서 csproj로 마이그레이션
*project.json*에서 *.csproj*로 마이그레이션하려면 다음 방법 중 하나를 사용할 수 있습니다.

- [Visual Studio 2017](#visual-studio-2017)
- [dotnet 마이그레이션 명령줄 도구](#dotnet-migrate)
 
두 방법 모두 동일한 기본 엔진을 사용하여 프로젝트를 마이그레이션하므로 결과가 동일합니다. 대부분의 경우 이러한 두 가지 방법 중 하나를 사용하여 *project.json*을 *csproj*로 마이그레이션하기만 하면 되며 프로젝트 파일을 추가로 수동 편집할 필요가 없습니다. 결과로 얻는 *.csproj* 파일의 이름은 포함되는 디렉터리 이름과 동일하게 지정됩니다.

<a id="visual-studio-2017" class="xliff"></a>

### Visual Studio 2017

*.xproj* 파일이나 *.xproj* 파일을 참조하는 솔루션 파일을 열면 **단방향 업그레이드** 대화 상자가 나타납니다. 이 대화 상자에 마이그레이션할 프로젝트가 표시됩니다. 솔루션 파일을 여는 경우에는 솔루션 파일에 지정된 모든 프로젝트가 나열됩니다. 마이그레이션할 프로젝트 목록을 검토하고 **확인**을 선택합니다.

![마이그레이션할 프로젝트 목록을 표시하는 단방향 업그레이드 대화 상자](media/one-way-upgrade.jpg)

Visual Studio는 선택된 프로젝트를 자동으로 마이그레이션합니다. 솔루션을 마이그레이션할 때 모든 프로젝트를 선택하지 않는 경우에는 동일한 대화 상자에 해당 솔루션의 나머지 솔루션을 업그레이드할지 묻는 메시지가 표시됩니다.

마이그레이션된 파일(*project.json*, *global.json*, *.xproj* 및 솔루션 파일)은 *Backup* 폴더로 이동됩니다. 마이그레이션된 솔루션 파일은 Visual Studio 2017로 업그레이드되며 이전 버전의 Visual Studio에서 해당 솔루션 파일을 열 수 없습니다. 마이그레이션 보고서를 포함하는 *UpgradeLog.htm*이라는 파일도 저장되고 자동으로 열립니다.

> [!IMPORTANT]
> Visual Studio 2015에서는 새로운 도구를 사용할 수 없으므로, 해당 버전의 Visual Studio를 사용하여 프로젝트를 마이그레이션할 수 없습니다.

<a id="dotnet-migrate" class="xliff"></a>

### dotnet 마이그레이션

명령줄 시나리오에서는 [`dotnet migrate`](../tools/dotnet-migrate.md) 명령을 사용할 수 있습니다. 이 경우 프로젝트, 솔루션 또는 폴더 집합을 발견된 순서에 따라 차례로 마이그레이션합니다. 프로젝트를 마이그레이션하면 프로젝트 및 프로젝트의 모든 종속 항목이 마이그레이션됩니다.

마이그레이션된 파일(*project.json*, *global.json* 및 *.xproj*)은 *backup* 폴더로 이동됩니다.

> [!NOTE]
> Visual Studio Code를 사용 중인 경우 `dotnet migrate` 명령은 `tasks.json`과 같은 Visual Studio Code 관련 파일을 수정하지 않습니다. 이러한 파일은 수동으로 변경해야 합니다. Project Ryder나 다른 편집기 또는 Visual Studio 이외의 IDE(통합 개발 환경)를 사용 중인 경우에도 마찬가지입니다. 

project.json 및 csproj 형식 간을 비교하려면 [project.json 및 csproj 속성 간 매핑](../tools/project-json-to-csproj.md)을 참조하세요.

<a id="common-issues" class="xliff"></a>

### 일반적인 문제

- “No executable found matching command dotnet-migrate”(dotnet-migrate 명령과 일치하는 실행 파일을 찾을 수 없습니다.) 오류가 발생하는 경우 다음을 수행합니다.

`dotnet --version`을 실행하여 사용 중인 버전을 확인합니다. [`dotnet migrate`](../tools/dotnet-migrate.md)을 사용하려면 .NET Core CLI RC3 이상이 필요합니다.
*global.json* 파일이 현재 또는 상위 디렉터리에 있고 `sdk` 버전이 이전 버전으로 설정된 경우 이 오류가 발생합니다.

<a id="migration-from-dnx-to-csproj" class="xliff"></a>

## DNX에서 csproj로 마이그레이션
.NET Core 개발에 DNX를 여전히 사용 중인 경우 다음 두 단계로 마이그레이션 프로세스를 수행해야 합니다.

1. [기존 DNX 마이그레이션 지침](from-dnx.md)에 따라 DNX에서 project-json 사용 CLI로 마이그레이션합니다.
2. 이전 섹션의 단계에 따라 *project.json*에서 *.csproj*로 마이그레이션합니다.  

> [!NOTE]
> DNX는 .NET Core CLI의 Preview 1 릴리스부터 공식적으로 더 이상 사용되지 않습니다. 

<a id="migration-from-earlier-net-core-csproj-formats-to-rtm-csproj" class="xliff"></a>

## 이전 .NET Core csproj 형식에서 RTM csproj로 마이그레이션
.NET Core csproj 형식은 새 시험판 버전의 도구가 나올 때마다 변경되고 개선되었습니다. csproj의 이전 버전에서 최신 버전으로 프로젝트 파일을 마이그레이션하는 도구는 없으므로 프로젝트 파일을 수동으로 편집해야 합니다. 실제 단계는 마이그레이션하는 프로젝트 파일의 버전에 따라 달라집니다. 다음은 버전 간에 수행된 변경 사항에 따라 고려할 몇 가지 지침입니다.

* `<Project>` 요소에 도구 버전 속성이 있는 경우 제거합니다. 
* `<Project>` 요소에서 XML 네임스페이스(`xmlns`)를 제거합니다.
* `Sdk` 특성이 없는 경우 `<Project>` 요소에 추가하고 `Microsoft.NET.Sdk` 또는 `Microsoft.NET.Sdk.Web`으로 설정합니다. 이 특성은 프로젝트에서 사용할 SDK를 사용하도록 지정합니다. 웹앱에는 `Microsoft.NET.Sdk.Web`이 사용됩니다.
* 프로젝트의 맨 위와 맨 아래에서 `<Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />` 및 `<Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />` 문을 제거합니다. 이러한 import 문은 SDK에 포함되므로, 프로젝트에 있을 필요가 없습니다. 
* 프로젝트에 `Microsoft.NETCore.App` 또는 `NETStandard.Library` `<PackageReference>` 항목이 있으면 제거해야 합니다. 이러한 패키지 참조는 [SDK에 포함](https://aka.ms/sdkimplicitrefs)되어 있습니다. 
* `Microsoft.NET.Sdk` `<PackageReference>` 요소가 있는 경우 제거합니다. SDK 참조는 `<Project>` 요소의 `Sdk` 특성을 통해 가져옵니다. 
* [SDK에 포함](../tools/csproj.md#default-compilation-includes-in-net-core-projects)된 [glob](https://en.wikipedia.org/wiki/Glob_(programming))을 제거합니다. 프로젝트에 이러한 GLOB를 남겨 두면 컴파일 항목이 중복되므로 빌드 시 오류가 발생합니다. 

이러한 단계를 수행하면 프로젝트가 RTM .NET Core csproj 형식과 완벽히 호환됩니다. 

이전 csproj 형식에서 새 형식으로 마이그레이션하기 전후의 예는 .NET 블로그에서 [Updating Visual Studio 2017 RC – .NET Core Tooling improvements](https://blogs.msdn.microsoft.com/dotnet/2016/12/12/updating-visual-studio-2017-rc-net-core-tooling-improvements/)(Visual Studio 2017 RC 업데이트 – .NET Core 도구 개선 사항) 문서를 참조하세요.

