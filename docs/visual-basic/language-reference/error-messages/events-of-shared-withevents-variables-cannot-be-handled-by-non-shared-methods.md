---
title: "Events of shared WithEvents variables cannot be handled by non-shared methods | Microsoft Docs"
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
  - "bc30594"
  - "vbc30594"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30594"
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Events of shared WithEvents variables cannot be handled by non-shared methods
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`Shared` 한정자를 사용하여 선언한 변수는 공유 변수입니다.  공유 변수는 저장소 위치를 하나만 식별합니다.  `WithEvents` 한정자를 사용하여 변수를 선언하면 변수가 속한 형식에서 변수가 발생하는 이벤트 집합을 처리한다는 것을 나타냅니다.  변수에 값이 할당되면 `WithEvents` 선언에 의해 만들어진 속성에서 기존 이벤트 처리기를 언후크하고 `Add` 메서드를 통해 새 이벤트 처리기를 후크합니다.  
  
 **오류 ID:** BC30594  
  
### 이 오류를 해결하려면  
  
-   이벤트 처리기를 `Shared`로 선언합니다.  
  
## 참고 항목  
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)   
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)