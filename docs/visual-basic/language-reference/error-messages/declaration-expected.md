---
title: "Declaration expected | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30188"
  - "bc30188"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30188"
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Declaration expected
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

할당문 또는 루프 문과 같이 선언문이 아닌 문이 프로시저 외부에 있습니다.  프로시저 외부에는 선언만 사용할 수 있습니다.  
  
 또는 프로그래밍 요소를 선언하는 데 `Dim` 또는 `Const`와 같은 선언 키워드를 사용하지 않았습니다.  
  
 **오류 ID:** BC30188  
  
### 이 오류를 해결하려면  
  
-   선언문이 아닌 문을 프로시저 본문으로 이동합니다.  
  
-   선언 시작 부분에 적절한 선언 키워드를 사용합니다.  
  
-   선언 키워드의 철자를 확인합니다.  
  
## 참고 항목  
 [Procedures](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)