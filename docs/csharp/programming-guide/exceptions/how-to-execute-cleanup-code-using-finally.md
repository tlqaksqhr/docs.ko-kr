---
title: "방법: finally를 사용하여 정리 코드 실행(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "예외 처리[C#], try/finally 블록"
  - "예외[C#], try/finally 블록"
  - "try/finally 블록[C#]"
ms.assetid: 1b1e5aef-3f32-4a88-9d39-b5fffb33bdaf
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# 방법: finally를 사용하여 정리 코드 실행(C# 프로그래밍 가이드)
`finally` 문의 목적은 예외가 throw되더라도 개체에 필요한 정리 작업을 즉시 수행하는 데 있습니다. 이러한 개체는 일반적으로 외부 리소스를 사용하는 개체입니다.  이러한 정리 작업의 예로는 다음과 같이 공용 언어 런타임에 의해 개체가 가비지 수집되기를 기다리는 대신 사용 직후에 <xref:System.IO.FileStream>에 대해 <xref:System.IO.Stream.Close%2A>를 호출하는 경우를 들 수 있습니다.  
  
 [!code-cs[csProgGuideExceptions#16](../../../csharp/programming-guide/exceptions/codesnippet/csharp/how-to-execute-cleanup-c_1.cs)]  
  
## 예제  
 위 코드를 `try-catch-finally` 문으로 변환하려면 다음과 같이 정리 코드를 작업 코드와 분리해야 합니다.  
  
 [!code-cs[csProgGuideExceptions#17](../../../csharp/programming-guide/exceptions/codesnippet/csharp/how-to-execute-cleanup-c_2.cs)]  
  
 `OpenWrite()` 호출 이전에 `try` 블록 내에서 언제든지 예외가 발생할 수 있고 `OpenWrite()` 호출 자체가 실패할 수도 있으므로 파일을 닫으려고 할 때 해당 파일이 열려 있으리라는 보장이 없습니다.  `finally` 블록은 사용자가 <xref:System.IO.Stream.Close%2A> 메서드를 호출하기 전에 <xref:System.IO.FileStream> 개체가 `null`이 아닌지 확인하기 위한 검사를 추가합니다.  `null` 검사를 수행하지 않으면 `finally` 블록에서 자체적으로 <xref:System.NullReferenceException>을 throw할 수 있습니다. `finally` 블록에서 예외가 throw되는 경우는 가능한 한 피해야 합니다.  
  
 `finally` 블록에서 닫을 수 있는 또 다른 후보 중 하나로는 데이터베이스 연결이 있습니다.  데이터베이스 서버에 대해 허용된 연결의 수는 제한될 수 있으므로 가능한 한 빨리 데이터베이스 연결을 닫아야 합니다.  연결을 닫기 전에 예외가 throw되면 이 경우에도 가비지 수집을 기다리는 것보다 `finally` 블록을 사용하는 것이 좋습니다.  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [예외 및 예외 처리](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md)   
 [예외 처리](../../../csharp/programming-guide/exceptions/exception-handling.md)   
 [using 문](../../../csharp/language-reference/keywords/using-statement.md)   
 [try\-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [try\-finally](../../../csharp/language-reference/keywords/try-finally.md)   
 [try\-catch\-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)