---
title: "Return Statement (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Return"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Return statement, syntax"
  - "control flow, returning control to expressions"
  - "Return statement"
  - "expressions [Visual Basic], returning control to"
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Return Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`Function`, `Sub`, `Get`, `Set` 또는 `Operator` 프로시저를 호출한 코드로 제어를 반환합니다.  
  
## 구문  
  
```  
Return  
-or-  
Return expression  
```  
  
## 파트  
 `expression`  
 `Function`, `Get` 또는 `Operator` 프로시저에서는 필수 요소입니다.  호출 코드로 반환되는 값을 나타내는 식입니다.  
  
## 설명  
 `Sub` 또는 `Set` 프로시저에서는 `Return` 문이 `Exit Sub` 또는 `Exit Property` 문에 해당하고 `expression`을 사용하면 안 됩니다.  
  
 `Function`, `Get` 또는 `Operator` 프로시저에서는 `Return` 문이 `expression`을 포함해야 하고 `expression`이 프로시저의 반환 형식으로 변환할 수 있는 데이터 형식으로 계산되어야 합니다.  `Function` 또는 `Get` 프로시저에서는 반환 값의 역할을 수행하도록 프로시저 이름에 식을 할당한 다음 `Exit Function` 또는 `Exit Property` 문을 실행할 수도 있습니다.  `Operator` 프로시저에서는 `Return` `expression`을 사용해야 합니다.  
  
 동일한 프로시저에 `Return` 문을 가능한 한 여러 개 포함할 수 있습니다.  
  
> [!NOTE]
>  `Finally` 블록의 코드는 `Try` 또는 `Catch` 블록에서 `Return` 문을 만난 후 해당 `Return` 문이 실행되기 전에 실행됩니다.  A `Return` 에 문의 포함할 수 없습니다는 `Finally` 블록입니다.  
  
## 예제  
 다음 예제에서는 프로시저가 더 이상 필요하지 않을 때 `Return` 문을 여러 번 사용하여 해당 호출 코드로 돌아갑니다.  
  
 [!code-vb[VbVbalrStatements#53](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/return-statement_1.vb)]  
  
## 참고 항목  
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md)   
 [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md)   
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)   
 [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)