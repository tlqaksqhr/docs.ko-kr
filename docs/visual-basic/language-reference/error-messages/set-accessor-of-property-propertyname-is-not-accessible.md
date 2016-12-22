---
title: "&#39;Set&#39; accessor of property &#39;&lt;propertyname&gt;&#39; is not accessible | Microsoft Docs"
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
  - "vbc31102"
  - "bc31102"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31102"
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Set&#39; accessor of property &#39;&lt;propertyname&gt;&#39; is not accessible
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

속성의 `Set` 프로시저에 대한 액세스 권한이 없는 문에서 속성의 값을 저장하려고 합니다.  
  
 [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md)이 해당 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)보다 더 제한적인 액세스 수준으로 표시된 경우 속성 값을 설정하려고 하면 다음과 같은 경우 실패합니다.  
  
-   `Set` 문이 [Private](../../../visual-basic/language-reference/modifiers/private.md)으로 표시되고 속성이 정의된 클래스 또는 구조체의 외부에 호출 코드가 있는 경우  
  
-   `Set` 문이 [Protected](../../../visual-basic/language-reference/modifiers/protected.md)로 표시되고 속성이 정의된 클래스 또는 구조체의 내부 및 파생 클래스에 호출 코드가 없는 경우  
  
-   `Set` 문이 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)로 표시되고 속성이 정의된 같은 어셈블리에 호출 코드가 없는 경우  
  
 **오류 ID:** BC31102  
  
### 이 오류를 해결하려면  
  
-   속성을 정의하는 소스 코드에 대한 제어가 있는 경우 해당 속성과 액세스 수준이 같은 `Set` 프로시저 선언을 고려합니다.  
  
-   속성을 정의하는 소스 코드에 대한 제어가 없거나 속성 자체보다 `Set` 프로시저 액세스 수준을 제한해야 하는 경우 속성 값을 설정하는 문을 속성에 대해 덜 제한적인 액세스 수준을 가진 코드 영역으로 이동합니다.  
  
## 참고 항목  
 [Property 프로시저](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [How to: Declare a Property with Mixed Access Levels](../Topic/How%20to:%20Declare%20a%20Property%20with%20Mixed%20Access%20Levels%20\(Visual%20Basic\).md)