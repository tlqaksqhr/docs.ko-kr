---
title: "Structure &#39;&lt;structurename&gt;&#39; must contain at least one instance member variable or at least one instance event declaration not marked &#39;Custom&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30941"
  - "vbc30941"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30941"
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Structure &#39;&lt;structurename&gt;&#39; must contain at least one instance member variable or at least one instance event declaration not marked &#39;Custom&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

구조체 정의에는 비공유 변수 또는 비공유인 비사용자 지정 이벤트가 포함되지 않습니다.  
  
 각 구조체에는 모든 인스턴스에 집합적으로 적용되게 아니라\([Shared](../../../visual-basic/language-reference/modifiers/shared.md)\) 특정의 비공유 인스턴스에 각각 적용되는 변수나 이벤트가 있어야 합니다.  비공유 상수, 속성 및 프로시저는 이 요구 사항에 맞지 않습니다.  또한 비공유 변수가 없고 비공유 이벤트가 하나만 있는 경우 해당 이벤트는 `Custom` 이벤트가 될 수 없습니다.  
  
 **오류 ID:** BC30941  
  
### 이 오류를 해결하려면  
  
-   `Shared`가 아닌 변수나 이벤트를 하나 이상 정의합니다.  이벤트를 하나만 정의할 경우 이 이벤트는 비공유 이벤트인 동시에 비사용자 지정 이벤트여야 합니다.  
  
## 참고 항목  
 [Structures](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [How to: Declare a Structure](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md)