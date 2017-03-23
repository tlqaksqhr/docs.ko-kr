---
title: "Derived classes cannot raise base class events | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30029"
  - "bc30029"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30029"
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Derived classes cannot raise base class events
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이벤트는 해당 이벤트가 선언되어 있는 선언 공간에서만 발생시킬 수 있습니다.  따라서 클래스에서는 다른 클래스의 이벤트를 발생시킬 수 없으며 파생 클래스의 경우도 마찬가지입니다.  
  
 **오류 ID:** BC30029  
  
### 이 오류를 해결하려면  
  
-   `Event` 문 또는 `RaiseEvent` 문을 이동하여 같은 클래스에 놓습니다.  
  
## 참고 항목  
 [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)   
 [RaiseEvent Statement](../../../visual-basic/language-reference/statements/raiseevent-statement.md)