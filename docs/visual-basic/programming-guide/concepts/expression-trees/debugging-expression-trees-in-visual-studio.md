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
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 84de749afad6abb748d0622561f8ee7cd399ed54
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a><span data-ttu-id="d04f7-102">Visual Studio (Visual Basic)에서 식 트리 디버깅</span><span class="sxs-lookup"><span data-stu-id="d04f7-102">Debugging Expression Trees in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="d04f7-103">응용 프로그램을 디버깅할 때 구조와 식 트리의 내용을 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d04f7-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="d04f7-104">간략 한 식 트리 구조를 얻으려면 사용할 수는 `DebugView` 디버그 모드 에서만 사용할 수 있는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d04f7-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which is available only in debug mode.</span></span> <span data-ttu-id="d04f7-105">디버깅 하는 방법에 대 한 자세한 내용은 참조 [Visual Studio에서 디버깅](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio)합니다.</span><span class="sxs-lookup"><span data-stu-id="d04f7-105">For more information about debugging, see [Debugging in Visual Studio](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio).</span></span>  
  
 <span data-ttu-id="d04f7-106">식 트리의 콘텐츠를 보다 잘 나타내는 하는 `DebugView` 속성은 Visual Studio 시각화 도우미를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d04f7-106">To better represent the content of expression trees, the `DebugView` property uses Visual Studio visualizers.</span></span> <span data-ttu-id="d04f7-107">자세한 내용은 참조 [사용자 지정 시각화 도우미 만들기](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data)합니다.</span><span class="sxs-lookup"><span data-stu-id="d04f7-107">For more information, see [Create Custom Visualizers](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data).</span></span>  
  
### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="d04f7-108">식 트리에 대 한 시각화 도우미를 열려면</span><span class="sxs-lookup"><span data-stu-id="d04f7-108">To open a visualizer for an expression tree</span></span>  
  
1.  <span data-ttu-id="d04f7-109">옆에 나타나는 돋보기 아이콘을 클릭 하는 `DebugView` 속성에서 식 트리 **DataTips**, **조사식** 창은 **자동** 창 또는 **지역** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="d04f7-109">Click the magnifying glass icon that appears next to the `DebugView` property of an expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="d04f7-110">시각화 도우미의 목록이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d04f7-110">A list of visualizers is displayed.</span></span>  
  
2.  <span data-ttu-id="d04f7-111">사용할 시각화 도우미를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d04f7-111">Click the visualizer you want to use.</span></span>  
  
 <span data-ttu-id="d04f7-112">다음 섹션에 설명 된 대로 각 식 형식은 시각화 도우미에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d04f7-112">Each expression type is displayed in the visualizer as described in the following sections.</span></span>  
  
## <a name="parameterexpressions"></a><span data-ttu-id="d04f7-113">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="d04f7-113">ParameterExpressions</span></span>  
 <span data-ttu-id="d04f7-114"><xref:System.Linq.Expressions.ParameterExpression>변수 이름 시작 부분에 "$" 기호로 표시 됩니다.</xref:System.Linq.Expressions.ParameterExpression></span><span class="sxs-lookup"><span data-stu-id="d04f7-114"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>  
  
 <span data-ttu-id="d04f7-115">자동으로 생성 된 이름이 같은 할당 됩니다 매개 변수는 이름이 없으면 `$var1` 또는 `$var2`합니다.</span><span class="sxs-lookup"><span data-stu-id="d04f7-115">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="d04f7-116">예제</span><span class="sxs-lookup"><span data-stu-id="d04f7-116">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim numParam As ParameterExpression =   
    Expression.Parameter(GetType(Integer), "num")  
    ```  
  
     <span data-ttu-id="d04f7-117">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="d04f7-117">`DebugView` property</span></span>  
  
     `$num`  
  
-   `Expression`  
  
    ```vb  
    Dim numParam As ParameterExpression =   
    Expression.Parameter(GetType(Integer))  
    ```  
  
     <span data-ttu-id="d04f7-118">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="d04f7-118">`DebugView` property</span></span>  
  
     `$var1`  
  
## <a name="constantexpressions"></a><span data-ttu-id="d04f7-119">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="d04f7-119">ConstantExpressions</span></span>  
 <span data-ttu-id="d04f7-120">에 대 한 <xref:System.Linq.Expressions.ConstantExpression>문자열, 정수 값을 나타내는 개체를 및 `null`, 상수 값이 표시 됩니다.</xref:System.Linq.Expressions.ConstantExpression></span><span class="sxs-lookup"><span data-stu-id="d04f7-120">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="d04f7-121">예제</span><span class="sxs-lookup"><span data-stu-id="d04f7-121">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim num as Integer= 10  
    Dim expr As ConstantExpression = Expression.Constant(num)  
    ```  
  
     <span data-ttu-id="d04f7-122">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="d04f7-122">`DebugView` property</span></span>  
  
     <span data-ttu-id="d04f7-123">10</span><span class="sxs-lookup"><span data-stu-id="d04f7-123">10</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim num As Double = 10  
    Dim expr As ConstantExpression = Expression.Constant(num)  
    ```  
  
     <span data-ttu-id="d04f7-124">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="d04f7-124">`DebugView` property</span></span>  
  
     <span data-ttu-id="d04f7-125">10 일</span><span class="sxs-lookup"><span data-stu-id="d04f7-125">10D</span></span>  
  
## <a name="blockexpression"></a><span data-ttu-id="d04f7-126">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="d04f7-126">BlockExpression</span></span>  
 <span data-ttu-id="d04f7-127">경우 유형의 <xref:System.Linq.Expressions.BlockExpression>블록의 마지막 식의 형식에서 다른 개체, 형식에 표시 됩니다는 `DebugInfo` 꺾쇠 괄호로 속성 (\< 및 >).</xref:System.Linq.Expressions.BlockExpression></span><span class="sxs-lookup"><span data-stu-id="d04f7-127">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="d04f7-128">그렇지 않으면 유형의 <xref:System.Linq.Expressions.BlockExpression>개체가 표시 되지 않습니다.</xref:System.Linq.Expressions.BlockExpression></span><span class="sxs-lookup"><span data-stu-id="d04f7-128">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="d04f7-129">예제</span><span class="sxs-lookup"><span data-stu-id="d04f7-129">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))  
    ```  
  
     <span data-ttu-id="d04f7-130">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="d04f7-130">`DebugView` property</span></span>  
  
     `.Block() {`  
  
     `"test"`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim block As BlockExpression =   
    Expression.Block(GetType(Object), Expression.Constant("test"))  
    ```  
  
     <span data-ttu-id="d04f7-131">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="d04f7-131">`DebugView` property</span></span>  
  
     `.Block<System.Object>() {`  
  
     `"test"`  
  
     `}`  
  
## <a name="lambdaexpression"></a><span data-ttu-id="d04f7-132">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="d04f7-132">LambdaExpression</span></span>  
 <span data-ttu-id="d04f7-133"><xref:System.Linq.Expressions.LambdaExpression>개체는 대리자 형식과 함께 표시 됩니다.</xref:System.Linq.Expressions.LambdaExpression></span><span class="sxs-lookup"><span data-stu-id="d04f7-133"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>  
  
 <span data-ttu-id="d04f7-134">자동으로 생성 된 이름이 같은 할당 됩니다 람다 식에는 이름이 없는 경우 `#Lambda1` 또는 `#Lambda2`합니다.</span><span class="sxs-lookup"><span data-stu-id="d04f7-134">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="d04f7-135">예제</span><span class="sxs-lookup"><span data-stu-id="d04f7-135">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim lambda As LambdaExpression =   
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1))  
    ```  
  
     <span data-ttu-id="d04f7-136">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="d04f7-136">`DebugView` property</span></span>  
  
     `.Lambda #Lambda1<System.Func'1[System.Int32]>() {`  
  
     `1`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim lambda As LambdaExpression =   
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1), "SampleLamda", Nothing)  
    ```  
  
     <span data-ttu-id="d04f7-137">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="d04f7-137">`DebugView` property</span></span>  
  
     `.Lambda SampleLambda<System.Func'1[System.Int32]>() {`  
  
     `1`  
  
     `}`  
  
## <a name="labelexpression"></a><span data-ttu-id="d04f7-138">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="d04f7-138">LabelExpression</span></span>  
 <span data-ttu-id="d04f7-139">에 대 한 기본값을 지정 하는 경우는 <xref:System.Linq.Expressions.LabelExpression>개체를 하기 전에이 값이 표시는 <xref:System.Linq.Expressions.LabelTarget>개체.</xref:System.Linq.Expressions.LabelTarget> </xref:System.Linq.Expressions.LabelExpression></span><span class="sxs-lookup"><span data-stu-id="d04f7-139">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>  
  
 <span data-ttu-id="d04f7-140">`.Label` 토큰 레이블의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d04f7-140">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="d04f7-141">`.LabelTarget` 토큰을 이동할 대상의 대상을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d04f7-141">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>  
  
 <span data-ttu-id="d04f7-142">자동으로 생성 된 이름을 같은 할당은 레이블 이름을 없는 경우 `#Label1` 또는 `#Label2`합니다.</span><span class="sxs-lookup"><span data-stu-id="d04f7-142">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="d04f7-143">예제</span><span class="sxs-lookup"><span data-stu-id="d04f7-143">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")  
    Dim label1 As BlockExpression = Expression.Block(  
    Expression.Goto(target, Expression.Constant(0)),  
    Expression.Label(target, Expression.Constant(-1)))  
    ```  
  
     <span data-ttu-id="d04f7-144">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="d04f7-144">`DebugView` property</span></span>  
  
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
  
     <span data-ttu-id="d04f7-145">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="d04f7-145">`DebugView` property</span></span>  
  
     `.Block() {`  
  
     `.Goto #Label1 { };`  
  
     `.Label`  
  
     `.LabelTarget #Label1:`  
  
     `}`  
  
## <a name="checked-operators"></a><span data-ttu-id="d04f7-146">확인 된 연산자</span><span class="sxs-lookup"><span data-stu-id="d04f7-146">Checked Operators</span></span>  
 <span data-ttu-id="d04f7-147">확인 된 연산자는 연산자 앞에 "#" 기호가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d04f7-147">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="d04f7-148">로 확인 된 더하기 연산자가 표시 하는 예를 들어 `#+`합니다.</span><span class="sxs-lookup"><span data-stu-id="d04f7-148">For example, the checked addition operator is displayed as `#+`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="d04f7-149">예제</span><span class="sxs-lookup"><span data-stu-id="d04f7-149">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim expr As Expression = Expression.AddChecked(  
    Expression.Constant(1), Expression.Constant(2))  
    ```  
  
     <span data-ttu-id="d04f7-150">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="d04f7-150">`DebugView` property</span></span>  
  
     `1 #+ 2`  
  
-   `Expression`  
  
    ```vb  
    Dim expr As Expression = Expression.ConvertChecked(  
    Expression.Constant(10.0), GetType(Integer))  
    ```  
  
     <span data-ttu-id="d04f7-151">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="d04f7-151">`DebugView` property</span></span>  
  
     `#(System.Int32)10D`  
  
## <a name="see-also"></a><span data-ttu-id="d04f7-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d04f7-152">See Also</span></span>  
 <span data-ttu-id="d04f7-153">[식 트리 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) </span><span class="sxs-lookup"><span data-stu-id="d04f7-153">[Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) </span></span>  
<span data-ttu-id="d04f7-154"> [Visual Studio의 디버깅](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio) </span><span class="sxs-lookup"><span data-stu-id="d04f7-154"> [Debugging in Visual Studio](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio) </span></span>  
<span data-ttu-id="d04f7-155"> [사용자 지정 시각화 도우미 만들기](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data)</span><span class="sxs-lookup"><span data-stu-id="d04f7-155"> [Create Custom Visualizers](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data)</span></span>
