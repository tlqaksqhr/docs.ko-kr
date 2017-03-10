---
title: "Delegate class &#39;&lt;classname&gt;&#39; has no Invoke method, so an expression of this type cannot be the target of a method call | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30220"
  - "bc30220"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30220"
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Delegate class &#39;&lt;classname&gt;&#39; has no Invoke method, so an expression of this type cannot be the target of a method call
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

대리자 클래스에서 `Invoke`를 구현하지 않았으므로 대리자를 통해 `Invoke`를 호출할 수 없습니다.  
  
 **오류 ID:** BC30220  
  
### 이 오류를 해결하려면  
  
1.  대리자 클래스의 인스턴스가 `Dim` 문을 통해 만들어졌는지를 확인하고 프로시저가 `AddressOf` 연산자를 통해 대리자 인스턴스에 할당되었는지 확인합니다.  
  
2.  대리자 클래스를 구현하는 코드에서 `Invoke` 프로시저를 구현합니다.  
  
## 참고 항목  
 [Delegates](../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)