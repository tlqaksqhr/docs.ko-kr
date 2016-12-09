---
title: ".NET Core 필수 구성 요소(Preview 3 Tooling)"
description: ".NET Core 필수 구성 요소(Preview 3 Tooling)"
keywords: .NET, .NET Core
author: billwagner
ms.author: wiwagn
ms.date: 09/15/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
translationtype: Human Translation
ms.sourcegitcommit: 07b62bd7163193eff8dc8f61fda7a45a924bba2b
ms.openlocfilehash: ee4ccba7c06f0a7f67e3fe59c885febf895235fd

---

# <a name="prerequisites-for-windows-development-preview-3-tooling"></a>Windows 개발을 위한 필수 구성 요소(Preview 3 Tooling)

Visual Studio를 사용하여 Windows에서 .NET Core로 개발하려면 다음이 필요합니다.

* 지원되는 Windows 클라이언트 또는 운영 체제 버전
* Visual Studio 2017 RC 이상 버전
* .NET Core Tooling Preview 3

## <a name="supported-windows-versions"></a>지원되는 Windows 버전

.NET Core는 다음 Windows 버전에서 지원됩니다.

* Windows 7 SP1
* Windows 8.1
* Windows 10
* Windows Server 2008 R2 SP1(전체 서버 또는 Server Core)
* Windows Server 2012 SP1(전체 서버 또는 Server Core)
* Windows Server 2012 R2 SP1(전체 서버 또는 Server Core)
* Windows Server 2016(전체 서버, Server Core 또는 Nano 서버)

[.NET Core 릴리스 정보](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0.md)에서 [지원되는 운영 체제](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0.md#rtm-platform-support)의 전체 집합을 볼 수 있습니다.

## <a name="net-core-dependencies"></a>.NET Core 종속성

.NET Core를 Windows에서 실행하려면 VC++ 재배포 가능 패키지가 필요합니다. .NET Core 설치 관리자에서 이를 설치합니다. 설치 관리자 스크립트를 통해 .NET Core를 설치하는 경우 Visual C++ 재배포 가능 패키지를 수동으로 설치해야 합니다(`dotnet-install.ps1`). 

Visual C++ 재배포 가능 패키지 버전은 Windows 버전에 따라 다릅니다.

* Windows 10
    * [Visual Studio 2015용 Visual C++ 재배포 가능 패키지](https://www.microsoft.com/en-us/download/details.aspx?id=48145)
* Windows 7 이상(Windows 10 제외)
    * 설치된 Windows가 최신 버전이며 Windows 업데이트를 통해 설치된 핫픽스 [KB2533623](https://support.microsoft.com/en-us/kb/2533623)이 포함되어 있는지 확인하세요.
    * [유니버설 CRT 업데이트](https://www.microsoft.com/en-us/download/details.aspx?id=48234)(유니버설 CRT에 대한 자세한 내용은 [이 블로그 게시물](https://blogs.msdn.microsoft.com/vcblog/2015/03/03/introducing-the-universal-crt/) 참조)

## <a name="visual-studio"></a>Visual Studio

.NET Core 명령줄 도구를 사용하는 어느 편집기에서나 .NET Core 앱을 개발할 수 있습니다. 하지만 Visual Studio와, .NET Core 도구의 Preview 3을 사용하려면 Visual Studio 2017 RC 이상이 필요합니다. [Visual Studio Community 2017 RC](https://www.visualstudio.com/vs/visual-studio-2017-rc/)는 무료로 다운로드할 수 있습니다. 

Visual Studio 2017 RC를 실행 중인지 확인하세요.

* **도움말** 메뉴에서 **Microsoft Visual Studio 정보**를 선택합니다.
* **Microsoft Visual Studio 정보** 대화 상자에서 버전 번호가 15.0.25831.1 이상이어야 합니다.

[릴리스 정보](https://www.visualstudio.com/en-us/news/releasenotes/vs2017-relnotes)에서 Visual Studio 2017 RC의 변경 내용에 대해 자세히 알아볼 수 있습니다.

설치하는 동안 ".NET Core 및 Docker(Preview)" 작업을 설치했는지 확인하세요. 그렇지 않은 경우 설치 프로그램을 다시 실행하여 선택할 수 있습니다.



<!--HONumber=Nov16_HO3-->


