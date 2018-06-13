---
title: For...Next 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Step
- vb.Next
- vb.To
- vb.for
helpviewer_keywords:
- infinite loops
- Next keyword [Visual Basic], For...Next statements
- For keyword [Visual Basic], For...Next statements
- Step keyword [Visual Basic], For...Next statements
- operator overloading, For...Next statement
- To keyword [Visual Basic], For...Next statements
- endless loops
- loops, endless
- instructions, repeating
- Next statement [Visual Basic], For...Next
- For...Next statements
- loop structures [Visual Basic], For...Next
- loops, infinite
- Exit statement [Visual Basic], For...Next statements
- For statement [Visual Basic]
ms.assetid: f5fc0d51-67ce-4c36-9f09-31c9a91c94e9
ms.openlocfilehash: 8c54189499b7d5b52cf93b4a0ae6cc47356bf57e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605331"
---
# <a name="fornext-statement-visual-basic"></a>For...Next 문(Visual Basic)
문 그룹을 지정한 횟수 만큼을 반복합니다.  
  
## <a name="syntax"></a>구문  
  
```  
For counter [ As datatype ] = start To end [ Step step ]  
    [ statements ]  
    [ Continue For ]  
    [ statements ]  
    [ Exit For ]  
    [ statements ]  
Next [ counter ]  
```  
  
## <a name="parts"></a>요소  
  
|파트|설명|  
|----------|-----------------|  
|`counter`|에 필요한는 `For` 문. 숫자 변수입니다. 루프 제어 변수입니다. 자세한 내용은 참조 [카운터 인수](#BKMK_Counter) 이 항목의 뒷부분에 나오는 합니다.|  
|`datatype`|선택 사항입니다. 데이터 형식이 `counter`합니다. 자세한 내용은 참조 [카운터 인수](#BKMK_Counter) 이 항목의 뒷부분에 나오는 합니다.|  
|`start`|필수. 숫자 식입니다. `counter`의 초기 값입니다.|  
|`end`|필수. 숫자 식입니다. 최종 값 `counter`합니다.|  
|`step`|선택 사항입니다. 숫자 식입니다. 양입니다 `counter` 루프가 반복 될 때마다 증가 합니다.|  
|`statements`|선택 사항입니다. 사이 하나 이상의 문이 `For` 및 `Next` 지정한 횟수 만큼을 실행 하는 합니다.|  
|`Continue For`|선택 사항입니다. 다음 루프 반복으로 제어를 전송 합니다.|  
|`Exit For`|선택 사항입니다. 밖으로 제어를 전송에서 `For` 루프입니다.|  
|`Next`|필수. 정의 종료는 `For` 루프입니다.|  
  
> [!NOTE]
>  `To` 카운터에 대 한 범위를 지정 하려면이 문을 키워드를 사용 합니다. 이 키워드를 사용할 수도 있습니다는 [선택... Case 문](../../../visual-basic/language-reference/statements/select-case-statement.md) 및 배열 선언 합니다. 배열 선언에 대 한 자세한 내용은 참조 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)합니다.  
  
## <a name="simple-examples"></a>간단한 예  
 사용 된 `For`... `Next` 횟수 만큼 문 집합을 반복할 때 구성 합니다.  
  
 다음 예제에서는 `index` 변수 값이 1로 시작 하 고이 값의 끝에서 끝나는 루프의 각 반복 증가 `index` 5에 도달 합니다.  
  
 [!code-vb[VbVbalrStatements#111](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_1.vb)]  
  
 다음 예제에서는 `number` 변수 2에서 시작 하 고 값의 끝에서 끝나는 루프의 각 반복에서 0.25에 의해 감소 `number` 0에 도달 합니다. `Step` 의 인수 `-.25` 루프의 각 반복에서 0.25 하 여 값을 줄입니다.  
  
 [!code-vb[VbVbalrStatements#112](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_2.vb)]  
  
> [!TIP]
>  A [동안... While 문 종료](../../../visual-basic/language-reference/statements/while-end-while-statement.md) 또는 [수행... Loop 문과](../../../visual-basic/language-reference/statements/do-loop-statement.md) 때 알 수 없는 사전에 루프에서 문을 실행 횟수 효과적으로 작동 합니다. 그러나 아는 경우 루프는 특정 횟수 만큼 실행 된 `For`... `Next` 루프는 것이 좋습니다. 루프를 처음 입력할 때의 반복 횟수를 결정 합니다.  
  
## <a name="nesting-loops"></a>중첩 루프  
 중첩할 수 `For` 서로 배치 하 여 루프입니다. 다음 예제에서는 중첩 된 `For`... `Next` 단계 값이 있는 구조입니다. 외부 루프의 루프의 각 반복에 대해 문자열을 만듭니다. 내부 루프 루프의 각 반복에 대해 루프 카운터 변수를 감소 시킵니다.  
  
 [!code-vb[VbVbalrStatements#113](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_3.vb)]  
  
 중첩 루프를 각 루프는 고유 해야 `counter` 변수입니다.  
  
 서로 다른 제어 구조가 서로 중첩할 수도 있습니다. 자세한 내용은 참조 [중첩 제어 구조](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)합니다.  
  
## <a name="exit-for-and-continue-for"></a>에 대 한 종료 하 고 계속 하기  
 `Exit For` 문을 즉시 끝내는 `For`...`Next` 루프 및 전송 컨트롤 뒤에 오는 문에 `Next` 문.  
  
 `Continue For` 문은 제어 즉시 루프의 다음 반복으로 합니다. 자세한 내용은 참조 [Continue 문을](../../../visual-basic/language-reference/statements/continue-statement.md)합니다.  
  
 다음 예제에서는 `Continue For` 및 `Exit For` 문.  
  
 [!code-vb[VbVbalrStatements#115](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_4.vb)]  
  
 개수에 관계 없이 넣을 수 `Exit For` 의 문에서 `For`...`Next` 루프입니다. 사용할 경우 내에 중첩 `For`중...`Next` 루프, `Exit For` 가장 안쪽 루프를 끝내 고 중첩 다음으로 높은 수준으로 제어를 전달 합니다.  
  
 `Exit For` 일부 조건 평가 후에 주로 사용 됩니다 (예를 들어 한 `If`... `Then`... `Else` 구조). 사용 하려는 경우도 `Exit For` 다음 조건에 대 한 합니다.  
  
-   계속 반복은 불필요 하거나 불가능 합니다. 잘못 된 값 이나 종료 요청에는이 조건을 만들 수 있습니다.  
  
-   A `Try`... `Catch`... `Finally` 문이 된 예외를 catch 합니다. 사용할 수 있습니다 `Exit For` 의 끝에는 `Finally` 블록입니다.  
  
-   크거나 무한도 가능 여러 번 실행 될 수 있는 루프는 무한 루프를 만들어야 합니다. 사용할 수 있습니다 이러한 조건을 감지 하면 `Exit For` 루프를 이스케이프 합니다. 자세한 내용은 참조 [수행... 문은 루프](../../../visual-basic/language-reference/statements/do-loop-statement.md)합니다.  
  
## <a name="technical-implementation"></a>기술 구현  
 경우는 `For`... `Next` 루프가 시작, Visual Basic 조건이 `start`, `end`, 및 `step`합니다. 이 다시 할당에만 이러한 값을 평가 하는 Visual Basic `start` 를 `counter`합니다. 문 전에 블록 실행의 Visual Basic 비교 `counter` 를 `end`합니다. 경우 `counter` 보다 크면 이미는 `end` 값 (또는 더 작은 경우 `step` 가 음수), `For` 루프가 종료 되 고 제어를 다음 문으로 전달은 `Next` 문. 그렇지 않은 경우 문 블록이 실행 됩니다.  
  
 Visual Basic 발생할 때마다는 `Next` 문 수를 늘리면 `counter` 여 `step` 돌아갑니다는 `For` 문. 비교 다시 `counter` 를 `end`, 다시 블록을 실행 하거나 결과 따라 루프를 종료 하 고 있습니다. 까지이 프로세스를 계속 `counter` 전달 `end` 또는 `Exit For` 문이 실행 됩니다.  
  
 반복 될 때까지 중단 되지 않는 `counter` 경과 `end`합니다. 경우 `counter` 같으면 `end`, 루프가 계속 됩니다. 블록을 실행할지 여부를 결정 하는 비교는 `counter`  <=  `end` 경우 `step` 가 양수 및 `counter`  >=  `end` 경우 `step` 음수입니다.  
  
 값을 변경 하면 `counter` 루프 내부에 있는 동안 코드를 읽고 디버깅 어려울 수 있습니다. 값을 변경 `start`, `end`, 또는 `step` 루프를 먼저 입력 하는 경우 확인 된 반복 값에 영향을 주지 않습니다.  
  
 루프를 중첩 하는 경우 컴파일러에서 오류를 알립니다 발견 하는 경우는 `Next` 하기 전에 외부 중첩 수준의 문이 `Next` 내부 수준의 문이 있습니다. 하지만, 컴파일러가 검색할 수 있습니다이 지정 하는 경우에 중복 오류 `counter` 에 모든 `Next` 문.  
  
### <a name="step-argument"></a>단계 인수  
 값 `step` 양수 또는 음수가 될 수 있습니다. 이 매개 변수는 다음 표에 따라 루프 처리를 결정합니다.  
  
|**단계 값**|**루프를 실행 하는 경우**|  
|--------------------|--------------------------|  
|양수 또는 0|`counter` <= `end`|  
|음수|`counter` >= `end`|  
  
 기본값 `step` 는 1입니다.  
  
###  <a name="BKMK_Counter"></a> 카운터 인수  
 다음 표에서 여부 `counter` 전체 범위가 지정 된 새 지역 변수를 정의 `For…Next` 루프입니다. 이 결정에 따라 다릅니다. `datatype` 있는지 여부와 `counter` 이미 정의 되었습니다.  
  
|`datatype` 존재?|`counter` 이미 정의 되어 있습니까?|결과 (여부 `counter` 전체 범위가 지정 된 새 지역 변수를 정의 `For...Next` 루프)|  
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|  
|아니요|예|아니요, 때문에 `counter` 이미 정의 되었습니다. 경우 범위 `counter` 되지 않습니다는 프로시저에 로컬인 컴파일 타임 경고 메시지가 발생 합니다.|  
|아니요|아니요|예. 데이터 형식에서 유추 됩니다는 `start`, `end`, 및 `step` 식입니다. 형식 유추에 대 한 정보를 참조 하십시오. [Option Infer 문](../../../visual-basic/language-reference/statements/option-infer-statement.md) 및 [지역 형식 유추](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)합니다.|  
|예|예|예, 하지만 경우에만 기존 `counter` 변수는 프로시저 밖에 서 정의 됩니다. 해당 변수는 별도 상태로 유지 됩니다. 경우 기존 범위 `counter` 변수가 프로시저에 로컬인는 컴파일 타임 오류가 발생 합니다.|  
|예|아니요|예.|  
  
 데이터 형식이 `counter` 다음 유형 중 하나가 되도록 반복의 유형을 결정 합니다.  
  
-   A `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, 또는 `Double`합니다.  
  
-   사용 하 여 선언 하는 열거는 [Enum 문](../../../visual-basic/language-reference/statements/enum-statement.md)합니다.  
  
-   `Object`입니다.  
  
-   형식 `T` 다음과 같은 연산자가 있는 여기서 `B` 에 사용할 수 있는 형식인는 `Boolean` 식입니다.  
  
     `Public Shared Operator >= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator <= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator - (op1 As T, op2 As T) As T`  
  
     `Public Shared Operator + (op1 As T, op2 As T) As T`  
  
 선택적으로 지정할 수는 `counter` 변수에 `Next` 문. 이 구문은 중첩 된 경우에 특히 프로그램의 가독성을 높일 수 `For` 루프입니다. 해당 표시 되는 변수를 지정 해야 `For` 문.  
  
 `start`, `end`, 및 `step` 식의 형식으로 확대 되는 모든 데이터 형식으로 평가할 수 `counter`합니다. 에 대 한 사용자 정의 형식을 사용 하면 `counter`를 정의 해야 할 수 있습니다는 `CType` 변환 연산자의 종류를 `start`, `end`, 또는 `step` 유형과 `counter`합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 제네릭 목록에서 모든 요소를 제거합니다. 대신는 [각각에 대해... 다음 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md), 예제에 나와 있는 `For`... `Next` 내림차순 반복 하는 문입니다. 이 예제에서는 때문에이 기술을 사용 하 여는 `removeAt` 메서드 더 낮은 인덱스 값을 제거 하는 요소 뒤 요소를 사용 하면 됩니다.  
  
 [!code-vb[VbVbalrStatements#114](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_5.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 사용 하 여 선언 하는 열거형 반복는 [Enum 문](../../../visual-basic/language-reference/statements/enum-statement.md)합니다.  
  
 [!code-vb[VbVbalrStatements#116](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_6.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 문 매개 변수 사용에 대 한 연산자 오버 로드가 있는 클래스는 `+`, `-`, `>=`, 및 `<=` 연산자입니다.  
  
 [!code-vb[VbVbalrStatements#117](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_7.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Collections.Generic.List%601>  
 [루프 구조](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [While...End While 문](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [Do...Loop 문](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [중첩 제어 구조](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Exit 문](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [컬렉션](../../programming-guide/concepts/collections.md)
