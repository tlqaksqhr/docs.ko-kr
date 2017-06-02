---
title: "예외 및 예외 처리(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- exception handling [C#]
- exceptions [C#]
- C# language, exceptions
ms.assetid: 0001887f-4fa2-47e2-8034-2819477e2344
caps.latest.revision: 33
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
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 561113241f7433d8e0f7f1f1f96f0338ebe81ae3
ms.contentlocale: ko-kr
ms.lasthandoff: 05/10/2017

---
# <a name="exceptions-and-exception-handling-c-programming-guide"></a>예외 및 예외 처리(C# 프로그래밍 가이드)
C# 언어의 예외 처리 기능은 프로그램이 실행 중일 때 발생하는 예기치 않은 문제나 예외 상황을 처리하는 데 도움이 됩니다. 예외 처리는 `try`, `catch` 및 `finally` 키워드를 사용하여 실패했을 수 있는 작업을 시도하고, 실패를 처리하는 것이 적절하다고 판단될 때 처리하고, 리소스를 정리합니다. 예외는 CLR(공용 언어 런타임), .NET Framework, 타사 라이브러리 또는 응용 프로그램 코드에서 생성될 수 있습니다. 예외는 `throw` 키워드를 사용하여 생성됩니다.  
  
 대부분의 경우 코드에서 직접 호출한 메서드가 아니라 호출 스택에서 추가로 작동 중단된 다른 메서드에 의해 예외가 throw될 수 있습니다. 이 경우 CLR에서는 스택을 해제하고 특정 예외 형식에 대해 `catch` 블록이 있는 메서드를 찾은 다음 이러한 `catch` 블록을 먼저 실행합니다. 호출 스택에서 적절한 `catch` 블록을 찾지 못하면 프로세스를 종료하고 사용자에게 메시지를 표시합니다.  
  
 이 예제에서 메서드는 0으로 나누기를 테스트하고 오류를 catch합니다. 예외 처리를 사용하지 않을 경우 이 프로그램은 **DivideByZeroException이(가) 처리되지 않았습니다.** 오류를 나타내며 종료됩니다.  
  
 [!code-cs[csProgGuideExceptions#18](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exceptions-and-exception-handling_1.cs)]  
  
## <a name="exceptions-overview"></a>예외 개요  
 예외는 다음과 같은 속성을 갖습니다.  
  
-   모든 예외는 궁극적으로 `System.Exception`에서 파생되는 형식입니다.  
  
-   예외를 throw할 수 있는 문 주위에 `try` 블록을 사용합니다.  
  
-   `try` 블록에서 예외가 발생하면 제어 흐름이 호출 스택에 있는 첫 번째 관련 예외 처리기로 이동됩니다. C#에서 `catch` 키워드는 예외 처리기를 정의하는 데 사용됩니다.  
  
-   지정된 예외에 대한 예외 처리기가 없으면 프로그램은 오류 메시지를 나타내며 실행을 중지합니다.  
  
-   예외를 처리하고 응용 프로그램을 알려진 상태로 둘 수 없으면 예외를 catch하지 마세요. `System.Exception`을 catch하는 경우 `catch` 블록 끝에서 `throw` 키워드를 사용하여 다시 throw하세요.  
  
-   `catch` 블록이 예외 변수를 정의하는 경우 이 변수를 사용하여 발생한 예외 형식에 대한 추가 정보를 얻을 수 있습니다.  
  
-   `throw` 키워드를 사용하여 프로그램에서 명시적으로 예외를 생성할 수 있습니다.  
  
-   예외 개체는 호출 스택의 상태 및 오류에 대한 텍스트 설명 같은 오류에 대한 자세한 정보를 포함합니다.  
  
-   `finally` 블록의 코드는 예외가 throw되더라도 실행됩니다. `finally` 블록을 사용하여 `try` 블록에서 열려 있는 스트림이나 파일을 닫는 것처럼 리소스를 해제합니다.  
  
-   .NET Framework의 관리되는 예외는 Win32 구조적 예외 처리 메커니즘을 토대로 구현됩니다. 자세한 내용은 [구조적 예외 처리(C/C++)](https://docs.microsoft.com/cpp/cpp/structured-exception-handling-c-cpp) 및 [Win32 구조적 예외 처리에 대한 집중 과정](http://go.microsoft.com/fwlink/?LinkId=119654)을 참조하세요.  
  
## <a name="related-sections"></a>관련 단원  
 예외 및 예외 처리에 대한 자세한 내용은 다음 항목을 참조하세요.  
  
-   [예외 사용](../../../csharp/programming-guide/exceptions/using-exceptions.md)  
  
-   [예외 처리](../../../csharp/programming-guide/exceptions/exception-handling.md)  
  
-   [예외 만들기 및 Throw](../../../csharp/programming-guide/exceptions/creating-and-throwing-exceptions.md)  
  
-   [컴파일러 생성 예외](../../../csharp/programming-guide/exceptions/compiler-generated-exceptions.md)  
  
-   [방법: try/catch를 사용하여 예외 처리(C# 프로그래밍 가이드)](../../../csharp/programming-guide/exceptions/how-to-handle-an-exception-using-try-catch.md)  
  
-   [방법: finally를 사용하여 정리 코드 실행](../../../csharp/programming-guide/exceptions/how-to-execute-cleanup-code-using-finally.md)  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.SystemException>   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [throw](../../../csharp/language-reference/keywords/throw.md)   
 [try-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [try-finally](../../../csharp/language-reference/keywords/try-finally.md)   
 [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)   
 [예외](../../../standard/exceptions/index.md)   
 [예외 계층](http://msdn.microsoft.com/library/f7d68675-be06-40fb-a555-05f0c5a6f66b)   
 [안정적인 .NET 코드 작성](http://go.microsoft.com/fwlink/?LinkId=112400)   
 [특정 예외에 대한 미니덤프](http://go.microsoft.com/fwlink/?LinkId=112408)
