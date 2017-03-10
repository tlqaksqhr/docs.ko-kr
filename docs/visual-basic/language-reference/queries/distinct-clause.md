---
title: "Distinct Clause (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QueryDistinct"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Distinct clause"
  - "Distinct statement"
  - "queries [Visual Basic], Distinct"
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Distinct Clause (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

현재 범위 변수의 값을 제한하여 후속 쿼리 절에서 중복 값을 제거합니다.  
  
## 구문  
  
```  
Distinct  
```  
  
## 설명  
 `Distinct` 절을 사용하여 고유 항목의 목록을 반환할 수 있습니다.  `Distinct` 절을 사용하면 쿼리에서 중복되는 쿼리 결과가 무시됩니다.  `Distinct` 절은 `Select` 절에서 지정하는 모든 반환 필드의 중복 값에 적용됩니다.  `Select` 절을 지정하지 않으면 `Distinct` 절은 `From` 절에서 식별된 쿼리의 범위 변수에 적용됩니다.  범위 변수가 변경할 수 없는 형식이 아니면 쿼리에서는 해당 형식의 모든 멤버가 기존 쿼리 결과와 일치하는 경우에만 쿼리 결과를 무시합니다.  
  
## 예제  
 다음 쿼리 식은 고객 목록과 고객 주문 목록을 조인합니다.  `Distinct` 절은 고유한 고객 이름과 주문 날짜의 목록을 반환하기 위해 포함됩니다.  
  
 [!code-vb[VbSimpleQuerySamples#20](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#20)]  
  
## 참고 항목  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Queries](../../../visual-basic/language-reference/queries/queries.md)   
 [From Clause](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Select Clause](../../../visual-basic/language-reference/queries/select-clause.md)   
 [Where Clause](../../../visual-basic/language-reference/queries/where-clause.md)