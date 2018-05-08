---
title: Visual Studio (Visual Basic)에서 식 트리 디버깅
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: 2addba2654067eaaf6c621c927e0992308879ae4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a>Visual Studio (Visual Basic)에서 식 트리 디버깅
응용 프로그램을 디버그할 때 식 트리의 구조 및 내용을 분석할 수 있습니다. 식 트리 구조의 개요를 빠르게 확인하려면 디버그 모드에서만 제공되는 `DebugView` 속성을 사용합니다. 디버깅에 대한 자세한 내용은 [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio)(Visual Studio의 디버깅)를 참조하세요.  
  
 식 트리의 내용을 더 잘 표현하기 위해 `DebugView` 속성은 Visual Studio 시각화 도우미를 사용합니다. 자세한 내용은 [Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data)(사용자 지정 시각화 도우미 만들기)를 참조하세요.  
  
### <a name="to-open-a-visualizer-for-an-expression-tree"></a>식 트리에 대한 시각화 도우미를 열려면  
  
1.  **DataTips**, **조사식** 창, **자동** 창 또는 **지역** 창에서 식 트리의 `DebugView` 속성 옆에 표시되는 돋보기 아이콘을 클릭합니다.  
  
     시각화 도우미의 목록이 나타납니다.  
  
2.  사용할 시각화 도우미를 클릭합니다.  
  
 각 식 형식은 다음 섹션에 설명된 대로 시각화 도우미에 표시됩니다.  
  
## <a name="parameterexpressions"></a>ParameterExpressions  
 <xref:System.Linq.Expressions.ParameterExpression> 변수 이름의 시작 부분에 “$” 기호가 표시됩니다.  
  
 매개 변수에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `$var1` 또는 `$var2`).  
  
### <a name="examples"></a>예제  
  
-   `Expression`  
  
    ```vb  
    Dim numParam As ParameterExpression =   
    Expression.Parameter(GetType(Integer), "num")  
    ```  
  
     `DebugView` 속성  
  
     `$num`  
  
-   `Expression`  
  
    ```vb  
    Dim numParam As ParameterExpression =   
    Expression.Parameter(GetType(Integer))  
    ```  
  
     `DebugView` 속성  
  
     `$var1`  
  
## <a name="constantexpressions"></a>ConstantExpressions  
 정수 값, 문자열 및 `null`을 나타내는 <xref:System.Linq.Expressions.ConstantExpression> 개체의 경우 상수 값이 표시됩니다.  
  
### <a name="examples"></a>예제  
  
-   `Expression`  
  
    ```vb  
    Dim num as Integer= 10  
    Dim expr As ConstantExpression = Expression.Constant(num)  
    ```  
  
     `DebugView` 속성  
  
     10  
  
-   `Expression`  
  
    ```vb  
    Dim num As Double = 10  
    Dim expr As ConstantExpression = Expression.Constant(num)  
    ```  
  
     `DebugView` 속성  
  
     10D  
  
## <a name="blockexpression"></a>BlockExpression  
 <xref:System.Linq.Expressions.BlockExpression> 개체의 형식이 블록에 있는 마지막 식의 형식과 다를 경우 형식은 꺾쇠 괄호(\< 및 >) 안의 `DebugInfo` 속성에 표시됩니다. 같을 경우 <xref:System.Linq.Expressions.BlockExpression> 개체의 형식이 표시되지 않습니다.  
  
### <a name="examples"></a>예제  
  
-   `Expression`  
  
    ```vb  
    Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))  
    ```  
  
     `DebugView` 속성  
  
     `.Block() {`  
  
     `"test"`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim block As BlockExpression =   
    Expression.Block(GetType(Object), Expression.Constant("test"))  
    ```  
  
     `DebugView` 속성  
  
     `.Block<System.Object>() {`  
  
     `"test"`  
  
     `}`  
  
## <a name="lambdaexpression"></a>LambdaExpression  
 <xref:System.Linq.Expressions.LambdaExpression> 개체는 대리자 형식과 함께 표시됩니다.  
  
 람다 식에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `#Lambda1` 또는 `#Lambda2`).  
  
### <a name="examples"></a>예제  
  
-   `Expression`  
  
    ```vb  
    Dim lambda As LambdaExpression =   
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1))  
    ```  
  
     `DebugView` 속성  
  
     `.Lambda #Lambda1<System.Func'1[System.Int32]>() {`  
  
     `1`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim lambda As LambdaExpression =   
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1), "SampleLamda", Nothing)  
    ```  
  
     `DebugView` 속성  
  
     `.Lambda SampleLambda<System.Func'1[System.Int32]>() {`  
  
     `1`  
  
     `}`  
  
## <a name="labelexpression"></a>LabelExpression  
 <xref:System.Linq.Expressions.LabelExpression> 개체의 기본값을 지정하면 이 값은 <xref:System.Linq.Expressions.LabelTarget> 개체 앞에 표시됩니다.  
  
 `.Label` 토큰은 레이블의 시작을 나타냅니다. `.LabelTarget` 토큰은 이동할 대상의 목적지를 나타냅니다.  
  
 레이블에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `#Label1` 또는 `#Label2`).  
  
### <a name="examples"></a>예제  
  
-   `Expression`  
  
    ```vb  
    Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")  
    Dim label1 As BlockExpression = Expression.Block(  
    Expression.Goto(target, Expression.Constant(0)),  
    Expression.Label(target, Expression.Constant(-1)))  
    ```  
  
     `DebugView` 속성  
  
     `.Block() {`  
  
     `.Goto SampleLabel { 0 };`  
  
     `.Label`  
  
     `-1`  
  
     `.LabelTarget SampleLabel:`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim target As LabelTarget = Expression.Label()  
    Dim block As BlockExpression = Expression.Block(  
    Expression.Goto(target), Expression.Label(target))  
    ```  
  
     `DebugView` 속성  
  
     `.Block() {`  
  
     `.Goto #Label1 { };`  
  
     `.Label`  
  
     `.LabelTarget #Label1:`  
  
     `}`  
  
## <a name="checked-operators"></a>확인된 연산자  
 확인된 연산자는 연산자 앞에 "#" 기호가 표시됩니다. 예를 들어 확인된 더하기 연산자는 `#+`로 표시됩니다.  
  
### <a name="examples"></a>예제  
  
-   `Expression`  
  
    ```vb  
    Dim expr As Expression = Expression.AddChecked(  
    Expression.Constant(1), Expression.Constant(2))  
    ```  
  
     `DebugView` 속성  
  
     `1 #+ 2`  
  
-   `Expression`  
  
    ```vb  
    Dim expr As Expression = Expression.ConvertChecked(  
    Expression.Constant(10.0), GetType(Integer))  
    ```  
  
     `DebugView` 속성  
  
     `#(System.Int32)10D`  
  
## <a name="see-also"></a>참고 항목  
 [식 트리(Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)  
 [Visual Studio의 디버깅](/visualstudio/debugger/debugging-in-visual-studio)  
 [Create Custom Visualizers of Data](/visualstudio/debugger/create-custom-visualizers-of-data)(데이터의 사용자 지정 시각화 도우미 만들기)
