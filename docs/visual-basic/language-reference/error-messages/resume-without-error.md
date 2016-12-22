---
title: "Resume without error | Microsoft Docs"
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
  - "vbrID20"
dev_langs: 
  - "VB"
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Resume without error
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`Resume` 문이 오류 처리 코드 외부에 있거나, 오류가 없음에도 불구하고 코드가 오류 처리기로 점프했습니다.  
  
### 이 오류를 해결하려면  
  
1.  `Resume` 문을 오류 처리기로 이동하거나 삭제합니다.  
  
2.  다른 프로시저에 있는 레이블로 점프할 수 없으므로 오류 처리기와 동일한 레이블에 대한 프로시저를 검색합니다.  `On Error GoTo` 문이 아닌 `GoTo` 문의 대상으로 지정된 레이블과 중복된 경우 줄 레이블을 변경하여 원래 대상과 일치하도록 합니다.  
  
## 참고 항목  
 [Resume Statement](../../../visual-basic/language-reference/statements/resume-statement.md)   
 [On Error Statement](../../../visual-basic/language-reference/statements/on-error-statement.md)