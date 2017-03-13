---
title: "예외 처리(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "예외 처리[C#], 예외 처리 정보"
  - "예외[C#], 처리"
ms.assetid: b4e4ecf2-b907-4e58-891f-2563762258e9
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# 예외 처리(C# 프로그래밍 가이드)
[try](../../../csharp/language-reference/keywords/try-catch.md) 블록은 C\# 프로그래머가 예외의 영향을 받을 수 있는 코드를 분할하는 데 사용됩니다.  관련 [catch](../../../csharp/language-reference/keywords/try-catch.md) 블록은 예외 결과를 처리하는 데 사용됩니다.  [finally](../../../csharp/language-reference/keywords/try-finally.md) 블록에는 `try` 블록에 할당된 리소스의 해제 같이 `try` 블록에서 예외가 throw되는지 여부에 관계 없이 실행되는 코드가 포함되어 있습니다.  `try` 블록에서는 하나 이상의 관련 `catch` 블록이나 `finally` 블록, 또는 두 블록 모두를 필요로 합니다.  
  
 다음 예제는 `try-catch` 문, `try-finally` 문 및 `try-catch-finally` 문을 보여 줍니다.  
  
 [!code-cs[csProgGuideExceptions#6](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_1.cs)]  
  
 [!code-cs[csProgGuideExceptions#7](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_2.cs)]  
  
 [!code-cs[csProgGuideExceptions#8](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_3.cs)]  
  
 `catch` 또는 `finally` 블록이 없는 `try` 블록으로 인해 컴파일러 오류가 발생합니다.  
  
## catch 블록  
 `catch` 블록에서는 catch할 예외 형식을 지정할 수 있습니다.  형식 사양을 *예외 필터*라고 합니다.  예외 형식은 <xref:System.Exception>에서 파생되어야 합니다.  일반적으로, `try` 블록에서 throw될 수 있는 모든 예외를 처리하는 방법을 명확히 알고 있거나 `catch` 블록의 끝에 [throw](../../../csharp/language-reference/keywords/throw.md) 문을 포함하는 경우가 아니라면 <xref:System.Exception>을 예외 필터로 지정해서는 안 됩니다.  
  
 예외 필터가 서로 다른 여러 개의 `catch` 블록을 함께 연결할 수 있습니다.  `catch` 블록이 코드 내 위에서 아래 순으로 계산되지만 throw된 각 예외에 대해서는 `catch` 블록이 하나만 실행됩니다.  throw된 예외의 정확한 형식이나 기본 클래스를 지정하는 첫 번째 `catch` 블록이 실행됩니다.  일치하는 예외 필터를 지정하는 `catch` 블록이 없는 경우 문에 블록이 표시된 경우 필터가 없는 `catch` 블록이 선택됩니다.  `catch` 블록은 가장 구체적인, 즉 가장 많이 파생되는 예외 형식에 먼저 배치해야 합니다.  
  
 다음 조건에 해당되면 예외를 catch해야 합니다.  
  
-   이제 예외가 throw될 수 있는 이유에 대해 올바르게 이해했으며 <xref:System.IO.FileNotFoundException> 개체를 catch할 때 새 파일 이름을 입력하라는 메시지가 표시되는 경우와 같이 상황에 맞게 적절한 복구를 구현할 수 있습니다.  
  
-   더 구체적인 새 예외를 만들고 throw할 수 있는 경우입니다.  
  
     [!code-cs[csProgGuideExceptions#9](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_4.cs)]  
  
-   추가 처리를 위해 전달하기 전에 예외를 부분적으로 처리합니다.  다음 예제에서 `catch` 블록은 예제를 다시 throw하기 전에 오류 로그에 항목을 추가하는 데 사용됩니다.  
  
     [!code-cs[csProgGuideExceptions#10](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_5.cs)]  
  
## finally 블록  
 `finally` 블록에서는 `try` 블록에서 수행되는 작업을 정리할 수 있습니다.  `finally` 블록이 있는 경우 이 블록은 `try` 및 일치하는 모든 `catch` 블록을 실행한 후에 마지막으로 실행됩니다.  `finally` 블록은 예외가 throw되었는지 여부나 예외 형식이 일치하는 `catch` 블록을 찾았는지 여부와 상관없이 항상 실행됩니다.  
  
 `finally` 블록을 사용하면 런타임에 가비지 수집기가 개체를 종료할 때까지 기다리지 않고도 파일 스트림, 데이터베이스 연결, 그래픽 핸들 등의 리소스를 해제할 수 있습니다.  자세한 내용은 [using 문](../../../csharp/language-reference/keywords/using-statement.md)를 참조하십시오.  
  
 다음 예제에서 `finally` 블록은 `try` 블록에 열려 있는 파일을 닫는 데 사용됩니다.  파일을 닫기 전에 파일 핸들의 상태를 검사합니다.  `try` 블록에서 파일을 열 수 없는 경우 파일 핸들에는 `null` 값이 여전히 있으며 `finally` 블록을 닫기 위한 시도를 하지 않습니다.  또는 `try` 블록에서 파일이 성공적으로 열린 경우 `finally` 블록은 열린 파일을 닫습니다.  
  
 [!code-cs[csProgGuideExceptions#11](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_6.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [예외 및 예외 처리](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md)   
 [try\-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [try\-finally](../../../csharp/language-reference/keywords/try-finally.md)   
 [try\-catch\-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)   
 [using 문](../../../csharp/language-reference/keywords/using-statement.md)