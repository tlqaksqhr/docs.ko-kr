---
title: For Each...Next 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ForEach
- vb.ForEachNext
- vb.Each
- ForEachNext
helpviewer_keywords:
- infinite loops
- Next statement [Visual Basic], For Each...Next
- endless loops
- loop structures [Visual Basic], For Each...Next
- loops, endless
- Each keyword [Visual Basic]
- instructions, repeating
- For Each statement [Visual Basic]
- collections, instruction repetition
- loops, infinite
- For Each...Next statements
- For keyword [Visual Basic], For Each...Next statements
- Exit statement [Visual Basic], For Each...Next statements
- iteration
ms.assetid: ebce3120-95c3-42b1-b70b-fa7da40c75e2
ms.openlocfilehash: ec7e5196bcb939631f4bf426f2e94cddc0c88a9a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="for-eachnext-statement-visual-basic"></a>For Each...Next 문(Visual Basic)
컬렉션의 각 요소에 대 한 문 그룹을 반복합니다.  
  
## <a name="syntax"></a>구문  
  
```  
For Each element [ As datatype ] In group  
    [ statements ]  
    [ Continue For ]  
    [ statements ]  
    [ Exit For ]  
    [ statements ]  
Next [ element ]  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`element`|에 필요한는 `For Each` 문. 경우 선택 사항는 `Next` 문. 변수입니다. 컬렉션의 요소를 반복 하는 데 사용 합니다.|  
|`datatype`|필요한 경우 `element` 이미 선언 되지 않습니다. 데이터 형식이 `element`합니다.|  
|`group`|필수. 컬렉션 형식 이거나 개체는 형식으로 사용 되는 변수입니다. 컬렉션을 참조 하는 `statements` 를 반복할 합니다.|  
|`statements`|선택 사항입니다. 사이 하나 이상의 문이 `For Each` 및 `Next` 각 항목에 대해 실행 하는 `group`합니다.|  
|`Continue For`|선택 사항입니다. 제어의 시작 부분에 전달 된 `For Each` 루프입니다.|  
|`Exit For`|선택 사항입니다. 밖으로 제어를 전송에서 `For Each` 루프입니다.|  
|`Next`|필수. 정의 종료는 `For Each` 루프입니다.|  
  
## <a name="simple-example"></a>간단한 예  
 사용 하 여 한 `For Each`... `Next` 컬렉션 또는 배열의 각 요소에 대 한 문 집합을 반복할 때 루프입니다.  
  
> [!TIP]
>  A [에 대 한... 다음 문](../../../visual-basic/language-reference/statements/for-next-statement.md) 제어 변수는 루프의 각 반복 연결 하 고 해당 변수의 초기 및 최종 값을 확인 수 때 잘 작동 합니다. 그러나 컬렉션을 처리 하는 초기 및 최종 값의 개념은 의미가, 하며 컬렉션의 요소 수를 알 필요가 없습니다. 이러한 종류의 경우에는 `For Each`... `Next` 루프는 종종 더 좋습니다.  
  
 다음 예제에서는 `For Each`...`Next` 문 목록 컬렉션의 모든 요소를 반복합니다.  
  
 [!code-vb[VbVbalrStatements#121](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_1.vb)]  
  
 더 많은 예제를 참조 하십시오. [컬렉션](../../../standard/collections/index.md) 및 [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)합니다.  
  
## <a name="nested-loops"></a>중첩된 루프  
 중첩할 수 `For Each` 서로 배치 하 여 루프입니다.  
  
 다음 예제에서는 중첩 된 `For Each`...`Next` 구조입니다.  
  
 [!code-vb[VbVbalrStatements#122](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_2.vb)]  
  
 각 루프는 고유 해야 루프를 중첩할 때 `element` 변수입니다.  
  
 서로 다른 제어 구조가 서로 중첩할 수도 있습니다. 자세한 내용은 참조 [중첩 제어 구조](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)합니다.  
  
## <a name="exit-for-and-continue-for"></a>에 대 한 종료 하 고 계속 하기  
 [에 Exit](../../../visual-basic/language-reference/statements/exit-statement.md) 문을 사용 하면 실행 종료 하 고 `For`...`Next` 루프 및 전송 컨트롤 뒤에 오는 문에 `Next` 문.  
  
 `Continue For` 문은 제어 즉시 루프의 다음 반복으로 합니다. 자세한 내용은 참조 [Continue 문을](../../../visual-basic/language-reference/statements/continue-statement.md)합니다.  
  
 사용 하는 방법을 보여 주는 다음 예제는 `Continue For` 및 `Exit For` 문.  
  
 [!code-vb[VbVbalrStatements#123](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_3.vb)]  
  
 개수에 관계 없이 넣을 수 `Exit For` 의 문에서 `For Each` 루프입니다. 사용할 경우 내에 중첩 `For Each` 루프, `Exit For` 실행이 중첩 다음으로 높은 수준으로 가장 안쪽 루프 및 전송에 제어를 종료 합니다.  
  
 `Exit For` 일부 조건에 대 한 평가 후에 대개에서 예를 들어 한 `If`... `Then`... `Else` 구조입니다. 사용 하려는 경우도 `Exit For` 다음 조건에 대 한 합니다.  
  
-   계속 반복은 불필요 하거나 불가능 합니다. 이 잘못 된 값 이나 종료 요청으로 발생할 수 있습니다.  
  
-   예외가 발생 위치는 `Try`... `Catch`... `Finally`. 사용할 수 있습니다 `Exit For` 의 끝에는 `Finally` 블록입니다.  
  
-   여기서는 크거나 무한도 가능 여러 번 실행 될 수 있는 루프는 무한 루프입니다. 사용할 수 있습니다 이러한 조건을 감지 하면 `Exit For` 루프를 이스케이프 합니다. 자세한 내용은 참조 [수행... 문은 루프](../../../visual-basic/language-reference/statements/do-loop-statement.md)합니다.  
  
## <a name="iterators"></a>반복기  
 사용 하면는 *반복기* 하는 컬렉션에 대해 사용자 지정 반복을 수행 합니다. 반복기는 함수 일 수 또는 `Get` 접근자입니다. 사용 하 여 한 `Yield` 문을 한 번에 하나씩 컬렉션의 각 요소를 반환 합니다.  
  
 사용 하 여 반복기를 호출는 `For Each...Next` 문. 각각의 `For Each` 루프의 반복이 반복기를 호출합니다. 경우는 `Yield` 문이 반복기에서 식에 도달 하면는 `Yield` 문을 반환 되 고 코드에서 현재 위치는 유지 됩니다. 다음에 반복기가 호출되면 해당 위치에서 실행이 다시 시작됩니다.  
  
 다음 예제에서는 반복기 함수를 사용 합니다. 반복기 함수에는 `Yield` 문 내에 있는 한 [에 대 한... 다음](../../../visual-basic/language-reference/statements/for-next-statement.md) 루프입니다. 에 `ListEvenNumbers` 메서드, 각 반복의는 `For Each` 문 본문에서 다음 단계로 진행 하는 반복기 함수를 한 호출이 생성 `Yield` 문.  
  
 [!code-vb[VbVbalrStatements#127](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_4.vb)]  
  
 자세한 내용은 참조 [반복기](../../programming-guide/concepts/iterators.md), [Yield 문을](../../../visual-basic/language-reference/statements/yield-statement.md), 및 [반복기](../../../visual-basic/language-reference/modifiers/iterator.md)합니다.  
  
## <a name="technical-implementation"></a>기술 구현  
 경우는 `For Each`...`Next` Visual Basic, 문을 실행 한 번만 루프를 시작 하기 전에 컬렉션 자체를 평가 합니다. 문 블록 변경 되 면 `element` 또는 `group`, 이러한 변경 내용은 루프의 반복 영향을 주지 않습니다.  
  
 때 컬렉션의 모든 요소가 연속적으로 옅에 할당 된 `element`, `For Each` 루프가 종료 되 고 다음 문으로 전달 제어는 `Next` 문.  
  
 경우 `element` 선언 해야이 루프 외부 선언 되지 않은에 `For Each` 문. 형식을 선언할 수 있습니다 `element` 를 사용 하 여 명시적으로 `As` 문이 형식을 할당 하는 형식 유추에 의존할 수 있습니다. 두 경우 모두의 범위 `element` 루프의 본문입니다. 그러나 선언할 수 없습니다 `element` 외부와 루프 내부입니다.  
  
 선택적으로 지정할 수 `element` 에 `Next` 문. 중첩 된 경우에 특히 프로그램의 가독성을 높일이 `For Each` 루프입니다. 표시에 해당 하는 것과 동일한 변수를 지정 해야 `For Each` 문.  
  
 값이 변경 되지 않도록 하려는 경우 `element` 루프 내부입니다. 이 작업을 수행 하기 더 어렵게 만들 수를 읽고 코드를 디버깅 합니다. 값을 변경 `group` 컬렉션 또는 해당 요소에는 루프를 먼저 입력 하는 경우 확인 된 영향을 주지 않습니다.  
  
 경우 루프를 중첩 하는 경우는 `Next` 외부 중첩 수준의의 문이 하기 전에 `Next` 내부 수준의 컴파일러에서 오류를 알립니다. 하지만, 컴파일러가 검색할 수 있습니다이 지정 하는 경우에 중복 오류 `element` 에 모든 `Next` 문.  
  
 특정 한 순서로 컬렉션을 트래버스하에 종속 되는 코드는 `For Each`... `Next` 루프에 적합 하지 않을, 컬렉션을 노출 하는 열거자 개체의 특성을 확신할 수 있습니다. 탐색 순서에서 하지만 Visual Basic에서 결정 되지 않습니다는 <xref:System.Collections.IEnumerator.MoveNext%2A> 열거자 개체의 메서드. 처음에 반환 되는 컬렉션의 요소를 예측할 수 없습니다 따라서 `element`, 다음에 지정 된 요소 반환 되는 또는 합니다. 와 같은 다른 루프 구조를 사용 하 여 더욱 안정적인 결과 얻을 수 있습니다 `For`... `Next` 또는 `Do`... `Loop`.  
  
 데이터 형식이 `element` 요소의의 데이터 형식이 있는 형식 이어야 합니다 `group` 변환할 수 있습니다.  
  
 데이터 형식이 `group` 열거 가능한 배열 또는 컬렉션에 대 한 참조는 참조 형식 이어야 합니다. 즉 가장 일반적으로 `group` 구현 하는 개체를 참조 하는 <xref:System.Collections.IEnumerable> 의 인터페이스는 `System.Collections` 네임 스페이스 또는 <xref:System.Collections.Generic.IEnumerable%601> 의 인터페이스는 `System.Collections.Generic` 네임 스페이스입니다. `System.Collections.IEnumerable` 정의 <xref:System.Collections.IEnumerable.GetEnumerator%2A> 메서드는 컬렉션에 대 한 열거자 개체를 반환 합니다. 열거자 개체를 구현 하는 `System.Collections.IEnumerator` 의 인터페이스는 `System.Collections` 네임 스페이스를 노출 하 고는 <xref:System.Collections.IEnumerator.Current%2A> 속성 및 <xref:System.Collections.IEnumerator.Reset%2A> 및 <xref:System.Collections.IEnumerator.MoveNext%2A> 메서드. 사용 하 여 이러한 컬렉션을 순회 하 합니다.  
  
### <a name="narrowing-conversions"></a>축소 변환  
 때 `Option Strict` 로 설정 된 `On`, 축소 변환에는 일반적으로 컴파일러 오류가 발생 합니다. 그러나에 `For Each` 문을의 요소에서 변환 `group` 를 `element` 계산 되 고 실행 시 수행 축소 변환 하 여 발생 하는 컴파일러 오류 표시 되지 않습니다.  
  
 다음 예제에서는 할당 `m` 에 대 한 초기 값으로 `n` 때 컴파일되지 않습니다 `Option Strict` 때문에 않습니다 변환은 `Long` 에 `Integer` 축소 변환입니다. 그러나에 `For Each` 문, 컴파일러 오류가 발생 하지 않습니다에 대 한 할당도 보고 `number` 에서 동일한 변환이 필요한 `Long` 를 `Integer`합니다. 에 `For Each` 다 수 포함 된 문 실행 시 오류가 발생 하는 경우 <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A> 다 수에 적용 됩니다.  
  
 [!code-vb[VbVbalrStatements#89](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_5.vb)]  
  
### <a name="ienumerator-calls"></a>IEnumerator 호출  
 경우 실행은 `For Each`... `Next` 루프가 시작, Visual Basic 확인 `group` 유효한 컬렉션 개체를 참조 합니다. 파일이 없으면 예외를 throw 합니다. 호출 된 <xref:System.Collections.IEnumerator.MoveNext%2A> 메서드 및 <xref:System.Collections.IEnumerator.Current%2A> 첫 번째 요소를 반환 하는 열거자 개체의 속성입니다. 경우 `MoveNext` 않음을 의미 없는 다음 요소 즉, 컬렉션이 비어 있는 경우는 `For Each` 루프가 종료 되 고 다음 문으로 전달 제어는 `Next` 문. 그렇지 않은 경우 Visual Basic 설정 `element` 첫 번째 요소와 실행 문 블록에 있습니다.  
  
 Visual Basic 발생할 때마다는 `Next` 에 반환 문에 `For Each` 문. 호출 다시 `MoveNext` 및 `Current` 및 반환 하 고 다음 요소인 다시 것 블록을 실행 하거나 결과 따라 루프를 중지 합니다. 까지이 프로세스를 계속 `MoveNext` 다음 요소가 임을 나타냅니다 또는 `Exit For` 문이 있습니다.  
  
 **컬렉션을 수정 합니다.** 반환 되는 열거자 개체 <xref:System.Collections.IEnumerable.GetEnumerator%2A> 정상적으로 선택할 수는 없습니다 추가, 삭제, 교체, 또는 모든 요소를 다시 정렬 하 여 컬렉션을 변경 합니다. 초기화 한 후에 컬렉션을 변경 하는 경우는 `For Each`... `Next` 루프 무효화 되는 열거자 개체 및 요소에 액세스 하는 다음 시도 인해는 <xref:System.InvalidOperationException> 예외입니다.  
  
 그러나 수정 작업의이 차단은으로 Visual Basic에서 있지만 구현에 의해 대신 결정 되지 않습니다는 <xref:System.Collections.IEnumerable> 인터페이스입니다. 구현 하는 것이 불가능 `IEnumerable` 반복 과정에서 수정할 수 있도록 하는 방식에서입니다. 그러한 동적 수정 방식을 고려 하는 경우의 특징을 이해 하 고 있는지 확인은 `IEnumerable` 구현을 사용 하는 컬렉션에 있습니다.  
  
 **컬렉션 요소를 수정 합니다.** <xref:System.Collections.IEnumerator.Current%2A> 열거자 개체의 속성은 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), 각 컬렉션 요소의의 로컬 복사본을 반환 합니다. 즉, 요소 자체를 수정할 수 없음을에 `For Each`... `Next` 루프입니다. 수정 내용이의 로컬 복사본에 영향을 줍니다 `Current` 및 기본 컬렉션에 반영 되지 않습니다. 그러나 요소 참조 형식인 가리키는 인스턴스의 멤버를 수정할 수 있습니다. 다음 예제에서는 수정 된 `BackColor` 의 각 구성원 `thisControl` 요소입니다. 그러나 수정할 수는 없습니다 `thisControl` 자체입니다.  
  
```vb  
Sub lightBlueBackground(ByVal thisForm As System.Windows.Forms.Form)  
    For Each thisControl As System.Windows.Forms.Control In thisForm.Controls  
        thisControl.BackColor = System.Drawing.Color.LightBlue  
    Next thisControl  
End Sub  
```  
  
 앞의 예제를 수정할 수는 `BackColor` 의 각 구성원 `thisControl` 요소를 수정할 수 있지만 `thisControl` 자체입니다.  
  
 **배열을 탐색 합니다.** 때문에 <xref:System.Array> 클래스가 구현 하는 <xref:System.Collections.IEnumerable> 인터페이스, 모든 배열 노출는 <xref:System.Array.GetEnumerator%2A> 메서드. 즉, 배열을으로 반복할 수 있는지는 `For Each`... `Next` 루프입니다. 그러나 배열 요소만 읽을 수 있습니다. 변경할 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 C:\ 디렉터리에 있는 모든 폴더를 사용 하 여 나열 된 <xref:System.IO.DirectoryInfo> 클래스입니다.  
  
 [!code-vb[VbVbalrStatements#124](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_6.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 컬렉션 정렬 절차를 보여 줍니다. 이 예제에서는 인스턴스를 정렬 한 `Car` 에 저장 되어 있는 클래스는 <xref:System.Collections.Generic.List%601>합니다. `Car` 클래스는 <xref:System.IComparable%601.CompareTo%2A> 메서드가 구현되어야 하는 <xref:System.IComparable%601> 인터페이스를 구현합니다.  
  
 호출할 때마다는 <xref:System.IComparable%601.CompareTo%2A> 메서드 정렬에 사용 되는 단일 비교가 수행 합니다. `CompareTo` 메서드의 사용자 작성 코드는 다른 개체와 현재 개체의 각 비교에 대한 값을 반환합니다. 현재 개체가 다른 개체보다 작으면 반환되는 값이 0보다 작고, 현재 개체가 다른 개체보다 크면 0보다 크고, 같으면 0입니다. 이렇게 하면 보다 큼, 보다 작음 및 같음에 대한 조건을 코드에서 정의할 수 있습니다.  
  
 `ListCars` 메서드에서 `cars.Sort()` 문은 목록을 정렬합니다. <xref:System.Collections.Generic.List%601>의 <xref:System.Collections.Generic.List%601.Sort%2A> 메서드를 호출하면 `List`의 `Car` 개체에 대해 `CompareTo` 메서드가 자동으로 호출됩니다.  
  
 [!code-vb[VbVbalrStatements#125](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_7.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [컬렉션](../../../standard/collections/index.md)  
 [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [루프 구조](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [While...End While 문](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [Do...Loop 문](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [확대 변환과 축소 변환](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [개체 이니셜라이저: 명명된 형식과 익명 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [컬렉션 이니셜라이저](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)  
 [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)
