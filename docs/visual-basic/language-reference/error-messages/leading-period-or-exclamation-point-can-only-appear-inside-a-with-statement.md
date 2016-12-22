---
title: "Leading &#39;.&#39; or &#39;!&#39; can only appear inside a &#39;With&#39; statement | Microsoft Docs"
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
  - "vbc30157"
  - "bc30157"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30157"
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Leading &#39;.&#39; or &#39;!&#39; can only appear inside a &#39;With&#39; statement
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

왼쪽 식이 없는 마침표\(.\) 또는 느낌표\(\!\)를 `With` 블록 밖에 사용했습니다.  멤버 액세스\(`.`\) 및 사전 멤버 액세스\(`!`\)에는 멤버를 포함하는 요소를 지정하는 식이 필요합니다.  이 식은 접근자의 바로 왼쪽에 사용하거나 멤버 액세스를 포함하는 `With` 블록의 대상으로 사용해야 합니다.  
  
 **오류 ID:** BC30157  
  
### 이 오류를 해결하려면  
  
1.  `With` 블록의 형식이 올바로 지정되었는지 확인합니다.  
  
2.  `With` 블록이 없으면 멤버를 포함하는 정의된 요소가 되는 식을 접근자의 왼쪽에 추가합니다.  
  
## 참고 항목  
 [Special Characters in Code](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)   
 [With...End With Statement](../../../visual-basic/language-reference/statements/with-end-with-statement.md)