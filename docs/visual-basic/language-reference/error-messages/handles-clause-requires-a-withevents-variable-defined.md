---
title: "Handles clause requires a WithEvents variable defined in the containing type or one of its base types | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30506"
  - "bc30506"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30506"
ms.assetid: 5b66f6a8-f050-4e03-a57f-a64e85f80cb5
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Handles clause requires a WithEvents variable defined in the containing type or one of its base types
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`Handles` 절에 `WithEvents` 변수를 사용하지 않았습니다.  프로시저 선언의 끝 부분에서 `Handles` 키워드를 사용하면 `WithEvents` 키워드를 사용하여 선언한 개체 변수로 발생시킨 이벤트를 처리하도록 할 수 있습니다.  
  
 **오류 ID:** BC30506  
  
### 이 오류를 해결하려면  
  
-   필요한 `WithEvents` 변수를 사용합니다.  
  
## 참고 항목  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)