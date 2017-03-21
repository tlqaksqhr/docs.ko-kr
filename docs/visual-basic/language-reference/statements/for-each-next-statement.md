---
title: "각각에 대해... 다음 문 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ForEach
- vb.ForEachNext
- vb.Each
- ForEachNext
dev_langs:
- VB
helpviewer_keywords:
- infinite loops
- Next statement, For Each...Next
- endless loops
- loop structures, For Each...Next
- loops, endless
- Each keyword
- instructions, repeating
- For Each statement
- collections, instruction repetition
- loops, infinite
- For Each...Next statements
- For keyword [Visual Basic], For Each...Next statements
- Exit statement, For Each...Next statements
- iteration
ms.assetid: ebce3120-95c3-42b1-b70b-fa7da40c75e2
caps.latest.revision: 56
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e0173877fa4a57da76fd774d70ce63d2beda23ad
ms.lasthandoff: 03/13/2017

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
|`element`|에 필요한는 `For Each` 문입니다. 경우 선택 사항는 `Next` 문입니다. 변수입니다. 컬렉션의 요소를 반복 하는 데 사용 합니다.|  
|`datatype`|필요한 경우 `element` 이미 선언 되지 않습니다. 데이터 형식이 `element`합니다.|  
|`group`|필수 요소. 컬렉션 형식 이거나 개체 형식이 있는 변수입니다. 컬렉션을 참조 하는 `statements` 를 반복할 합니다.|  
|`statements`|선택적 요소. 하나 이상의 문 사이의 `For Each` 및 `Next` 각 항목에 대해 실행 하는 `group`합니다.|  
|`Continue For`|선택적 요소. 시작 부분으로 제어를 전송에서 `For Each` 루프입니다.|  
|`Exit For`|선택적 요소. 밖으로 제어를 전송에서 `For Each` 루프입니다.|  
|`Next`|필수 요소. 정의 종료는 `For Each` 루프입니다.|  
  
## <a name="simple-example"></a>간단한 예  
 Use a `For Each`... `Next` 컬렉션 또는 배열의 각 요소에 대 한 문 집합을 반복할 때 반복 합니다.  
  
> [!TIP]
>  A [For... 다음 문](../../../visual-basic/language-reference/statements/for-next-statement.md) 루프의 각 반복을 제어 변수와 연결 하 고 해당 변수의 초기 및 최종 값을 결정 수 경우 잘 작동 합니다. 그러나 컬렉션을 다룰 때는 초기 및 최종 값의 개념, 의미 있는 없고 컬렉션의 요소 수를 알 필요가 없습니다. 이러한 종류의 경우에는 `For Each`... `Next` 루프는 대개 더 좋습니다.  
  
 다음 예제에서는 `For Each`...`Next` 문 목록 컬렉션의 모든 요소를 반복합니다.  
  
 [!code-vb[VbVbalrStatements #&121;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_1.vb)]  
  
 더 많은 예제를 참조 하십시오. [컬렉션](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b) 및 [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)합니다.  
  
## <a name="nested-loops"></a>중첩 된 루프  
 중첩할 수 `For Each` 서로 배치 하 여 루프입니다.  
  
 다음 예제에서는 중첩 된 `For Each`...`Next` 구조입니다.  
  
 [!code-vb[VbVbalrStatements #&122;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_2.vb)]  
  
 각 루프는 고유 해야 루프를 중첩할 때 `element` 변수입니다.  
  
 또한 다른 종류의 제어 구조 서로 중첩할 수 있습니다. 자세한 내용은 참조 [중첩 제어 구조](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)합니다.  
  
## <a name="exit-for-and-continue-for"></a>에 대 한 종료 하 고 계속 하기  
 [에 Exit](../../../visual-basic/language-reference/statements/exit-statement.md) 문을 사용 하면 실행을 종료 하는 `For`...`Next` 루프 및 전송 컨트롤 뒤에 오는 문에 `Next` 문입니다.  
  
 `Continue For` 문은 제어 즉시 루프의 다음 반복으로 합니다. 자세한 내용은 참조 [Continue 문을](../../../visual-basic/language-reference/statements/continue-statement.md)합니다.  
  
 다음 예제를 사용 하는 방법을 보여 줍니다는 `Continue For` 및 `Exit For` 문입니다.  
  
 [!code-vb[VbVbalrStatements #&123;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_3.vb)]  
  
 개수에 관계 없이 입력할 수 있습니다 `Exit For` 의 문에서 `For Each` 루프입니다. 사용 하는 경우 내에 중첩 된 `For Each` 루프, `Exit For` 실행이 다음으로 높은 중첩 수준에 가장 안쪽의 루프 및 전송에 컨트롤을 종료 합니다.  
  
 `Exit For`일부 조건 평가한 후에 대개에서 예를 들어 한 `If`... `Then`... `Else` 구조입니다. 사용 하려는 `Exit For` 다음 조건에 대 한 합니다.  
  
-   계속 반복은 불필요 하거나 불가능 합니다. 이 잘못 된 값 이나 종료 요청으로 발생할 수 있습니다.  
  
-   예외가 포착 되는 `Try`... `Catch`... `Finally`. 사용할 수 있는 `Exit For` 의 끝에는 `Finally` 블록입니다.  
  
-   여기는 길어지거나 무한히 계속도 여러 번 실행 될 수 있는 루프는 무한 반복 합니다. 이러한 조건을 감지한 경우 사용할 수 있습니다 `Exit For` 를 루프를 이스케이프 합니다. 자세한 내용은 참조 [수행... 반복 문](../../../visual-basic/language-reference/statements/do-loop-statement.md)합니다.  
  
## <a name="iterators"></a>반복기  
 사용 된 *반복기* 컬렉션에 대해 사용자 지정 반복을 수행 하 합니다. 반복기는 함수 일 수 또는 `Get` 접근자입니다. 사용 하 여 한 `Yield` 문을 한 번에 컬렉션의 각 요소를 반환 합니다.  
  
 반복기를 사용 하 여 호출을 `For Each...Next` 문입니다. 각 반복에서 `For Each` 루프는 반복기를 호출 합니다. 때는 `Yield` 반복기의 식에서 문에 도달 하면는 `Yield` 문을 반환 되 고 코드에서 현재 위치는 유지 됩니다. 다음에 반복기가 호출되면 해당 위치에서 실행이 다시 시작됩니다.  
  
 다음 예제에서는 반복기 함수를 사용 합니다. 반복기 함수에는 `Yield` 문 내에 있는 한 [에 대 한... 다음](../../../visual-basic/language-reference/statements/for-next-statement.md) 루프입니다. 에 `ListEvenNumbers` 메서드, 각 반복의는 `For Each` 문 본문에서 다음 단계로 진행 하는 반복기 함수에 대 한 호출을 만듭니다 `Yield` 문입니다.  
  
 [!code-vb[VbVbalrStatements&127;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_4.vb)]  
  
 자세한 내용은 참조 [반복기](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7), [Yield 문을](../../../visual-basic/language-reference/statements/yield-statement.md), 및 [반복기](../../../visual-basic/language-reference/modifiers/iterator.md)합니다.  
  
## <a name="technical-implementation"></a>기술 구현  
 경우는 `For Each`...`Next` Visual Basic, 문을 실행 한 번만 루프를 시작 하기 전에 컬렉션 자체를 평가 합니다. 문 블록 변경 되 면 `element` 또는 `group`, 이러한 변경 내용은 루프의 반복 영향을 주지 않습니다.  
  
 때 컬렉션의 모든 요소가 표시 된 순서 대로에 할당 된 `element`, `For Each` 루프가 종료 되 고 다음 문으로 전달 제어는 `Next` 문입니다.  
  
 경우 `element` 되지 않은 외부에 선언이 루프에서 선언 해야에 `For Each` 문입니다. 형식을 선언할 수 있습니다 `element` 를 사용 하 여 명시적으로 `As` 문이 형식을 할당 하는 형식 유추에 사용할 수 있습니다. 두 경우 모두의 범위 `element` 루프의 본문입니다. 그러나 선언할 수 없습니다 `element` 외부 및 내부 루프입니다.  
  
 선택적으로 지정할 수 `element` 에 `Next` 문입니다. 중첩 된 경우에 특히 프로그램의 가독성이 향상 됩니다 `For Each` 루프입니다. 표시에 해당 하는 것과 같은 변수를 지정 해야 `For Each` 문입니다.  
  
 값을 변경 하지 않도록 하려는 경우 `element` 루프 안에 있습니다. 이렇게 것 더 어렵게 만들 수를 읽고 코드를 디버깅 합니다. 값을 변경 `group` 컬렉션 또는 루프를 처음으로 입력 하는 경우는 해당 요소에 영향을 주지 않습니다.  
  
 경우 루프를 중첩 하는 경우는 `Next` 외부 중첩 수준의의 문이 하기 전에 `Next` 내부 수준의 컴파일러에서 오류를 알립니다. 그러나 컴파일러 검색할 수 지정 하는 경우에 중복 오류 `element` 에서 모든 `Next` 문입니다.  
  
 코드가 특정 한 순서로 컬렉션을 이동 하는 경우는 `For Each`... `Next` 루프에 적합 하지 않을, 열거자 개체의 특징을 알 수 없는 경우 컬렉션을 노출 합니다. 탐색 순서에서 하지만 Visual Basic에서 결정 되지는 <xref:System.Collections.IEnumerator.MoveNext%2A>열거자 개체의 메서드.</xref:System.Collections.IEnumerator.MoveNext%2A> 처음에 반환 될 컬렉션의 요소를 예측할 수 없습니다 따라서 `element`, 다음에 지정 된 요소 반환 되는 또는입니다. 와 같은 다른 루프 구조를 사용 하 여 더 안정적인 결과 얻을 수 `For`... `Next` or `Do`... `Loop`.  
  
 데이터 형식이 `element` 으로 있어야 데이터의 요소 형식 `group` 변환할 수 있습니다.  
  
 데이터 형식이 `group` 컬렉션 또는 열거 가능 배열을 참조 하는 참조 형식 이어야 합니다. 따라서 가장 일반적으로 `group` 구현 하는 개체를 참조 하는 <xref:System.Collections.IEnumerable>의 인터페이스는 `System.Collections` 네임 스페이스 또는 <xref:System.Collections.Generic.IEnumerable%601>의 인터페이스는 `System.Collections.Generic` 네임 스페이스.</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable> `System.Collections.IEnumerable`정의 <xref:System.Collections.IEnumerable.GetEnumerator%2A>메서드는 컬렉션에 대 한 열거자 개체를 반환 합니다.</xref:System.Collections.IEnumerable.GetEnumerator%2A> 열거자 개체를 구현 하는 `System.Collections.IEnumerator` 의 인터페이스는 `System.Collections` 네임 스페이스를 노출 하 고는 <xref:System.Collections.IEnumerator.Current%2A>속성 및 <xref:System.Collections.IEnumerator.Reset%2A>및 <xref:System.Collections.IEnumerator.MoveNext%2A>메서드.</xref:System.Collections.IEnumerator.MoveNext%2A> </xref:System.Collections.IEnumerator.Reset%2A> </xref:System.Collections.IEnumerator.Current%2A> Visual Basic 컬렉션을 탐색 하려면이 사용 합니다.  
  
### <a name="narrowing-conversions"></a>축소 변환  
 때 `Option Strict` 로 설정 된 `On`, 축소 변환에는 일반적으로 컴파일러 오류가 발생 합니다. 그러나에 `For Each` 문을 요소에서 변환 `group` 를 `element` 계산 되 고 실행 시 수행 축소 변환으로 발생 하는 컴파일러 오류 표시 되지 않습니다.  
  
 다음 예제에서는 할당에에서 `m` 에 대 한 초기 값으로 `n` 때 컴파일되지 않습니다 `Option Strict` 때문에 켜져 변환은 `Long` 에 `Integer` 축소 변환입니다. 에 `For Each` 반면 컴파일러 오류가 발생은 문에 대 한 할당도 보고 `number` 에서 동일한 변환 해야 하는 `Long` 를 `Integer`합니다. 에 `For Each` 다 수 포함 된 문에서 런타임 오류가 발생 하는 경우 <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A>큰 숫자에 적용 됩니다.</xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A>  
  
 [!code-vb[VbVbalrStatements #&89;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_5.vb)]  
  
### <a name="ienumerator-calls"></a>IEnumerator 호출  
 경우 실행을 `For Each`... `Next` 루프가 시작, Visual Basic 확인 `group` 유효한 컬렉션 개체를 참조 합니다. 그렇지 않으면 예외를 throw 합니다. 호출 된 <xref:System.Collections.IEnumerator.MoveNext%2A>메서드 및 <xref:System.Collections.IEnumerator.Current%2A>첫 번째 요소를 반환 하는 열거자 개체의 속성입니다.</xref:System.Collections.IEnumerator.Current%2A> </xref:System.Collections.IEnumerator.MoveNext%2A> 경우 `MoveNext` 중임을 나타냅니다 다음 없는 요소 즉, 컬렉션이 비어 있는 경우는 `For Each` 루프가 종료 되 고 다음 문으로 전달 제어는 `Next` 문입니다. 그렇지 않은 경우 Visual Basic 설정 `element` 첫 번째 요소 및 문 블록을 실행 합니다.  
  
 Visual Basic 발견할 때마다는 `Next` 에 반환 문에 `For Each` 문. 호출 다시 `MoveNext` 및 `Current` 및 반환 하 고 다음 요소인 다시 것 블록을 실행 하거나 결과 따라 루프를 중지 합니다. 될 때까지이 프로세스를 계속 `MoveNext` 는 다음 요소가 나타냅니다 또는 `Exit For` 문이 있습니다.  
  
 **컬렉션을 수정 합니다.** 반환 되는 열거자 개체 <xref:System.Collections.IEnumerable.GetEnumerator%2A>일반적으로 허용 하지 않습니다 추가, 삭제, 바꾸기 또는 모든 요소를 다시 정렬 하 여 컬렉션을 변경할 수 있습니다.</xref:System.Collections.IEnumerable.GetEnumerator%2A> 초기화 한 후에 컬렉션을 변경 하는 경우는 `For Each`... `Next` 루프 열거자 개체는 유효 하지 않았으며 요소에 액세스 하 여 다음 시도 <xref:System.InvalidOperationException>예외.</xref:System.InvalidOperationException>  
  
 그러나이 인해 수정 되지 않습니다에 따른 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], 하지만 구현에 의해 아니라는 <xref:System.Collections.IEnumerable>인터페이스.</xref:System.Collections.IEnumerable> 구현 하는 것이 불가능 `IEnumerable` 반복 중 수정을 허용 하는 방식에서입니다. 그러한 동적 수정 방식을 고려 하는 경우의 특징을 이해 하 고 있는지 확인은 `IEnumerable` 를 사용 하는 컬렉션에서 구현 합니다.  
  
 **컬렉션 요소를 수정 합니다.** <xref:System.Collections.IEnumerator.Current%2A>열거자 개체의 속성은 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), 각 컬렉션 요소의 로컬 복사본을 반환 합니다.</xref:System.Collections.IEnumerator.Current%2A> 이 요소 자체를 수정할 수 없음을 의미에 `For Each`... `Next` loop. 수정 내용이에서 로컬 복사본에만 영향을 줍니다 `Current` 다시 기본 컬렉션에 반영 되지 않습니다. 그러나 요소 참조 형식인 경우 가리키는 인스턴스의 멤버를 수정할 수 있습니다. 다음 예제에서는 수정 된 `BackColor` 의 각 구성원 `thisControl` 요소입니다. 그러나 수정할 수는 없습니다 `thisControl` 자체입니다.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 앞의 예제를 수정할 수는 `BackColor` 의 각 구성원 `thisControl` 요소를 수정할 수는 있지만 `thisControl` 자체입니다.  
  
 **배열을 탐색 합니다.** 때문에 <xref:System.Array>클래스가 구현 하는 <xref:System.Collections.IEnumerable>인터페이스, 모든 배열 노출 된 <xref:System.Array.GetEnumerator%2A>메서드.</xref:System.Array.GetEnumerator%2A> </xref:System.Collections.IEnumerable> </xref:System.Array> 즉, 배열을 반복할 수 있는지는 `For Each`... `Next` loop. 그러나 배열 요소만 읽을 수 있습니다. 변경할 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 <xref:System.IO.DirectoryInfo>클래스</xref:System.IO.DirectoryInfo> 를 사용 하 여 C:\ 디렉터리에 있는 모든 폴더를 나열 합니다.  
  
 [!code-vb[VbVbalrStatements #&124;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_6.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 컬렉션 정렬 절차를 보여 줍니다. 인스턴스를 정렬 하는 예제는 `Car` <xref:System.Collections.Generic.List%601>.</xref:System.Collections.Generic.List%601> 에 저장 되어 있는 클래스 `Car` 클래스가 구현 하는 <xref:System.IComparable%601>인터페이스를 필요로 하는 <xref:System.IComparable%601.CompareTo%2A>메서드를 구현 합니다.</xref:System.IComparable%601.CompareTo%2A> </xref:System.IComparable%601>  
  
 각 호출에는 <xref:System.IComparable%601.CompareTo%2A>메서드 정렬에 사용 되는 단일 비교를 수행 합니다.</xref:System.IComparable%601.CompareTo%2A> 사용자가 작성 한 코드는 `CompareTo` 메서드를 다른 개체와 현재 개체의 각 비교에 대 한 값을 반환 합니다. 현재 개체가 다른 개체보다 작으면 반환되는 값이&0;보다 작고, 현재 개체가 다른 개체보다 크면&0;보다 크고, 같으면&0;입니다. 이렇게 하면 보다 큼, 보다 작음 및 같음에 대한 조건을 코드에서 정의할 수 있습니다.  
  
 에 `ListCars` 메서드를는 `cars.Sort()` 문 목록을 정렬 합니다. 이 호출으로는 <xref:System.Collections.Generic.List%601.Sort%2A>의 메서드는 <xref:System.Collections.Generic.List%601>하면는 `CompareTo` 에 대 한 자동으로 호출 될 메서드를는 `Car` 개체에 `List`.</xref:System.Collections.Generic.List%601> </xref:System.Collections.Generic.List%601.Sort%2A>  
  
 [!code-vb[VbVbalrStatements #&125;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_7.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [컬렉션](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)   
 [...에 대 한 Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [루프 구조](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [While... While 문 종료](../../../visual-basic/language-reference/statements/while-end-while-statement.md)   
 [... 반복 문](../../../visual-basic/language-reference/statements/do-loop-statement.md)   
 [확대 변환과 축소 변환](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [개체 이니셜라이저: 명명 된 형식과 익명 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [컬렉션 이니셜라이저](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)   
 [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)
