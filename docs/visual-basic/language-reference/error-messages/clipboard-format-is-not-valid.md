---
title: "Clipboard format is not valid | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID460"
dev_langs: 
  - "VB"
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Clipboard format is not valid
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

지정된 Clipboard 형식이 실행되고 있는 메서드와 호환되지 않습니다.  이 오류가 발생하는 몇 가지 원인은 다음과 같습니다.  
  
-   `vbCFText` 또는 `vbCFLink`가 아닌 `GetText` 또는 `SetText` 메서드를 클립보드 형식으로 사용하는 경우  
  
-   `vbCFBitmap`, `vbCFDIB` 또는 `vbCFMetafile`이 아닌 `GetData` 또는 `SetData` 메서드를 클립보드 형식으로 사용하는 경우  
  
-   `DataObject` `GetData` 메서드 또는 `SetData` 메서드를 Microsoft Windows에 예약된 범위\(&HC000\-&HFFFF\)의 클립보드 형식으로 사용하려고 했지만 클립보드 형식이 Microsoft Windows에 예약되지 않은 경우  
  
### 이 오류를 해결하려면  
  
-   잘못된 형식을 제거하고 올바른 형식을 지정합니다.  
  
## 참고 항목  
 [클립보드: 기타 서식 추가](../Topic/Clipboard:%20Adding%20Other%20Formats.md)