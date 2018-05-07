---
title: While...End While 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.While
- vb.While...EndWhile
helpviewer_keywords:
- While statement [Visual Basic], While...End While
- While statement [Visual Basic]
- While...End While statements [Visual Basic]
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
ms.openlocfilehash: 9f46a6ec65faef4448bdd25e30a6cc0c605cd0f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="whileend-while-statement-visual-basic"></a>While...End While 문(Visual Basic)
지정한 조건이으로 일련의 문 실행 `True`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`condition`|필수. `Boolean` 식입니다. 경우 `condition` 은 `Nothing`, Visual Basic로 처리 `False`합니다.|  
|`statements`|선택 사항입니다. 하나 이상의 문 다음 `While`, 때마다 실행 `condition` 은 `True`합니다.|  
|`Continue While`|선택 사항입니다. 다음 반복으로 제어를 전달는 `While` 블록입니다.|  
|`Exit While`|선택 사항입니다. 밖으로 제어를 전송에서 `While` 블록입니다.|  
|`End While`|필수. `While` 블록의 정의를 종료합니다.|  
  
## <a name="remarks"></a>설명  
 사용 하 여 한 `While...End While` 조건이으로 문을 번 무한히 반복 하려는 경우 구조체 `True`합니다. 조건을 테스트 하는 위치 또는 결과 합니다 유연한이 할 것에 대 한 테스트 하려는 경우는 [수행... 문은 루프](../../../visual-basic/language-reference/statements/do-loop-statement.md)합니다. 문을 횟수 만큼 반복 하려는 경우는 [에 대 한... 다음 문](../../../visual-basic/language-reference/statements/for-next-statement.md) 일반적으로 것이 좋습니다.  
  
> [!NOTE]
>  `While` 키워드는 또한는 [수행... 문은 루프](../../../visual-basic/language-reference/statements/do-loop-statement.md), [Skip While 절](../../../visual-basic/language-reference/queries/skip-while-clause.md) 및 [Take While 절](../../../visual-basic/language-reference/queries/take-while-clause.md)합니다.  
  
 경우 `condition` 은 `True`모든의 `statements` 실행 될 때까지 `End While` 문이 합니다. 돌아올 제어는 `While` 문, 및 `condition` 를 다시 확인 합니다. 경우 `condition` 여전히 `True`, 프로세스를 반복 합니다. 설정한 경우 `False`, 제어 뒤에 오는 문으로 전달은 `End While` 문.  
  
 `While` 문은 항상 루프를 시작 하기 전에 조건을 확인 합니다. 조건이 동안 계속 반복 `True`합니다. 경우 `condition` 은 `False` 루프 처음 입력할 때 실행 되는 한 번도 합니다.  
  
 `condition` 일반적으로 두 값의 비교 결과로 계산 되는 식일 수는 [Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md) 값 (`True` 또는 `False`). 이 식은로 변환 된 하는 숫자 형식과 같은 다른 데이터 형식의 값을 포함할 수 있습니다 `Boolean`합니다.  
  
 중첩할 수 `While` 서로 배치 하 여 루프입니다. 또한 다른 종류의 제어 구조를 중첩할 수 있습니다. 자세한 내용은 참조 [중첩 제어 구조](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)합니다.  
  
## <a name="exit-while"></a>종료 하는 동안  
 [종료 동안](../../../visual-basic/language-reference/statements/exit-statement.md) 문을 종료 하는 다른 방법은 제공할 수는 `While` 루프입니다. `Exit While` 바로 뒤에 오는 문으로 제어를 전송에서 `End While` 문.  
  
 일반적으로 사용 `Exit While` 일부 조건이 계산 된 후 (예를 들어 한 `If...Then...Else` 구조). 불필요 하거나 잘못 된 값 이나 종료 요청 같이 계속 반복할 수 있게 해 주는 조건을 발견 하면 루프를 끝낼 할 수 있습니다. 사용할 수 있습니다 `Exit While` 를 일으킬 수 있는 조건에 대 한 테스트는 *무한 루프*, 상태가 매우 크거나 무한도 가능 여러 번 실행 될 수 있는 합니다. 사용할 수 있습니다 `Exit While` 루프를 이스케이프 합니다.  
  
 개수에 관계 없이 배치할 수 `Exit While` 의 아무 곳 이나 문에서 `While` 루프입니다.  
  
 사용할 경우 내에 중첩 `While` 루프, `Exit While` 제어 하며 다음 상위 수준의 중첩이 가장 안쪽 루프 밖으로 전달 합니다.  
  
 `Continue While` 문은 루프의 다음 반복으로 즉시 제어를 전달 합니다. 자세한 내용은 참조 [Continue 문을](../../../visual-basic/language-reference/statements/continue-statement.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 루프에서 계속 실행 될 때까지 `index` 변수 10 보다 큽니다.  
  
 [!code-vb[VbVbalrStatements#171](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/while-end-while-statement_1.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Continue While` 및 `Exit While` 문.  
  
 [!code-vb[VbVbalrStatements#172](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/while-end-while-statement_2.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 텍스트 파일에 있는 모든 줄을 읽습니다. <xref:System.IO.File.OpenText%2A> 메서드는 파일을 열고 반환는 <xref:System.IO.StreamReader> 는 문자를 읽는 합니다. 에 `While` 조건은 <xref:System.IO.StreamReader.Peek%2A> 의 메서드는 `StreamReader` 파일에 추가 문자가 포함 되어 있는지 확인 합니다.  
  
 [!code-vb[VbVbalrStatements#173](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/while-end-while-statement_3.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [루프 구조](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Do...Loop 문](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md)  
 [중첩 제어 구조](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Exit 문](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [Continue 문](../../../visual-basic/language-reference/statements/continue-statement.md)
