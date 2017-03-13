---
title: "Lambda Expressions (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.LambdaFunction"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "functions [Visual Basic], lambda expressions"
  - "lambda expressions [Visual Basic]"
  - "expressions [Visual Basic], lambda"
  - "inline functions [Visual Basic]"
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
caps.latest.revision: 52
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 52
---
# Lambda Expressions (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

*람다 식*은 대리자가 유효한 모든 곳에서 사용할 수 있는, 이름이 없는 함수 또는 서브루틴입니다.  람다 식은 함수 또는 서브루틴일 수 있으며, 한 줄이나 여러 줄로 구성될 수 있습니다.  현재 범위의 값을 람다 식에 전달할 수 있습니다.  
  
> [!NOTE]
>  `RemoveHandler` 문은 예외입니다.  `RemoveHandler`의 대리자 매개 변수에는 람다 식을 전달할 수 없습니다.  
  
 표준 함수 또는 서브루틴을 만드는 경우와 마찬가지로, `Function` 또는 `Sub` 키워드를 사용하여 람다 식을 만듭니다.  그러나 람다 식은 문에 포함됩니다.  
  
 다음 예제에서는 인수를 점증적으로 늘리고 값을 반환하는 람다 식입니다.  다음 예제에서는 한 줄과 여러 줄로 구성된 함수에 대한 람다 식 구문을 보여 줍니다.  
  
 [!code-vb[VbVbalrLambdas#14](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_1.vb)]  
  
 다음 예제는 콘솔에 값을 쓰는 람다 식입니다.  다음 예제에서는 한 줄과 여러 줄로 구성된 서브루틴에 대한 람다 식 구문을 보여 줍니다.  
  
 [!code-vb[VbVbalrLambdas#15](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_2.vb)]  
  
 앞의 예제에서는 변수 이름에 람다 식이 할당되었습니다.  변수를 참조할 때마다 람다 식이 호출됩니다.  다음 예제와 같이 람다 식을 동시에 선언하고 호출할 수도 있습니다.  
  
 [!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_3.vb)]  
  
 람다 식은 이 항목의 뒷부분에 있는 [컨텍스트](#context) 단원의 예제와 같이 함수 호출의 값으로 반환될 수도 있고, 다음 예제와 같이 대리자 형식을 사용하는 매개 변수에 인수로 전달될 수도 있습니다.  
  
 [!code-vb[VbVbalrLambdas#8](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_4.vb)]  
  
## 람다 식 구문  
 람다 식의 구문은 표준 함수 또는 서브루틴의 구문과 유사합니다.  차이점은 다음과 같습니다.  
  
-   람다 식에는 이름이 없습니다.  
  
-   람다 식에는 `Overloads` 또는 `Overrides`와 같은 한정자가 있을 수 없습니다.  
  
-   한 줄로 된 람다 함수는 `As` 절을 사용하여 반환 형식을 지정하지 않습니다.  대신 람다 식의 본문이 평가되는 값에서 형식이 유추됩니다.  예를 들어 람다 식의 본문이 `cust.City = "London"`이면 반환 형식은 `Boolean`입니다.  
  
-   여러 줄로 된 람다 함수에서는 `As` 절을 사용하여 반환 형식을 지정하거나, 반환 형식이 유추되도록 `As` 절을 생략할 수 있습니다.  여러 줄로 된 람다 함수에 대해 `As` 절을 생략하면 반환 형식은 여러 줄로 된 람다 함수에 있는 모든 `Return` 문의 기준 형식으로 유추됩니다.  *기준 형식* 모든 다른 형식으로 넓힐 수 있습니다 있는 고유한 형식입니다.  이 고유 형식을 확인할 수 없는 경우 기준 형식은 배열의 다른 모든 형식이 축소 변환될 수 있는 고유 형식입니다.  이러한 두 고유 형식을 모두 확인할 수 없는 경우 기준 형식은 `Object`입니다.  이 경우 `Option Strict`가 `On`으로 설정되어 있으면 컴파일러 오류가 발생합니다.  
  
     예를 들어, 식에 제공 하는 경우는 `Return` 문 형식의 값이 들어 `Integer`, `Long`, 및 `Double`, 결과 배열 형식인 `Double`.  `Integer` 및 `Long`은 모두 `Double`로 확대 변환되며, `Double`로만 확대 변환됩니다.  따라서 `Double`이 기준 형식이 됩니다.  자세한 내용은 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)을 참조하십시오.  
  
-   한 줄로 된 함수의 본문은 문이 아니라 값을 반환하는 식이어야 합니다.  한 줄로 된 함수에는 `Return` 문이 없습니다.  한 줄로 된 함수가 반환하는 값은 함수 본문에 있는 식의 값입니다.  
  
-   한 줄로 된 서브루틴의 본문은 한 줄로 된 문이어야 합니다.  
  
-   한 줄로 된 함수와 서브루틴에는 `End Function` 또는 `End Sub` 문이 포함되지 않습니다.  
  
-   `As` 키워드를 사용하여 람다 식 매개 변수의 데이터 형식을 지정할 수도 있고, 매개 변수의 데이터 형식이 유추될 수도 있습니다.  모든 매개 변수에 지정된 데이터 형식이 있거나 모든 매개 변수가 유추되어야 합니다.  
  
-   `Optional` 및 `Paramarray` 매개 변수는 허용되지 않습니다.  
  
-   제네릭 매개 변수가 허용되지 않습니다.  
  
## 비동기 람다  
 람다 식 및 비동기 처리를 사용 하 여 통합 문을 쉽게 만들 수 있는 [Async](../../../../visual-basic/language-reference/modifiers/async.md) 및 [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) 키워드.  예를 들어, Windows Forms 예제는 이벤트 처리기를 호출 하는 비동기 메서드를 기다려를 포함 `ExampleMethodAsync`.  
  
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
  
 에 비동기 람다를 사용 하 여 동일한 이벤트 처리기를 추가할 수 있습니다는 [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).  이 처리기를 추가 하려면 추가 `Async` 전에 다음 예제와 같이 람다 매개 변수 목록에서 한정자입니다.  
  
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
  
 만들어 비동기 메서드를 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오. [Async 및 Await를 사용한 비동기 프로그래밍](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md).  
  
##  <a name="context"></a> 컨텍스트  
 람다 식과 해당 람다 식을 정의한 범위는 컨텍스트를 공유합니다.  람다 식은 포함하는 범위에서 작성된 모든 코드와 동일한 액세스 권한을 갖습니다.  여기에는 멤버 변수, 함수 및 sub, `Me`, 그리고 포함하는 범위에 있는 매개 변수 및 지역 변수에 대한 액세스가 포함됩니다.  
  
 포함하는 범위에 있는 지역 변수 및 매개 변수에 대한 액세스는 해당 범위의 수명 이후에도 유지될 수 있습니다.  람다 식에서 유추하는 대리자를 가비지 수집에 사용할 수 없는 한 원래 환경의 변수에 계속 액세스할 수 있습니다.  다음 예제에서 변수 `target`은 람다 식 `playTheGame`을 정의하는 메서드 `makeTheGame`의 지역 변수입니다.  `Main`에서 `takeAGuess`에 할당되는 반환된 람다 식은 지역 변수 `target`에 여전히 액세스할 수 있습니다.  
  
 [!code-vb[VbVbalrLambdas#12](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_5.vb)]  
  
 다음 예제에서는 중첩된 람다 식의 광범위한 액세스 권한을 보여 줍니다.  반환된 람다 식이 `Main`에서 `aDel`로 실행될 때는 다음 요소에 액세스합니다.  
  
-   반환된 람다 식을 정의한 클래스의 필드: `aField`  
  
-   반환된 람다 식을 정의한 클래스의 속성: `aProp`  
  
-   반환된 람다 식을 정의한 `functionWithNestedLambda` 메서드의 매개 변수: `level1`  
  
-   `functionWithNestedLambda`의 지역 변수: `localVar`  
  
-   반환된 람다 식이 중첩된 람다 식의 매개 변수: `level2`  
  
 [!code-vb[VbVbalrLambdas#9](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_6.vb)]  
  
## 대리자 형식으로 변환  
 람다 식은 호환되는 대리자 형식으로 암시적으로 변환될 수 있습니다.  호환성을 위한 일반적인 요구 사항에 대한 자세한 내용은 [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)을 참조하십시오.  예를 들어, 다음 코드 예제에서는 암시적으로 `Func(Of Integer, Boolean)` 또는 일치하는 대리자 시그니처로 변환되는 람다 식을 보여 줍니다.  
  
 [!code-vb[VbVbalrLambdas#16](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_7.vb)]  
  
 다음 코드 예제에서는 암시적으로 `Sub(Of Double, String, Double)` 또는 일치하는 대리자 시그니처로 변환되는 람다 식을 보여 줍니다.  
  
 [!code-vb[VbVbalrLambdas#23](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_8.vb)]  
  
 람다 식을 대리자에 할당하거나 프로시저에 인수로 전달할 때 매개 변수 이름만 지정하고 해당 데이터 형식은 생략하여 대리자에서 형식을 가져오도록 할 수 있습니다.  
  
## 예제  
  
-   다음 예제에서는 nullable 인수에 할당된 값이 있으면 `True`를 반환하고 해당 값이 `Nothing`이면 `False`를 반환하는 람다 식을 정의합니다.  
  
     [!code-vb[VbVbalrLambdas#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_9.vb)]  
  
-   다음 예제에서는 배열에 있는 마지막 요소의 인덱스를 반환하는 람다 식을 정의합니다.  
  
     [!code-vb[VbVbalrLambdas#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_10.vb)]  
  
## 참고 항목  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Delegates](../../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Nullable Value Types](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)   
 [How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)   
 [How to: Create a Lambda Expression](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-lambda-expression.md)   
 [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)