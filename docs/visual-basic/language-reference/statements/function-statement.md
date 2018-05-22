---
title: Function 문(Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Function
helpviewer_keywords:
- procedures [Visual Basic], creating
- Function procedures [Visual Basic], Function statement syntax
- functions [Visual Basic], function procedures
- ParamArray keyword [Visual Basic], Function statements
- Private keyword [Visual Basic], Function statements
- declarations [Visual Basic], procedures
- procedures [Visual Basic], declaration
- Public keyword [Visual Basic], in Function statement
- ByVal keyword [Visual Basic], Function statements
- procedures [Visual Basic], recursive
- Implements keyword [Visual Basic], Function statements
- procedures [Visual Basic], returning values
- Exit statement [Visual Basic], in Function procedures
- recursive procedures
- As keyword [Visual Basic], in Function statement
- Optional keyword [Visual Basic], Function statements
- Function statement [Visual Basic]
- Visual Basic code, Function procedures
- procedures [Visual Basic], function
- ByRef keyword [Visual Basic], Function statements
- Friend keyword [Visual Basic], Function statements
- End keyword [Visual Basic], Function statements
- Handles keyword [Visual Basic], Function statements
ms.assetid: a4497077-0f46-4ede-a27f-9e8670df52b9
ms.openlocfilehash: 908aa594ecbdd8ae2ec5a06de8181a1b16bb7e40
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
---
# <a name="function-statement-visual-basic"></a>Function 문(Visual Basic)
선언 이름과 매개 변수를 정의 하는 코드는 `Function` 프로시저입니다.  
  
## <a name="syntax"></a>구문  
  
```  
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]  
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Function ]  
    [ statements ]  
End Function  
```  
  
## <a name="parts"></a>요소  
  
-   `attributelist`  
  
     선택 사항입니다. 참조 [특성 목록](attribute-list.md)합니다.  
  
-   `accessmodifier`  
  
     선택 사항입니다. 다음 중 하나일 수 있습니다.  
  
    -   [공용](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [보호됨](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [전용](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   [Protected Friend](../../language-reference/modifiers/protected-friend.md)

    - [보호 된 개인](../../language-reference/modifiers/private-protected.md)  
  
     참조 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.  
  
-   `proceduremodifiers`  
  
     선택 사항입니다. 다음 중 하나일 수 있습니다.  
  
    -   [오버로드](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [재정의](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [재정의 가능](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     선택 사항입니다. 참조 [공유](../../../visual-basic/language-reference/modifiers/shared.md)합니다.  
  
-   `Shadows`  
  
     선택 사항입니다. 참조 [그림자](../../../visual-basic/language-reference/modifiers/shadows.md)합니다.  
  
-   `Async`  
  
     선택 사항입니다. 참조 [비동기](../../../visual-basic/language-reference/modifiers/async.md)합니다.  
  
-   `Iterator`  
  
     선택 사항입니다. 참조 [반복기](../../../visual-basic/language-reference/modifiers/iterator.md)합니다.  
  
-   `name`  
  
     필수. 프로시저의 이름입니다. 참조 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.  
  
-   `typeparamlist`  
  
     선택 사항입니다. 제네릭 프로시저에 대 한 형식 매개 변수의 목록입니다. 참조 [목록을 입력](type-list.md)합니다.  
  
-   `parameterlist`  
  
     선택 사항입니다. 이 프로시저의 매개 변수를 나타내는 지역 변수 이름의 목록이 있습니다. 참조 [매개 변수 목록](parameter-list.md)합니다.  
  
-   `returntype`  
  
     필요한 경우 `Option Strict` 은 `On`합니다. 이 프로시저에서 반환 된 값의 데이터 형식입니다.  
  
-   `Implements`  
  
     선택 사항입니다. 하나 이상의이 절차를 구현 함을 나타냅니다 `Function` 절차,이 프로시저의 포함 하는 클래스 또는 구조체에서 구현 되는 인터페이스에 정의 된 하나씩 있습니다. 참조 [문을 구현](implements-statement.md)합니다.  
  
-   `implementslist`  
  
     `Implements`가 제공된 경우 필수입니다. 구현할 `Function` 프로시저 목록입니다.  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     각 `implementedprocedure`에는 다음과 같은 구문과 요소가 있습니다.  
  
     `interface.definedname`  
  
    |파트|설명|  
    |---|---|  
    |`interface`|필수. 이 프로시저에 의해 구현 되는 인터페이스의 이름의 클래스 또는 구조체를 포함 합니다.|  
    |`definedname`|필수. 프로시저가 `interface`에 정의되는 이름입니다.|  
  
-   `Handles`  
  
     선택 사항입니다. 이 절차에서 하나 이상의 특정 이벤트를 처리할 수 있음을 나타냅니다. 참조 [처리](handles-clause.md)합니다.  
  
-   `eventlist`  
  
     `Handles`가 제공된 경우 필수입니다. 이 프로시저에서 처리 하는 이벤트 목록입니다.  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     각 `eventspecifier`에는 다음과 같은 구문과 요소가 있습니다.  
  
     `eventvariable.event`  
  
    |파트|설명|  
    |---|---|  
    |`eventvariable`|필수. 개체 변수는 이벤트를 발생 시키는 구조체 또는 클래스의 데이터 형식으로 선언 합니다.|  
    |`event`|필수. 이 프로시저에서 처리 하는 이벤트의 이름입니다.|  
  
-   `statements`  
  
     선택 사항입니다. 이 프로시저 내에서 실행할 문 블록.  
  
-   `End Function`  
  
     이 프로시저의 정의 종료합니다.  
  
## <a name="remarks"></a>설명  
 모든 실행 코드는 프로시저 안에 있어야 합니다. 차례로 각 프로시저에는 클래스, 구조체 또는 포함 하는 클래스, 구조체 또는 모듈 참조 하는 모듈 내에서 선언 됩니다.  
  
 호출 코드에는 값을 반환 하려면 사용는 `Function` 프로시저; 사용 그렇지 않은 경우는 `Sub` 프로시저입니다.  
  
## <a name="defining-a-function"></a>함수를 정의합니다.  
 정의할 수는 `Function` 모듈 수준에만 프로시저입니다. 따라서 함수에 대 한 선언 컨텍스트 클래스, 구조체, 모듈의 경우, 또는 인터페이스 여야 하며 소스 파일, 네임 스페이스, 프로시저 또는 블록 수 없습니다. 자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](declaration-contexts-and-default-access-levels.md)을 참조하세요.  
  
 `Function` 프로시저는 기본적으로 공용 액세스 합니다. 액세스 한정자로 액세스 수준을 조정할 수 있습니다.  
  
 A `Function` 프로시저는 프로시저에서 반환 하는 값의 데이터 형식을 선언할 수 있습니다. 모든 데이터 형식이 나 열거형, 구조체, 클래스 또는 인터페이스의 이름을 지정할 수 있습니다. 지정 하지 않으면는 `returntype` 매개 변수, 프로시저 반환 `Object`합니다.  
  
 이 절차를 사용 하는 경우는 `Implements` 있어야 키워드, 클래스 또는 구조체는 `Implements` 바로 뒤에 오는 문을 해당 `Class` 또는 `Structure` 문. `Implements` 문을에 지정 된 각 인터페이스를 포함 해야 `implementslist`합니다. 그러나는 인터페이스를 정의 하 여 이름을 `Function` (에서 `definedname`)이이 프로시저의 이름과 일치할 필요가 없습니다 (에서 `name`).  
  
> [!NOTE]
>  함수 식 인라인으로 정의를 람다 식에 사용할 수 있습니다. 자세한 내용은 참조 [함수 식](../../../visual-basic/language-reference/operators/function-expression.md) 및 [람다 식](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)합니다.  
  
## <a name="returning-from-a-function"></a>함수에서 반환  
 경우는 `Function` 프로시저가 호출 코드에 반환 되 면 실행이 프로시저를 호출한 문 다음에 오는 문을 사용 하 여 계속 합니다.  
  
 함수에서 값을 반환 하려면 함수 이름에 값을 할당 하거나 포함 된 `Return` 문.  
  
 `Return` 문은 동시에 반환 값을 할당 하 고 다음 예와 같이 함수를 종료 합니다.  
  
 [!code-vb[VbVbalrStatements#24](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_1.vb)]  
  
 다음 예제에서는 함수 이름에 반환 값을 할당 `myFunction` 다음 사용 하 여는 `Exit Function` 문 실행 합니다.  
  
 [!code-vb[VbVbalrStatements#23](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_2.vb)]  
  
 `Exit Function` 및 `Return` 문을 사용 하면 즉시 종료 한 `Function` 프로시저입니다. 개수에 관계 없이 `Exit Function` 및 `Return` 문은 프로시저에서 아무 곳 이나 나타날 수 있으며 함께 사용할 수 있습니다 `Exit Function` 및 `Return` 문.  
  
 사용 하는 경우 `Exit Function` 값을 할당 하지 않고 `name`에 지정 된 데이터 형식에 대 한 기본값을 반환 하는 프로시저 `returntype`합니다. 경우 `returntype` 지정 하지 않은 경우 프로시저가 반환 `Nothing`에 대 한 기본 값인 `Object`합니다.  
  
## <a name="calling-a-function"></a>함수 호출  
 호출 하는 `Function` 프로시저 이름, 식의 괄호 안에 인수 목록을 사용 하 여 프로시저입니다. 인수를 제공 하지 하는 경우에 괄호를 생략할 수 있습니다. 그러나 코드는 항상 괄호를 포함 하는 경우 더 쉽게 읽을 수 있습니다.  
  
 호출 하는 `Function` 모든 라이브러리를 호출 하는 동일한 방식으로 작동와 같은 절차 `Sqrt`, `Cos`, 또는 `ChrW`합니다.  
  
 사용 하 여 함수를 호출할 수도 있습니다는 `Call` 키워드입니다. 이 경우 반환 값은 무시 됩니다. 사용은 `Call` 키워드는 대부분의 경우에 권장 되지 않습니다. 자세한 내용은 참조 [Call 문을](call-statement.md)합니다.  
  
 Visual Basic에는 산술 식 내부 효율성을 높이기 위해 경우에 따라 다시 정렬 합니다. 이런 이유로 사용해 서는 안는 `Function` 함수 같은 식에서 변수 값이 변경 될 때 산술 식에는 프로시저입니다.  
  
## <a name="async-functions"></a>비동기 함수  
 *비동기* 기능을 사용 하면 명시적 콜백을 사용 하거나 수동으로 여러 함수 또는 람다 식에 코드를 분할 하지 않고도 비동기 함수를 호출할 수 있습니다.  
  
 사용 하는 함수를 표시 하는 경우는 [비동기](../../../visual-basic/language-reference/modifiers/async.md) 사용할 수 있습니다 한정자는 [Await](../../../visual-basic/language-reference/operators/await-operator.md) 함수에 연산자. 에 도달할 때 제어는 `Await` 식에는 `Async` 호출자에 게 제어가 반환 함수와 함수에서 진행 대기 중인된 작업이 완료 될 때까지 일시 중단 합니다. 작업이 완료 될 때 실행 함수에서 다시 시작 수 있습니다.  
  
> [!NOTE]
>  `Async` 는 첫 번째 대기 된 개체를 아직 완료 되지 않은 발생 하거나 프로시저가 호출자에 게 반환 또는의 끝에 도달는 `Async` 프로시저 중 먼저 발생 합니다.  
  
 `Async` 함수 반환 형식으로 지정할 수 있습니다 <xref:System.Threading.Tasks.Task%601> 또는 <xref:System.Threading.Tasks.Task>합니다. 예로 `Async` 의 반환 형식을 가진 함수를 <xref:System.Threading.Tasks.Task%601> 아래에 제공 됩니다.  
  
 `Async` 함수는 선언할 수 없습니다 [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) 매개 변수입니다.  
  
 A [Sub 문을](sub-statement.md) 로 표시할 수 있습니다는 `Async` 한정자입니다. 이 주로 사용 이벤트 처리기에 대 한 값을 반환할 수 없습니다. `Async``Sub` 프로시저 대기할 수 없습니다 및의 호출자는 `Async``Sub` 프로시저에 의해 throw 되는 예외를 catch 할 수 없습니다는 `Sub` 프로시저입니다.  
  
 에 대 한 자세한 내용은 `Async` 함수 참조 [Async 및 Await를 사용한 비동기 프로그래밍](../../../visual-basic/programming-guide/concepts/async/index.md), [비동기 프로그램의 제어 흐름](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), 및 [비동기 반환 형식](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
## <a name="iterator-functions"></a>반복기 함수  
 *반복기* 함수 목록 또는 배열의 같은 컬렉션에 대해 사용자 지정 반복을 수행 합니다. 반복기 함수를 사용 하 여는 [Yield](yield-statement.md) 문을 한 번에 각 요소를 반환할 수 있습니다. 경우는 [Yield](yield-statement.md) 문에 도달 하면 코드의 현재 위치가 기억 됩니다. 다음에 반복기 함수가 호출되면 해당 위치에서 실행이 다시 시작됩니다.  
  
 사용 하 여 클라이언트 코드에서 반복기를 호출는 [각각에 대해... 다음](for-each-next-statement.md) 문.  
  
 반복기 함수의 반환 형식은 <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, 또는 <xref:System.Collections.Generic.IEnumerator%601>합니다.  
  
 자세한 내용은 [반복기](../../programming-guide/concepts/iterators.md)를 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Function` 이름, 매개 변수, 및의 본문을 형성 하는 코드를 선언 하는 문에 `Function` 프로시저입니다. `ParamArray` 한정자를 통해 함수에 가변 개수의 인수를 수락 합니다.  
  
 [!code-vb[VbVbalrStatements#25](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_3.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 앞의 예제에서 선언 된 함수를 호출 합니다.  
  
 [!code-vb[VbVbalrStatements#26](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_4.vb)]  
  
## <a name="example"></a>예제  
 다음 예에서 `DelayAsync` 는 `Async``Function` 의 반환 형식이 있는 <xref:System.Threading.Tasks.Task%601>합니다. `DelayAsync`에는 정수를 반환하는 `Return` 문이 포함됩니다. 따라서 함수 선언의 `DelayAsync` 의 반환 형식이 있어야 `Task(Of Integer)`합니다. 반환 형식이 이기 `Task(Of Integer)`, 평가 `Await` 에 식을 `DoSomethingAsync` 정수가 생성 됩니다. 이 문에서이 확인할: `Dim result As Integer = Await delayTask`합니다.  
  
 `startButton_Click` 절차의 한 예로 `Async Sub` 프로시저입니다. 때문에 `DoSomethingAsync` 는 `Async` 함수, 작업에 대 한 호출에 대 한 `DoSomethingAsync` 기다려야, 다음 문과 같이: `Await DoSomethingAsync()`합니다. `startButton_Click``Sub` 프로시저 함께 정의 되어야 합니다는 `Async` 한정자 있기 때문에 `Await` 식입니다.  
  
 [!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/function-statement_5.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Sub 문](sub-statement.md)  
 [Function 프로시저](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)  
 [매개 변수 목록](parameter-list.md)  
 [Dim 문](dim-statement.md)  
 [Call 문](call-statement.md)  
 [Of](of-clause.md)  
 [매개 변수 배열](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)  
 [방법: 제네릭 클래스 사용](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [프로시저 문제 해결](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)  
 [람다 식](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [함수 식](../../../visual-basic/language-reference/operators/function-expression.md)
