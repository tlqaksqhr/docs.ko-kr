---
title: "Hello World -- 프로그램 처음 만들기(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
f1_keywords: 
  - "cs.program"
  - "vs.csharp.startpage.firstapplication"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "예제[C#], Hello World"
  - "Hello World 예제[C#]"
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
caps.latest.revision: 39
caps.handback.revision: 39
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Hello World -- 프로그램 처음 만들기(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

다음 절차는 전통적인 "Hello World\!" 프로그램의 C\# 버전을 만듭니다.  프로그램이 문자열 `Hello World!`를 표시합니다.  
  
 소개 개념의 다른 예제를 보려면 [Visual C\# 및 Visual Basic 시작](/visual-studio/ide/getting-started-with-visual-csharp-and-visual-basic)를 참조하십시오.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### 콘솔 응용 프로그램을 만들고 실행하려면  
  
1.  Visual Studio를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 선택합니다.  
  
     **새 프로젝트** 대화 상자가 열립니다.  
  
3.  **설치됨**, **템플릿** 및 **Visual C\#**를 차례로 확장한 다음 **콘솔 응용 프로그램**을 선택합니다.  
  
4.  **이름** 상자에 프로젝트 이름을 지정한 다음 **확인** 단추를 선택합니다.  
  
     **솔루션 탐색기**에 새 프로젝트가 나타납니다.  
  
5.  **코드 편집기**에서 Program.cs가 열리지 않는 경우 **솔루션 탐색기**에서 **Program.cs**에 대한 바로 가기 메뉴를 연 다음 **코드 보기**를 선택합니다.  
  
6.  Program.cs의 내용을 다음 코드로 바꿉니다.  
  
     [!code-cs[csProgGuide#21](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_1.cs)]  
  
7.  F5 키를 선택하여 프로젝트를 실행합니다.  `Hello World!` 줄을 포함하는 명령 프롬프트 창이 나타납니다.  
  
 그런 다음, 이 프로그램에서 중요한 부분이 검토됩니다.  
  
## 설명  
 첫째 행에 주석이 있습니다.  `//` 문자는 행의 나머지 부분을 주석으로 변환합니다.  
  
 [!code-cs[csProgGuide#32](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_2.cs)]  
  
 또한 다음 예제와 같이 `/*`와 `*/` 문자 사이에 텍스트를 포함시켜 텍스트 블록을 주석으로 만들 수 있습니다.  다음 예제에서 이를 확인할 수 있습니다.  
  
 [!code-cs[csProgGuide#33](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_3.cs)]  
  
## Main 메서드  
 C\# 콘솔 응용 프로그램에는 시작과 끝을 제어하는 `Main` 메서드가 있어야 합니다.  `Main` 메서드에서는 개체를 생성하고 다른 메서드를 실행합니다.  
  
 `Main` 메서드는 클래스 또는 구조체 내부에 있는 [static](../../../csharp/language-reference/keywords/static.md) 메서드입니다.  이전의 "Hello World\!" 예제에서는 `Hello`라는 클래스에 이 메서드가 있습니다.  다음 중 한 가지 방법으로 `Main` 메서드를 선언할 수 있습니다.  
  
-   `void`를 반환합니다.  
  
     [!code-cs[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_4.cs)]  
  
-   또는 정수를 반환할 수 있습니다.  
  
     [!code-cs[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_5.cs)]  
  
-   반환 형식 중 하나에서 인수를 취할 수 있습니다.  
  
     [!code-cs[csProgGuideMain#19](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_6.cs)]  
  
     또는  
  
     [!code-cs[csProgGuideMain#18](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_7.cs)]  
  
 `Main` 메서드 `args`의 매개 변수는 프로그램을 호출하는 데 사용되는 명령줄 인수를 포함하는 `string` 배열입니다.  C\+\+와 달리 이 배열에는 실행 파일\(.exe\)의 이름이 포함되지 않습니다.  
  
 명령줄 인수를 사용하는 방법에 대한 자세한 내용은 [Main\(\)과 명령줄 인수](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md) 및 [방법: 명령줄을 사용하여 어셈블리 만들기 및 사용](../Topic/How%20to:%20Create%20and%20Use%20Assemblies%20Using%20the%20Command%20Line%20\(C%23%20and%20Visual%20Basic\).md)에 나와 있는 예제를 참조하십시오.  
  
 `Main` 메서드 끝에 있는 <xref:System.Console.ReadKey%2A> 호출은 F5 키를 눌러 디버그 모드에서 프로그램을 실행할 때 출력 결과를 읽기 전에 콘솔 창이 닫히는 것을 방지합니다.  
  
## 입력 및 출력  
 C\# 프로그램에서는 일반적으로 .NET Framework의 런타임 라이브러리가 제공하는 입출력 서비스를 사용합니다.  `System.Console.WriteLine("Hello World!");` 문에서는 <xref:System.Console.WriteLine%2A> 메서드를 사용합니다.  이 런타임 라이브러리에서 <xref:System.Console> 클래스의 출력 방법 중 하나입니다.  이 메서드에서는 문자열 매개 변수를 표준 출력 스트림에 표시한 다음 줄 바꿈을 합니다.  다른 <xref:System.Console> 메서드는 다양한 입출력 작업에 사용할 수 있습니다.  프로그램 시작 부분에 `using System;` 지시문을 포함하면 <xref:System> 클래스와 메서드를 정규화하지 않고 직접 사용할 수 있습니다.  예를 들어, `System.Console.WriteLine` 대신 `Console.WriteLine`을 호출할 수 있습니다.  
  
 [!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_8.cs)]  
  
 [!code-cs[csProgGuide#23](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_9.cs)]  
  
 입출력 메서드에 대한 자세한 내용은 <xref:System.IO>를 참조하십시오.  
  
## 명령줄 컴파일 및 실행  
 Visual Studio IDE\(통합 개발 환경\) 대신 명령줄을 사용하여 "Hello, World\!" 프로그램을 컴파일할 수 있습니다.  
  
#### 명령 프롬프트에서 컴파일하고 실행하려면  
  
1.  모든 텍스트 편집기에 이전 절차에서 표시된 코드를 붙여 넣고 해당 파일을 텍스트 파일로 저장합니다.  파일 `Hello.cs`의 이름을 지정합니다.  C\# 소스 코드 파일은 `.cs` 확장명을 사용합니다.  
  
2.  명령 프롬프트 창을 열려면 다음 중 한 가지 단계를 수행하십시오.  
  
    -   Windows 8 의 **시작** 화면에서, `개발자 명령 프롬프트`를 검색하고 나서 **VS2012용 개발자 명령 프롬프트**를 탭하거나 선택합니다.  
  
         개발자 명령 프롬프트 창이 나타납니다.  
  
    -   Windows 7에서 **Start** 메뉴를 열고, 최신 버전의 Visual Studio 폴더를 확장하고, **Visual Studio Tools** 바로 가기 메뉴를 열고 나서 **VS2012 Developer Command Prompt**를 선택합니다.  
  
         개발자 명령 프롬프트 창이 나타납니다.  
  
    -   표준 명령 프롬프트 창에서 명령줄 빌드를 활성화합니다.  
  
         자세한 내용은 [How to: Set Environment Variables for the Visual Studio Command Line](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)를 참조하십시오.  
  
3.  명령 프롬프트 창에서 `Hello.cs` 파일이 들어 있는 폴더로 이동합니다.  
  
4.  다음 명령을 입력하여 `Hello.cs`를 컴파일합니다.  
  
     `csc Hello.cs`  
  
     프로그램에 컴파일 오류가 없으면 `Hello.exe`라는 실행 파일이 만들어집니다.  
  
5.  명령 프롬프트 창에서 다음 명령을 입력하여 프로그램을 실행합니다.  
  
     `Hello`  
  
 C\# 컴파일러 및 해당 옵션에 대한 자세한 내용은 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)를 참조하십시오.  
  
## 중요 설명서 장  
 [Visual C\# 2010 시작](http://go.microsoft.com/fwlink/?LinkId=221214)의 [C\# 프로그램 작성](http://go.microsoft.com/fwlink/?LinkId=221227)  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 프로그램 내부](../../../csharp/programming-guide/inside-a-program/index.md)   
 [문자열](../../../csharp/programming-guide/strings/index.md)   
 [\<paveover\>C\# Sample Applications](http://msdn.microsoft.com/ko-kr/9a9d7aaa-51d3-4224-b564-95409b0f3e15)   
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [Main\(\)과 명령줄 인수](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md)   
 [Visual C\# 및 Visual Basic 시작](/visual-studio/ide/getting-started-with-visual-csharp-and-visual-basic)