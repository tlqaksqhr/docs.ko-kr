---
title: "Subscript out of range (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID9"
dev_langs: 
  - "VB"
ms.assetid: d0344a65-ec02-4caf-8d3c-9977392ca353
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Subscript out of range (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

배열 첨자가 허용 범위 외부에 있으므로 잘못되었습니다.  차원에 대한 최소 첨자 값은 항상 0이고 최대 첨자 값은 해당 차원에 대한 `GetUpperBound` 메서드에 의해 반환됩니다.  
  
### 이 오류를 해결하려면  
  
-   올바른 범위에 속하도록 첨자를 변경합니다.  
  
## 참고 항목  
 <xref:System.Array.GetUpperBound%2A?displayProperty=fullName>   
 [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)