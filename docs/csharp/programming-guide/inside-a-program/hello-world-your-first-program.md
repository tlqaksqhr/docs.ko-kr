---
title: "Hello World -- 프로그램 처음 만들기(C# 프로그래밍 가이드) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: get-started-article
f1_keywords:
- cs.program
- vs.csharp.startpage.firstapplication
dev_langs:
- CSharp
helpviewer_keywords:
- examples [C#], Hello World
- Hello World example [C#]
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
caps.latest.revision: 39
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 7e33ed084c560470a486ebbb25035a59ddc18565
ms.openlocfilehash: 21abcf70cce2d6c9052629ce60d08e9ec6ac16e7
ms.contentlocale: ko-kr
ms.lasthandoff: 03/31/2017

---
# <a name="hello-world----your-first-program-c-programming-guide"></a>Hello World -- 프로그램 처음 만들기(C# 프로그래밍 가이드)
다음 절차에서는 기존 "Hello World!" 프로그램의 C# 버전을 만듭니다. 이 프로그램은 문자열 `Hello World!`를 표시합니다.  
  
 소개 개념에 대한 추가 예제는 [Visual C# 및 Visual Basic 시작](https://docs.microsoft.com/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic)을 참조하세요.  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-create-and-run-a-console-application"></a>콘솔 응용 프로그램을 만들고 실행하려면  
  
1.  Visual Studio를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.  
  
     **새 프로젝트** 대화 상자가 열립니다.  
  
3.  **설치됨**, **템플릿**, **Visual C#**을 차례로 확장하고 **콘솔 응용 프로그램**을 선택합니다.  
  
4.  **이름** 상자에 프로젝트의 이름을 지정하고 **확인** 단추를 선택합니다.  
  
     **솔루션 탐색기**에 새 프로젝트가 표시됩니다.  
  
5.  Program.cs가 **코드 편집기**에 열려 있지 않으면 **솔루션 탐색기**에서 **Program.cs**의 바로 가기 메뉴를 열고 **코드 보기**를 선택합니다.  
  
6.  Program.cs의 내용을 다음 코드로 바꿉니다.  
  
     [!code-cs[csProgGuide#21](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_1.cs)]  
  
7.  F5 키를 선택하여 프로젝트를 실행합니다. `Hello World!` 줄이 포함된 명령 프롬프트 창이 나타납니다.  
  
 다음으로 이 프로그램의 중요 경로가 검사됩니다.  
  
## <a name="comments"></a>설명  
 첫 번째 줄에는 설명이 포함됩니다. `//` 문자는 줄의 나머지 부분을 설명으로 변환합니다.  
  
 [!code-cs[csProgGuide#32](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_2.cs)]  
  
 텍스트 블록을 `/*` 및 `*/` 문자 사이에 포함하여 주석으로 처리할 수도 있습니다. 다음 예제에서 이를 확인할 수 있습니다.  
  
 [!code-cs[csProgGuide#33](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_3.cs)]  
  
## <a name="main-method"></a>Main 메서드  
 C# 콘솔 응용 프로그램에는 시작 및 끝을 제어하는 `Main` 메서드가 포함되어야 합니다. `Main` 메서드에서 개체를 만들고 다른 메서드를 실행합니다.  
  
 `Main` 메서드는 클래스나 구조체 내부에 있는 [정적](../../../csharp/language-reference/keywords/static.md) 메서드입니다. 이전 "Hello World!" 예제에서 이 메서드는 `Hello` 클래스에 있습니다. 다음 방법 중 하나로 `Main` 메서드를 선언할 수 있습니다.  
  
-   이 메서드는 `void`를 반환합니다.  
  
     [!code-cs[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_4.cs)]  
  
-   정수를 반환할 수도 있습니다.  
  
     [!code-cs[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_5.cs)]  
  
-   반환 형식은 각각 인수를 사용할 수 있습니다.  
  
     [!code-cs[csProgGuideMain#19](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_6.cs)]  
  
     또는  
  
     [!code-cs[csProgGuideMain#18](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_7.cs)]  
  
 `Main` 메서드의 매개 변수 `args`는 프로그램을 호출하는 데 사용된 명령줄 인수가 포함된 `string` 배열입니다. C++의 경우와는 달리 배열에 실행(exe) 파일의 이름이 포함되지 않습니다.  
  
 명령줄 인수를 사용하는 방법에 대한 자세한 내용은 [Main() 및 명령줄 인수](../../../csharp/programming-guide/main-and-command-args/index.md) 및 [How to: Create and Use Assemblies Using the Command Line](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4)(방법: 명령줄을 사용하여 어셈블리 만들기 및 사용)의 예제를 참조하세요.  
  
 `Main` 메서드가 끝날 때 <xref:System.Console.ReadKey%2A>를 호출하면 프로그램을 디버그 모드에서 실행할 경우 F5 키를 눌러 출력을 읽을 수 있는 기회를 얻기 전에 콘솔 창이 닫히지 않습니다.  
  
## <a name="input-and-output"></a>입력 및 출력  
 일반적으로 C# 프로그램에서는 .NET Framework의 런타임 라이브러리에서 제공되는 입출력 서비스를 사용합니다. `System.Console.WriteLine("Hello World!");` 문에는 <xref:System.Console.WriteLine%2A> 메서드가 사용됩니다. 이 메서드는 런타임 라이브러리에 있는 <xref:System.Console> 클래스의 출력 메서드 중 하나입니다. 이 메서드는 표준 출력 스트림에 문자열 매개 변수를 표시하고 이어서 새 줄을 표시합니다. 기타 <xref:System.Console> 메서드는 다양한 입력 및 출력 작업에 사용할 수 있습니다. 프로그램 시작 부분에 `using System;` 지시문을 포함하면 <xref:System> 클래스 및 메서드를 정규화하지 않고 바로 사용할 수 있습니다. 예를 들어 `System.Console.WriteLine` 대신 `Console.WriteLine`을 호출할 수 있습니다.  
  
 [!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_8.cs)]  
  
 [!code-cs[csProgGuide#23](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_9.cs)]  
  
 입출력 메서드에 대한 자세한 내용은 <xref:System.IO>를 참조하세요.  
  
## <a name="command-line-compilation-and-execution"></a>명령줄 컴파일 및 실행  
 "Hello World!" 프로그램을 컴파일하려면 Visual Studio IDE(통합 개발 환경) 대신 명령줄을 사용합니다.  
  
#### <a name="to-compile-and-run-from-a-command-prompt"></a>명령 프롬프트에서 컴파일 및 실행하려면  
  
1.  이전 절차의 코드를 텍스트 편집기에 붙여넣고 파일을 텍스트 파일로 저장합니다. 파일 이름을 `Hello.cs`로 지정합니다. C# 소스 코드 파일에는 `.cs` 확장명이 사용됩니다.  
  
2.  다음 단계 중 하나를 수행하여 명령 프롬프트 창을 엽니다.  
  
    -   Windows 8의 경우 **시작** 화면에서 `Developer Command Prompt`를 검색하고 **VS2012용 개발자 명령 프롬프트**를 탭하거나 선택합니다.  
  
         개발자 명령 프롬프트 창이 나타납니다.  
  
    -   Windows 7의 경우 **시작** 메뉴를 열고, Visual Studio 현재 버전의 폴더를 확장하고, **Visual Studio Tools**의 바로 가기 메뉴를 열고 나서, **VS2012용 개발자 명령 프롬프트**를 선택합니다.  
  
         개발자 명령 프롬프트 창이 나타납니다.  
  
    -   표준 명령 프롬프트 창에서 명령줄 빌드를 사용하도록 설정합니다.  
  
         [방법: Visual Studio 명령줄에 필요한 환경 변수 설정](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)을 참조하세요.  
  
3.  명령 프롬프트 창에서 `Hello.cs` 파일이 포함된 폴더로 이동합니다.  
  
4.  다음 명령을 입력하여 `Hello.cs`를 컴파일합니다.  
  
     `csc Hello.cs`  
  
     프로그램에 컴파일 오류가 없으면 `Hello.exe`라는 실행 파일이 만들어집니다.  
  
5.  명령 프롬프트 창에서 다음 명령을 입력하여 프로그램을 실행합니다.  
  
     `Hello`  
  
 C# 컴파일러 및 관련 옵션에 대한 자세한 내용은 [C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md)을 참조하세요.
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 프로그램 내부](../../../csharp/programming-guide/inside-a-program/index.md)   
 [문자열](../../../csharp/programming-guide/strings/index.md)   
 [\<paveover>C# 샘플 응용 프로그램](http://msdn.microsoft.com/en-us/9a9d7aaa-51d3-4224-b564-95409b0f3e15)   
 [C# 참조](../../../csharp/language-reference/index.md)   
 [Main()과 명령줄 인수](../../../csharp/programming-guide/main-and-command-args/index.md)   
 [Visual C# 및 Visual Basic 시작](https://docs.microsoft.com/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic)
