---
title: "Statement cannot end a block outside of a line &#39;If&#39; statement | Microsoft Docs"
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
  - "vbc32005"
  - "bc32005"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32005"
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Statement cannot end a block outside of a line &#39;If&#39; statement
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

한 줄의 `If` 문에서 여러 개의 문이 콜론\(:\)으로 구분되어 있으며, 그 중 하나가 해당 `If` 문 외부의 제어 블록에 대한 `End` 문입니다.  한 줄의 `If` 문에는 `End If` 문이 사용되지 않습니다.  
  
 **오류 ID:** BC32005  
  
### 이 오류를 해결하려면  
  
-   한 줄의 `If` 문을 `End If` 문이 포함된 제어 블록 밖으로 이동합니다.  
  
## 참고 항목  
 [If...Then...Else Statement](../../../visual-basic/language-reference/statements/if-then-else-statement.md)