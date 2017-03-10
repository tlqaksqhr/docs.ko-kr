---
title: "How to: Force an Argument to Be Passed by Value (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "procedures, arguments"
  - "procedures, parameters"
  - "procedure arguments"
  - "Visual Basic code, procedures"
  - "arguments [Visual Basic], ByVal"
  - "arguments [Visual Basic], passing by value"
  - "procedure parameters"
  - "procedures, calling"
  - "arguments [Visual Basic], in parentheses"
  - "procedure arguments, in parentheses"
  - "arguments [Visual Basic], changing value"
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# How to: Force an Argument to Be Passed by Value (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

프로시저 선언에 따라 전달 메커니즘이 결정됩니다.  매개 변수가 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)로 선언되면 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 해당 인수가 참조로 전달된다고 예상합니다.  이렇게 하면 프로시저가 호출 코드에서 내부 인수로 사용하는 프로그래밍 요소의 값을 변경할 수 있습니다.  이러한 변경으로부터 내부 요소를 보호하려면 인수 이름을 괄호로 묶어 프로시저 호출에서 `ByRef` 전달 메커니즘을 재정의할 수 있습니다.  호출에서 인수 목록을 묶는 괄호에 이러한 괄호가 추가됩니다.  
  
 호출 코드에서 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 메커니즘을 재정의할 수는 없습니다.  
  
### 인수가 값으로 전달되게 설정하려면  
  
-   해당 매개 변수가 프로시저에서 `ByVal`로 선언된 경우 어떠한 추가 단계도 수행할 필요가 없습니다.  이미 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 인수가 값으로 전달되는 것으로 간주됩니다.  
  
-   해당 매개 변수가 프로시저에서 `ByRef`로 선언된 경우 프로시저 호출에서 인수를 괄호로 묶습니다.  
  
## 예제  
 다음 예제에서는 `ByRef` 매개 변수 선언을 재정의합니다.  `ByVal`로 처리하는 호출에서는 중첩 괄호를 사용함을 유의하십시오.  
  
 [!code-vb[VbVbcnProcedures#39](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-force-an-argument_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#40](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-force-an-argument_2.vb)]  
  
 인수 목록 내에서 `str`를 추가 괄호로 묶으면 `setNewString` 프로시저는 호출 코드에서 해당 값을 변경할 수 없으며 `MsgBox`에는 "Cannot be replaced if passed ByVal"이 표시됩니다.  `str`를 추가 괄호로 묶지 않으면 프로시저가 해당 값을 변경할 수 있으며 `MsgBox`에는 "This is a new value for the inString argument."가 표시됩니다.  
  
## 코드 컴파일  
 변수를 참조로 전달할 경우 `ByRef` 키워드를 사용하여 이 메커니즘을 지정해야 합니다.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 기본적으로 인수를 값으로 전달합니다.  그러나 선언된 모든 매개 변수에 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 또는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 키워드를 사용하는 것이 바람직한 프로그래밍 습관입니다.  그러면 코드를 읽기가 더 쉽습니다.  
  
## 강력한 프로그래밍  
 프로시저에서 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 매개 변수를 선언한 경우 호출 코드의 내부 요소를 변경할 수 있는지 여부에 따라 코드가 올바르게 실행되는지 결정됩니다.  인수를 괄호로 묶어 호출 코드에서 이 호출 메커니즘을 재정의하거나 수정할 수 없는 인수가 전달될 경우 프로시저는 내부 요소를 변경할 수 없습니다.  이로 인해서 호출 코드에서 예기치 않은 결과가 발생할 수 있습니다.  
  
## .NET Framework 보안  
 호출 코드에서 내부 인수로 사용하는 값을 프로시저에서 변경하도록 허용하는 것은 항상 잠재적인 위험을 갖고 있습니다.  따라서 이 값이 변경될 것을 예상해야 하고 값을 사용하기 전에 유효성을 검사할 수 있도록 준비해야 합니다.  
  
## 참고 항목  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [How to: Pass Arguments to a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Passing Arguments by Value and by Reference](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Differences Between Modifiable and Nonmodifiable Arguments](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md)   
 [Differences Between Passing an Argument By Value and By Reference](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)   
 [How to: Change the Value of a Procedure Argument](../../../../visual-basic/programming-guide/language-features/procedures/how-to-change-the-value-of-a-procedure-argument.md)   
 [How to: Protect a Procedure Argument Against Value Changes](../../../../visual-basic/programming-guide/language-features/procedures/how-to-protect-a-procedure-argument-against-value-changes.md)   
 [Passing Arguments by Position and by Name](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)