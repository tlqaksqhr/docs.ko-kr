---
title: "Main() 및 명령줄 인수(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- CS5001
- main_CSharpKeyword
- Main
dev_langs:
- CSharp
helpviewer_keywords:
- Main method [C#]
- C# language, command-line arguments
- arguments [C#], command-line
- command line [C#], arguments
- command-line arguments [C#], Main method
ms.assetid: 73a17231-cf96-44ea-aa8a-54807c6fb1f4
caps.latest.revision: 30
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
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: eb1d380ee4dfd64081d8fe36880a06e3a450f639
ms.contentlocale: ko-kr
ms.lasthandoff: 05/26/2017

---
<a id="main-and-command-line-arguments-c-programming-guide" class="xliff"></a>

# Main()과 명령줄 인수(C# 프로그래밍 가이드)
`Main` 메서드는 C# 콘솔 응용 프로그램 또는 Windows 응용 프로그램의 진입점입니다. (라이브러리와 서비스에는 `Main` 메서드가 진입점으로 필요하지 않습니다.) 응용 프로그램이 시작될 때 `Main` 메서드는 호출되는 첫 번째 메서드입니다.  
  
 C# 프로그램에는 하나의 진입점만 있을 수 있습니다. `Main` 메서드가 있는 클래스가 둘 이상 있는 경우 **/main** 컴파일러 옵션으로 프로그램을 컴파일하여 진입점으로 사용할 `Main` 메서드를 지정해야 합니다. 자세한 내용은 [/main(C# 컴파일러 옵션)](../../../csharp/language-reference/compiler-options/main-compiler-option.md)을 참조하세요.  
  
 [!code-cs[csProgGuideMain#17](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-and-command-line-arguments_1.cs)]  
  
<a id="overview" class="xliff"></a>

## 개요  
  
-   `Main` 메서드는 .exe 프로그램의 진입점으로, 프로그램의 제어가 시작되고 끝나는 위치합니다.  
  
-   `Main`은 클래스 또는 구조체 내부에 선언됩니다 `Main`은 [정적](../../../csharp/language-reference/keywords/static.md)이어야 하며 [공용](../../../csharp/language-reference/keywords/public.md)이어서는 안 됩니다. (앞의 예제에서는 기본 액세스 권한 [개인](../../../csharp/language-reference/keywords/private.md)을 받습니다.) 바깥쪽 클래스 또는 구조체는 정적일 필요가 없습니다.  
  
-   `Main`은 `void` 또는 `int` 반환 형식을 가질 수 있습니다.  
  
-   `Main` 메서드는 명령줄 인수를 포함하는 `string[]` 매개 변수 사용 여부에 관계 없이 선언될 수 있습니다. [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]를 사용하여 Windows Forms 응용 프로그램을 만드는 경우 매개 변수를 수동으로 추가하거나 <xref:System.Environment> 클래스를 사용하여 명령줄 인수를 얻을 수 있습니다. 매개 변수는 0부터 시작하는 명령줄 인수로 읽힙니다. C 및 C++와 달리 프로그램의 이름이 첫 번째 명령줄 인수로 처리되지 않습니다.  
  
<a id="in-this-section" class="xliff"></a>

## 단원 내용  
  
-   [명령줄 인수](../../../csharp/programming-guide/main-and-command-args/command-line-arguments.md)  
  
-   [방법: 명령줄 인수 표시](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)  
  
-   [방법: foreach를 사용하여 명령줄 인수 액세스](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)  
  
-   [Main() 반환 값](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)  
  
<a id="c-language-specification" class="xliff"></a>

## C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
<a id="see-also" class="xliff"></a>

## 참고 항목  
 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [메서드](../../../csharp/programming-guide/classes-and-structs/methods.md)   
 [C# 프로그램 내부](../../../csharp/programming-guide/inside-a-program/index.md)   
 [\<paveover>C# 샘플 응용 프로그램](http://msdn.microsoft.com/en-us/9a9d7aaa-51d3-4224-b564-95409b0f3e15)
