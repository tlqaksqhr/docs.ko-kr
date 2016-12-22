---
title: "How to: Protect a Procedure Argument Against Value Changes (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "procedures, arguments"
  - "procedures, parameters"
  - "procedure arguments"
  - "arguments [Visual Basic], passing by reference"
  - "Visual Basic code, procedures"
  - "arguments [Visual Basic], ByVal"
  - "arguments [Visual Basic], passing by value"
  - "procedure parameters"
  - "procedures, calling"
  - "arguments [Visual Basic], ByRef"
  - "arguments [Visual Basic], changing value"
ms.assetid: d2b7c766-ce16-4d2c-8d79-3fc0e7ba2227
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Protect a Procedure Argument Against Value Changes (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

프로시저에서 매개 변수를 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)로 선언하면 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 호출 코드의 내부 인수로 사용하는 프로그래밍 요소에 대한 직접적인 참조를 프로시저 코드에 제공합니다.  이 경우 프로시저에서 호출 코드의 내부 인수로 사용하는 값을 변경할 수 있습니다.  때로는 호출 코드에서 그러한 변경을 금지해야 하는 경우도 있습니다.  
  
 프로시저에서 해당 매개 변수를 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)로 선언하면 인수가 변경되는 것을 항상 방지할 수 있습니다.  지정된 인수를 일부 경우에만 변경할 수 있도록 하려면 인수를 `ByRef`로 선언하고 호출 코드에서 각각의 호출에 사용되는 전달 메커니즘을 결정하도록 하면 됩니다.  이때는 참조로 전달할 인수를 괄호로 묶는 것이 아니라 값으로 전달할 해당 인수를 괄호로 묶습니다.  자세한 내용은 [How to: Force an Argument to Be Passed by Value](../Topic/How%20to:%20Force%20an%20Argument%20to%20Be%20Passed%20by%20Value%20\(Visual%20Basic\).md)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 배열 변수를 받아 그 요소로 작업하는 두 개의 프로시저를 보여 줍니다.  `increase` 프로시저는 각 요소에 1만 더합니다.  `replace` 프로시저는 `a()` 매개 변수에 새 배열을 할당한 다음 각 요소에 1씩 더합니다.  그러나 다시 할당해도 호출 코드의 내부 배열 변수는 영향을 받지 않습니다.  
  
 [!code-vb[VbVbcnProcedures#35](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#38](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#37](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_3.vb)]  
  
 첫 번째 `MsgBox` 호출에서는 "After increase\(n\): 11, 21, 31, 41"이 표시됩니다.   `n` 배열이 참조 형식이기 때문에 전달 메커니즘이 `ByVal`인 경우에도 `replace`에서 해당 멤버를 변경할 수 있습니다.  
  
 두 번째 `MsgBox` 호출에서는 "After replace\(n\): 11, 21, 31, 41"이 표시됩니다.   `n`은 `ByVal`로 전달되므로, `replace`는 새 배열을 지정하여 호출 코드에서 `n` 변수를 수정할 수 없습니다.   `replace`가 새 배열 인스턴스 `k`를 만들어 지역 변수 `a`에 지정하면 호출 코드에서 전달된 `n`에 대한 참조가 손실됩니다.   `a`의 멤버를 변경할 경우 지역 배열 `k`만 영향을 받습니다.  따라서 `replace`는 호출 코드에서 `n` 배열 값을 늘리지 않습니다.  
  
## 코드 컴파일  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 기본적으로 인수를 값으로 전달합니다.  그러나 선언된 모든 매개 변수에 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 또는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 키워드를 사용하는 것이 바람직한 프로그래밍 습관입니다.  그러면 코드를 읽기가 더 쉽습니다.  
  
## 참고 항목  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [How to: Pass Arguments to a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Passing Arguments by Value and by Reference](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Differences Between Modifiable and Nonmodifiable Arguments](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md)   
 [Differences Between Passing an Argument By Value and By Reference](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)   
 [How to: Change the Value of a Procedure Argument](../../../../visual-basic/programming-guide/language-features/procedures/how-to-change-the-value-of-a-procedure-argument.md)   
 [How to: Force an Argument to Be Passed by Value](../Topic/How%20to:%20Force%20an%20Argument%20to%20Be%20Passed%20by%20Value%20\(Visual%20Basic\).md)   
 [Passing Arguments by Position and by Name](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)