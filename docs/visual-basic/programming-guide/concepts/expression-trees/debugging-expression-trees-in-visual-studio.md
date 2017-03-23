---
title: "Visual Studio (Visual Basic)에서 식 트리 디버깅 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
caps.latest.revision: 4
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: efbd8c19947c45b3ba15ce7b574000d56526ef45
ms.lasthandoff: 03/13/2017

---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a>Visual Studio (Visual Basic)에서 식 트리 디버깅
응용 프로그램을 디버깅할 때 구조와 식 트리의 내용을 분석할 수 있습니다. 간략 한 식 트리 구조를 얻으려면 사용할 수는 `DebugView` 디버그 모드 에서만 사용할 수 있는 속성입니다. 디버깅 하는 방법에 대 한 자세한 내용은 참조 [Visual Studio에서 디버깅](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio)합니다.  
  
 식 트리의 콘텐츠를 보다 잘 나타내는 하는 `DebugView` 속성은 Visual Studio 시각화 도우미를 사용 합니다. 자세한 내용은 참조 [사용자 지정 시각화 도우미 만들기](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data)합니다.  
  
### <a name="to-open-a-visualizer-for-an-expression-tree"></a>식 트리에 대 한 시각화 도우미를 열려면  
  
1.  옆에 나타나는 돋보기 아이콘을 클릭 하는 `DebugView` 속성에서 식 트리 **DataTips**, **조사식** 창은 **자동** 창 또는 **지역** 창입니다.  
  
     시각화 도우미의 목록이 나타납니다.  
  
2.  사용할 시각화 도우미를 클릭합니다.  
  
 다음 섹션에 설명 된 대로 각 식 형식은 시각화 도우미에 표시 됩니다.  
  
## <a name="parameterexpressions"></a>ParameterExpressions  
 <xref:System.Linq.Expressions.ParameterExpression>변수 이름 시작 부분에 "$" 기호로 표시 됩니다.</xref:System.Linq.Expressions.ParameterExpression>  
  
 자동으로 생성 된 이름이 같은 할당 됩니다 매개 변수는 이름이 없으면 `$var1` 또는 `$var2`합니다.  
  
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
 에 대 한 <xref:System.Linq.Expressions.ConstantExpression>문자열, 정수 값을 나타내는 개체를 및 `null`, 상수 값이 표시 됩니다.</xref:System.Linq.Expressions.ConstantExpression>  
  
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
  
     10 일  
  
## <a name="blockexpression"></a>BlockExpression  
 경우 유형의 <xref:System.Linq.Expressions.BlockExpression>블록의 마지막 식의 형식에서 다른 개체, 형식에 표시 됩니다는 `DebugInfo` 꺾쇠 괄호로 속성 (\< 및 >).</xref:System.Linq.Expressions.BlockExpression> 그렇지 않으면 유형의 <xref:System.Linq.Expressions.BlockExpression>개체가 표시 되지 않습니다.</xref:System.Linq.Expressions.BlockExpression>  
  
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
 <xref:System.Linq.Expressions.LambdaExpression>개체는 대리자 형식과 함께 표시 됩니다.</xref:System.Linq.Expressions.LambdaExpression>  
  
 자동으로 생성 된 이름이 같은 할당 됩니다 람다 식에는 이름이 없는 경우 `#Lambda1` 또는 `#Lambda2`합니다.  
  
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
 에 대 한 기본값을 지정 하는 경우는 <xref:System.Linq.Expressions.LabelExpression>개체를 하기 전에이 값이 표시는 <xref:System.Linq.Expressions.LabelTarget>개체.</xref:System.Linq.Expressions.LabelTarget> </xref:System.Linq.Expressions.LabelExpression>  
  
 `.Label` 토큰 레이블의 시작을 나타냅니다. `.LabelTarget` 토큰을 이동할 대상의 대상을 나타냅니다.  
  
 자동으로 생성 된 이름을 같은 할당은 레이블 이름을 없는 경우 `#Label1` 또는 `#Label2`합니다.  
  
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
  
## <a name="checked-operators"></a>확인 된 연산자  
 확인 된 연산자는 연산자 앞에 "#" 기호가 표시 됩니다. 로 확인 된 더하기 연산자가 표시 하는 예를 들어 `#+`합니다.  
  
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
 [식 트리 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)   
 [Visual Studio의 디버깅](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio)   
 [사용자 지정 시각화 도우미 만들기](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data)
