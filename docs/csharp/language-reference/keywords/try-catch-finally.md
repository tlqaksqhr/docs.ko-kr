---
title: "try-catch-finally(C# 참조) | Microsoft Docs"
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
  - "catch-finally_CSharpKeyword"
  - "catch-finally"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "finally 블록[C#]"
  - "try-catch 문[C#]"
ms.assetid: a1b443b0-ff7a-43ab-b835-0cc9bfbd15ca
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# try-catch-finally(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

일반적으로 `catch`와 `finally`를 함께 사용하여 `try` 블록에서 리소스를 가져와 사용하고 `catch` 블록에서 예외 상황을 처리한 다음, `finally` 블록에서 리소스를 해제합니다.  
  
 예외를 다시 throw하는 것에 대한 자세한 내용 및 예제는 [try\-catch](../../../csharp/language-reference/keywords/try-catch.md) 및 [예외 throw](../Topic/How%20to:%20Explicitly%20Throw%20Exceptions.md)를 참조하십시오.  에 대 한 자세한 내용은 `finally` 블록에서 참조 하십시오  [try\-finally](../../../csharp/language-reference/keywords/try-finally.md).  
  
## 예제  
 [!code-cs[csrefKeywordsExceptions#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch-finally_1.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [Try, Throw 및 Catch 문\(C\+\+\)](/visual-cpp/cpp/try-throw-and-catch-statements-cpp)   
 [예외 처리문](../../../csharp/language-reference/keywords/exception-handling-statements.md)   
 [throw](../../../csharp/language-reference/keywords/throw.md)   
 [방법: 명시적으로 예외 Throw](../Topic/How%20to:%20Explicitly%20Throw%20Exceptions.md)   
 [using 문](../../../visual-basic/language-reference/statements/using-statement.md)