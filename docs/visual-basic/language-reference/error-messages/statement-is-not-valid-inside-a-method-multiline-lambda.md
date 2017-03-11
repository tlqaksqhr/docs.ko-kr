---
title: "Statement is not valid inside a method/multiline lambda | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30024"
  - "bc30024"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30024"
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Statement is not valid inside a method/multiline lambda
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`Sub`, `Function`, `Get` 속성 또는 `Set` 속성 프로시저 내부에는 문을 사용할 수 없습니다.  일부 문은 모듈 또는 클래스 수준에서 사용할 수 있지만  `Option Strict`와 같은 다른 문은 네임스페이스 수준에서 다른 모든 선언 앞에 사용해야 합니다.  
  
 **오류 ID:** BC30024  
  
### 이 오류를 해결하려면  
  
-   프로시저에서 문을 제거합니다.  
  
## 참고 항목  
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md)   
 [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md)