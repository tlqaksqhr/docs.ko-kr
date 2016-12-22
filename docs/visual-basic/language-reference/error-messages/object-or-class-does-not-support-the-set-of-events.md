---
title: "Object or class does not support the set of events | Microsoft Docs"
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
  - "vbrID459"
dev_langs: 
  - "VB"
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Object or class does not support the set of events
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

지정된 이벤트 집합에 대한 이벤트 소스로 작동할 수 없는 구성 요소에 `WithEvents` 변수를 사용하려고 했습니다.  예를 들어, 개체의 이벤트를 싱크한 다음 첫째 개체의 `Implements`를 수행하는 다른 개체를 만들 수 있습니다.  구현된 개체에서 이벤트를 싱크할 수도 있지만 항상 가능하지는 않습니다.  `Implements`는 메서드와 속성에 대한 인터페이스만 구현합니다.  `ObjectEvent`를 발생시키는 데 필요한 형식 정보는 런타임에 사용할 수 없으므로 `WithEvents`는 private`UserControls`에 지원되지 않습니다.  
  
### 이 오류를 해결하려면  
  
1.  이벤트 소스가 아닌 구성 요소의 이벤트는 싱크할 수 없습니다.  
  
## 참고 항목  
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)   
 [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md)