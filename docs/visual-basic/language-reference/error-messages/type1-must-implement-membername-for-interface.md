---
title: "&lt;type1&gt;&#39;&lt;typename&gt;&#39; must implement &#39;&lt;membername&gt;&#39; for interface &#39;&lt;interfacename&gt;&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30154"
  - "bc30154"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30154"
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# &lt;type1&gt;&#39;&lt;typename&gt;&#39; must implement &#39;&lt;membername&gt;&#39; for interface &#39;&lt;interfacename&gt;&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

'\<typename\>'은\(는\) '\<interfacename\>' 인터페이스에 대한 '\<membername\>'을\(를\) 구현해야 합니다.구현 속성에는 일치하는 'ReadOnly'\/'WriteOnly' 지정자가 있어야 합니다.  
  
 클래스 또는 구조체에서는 인터페이스를 구현해야 하지만 인터페이스에서 정의한 프로시저, 속성 또는 이벤트를 구현하지는 않습니다.  인터페이스의 멤버는 모두 구현해야 합니다.  
  
 **오류 ID:** BC30154  
  
### 이 오류를 해결하려면  
  
1.  인터페이스에 정의한 이름 및 시그니처와 동일하게 멤버를 선언합니다.  최소한 `End Function`, `End Sub` 또는 `End Property` 문을 포함해야 합니다.  
  
2.  `Function`, `Sub`, `Property` 또는 `Event` 문의 끝에 `Implements` 절을 추가합니다.  예를 들면 다음과 같습니다.  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3.  속성을 구현할 때 인터페이스 정의에서와 같이 `ReadOnly` 또는 `WriteOnly`를 사용하도록 합니다.  
  
4.  속성을 구현할 때 `Get` 및 `Set` 프로시저를 적절히 선언합니다.  
  
## 참고 항목  
 [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md)   
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)