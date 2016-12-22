---
title: "&#39;&lt;eventname&gt;&#39; is an event, and cannot be called directly | Microsoft Docs"
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
  - "bc32022"
  - "vbc32022"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32022"
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;eventname&gt;&#39; is an event, and cannot be called directly
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

'\<`eventname`\>'은 이벤트이므로 직접 호출할 수 없습니다.  `RaiseEvent` 문을 사용하여 이벤트를 발생시키십시오.  
  
 프로시저 호출이 프로시저 이름에 대한 이벤트를 지정합니다.  이벤트 처리기는 프로시저이지만 이벤트 자체는 반드시 발생되고 처리되어야 하는 일종의 신호입니다.  
  
 **오류 ID:** BC32022  
  
### 이 오류를 해결하려면  
  
1.  `RaiseEvent` 문을 사용하여 이벤트 발생 신호를 보내고 이벤트를 처리하는 프로시저를 호출하십시오.  
  
## 참고 항목  
 [RaiseEvent Statement](../../../visual-basic/language-reference/statements/raiseevent-statement.md)