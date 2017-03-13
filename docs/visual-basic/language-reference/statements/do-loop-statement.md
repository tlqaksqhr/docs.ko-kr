---
title: "Do...Loop Statement (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Do"
  - "vb.Loop"
  - "vb.Until"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "conditional statements, Do…Loop"
  - "while statement, Do...Loop"
  - "execution, conditional"
  - "Do loops"
  - "Until keyword, Do...Loop statement"
  - "Do...Loop statement"
  - "instructions, repeating"
  - "Do statement"
  - "Exit statement, in Do...Loop statements"
  - "loop structures, Do…Loop statements"
  - "do-while statements"
  - "loops, exiting"
  - "Loop keyword, Do...Loop statement"
ms.assetid: 892f9096-b3e2-4aee-834d-83bc4e2c379d
caps.latest.revision: 37
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 37
---
# Do...Loop Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`Boolean` 조건이 `True`인 동안 또는 해당 조건이 `True`가 될 때까지 문의 블록을 반복합니다.  
  
## 구문  
  
```  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
-or-  
Do  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop { While | Until } condition  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`Do`|필수 요소.  `Do` 루프의 정의를 시작합니다.|  
|`While`|`Until`이 사용되지 않는 경우 필수적 요소입니다.  `condition`이 `False`가 될 때까지 루프를 반복합니다.|  
|`Until`|`While`이 사용되지 않는 경우 필수적 요소입니다.  `condition`이 `True`가 될 때까지 루프를 반복합니다.|  
|`condition`|선택 사항입니다.  `Boolean` 식입니다.  `condition`이 `Nothing`이면 Visual Basic에서 `False`로 간주합니다.|  
|`statements`|선택 사항입니다.  `condition`이 `True`인 동안 또는 True가 될 때까지 반복되는 하나 이상의 문입니다.|  
|`Continue Do`|선택 사항입니다.  다음 반복으로 제어를 전달 된 `Do` 루프.|  
|`Exit Do`|선택 사항입니다.  `Do` 루프 밖으로 제어를 전송합니다.|  
|`Loop`|필수 요소.  `Do` 루프의 정의를 끝냅니다.|  
  
## 설명  
 조건이 충족될 때까지 문을 무한히 반복하려면 `Do...Loop` 구조를 사용합니다.  문을 지정된 횟수만큼 반복하려면 [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)을 사용하는 것이 좋습니다.  
  
 `While` 또는 `Until` 중 하나를 사용하여 `condition`을 지정할 수 있으며 둘 다 사용할 수는 없습니다.  
  
 루프의 시작 부분이나 끝 부분에서 `condition`을 한 번만 테스트할 수 있습니다.  루프의 시작 부분에 있는 `Do` 문에서 `condition`을 테스트하는 경우 루프가 한 번도 실행되지 않을 수 있습니다.  `Loop` 문의 루프 끝 부분에서 테스트하는 경우 루프는 항상 한 번 이상 실행됩니다.  
  
 조건은 일반적으로 두 값을 비교해서 지정됩니다. 그러나 [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) 값\(`True` 또는 `False`\)이 되는 식도 조건이 될 수 있으며,  이런 경우 `Boolean`으로 변환된 다른 데이터 형식\(예: 숫자 형식\)의 값을 포함합니다.  
  
 한 루프를 다른 루프 내에 배치하여 `Do` 루프를 서로 중첩할 수 있습니다.  또한 다른 종류의 제어 구조를 서로 중첩할 수 있습니다.  자세한 내용은 [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)를 참조하십시오.  
  
> [!NOTE]
>  `Do...Loop` 구조를 사용하면 `condition`이 `True`에서 변경된 경우 또는 처음으로 `True`가 된 경우에 루프를 끝낼지 여부를 결정할 수 있으므로 [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md)을 사용하는 것보다 더 융통성 있습니다.  또한 루프의 시작 부분이나 끝 부분에서 `condition`을 테스트할 수 있습니다.  
  
## Exit Do  
 [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) 문은 `Do…Loop`를 종료하기 위한 대체 방법을 제공할 수 있습니다.  `Exit Do`를 사용하면 제어가 `Loop` 문 다음 문으로 바로 전달됩니다.  
  
 `Exit Do`는 `If...Then...Else` 구조와 마찬가지로 주로 일부 조건을 계산한 후에 사용됩니다.  예를 들어, 잘못된 값이나 종료 요청과 같이 계속 반복할 필요가 없거나 반복할 수 없는 조건을 발견하면 루프를 끝내야 할 수 있습니다.  `Exit Do`를 사용하여 조건이 *무한 루프* 상태가 되는지 여부를 테스트할 수도 있습니다. 무한 루프란 매우 많이 또는 무한정 실행되는 루프를 말합니다.  `Exit Do`를 사용하여 루프를 빠져 나올 수 있습니다.  
  
 `Do…Loop`의 아무 위치에 임의 수의 `Exit Do` 문을 포함시킬 수 있습니다.  
  
 중첩된 `Do` 루프 내에 `Exit Do`를 사용하면 Exit Do는 가장 안쪽 루프 밖의 제어를 중첩 수준이 그 다음으로 높은 루프에 전달합니다.  
  
## 예제  
 다음 예에서 루프의 문은 `index` 변수가 10보다 커질 때까지 계속 실행됩니다.  루프의 끝에 `Until` 절이 있습니다.  
  
 [!code-vb[VbVbalrStatements#131](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_1.vb)]  
  
## 예제  
 다음 예제에서는 `Until` 절 대신 `While` 절을 사용하며 루프의 끝 부분이 아닌 시작 부분에서 `condition`을 테스트합니다.  
  
 [!code-vb[VbVbalrStatements#132](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_2.vb)]  
  
## 예제  
 다음 예에서는 `index` 변수가 100보다 클 때 `condition`이 루프를 정지합니다.  하지만 루프에 `If` 문을 사용하면 인덱스 변수가 10보다 커질 때 `Exit Do` 문이 루프를 중단합니다.  
  
 [!code-vb[VbVbalrStatements#133](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_3.vb)]  
  
## 예제  
 다음 예제에서는 텍스트 파일의 모든 줄을 읽습니다.  <xref:System.IO.File.OpenText%2A> 메서드는 파일을 열고 문자를 읽는 <xref:System.IO.StreamReader>를 반환합니다.  `Do...Loop` 조건에서 `StreamReader`의 <xref:System.IO.StreamReader.Peek%2A> 메서드는 추가 문자가 있는지 여부를 판단합니다.  
  
 [!code-vb[VbVbalrStatements#134](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_4.vb)]  
  
## 참고 항목  
 [Loop Structures](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md)   
 [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)   
 [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md)