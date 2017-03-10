---
title: "From Clause (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QueryFrom"
  - "vb.QueryFromIn"
  - "vb.QueryFromLet"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "queries [Visual Basic], From"
  - "From clause"
  - "From statement"
ms.assetid: 83e3665e-68a0-4540-a3a3-3d777a0f95d5
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# From Clause (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

하나 이상의 범위 변수와 쿼리할 컬렉션을 지정합니다.  
  
## 구문  
  
```  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`element`|필수 요소.  컬렉션의 요소를 반복하는 데 사용되는 *범위 변수*입니다.  범위 변수는 쿼리에서 `collection`을 반복할 때 `collection`의 각 멤버를 참조하는 데 사용되며  열거 가능한 형식이어야 합니다.|  
|`type`|선택적 요소.  `element`의 형식입니다.  `type`을 지정하지 않은 경우 `element`의 형식이 `collection`에서 유추됩니다.|  
|`collection`|필수 요소.  쿼리할 컬렉션을 나타냅니다.  열거 가능한 형식이어야 합니다.|  
  
## 설명  
 `From` 절은 쿼리의 소스 데이터와 소스 컬렉션의 요소를 참조하는 데 사용하는 변수를 식별합니다.  이러한 변수를 *범위 변수*라고 합니다.  집계된 결과만 반환하는 쿼리를 식별하기 위해 `Aggregate` 절을 사용하는 경우를 제외하고 쿼리에 `From` 절이 있어야 합니다.  자세한 내용은 [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md)를 참조하십시오.  
  
 쿼리에서 여러 `From` 절을 지정하여 조인할 여러 컬렉션을 식별할 수 있습니다.  여러 컬렉션을 지정하는 경우 각 컬렉션을 독립적으로 반복할 수도 있고 컬렉션이 서로 연관된 경우 조인할 수도 있습니다.  컬렉션을 `Select` 절을 사용하여 암시적으로 조인하거나 `Join` 또는 `Group Join` 절을 사용하여 명시적으로 조인할 수 있습니다.  또는 하나의 `From` 절에서 관련된 여러 범위 변수와 컬렉션을 각각 쉼표로 구분하여 지정할 수 있습니다.  다음 코드 예제에서는 `From` 절에 대한 두 구문 옵션을 보여 줍니다.  
  
 [!code-vb[VbSimpleQuerySamples#21](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#21)]  
  
 `From` 절에서는 쿼리의 범위를 정의하며 이는 `For` 루프의 범위와 유사합니다.  따라서 쿼리 범위에서 각 `element` 범위 변수에는 고유한 이름이 있어야 합니다.  쿼리에 여러 `From` 절을 지정할 수 있으므로 이후의 `From` 절에서 해당 `From` 절의 범위 변수를 참조하거나 이전 `From` 절의 범위 변수를 참조할 수 있습니다.  예를 들어 다음 예제에서는 두 번째 절의 컬렉션이 첫 번째 절의 범위 변수 속성을 기반으로 하는 중첩된 `From` 절을 보여 줍니다.  
  
 [!code-vb[VbSimpleQuerySamples#22](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#22)]  
  
 각 `From` 절 다음에 다른 쿼리 절 조합을 추가하여 쿼리 조건을 더 구체화할 수 있습니다.  쿼리 조건을 구체화하는 방법은 다음과 같습니다.  
  
-   여러 컬렉션을 `From` 및 `Select` 절을 사용하여 암시적으로 결합하거나 `Join` 또는 `Group Join` 절을 사용하여 명시적으로 결합합니다.  
  
-   `Where` 절을 사용하여 쿼리 결과를 필터링합니다.  
  
-   `Order By` 절을 사용하여 결과를 정렬합니다.  
  
-   `Group By` 절을 사용하여 유사한 결과를 그룹화합니다.  
  
-   `Aggregate` 절을 사용하여 전체 쿼리 결과를 평가할 집계 함수를 식별합니다.  
  
-   `Let` 절을 사용하여 해당 값이 컬렉션이 아닌 식으로 결정되는 반복 변수를 도입합니다.  
  
-   `Distinct` 절을 사용하여 중복되는 쿼리 결과를 무시합니다.  
  
-   `Skip`, `Take`, `Skip While` 및 `Take While` 절을 사용하여 반환할 결과의 일부를 식별합니다.  
  
## 예제  
 다음 쿼리 식에서는 `From` 절을 사용하여 `customers` 컬렉션의 각 `Customer` 개체에 대해 범위 변수 `cust`를 선언합니다.  `Where` 절은 범위 변수를 사용하여 지정한 지역의 고객으로 출력을 제한합니다.  `For Each` 루프는 각 고객의 회사 이름을 쿼리 결과에 표시합니다.  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#23)]  
  
## 참고 항목  
 [Queries](../../../visual-basic/language-reference/queries/queries.md)   
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [For Each...Next 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md)   
 [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Select Clause](../../../visual-basic/language-reference/queries/select-clause.md)   
 [Where Clause](../../../visual-basic/language-reference/queries/where-clause.md)   
 [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md)   
 [Distinct Clause](../../../visual-basic/language-reference/queries/distinct-clause.md)   
 [Join Clause](../../../visual-basic/language-reference/queries/join-clause.md)   
 [Group Join Clause](../../../visual-basic/language-reference/queries/group-join-clause.md)   
 [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md)   
 [Let Clause](../../../visual-basic/language-reference/queries/let-clause.md)   
 [Skip Clause](../../../visual-basic/language-reference/queries/skip-clause.md)   
 [Take Clause](../../../visual-basic/language-reference/queries/take-clause.md)   
 [Skip While Clause](../../../visual-basic/language-reference/queries/skip-while-clause.md)   
 [Take While Clause](../../../visual-basic/language-reference/queries/take-while-clause.md)