---
title: "Windows | Microsoft Docs에서 .NET Core의 필수 구성 요소"
description: "Windows 컴퓨터에서 .NET Core 응용프로그램을 개발 및 실행하기 위해 필요한 종속성이 무엇인지 살펴보세요."
keywords: ".NET Core, Windows, 필수 구성 요소, 종속성, Visual Studio"
author: mairaw
ms.author: mairaw
ms.date: 01/05/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
translationtype: Human Translation
ms.sourcegitcommit: a8019c9fc25ef458aa555743e61cd83a3beb11ed
ms.openlocfilehash: b5c088da7d1155414a08995ae0d72154af891190
ms.lasthandoff: 02/28/2017

---

# <a name="prerequisites-for-net-core-on-windows"></a>Windows에서 .NET Core의 필수 구성 요소

이 문서에서는 Windows 컴퓨터에서 .NET Core 응용프로그램을 배포 및 실행하고 Visual Studio 를 사용하여 개발하기 위해 필요한 종속성을 보여 줍니다.

## <a name="supported-windows-versions"></a>지원되는 Windows 버전

.NET Core는 다음 Windows 버전에서 지원됩니다.

* Windows 7 SP1
* Windows 8.1
* Windows 10
* Windows Server 2008 R2 SP1(전체 서버 또는 Server Core)
* Windows Server 2012 SP1(전체 서버 또는 Server Core)
* Windows Server 2012 R2 SP1(전체 서버 또는 Server Core)
* Windows Server 2016(전체 서버, Server Core 또는 Nano 서버)

[.NET Core 1.0.0 릴리스 정보](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0.md)에서 [지원되는 운영 체제](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0.md#rtm-platform-support)의 전체 집합을 볼 수 있습니다.

## <a name="net-core-dependencies"></a>.NET Core 종속성

Windows 10 및 Windows Server 2016보다 이전 버전의 Windows에서 실행하는 경우.NET core는 Visual C++ 재배포 가능 패키지가 필요합니다. 이 종속성은.NET Core 설치 관리자를 사용하는 경우에 자동으로 설치됩니다. 그러나 [설치 관리자 스크립트](https://docs.microsoft.com/en-us/dotnet/articles/core/tools/dotnet-install-script)를 통해 .NET Core를 설치하거나 자체 포함 .NET Core 응용프로그램을 배포하는 경우에는 [Visual Studio 2015용 Visual C++ 재배포 가능 패키지](https://www.microsoft.com/en-us/download/details.aspx?id=48145)를 수동으로 설치해야 합니다.

> [!NOTE]
> <em>Windows 7 및 Windows Server 2008용 컴퓨터만 해당:</em><br>
> 설치된 Windows가 최신 버전이며 Windows 업데이트를 통해 설치된 핫픽스 [KB2533623](https://support.microsoft.com/en-us/kb/2533623)이 포함되어 있는지 확인하세요.

## <a name="prerequisites-with-visual-studio"></a>Visual Studio 필수 구성 요소

.NET Core SDK를 사용하여 .NET Core 응용 프로그램을 개발할 수 있도록 원하는 편집기를 사용할 수 있습니다. 그러나 Visual Studio를 사용하여 Windows에서 .NET Core 응용 프로그램을 개발하려는 경우 두 가지 버전을 사용할 수 있습니다.

* [Visual Studio 2015](#visual-studio-2015)
* [Visual Studio 2017 RC](#visual-studio-2017-rc)

Visual Studio 2015를 사용하여 만든 프로젝트는 기본적으로 project.json 기반이지만 Visual Studio 2017 RC를 사용하여 만든 프로젝트는 항상 MSBuild 기반이 됩니다. 형식 변경에 대한 자세한 내용은 [변경 내용의 대략적인 개요](./preview3/tools/layering.md)를 참조하세요.

### <a name="visual-studio-2015"></a>Visual Studio 2015

.NET Core 앱을 개발하기 위해 Visual Studio 2015를 사용하려는 경우 다음이 필요합니다.

* Visual Studio 2015 업데이트 3.3 이상

   여러 [버전](https://www.visualstudio.com/vs/compare)의 Visual Studio 2015가 있습니다. [Visual Studio Community 2015](https://www.visualstudio.com/downloads/)를 무료로 다운로드하여 시작할 수 있습니다. 

   [Visual Studio 2015 업데이트 3.3](https://msdn.microsoft.com/library/mt752379.aspx)을 실행 중인지 확인하려면 다음을 수행하세요.

   * **도움말** 메뉴에서 **Microsoft Visual Studio 정보**를 선택합니다.
   * **Microsoft Visual Studio 정보** 대화 상자에서 버전 번호가 14.0.25424.00 이상이어야 하며, "업데이트 3"을 포함해야 합니다.
   * 업데이트 3이 없으면 먼저 [Visual Studio 2015 업데이트 3](https://www.visualstudio.com/news/releasenotes/vs2015-update3-vs)을 다운로드 및 설치해야 합니다.
   * 업데이트 3이 있지만 버전 번호가 14.0.25424.00보다 작은 경우 [Visual Studio 2015 업데이트 3.3](https://msdn.microsoft.com/library/mt752379.aspx)을 다운로드 및 설치해야 합니다.

   [릴리스 정보](https://www.visualstudio.com/news/releasenotes/vs2015-update3-vs)에서 업데이트 3의 변경 내용에 대해 자세히 알아볼 수 있습니다.

* Visual Studio용 NuGet Manager 확장

   NuGet은 .NET Core를 포함한 Microsoft 개발 플랫폼에 대한 패키지 관리자입니다. .NET Core 앱을 빌드하려면 [NuGet 3.5.0-beta](https://dist.nuget.org/visualstudio-2015-vsix/v3.5.0-beta/NuGet.Tools.vsix) 이상이 필요합니다.

* .NET Core Tooling Preview 2

   [.NET Core 1.0.1 - VS 2015 Tooling Preview 2][sdk]를 다운로드하여 설치합니다. 

   .NET Core 도구 패키지는 Visual Studio 2015용 .NET Core, 프로젝트 템플릿 및 기타 도구를 설치합니다.

   > [!NOTE]
   > 지금은 [.NET Core 1.0.1 - VS 2015 Tooling Preview 2][sdk]용 오프라인 설치 관리자를 다운로드할 수 없습니다. 오프라인 레이아웃을 이용하려면 대신 [일반 부트스트래퍼][sdk]를 다운로드하고 명령줄 옵션(예: `/layout c:\path`)과 함께 실행해야 합니다. 그런 다음 오프라인 설치 관리자로 사용할 수 있습니다. 로컬 경로에서 바로 실행 파일을 실행합니다. 이 절차는 전체 레이아웃이므로 지원되는 모든 언어의 모든 패키지를 다운로드하며 크기는 약 1GB입니다.

### <a name="visual-studio-2017-rc"></a>Visual Studio 2017 RC

.NET Core 앱을 개발하기 위해 Visual Studio 2017 RC를 사용하려는 경우 선택한 ".NET Core and Docker (Preview)" 워크로드를 사용하여 최신 버전의 Visual Studio RC를 설치해야 합니다. 

여러 버전의 Visual Studio 2017 RC가 있습니다. [Visual Studio Community 2017 RC](https://www.visualstudio.com/vs/visual-studio-2017-rc/#downloadvs)는 무료로 다운로드하여 시작할 수 있습니다.  Visual Studio 설치 프로세스에 대한 자세한 내용은 [Visual Studio 2017 RC 설치](https://docs.microsoft.com/en-us/visualstudio/install/install-visual-studio)를 참조하세요.

최신 버전의 Visual Studio 2017 RC를 실행 중인지 확인하려면 다음을 수행합니다.

* **도움말** 메뉴에서 **Microsoft Visual Studio 정보**를 선택합니다.
* **Microsoft Visual Studio 정보** 대화 상자에서 버전 번호가 15.0.26020.0 이상이어야 합니다.

[릴리스 정보](https://www.visualstudio.com/en-us/news/releasenotes/vs2017-relnotes)에서 Visual Studio 2017 RC의 변경 내용에 대해 자세히 알아볼 수 있습니다.

[sdk]: https://go.microsoft.com/fwlink/?LinkID=827546

