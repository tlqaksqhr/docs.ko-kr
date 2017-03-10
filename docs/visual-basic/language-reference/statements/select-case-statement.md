---
title: "Select...Case Statement (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Select"
  - "vb.Case"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Select statement"
  - "Case statement"
  - "Select...Case statements"
  - "conditional statements, Select Case"
  - "control flow, branching"
  - "Else keyword [Visual Basic], in Select...Case statements"
  - "execution, conditional"
  - "To keyword, in Select...Case statements"
  - "Select Case statement, Select...Case"
  - "Select statement, Select...Case"
  - "Is operator [Visual Basic], in Select...Case statements"
  - "branching, conditional"
  - "Case Else statement, Select...Case"
  - "End keyword, Select Case statements"
  - "Case statement, Select...Case"
ms.assetid: 68877b65-5419-4bf0-a465-20cd0e4c7d44
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Select...Case Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

식의 값에 따라 여러 문 그룹 중 하나를 실행합니다.  
  
## 구문  
  
```  
Select [ Case ] testexpression  
    [ Case expressionlist  
        [ statements ] ]  
    [ Case Else  
        [ elsestatements ] ]  
End Select  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`testexpression`|필수 요소.  식입니다.  `Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, `UShort` 등의 기본 데이터 형식 중 하나로 계산되어야 합니다.|  
|`expressionlist`|`Case` 문에서는 필수적 요소입니다.  `testexpression`에 대한 일치 값을 나타내는 식 절의 목록입니다.  식 절이 여러 개 있으면 쉼표로 구분됩니다.  각 절에는 다음과 같은 형태 중 하나를 사용할 수 있습니다.<br /><br /> -   *expression1* `To` *expression2*<br />-   \[ `Is` \] *comparisonoperator* *expression*<br />-   *expression*<br /><br /> `To` 키워드를 사용하여 `testexpression`에 대한 일치 값 범위의 경계를 지정합니다.  `expression1`의 값은 `expression2`의 값보다 작거나 같아야 합니다.<br /><br /> `Is` 키워드를 비교 연산자\(`=`, `<>`, `<`, `<=`, `>` 또는 `>=`\)와 함께 사용하여 `testexpression`에 대한 일치 값을 제한합니다.  `Is` 키워드를 입력하지 않아도 *comparisonoperator* 앞에 자동으로 삽입됩니다.<br /><br /> `expression`만 지정하는 형태는 `Is` 형태의 특수한 경우로 처리되고, *comparisonoperator*로 등호\(`=`\)가 사용됩니다.  따라서 이 형태는 `testexpression` \= `expression`으로 계산됩니다.<br /><br /> `expressionlist`의 식이 암시적으로 `testexpression` 형식으로 변환될 수 있고, 함께 사용되는 두 형식에 대해 해당 `comparisonoperator`가 유효하면 expressionlist의 식은 모든 데이터 형식을 사용할 수 있습니다.|  
|`statements`|선택적 요소.  `testexpression`이 `expressionlist`에 있는 절과 일치하면 실행되며 `Case` 다음에 오는 하나 이상의 문입니다.|  
|`elsestatements`|선택적 요소.  `testexpression`이 `Case` 문의 `expressionlist`에 있는 절과 일치하지 않으면 실행되며 `Case Else` 다음에 오는 하나 이상의 문입니다.|  
|`End Select`|`Select`...`Case` 구문의 정의를 종료합니다.|  
  
## 설명  
 `testexpression`이 `Case` `expressionlist` 절과 일치하면 다음 `Case`, `Case Else` 또는 `End Select` 문을 실행하는 `Case` 다음에 오는 문입니다.  그러면 `End Select` 다음에 오는 문으로 제어가 전달됩니다.  `testexpression`이 둘 이상의 `Case` 절에 있는 `expressionlist` 절과 일치하면 첫 번째 일치를 실행한 다음에 나오는 문입니다.  
  
 `Case Else` 문은 다른 `Case` 문의 `testexpression`과 `expressionlist` 절이 일치하지 않는 경우 실행되는 `elsestatements`를 나타낼 때 사용됩니다.  필수적인 사항은 아니지만 `Select Case` 구문에 `Case Else` 문을 사용하여 예기치 않은 `testexpression` 값을 처리하는 것이 좋습니다.  `Case` `expressionlist` 절이 `testexpression`과 일치하지 않고 `Case Else` 문이 없으면 `End Select` 다음에 오는 문으로 제어가 전달됩니다.  
  
 각 `Case` 절 안에서 여러 개의 식이나 범위를 사용할 수 있습니다.  예를 들어, 다음과 같은 줄을 사용할 수 있습니다.  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
>  `Case` 및 `Case Else` 문에 사용되는 `Is` 키워드는 개체 참조 비교에 사용되는 [Is Operator](../../../visual-basic/language-reference/operators/is-operator.md)와 같지 않습니다.  
  
 또한 문자열에 대해 범위와 여러 개의 식을 지정할 수도 있습니다.  다음 예제에서 `Case`는 "apples"와 정확하게 같은 문자열과 일치하거나 알파벳 순서로 "nuts"와 "soup" 사이의 값을 가지고 있거나 `testItem`의 현재 값과 정확하게 같은 값을 포함하고 있습니다.  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 `Option Compare`의 설정에 따라 문자열 비교가 달라질 수 있습니다.  `Option Compare Text`에서는 "Apples"와 "apples"가 같지만 `Option Compare Binary`에서는 두 값이 서로 다릅니다.  
  
> [!NOTE]
>  여러 절이 있는 `Case` 문은 *단락\(short circuit\)*이라고 하는 동작을 사용할 수 있습니다.  Visual Basic에서는 이 절을 왼쪽에서 오른쪽으로 계산하며 `testexpression`과 일치하는 절이 있으면 나머지 절을 계산하지 않습니다.  단락\(short circuit\)을 사용하면 성능을 향상시킬 수 있지만 계산될 `expressionlist`에 있는 각 식에 예상치 못한 결과가 발생할 수 있습니다.  단락\(short circuit\)에 대한 자세한 내용은 [Boolean Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)을 참조하십시오.  
  
 `Case` 또는 `Case Else` 문 블록 내에 있는 코드가 블록 내의 문을 더 이상 실행할 필요가 없는 경우에는 `Exit Select` 문을 사용하여 블록을 종료할 수 있습니다.  그러면 `End Select` 문 다음에 오는 문으로 제어권이 즉시 전달됩니다.  
  
 `Select Case` 구문은 중첩될 수 있습니다.  중첩된 각 `Select Case` 구문에는 일치하는 `End Select` 문이 있어야 하며 중첩된 Select Case 구문의 내부에 있는 외부 `Select Case` 구문의 `Case` 또는 `Case Else` 문 블록 내에 완전히 포함되어야 합니다.  
  
## 예제  
 다음 예제에서는 `Select Case` 구문을 사용하여 변수 `number`의 값에 해당하는 줄을 씁니다.  두 번째 `Case` 문에는 `number`의 현재 값과 일치하는 값이 들어 있으므로 "Between 6 and 8, inclusive"를 쓰는 문이 실행됩니다.  
  
 [!code-vb[VbVbalrStatements#54](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/select-case-statement_1.vb)]  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>   
 [End Statement](../../../visual-basic/language-reference/statements/end-statement.md)   
 [If...Then...Else Statement](../../../visual-basic/language-reference/statements/if-then-else-statement.md)   
 [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md)   
 [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)