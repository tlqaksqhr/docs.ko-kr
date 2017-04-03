---
title: "Visual Studio 2017에서 .NET Core로 클래스 라이브러리 사용"
description: "Visual Studio 2017에서 클래스 라이브러리의 멤버를 호출하는 방법 알아보기"
keywords: ".NET Core, .NET Core 클래스 라이브러리, .NET 표준, .NET 클래스 라이브러리 배포"
author: stevehoag
ms.author: shoag
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: d7b94076-1108-4174-94e7-a18f00072bb7
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 0b42eeb0149feec09ddacba98383da3abd53bb5e
ms.lasthandoff: 03/13/2017

---

# <a name="consuming-a-class-library-with-net-core-in-visual-studio-2017"></a>Visual Studio 2017에서 .NET Core로 클래스 라이브러리 사용 #

[Visual Studio 2017에서 .NET Core로 C# 클래스 라이브러리 빌드](./library-with-visual-studio-2017.md) 및 [Visual Studio 2017에서 .NET Core로 클래스 라이브러리 테스트](testing-library-with-visual-studio.md)의 단계를 따라 클래스 라이브러리를 빌드 및 테스트했으며 라이브러리의 릴리스 버전을 빌드했으므로 다음 단계는 호출자가 사용할 수 있게 만드는 것입니다. 이 작업은

- 라이브러리가 단일 솔루션에 사용되는 경우(예: 단일 대형 응용 프로그램의 구성 요소인 경우) 솔루션에 프로젝트로 포함할 수 있습니다.

- 라이브러리에 일반적으로 액세스할 수 있으면 NuGet 패키지로 배포할 수 있습니다.

## <a name="including-a-library-as-a-project-in-a-solution"></a>라이브러리를 솔루션에 프로젝트로 포함 ##

클래스 라이브러리와 동일한 솔루션에 단위 테스트를 포함한 것처럼 응용 프로그램을 해당 솔루션의 일부로 포함할 수 있습니다. 예를 들어 문자열을 입력하도록 요구하고 첫 번째 문자가 대문자인지 여부를 보고하는 콘솔 응용 프로그램에서 이 클래스 라이브러리를 사용해 보겠습니다.

1. [Visual Studio 2017에서 .NET Core로 C# 클래스 라이브러리 빌드](./library-with-visual-studio-2017.md) 항목에서 만든 `ClassLibraryProjects` 솔루션을 열고 솔루션 탐색기에서 **ClassLibraryProjects** 노드에 대한 상황에 맞는 메뉴를 열고 **추가**, **새 프로젝트**를 선택합니다.

1. 다음 그림과 같이 **새 프로젝트 추가** 대화 상자에서 **Visual C#** 및 **.NET Core** 노드를 확장하고 **콘솔 앱(.NET Core)** 프로젝트 템플릿을 선택합니다.

   ![이미지](./media/use-library.jpg)

1. **이름** 텍스트 상자에 `ShowCase`를 입력하고 **확인** 단추를 선택합니다.

1. 솔루션 탐색기에서 **ShowCase** 프로젝트 노드의 상황에 맞는 메뉴를 열고 **시작 프로젝트로 설정**을 선택합니다.

1. 처음에는 프로젝트에서 클래스 라이브러리에 액세스할 수 없습니다. 클래스 라이브러리의 메서드를 호출할 수 있도록 하려면 **솔루션 탐색기**에서 **Dependencies** 노드의 상황에 맞는 메뉴를 열고 **ShowCase** 프로젝트를 선택한 후 **참조 추가**를 선택합니다.

1. 다음 그림과 같이 **참조 관리자** 대화 상자에서 클래스 라이브러리 프로젝트인 **StringLibrary**를 선택한 후 **확인** 단추를 선택합니다.

   ![이미지](./media/add-lib-ref.jpg)

1. 'program.cs' 파일의 코드 창에서 모든 코드를 다음 코드로 바꿉니다.

 [!CODE-csharp[UsingClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/showcase.cs#1)]

   이 코드는 [Console.WindowHeight](xref:System.Console.WindowHeight) 속성을 사용하여 콘솔 창에 표시되는 행 수를 결정합니다. [Console.CursorTop](xref:System.Console.CursorTop) 속성이 콘솔 창에 있는 행의 총 수보다 크거나 같으면 코드는 콘솔 창을 지우고 사용자에게 메시지를 다시 표시합니다.

   프로그램 자체에 문자열을 입력하라는 메시지가 표시됩니다. 그런 후 문자열이 대문자로 시작하는지 여부를 나타냅니다. 사용자가 문자열을 입력하지 않고 **Enter** 키를 누르면 콘솔 창이 닫히고 응용 프로그램이 종료됩니다.

1. 필요한 경우 다음 그림과 같이 도구 모음을 변경하여 컴파일하는 `ShowCase` 프로젝트의 **디버그** 릴리스를 컴파일합니다.

   ![이미지](./media/showcase-toolbar.jpg)

1. **ShowCase** 단추에서 녹색 화살표를 클릭하여 프로그램을 컴파일하고 실행합니다.

그런 후에는 [Visual Studio 2017을 사용하여 C# Hello World 응용 프로그램 디버그](debugging-with-visual-studio-2017.md) 및 [Visual Studio 2017을 사용하여 Hello World 응용 프로그램 게시](publishing-with-visual-studio-2017.md)의 단계에 따라 이 라이브러리를 사용하는 응용 프로그램을 디버그하고 게시할 수 있습니다.

## <a name="distributing-the-library-in-a-nuget-package"></a>NuGet 패키지에 포함된 라이브러리 배포 ##

클래스 라이브러리를 NuGet 패키지로 게시하여 보다 광범위하게 사용하도록 할 수 있습니다. Visual Studio에서는 NuGet 패키지의 생성을 지원하지 않습니다. 이 패키지를 만들려면 다음과 같이 [`dotnet.exe` 명령줄 유틸리티](../../core/tools/dotnet.md)를 사용합니다.

1. 콘솔 창이 열립니다. 예를 들어 Windows 작업 표시줄의 **무엇이든 물어보세요.** 텍스트 상자에 `Command Prompt`를 입력한 다음 **명령 프롬프트** 데스크톱 앱을 선택하여 콘솔 창을 엽니다.

1. 라이브러리의 프로젝트 디렉터리로 이동합니다. 일반적으로 파일 위치를 다시 구성하지 않는 한, `Documents\Visual Studio 2017\Projects\ClassLibraryProjects\StringLibrary` 디렉터리에 있습니다. 이 디렉터리에 소스 코드 및 프로젝트 파일 `StringLibrary.csproj`가 있습니다.

1. 명령 `dotnet.exe pack --no-build`를 실행합니다. `dotnet.exe` 유틸리티는 .nupkg 확장명을 사용하여 패키지를 생성합니다.

   > [!TIP]
   > `dotnet.exe`를 포함하는 디렉터리가 해당 경로에 없는 경우 콘솔 창에 `where dotnet.exe`를 입력하여 해당 위치를 찾을 수 있습니다.

NuGet 패키지를 만드는 방법에 대한 자세한 내용은 [플랫폼 간 도구로 NuGet 패키지를 만드는 방법](../../core/deploying/creating-nuget-packages.md)을 참조하세요.
