---
title: Visual Studio for Mac을 사용하여 macOS에서 .NET Core 시작
description: 이 항목에서는 Mac 및 .NET Core용 Visual Studio를 사용하여 간단한 콘솔 응용 프로그램을 빌드하는 과정을 안내합니다.
author: guardrex
ms.author: mairaw
ms.date: 06/12/2017
ms.topic: get-started-article
ms.prod: dotnet-core
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: 97a9c62280f09f244028c066a04350a59dd0400d
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="getting-started-with-net-core-on-macos-using-visual-studio-for-mac"></a>Visual Studio for Mac을 사용하여 macOS에서 .NET Core 시작

Visual Studio for Mac은 .NET Core 응용 프로그램 개발을 위해 필요한 전기능 IDE(통합 개발 환경)를 제공합니다. 이 항목에서는 Mac 및 .NET Core용 Visual Studio를 사용하여 간단한 콘솔 응용 프로그램을 빌드하는 과정을 안내합니다.

> [!NOTE]
> 사용자 의견은 매우 중요합니다. 두 가지가 Visual Studio for Mac의 개발 팀에 다음 두 가지 방법으로 의견을 제공할 수 있습니다.
> * Mac용 Visual Studio의 메뉴에서 **도움말** > **문제 보고**를 선택하거나 시작 화면에서 **문제 보고**를 선택하면 버그 보고서를 작성하기 위한 창이 열립니다. [Developer Community](https://developercommunity.visualstudio.com/spaces/8/index.html)(개발자 커뮤니티) 포털에서 의견을 추적할 수 있습니다.
> * 제안하려면 메뉴에서 **도움말** > **제안하기**를 선택하거나 시작 화면에서 **제안하기**를 선택합니다. 그러면 [Mac용 Visual Studio UserVoice 웹 페이지](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac)로 이동됩니다.

## <a name="prerequisites"></a>전제 조건

[Mac에서 .NET Core의 필수 구성 요소](../../core/macos-prerequisites.md) 항목을 참조하세요.

## <a name="getting-started"></a>시작

필수 구성 요소와 Visual Studio for Mac을 이미 설치한 경우 이 섹션을 건너뛰고 [프로젝트 만들기](#creating-a-project)를 계속 진행합니다. 다음 단계에 따라 필수 구성 요소 및 Visual Studio for Mac을 설치합니다.

[Visual Studio for Mac 설치 관리자](https://www.visualstudio.com/vs/visual-studio-mac/)를 다운로드합니다. 설치 관리자를 실행합니다. 사용권 계약을 읽은 다음 동의합니다. 설치하는 동안 플랫폼 간 모바일 앱 개발 기술인 Xamarin을 설치할 기회가 제공됩니다. Xamarin 및 관련된 구성 요소의 설치는 .NET Core 개발에서 선택 사항입니다. Visual Studio for Mac 설치 프로세스에 대한 연습을 진행하려면 [Visual Studio for Mac 소개](https://developer.xamarin.com/guides/cross-platform/visual-studio-mac/)를 참조하세요. 설치가 완료되면 Visual Studio for Mac IDE를 시작합니다.

## <a name="creating-a-project"></a>프로젝트 만들기

1. 시작 화면에서 **새 프로젝트**를 선택합니다.

   ![Visual Studio for Mac 시작 화면의 새 프로젝트 단추](./media/using-on-mac-vs/vsmac1.png)

1. **새 프로젝트** 대화 상자에서 **.NET Core** 노드 아래에서 **앱**을 선택합니다. **콘솔 응용 프로그램** 템플릿을 선택하고 **다음**을 선택합니다.

   ![새 프로젝트 템플릿 목록](./media/using-on-mac-vs/vsmac2.png)

1. **프로젝트 이름**으로 "HelloWorld"를 입력합니다. **만들기**를 선택합니다.

   ![새 콘솔 응용 프로그램 대화 상자 구성](./media/using-on-mac-vs/vsmac3.png)

1. 프로젝트의 종속성이 복원되는 동안 기다립니다. 프로젝트에는 `Main` 메서드가 있는 `Program` 클래스를 포함하는 C# 파일 *Program.cs*가 있습니다. 앱이 실행되면 `Console.WriteLine` 문은 "Hello World!"를 콘솔에 출력합니다.

   ![Program.cs 파일이 열려 있는 주 창](./media/using-on-mac-vs/vsmac4.png)

## <a name="run-the-application"></a>응용 프로그램 실행

<kbd>F5</kbd> 키를 사용하여 디버그 모드에서 또는 <kbd>Ctrl</kbd>+<kbd>F5</kbd>를 사용하여 릴리스 모드에서 이 앱을 실행합니다.

![응용 프로그램 출력 창에 Hello World!가 표시됩니다.](./media/using-on-mac-vs/vsmac5.png)

## <a name="next-step"></a>다음 단계

[Visual Studio for Mac을 사용하여 macOS에서 완전한 .NET Core 솔루션 빌드](using-on-mac-vs-full-solution.md) 항목에서는 재사용 가능한 라이브러리 및 단위 테스트를 포함하는 전체 .NET Core 솔루션을 빌드하는 방법을 보여 줍니다.
