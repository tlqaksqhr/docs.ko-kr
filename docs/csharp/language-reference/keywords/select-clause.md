---
title: "select 절(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "select_CSharpKeyword"
  - "select"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "select 절[C#]"
  - "select 키워드[C#]"
ms.assetid: df01e266-5781-4aaa-80c4-67cf28ea093f
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# select 절(C# 참조)
쿼리 식에서 `select` 절은 쿼리가 실행될 때 생성할 값의 형식을 지정합니다.  결과는 앞의 모든 절과 `select` 절 자체의 모든 식을 기준으로 합니다.  쿼리 식은 `select` 절 또는 [group](../../../csharp/language-reference/keywords/group-clause.md) 절로 끝나야 합니다.  
  
 다음 예제에서는 쿼리 식에서의 간단한 `select` 절을 보여 줍니다.  
  
 [!code-cs[cscsrefQueryKeywords#8](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Select.cs#8)]  
  
 `select` 절에 의해 생성된 시퀀스의 형식은 쿼리 변수 `queryHighScores`의 형식을 결정합니다.  가장 간단하게는 `select` 절이 범위 변수만 지정합니다.  이로 인해 반환된 시퀀스에 데이터 소스와 동일한 형식의 요소가 포함됩니다.  자세한 내용은 [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)를 참조하십시오.  그러나 `select` 절에서는 소스 데이터를 새 형식으로 변환\(또는 *프로젝팅*\)하는 강력한 메커니즘을 제공합니다.  자세한 내용은 [LINQ를 통한 데이터 변환\(C\#\)](../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `select` 절의 여러 가지 가능한 형식을 모두 보여 줍니다.  각 쿼리에서 `select` 절과 *쿼리 변수*의 형식\(`studentQuery1` 및 `studentQuery2` 등\) 사이의 관계를 참고하십시오.  
  
 [!code-cs[cscsrefQueryKeywords#9](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Select.cs#9)]  
  
 앞 예제의 `studentQuery8`와 같이 반환된 시퀀스의 요소가 소스 요소의 속성의 하위 집합만 포함하도록 지정해야 하는 경우가 있습니다.  반환된 시퀀스를 가능한 한 작게 유지하면 메모리 요구 사항을 줄이고 쿼리 실행 속도를 높일 수 있습니다.  `select` 절에서 익명 형식을 만들고 개체 이니셜라이저를 사용하여 소스 요소의 적절한 속성으로 익명 형식을 초기화하면 이 작업을 수행할 수 있습니다.  이 작업을 수행하는 방법에 대한 예제는 [개체 및 컬렉션 이니셜라이저](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)를 참조하십시오.  
  
## 설명  
 컴파일 타임에 `select` 절은 <xref:System.Linq.Enumerable.Select%2A> 표준 쿼리 연산자에 대한 메서드 호출로 변환됩니다.  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [쿼리 키워드\(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [from 절](../../../csharp/language-reference/keywords/from-clause.md)   
 [부분\(메서드\)\(C\# 참조\)](../../../csharp/language-reference/keywords/partial-method.md)   
 [익명 형식](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Getting Started with LINQ in C\#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)