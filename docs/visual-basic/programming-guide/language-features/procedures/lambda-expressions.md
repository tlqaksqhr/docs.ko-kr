---
title: 람다 식(Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.LambdaFunction
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
caps.latest.revision: 52
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 69ac88d295420277e99058d0f80a5ae1c2ce2e39
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="lambda-expressions-visual-basic"></a>람다 식(Visual Basic)
A *람다 식을* 은 함수 또는 서브루틴 대리자가 유효한 함께 사용 될 수 있는 이름이 없는 합니다. 람다 식을 함수 또는 서브루틴 수 있으며 또는 여러 줄 수 있습니다. 람다 식에는 현재 범위에서 값을 전달할 수 있습니다.  
  
> [!NOTE]
>  `RemoveHandler` 문은 예외입니다. 람다 식에는 대리자 매개 변수에 전달할 수 없습니다 `RemoveHandler`합니다.  
  
 람다 식을 사용 하 여 만듭니다는 `Function` 또는 `Sub` 표준 함수 또는 서브루틴을 만드는 경우와 마찬가지로 키워드입니다. 그러나 람다 식 문에 포함 됩니다.  
  
 다음 예제는 해당 인수를 증가 시키고 값을 반환 하는 람다 식입니다. 함수에 대 한 두에서는 한 줄 및 여러 줄 람다 식 구문을 보여 줍니다.  
  
 [!code-vb[VbVbalrLambdas#14](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_1.vb)]  
  
 다음 예제는 값을 콘솔에 작성 하는 람다 식입니다. 서브루틴에 대 한 두에서는 한 줄 및 여러 줄 람다 식 구문을 보여 줍니다.  
  
 [!code-vb[VbVbalrLambdas#15](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_2.vb)]  
  
 이전 예제에서 람다 식에 할당 되지 않았는지 변수 이름을 확인 합니다. 변수를 참조할 때마다 람다 식을 호출 합니다. 선언 하 고 다음 예제와 같이 같은 시간에 람다 식을 호출할 수도 있습니다.  
  
 [!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_3.vb)]  
  
 람다 식을 함수 호출의 값으로 반환 될 수 있습니다 (의 예제 에서처럼는 [컨텍스트](#context) 이 항목의 뒷부분에 나오는 섹션), 다음에 표시 된 대로 대리자 형식을 사용 하는 매개 변수에 대해 인수로 전달 하거나 예입니다.  
  
 [!code-vb[VbVbalrLambdas#8](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_4.vb)]  
  
## <a name="lambda-expression-syntax"></a>람다 식 구문  
 람다 식의 구문은 유사 표준 함수 또는 서브루틴의 합니다. 차이점은 다음과 같습니다.  
  
-   람다 식에 이름이 없습니다.  
  
-   람다 식은와 같은 한정자를 사용할 수 없습니다 `Overloads` 또는 `Overrides`합니다.  
  
-   한 줄 람다 함수를 사용 하지 않는 한 `As` 절에 반환 형식을 지정 합니다. 대신, 람다 식의 본문으로 계산 되는 값과에서 형식 유추 됩니다. 예를 들어 람다 식의 본문이 `cust.City = "London"`, 해당 반환 형식이 `Boolean`합니다.  
  
-   여러 줄 람다 함수에서 있습니다 지정 하거나 반환 형식을 사용 하 여는 `As` 절을 생략 하거나는 `As` 절 반환 형식을 유추 되도록 합니다. 경우는 `As` 여러 줄 람다 함수에 대 한 절을 생략 하면, 모든 기준 형식에 반환 형식이 유추는 `Return` 여러 줄 람다 함수의 문에서 합니다. *기준 형식은* 를 다른 모든 형식이 확장 될 수 있는 고유 형식입니다. 이 고유 형식을 확인할 수 없는 경우 기준 형식은 배열의 다른 모든 형식에 범위를 좁힐 수 있는 고유 형식이입니다. 이러한 고유 형식을 모두 확인할 수 없는 경우 기준 형식은 `Object`입니다. 이 예제의 경우 `Option Strict` 로 설정 된 `On`, 컴파일러 오류가 발생 합니다.  
  
     예를 들어 식에 제공 되는 `Return` 형식의 값을 포함 하는 문을 `Integer`, `Long`, 및 `Double`, 결과 배열의 형식입니다 `Double`합니다. 둘 다 `Integer` 및 `Long` 으로 확장 `Double` 만 `Double`합니다. 따라서 기준 형식은 `Double` 입니다. 자세한 내용은 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)을 참조하세요.  
  
-   한 줄 함수 본문에는 문이 아닌 값을 반환 하는 식 이어야 합니다. 없는 `Return` 함수의 한 줄 문입니다. 한 줄 함수에서 반환 된 값에는 함수 본문에 있는 식의 값이입니다.  
  
-   한 줄 서브루틴의 본문은 한 줄 문 이어야 합니다.  
  
-   한 줄 함수와 서브루틴을 다루지 않습니다는 `End Function` 또는 `End Sub` 문.  
  
-   람다 식 매개 변수의 데이터 형식을 사용 하 여 지정할 수 있습니다는 `As` 키워드 또는 매개 변수의 데이터 형식을 유추할 수 있습니다. 데이터 형식 중 하나 또는 모두를 유추 합니다 모든 매개 변수에 지정 해야 합니다.  
  
-   `Optional`및 `Paramarray` 매개 변수는 허용 되지 않습니다.  
  
-   제네릭 매개 변수가 허용 되지 않습니다.  
  
## <a name="async-lambdas"></a>비동기 람다  
 람다 식과 사용 하 여 비동기 처리를 통합 하는 문을 쉽게 만들 수 있습니다는 [비동기](../../../../visual-basic/language-reference/modifiers/async.md) 및 [Await 연산자](../../../../visual-basic/language-reference/operators/await-operator.md) 키워드입니다. 예를 들어 다음 Windows Forms 예제에는 비동기 메서드 `ExampleMethodAsync`를 호출하고 기다리는 이벤트 처리기가 포함되어 있습니다.  
  
```vb  
Public Class Form1  
  
    Async Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click  
        ' ExampleMethodAsync returns a Task.  
        Await ExampleMethodAsync()  
        TextBox1.Text = vbCrLf & "Control returned to button1_Click."  
    End Sub  
  
    Async Function ExampleMethodAsync() As Task  
        ' The following line simulates a task-returning asynchronous process.  
        Await Task.Delay(1000)  
    End Function  
  
End Class  
```  
  
 비동기 람다를 사용 하 여 동일한 이벤트 처리기를 추가할 수는 [AddHandler 문](../../../../visual-basic/language-reference/statements/addhandler-statement.md)합니다. 이 처리기를 추가하려면 다음 예제에 표시된 것처럼 람다 매개 변수 목록에 `Async` 한정자를 추가합니다.  
  
```vb  
Public Class Form1  
  
    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load  
        AddHandler Button1.Click,   
            Async Sub(sender1, e1)  
                ' ExampleMethodAsync returns a Task.  
                Await ExampleMethodAsync()  
                TextBox1.Text = vbCrLf & "Control returned to Button1_ Click."  
            End Sub  
    End Sub  
  
    Async Function ExampleMethodAsync() As Task  
        ' The following line simulates a task-returning asynchronous process.  
        Await Task.Delay(1000)  
    End Function  
  
End Class  
```  
  
 만들고 비동기 메서드를 사용 하는 방법에 대 한 자세한 내용은 참조 [Async 및 Await를 사용한 비동기 프로그래밍](../../../../visual-basic/programming-guide/concepts/async/index.md)합니다.  
  
##  <a name="context"></a>컨텍스트  
 람다 식 정의 된 범위와 해당 컨텍스트를 공유 합니다. 포함 범위에 작성 된 코드와 동일한 액세스 권한이 있음 여기에 멤버 변수, 함수 및 sub에 대 한 액세스 포함 됩니다. `Me`를 포함 하는 범위에서 지역 변수 및 매개 변수입니다.  
  
 지역 변수 및 매개 변수를 포함 하는 범위에 대 한 액세스 범위 하의 수명을 넘어서는 확장할 수 있습니다. 으로 참조 하는 람다 식을 대리자를 가비지 수집에 사용할 수 없는 원본 환경에서 변수에 액세스할 수 있도록 유지 됩니다. 다음 예에서는 변수에서 `target` 에 로컬인 `makeTheGame`, 메서드를 람다 식 `playTheGame` 정의 됩니다. 반환 된 람다 식에 할당 하는 참고 `takeAGuess` 에 `Main`, 지역 변수에 대 한 액세스를 아직 `target`합니다.  
  
 [!code-vb[VbVbalrLambdas#12](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_5.vb)]  
  
 다음 예제에서는 다양 한 범위의 중첩 된 람다 식의 액세스 권한 보여 줍니다. 반환된 된 람다 식이 실행 되 면 `Main` 으로 `aDel`, 이러한 요소에 액세스 합니다.  
  
-   이전에 정의 된 클래스의 필드:`aField`  
  
-   이전에 정의 된 클래스의 속성:`aProp`  
  
-   메서드의 매개 변수 `functionWithNestedLambda`에서 정의 됩니다.`level1`  
  
-   지역 변수가 `functionWithNestedLambda`:`localVar`  
  
-   중첩 된 람다 식의 매개 변수:`level2`  
  
 [!code-vb[VbVbalrLambdas#9](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_6.vb)]  
  
## <a name="converting-to-a-delegate-type"></a>대리자 형식으로 변환  
 람다 식은 호환 되는 대리자 형식으로 암시적으로 변환할 수 있습니다. 호환성에 대 한 일반 요구 사항에 대 한 정보를 참조 하십시오. [완화 된 대리자 변환](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)합니다. 다음 코드 예제에서는 암시적으로 변환 하는 람다 식을 표시 하는 예를 들어 `Func(Of Integer, Boolean)` 또는 일치 하는 대리자 서명입니다.  
  
 [!code-vb[VbVbalrLambdas#16](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_7.vb)]  
  
 다음 코드 예제에서는 암시적으로 변환 하는 람다 식을 보여 줍니다 `Sub(Of Double, String, Double)` 또는 일치 하는 대리자 서명입니다.  
  
 [!code-vb[VbVbalrLambdas#23](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_8.vb)]  
  
 람다 식을 대리자에 할당 하거나 프로시저에 인수로 전달할 때 매개 변수 이름을 지정할 수 있지만 형식을 가져오도록 될 대리자에서 해당 데이터 형식은 생략 합니다.  
  
## <a name="examples"></a>예제  
  
-   다음 예제에서는 반환 하는 람다 식을 정의 `True` nullable 인수에 할당된 된 값 및 `False` 값이 `Nothing`합니다.  
  
     [!code-vb[VbVbalrLambdas#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_9.vb)]  
  
-   다음 예제에서는 배열에서 마지막 요소의 인덱스를 반환 하는 람다 식을 정의 합니다.  
  
     [!code-vb[VbVbalrLambdas#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_10.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [절차](./index.md)  
 [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [대리자](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [Sub 문](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Nullable 값 형식](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [방법: Visual Basic에서 프로시저에 다른 프로시저 전달](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)  
 [방법: 람다 식 만들기](./how-to-create-a-lambda-expression.md)  
 [완화된 대리자 변환](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
