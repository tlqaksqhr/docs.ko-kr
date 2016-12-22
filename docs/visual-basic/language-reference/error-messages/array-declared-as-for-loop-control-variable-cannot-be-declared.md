---
title: "Array declared as for loop control variable cannot be declared with an initial size | Microsoft Docs"
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
  - "vbc32039"
  - "bc32039"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32039"
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Array declared as for loop control variable cannot be declared with an initial size
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`For Each` 루프는 배열을 *element* 반복 변수로 사용하지만 해당 배열을 초기화하지 않습니다.  
  
 다음 문은 이 오류가 발생할 수 있는 경우를 보여 줍니다.  
  
```  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 첫째 `For Each` 문은 `arrayList` 요소에 액세스하는 올바른 방법입니다.  둘째 `For Each` 문에서 이 오류가 발생합니다.  
  
 **오류 ID:** BC32039  
  
### 이 오류를 해결하려면  
  
-   *element* 반복 변수 선언에서 초기화를 제거합니다.  
  
## 참고 항목  
 [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [컬렉션](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md)