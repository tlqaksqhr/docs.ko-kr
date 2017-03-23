---
title: "File not found (Visual Basic Run-Time Error) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID53"
dev_langs: 
  - "VB"
ms.assetid: 57addb16-6f9a-444d-8af8-dda52431daca
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# File not found (Visual Basic Run-Time Error)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

지정된 위치에서 파일을 찾을 수 없습니다.  이 오류가 발생하는 원인은 다음과 같습니다.  
  
-   문에서 존재하지 않는 파일을 참조했습니다.  
  
-   DLL\(동적 연결 라이브러리\)의 프로시저를 호출하려고 했지만 `Declare` 문의 `Lib` 절에 지정된 라이브러리를 찾을 수 없습니다.  
  
-   존재하지 않는 프로젝트를 열거나 존재하지 않는 텍스트 파일을 로드하려고 했습니다.  
  
### 이 오류를 해결하려면  
  
1.  파일 이름 및 경로 사양의 철자를 확인합니다.  
  
## 참고 항목  
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)