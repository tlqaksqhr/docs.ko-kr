---
title: "Visual Studio Code 시작 | C# 가이드"
description: "VS Code를 사용하여 C#에서 첫 번째 .NET Core 응용 프로그램을 만들고 디버그하는 방법을 알아봅니다."
keywords: "C#, 시작, 취득, 설치, Visual Studio Code, 플랫폼 간"
author: kendrahavens
ms.author: mairaw
ms.date: 03/07/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 76c23597-4cf9-467e-8a47-0c3703ce37e7
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 4550129f4e6f1eeb3521ad7fe3233f2bda49e5c5
ms.lasthandoff: 03/13/2017

---

# <a name="getting-started-with-visual-studio-code"></a>Visual Studio Code 시작

.NET Core는 Windows, Linux 및 macOS에서 실행되는 서버 응용 프로그램을 만들기 위한 빠른 모듈식 플랫폼을 제공합니다. C# 확장이 있는 Visual Studio Code를 사용하면 C# IntelliSense(스마트 코드 완성) 및 디버깅을 완벽하게 지원하는 강력한 편집 환경이 구현됩니다.

## <a name="prerequisites"></a>필수 구성 요소

1. [Visual Studio Code](https://code.visualstudio.com/)를 설치합니다.
2. [.NET Core SDK](https://www.microsoft.com/net/download/core)를 설치합니다.
3. Visual Studio Code Marketplace에서 [C# 확장](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)을 설치합니다.

## <a name="hello-world"></a>Hello World

.NET Core에서 간단한 "Hello World" 프로그램으로 시작해 보겠습니다.

1. 프로젝트 열기

    * VS Code를 엽니다.
    * 왼쪽 메뉴에 있는 탐색기 아이콘을 클릭한 다음 **폴더 열기**를 클릭합니다.
    * C# 프로젝트를 저장할 폴더를 선택하고 **폴더 선택**을 클릭합니다. 이 예제에서는 'hello World'라는 프로젝트에 대한 폴더를 만들어 봅니다. 

  ![VSCodeOpenFolder](media/with-visual-studio-code/vscodeopenfolder.png)

    * 또는 주 메뉴에서 **파일** > **폴더 열기**를 선택하여 프로젝트 폴더를 열 수 있습니다.

2. C# 프로젝트 초기화
    * <kbd>CTRL</kbd>+<kbd>\` </kbd>(백틱 기호)을 입력하여 VS Code에서 통합 터미널을 엽니다.
    * 터미널 창에서 `dotnet new console`을 입력합니다.
    * 이렇게 하면 이미 작성된 간단한 "Hello World" 프로그램이 있는 폴더에 `Program.cs` 파일이 만들어지고 `HelloWorld.csproj`라는 C# 프로젝트 파일이 만들어집니다.

  ![dotnet new 명령](media/with-visual-studio-code/dotnetnew.png)

3. 빌드 자산 확인

    * `dotnet restore`를 입력합니다. `dotnet restore`를 실행하면 프로젝트를 빌드하는 데 필요한 필수 .NET Core 패키지에 액세스할 수 있습니다.

  ![dotnet restore 명령](media/with-visual-studio-code/dotnetrestore.png)

4. "Hello World" 프로그램 실행

    * `dotnet run`를 입력합니다. 

  ![dotnet run 명령](media/with-visual-studio-code/dotnetrun.png)

[Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS) 또는 [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu)에 대한 추가 설치 도움말이 제공되는 짧은 비디오 자습서를 볼 수도 있습니다.

## <a name="debug"></a>디버그
1. *Program.cs*를 클릭하여 엽니다. VS Code에서 C# 파일을 처음 열면 [OmniSharp](http://www.omnisharp.net/)에서 편집기가 로드됩니다.

  ![Program.cs 파일 열기](media/with-visual-studio-code/opencs.png)

2. VS Code는 앱을 빌드하고 디버그하기 위해 누락된 자산을 추가하라는 메시지를 표시합니다. **예**를 선택합니다. 

  ![누락된 자산에 대한 프롬프트](media/with-visual-studio-code/missing-assets.png)

3. 디버그 보기를 열려면 왼쪽 메뉴에서 디버깅 아이콘을 클릭합니다.

  ![디버그 탭 열기](media/with-visual-studio-code/opendebug.png)

4. 창 위쪽에서 녹색 화살표를 찾습니다. 옆에 있는 드롭다운 목록에서 `.NET Core Launch (console)`가 선택되어 있는지 확인합니다.

  ![.NET Core 선택](media/with-visual-studio-code/selectcore.png)

5. 9번째 줄 옆에 있는 **편집기 여백**(편집기에서 줄 번호 왼쪽에 있는 공간)을 클릭하여 프로젝트에 중단점을 추가합니다.

  ![중단점 설정](media/with-visual-studio-code/setbreakpoint.png)

6. <kbd>F5</kbd> 또는 녹색 화살표를 선택하여 디버그를 시작합니다. 이전 단계에서 설정한 중단점에 도달하면 디버거에서 프로그램 실행을 중지합니다.
    * 디버깅 동안 왼쪽 위에 있는 창에서 지역 변수를 보거나 디버그 콘솔을 사용할 수 있습니다.

  ![실행 및 디버그](media/with-visual-studio-code/rundebug.png)

7. 디버깅을 계속하려면 위쪽에 있는 녹색 화살표를 선택하고, 중지하려면 빨간색 사각형을 누릅니다.

> [!TIP] 
> VS Code에서 OmniSharp를 사용한 .NET Core 디버깅에 대한 자세한 내용 및 문제 해결 정보는 [.NET Core 디버거 설정 지침](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md)을 참조하세요.

## <a name="see-also"></a>참고 항목
- [Visual Studio Code 설치](https://code.visualstudio.com/docs/setup/setup-overview)
- [Visual Studio Code의 디버깅](https://code.visualstudio.com/Docs/editor/debugging)

