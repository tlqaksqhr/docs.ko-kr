---
title: "&#39;IsNot&#39; operand of type &#39;typename&#39; can only be compared to &#39;Nothing&#39;, because &#39;typename&#39; is a nullable type | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc32128"
  - "vbc32128"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32128"
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
caps.latest.revision: 5
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 5
---
# &#39;IsNot&#39; operand of type &#39;typename&#39; can only be compared to &#39;Nothing&#39;, because &#39;typename&#39; is a nullable type
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

nullable로 선언한 변수를 `IsNot` 연산자를 사용하여 `Nothing` 이외의 식과 비교했습니다.  
  
 **오류 ID:** BC32128  
  
### 이 오류를 해결하려면  
  
1.  `IsNot` 연산자를 사용하여 nullable 형식을 `Nothing` 이외의 식과 비교하려면 다음 예제와 같이 nullable 형식에서 `GetType` 메서드를 호출한 후 그 결과를 식과 비교합니다.  
  
    ```vb#  
    Dim number? As Integer = 5  
  
    If number IsNot Nothing Then  
      If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
      End If  
    End If  
    ```  
  
## 참고 항목  
 [Nullable Value Types](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)   
 [IsNot Operator](../../../visual-basic/language-reference/operators/isnot-operator.md)