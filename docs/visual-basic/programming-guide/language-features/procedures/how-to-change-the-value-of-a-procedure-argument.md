---
title: "How to: Change the Value of a Procedure Argument (Visual Basic) | Microsoft Docs"
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
  - "arguments [Visual Basic], ByRef"
  - "arguments [Visual Basic], changing value"
ms.assetid: 6fad2368-5da7-4c07-8bf8-0f4e65a1be67
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Change the Value of a Procedure Argument (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

프로시저를 호출할 때 사용자가 제공하는 각 인수는 프로시저에 정의된 매개 변수 중 하나에 해당합니다.  경우에 따라서는 호출 코드에서 인수를 원본으로 사용하는 값을 프로시저 코드에서 변경할 수 있습니다.  그 외의 경우에는 프로시저에서 인수의 로컬 복사본만 변경할 수 있습니다.  
  
 프로시저를 호출할 경우 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)로 전달되는 모든 인수의 로컬 복사본을 만듭니다.  [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)가 전달된 각 인수에 대해 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 호출 코드에서 인수를 원본으로 사용하는 프로그래밍 요소에 대한 직접 참조를 프로시저 코드에 제공합니다.  
  
 호출 코드에 있는 내부 요소를 수정할 수 있고 인수에 `ByRef`를 전달하면 프로시저 코드는 직접 참조를 사용하여 호출 코드에 있는 요소의 값을 변경할 수 있습니다.  
  
## 내부 값 변경  
  
#### 호출 코드에 있는 프로시저 인수의 내부 값을 변경하려면  
  
1.  프로시저 선언에서 인수에 해당하는 매개 변수에 대해 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)를 지정합니다.  
  
2.  호출 코드에서 수정할 수 있는 프로그래밍 요소를 인수로 전달합니다.  
  
3.  호출 코드에서 인수 목록의 인수를 괄호로 묶지 않습니다.  
  
4.  프로시저 코드에서 매개 변수 이름을 사용하여 호출 코드에 있는 내부 요소에 값을 할당합니다.  
  
 실례는 아래 쪽에 나와 있는 예제를 참조하십시오.  
  
## 로컬 복사본 변경  
 호출 코드에 있는 내부 요소를 수정할 수 없거나 인수에 `ByVal`을 전달한 경우 프로시저는 호출 코드에서 해당 값을 변경할 수 없습니다.  그러나 프로시저는 이러한 인수의 로컬 복사본을 변경할 수 있습니다.  
  
#### 프로시저 코드에 있는 프로시저 인수의 복사본을 변경하려면  
  
1.  프로시저 선언에서 인수에 해당하는 매개 변수에 대해 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)을 지정합니다.  
  
     또는  
  
     호출 코드에서 인수 목록의 인수를 괄호로 묶습니다.  이렇게 하면 해당 매개 변수에서 `ByRef`를 지정하더라도 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 인수를 값으로 전달합니다.  
  
2.  프로시저 코드에서 매개 변수 이름을 사용하여 인수의 로컬 복사본에 값을 할당합니다.  호출 코드에 있는 내부 값은 변경되지 않습니다.  
  
## 예제  
 다음 예제에서는 배열 변수를 받아 그 요소로 작업하는 두 개의 프로시저를 보여 줍니다.  `increase` 프로시저는 각 요소에 1만 더합니다.  `replace` 프로시저는 `a()` 매개 변수에 새 배열을 할당한 다음 각 요소에 1씩 더합니다.  
  
 [!code-vb[VbVbcnProcedures#35](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#36](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#37](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_3.vb)]  
  
 첫 번째 `MsgBox` 호출에서는 "After increase\(n\): 11, 21, 31, 41"이 표시됩니다.   `n` 배열이 참조 형식이기 때문에 전달 메커니즘이 `ByVal`인 경우에도 `replace`에서 해당 멤버를 변경할 수 있습니다.  
  
 두 번째 `MsgBox` 호출은 "After replace\(n\): 101, 201, 301"을 표시합니다.  `n`에는 `ByRef`가 전달되므로  `replace` 가 호출 코드에서  `n`  변수를 수정하고 이 변수에 새 배열을 할당할 수 있습니다.   `n` 이 참조 형식이므로  `replace` 는 해당 멤버 또한 변경할 수 있습니다.  
  
 호출 코드에서 프로시저가 변수 자체를 수정하지 못하도록 방지할 수 있습니다.  [How to: Protect a Procedure Argument Against Value Changes](../../../../visual-basic/programming-guide/language-features/procedures/how-to-protect-a-procedure-argument-against-value-changes.md)를 참조하십시오.  
  
## 코드 컴파일  
 변수를 참조로 전달할 경우 `ByRef` 키워드를 사용하여 이 메커니즘을 지정해야 합니다.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 기본적으로 인수를 값으로 전달합니다.  그러나 선언된 모든 매개 변수에 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 또는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 키워드를 사용하는 것이 바람직한 프로그래밍 습관입니다.  그러면 코드를 읽기가 더 쉽습니다.  
  
## .NET Framework 보안  
 호출 코드에서 내부 인수로 사용하는 값을 프로시저에서 변경하도록 허용하는 것은 항상 잠재적인 위험을 갖고 있습니다.  따라서 이 값이 변경될 것을 예상해야 하고 값을 사용하기 전에 유효성을 검사할 수 있도록 준비해야 합니다.  
  
## 참고 항목  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [How to: Pass Arguments to a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Passing Arguments by Value and by Reference](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Differences Between Modifiable and Nonmodifiable Arguments](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md)   
 [Differences Between Passing an Argument By Value and By Reference](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)   
 [How to: Protect a Procedure Argument Against Value Changes](../../../../visual-basic/programming-guide/language-features/procedures/how-to-protect-a-procedure-argument-against-value-changes.md)   
 [How to: Force an Argument to Be Passed by Value](../Topic/How%20to:%20Force%20an%20Argument%20to%20Be%20Passed%20by%20Value%20\(Visual%20Basic\).md)   
 [Passing Arguments by Position and by Name](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)