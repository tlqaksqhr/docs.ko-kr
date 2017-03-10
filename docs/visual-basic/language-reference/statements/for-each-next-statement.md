---
title: "For Each...Next 문(Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ForEach"
  - "vb.ForEachNext"
  - "vb.Each"
  - "ForEachNext"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "무한 루프"
  - "Next 문, For Each...Next"
  - "무한 루프"
  - "루프 구조, For Each...Next"
  - "루프, 무한"
  - "Each 키워드"
  - "명령, 반복"
  - "For Each 문"
  - "컬렉션, 명령 반복"
  - "루프, 무한"
  - "For Each...Next 문"
  - "For 키워드[Visual Basic], For Each...Next 문"
  - "Exit 문, For Each...Next 문"
  - "반복"
ms.assetid: ebce3120-95c3-42b1-b70b-fa7da40c75e2
caps.latest.revision: 56
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 56
---
# For Each...Next 문(Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

컬렉션의 각 요소에 대해 문의 그룹을 반복합니다.  
  
## 구문  
  
```  
For Each element [ As datatype ] In group  
    [ statements ]  
    [ Continue For ]  
    [ statements ]  
    [ Exit For ]  
    [ statements ]  
Next [ element ]  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`element`|`For Each` 문에서는 필수적 요소입니다.  `Next` 문에서는 선택적 요소입니다.  컬렉션의  요소를 반복하는 데 사용되는 변수입니다.|  
|`datatype`|필요한 경우 `element` 이미 선언 되지 않습니다.  `element`의 데이터 형식입니다.|  
|`group`|필수 요소.  컬렉션 형식 또는 개체 형식 사용 하는 변수입니다.  `statements`를 반복할 컬렉션을 참조합니다.|  
|`statements`|선택 사항입니다.  `For Each`와 `Next` 사이에서 `group`의 각 항목에 대해 실행되는 하나 이상의 문입니다.|  
|`Continue For`|선택 사항입니다.  컨트롤을 `For Each` 루프 시작으로 전송합니다.|  
|`Exit For`|선택 사항입니다.  `For Each` 루프 밖으로 제어를 전달합니다.|  
|`Next`|필수 요소.  `For Each` 루프의 정의를 끝냅니다.|  
  
## 간단한 예제  
 컬렉션이나 배열의 각 요소에 대해 여러 문을 반복하려는 경우 `For Each`...`Next` 루프를 사용합니다.  
  
> [!TIP]
>  [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)은 각 루프의 반복을 제어 변수와 연결하고 해당 변수의 초기 값과 최종 값을 결정할 수 있는 경우에 제대로 작동합니다.  그러나 컬렉션을 처리 하는 경우는 초기 값과 최종 값 이라는 개념이 의미 없고 컬렉션의 요소 수를 반드시 알 수 없습니다.  이 이런 경우에에서는 `For Each`...`Next` 루프 더 나은 선택 하는 경우가 많습니다.  
  
 다음 예제에서는 `For Each`...`Next` 문 목록 컬렉션의 모든 요소를 통해 반복 합니다.  
  
 [!code-vb[VbVbalrStatements#121](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-each-next-statement_1.vb)]  
  
 추가 예제는 [컬렉션](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md) 및 [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)을 참조하십시오.  
  
## 중첩 된 루프  
 한 루프를 다른 루프 내에 배치하여 `For Each` 루프를 서로 중첩할 수 있습니다.  
  
 다음 예제는 중첩된 `For Each`…`Next` 구조체를 보여 줍니다.  
  
 [!code-vb[VbVbalrStatements#122](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-each-next-statement_2.vb)]  
  
 루프를 중첩 하는 경우 각 루프에는 고유 해야 합니다 `element` 변수입니다.  
  
 또한 다른 종류의 제어 구조를 서로 중첩할 수 있습니다.  자세한 내용은 [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)을 참조하십시오.  
  
## 계속 해 서 exit  
 [Exit For](../../../visual-basic/language-reference/statements/exit-statement.md) 문 실행을 종료 하는 `For`...`Next` 다음에 오는 문에 루프 및 전송 컨트롤의 `Next` 문.  
  
 `Continue For` 문은 제어를 루프의 다음 반복으로 바로 이동합니다.  자세한 내용은 [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md)을 참조하십시오.  
  
 다음 예제에서는 `Continue For` 및 `Exit For` 문을 사용하는 방법을 설명합니다.  
  
 [!code-vb[VbVbalrStatements#123](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-each-next-statement_3.vb)]  
  
 `For Each` 루프에 임의 수의 `Exit For` 문을 배치할 수 있습니다.  중첩된 `For Each` 루프 내에 `Exit For`를 사용하면 Exit For는 가장 안쪽의 루프를 끝내고 중첩 수준이 그 다음으로 높은 루프에 제어를 전달합니다.  
  
 `Exit For`는 `If`...`Then`...`Else` 구조와 마찬가지로 주로 일부 조건을 계산한 후에 사용됩니다.  다음 조건에 대해 `Exit For`를 사용할 수 있습니다.  
  
-   계속 반복은 불필요하며 불가능합니다.  오류가 있는 값 또는 종료 요청이 원인일 수 있습니다.  
  
-   `Try`...`Catch`...`Finally`에 예외가 catch되었습니다.  `Finally` 블록 끝에 `Exit For`를 사용할 수 있습니다.  
  
-   매우 많이 또는 무한정 실행되는 루프인 무한 루프가 있습니다.  이러한 조건을 감지한 경우 `Exit For`를 사용하여 루프를 이스케이프할 수 있습니다.  자세한 내용은 [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md)을 참조하십시오.  
  
## 반복기  
 사용 하는  *반복기* 통해 사용자 지정 반복을 수행 합니다.  반복기는 함수가 될 수 있습니다 또는 `Get` 접근자입니다.  사용 하는 `Yield` 문 컬렉션 1 번의 각 요소를 반환 합니다.  
  
 반복기를 사용 하 여 호출을 `For Each...Next` 문.  각 반복의 `For Each` 루프 반복기를 호출 합니다.  때는 `Yield` 문에 도달에서 반복기가 식에는 `Yield` 문입니다 반환 하 고 코드에서 현재 위치를 유지 합니다.  실행 위치에서 반복기가 호출 되는 다음 번 다시 시작 됩니다.  
  
 다음 예제에서는 반복기 함수를 사용합니다.  반복기 함수는 `Yield` 문 내부에  [에 대 한...다음](../../../visual-basic/language-reference/statements/for-next-statement.md) 루프.  에 `ListEvenNumbers` 메서드를 반복할 때마다의 `For Each` 문의 본문 옆에 진행 하는 반복기 함수 호출을 만듭니다 `Yield` 문.  
  
 [!code-vb[VbVbalrStatements#127](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-each-next-statement_4.vb)]  
  
 자세한 내용은 [반복기](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md), [Yield 문](../../../visual-basic/language-reference/statements/yield-statement.md) 및 [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md)을 참조하십시오.  
  
## 기술 구현  
 When a `For Each`…`Next` 문이 실행 되 면, Visual Basic 컬렉션에 루프를 시작 하기 전에 한 번만 계산 합니다.  문 블록이 변경 되는 경우 `element` 또는 `group`, 이러한 변경 내용은 루프의 반복 영향을 주지 않습니다.  
  
 컬렉션의 모든 요소가 `element`에 할당되었으면 `For Each` 루프가 종료되고 `Next` 문 다음 문으로 제어가 전달됩니다.  
  
 경우 `element` 않은 선언 된이 루프의 외부에 선언 해야에 `For Each` 문.  `As` 문을 사용하여 `element`의 형식을 명시적으로 선언할 수도 있고 형식을 할당하는 형식 유추에 의존할 수도 있습니다.  어느 경우든 `element`의 범위는 루프의 본문입니다.  그러나 루프 외부와 내부 모두에 `element`를 선언할 수는 없습니다.  
  
 필요에 따라 `Next` 문에 `element`를 지정할 수 있습니다.  이렇게 하면 `For Each` 루프가 중첩된 경우에 특히 프로그램의 가독성이 향상됩니다.  해당 `For Each` 문에 나타나는 변수와 동일한 변수를 지정해야 합니다.  
  
 루프 안에서 `element` 값을 변경하지 못하도록 할 수 있습니다.  이렇게 하면 코드를 읽고 디버그하기가 더 어려워질 수 있습니다.  값을 변경 `group` 컬렉션이 나 루프를 처음 입력 해도 해당 요소에 영향을 주지 않습니다.  
  
 때에 중첩 루프를 경우는 `Next` 외부 중첩 수준의 문이 전에 `Next` 내부 수준에, 컴파일러는 오류 신호를 보냅니다.  그러나 모든 `Next` 문에 `element`를 지정하는 경우에만 컴파일러에서 이러한 겹치는 오류를 검색할 수 있습니다.  
  
 코드가 특정 순서로 컬렉션을 통과 하는에 있는 `For Each`...`Next` 루프 없는 최선의 선택, 열거자 개체의 특징을 모르면 컬렉션을 노출 합니다.  이동 Visual Basic 있지만 여 결정 되지 않습니다는 <xref:System.Collections.IEnumerator.MoveNext%2A> 메서드는 열거자 개체의.  따라서 `element`에서 처음 반환되는 컬렉션 요소나 지정된 요소 다음에 반환되는 컬렉션 요소를 예측할 수 없을 수 있습니다.  이 경우 `For`...`Next` 또는 `Do`...`Loop` 등의 다른 루프 구조를 사용하면 좀더 신뢰할 수 있는 결과를 얻을 수 있습니다..  
  
 `element`의 데이터 형식은 `group` 요소의 데이터 형식을 변환할 수 있는 형식이어야 합니다.  
  
 데이터 형식은 `group` 열거 가능한 배열 또는 컬렉션을 참조 하는 참조 형식 이어야 합니다.  대부분 `group`은 [System.Collections](assetId:///System.Collections?qualifyHint=False&amp;autoUpgrade=True) 네임스페이스의 `T:System.Collections.IEnumerable` 인터페이스 또는 [System.Collections.Generic](assetId:///System.Collections.Generic?qualifyHint=False&amp;autoUpgrade=True) 네임스페이스의 `T:System.Collections.Generic.IEnumerable`1` 인터페이스를 구현하는 개체를 참조한다는 뜻입니다.  `System.Collections.IEnumerable`은 <xref:System.Collections.IEnumerable.GetEnumerator%2A> 메서드를 정의하여, 컬렉션의 열거자 개체를 반환합니다.  열거자 개체는 `System.Collections` 네임스페이스의 `System.Collections.IEnumerator` 인터페이스를 구현하며 <xref:System.Collections.IEnumerator.Current%2A> 속성과 <xref:System.Collections.IEnumerator.Reset%2A> 및 <xref:System.Collections.IEnumerator.MoveNext%2A> 메서드를 노출합니다.  Visual Basic에서는 이를 사용하여 컬렉션을 순회합니다.  
  
### 축소 변환  
 `Option Strict`가 `On`으로 설정된 경우 축소 변환을 수행하면 대개 컴파일 오류가 발생합니다.  하지만 `For Each` 문에서는 `group`의 요소에서 `element`로의 변환이 런타임에 계산되고 수행되므로 변환 축소로 인한 컴파일러 오류가 표시되지 않습니다.  
  
 다음 예제에 대 한 할당 `m` 초기 값으로 `n` 때 컴파일되지 `Option Strict` 때문에 변환에 `Long` 에 `Integer` 은 축소 변환입니다.  하지만 `For Each` 문에서는 `number`에 대한 할당 시 `Long`에서 `Integer`로의 변환이 필요함에도 불구하고 컴파일러 오류가 보고되지 않습니다.  큰 숫자가 포함된 `For Each` 문에서는 <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A>가 큰 숫자에 적용될 때 런타임 오류가 발생합니다.  
  
 [!code-vb[VbVbalrStatements#89](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-each-next-statement_5.vb)]  
  
### IEnumerator 호출  
 `For Each`...`Next` 루프 실행이 시작되면 Visual Basic에서 `group`이 올바른 컬렉션 개체를 참조하는지 확인합니다.  올바른 컬렉션 개체를 참조하지 않는 경우 예외가 throw됩니다.  그렇지 않으면 열거자 개체의 <xref:System.Collections.IEnumerator.MoveNext%2A> 메서드와 <xref:System.Collections.IEnumerator.Current%2A> 속성을 호출하여 첫 번째 요소를 반환합니다.  `MoveNext`가 다음 요소가 없음을 나타내면, 즉 컬렉션이 비어 있으면 `For Each` 루프가 종료되고 `Next` 문 다음 문으로 제어가 전달됩니다.  그렇지 않으면 Visual Basic에서 `element`를 첫 번째 요소로 설정하고 문 블록을 실행합니다.  
  
 Visual Basic에서는 `Next` 문을 만날 때마다 `For Each` 문으로 돌아갑니다.  다시 `MoveNext`와 `Current`를 호출하여 다음 요소를 반환하고 결과에 따라 블록을 다시 실행하거나 루프를 종료합니다.  `MoveNext`에서 다음 요소가 없음을 나타내거나 `Exit For` 문을 만날 때까지 이 과정이 계속됩니다.  
  
 **컬렉션 수정.** 반환 된 열거자 개체 <xref:System.Collections.IEnumerable.GetEnumerator%2A> 일반적으로 추가, 삭제, 교체 또는 재배열 된 요소 컬렉션을 변경할 수 없습니다.  `For Each`...`Next` 루프를 시작한 다음 컬렉션을 변경하면 열거자 개체는 유효하지 않게 되고, 다음에 요소에 액세스하려고 하면 <xref:System.InvalidOperationException> 예외가 발생합니다.  
  
 그러나 이와 같이 수정을 차단할지 결정 되지 않은 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], 하지 않고 구현 된 <xref:System.Collections.IEnumerable> 인터페이스.  반복 과정에서 수정할 수 있도록 `IEnumerable`을 구현할 수 있습니다.  그러한 동적 수정 방식을 염두에 두고 있다면 사용 중인 컬렉션에 대한 `IEnumerable` 구현의 특징을 이해할 필요가 있습니다.  
  
 **컬렉션 요소 수정.** 열거자 개체의 <xref:System.Collections.IEnumerator.Current%2A> 속성은 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)이며 각 컬렉션 요소의 로컬 복사본을 반환합니다.  이것은 `For Each`...`Next` 루프에서 요소 자체를 수정할 수 없음을 의미합니다.  수정 내용을 들은 로컬 사본 으로부터 영향을 `Current` 를 내부 컬렉션에 반영 되지 않습니다.  그러나 요소가 참조 형식인 경우에는 요소가 가리키는 인스턴스의 멤버를 수정할 수 있습니다.  다음 예제에서는 수정의 `BackColor` 멤버 각각의 `thisControl` 요소.  그러나 수정할 수 없습니다 `thisControl` 자체.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 앞의 예제에서는 `thisControl` 자체는 수정할 수 없어도 각 `thisControl` 요소의 `BackColor` 멤버는 수정할 수 있습니다.  
  
 **배열 탐색.** <xref:System.Array> 클래스는 <xref:System.Collections.IEnumerable> 인터페이스를 구현하므로 모든 배열이 <xref:System.Array.GetEnumerator%2A> 메서드를 노출합니다.  이것은 `For Each`...`Next` 루프로 배열을 여러 번 반복할 수 있음을 의미합니다.  그러나 배열 요소는 읽을 수만 있습니다.  이는 변경할 수 없습니다.  
  
## 예제  
 다음 예제에서는 <xref:System.IO.DirectoryInfo> 클래스를 사용하여 C:\\ 디렉터리에 있는 모든 폴더를 표시합니다.  
  
 [!code-vb[VbVbalrStatements#124](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-each-next-statement_6.vb)]  
  
## 예제  
 다음 예제에서는 컬렉션을 정렬 하는 프로시저를 보여 줍니다.  인스턴스를 정렬 하는 예제는 한 `Car` 에 저장 하는 클래스는 <xref:System.Collections.Generic.List%601>.  `Car` 클래스가 구현 된 <xref:System.IComparable%601> 인터페이스를 필요로 하는 <xref:System.IComparable%601.CompareTo%2A> 메서드 구현.  
  
 각 호출에는 <xref:System.IComparable%601.CompareTo%2A> 메서드는 정렬에 사용 되는 단일 비교를 만듭니다.  사용자가 작성 한 코드에는 `CompareTo` 각 비교의 현재 개체를 다른 개체에 대 한 값을 반환 합니다.  반환 되는 값 이하일 경우 현재 개체 보다 다른 개체를 현재 개체가 다른 개체 보다 크면 0 보다 크고 0 같으면.  이 코드를 보다 큼, 보다 작음, 기준을 정의 하 고 같은 수 있습니다.  
  
 에 `ListCars` 메서드는 `cars.Sort()` 문 목록 정렬.  이 호출에는 <xref:System.Collections.Generic.List%601.Sort%2A> 메서드는 <xref:System.Collections.Generic.List%601> 발생의 `CompareTo` 메서드가 자동으로 호출 하려면는 `Car` 개체의 `List`.  
  
 [!code-vb[VbVbalrStatements#125](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-each-next-statement_7.vb)]  
  
## 참고 항목  
 [컬렉션](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md)   
 [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Loop Structures](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md)   
 [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md)   
 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [Collection Initializers](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)   
 [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)