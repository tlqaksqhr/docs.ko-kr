---
title: "&#39;&lt;typename&gt;&#39; cannot inherit from &lt;type&gt; &#39;&lt;basetypename&gt;&#39; because it expands the access of the base &lt;type&gt; outside the assembly | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30910"
  - "bc30910"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30910"
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# &#39;&lt;typename&gt;&#39; cannot inherit from &lt;type&gt; &#39;&lt;basetypename&gt;&#39; because it expands the access of the base &lt;type&gt; outside the assembly
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

클래스 또는 인터페이스는 기본 클래스 또는 인터페이스에서 상속하지만 덜 제한적인 액세스 수준을 가지고 있습니다.  
  
 예를 들어, `Public` 인터페이스는 `Friend` 인터페이스에서 상속되거나 `Protected` 클래스는 `Private` 클래스에서 상속됩니다.  이렇게 되면 기본 클래스나 인터페이스를 노출하여 원하는 액세스 수준을 넘게 됩니다.  
  
 **오류 ID:** BC30910  
  
### 이 오류를 해결하려면  
  
-   파생 클래스 또는 인터페이스의 액세스 수준을 최소한 기본 클래스 또는 인터페이스의 액세스 제한 수준으로 변경합니다.  
  
     또는  
  
-   덜 제한적인 액세스 수준이 필요한 경우에는 `Inherits` 문을 제거합니다.  더 제한된 기본 클래스 또는 인터페이스에서 상속할 수 없습니다.  
  
## 참고 항목  
 [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md)   
 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)