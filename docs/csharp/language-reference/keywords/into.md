---
title: "into(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "into_CSharpKeyword"
  - "into"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "into 키워드[C#]"
ms.assetid: 81ec62c1-f0b1-4755-8a31-959876e77f65
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# into(C# 참조)
컨텍스트 키워드 `into`는 [group](../../../csharp/language-reference/keywords/group-clause.md), [join](../../../csharp/language-reference/keywords/join-clause.md) 또는 [select](../../../csharp/language-reference/keywords/select-clause.md) 절의 결과를 새 식별자에 저장하는 임시 식별자를 만드는 데 사용할 수 있습니다.  이 식별자 자체는 추가 쿼리 명령에 대한 생성기가 될 수 있습니다.  `group` 또는 `select` 절에서 사용되는 경우 새 식별자의 사용을 *연속*이라고도 합니다.  
  
## 예제  
 다음 예제에서는 `IGrouping`의 유추된 형식을 포함하는 임시 식별자 `fruitGroup`을 활성화하도록 `into` 키워드를 사용하는 방법을 보여 줍니다.  식별자를 사용하여 각 그룹에서 <xref:System.Linq.Enumerable.Count%2A> 메서드를 호출하고 두 개 이상의 단어를 포함하는 해당 그룹만 선택할 수 있습니다.  
  
 [!code-cs[cscsrefQueryKeywords#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/into_1.cs)]  
  
 각 그룹에 대해 추가 쿼리 작업을 수행하려는 경우에만 `group` 절에 `into`를 사용해야 합니다.  자세한 내용은 [group 절](../../../csharp/language-reference/keywords/group-clause.md)을 참조하십시오.  
  
 `join` 절에서 `into`을 사용하는 방법에 대한 예제는 [join 절](../../../csharp/language-reference/keywords/join-clause.md)을 참조하십시오.  
  
## 참고 항목  
 [쿼리 키워드\(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [group 절](../../../csharp/language-reference/keywords/group-clause.md)