---
title: "Visual Studio 2017에서 .NET Core를 사용하여 C# Hello World 응용 프로그램 빌드"
description: "Visual Studio 2017을 사용하여 간단한 .NET Core 콘솔 응용 프로그램을 빌드하는 방법을 알아봅니다."
keywords: ".NET Core, .NET Core 콘솔 응용 프로그램, Visual Studio 2017"
author: stevehoag
ms.author: shoag
ms.date: 03/07/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 97aa50bf-bdf8-416d-a56c-ac77504c14ea
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f1a20f399b4ab34986d700622ff3bf3859b001bd
ms.lasthandoff: 03/13/2017

---

# <a name="building-a-c-hello-world-application-with-net-core-in-visual-studio-2017"></a>Visual Studio 2017에서 .NET Core를 사용하여 C# Hello World 응용 프로그램 빌드 #

이 항목에서는 Visual Studio 2017을 사용하여 간단한 .NET Core 콘솔 응용 프로그램을 빌드, 디버그 및 게시하는 과정을 단계별로 소개합니다. Visual Studio 2017은 .NET Core 응용 프로그램 빌드를 위해 필요한 모든 기능을 갖춘 개발 환경을 제공합니다. 응용 프로그램에 플랫폼 특정 종속성이 없으면 응용 프로그램 자체는 .NET Core에서 대상으로 하는 모든 플랫폼과 .NET Core가 설치된 모든 시스템에서 실행될 수 있습니다.

## <a name="prerequisites"></a>필수 구성 요소 ##

- ".NET Core 플랫폼 간 개발" 워크로드가 설치된 [Visual Studio 2017](https://www.visualstudio.com/downloads/). 

자세한 내용은 Windows 필수 구성 요소 항목에 대한 [Visual Studio 2017](../../core/windows-prerequisites.md) 섹션을 참조하세요.

## <a name="a-simple-hello-world-application"></a>간단한 “Hello World” 응용 프로그램 ##

먼저 간단한 "Hello World" 콘솔 응용 프로그램을 만들어 보겠습니다. 단계는 다음과 같습니다.

1. Visual Studio를 시작하고 **파일** 메뉴에서 **새로 만들기** > **프로젝트**를 선택합니다. **새 프로젝트** 대화 상자의 왼쪽 창에 있는 **Visual C#** 노드를 확장하고 **.NET Core** 노드를 선택합니다.

2. 오른쪽 창에서 **콘솔 앱(.NET Core)**을 선택합니다. 프로젝트의 이름으로 `HelloWorld`를 입력하고 다음 그림과 같이 **솔루션용 디렉터리 만들기** 확인란이 선택되어 있는지 확인합니다.

   ![콘솔 앱이 선택된 새 프로젝트 대화 상자를 보여 주는 스크린샷](./media/with-visual-studio/vs_newproject.jpg)
   
3. **확인** 단추를 선택합니다. Visual Studio에서는 다음 그림과 같이 코드 창이 있는 개발 환경을 표시합니다. .NET Core용 C# 콘솔 응용 프로그램 템플릿은 @System.String 배열을 인수로 사용하는 단일 메서드 `Main`로 `Program` 클래스를 자동으로 정의합니다. `Main`은 응용 프로그램 진입점으로, 응용 프로그램을 시작할 때 런타임에 의해 자동으로 호출되는 메서드입니다. 응용 프로그램이 시작될 때 제공되는 모든 명령줄 인수는 *args* 배열에서 사용할 수 있습니다.

   ![Visual Studio 및 새 HelloWorld 프로젝트](./media/with-visual-studio/vs_devenv.jpg)

   이 템플릿은 매우 간단한 "Hello world" 응용 프로그램을 만듭니다. 이 프로그램은 @System.Console.WriteLine(System.String) 메서드를 호출하여 리터럴 문자열 "Hello World!"를 콘솔 창에 표시합니다. 도구 모음에서 녹색 화살표가 있는 "HelloWorld" 단추를 선택하여 디버그 모드에서 프로그램을 실행할 수 있습니다. 그러나 이렇게 하면 콘솔 창이 아주 잠깐만 표시되었다가 닫힙니다. `Main`은 `Main` 메서드의 단일 문이 실행되는 즉시 종료되고 응용 프로그램도 종료되기 때문입니다.

4. 콘솔 창을 닫기 전에 기존 응용 프로그램이 일시 중지되도록 해보겠습니다. @System.Console.WriteLine(System.String) 메서드 호출 바로 다음에 아래 코드를 추가합니다.

   ```csharp
   Console.Write("Press any key to continue...");
   Console.ReadKey(true);
   ```
   이 코드는 프로그램을 중지하려면 아무 키나 누르라는 메시지를 표시하며, 사용자가 아무 키나 누르면 프로그램이 일시 중지됩니다.

5. 메뉴 모음에서 **빌드**, **솔루션 빌드**를 선택합니다. 이렇게 하면 프로그램은 IL(중간 언어)로 컴파일됩니다. 이 컴파일 결과는 JIT(Just-In-Time) 컴파일러에 의해 이진 코드로 변환됩니다.

6. 도구 모음에서 녹색 화살표가 있는 "HelloWorld" 단추를 선택하여 프로그램을 실행합니다. 결과는 다음 그림에 나와 있습니다.

   ![이미지](./media/with-visual-studio/simple_hello.jpg)

7. 창을 닫으려면 아무 키나 누릅니다.

## <a name="enhancing-the-hello-world-application"></a>“Hello World” 응용 프로그램 개선 ##

사용자에게 자신의 이름을 지정하라는 메시지를 표시한 다음 콘솔 창에 날짜 및 시간과 함께 해당 사용자 이름을 표시하도록 응용 프로그램을 개선해 보겠습니다. 프로그램을 수정하고 테스트하려면 다음을 수행합니다.

1. 코드 창에서 `public static void Main(string[] args)` 줄을 입력하고 첫 번째 닫는 중괄호를 입력하기 전에 여는 중괄호 바로 뒤에 다음 C# 코드를 입력합니다.

   [!CODE [GettingStarted#1](../../../samples/snippets/csharp/getting_started/with_visual_studio/helloworld.cs#1)]

   다음 그림에서는 결과 코드 창을 보여 줍니다.

   ![수정된 프로그램 실행](./media/with-visual-studio/codewindow.jpg)

   이 코드는 "What is your name?"을 콘솔에 표시하고 사용자가 문자열을 입력한 후 Enter 키를 누를 때까지 기다립니다. 이 문자열을 `name`이라는 변수에 저장합니다. 또한 현재 현지 시간을 포함하는 @System.DateTime.Now 속성 값을 검색한 후 `date`라는 변수에 할당합니다. 그런 후 [복합 형식 문자열](../../standard/base-types/composite-format.md)을 사용하여 콘솔에 이러한 값을 표시합니다.

2. **빌드** > **솔루션 빌드**를 선택하여 프로그램을 컴파일합니다. 이렇게 하면 프로그램은 IL(중간 언어)로 컴파일됩니다. 이 컴파일 결과는 JIT(Just-In-Time) 컴파일러에 의해 이진 코드로 변환됩니다.

3. 도구 모음에서 녹색 화살표를 선택하거나, F5 키를 누르거나, **디버그** > **디버깅 시작** 메뉴 항목을 선택하여 Visual Studio의 디버그 모드에서 프로그램을 실행합니다. 이름을 입력하고 Enter 키를 눌러 프롬프트에 응답하면 콘솔 창은 다음과 같이 표시됩니다.

   ![수정된 프로그램 실행](./media/with-visual-studio/console.jpg)

4. 콘솔 창을 닫으려면 아무 키나 누릅니다. 그러면 디버그 모드가 종료됩니다.

이제 간단한 응용 프로그램을 만들고 실행했습니다. 전문가 수준의 응용 프로그램을 개발하기 위해서는 응용 프로그램 릴리스 준비를 위해 수행할 수 있는 몇 가지 추가 단계가 여전히 남아 있습니다.

- 응용 프로그램 디버그에 대한 자세한 내용은 [Hello World 응용 프로그램 디버그](debugging-with-visual-studio-2017.md)를 참조하세요.

- 응용 프로그램의 배포 가능 버전 개발에 대한 자세한 내용은 [Hello World 응용 프로그램 게시](publishing-with-visual-studio-2017.md)를 참조하세요.

## <a name="related-topics"></a>관련 항목 ##

콘솔 응용 프로그램 대신 .NET Core 및 Visual Studio 2017을 사용하여 클래스 라이브러리를 빌드할 수도 있습니다. 단계별 지침을 보려면 [Visual Studio 2017에서 C# 및 .NET Core로 클래스 라이브러리 빌드](library-with-visual-studio-2017.md)를 참조하세요.

또한 무료로 다운로드할 수 있는 코드 편집기인 Visual Studio Code를 사용하여 Mac, Linux 및 Windows에서 .NET Core 콘솔 응용 프로그램을 개발할 수 있습니다. 단계별 자습서에 대해서는 [Visual Studio Code 시작](with-visual-studio-code.md)을 참조하세요.

