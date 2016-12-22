---
title: "Select Clause (Visual Basic) | Microsoft Docs"
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
  - "vb.QuerySelect"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Select statement"
  - "Select clause"
  - "queries [Visual Basic], Select"
ms.assetid: 27a3f61c-5960-4692-9b91-4d0c4b6178fe
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Select Clause (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

쿼리의 결과를 정의합니다.  
  
## 구문  
  
```  
Select [ var1 = ] fieldName1 [, [ var2 = ] fieldName2 [...] ]  
```  
  
## 요소  
 `var1`  
 선택적 요소.  열 식의 결과를 참조하는 데 사용할 수 있는 별칭입니다.  
  
 `fieldName1`  
 필수 요소.  쿼리 결과에 반환할 필드의 이름입니다.  
  
## 설명  
 `Select` 절을 사용하여 쿼리에서 반환할 결과를 정의합니다.  이를 통해 쿼리에 의해 만들어지는 새 익명 형식의 멤버를 정의하거나 쿼리에 의해 반환되는 명명된 형식의 멤버를 대상으로 지정할 수 있습니다.  쿼리에 `Select` 절은 필요하지 않습니다.  `Select` 절을 지정하지 않으면 쿼리는 현재 범위에 대해 식별되는 범위 변수의 모든 멤버를 기준으로 형식을 반환합니다.  자세한 내용은 [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)을 참조하십시오.  쿼리가 명명된 형식을 만들 때 형식이 <xref:System.Collections.Generic.IEnumerable%601>인 결과를 반환하는데 이때 `T`는 만들어진 형식입니다.  
  
 `Select` 절은 현재 범위의 모든 변수를 참조할 수 있습니다.  여기에는 `From` 절\(또는 `From` 절\)에서 식별된 범위 변수가 포함됩니다.  또한 `Aggregate`, `Let`, `Group By` 또는 `Group Join` 절에 의해 별칭을 사용하여 만들어진 새 변수 또는 쿼리 식에서 이전 `Select` 절의 변수도 포함됩니다.  `Select` 절에는 정적 값도 포함될 수 있습니다.  예를 들어 다음 코드 예제에서는 `Select` 절이 `ProductName`, `Price`, `Discount` 및 `DiscountedPrice`의 네 개의 멤버를 사용하여 익명 형식으로 쿼리 결과를 정의하는 쿼리 식을 보여 줍니다.  `ProductName` 및 `Price` 멤버 값은 `From` 절에 정의된 제품 범위 변수에서 가져옵니다.  `DiscountedPrice` 멤버 값은 `Let` 절에서 계산됩니다.  `Discount` 멤버는 정적 값입니다.  
  
 [!code-vb[VbSimpleQuerySamples#27](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_1.vb)]  
  
 `Select` 절에서는 후속 쿼리 절을 위해 새로운 범위 변수 집합을 도입하고 이전 범위 변수는 더 이상 해당 범위에 포함되지 않습니다.  쿼리 식의 마지막 `Select` 절은 쿼리의 반환 값을 결정합니다.  예를 들어 다음 쿼리는 전체 500개를 초과하는 모든 고객 주문의 회사 이름과 주문 ID를 반환합니다.  첫 번째 `Select` 절은 `Where` 절 및 두 번째 `Select` 절의 범위 변수를 식별합니다.  두 번째 `Select` 절은 쿼리가 새 익명 형식으로 반환한 값을 식별합니다.  
  
 [!code-vb[VbSimpleQuerySamples#28](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_2.vb)]  
  
 `Select` 절이 반환할 단일 항목을 식별하는 경우 쿼리 식은 해당 단일 항목 형식의 컬렉션을 반환합니다.  `Select` 절이 반환할 여러 항목을 식별하는 경우 쿼리 식은 선택된 항목을 기준으로 하여 새 익명 유형의 컬렉션을 반환합니다.  예를 들어 다음 두 개의 쿼리는 `Select` 절을 기준으로 서로 다른 두 형식의 컬렉션을 반환합니다.  첫 번째 쿼리는 회사 이름 컬렉션을 문자열로 반환합니다.  두 번째 쿼리는 회사 이름과 주소 정보가 채워진 `Customer` 개체의 컬렉션을 반환합니다.  
  
 [!code-vb[VbSimpleQuerySamples#29](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_3.vb)]  
  
## 예제  
 다음 쿼리 식은 `From` 절을 사용하여 `customers` 컬렉션에 대해 `cust` 범위 변수를 선언합니다.  `Select` 절은 고객 이름 및 ID 값을 선택하고 새 범위 변수의 `CompanyName` 및 `CustomerID` 열을 채웁니다.  `For Each` 문은 반환된 각 개체를 반복 수행하고 각 레코드에 대해 `CompanyName` 및 `CustomerID` 열을 표시합니다.  
  
 [!code-vb[VbSimpleQuerySamples#30](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_4.vb)]  
  
## 참고 항목  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Queries](../../../visual-basic/language-reference/queries/queries.md)   
 [From Clause](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Where Clause](../../../visual-basic/language-reference/queries/where-clause.md)   
 [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md)   
 [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)