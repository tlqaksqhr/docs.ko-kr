---
title: "&#39;Class&#39; statement must end with a matching &#39;End Class&#39; | Microsoft Docs"
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
  - "vbc30481"
  - "bc30481"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30481"
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Class&#39; statement must end with a matching &#39;End Class&#39;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`Class`는 `Class` 블록을 초기화하는 데 사용되므로 블록의 시작 부분에만 사용할 수 있으며 짝이 되는`End Class` 문으로 블록을 마쳐야 합니다.  중복된 `Class` 문이 있거나 `Class` 블록을 마치는 데 `End Class`를 사용하지 않았습니다.  
  
 **오류 ID:** BC30481  
  
### 이 오류를 해결하려면  
  
-   불필요한 `Class` 문을 찾아 제거합니다.  
  
-   `Class` 블록을 짝이 되는 `End Class`로 마칩니다.  
  
## 참고 항목  
 [End \<keyword\> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md)   
 [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)