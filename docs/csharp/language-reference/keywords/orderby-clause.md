---
title: "orderby 절(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "orderby"
  - "orderby_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "orderby 절[C#]"
  - "orderby 키워드[C#]"
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# orderby 절(C# 참조)
쿼리 식에서 `orderby` 절은 반환된 시퀀스 또는 오름차순이나 내림차순으로 정렬된 결과\(그룹\)를 보여 줍니다.  둘 이상의 보조 정렬 작업을 수행하기 위해 여러 개의 키를 지정할 수 있습니다.  요소의 형식에 대한 기본 비교자를 사용하여 정렬 작업을 수행합니다.  기본 정렬 순서는 오름차순입니다.  사용자 지정 비교자를 지정할 수도 있습니다.  그러나 메서드 기반 구문을 사용하는 경우에만 지정할 수 있습니다.  자세한 내용은 [Sorting Data](../../../visual-basic/programming-guide/concepts/linq/sorting-data.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서 첫 번째 쿼리는 사전순으로 A부터 시작하는 단어를 정렬하고 두 번째 쿼리에서는 동일한 단어를 내림차순으로 정렬합니다.  `ascending` 키워드는 기본 정렬 값이므로 생략할 수 있습니다.  
  
 [!code-cs[cscsrefQueryKeywords#20](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Orderby.cs#20)]  
  
## 예제  
 다음 예제에서는 학생의 성을 기준으로 기본 정렬을 수행한 다음 이름 순으로 두 번째 정렬을 수행합니다.  
  
 [!code-cs[cscsrefQueryKeywords#22](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Orderby.cs#22)]  
  
## 설명  
 컴파일 타임에 `orderby` 절은 <xref:System.Linq.Enumerable.OrderBy%2A> 메서드를 호출하여 변환됩니다.  `orderby` 절의 여러 키는 <xref:System.Linq.Enumerable.ThenBy%2A> 메서드 호출을 변환합니다.  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [쿼리 키워드\(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [group 절](../../../csharp/language-reference/keywords/group-clause.md)   
 [Getting Started with LINQ in C\#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)