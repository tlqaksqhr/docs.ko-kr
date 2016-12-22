---
title: "try-finally(C# 참조) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "finally"
  - "finally_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "finally 키워드[C#]"
  - "try-finally 문[C#]"
ms.assetid: c27623fb-7261-4464-862c-7a369d3c8f0a
caps.latest.revision: 25
caps.handback.revision: 25
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# try-finally(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`finally` 블록을 사용하여 [try](../../../csharp/language-reference/keywords/try-catch.md) 블록에 할당된 리소스를 정리하고 `try` 블록에 예외가 발생하더라도 코드를 실행할 수 있습니다.  일반적으로 컨트롤이 `try` 문을 나갈 때 `finally` 블록 문이 실행됩니다.  컨트롤 전송은 일반 실행, `break`, `continue`, `goto` 또는 `return` 문 실행 또는 `try` 문에서 예외 전파의 결과로 발생할 수 있습니다.  
  
 처리된 예외 안에서는 연결된 `finally` 블록이 반드시 실행됩니다.  그러나 예외가 처리되지 않은 경우 `finally` 블록은 예외 해제 작업이 트리거되는 방법에 따라 다르게 실행됩니다.  이것도 컴퓨터 설정 방법에 따라 다릅니다.  자세한 내용은 [Unhandled Exception Processing in the CLR](http://go.microsoft.com/fwlink/?LinkId=128371)을 참조하십시오.  
  
 일반적으로 처리되지 않은 예외로 응용 프로그램이 종료되면 `finally` 블록의 실행 여부는 중요하지 않습니다.  그러나 이러한 상황에서도 실행되어야 하는 `finally` 블록의 문이 있는 경우 하나의 솔루션은 `catch` 블록을 `try`\-`finally` 문에 추가하는 것입니다.  또는 높은 호출 스택에 있는 `try`\-`finally`의 `try` 블록에서 throw될 수 있는 예외를 catch할 수 있습니다.  `try`\-`finally` 문이 포함된 메서드를 호출하는 메서드에서, 이 메서드를 호출하는 메서드에서 또는 호출 스택의 모든 메서드에서 예외를 catch할 수 있습니다.  예외가 catch되지 않는 경우 `finally` 블록은 운영 체제에서 예외 해제 작업을 트리거하도록 선택하는지 여부에 따라 다르게 실행됩니다.  
  
## 예제  
 아래 예제에서는 잘못된 변환문이 `System.InvalidCastException` 예외를 발생시킵니다.  예외는 처리되지 않습니다.  
  
 [!code-cs[csrefKeywordsExceptions#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_1.cs)]  
  
 다음 예에서 `TryCast` 메서드 예외는 메서드에서 호출 스택까지 catch됩니다.  
  
 [!code-cs[csrefKeywordsExceptions#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_2.cs)]  
  
 `finally`에 대한 자세한 내용은 [try\-catch\-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)를 참조하십시오.  
  
 C\#에는 [using 문](../../../visual-basic/language-reference/statements/using-statement.md)도 포함됩니다. 이 문은 간편한 구문에서 <xref:System.IDisposable> 개체에 대해 비슷한 기능을 제공합니다.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [Try, Throw 및 Catch 문\(C\+\+\)](/visual-cpp/cpp/try-throw-and-catch-statements-cpp)   
 [예외 처리문](../../../csharp/language-reference/keywords/exception-handling-statements.md)   
 [throw](../../../csharp/language-reference/keywords/throw.md)   
 [try\-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [방법: 명시적으로 예외 Throw](../Topic/How%20to:%20Explicitly%20Throw%20Exceptions.md)