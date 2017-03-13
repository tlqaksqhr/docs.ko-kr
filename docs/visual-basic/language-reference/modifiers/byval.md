---
title: "ByVal (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ByVal"
  - "ByVal"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ByVal keyword, contexts"
  - "ByVal keyword"
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# ByVal (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

호출된 프로시저나 속성은 호출 코드에서 내부 인수로 사용하는 변수의 값을 변경할 수 없도록 하는 방식으로 인수가 전달되도록 지정합니다.  
  
## 설명  
 `ByVal` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## 예제  
 다음 예제에서는 `ByVal` 매개 변수 전달 메커니즘을 참조 형식 인수와 함께 사용하는 방법을 보여 줍니다.  이 예제에서 인수는 `Class1` 클래스의 인스턴스인 `c1`입니다.  `ByVal`을 사용하면 프로시저의 코드에서 참조 인수 `c1`의 내부 값을 변경할 수 없도록 차단하지만 `c1`의 액세스 가능 필드와 속성은 보호되지 않습니다.  
  
 [!code-vb[VbVbalrKeywords#10](../../../visual-basic/language-reference/codesnippet/VisualBasic/byval_1.vb)]  
  
## 참고 항목  
 [키워드](../../../visual-basic/language-reference/keywords/index.md)   
 [Passing Arguments by Value and by Reference](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)