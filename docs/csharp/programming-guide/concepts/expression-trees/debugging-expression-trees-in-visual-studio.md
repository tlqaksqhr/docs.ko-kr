---
title: Visual Studio에서 식 트리 디버그(C#)
ms.date: 07/20/2015
ms.assetid: 1369fa25-0fbd-4b92-98d0-8df79c49c27a
ms.openlocfilehash: 0b3017f2800a2eb7332028b9cfe6ed9877222087
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="debugging-expression-trees-in-visual-studio-c"></a>Visual Studio에서 식 트리 디버그(C#)
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
  
|식|`DebugView` 속성|  
|----------------|--------------------------|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int), "num");`|`$num`|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int));`|`$var1`|  
  
## <a name="constantexpressions"></a>ConstantExpressions  
 정수 값, 문자열 및 `null`을 나타내는 <xref:System.Linq.Expressions.ConstantExpression> 개체의 경우 상수 값이 표시됩니다.  
  
 표준 접미사인 C# 리터럴이 있는 숫자 형식의 경우 접미사가 값에 추가됩니다. 다음 표에서는 다양한 숫자 형식과 연결된 접미사를 보여 줍니다.  
  
|형식|접미사|  
|----------|------------|  
|<xref:System.UInt32>|U|  
|<xref:System.Int64>|L|  
|<xref:System.UInt64>|UL|  
|<xref:System.Double>|D|  
|<xref:System.Single>|F|  
|<xref:System.Decimal>|M|  
  
### <a name="examples"></a>예제  
  
|식|`DebugView` 속성|  
|----------------|--------------------------|  
|`int num = 10; ConstantExpression expr = Expression.Constant(num);`|10|  
|`double num = 10; ConstantExpression expr = Expression.Constant(num);`|10D|  
  
## <a name="blockexpression"></a>BlockExpression  
 <xref:System.Linq.Expressions.BlockExpression> 개체의 형식이 블록에 있는 마지막 식의 형식과 다를 경우 형식은 꺾쇠 괄호(\< 및 >) 안의 `DebugInfo` 속성에 표시됩니다. 같을 경우 <xref:System.Linq.Expressions.BlockExpression> 개체의 형식이 표시되지 않습니다.  
  
### <a name="examples"></a>예제  
  
|식|`DebugView` 속성|  
|----------------|--------------------------|  
|`BlockExpression block = Expression.Block(Expression.Constant("test"));`|`.Block() {`<br /><br /> `"test"`<br /><br /> `}`|  
|`BlockExpression block =  Expression.Block(typeof(Object), Expression.Constant("test"));`|`.Block<System.Object>() {`<br /><br /> `"test"`<br /><br /> `}`|  
  
## <a name="lambdaexpression"></a>LambdaExpression  
 <xref:System.Linq.Expressions.LambdaExpression> 개체는 대리자 형식과 함께 표시됩니다.  
  
 람다 식에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `#Lambda1` 또는 `#Lambda2`).  
  
### <a name="examples"></a>예제  
  
|식|`DebugView` 속성|  
|----------------|--------------------------|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1));`|`.Lambda #Lambda1<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1), "SampleLambda", null);`|`.Lambda SampleLambda<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
  
## <a name="labelexpression"></a>LabelExpression  
 <xref:System.Linq.Expressions.LabelExpression> 개체의 기본값을 지정하면 이 값은 <xref:System.Linq.Expressions.LabelTarget> 개체 앞에 표시됩니다.  
  
 `.Label` 토큰은 레이블의 시작을 나타냅니다. `.LabelTarget` 토큰은 이동할 대상의 목적지를 나타냅니다.  
  
 레이블에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `#Label1` 또는 `#Label2`).  
  
### <a name="examples"></a>예제  
  
|식|`DebugView` 속성|  
|----------------|--------------------------|  
|`LabelTarget target = Expression.Label(typeof(int), "SampleLabel"); BlockExpression block = Expression.Block( Expression.Goto(target, Expression.Constant(0)), Expression.Label(target, Expression.Constant(-1)));`|`.Block() {`<br /><br /> `.Goto SampleLabel { 0 };`<br /><br /> `.Label`<br /><br /> `-1`<br /><br /> `.LabelTarget SampleLabel:`<br /><br /> `}`|  
|`LabelTarget target = Expression.Label(); BlockExpression block = Expression.Block( Expression.Goto(target5), Expression.Label(target5));`|`.Block() {`<br /><br /> `.Goto #Label1 { };`<br /><br /> `.Label`<br /><br /> `.LabelTarget #Label1:`<br /><br /> `}`|  
  
## <a name="checked-operators"></a>확인된 연산자  
 확인된 연산자는 연산자 앞에 "#" 기호가 표시됩니다. 예를 들어 확인된 더하기 연산자는 `#+`로 표시됩니다.  
  
### <a name="examples"></a>예제  
  
|식|`DebugView` 속성|  
|----------------|--------------------------|  
|`Expression expr = Expression.AddChecked( Expression.Constant(1), Expression.Constant(2));`|`1 #+ 2`|  
|`Expression expr = Expression.ConvertChecked( Expression.Constant(10.0), typeof(int));`|`#(System.Int32)10D`|  
  
## <a name="see-also"></a>참고 항목  
 [식 트리(C#)](../../../../csharp/programming-guide/concepts/expression-trees/index.md)  
 [Visual Studio의 디버깅](/visualstudio/debugger/debugging-in-visual-studio)  
 [Create Custom Visualizers of Data](/visualstudio/debugger/create-custom-visualizers-of-data)(데이터의 사용자 지정 시각화 도우미 만들기)
