---
title: Do...Loop 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Do
- vb.Loop
- vb.Until
helpviewer_keywords:
- conditional statements [Visual Basic], Do�Loop
- while statement [Visual Basic], Do...Loop
- execution [Visual Basic], conditional
- Do loops
- Until keyword [Visual Basic], Do...Loop statement
- Do...Loop statement
- instructions, repeating
- Do statement [Visual Basic]
- Exit statement [Visual Basic], in Do...Loop statements
- loop structures [Visual Basic], Do�Loop statements
- do-while statements [Visual Basic]
- loops, exiting
- Loop keyword [Visual Basic], Do...Loop statement
ms.assetid: 892f9096-b3e2-4aee-834d-83bc4e2c379d
ms.openlocfilehash: e12cdc1ae405b877d4d27d1947c98dcb51938ba7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604941"
---
# <a name="doloop-statement-visual-basic"></a>Do...Loop 문(Visual Basic)
동안 문 블록을 반복 하는 `Boolean` 조건이 `True` 조건이 있을 때까지 또는 `True`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
-or-  
Do  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop { While | Until } condition  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`Do`|필수. 시작의 정의 `Do` 루프입니다.|  
|`While`|`Until`를 사용하는 경우를 제외하고는 필수입니다. 반복 될 때까지 루프 `condition` 은 `False`합니다.|  
|`Until`|`While`를 사용하는 경우를 제외하고는 필수입니다. 반복 될 때까지 루프 `condition` 은 `True`합니다.|  
|`condition`|선택 사항입니다. `Boolean` 식입니다. 경우 `condition` 은 `Nothing`, Visual Basic로 처리 `False`합니다.|  
|`statements`|선택 사항입니다. 동안 또는 하기 전 까지는 반복 되는 하나 이상의 문을 `condition` 은 `True`합니다.|  
|`Continue Do`|선택 사항입니다. 다음 반복으로 제어를 전달는 `Do` 루프입니다.|  
|`Exit Do`|선택 사항입니다. 밖으로 제어를 전송에서 `Do` 루프입니다.|  
|`Loop`|필수. 정의 종료는 `Do` 루프입니다.|  
  
## <a name="remarks"></a>설명  
 사용 하 여 한 `Do...Loop` 조건이 충족 될 때까지 여러 번 무한히 문 집합을 반복할 때 구성 합니다. 문을 횟수 만큼 반복 하려는 경우는 [에 대 한... 다음 문](../../../visual-basic/language-reference/statements/for-next-statement.md) 일반적으로 것이 좋습니다.  
  
 사용할 수 있습니다 `While` 또는 `Until` 지정 하려면 `condition`, 둘 중 하나입니다.  
  
 테스트할 수 `condition` 시작 부분이 나 루프의 끝에만 한 번입니다. 테스트 하는 경우 `condition` 루프가 시작 될 때 (에 `Do` 문), 루프가 한 번도 실행 되지 않을 수 있습니다. 루프의 끝에서 테스트 하는 경우 (에 `Loop` 문), 루프는 항상 한 번 이상 실행 합니다.  
  
 두 값의 비교에서 조건 일반적으로 발생 하지만 모든 식으로 계산 되는 [Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md) 값 (`True` 또는 `False`). 예: 숫자 형식으로 변환 된 다른 데이터 형식의 값을 포함이 `Boolean`합니다.  
  
 중첩할 수 `Do` 서로 배치 하 여 루프입니다. 서로 다른 제어 구조가 서로 중첩할 수도 있습니다. 자세한 내용은 참조 [중첩 제어 구조](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)합니다.  
  
> [!NOTE]
>  `Do...Loop` 구조 보다 더 많은 유연성을 제공 된 [동안... End While 문](../../../visual-basic/language-reference/statements/while-end-while-statement.md) 하면 루프를 끝내 여부를 결정할 수 있기 때문에 때 `condition` 중지 되 `True` 되거나 먼저 `True`합니다. 테스트할 수도 있습니다 `condition` 시작 부분이 나 루프의 끝에 있습니다.  
  
## <a name="exit-do"></a>종료 안 함  
 [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) 문을 종료 하는 다른 방법으로 제공할 수는 `Do…Loop`합니다. `Exit Do` 뒤에 오는 문으로 제어를 즉시 전달는 `Loop` 문.  
  
 `Exit Do` 일부 조건이 계산에 사용 예는 대개는 `If...Then...Else` 구조입니다. 불필요 하거나 잘못 된 값 이나 종료 요청 같이 계속 반복할 수 있게 해 주는 조건을 발견 하면 루프를 끝낼 할 수 있습니다. 용도 중 하나 `Exit Do` 를 일으킬 수 있는 조건에 대해 테스트 하는 *무한 루프*, 상태가 대형 또는 무한도 가능 여러 번 실행 될 수 있는 합니다. 사용할 수 있습니다 `Exit Do` 루프를 이스케이프 합니다.  
  
 개수에 관계 없이 포함할 수 있습니다 `Exit Do` 의 아무 곳 이나 문에서 `Do…Loop`합니다.  
  
 사용할 경우 내에 중첩 `Do` 루프, `Exit Do` 제어 하며 다음 상위 수준의 중첩이 가장 안쪽 루프 밖으로 전달 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 루프에서 계속 실행 될 때까지 `index` 변수 10 보다 큽니다. `Until` 절 루프의 끝입니다.  
  
 [!code-vb[VbVbalrStatements#131](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_1.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 한 `While` 절 대신는 `Until` 절 및 `condition` 끝 대신 루프의 시작 부분에서 테스트 합니다.  
  
 [!code-vb[VbVbalrStatements#132](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_2.vb)]  
  
## <a name="example"></a>예제  
 다음 예에서 `condition` 루프를 중지 때는 `index` 변수는 100을 초과 합니다. 그러나 `If` 루프에 문을 지정 하면는 `Exit Do` 문의 인덱스 변수는 10 보다 큰 경우에 루프를 중지 합니다.  
  
 [!code-vb[VbVbalrStatements#133](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_3.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 텍스트 파일에 있는 모든 줄을 읽습니다. <xref:System.IO.File.OpenText%2A> 메서드는 파일을 열고 반환는 <xref:System.IO.StreamReader> 는 문자를 읽는 합니다. 에 `Do...Loop` 조건은 <xref:System.IO.StreamReader.Peek%2A> 의 메서드는 `StreamReader` 추가 문자가 있는지 여부를 결정 합니다.  
  
 [!code-vb[VbVbalrStatements#134](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_4.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [루프 구조](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md)  
 [중첩 제어 구조](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Exit 문](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [While...End While 문](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
