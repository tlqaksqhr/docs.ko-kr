---
title: "Nullable type inference is not supported in this context | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc36629"
  - "bc36629"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36629"
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
caps.latest.revision: 5
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 5
---
# Nullable type inference is not supported in this context
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

값 형식 및 구조는 nullable로 선언할 수 있습니다.  
  
```vb#  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 그러나 형식을 유추하는 데 nullable 선언을 사용할 수는 없습니다.  다음 예제는 이 오류를 발생시킵니다.  
  
```vb#  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 **오류 ID:** BC36629  
  
### 이 오류를 해결하려면  
  
-   `As` 절을 사용하여 변수를 nullable로 선언합니다.  
  
## 참고 항목  
 [Nullable Value Types](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)   
 [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)