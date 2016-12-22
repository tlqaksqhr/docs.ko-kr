---
title: "Order By Clause (Visual Basic) | Microsoft Docs"
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
  - "vb.QueryOrderBy"
  - "vb.QueryAscending"
  - "vb.QueryDescending"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "queries [Visual Basic], Order By"
  - "Order By clause"
  - "Order By statement"
ms.assetid: fa911282-6b81-44c7-acfa-46b5bb93df75
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Order By Clause (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

쿼리 결과의 정렬 순서를 지정합니다.  
  
## 구문  
  
```  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## 요소  
 `orderExp1`  
 필수 요소.  현재 쿼리 결과에서 반환된 값의 순서를 지정하는 방법을 식별하는 하나 이상의 필드입니다.  필드 이름은 쉼표\(,\)로 구분되어야 합니다.  `Ascending` 또는 `Descending` 키워드를 사용하여 오름차순 또는 내림차순으로 정렬된 각 필드를 식별할 수 있습니다.  `Ascending` 또는 `Descending` 키워드가 지정되지 않은 경우 기본 정렬 순서는 오름차순입니다.  정렬 순서 필드는 왼쪽에서 오른쪽으로 우선 순위를 갖습니다.  
  
## 설명  
 `Order By` 절을 사용하여 쿼리 결과를 정렬할 수 있습니다.  `Order By` 절은 현재 범위의 범위 변수를 기준으로만 결과를 정렬합니다.  예를 들어 `Select` 절은 쿼리 식에서 새 범위를 도입할 때 해당 범위에 대한 새 반복 변수를 사용합니다.  쿼리에서 `Select` 절 앞에 정의된 범위 변수는 `Select` 절 뒤에 사용할 수 없습니다.  따라서 `Select` 절에서 사용할 수 없는 필드를 기준으로 결과의 순서를 지정하려면 `Order By` 절을 `Select` 절 앞에 배치해야 합니다.  이 방법을 사용해야 하는 한 가지 예는 결과의 일부분으로 반환되지 않은 필드를 기준으로 쿼리를 정렬하려는 경우입니다.  
  
 필드의 오름차순 및 내림차순은 필드의 데이터 형식에 대한 <xref:System.IComparable> 인터페이스의 구현에 의해 결정됩니다.  데이터 형식이 <xref:System.IComparable> 인터페이스를 구현하지 않으면 정렬 순서가 무시됩니다.  
  
## 예제  
 다음 쿼리 식은 `From` 절을 사용하여 `books` 컬렉션에 대해 `book` 범위 변수를 선언합니다.  `Order By` 절은 가격을 기준으로 쿼리 결과를 오름차순\(기본값\)으로 정렬합니다.  동일한 가격의 책은 제목을 기준으로 오름차순으로 정렬됩니다.  `Select` 절은 쿼리에 의해 반환되는 값으로 `Title` 및 `Price` 속성을 선택합니다.  
  
 [!code-vb[VbSimpleQuerySamples#24](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_1.vb)]  
  
## 예제  
 다음 쿼리 식은 `Order By` 절을 사용하여 가격 기준으로 쿼리 결과를 내림차순으로 정렬합니다.  동일한 가격의 책은 제목을 기준으로 오름차순으로 정렬됩니다.  
  
 [!code-vb[VbSimpleQuerySamples#25](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_2.vb)]  
  
## 예제  
 다음 쿼리 식은 `Select` 절을 사용하여 책 제목, 가격, 출판 날짜 및 저자를 선택합니다.  그런 다음 새 범위에 대한 범위 변수의 `Title`, `Price`, `PublishDate` 및 `Author` 필드를 채웁니다.  `Order By` 절은 저자 이름, 책 제목 그리고 마지막으로 가격을 기준으로 새 범위 변수의 순서를 지정합니다.  각 열은 기본 순서\(오름차순\)으로 정렬됩니다.  
  
 [!code-vb[VbSimpleQuerySamples#26](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_3.vb)]  
  
## 참고 항목  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Queries](../../../visual-basic/language-reference/queries/queries.md)   
 [Select Clause](../../../visual-basic/language-reference/queries/select-clause.md)   
 [From Clause](../../../visual-basic/language-reference/queries/from-clause.md)