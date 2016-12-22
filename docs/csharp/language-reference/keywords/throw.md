---
title: "throw(C# 참조) | Microsoft Docs"
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
  - "throw"
  - "throw_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "throw 키워드[C#]"
  - "throw 문[C#]"
ms.assetid: 5ac4feef-4b1a-4c61-aeb4-61d549e5dd42
caps.latest.revision: 22
caps.handback.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# throw(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`throw` 문은 프로그램 실행 중에 비정상적인 상황\(예외\)이 발생한 경우 이를 알리는 데 사용됩니다.  
  
## 설명  
 아래 예제에서 볼 수 있는 것처럼 throw된 예제는 <xref:System.Exception?displayProperty=fullName>에서 파생된 클래스의 개체입니다.  
  
```  
class MyException : System.Exception {}  
// ...  
throw new MyException();  
```  
  
 일반적으로 `throw` 문은 `try-catch` 또는 `try-finally` 문과 함께 사용됩니다.  [throw](../../../csharp/language-reference/keywords/throw.md) 문을 `catch` 블록에 사용하여 `catch` 블록에서 catch한 예외를 다시 throw할 수 있습니다.  이 경우에 [throw](../../../csharp/language-reference/keywords/throw.md) 문은 예외 피연산자를 사용하지 않습니다.  자세한 내용 및 예제를 보려면 [try\-catch](../../../csharp/language-reference/keywords/try-catch.md) 및 [방법: 명시적으로 예외 Throw](../Topic/How%20to:%20Explicitly%20Throw%20Exceptions.md)를 참조하십시오.  
  
## 예제  
 아래 예제는 `throw` 문을 사용하여 예외를 throw하는 방법을 보여 줍니다.  
  
 [!code-cs[csrefKeywordsExceptions#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/throw_1.cs)]  
  
## 코드 예제  
 [try\-catch](../../../csharp/language-reference/keywords/try-catch.md) 및 [방법: 명시적으로 예외 Throw](../Topic/How%20to:%20Explicitly%20Throw%20Exceptions.md)에서 예제를 참조하십시오.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [try\-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [C\+\+에서의 Try, Catch 및 Throw 문](../../../csharp/language-reference/keywords/try-catch.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [예외 처리문](../../../csharp/language-reference/keywords/exception-handling-statements.md)   
 [방법: 명시적으로 예외 Throw](../Topic/How%20to:%20Explicitly%20Throw%20Exceptions.md)