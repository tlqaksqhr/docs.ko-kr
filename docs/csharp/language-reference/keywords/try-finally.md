---
title: try-finally(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- finally
- finally_CSharpKeyword
helpviewer_keywords:
- finally keyword [C#]
- try-finally statement [C#]
ms.assetid: c27623fb-7261-4464-862c-7a369d3c8f0a
ms.openlocfilehash: 696eb531fe3e340f7fe0ae12483648119cf5a7eb
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925181"
---
# <a name="try-finally-c-reference"></a>try-finally(C# 참조)
`finally` 블록을 사용하면 [try](../../../csharp/language-reference/keywords/try-catch.md) 블록에서 할당된 리소스를 정리할 수 있으며, `try` 블록에서 예외가 발생하는 경우에도 코드를 실행할 수 있습니다. 일반적으로 `finally` 블록의 문은 제어가 `try` 문을 벗어날 때 실행됩니다. 제어 전송은 정상적인 실행 결과, `break`, `continue`, `goto` 또는 `return` 문의 실행 결과 또는 `try` 문에서 예외 전파의 결과로 발생할 수 있습니다.  
  
 처리된 예외 내에서는 연결된 `finally` 블록이 항상 실행됩니다. 그러나 예외가 처리되지 않은 경우 `finally` 블록의 실행 여부는 예외 해제 작업의 트리거 방법에 따라 달라집니다. 트리거 방법은 다시 사용자 컴퓨터의 설정 방법에 따라 달라집니다.
  
 일반적으로 처리되지 않은 예외로 응용 프로그램이 종료되는 경우 `finally` 블록의 실행 여부는 중요하지 않습니다. 그러나 해당 상황에서도 실행해야 하는 문이 `finally` 블록에 있는 경우 한 가지 솔루션은 `catch` 블록을 `try`-`finally` 문에 추가하는 것입니다. 또는 호출 스택에서 상위 `try`-`finally` 문의 `try` 블록에 throw될 수 있는 예외를 catch할 수 있습니다. 즉, `try`-`finally` 문을 포함하는 메서드를 호출하는 메서드, 해당 메서드를 호출하는 메서드 또는 호출 스택의 임의 메서드에 예외를 catch할 수 있습니다. 예외가 catch되지 않는 경우 `finally`의 실행은 운영 체제에서 예외 해제 작업 트리거를 선택하는지 여부에 따라 달라집니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 잘못된 변환 문으로 인해 `System.InvalidCastException` 예외가 발생합니다. 예외가 처리되지 않습니다.  
  
 [!code-csharp[csrefKeywordsExceptions#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_1.cs)]  
  
 다음 예제에서는 `TryCast` 메서드의 예외가 호출 스택의 위에 있는 메서드에서 catch됩니다.  
  
 [!code-csharp[csrefKeywordsExceptions#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_2.cs)]  
  
 `finally`에 대한 자세한 내용은 [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)를 참조하세요.  
  
 C#에는 <xref:System.IDisposable> 개체에 대한 유사한 기능을 편리한 구문으로 제공하는 [using 문](../../../csharp/language-reference/keywords/using-statement.md)도 포함되어 있습니다.  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)  
 [try, throw 및 catch 문(C++)](/cpp/cpp/try-throw-and-catch-statements-cpp)  
 [예외 처리 문](../../../csharp/language-reference/keywords/exception-handling-statements.md)  
 [throw](../../../csharp/language-reference/keywords/throw.md)  
 [try-catch](../../../csharp/language-reference/keywords/try-catch.md)  
 [방법: 명시적으로 예외 Throw](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
