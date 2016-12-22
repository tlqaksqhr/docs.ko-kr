---
title: "방법: try/catch를 사용하여 예외 처리(C# 프로그래밍 가이드) | Microsoft Docs"
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
  - "예외 처리[C#], try/catch 블록"
  - "예외[C#], try/catch 블록"
  - "try/catch 블록[C#]"
ms.assetid: ca8e3773-980e-4767-8633-7408540e9818
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 방법: try/catch를 사용하여 예외 처리(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

[try\-catch](../../../csharp/language-reference/keywords/try-catch.md) 블록의 사용 목적은 작업 코드에서 발생하는 예외를 catch하여 처리하는 것입니다.  일부 예외는 `catch` 블록에서 처리할 수 있고 예외를 다시 throw할 필요 없이 문제가 해결됩니다. 그러나 대부분의 경우에는 적절한 예외가 throw되었는지 확인하는 작업만 할 수 있습니다.  
  
## 예제  
 다음 예제에서 <xref:System.IndexOutOfRangeException>은 가장 적절한 예외가 아닙니다. 이 오류는 호출자가 전달한 `index` 인수 때문에 발생한 것이므로 해당 메서드에는 <xref:System.ArgumentOutOfRangeException>이 보다 적절합니다.  
  
 [!code-cs[csProgGuideExceptions#5](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-handle-an-exception-using-try-catch_1.cs)]  
  
## 설명  
 예외가 발생한 코드는 `try` 블록으로 묶여 있습니다.  예외가 발생할 때 `IndexOutOfRangeException`을 처리하기 위한 `catch` 문이 바로 다음에 추가되어 있습니다.  `catch` 블록에서는 `IndexOutOfRangeException`을 처리하고 보다 적합한 `ArgumentOutOfRangeException` 예외를 대신 throw합니다.  호출자에 가능한 한 많은 정보를 제공하려면 원래 예외를 새 예외의 <xref:System.Exception.InnerException%2A>으로 지정하는 것이 좋습니다.  <xref:System.Exception.InnerException%2A> 속성은 [읽기 전용](../../../csharp/language-reference/keywords/readonly.md)이므로 새 예외의 생성자에서 이 속성을 할당해야 합니다.  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [예외 및 예외 처리](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md)   
 [예외 처리](../../../csharp/programming-guide/exceptions/exception-handling.md)