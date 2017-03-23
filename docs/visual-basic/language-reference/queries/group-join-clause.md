---
title: "Group Join Clause (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QueryGroupJoinIn"
  - "vb.QueryGroupJoinOn"
  - "vb.QueryGroupJoin"
  - "vb.QueryGroupJoinInto"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Group Join clause"
  - "Group Join statement"
  - "queries [Visual Basic], Group Join"
ms.assetid: 37dbf79c-7b5c-421b-bbb7-dadfd2b92a1c
caps.latest.revision: 24
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 24
---
# Group Join Clause (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

두 개의 컬렉션을 하나의 계층적 컬렉션으로 결합합니다.  조인 연산은 일치하는 키를 기준으로 합니다.  
  
## 구문  
  
```  
Group Join element [As type] In collection _  
  On key1 Equals key2 [ And key3 Equals key4 [... ] ] _  
  Into expressionList  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`element`|필수 요소.  조인된 컬렉션의 제어 변수입니다.|  
|`type`|선택적 요소.  `element`의 형식입니다.  `type`을 지정하지 않은 경우 `element`의 형식이 `collection`에서 유추됩니다.|  
|`collection`|필수 요소.  `Group Join` 연산자의 왼쪽에 있는 컬렉션과 결합할 컬렉션입니다.  `Group Join` 절은 다른 `Join` 절 또는 다른 `Group Join` 절에서 중첩될 수 있습니다.|  
|`key1` `Equals` `key2`|필수 요소.  조인된 컬렉션의 키를 식별합니다.  조인된 컬렉션에서 키를 비교하려면 `Equals` 연산자를 사용해야 합니다.  `And` 연산자를 사용하여 조인 조건을 결합함으로써 여러 개의 키를 식별할 수 있습니다.  `key1` 매개 변수는 `Join` 연산자의 왼쪽에 있는 컬렉션에서 가져와야 합니다.  `key2` 매개 변수는 `Join` 연산자의 오른쪽에 있는 컬렉션에서 가져와야 합니다.<br /><br /> 조인 조건에 사용되는 키는 컬렉션에서 두 개 이상의 항목을 포함하는 식일 수 있습니다.  하지만 각 키 식에는 해당 컬렉션의 항목만 포함할 수 있습니다.|  
|`expressionList`|필수 요소.  컬렉션의 요소 그룹이 집계되는 방법을 식별하는 하나 이상의 식입니다.  그룹화된 결과의 멤버 이름을 식별하려면 `Group` 키워드\(`<alias> = Group`\)를 사용합니다.  또한 집계 함수를 포함하여 그룹에 적용할 수 있습니다.|  
  
## 설명  
 `Group Join` 절은 조인된 컬렉션의 일치하는 키 값을 기준으로 두 개의 컬렉션을 결합합니다.  결과 컬렉션에는 첫 번째 컬렉션의 키 값과 일치하는 두 번째 컬렉션의 요소 컬렉션을 참조하는 멤버가 포함될 수 있습니다.  또한 집계 함수를  지정하여 두 번째 컬렉션의 그룹화된 요소에 적용할 수 있습니다.  집계 함수에 대한 자세한 내용은 [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md)을 참조하십시오.  
  
 예를 들어 관리자 컬렉션과 직원 컬렉션을 고려해 보십시오.  두 컬렉션의 요소에는 특정 관리자에게 보고하는 직원들을 식별하는 ManagerID 속성이 있습니다.  조인 연산의 결과에는 ManagerID 값이 일치하는 각 관리자와 직원에 대한 결과가 포함됩니다.  `Group Join` 연산의 결과에는 관리자 전체 목록이 포함됩니다.  각 관리자 결과에는 특정 관리자와 일치하는 직원 목록을 참조하는 멤버가 포함됩니다.  
  
 `Group Join` 연산의 결과 컬렉션에는 `From` 절에서 식별된 컬렉션의 값과 `Group Join` 절의 `Into` 절에서 식별된 식의 값의 모든 조합이 포함될 수 있습니다.  `Into` 절의 유효한 식에 대한 자세한 내용은 [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md)을 참조하십시오.  
  
 `Group Join` 연산은 `Group Join` 연산자 왼쪽에서 식별된 컬렉션에서 모든 결과를 반환합니다.  조인되는 컬렉션에 일치하는 개체가 없는 경우에도 그렇습니다.  이는 SQL의 `LEFT OUTER JOIN`과 유사합니다.  
  
 `Join` 절을 사용하여 컬렉션을 단일 컬렉션으로 결합할 수 있습니다.  이는 SQL의 `INNER JOIN`과 같습니다.  
  
## 예제  
 다음 코드 예제에서는 `Group Join` 절을 사용하여 두 개의 컬렉션을 조인합니다.  
  
 [!code-vb[VbSimpleQuerySamples#14](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/group-join-clause_1.vb)]  
  
## 참고 항목  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Queries](../../../visual-basic/language-reference/queries/queries.md)   
 [Select Clause](../../../visual-basic/language-reference/queries/select-clause.md)   
 [From Clause](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Join Clause](../../../visual-basic/language-reference/queries/join-clause.md)   
 [Where Clause](../../../visual-basic/language-reference/queries/where-clause.md)   
 [Group By 절](../../../visual-basic/language-reference/queries/group-by-clause.md)