---
title: "&lt;type1&gt;&#39;&lt;typename&gt;&#39; must implement &#39;&lt;methodname&gt;&#39; for interface &#39;&lt;interfacename&gt;&#39; | Microsoft Docs"
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
  - "vbc30149"
  - "bc30149"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30149"
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;type1&gt;&#39;&lt;typename&gt;&#39; must implement &#39;&lt;methodname&gt;&#39; for interface &#39;&lt;interfacename&gt;&#39;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

클래스 또는 구조체에서는 인터페이스를 구현해야 하지만 인터페이스에서 정의한 프로시저를 구현하지는 않습니다.  인터페이스의 멤버는 모두 구현해야 합니다.  
  
 **오류 ID:** BC30149  
  
### 이 오류를 해결하려면  
  
1.  인터페이스에 정의한 이름 및 시그니처와 동일하게 프로시저를 선언합니다.  최소한 `End Function` 또는 `End Sub` 문을 포함해야 합니다.  
  
2.  `Function` 또는 `Sub` 문의 끝에 `Implements` 절을 추가합니다.  예를 들면 다음과 같습니다.  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## 참고 항목  
 [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md)   
 [Interfaces](../../../visual-basic/reference/command-line-compiler/index.md)