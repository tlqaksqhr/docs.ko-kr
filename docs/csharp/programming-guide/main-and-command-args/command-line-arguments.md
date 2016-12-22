---
title: "명령줄 인수(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "명령줄 인수[C#]"
ms.assetid: 0e597e0d-ea7a-41ba-a38a-0198122f3c26
caps.latest.revision: 27
caps.handback.revision: 27
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 명령줄 인수(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

다음 방법 중 하나로 메서드를 정의하여 인수를 `Main` 메서드에 보낼 수 있습니다.  
  
 [!code-cs[csProgGuideMain#2](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/command-line-arguments_1.cs)]  
  
 [!code-cs[csProgGuideMain#3](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/command-line-arguments_2.cs)]  
  
> [!NOTE]
>  Windows Forms 응용 프로그램의 `Main` 메서드에서 명령줄 인수를 사용하려면 program.cs에서 `Main` 시그니처를 직접 수정해야 합니다.  Windows Forms 디자이너에서 생성된 코드에서는 입력 매개 변수가 없는 상태로 `Main`을 만듭니다.  또한 <xref:System.Environment.CommandLine%2A?displayProperty=fullName> 또는 <xref:System.Environment.GetCommandLineArgs%2A?displayProperty=fullName>를 사용하여 콘솔 또는 Windows 응용 프로그램에서 언제든지 명령줄 인수에 액세스할 수 있습니다.  
  
 `Main` 메서드의 매개 변수는 명령줄 인수를 나타내는 <xref:System.String> 배열입니다.  일반적으로 다음 예제와 같이 `Length` 속성을 테스트하여 인수가 있는지 확인합니다.  
  
 [!code-cs[csProgGuideMain#4](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/command-line-arguments_3.cs)]  
  
 또한 <xref:System.Convert> 클래스나 `Parse` 메서드를 사용하여 문자열 인수를 숫자 형식으로 변환할 수 있습니다.  예를 들어 다음 문에서는 <xref:System.Int64.Parse%2A> 메서드를 사용하여 `string`을 `long` 숫자로 변환합니다.  
  
```  
long num = Int64.Parse(args[0]);  
```  
  
 또한 `Int64`의 별칭인 C\#의 `long` 형식을 사용할 수도 있습니다.  
  
```  
long num = long.Parse(args[0]);  
```  
  
 또한 `Convert` 클래스 메서드 `ToInt64`를 사용할 수도 있습니다.  
  
```  
long num = Convert.ToInt64(s);  
```  
  
 자세한 내용은 <xref:System.Int64.Parse%2A> 및 <xref:System.Convert>을 참조하십시오.  
  
## 예제  
 다음 예제에서는 콘솔 응용 프로그램에서 명령줄 인수를 사용하는 방법을 보여 줍니다.  이 응용 프로그램에서는 런타임에 하나의 인수를 받아들여 해당 인수를 정수로 변환하며 숫자의 계승을 계산합니다.  인수를 제공하지 않으면 응용 프로그램에서 올바른 사용법을 설명하는 메시지를 표시합니다.  
  
 명령 프롬프트에서 응용 프로그램을 컴파일 및 실행하려면 다음과 같이 하십시오.  
  
1.  모든 텍스트 편집기에 다음 코드를 붙여 넣고 해당 파일을 이름이 `Factorial.cs`인 텍스트 파일로 저장합니다.  
  
     [!code-cs[csProgGuideMain#16](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/command-line-arguments_4.cs)]  
  
2.  **시작** 화면 또는 **시작** 메뉴에서 Visual Studio **개발자 명령 프롬프트** 창을 연 다음 방금 만든 파일이 포함되어 있는 폴더로 이동합니다.  
  
3.  다음 명령을 입력하여 응용 프로그램을 컴파일러합니다.  
  
     `csc Factorial.cs`  
  
     응용 프로그램에 컴파일 오류가 없으면 `Factorial.exe`라는 실행 파일이 만들어집니다.  
  
4.  다음 명령을 입력하여 3의 팩토리얼을 계산합니다.  
  
     `Factorial 3`  
  
5.  명령은 다음과 같은 출력을 생성합니다.`The factorial of 3 is 6.`  
  
> [!NOTE]
>  Visual Studio에서 응용 프로그램을 실행할 때 [프로젝트 디자이너, 디버그 페이지](/visual-studio/ide/reference/debug-page-project-designer)에서 명령줄 인수를 지정할 수 있습니다.  
  
 명령줄 인수 사용 방법에 대한 예제를 좀 더 보려면 [방법: 명령줄을 사용하여 어셈블리 만들기 및 사용](../Topic/How%20to:%20Create%20and%20Use%20Assemblies%20Using%20the%20Command%20Line%20\(C%23%20and%20Visual%20Basic\).md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Environment?displayProperty=fullName>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [Main\(\)과 명령줄 인수](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md)   
 [방법: 명령줄 인수 표시](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)   
 [방법: foreach를 사용하여 명령줄 인수 액세스](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)   
 [Main\(\) 반환 값](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)   
 [클래스](../../../csharp/programming-guide/classes-and-structs/classes.md)