---
title: If...Then...Else 문(Visual Basic)
ms.date: 04/16/2018
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: conceptual
f1_keywords:
- vb.ElseIf
- vb.Then
- vb.If
- vb.EndIf
helpviewer_keywords:
- ElseIf statement [Visual Basic], If...Then...Else
- Then statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], branching
- execution [Visual Basic], conditional
- TypeOf...Is expression, and If...Then...Else statements
- If...Then...Else statements
- If statement [Visual Basic], If...Then...Else
- If statement [Visual Basic]
- Is operator [Visual Basic], in If...Then...Else statements
- If Operator [Visual Basic]
- branching [Visual Basic], conditional
- If function [Visual Basic], and If...Then...Else statements
- Else statement [Visual Basic]
ms.assetid: 790068a2-1307-4e28-8a72-be5ebda099e9
caps.latest.revision: 29
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1080a17cfcc493175c1e2f3527837030b4254bc2
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="ifthenelse-statement-visual-basic"></a>If...Then...Else 문(Visual Basic)
식의 값에 따라 문 그룹을 조건부로 실행합니다.  
  
## <a name="syntax"></a>구문  
  
```  
' Multiline syntax:  
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

## <a name="quick-links-to-example-code"></a>예제 코드에 대 한 빠른 링크

이 문서 포함의 용도 설명 하는 샘플 몇 가지 예는 `If`... `Then`... `Else` 문:

* [여러 줄로 된 구문 예제](#multi-line)
* [중첩 된 구문 예제](#nested)
* [한 줄 구문 예제](#single-line)

## <a name="parts"></a>요소  
 `condition`  
 필수. 식입니다. 로 계산 되어야 `True` 또는 `False`, 또는로 암시적으로 변환할 수 있는 데이터 형식 `Boolean`합니다.  
  
 식이 [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` 변수 [Nothing](../../../visual-basic/language-reference/nothing.md), 조건 식은 처럼 처리 됩니다 `False` 및 `Else` 블록이 실행 됩니다.  
  
 `Then`  
 한 줄 구문;에 필요한 여러 줄 구문에서 선택 사항입니다.  
  
 `statements`  
 선택 사항입니다. 하나 이상의 문 다음 `If`... `Then` 경우 실행 되는 `condition` 계산 `True`합니다.  
  
 `elseifcondition`  
 필요한 경우 `ElseIf` 있는 합니다. 식입니다. 로 계산 되어야 `True` 또는 `False`, 또는로 암시적으로 변환할 수 있는 데이터 형식 `Boolean`합니다.  
  
 `elseifstatements`  
 선택 사항입니다. 하나 이상의 문 다음 `ElseIf`... `Then` 경우 실행 되는 `elseifcondition` 계산 `True`합니다.  
  
 `elsestatements`  
 선택 사항입니다. 앞에 나오는 경우 실행 되는 하나 이상의 문 `condition` 또는 `elseifcondition` 식이 `True`합니다.  
  
 `End If`  
 여러 줄로 된 버전의 종료 `If`... `Then`... `Else` 블록입니다.  
  
## <a name="remarks"></a>설명  
  
### <a name="multiline-syntax"></a>여러 줄 구문  
 경우는 `If`... `Then`... `Else` 문이 실행 될 `condition` 테스트 됩니다. 경우 `condition` 은 `True`, 다음 문을 `Then` 실행 됩니다. 경우 `condition` 은 `False`, 각 `ElseIf` 문 (있는 경우) 순서로 평가 됩니다. 경우는 `True` `elseifcondition` 발견 되 면 바로 다음에 관련 된 문을 `ElseIf` 실행 됩니다. 없는 경우 `elseifcondition` 계산 `True`, 없는 경우 또는 없습니다 `ElseIf` 다음 문은 `Else` 실행 됩니다. 다음 문을 실행 한 후 `Then`, `ElseIf`, 또는 `Else`, 실행이 계속 다음 문으로 `End If`합니다.  
  
 `ElseIf` 및 `Else` 절은 모두 선택적 요소입니다. 만큼 가질 수 `ElseIf` 때 절에서 원하는 `If`... `Then`... `Else` 문은 되지만 아니요 `ElseIf` 절 뒤에 나타날 수는 `Else` 절. `If`... `Then`... `Else` 문은은 서로 중첩 될 수 있습니다.  
  
 여러 줄로 된 구문에는 `If` 문은 첫 번째 줄에서 유일한 문 이어야 합니다. `ElseIf`, `Else`, 및 `End If` 문 앞에 줄 레이블을 나와야 합니다. `If`... `Then`... `Else` 로 끝나야 합니다. 블록은 `End If` 문.  
  
> [!TIP]
>  [선택... Case 문](../../../visual-basic/language-reference/statements/select-case-statement.md) 가능한 값이 여러 개 있는 단일 식을 계산 하는 경우 더 유용할 수 있습니다.  
  
### <a name="single-line-syntax"></a>한 줄 구문  
 True 일 경우 실행할 코드를 사용 하 여 단일 조건 단일 인라인 구문을 사용할 수 있습니다. 그러나 다중 인라인 구문을 유연성과 구조를 제공 하며 읽고 유지 관리 하 고, 디버깅 하기가 더 쉽습니다.  
  
 다음은 `Then` 키워드를 검사 하는 문을 한 줄 인지 확인 `If`합니다. 주석 이외의 뒤에 표시 하는 경우 `Then` 같은 줄에는 문을 한 줄으로 처리 됩니다 `If` 문. 경우 `Then` 이 없음, 여러 줄의 시작 해야 `If`... `Then`... `Else`.  
  
 한 줄 구문에서의 결과로 실행 하는 여러 개의 문을 포함할 수 있습니다는 `If`... `Then` 의사 결정 합니다. 모든 문이 같은 줄에 있어야 하며 콜론으로 구분 되어야 합니다.  

## <a name="multiline-syntax-example"></a>여러 줄로 된 구문 예제

<a name="multi-line"></a>
 
 다음 예제에서는 여러 줄 구문의 사용을 보여 줍니다.는 `If`... `Then`... `Else` 문.  
  
 [!code-vb[VbVbalrStatements#101](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_1.vb?highlight=11,14,17,19)]

## <a name="nested-syntax-example"></a>중첩 된 구문 예제

<a name="nested"></a>

 다음 예제에는 중첩 된 `If`... `Then`... `Else` 문.  
  
 [!code-vb[VbVbalrStatements#102](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_2.vb?highlight=14,15,17,19,20,21,23,25,26,28)]

## <a name="single-line-syntax-example"></a>한 줄 구문 예제
  
<a name="single-line"></a> 다음 예제는 한 줄 구문 사용 합니다.  
  
 [!code-vb[VbVbalrStatements#103](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_3.vb?highlight=18)]
  
## <a name="see-also"></a>참고자료  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>  
 <xref:Microsoft.VisualBasic.Interaction.Switch%2A>  
 [#If...Then...#Else 지시문](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [Select...Case 문](../../../visual-basic/language-reference/statements/select-case-statement.md)  
 [중첩 제어 구조](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [판단 구조](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [Visual Basic의 논리 및 비트 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [If 연산자](../../../visual-basic/language-reference/operators/if-operator.md)
