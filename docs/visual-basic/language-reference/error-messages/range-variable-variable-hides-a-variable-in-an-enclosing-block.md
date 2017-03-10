---
title: "Range variable &lt;variable&gt; hides a variable in an enclosing block, a previously defined range variable, or an implicitly declared variable in a query expression | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc36633"
  - "vbc36633"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36633"
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
caps.latest.revision: 5
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 5
---
# Range variable &lt;variable&gt; hides a variable in an enclosing block, a previously defined range variable, or an implicitly declared variable in a query expression
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`Select`, `From`, `Aggregate` 또는 `Let` 절에 지정한 범위 변수 이름이 쿼리에서 이전에 이미 지정한 범위 변수 이름 또는 쿼리를 통해 암시적으로 선언한 변수 이름\(예: 필드 이름 또는 집계 함수의 이름\)과 중복됩니다.  
  
 **오류 ID:** BC36633  
  
### 이 오류를 해결하려면  
  
-   특정 쿼리 범위의 모든 범위 변수 이름이 고유한지 확인합니다.  쿼리를 괄호로 묶어 중첩 쿼리의 범위를 고유하게 지정할 수 있습니다.  
  
## 참고 항목  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [From Clause](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Let Clause](../../../visual-basic/language-reference/queries/let-clause.md)   
 [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md)   
 [Select Clause](../../../visual-basic/language-reference/queries/select-clause.md)