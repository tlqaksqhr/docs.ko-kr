---
title: "Let Clause (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QueryLet"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "queries [Visual Basic], Let"
  - "Let clause"
  - "Let statement"
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Let Clause (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

값을 계산하고 이 값을 쿼리의 새 변수에 할당합니다.  
  
## 구문  
  
```  
Let variable = expression [, ...]  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`variable`|필수 요소.  지정된 식의 결과를 참조하는 데 사용할 수 있는 별칭입니다.|  
|`expression`|필수 요소.  평가될 때 지정된 변수에 할당되는 식입니다.|  
  
## 설명  
 `Let` 절을 사용하면 각 쿼리 결과의 값을 계산하고 별칭을 사용하여 해당 값을 참조할 수 있습니다.  별칭은 `Where` 절과 같은 다른 절에서 사용할 수 있습니다.  `Let` 절을 사용하면 쿼리에 포함된 식 절에 별칭을 지정하여 식 절을 사용할 때마다 별칭으로 대체할 수 있기 때문에 더 읽기 쉬운 쿼리 문을 만들 수 있습니다.  
  
 `Let` 절에는 `variable` 및 `expression` 할당을 제한 없이 포함시킬 수 있습니다.  각 할당은 쉼표\(,\)로 구분합니다.  
  
## 예제  
 다음 코드 예제에서는 `Let` 절을 사용하여 제품의 10% 할인을 계산합니다.  
  
 [!code-vb[VbSimpleQuerySamples#16](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/let-clause_1.vb)]  
  
## 참고 항목  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Queries](../../../visual-basic/language-reference/queries/queries.md)   
 [Select Clause](../../../visual-basic/language-reference/queries/select-clause.md)   
 [From Clause](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Where Clause](../../../visual-basic/language-reference/queries/where-clause.md)