---
title: "Skip Clause (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QuerySkip"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "queries [Visual Basic], Skip"
  - "Skip statement"
  - "Skip clause"
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Skip Clause (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

컬렉션에서 지정된 수의 요소를 건너뛴 다음 나머지 요소를 반환합니다.  
  
## 구문  
  
```  
Skip count  
```  
  
## 요소  
 `count`  
 필수 요소.  건너뛸 시퀀스의 요소 수로 계산되는 값이나 식입니다.  
  
## 설명  
 `Skip` 절을 사용하면 쿼리에서 결과 목록의 시작에 있는 요소를 건너 뛰고 나머지 요소를 반환합니다.  건너뛸 요소의 수는 `count` 매개 변수에 의해 식별됩니다.  
  
 `Take` 절과 함께 `Skip` 절을 사용하여 쿼리에 대한 특정 세그먼트의 데이터 범위를 반환할 수 있습니다.  이렇게 하려면 범위의 첫 번째 요소에 대한 인덱스를 `Skip` 절에 전달하고 범위 크기를 `Take` 절에 전달합니다.  
  
 쿼리에 `Skip` 절을 사용하는 경우에는 `Skip` 절에서 의도한 결과를 건너뛸 수 있는 순서로 결과가 반환되도록 해야 합니다.  쿼리 결과 정렬에 대한 자세한 내용은 [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md)을 참조하십시오.  
  
 `SkipWhile` 절을 사용하여 지정된 조건에 따라 특정 요소만 무시하도록 지정할 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 `Skip` 절을 `Take` 절과 함께 사용하여 페이지의 쿼리에서 데이터를 반환합니다.  `GetCustomers` 함수는 `Skip` 절을 사용하여 지정된 시작 인덱스 값까지 목록에서 고객을 건너뛰고 `Take` 절을 사용하여 해당 인덱스 값에서 시작하는 고객의 페이지를 반환합니다.  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#1)]  
  
## 참고 항목  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Queries](../../../visual-basic/language-reference/queries/queries.md)   
 [Select Clause](../../../visual-basic/language-reference/queries/select-clause.md)   
 [From Clause](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md)   
 [Skip While Clause](../../../visual-basic/language-reference/queries/skip-while-clause.md)   
 [Take Clause](../../../visual-basic/language-reference/queries/take-clause.md)