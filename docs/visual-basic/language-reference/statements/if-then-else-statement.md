---
title: "If...Then...Else Statement (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ElseIf"
  - "vb.Then"
  - "vb.If"
  - "vb.EndIf"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ElseIf statement, If...Then...Else"
  - "Then statement, If...Then...Else"
  - "control flow, branching"
  - "execution, conditional"
  - "TypeOf...Is expression, and If...Then...Else statements"
  - "If...Then...Else statements"
  - "If statement, If...Then...Else"
  - "If statement"
  - "Is operator [Visual Basic], in If...Then...Else statements"
  - "If Operator [Visual Basic]"
  - "branching, conditional"
  - "IIf function, and If...Then...Else statements"
  - "Else statement [Visual Basic]"
ms.assetid: 790068a2-1307-4e28-8a72-be5ebda099e9
caps.latest.revision: 29
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 29
---
# If...Then...Else Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

식의 값에 따라 문 그룹을 조건부로 실행합니다.  
  
## 구문  
  
```  
' Multiple-line syntax:  
If condition [ Then ]  
    [ statements ]  
[ ElseIf elseifcondition [ Then ]  
    [ elseifstatements ] ]  
[ Else  
    [ elsestatements ] ]  
End If  
  
' Single-line syntax:  
If condition Then [ statements ] [ Else [ elsestatements ] ]  
```  
  
## 요소  
 `condition`  
 필수 요소.  식입니다.  `True` 또는 `False`이거나 암시적으로 `Boolean`으로 변환할 수 있는 데이터 형식이어야 합니다.  
  
 기호는  [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)`Boolean` 산출 변수  [아무](../../../visual-basic/language-reference/nothing.md), 조건 식이 아닌 것 처럼 취급 됩니다 `True`, 및 `Else` 블록이 실행.  
  
 `Then`  
 한 줄 구문에서는 필수적 요소이고 여러 줄 구문에서는 선택적 요소입니다.  
  
 `statements`  
 선택 사항입니다.  `condition`이 `True`이면 실행되며 `If`...`Then` 다음에 오는 하나 이상의 문입니다.  
  
 `elseifcondition`  
 `ElseIf`가 있는 경우 필수적 요소로서,  식입니다.  `True` 또는 `False`이거나 암시적으로 `Boolean`으로 변환할 수 있는 데이터 형식이어야 합니다.  
  
 `elseifstatements`  
 선택 사항입니다.  `elseifcondition`이 `True`이면 실행되며 `ElseIf`...`Then` 다음에 오는 하나 이상의 문입니다.  
  
 `elsestatements`  
 선택 사항입니다.  앞에 나오는 `condition` 또는 `elseifcondition` 식이 `True`가 아니면 실행되는 하나 이상의 문입니다.  
  
 `End If`  
 `If`...`Then`...`Else` 블록을 끝냅니다.  
  
## 설명  
  
## 복수줄 구문  
 `If`...`Then`...`Else` 문을 만나면 `condition`이 테스트됩니다.  `condition`이 `True`이면 `Then` 다음에 오는 문이 실행되고  `condition`이 `False`이면 각 `ElseIf` 문\(있는 경우\)이 순서대로 실행됩니다.  `elseifcondition`이 `True`이면 연관된 `ElseIf`의 바로 다음에 오는 문이 실행됩니다.  `elseifcondition`이 `True`가 아니거나 `ElseIf` 문이 없으면 `Else` 다음에 오는 문이 실행됩니다.  `Then`, `ElseIf` 또는 `Else` 문 다음에 오는 문을 실행한 후에 `End If` 다음에 오는 문에서 실행이 계속됩니다.  
  
 `ElseIf` 및 `Else` 절은 모두 선택적 요소입니다.  `If`...`Then`...`Else` 문에 원하는 수의 `ElseIf` 절을 사용할 수는 있지만 `Else` 절 다음에는 `ElseIf` 절이 올 수 없습니다.  `If`...`Then`...`Else` 문은 서로 중첩할 수 있습니다.  
  
 여러 줄 구문에서는 첫 줄에 `If` 문만 있어야 합니다.  `ElseIf`, `Else` 및 `End If` 문은 줄 레이블 뒤에만 올 수 있습니다.  `If`...`Then`...`Else` 블록은 `End If` 문으로 끝나야 합니다.  
  
> [!TIP]
>  가능한 값이 여러 개 있는 단일 식을 계산하는 경우에는 [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md)를 사용하는 것이 좋습니다.  
  
## 단일줄 구문  
 짧고 간단한 테스트를 수행하는 경우 한 줄 구문을 사용할 수 있습니다.  그러나 여러 줄 구문은 많은 구조와 융통성을 제공하며, 일반적으로 읽고, 유지하고, 디버깅하기가 더 쉽습니다.  
  
 `Then` 키워드 다음에 오는 문을 검사하여 문이 한 줄 `If`인지를 판단합니다.  동일한 줄에서 `Then` 다음에 주석 이외의 다른 문이 오면 이 문은 한 줄 형태인 `If` 문으로 처리됩니다.  `Then`이 없는 경우 이 문은 여러 줄 `If`...`Then`...`Else` 문의 시작 부분이 되어야 합니다.  
  
 한 줄 구문에서는 `If`...`Then`의 결과에 따라 여러 개의 문을 실행할 수 있습니다.  모든 문은 같은 줄에 있어야 하며 콜론으로 구분되어야 합니다.  
  
## 예제  
 다음 예제는 `If`...`Then`...`Else` 문의 여러 줄로 된 구문 사용을 보여 줍니다.  
  
 [!code-vb[VbVbalrStatements#101](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_1.vb)]  
  
## 예제  
 다음 예제에는 중첩된 `If`...`Then`...`Else` 문이 포함되어 있습니다.  
  
 [!code-vb[VbVbalrStatements#102](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_2.vb)]  
  
## 예제  
 다음 예제에는 한 줄로 된 구문 사용을 보여 줍니다.  
  
 [!code-vb[VbVbalrStatements#103](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_3.vb)]  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>   
 <xref:Microsoft.VisualBasic.Interaction.Switch%2A>   
 [\#If...Then...\#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md)   
 [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md)   
 [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [Decision Structures](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)   
 [Logical and Bitwise Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)   
 [If Operator](../../../visual-basic/language-reference/operators/if-operator.md)