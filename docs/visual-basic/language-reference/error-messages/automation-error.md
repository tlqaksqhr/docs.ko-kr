---
title: "Automation error | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID440"
dev_langs: 
  - "VB"
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Automation error
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

메서드를 실행하는 동안 또는 개체 변수의 속성을 가져오거나 설정하는 동안 오류가 발생했습니다.  이 오류는 개체를 만든 응용 프로그램에서 보고했습니다.  
  
### 이 오류를 해결하려면  
  
1.  `Err` 개체의 속성을 점검해 오류의 원인과 특성을 확인합니다.  
  
2.  액세스하는 문 바로 전에 `On Error Resume Next` 문을 사용하고, 액세스하는 문 바로 후에 오류가 발생하는지 확인합니다.  
  
## 참고 항목  
 [Error Types](../../../visual-basic/programming-guide/language-features/error-types.md)   
 [의견 보내기](/visual-studio/ide/talk-to-us)