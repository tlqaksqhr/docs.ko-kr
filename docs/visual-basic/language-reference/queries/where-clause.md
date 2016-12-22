---
title: "Where Clause (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.QueryWhere"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Where statement"
  - "queries [Visual Basic], Where"
  - "Where clause"
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Where Clause (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

쿼리의 필터링 조건을 지정합니다.  
  
## 구문  
  
```  
Where condition  
```  
  
## 요소  
 `condition`  
 필수 요소.  컬렉션의 현재 항목에 대한 값이 출력 컬렉션에 포함되었는지 여부를 확인하는 식입니다.  식은 `Boolean` 값이나 `Boolean` 값에 상응하는 값으로 계산되어야 합니다.  조건이 `True`로 평가되면 요소는 쿼리 결과에 포함되며 그렇지 않은 경우 요소가 쿼리 결과에서 제외됩니다.  
  
## 설명  
 `Where` 절을 사용하면 특정 조건에 맞는 요소만 선택하여 쿼리 데이터를 필터링할 수 있습니다.  값이 `Where` 절을 `True`로 평가되게 만드는 요소는 쿼리 결과에 포함되며 다른 요소는 제외됩니다.  `Where` 절에 사용되는 식은 값이 0일때 `False`로 평가되는 정수처럼 `Boolean` 또는 `Boolean`에 상응하는 값으로 평가되어야 합니다.  `And`, `Or`, `AndAlso`, `OrElse`, `Is` 및 `IsNot`과 같은 논리 연산자를 사용하여 `Where` 절에서 여러 개의 식을 결합할 수 있습니다.  
  
 기본적으로 쿼리 식은 액세스될 때까지, 즉 데이터 바인딩되거나 `For` 루프를 통해 반복될 때까지 평가되지 않습니다.  따라서 `Where` 절은 쿼리에 액세스될 때까지 평가되지 않습니다.  `Where` 절에서 사용되는 쿼리 외부에 값이 있는 경우 쿼리가 실행될 때 적절한 값이 `Where` 절에서 사용되게 합니다.  쿼리 실행에 대한 자세한 내용은 [LINQ 쿼리 처음 작성](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)을 참조하십시오.  
  
 `Where` 절 내에서 함수를 호출하여 컬렉션의 현재 요소에서 값에 대한 계산이나 연산을 수행할 수 있습니다.  `Where` 절에서 함수를 호출하면 쿼리에 액세스할 때가 아닌 정의할 때 바로 실행되게 할 수 있습니다.  쿼리 실행에 대한 자세한 내용은 [LINQ 쿼리 처음 작성](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)을 참조하십시오.  
  
## 예제  
 다음 쿼리 식에서는 `From` 절을 사용하여 `customers` 컬렉션의 각 `Customer` 개체에 대해 범위 변수 `cust`를 선언합니다.  `Where` 절은 범위 변수를 사용하여 지정한 지역의 고객으로 출력을 제한합니다.  `For Each` 루프는 각 고객의 회사 이름을 쿼리 결과에 표시합니다.  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/where-clause_1.vb)]  
  
## 예제  
 다음 예제를 사용 하 여 `And` 및 `Or` 의 논리 연산자는 `Where` 절.  
  
 [!code-vb[VbSimpleQuerySamples#31](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/where-clause_2.vb)]  
  
## 참고 항목  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Queries](../../../visual-basic/language-reference/queries/queries.md)   
 [From Clause](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Select Clause](../../../visual-basic/language-reference/queries/select-clause.md)   
 [For Each...Next 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md)