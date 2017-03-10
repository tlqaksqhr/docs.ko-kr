---
title: "let 절(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "let_CSharpKeyword"
  - "let"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "let 절[C#]"
  - "let 키워드[C#]"
ms.assetid: 13c9c1a4-ce57-48ef-8e1b-4c2a59b99fb4
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# let 절(C# 참조)
쿼리 식에서는 후속 절에서 쿼리 식을 사용하기 위해 부분식의 결과를 저장하는 것이 좋습니다.  `let` 키워드를 사용하여 작업을 할 수 있는데 이 키워드는 새로운 범위 변수를 만들고 제공된 식의 결과로 범위 변수를 초기화합니다.  값으로 초기화되고 나면 범위 변수는 다른 값을 저장하는 데 사용될 수 없습니다.  그러나 범위 변수가 쿼리 가능한 형식을 사용할 경우에는 쿼리할 수 있습니다.  
  
## 예제  
 다음 예제에서는 `let`이 두 가지 방법으로 사용되고 있습니다.  
  
1.  쿼리될 수 있는 열거 가능한 형식을 만들려면  
  
2.  범위 변수 `word`에서 `ToLower`를 한번만 호출하기 위해 쿼리하려면  `let`을 사용하지 않고 `where` 절의 각 조건자에서 `ToLower`를 호출해야 합니다.  
  
 [!code-cs[cscsrefQueryKeywords#28](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Let.cs#28)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [쿼리 키워드\(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Getting Started with LINQ in C\#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [방법: 쿼리 식의 예외 처리](../../../csharp/programming-guide/linq-query-expressions/how-to-handle-exceptions-in-query-expressions.md)