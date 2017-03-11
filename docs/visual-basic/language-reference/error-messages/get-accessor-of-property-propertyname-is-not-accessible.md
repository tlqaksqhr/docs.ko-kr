---
title: "&#39;Get&#39; accessor of property &#39;&lt;propertyname&gt;&#39; is not accessible | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc31103"
  - "bc31103"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31103"
ms.assetid: 3c346c32-7669-4b04-841d-7a9df9cb703e
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# &#39;Get&#39; accessor of property &#39;&lt;propertyname&gt;&#39; is not accessible
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

속성의 `Get` 프로시저에 대한 액세스 권한이 없는 문에서 속성의 값을 검색하려고 시도합니다.  
  
 [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md)이 해당 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)보다 제한적인 액세스 수준으로 표시된 경우 속성 값을 읽으려고 시도하면 다음과 같은 경우에 실패합니다.  
  
-   `Get` 문이 [Private](../../../visual-basic/language-reference/modifiers/private.md)으로 표시되고 속성이 정의된 클래스 또는 구조체의 외부에 호출 코드가 있는 경우  
  
-   `Get` 문이 [Protected](../../../visual-basic/language-reference/modifiers/protected.md)로 표시되고 속성이 정의된 클래스 또는 구조체의 외부와 파생 클래스에 호출 코드가 없는 경우  
  
-   `Get` 문이 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)로 표시되고 속성이 정의된 동일한 어셈블리에 호출 코드가 없는 경우  
  
 **오류 ID:** BC31103  
  
### 이 오류를 해결하려면  
  
-   속성을 정의하는 소스 코드에 대한 제어권이 있는 경우 해당 속성과 액세스 수준이 같은 `Get` 프로시저 선언을 고려합니다.  
  
-   속성을 정의하는 소스 코드에 대한 제어권이 있거나 속성보다 `Get` 프로시저 액세스 수준을 제한해야 하는 경우에는 속성 값을 읽는 문을 속성에 대해 덜 제한적인 액세스 수준을 가진 코드 영역으로 이동합니다.  
  
## 참고 항목  
 [Property 프로시저](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [How to: Declare a Property with Mixed Access Levels](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)