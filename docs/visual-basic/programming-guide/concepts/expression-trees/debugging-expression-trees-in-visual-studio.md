---
title: Visual Studio (Visual Basic)에서 식 트리 디버깅
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: 2addba2654067eaaf6c621c927e0992308879ae4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33644240"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a><span data-ttu-id="81796-102">Visual Studio (Visual Basic)에서 식 트리 디버깅</span><span class="sxs-lookup"><span data-stu-id="81796-102">Debugging Expression Trees in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="81796-103">응용 프로그램을 디버그할 때 식 트리의 구조 및 내용을 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81796-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="81796-104">식 트리 구조의 개요를 빠르게 확인하려면 디버그 모드에서만 제공되는 `DebugView` 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81796-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which is available only in debug mode.</span></span> <span data-ttu-id="81796-105">디버깅에 대한 자세한 내용은 [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio)(Visual Studio의 디버깅)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81796-105">For more information about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span></span>  
  
 <span data-ttu-id="81796-106">식 트리의 내용을 더 잘 표현하기 위해 `DebugView` 속성은 Visual Studio 시각화 도우미를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81796-106">To better represent the content of expression trees, the `DebugView` property uses Visual Studio visualizers.</span></span> <span data-ttu-id="81796-107">자세한 내용은 [Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data)(사용자 지정 시각화 도우미 만들기)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81796-107">For more information, see [Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data).</span></span>  
  
### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="81796-108">식 트리에 대한 시각화 도우미를 열려면</span><span class="sxs-lookup"><span data-stu-id="81796-108">To open a visualizer for an expression tree</span></span>  
  
1.  <span data-ttu-id="81796-109">**DataTips**, **조사식** 창, **자동** 창 또는 **지역** 창에서 식 트리의 `DebugView` 속성 옆에 표시되는 돋보기 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="81796-109">Click the magnifying glass icon that appears next to the `DebugView` property of an expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="81796-110">시각화 도우미의 목록이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="81796-110">A list of visualizers is displayed.</span></span>  
  
2.  <span data-ttu-id="81796-111">사용할 시각화 도우미를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="81796-111">Click the visualizer you want to use.</span></span>  
  
 <span data-ttu-id="81796-112">각 식 형식은 다음 섹션에 설명된 대로 시각화 도우미에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="81796-112">Each expression type is displayed in the visualizer as described in the following sections.</span></span>  
  
## <a name="parameterexpressions"></a><span data-ttu-id="81796-113">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="81796-113">ParameterExpressions</span></span>  
 <span data-ttu-id="81796-114"><xref:System.Linq.Expressions.ParameterExpression> 변수 이름의 시작 부분에 “$” 기호가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="81796-114"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>  
  
 <span data-ttu-id="81796-115">매개 변수에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `$var1` 또는 `$var2`).</span><span class="sxs-lookup"><span data-stu-id="81796-115">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="81796-116">예제</span><span class="sxs-lookup"><span data-stu-id="81796-116">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim numParam As ParameterExpression =   
    Expression.Parameter(GetType(Integer), "num")  
    ```  
  
     <span data-ttu-id="81796-117">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="81796-117">`DebugView` property</span></span>  
  
     `$num`  
  
-   `Expression`  
  
    ```vb  
    Dim numParam As ParameterExpression =   
    Expression.Parameter(GetType(Integer))  
    ```  
  
     <span data-ttu-id="81796-118">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="81796-118">`DebugView` property</span></span>  
  
     `$var1`  
  
## <a name="constantexpressions"></a><span data-ttu-id="81796-119">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="81796-119">ConstantExpressions</span></span>  
 <span data-ttu-id="81796-120">정수 값, 문자열 및 `null`을 나타내는 <xref:System.Linq.Expressions.ConstantExpression> 개체의 경우 상수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="81796-120">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="81796-121">예제</span><span class="sxs-lookup"><span data-stu-id="81796-121">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim num as Integer= 10  
    Dim expr As ConstantExpression = Expression.Constant(num)  
    ```  
  
     <span data-ttu-id="81796-122">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="81796-122">`DebugView` property</span></span>  
  
     <span data-ttu-id="81796-123">10</span><span class="sxs-lookup"><span data-stu-id="81796-123">10</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim num As Double = 10  
    Dim expr As ConstantExpression = Expression.Constant(num)  
    ```  
  
     <span data-ttu-id="81796-124">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="81796-124">`DebugView` property</span></span>  
  
     <span data-ttu-id="81796-125">10D</span><span class="sxs-lookup"><span data-stu-id="81796-125">10D</span></span>  
  
## <a name="blockexpression"></a><span data-ttu-id="81796-126">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="81796-126">BlockExpression</span></span>  
 <span data-ttu-id="81796-127"><xref:System.Linq.Expressions.BlockExpression> 개체의 형식이 블록에 있는 마지막 식의 형식과 다를 경우 형식은 꺾쇠 괄호(\< 및 >) 안의 `DebugInfo` 속성에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="81796-127">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="81796-128">같을 경우 <xref:System.Linq.Expressions.BlockExpression> 개체의 형식이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81796-128">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="81796-129">예제</span><span class="sxs-lookup"><span data-stu-id="81796-129">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))  
    ```  
  
     <span data-ttu-id="81796-130">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="81796-130">`DebugView` property</span></span>  
  
     `.Block() {`  
  
     `"test"`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim block As BlockExpression =   
    Expression.Block(GetType(Object), Expression.Constant("test"))  
    ```  
  
     <span data-ttu-id="81796-131">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="81796-131">`DebugView` property</span></span>  
  
     `.Block<System.Object>() {`  
  
     `"test"`  
  
     `}`  
  
## <a name="lambdaexpression"></a><span data-ttu-id="81796-132">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="81796-132">LambdaExpression</span></span>  
 <span data-ttu-id="81796-133"><xref:System.Linq.Expressions.LambdaExpression> 개체는 대리자 형식과 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="81796-133"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>  
  
 <span data-ttu-id="81796-134">람다 식에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `#Lambda1` 또는 `#Lambda2`).</span><span class="sxs-lookup"><span data-stu-id="81796-134">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="81796-135">예제</span><span class="sxs-lookup"><span data-stu-id="81796-135">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim lambda As LambdaExpression =   
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1))  
    ```  
  
     <span data-ttu-id="81796-136">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="81796-136">`DebugView` property</span></span>  
  
     `.Lambda #Lambda1<System.Func'1[System.Int32]>() {`  
  
     `1`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim lambda As LambdaExpression =   
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1), "SampleLamda", Nothing)  
    ```  
  
     <span data-ttu-id="81796-137">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="81796-137">`DebugView` property</span></span>  
  
     `.Lambda SampleLambda<System.Func'1[System.Int32]>() {`  
  
     `1`  
  
     `}`  
  
## <a name="labelexpression"></a><span data-ttu-id="81796-138">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="81796-138">LabelExpression</span></span>  
 <span data-ttu-id="81796-139"><xref:System.Linq.Expressions.LabelExpression> 개체의 기본값을 지정하면 이 값은 <xref:System.Linq.Expressions.LabelTarget> 개체 앞에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="81796-139">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>  
  
 <span data-ttu-id="81796-140">`.Label` 토큰은 레이블의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="81796-140">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="81796-141">`.LabelTarget` 토큰은 이동할 대상의 목적지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="81796-141">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>  
  
 <span data-ttu-id="81796-142">레이블에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `#Label1` 또는 `#Label2`).</span><span class="sxs-lookup"><span data-stu-id="81796-142">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="81796-143">예제</span><span class="sxs-lookup"><span data-stu-id="81796-143">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")  
    Dim label1 As BlockExpression = Expression.Block(  
    Expression.Goto(target, Expression.Constant(0)),  
    Expression.Label(target, Expression.Constant(-1)))  
    ```  
  
     <span data-ttu-id="81796-144">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="81796-144">`DebugView` property</span></span>  
  
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
  
     <span data-ttu-id="81796-145">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="81796-145">`DebugView` property</span></span>  
  
     `.Block() {`  
  
     `.Goto #Label1 { };`  
  
     `.Label`  
  
     `.LabelTarget #Label1:`  
  
     `}`  
  
## <a name="checked-operators"></a><span data-ttu-id="81796-146">확인된 연산자</span><span class="sxs-lookup"><span data-stu-id="81796-146">Checked Operators</span></span>  
 <span data-ttu-id="81796-147">확인된 연산자는 연산자 앞에 "#" 기호가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="81796-147">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="81796-148">예를 들어 확인된 더하기 연산자는 `#+`로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="81796-148">For example, the checked addition operator is displayed as `#+`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="81796-149">예제</span><span class="sxs-lookup"><span data-stu-id="81796-149">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim expr As Expression = Expression.AddChecked(  
    Expression.Constant(1), Expression.Constant(2))  
    ```  
  
     <span data-ttu-id="81796-150">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="81796-150">`DebugView` property</span></span>  
  
     `1 #+ 2`  
  
-   `Expression`  
  
    ```vb  
    Dim expr As Expression = Expression.ConvertChecked(  
    Expression.Constant(10.0), GetType(Integer))  
    ```  
  
     <span data-ttu-id="81796-151">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="81796-151">`DebugView` property</span></span>  
  
     `#(System.Int32)10D`  
  
## <a name="see-also"></a><span data-ttu-id="81796-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="81796-152">See Also</span></span>  
 [<span data-ttu-id="81796-153">식 트리(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81796-153">Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)  
 [<span data-ttu-id="81796-154">Visual Studio의 디버깅</span><span class="sxs-lookup"><span data-stu-id="81796-154">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)  
 <span data-ttu-id="81796-155">[Create Custom Visualizers of Data](/visualstudio/debugger/create-custom-visualizers-of-data)(데이터의 사용자 지정 시각화 도우미 만들기)</span><span class="sxs-lookup"><span data-stu-id="81796-155">[Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data)</span></span>
