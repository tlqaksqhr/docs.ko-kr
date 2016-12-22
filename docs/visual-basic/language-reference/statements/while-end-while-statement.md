---
title: "While...End While Statement (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.While"
  - "vb.While...EndWhile"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "While statement, While...End While"
  - "While statement"
  - "While...End While statements"
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# While...End While Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

지정한 조건이 `True`인 동안 일련의 문을 계속 실행합니다.  
  
## 구문  
  
```  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`condition`|필수 요소.  `Boolean` 식입니다.  `condition`이 `Nothing`이면 Visual Basic에서 `False`로 간주합니다.|  
|`statements`|선택 사항입니다.  `While` 다음에 오는 하나 이상의 문이며 `condition`이 `True`일 때마다 실행됩니다.|  
|`Continue While`|선택 사항입니다.  다음 반복으로 제어를 전달 된 `While` 블록.|  
|`Exit While`|선택 사항입니다.  `While` 블록의 외부로 제어를 전송합니다.|  
|`End While`|필수 요소.  이 `While` 블록의 정의를 마칩니다.|  
  
## 설명  
 조건이 `True`인 동안 문을 무한히 반복하려면 `While...End While` 구조를 사용합니다.  조건을 테스트하는 위치나 테스트 결과에 융통성을 주려면 [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md)을 사용하는 것이 보다 나을 수도 있습니다.  문을 지정된 횟수만큼 반복하려면 [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)을 사용하는 것이 좋습니다.  
  
> [!NOTE]
>  `While` 키워드는 [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md), [Skip While Clause](../../../visual-basic/language-reference/queries/skip-while-clause.md) 및 [Take While Clause](../../../visual-basic/language-reference/queries/take-while-clause.md)에서도 사용됩니다.  
  
 `condition`이 `True`이면 `End While` 문이 나타날 때까지 모든 `statements`가 실행됩니다.  제어를 반환 하는 `While` 문 및 `condition` 다시 검사 됩니다.  `condition`이 계속 `True`이면 해당 프로세스가 반복되고  경우 `False`, 다음에 오는 문에 전달 제어는 `End While` 문.  
  
 `While` 문은 항상 루프를 시작 하기 전에 조건을 검사 합니다.  조건이 `True`인 동안 루프가 계속 실행됩니다.  경우 `condition` 는 `False` 루프를 처음 입력할 때 한 번도 실행 되지 않습니다.  
  
 `condition` 일반적으로 있지만 두 값의 결과를 비교 평가 되는 식 수는 [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) 값 \(`True` 또는 `False`\).  이 식은 숫자 형식으로 변환 된 다른 데이터 형식의 값을 포함할 수 있습니다 `Boolean`.  
  
 한 루프를 다른 루프 내에 배치하여 `While` 루프를 서로 중첩할 수 있습니다.  또한 하나의 With...End With 구조 내에 다른 종류의 제어 구조를 중첩할 수 있습니다.  자세한 내용은 [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)를 참조하십시오.  
  
## 종료 하는 동안  
 [를 종료 하는 동안](../../../visual-basic/language-reference/statements/exit-statement.md) 문을 종료 하는 다른 방법으로 제공할 수 있습니다는 `While` 루프.  `Exit While`바로 다음에 오는 문으로 제어를 전달 된 `End While` 문.  
  
 일반적으로 사용 `Exit While` 일부 조건을 계산 하면 \(예를 들어,는 `If...Then...Else` 구조\).  예를 들어, 잘못된 값이나 종료 요청과 같이 계속 반복할 필요가 없거나 반복할 수 없는 조건을 발견하면 루프를 끝내야 할 수 있습니다.  사용할 수 있는 `Exit While` 인해 조건에 대 한 테스트는  *무한 루프*, 루프는 매우 크고도 무한 횟수 만큼 실행 될 수 있는.  다음 `Exit While` 루프를.  
  
 `While` 루프 어디서나 많은 `Exit While` 문을 배치할 수 있습니다.  
  
 중첩된 `While` 루프 내에 `Exit While`를 사용하면 Exit Do는 가장 안쪽 루프 밖의 제어를 중첩 수준이 그 다음으로 높은 루프에 전달합니다.  
  
 `Continue While` 문은 즉시 전송 제어 루프의 다음 반복으로 합니다.  자세한 내용은 [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md)를 참조하십시오.  
  
## 예제  
 다음 예에서 루프의 문은 `index` 변수가 10보다 커질 때까지 계속 실행됩니다.  
  
 [!code-vb[VbVbalrStatements#171](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/while-end-while-statement_1.vb)]  
  
## 예제  
 다음 예제에서는 `Continue While` 및 `Exit While` 문을 사용하는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrStatements#172](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/while-end-while-statement_2.vb)]  
  
## 예제  
 다음 예제에서는 텍스트 파일의 모든 줄을 읽습니다.  <xref:System.IO.File.OpenText%2A> 메서드는 파일을 열고 문자를 읽는 <xref:System.IO.StreamReader>를 반환합니다.  에 `While` 조건을 <xref:System.IO.StreamReader.Peek%2A> 메서드는 `StreamReader` 파일 추가 문자가 포함 되어 있는지 여부를 결정.  
  
 [!code-vb[VbVbalrStatements#173](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/while-end-while-statement_3.vb)]  
  
## 참고 항목  
 [Loop Structures](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md)   
 [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md)   
 [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)   
 [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md)