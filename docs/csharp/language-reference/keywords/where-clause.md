---
title: "where 절(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "whereclause_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "where 절[C#]"
  - "where 키워드[C#]"
ms.assetid: 7f9bf952-7744-4f91-b676-cddb55d107c3
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# where 절(C# 참조)
`where` 절은 쿼리 식에서 반환할 데이터 소스의 요소를 쿼리 식에 지정하는 데 사용됩니다.  이 절은 범위 변수로 참조되는 각 소스 요소에 Boolean 조건\(*조건자*\)을 적용하고, 지정한 조건이 true인 요소를 반환합니다.  쿼리 식 하나에는 `where` 절을 여러 개 포함할 수 있으며 절 하나에는 조건자 하위 식을 여러 개 포함할 수 있습니다.  
  
## 예제  
 다음 예제에서 `where` 절은 5미만의 숫자만 필터링합니다.  `where` 절을 제거하면 데이터 소스에서 모든 숫자가 반환됩니다.  여기서 `num < 5` 식은 각 요소에 적용되는 조건자입니다.  
  
 [!code-cs[cscsrefQueryKeywords#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_1.cs)]  
  
## 예제  
 `where` 절 하나에는 [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) 및 [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) 연산자를 사용하여 조건자를 필요한 만큼 지정할 수 있습니다.  다음 예제에서는 쿼리에 조건자 두 개를 지정하여 5미만의 짝수만 선택합니다.  
  
 [!code-cs[cscsrefQueryKeywords#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_2.cs)]  
  
## 예제  
 `where` 절에는 Boolean 값을 반환하는 메서드를 하나 이상 포함할 수 있습니다.  다음 예제에서는 `where` 절에 메서드를 사용하여 범위 변수의 현재 값이 짝수인지 홀수인지 결정합니다.  
  
 [!code-cs[cscsrefQueryKeywords#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_3.cs)]  
  
## 설명  
 `where` 절은 필터링 메커니즘으로,  쿼리 식의 모든 위치에 사용할 수 있지만 첫 번째 또는 마지막 절은 될 수 없습니다.  `where` 절은 소스 요소 필터링을 그룹화 전에 할지, 그룹화 후에 할지에 따라 [group](../../../csharp/language-reference/keywords/group-clause.md) 절 앞이나 뒤에 올 수 있습니다.  
  
 지정한 조건자가 데이터 소스의 요소에 대해 올바르지 않으면 컴파일 타임 오류가 발생합니다.  이는 [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)]의 강력한 형식 검사 기능의 장점 중 하나입니다.  
  
 컴파일 타임에 `where` 키워드는 <xref:System.Linq.Enumerable.Where%2A> 표준 쿼리 연산자 메서드에 대한 호출로 변환됩니다.  
  
## 참고 항목  
 [쿼리 키워드\(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [from 절](../../../csharp/language-reference/keywords/from-clause.md)   
 [select 절](../../../csharp/language-reference/keywords/select-clause.md)   
 [Filtering Data](../../../visual-basic/programming-guide/concepts/linq/filtering-data.md)   
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Getting Started with LINQ in C\#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)