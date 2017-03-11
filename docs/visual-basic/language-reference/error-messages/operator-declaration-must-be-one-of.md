---
title: "Operator declaration must be one of:  +,-,*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, &lt;&lt;, &gt;&gt;, =, &lt;&gt;, &lt;, &lt;=, &gt;, &gt;=, CType, IsTrue, IsFalse | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc33000"
  - "vbc33000"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC33000"
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Operator declaration must be one of:  +,-,*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, &lt;&lt;, &gt;&gt;, =, &lt;&gt;, &lt;, &lt;=, &gt;, &gt;=, CType, IsTrue, IsFalse
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

오버로드할 수 있는 연산자만 선언할 수 있습니다.  다음 표에서는 선언할 수 있는 연산자를 보여 줍니다.  
  
|형식|연산자|  
|--------|---------|  
|단항|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|  
|Binary|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|  
|변환\(단항\)|`CType`|  
  
 이진 목록의 `=` 연산자는 할당 연산자가 아니라 비교 연산자입니다.  
  
 **오류 ID:** BC33000  
  
### 이 오류를 해결하려면  
  
1.  오버로드 가능한 연산자 집합에서 연산자를 선택합니다.  
  
2.  직접 오버로드할 수 없는 연산자에 오버로드하는 기능이 필요한 경우 적절한 매개 변수를 사용하여 적절한 값을 반환하는 `Function` 프로시저를 만듭니다.  
  
## 참고 항목  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [How to: Define an Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)