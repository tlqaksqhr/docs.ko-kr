---
title: "Take Clause (Visual Basic) | Microsoft Docs"
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
  - "vb.QueryTake"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Take statement"
  - "queries [Visual Basic], Take"
  - "Take clause"
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Take Clause (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

컬렉션의 시작 위치에서 지정된 수의 연속 요소를 반환합니다.  
  
## 구문  
  
```  
Take count  
```  
  
## 요소  
 `count`  
 필수 요소.  반환할 시퀀스의 요소 수로 계산되는 값이나 식입니다.  
  
## 설명  
 `Take` 절은 결과 목록의 시작 부분에서 지정된 수의 연속 요소가 쿼리에 포함되게 합니다.  포함할 요소의 수는 `count` 매개 변수에 의해 지정됩니다.  
  
 `Skip` 절과 함께 `Take` 절을 사용하여 쿼리의 세그먼트에서 데이터 범위를 반환할 수 있습니다.  이렇게 하려면 범위의 첫 번째 요소에 대한 인덱스를 `Skip` 절에 전달하고 범위 크기를 `Take` 절에 전달합니다.  이 경우 `Take` 절은 `Skip` 절 뒤에 지정되어야 합니다.  
  
 쿼리에 `Take` 절을 사용하는 경우 `Take` 절에서 의도한 결과를 포함하게 될 순서로 결과도 반환되어야 합니다.  쿼리 결과 정렬에 대한 자세한 내용은 [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md)을 참조하십시오.  
  
 `TakeWhile` 절을 사용하여 제공된 조건에 따라 해당 특정 요소만 반환되도록 지정할 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 `Take` 절을 `Skip` 절과 함께 사용하여 페이지의 쿼리에서 데이터를 반환합니다.  GetCustomers 함수는 `Skip` 절을 사용하여 제공된 시작 인덱스 값까지 목록에서 고객을 건너뛰고 `Take` 절을 사용하여 해당 인덱스 값에서 시작하는 고객의 페이지를 반환합니다.  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-clause_1.vb)]  
  
## 참고 항목  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Queries](../../../visual-basic/language-reference/queries/queries.md)   
 [Select Clause](../../../visual-basic/language-reference/queries/select-clause.md)   
 [From Clause](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md)   
 [Take While Clause](../../../visual-basic/language-reference/queries/take-while-clause.md)   
 [Skip Clause](../../../visual-basic/language-reference/queries/skip-clause.md)