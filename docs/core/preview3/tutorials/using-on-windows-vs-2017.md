---
title: "Visual Studio 2017을 사용하여 Windows에서 .NET Core 시작 | Microsoft 문서"
description: "Visual Studio 2017을 사용하여 Windows에서 .NET Core 시작"
keywords: .NET, .NET Core
author: bleroy
ms.author: mairaw
ms.date: 01/18/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 613c65d0-f773-41b8-ba0e-83f6a82a0b30
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: cc2c2853bc31e161d1fe0de4edc71d15281c6d24

---

# <a name="getting-started-with-net-core-on-windows-using-visual-studio-2017-net-core-tools-rc4"></a>Visual Studio 2017을 사용하여 Windows에서 .NET Core 시작(.NET Core 도구 RC4)

> [!WARNING]
> 이 항목은 .NET Core 도구 RC4에 적용됩니다. Visual Studio 2015 - .NET Core Tools Preview 2 버전의 경우 [Visual Studio 2015를 사용하여 Windows에서 .NET Core 시작](../../tutorials/using-on-windows.md) 항목을 참조하세요.

Visual Studio 2017은 .NET Core 응용 프로그램 개발을 위해 필요한 모든 기능을 갖춘 개발 환경을 제공합니다. 이 문서의 절차에서는 Visual Studio와 .NET Core를 사용하여 매우 간단한 콘솔 응용 프로그램을 빌드하는 데 필요한 단계를 설명합니다.

## <a name="prerequisites"></a>필수 구성 요소

[필수 조건 페이지](../windows-prerequisites.md)의 지침에 따라 환경을 업데이트합니다.

## <a name="getting-started"></a>시작

다음 단계는 .NET Core 콘솔 응용 프로그램 개발을 위해 Visual Studio 2017을 설정합니다.

1. Visual Studio를 열고 **파일** 메뉴에서 **새로 만들기**, **프로젝트**를 선택합니다.

2. **새 프로젝트** 대화 상자의 **템플릿** 목록에서 **Visual C#** 노드를 확장하고 **.NET Core**를 선택합니다. **콘솔 앱(.NET Core)**, **클래스 라이브러리(.NET 표준)**, **xUnit 테스트 프로젝트(.NET Core)**, **클래스 라이브러리(.NET Core)** 및 **ASP.NET Core 웹 응용 프로그램(.NET Core)**에 대한&5;개의 프로젝트 템플릿이 표시됩니다. **콘솔 앱(.NET Core)**을 선택하고, 프로젝트의 이름을 입력하고, 위치를 선택한 다음 [확인]을 클릭합니다.

  ![새 프로젝트: 콘솔 앱](media/new-project-console-app.png)

3. 결과로 생성되는 프로젝트에는 콘솔에 "Hello World"를 출력하는 단일 C# 파일이 있습니다.

  ![콘솔 앱 프로젝트](media/console-app-solution.png)

이 응용 프로그램은 F5 키를 사용하여 디버그 모드에서 또는 CTRL+F5를 사용하여 릴리스 모드에서 실행할 수 있습니다. 실행을 중단하고 변수를 검사하도록 중단점을 설정하거나, 더 흥미로운 코드 작성을 시작할 수도 있습니다.

즐거운 코딩을 경험하시기 바랍니다!

## <a name="next-steps"></a>다음 단계

이 간단한 소개를 마치고 나면 재사용 가능한 라이브러리 및 테스트로 고급 솔루션을 구축하는 방법이 궁금해질 수도 있습니다. [Visual Studio 2017을 사용하여 Windows에서 완전한 .NET Core 솔루션 구축](using-on-windows-vs-2017-full-solution.md) 항목에서는 이 방법에 대해 설명합니다.



<!--HONumber=Feb17_HO2-->


