---
title: "Visual Studio에서 식 트리 디버그(C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 1369fa25-0fbd-4b92-98d0-8df79c49c27a
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0cf40b38ca9a6f743aca2894506e1d0ea80c9d57
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="debugging-expression-trees-in-visual-studio-c"></a><span data-ttu-id="d9169-102">Visual Studio에서 식 트리 디버그(C#)</span><span class="sxs-lookup"><span data-stu-id="d9169-102">Debugging Expression Trees in Visual Studio (C#)</span></span>
<span data-ttu-id="d9169-103">응용 프로그램을 디버그할 때 식 트리의 구조 및 내용을 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9169-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="d9169-104">식 트리 구조의 개요를 빠르게 확인하려면 디버그 모드에서만 제공되는 `DebugView` 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d9169-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which is available only in debug mode.</span></span> <span data-ttu-id="d9169-105">디버깅에 대한 자세한 내용은 [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio)(Visual Studio의 디버깅)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9169-105">For more information about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span></span>  
  
 <span data-ttu-id="d9169-106">식 트리의 내용을 더 잘 표현하기 위해 `DebugView` 속성은 Visual Studio 시각화 도우미를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d9169-106">To better represent the content of expression trees, the `DebugView` property uses Visual Studio visualizers.</span></span> <span data-ttu-id="d9169-107">자세한 내용은 [Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data)(사용자 지정 시각화 도우미 만들기)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9169-107">For more information, see [Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data).</span></span>  
  
### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="d9169-108">식 트리에 대한 시각화 도우미를 열려면</span><span class="sxs-lookup"><span data-stu-id="d9169-108">To open a visualizer for an expression tree</span></span>  
  
1.  <span data-ttu-id="d9169-109">**DataTips**, **조사식** 창, **자동** 창 또는 **지역** 창에서 식 트리의 `DebugView` 속성 옆에 표시되는 돋보기 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9169-109">Click the magnifying glass icon that appears next to the `DebugView` property of an expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="d9169-110">시각화 도우미의 목록이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d9169-110">A list of visualizers is displayed.</span></span>  
  
2.  <span data-ttu-id="d9169-111">사용할 시각화 도우미를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9169-111">Click the visualizer you want to use.</span></span>  
  
 <span data-ttu-id="d9169-112">각 식 형식은 다음 섹션에 설명된 대로 시각화 도우미에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9169-112">Each expression type is displayed in the visualizer as described in the following sections.</span></span>  
  
## <a name="parameterexpressions"></a><span data-ttu-id="d9169-113">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="d9169-113">ParameterExpressions</span></span>  
 <span data-ttu-id="d9169-114"><xref:System.Linq.Expressions.ParameterExpression> 변수 이름의 시작 부분에 “$” 기호가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9169-114"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>  
  
 <span data-ttu-id="d9169-115">매개 변수에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `$var1` 또는 `$var2`).</span><span class="sxs-lookup"><span data-stu-id="d9169-115">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="d9169-116">예제</span><span class="sxs-lookup"><span data-stu-id="d9169-116">Examples</span></span>  
  
|<span data-ttu-id="d9169-117">식</span><span class="sxs-lookup"><span data-stu-id="d9169-117">Expression</span></span>|<span data-ttu-id="d9169-118">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="d9169-118">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int), "num");`|`$num`|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int));`|`$var1`|  
  
## <a name="constantexpressions"></a><span data-ttu-id="d9169-119">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="d9169-119">ConstantExpressions</span></span>  
 <span data-ttu-id="d9169-120">정수 값, 문자열 및 `null`을 나타내는 <xref:System.Linq.Expressions.ConstantExpression> 개체의 경우 상수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9169-120">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>  
  
 <span data-ttu-id="d9169-121">표준 접미사인 C# 리터럴이 있는 숫자 형식의 경우 접미사가 값에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9169-121">For numeric types that have standard suffixes as C# literals, the suffix is added to the value.</span></span> <span data-ttu-id="d9169-122">다음 표에서는 다양한 숫자 형식과 연결된 접미사를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d9169-122">The following table shows the suffixes associated with various numeric types.</span></span>  
  
|<span data-ttu-id="d9169-123">형식</span><span class="sxs-lookup"><span data-stu-id="d9169-123">Type</span></span>|<span data-ttu-id="d9169-124">접미사</span><span class="sxs-lookup"><span data-stu-id="d9169-124">Suffix</span></span>|  
|----------|------------|  
|<xref:System.UInt32>|<span data-ttu-id="d9169-125">U</span><span class="sxs-lookup"><span data-stu-id="d9169-125">U</span></span>|  
|<xref:System.Int64>|<span data-ttu-id="d9169-126">L</span><span class="sxs-lookup"><span data-stu-id="d9169-126">L</span></span>|  
|<xref:System.UInt64>|<span data-ttu-id="d9169-127">UL</span><span class="sxs-lookup"><span data-stu-id="d9169-127">UL</span></span>|  
|<xref:System.Double>|<span data-ttu-id="d9169-128">D</span><span class="sxs-lookup"><span data-stu-id="d9169-128">D</span></span>|  
|<xref:System.Single>|<span data-ttu-id="d9169-129">F</span><span class="sxs-lookup"><span data-stu-id="d9169-129">F</span></span>|  
|<xref:System.Decimal>|<span data-ttu-id="d9169-130">M</span><span class="sxs-lookup"><span data-stu-id="d9169-130">M</span></span>|  
  
### <a name="examples"></a><span data-ttu-id="d9169-131">예제</span><span class="sxs-lookup"><span data-stu-id="d9169-131">Examples</span></span>  
  
|<span data-ttu-id="d9169-132">식</span><span class="sxs-lookup"><span data-stu-id="d9169-132">Expression</span></span>|<span data-ttu-id="d9169-133">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="d9169-133">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`int num = 10; ConstantExpression expr = Expression.Constant(num);`|<span data-ttu-id="d9169-134">10</span><span class="sxs-lookup"><span data-stu-id="d9169-134">10</span></span>|  
|`double num = 10; ConstantExpression expr = Expression.Constant(num);`|<span data-ttu-id="d9169-135">10D</span><span class="sxs-lookup"><span data-stu-id="d9169-135">10D</span></span>|  
  
## <a name="blockexpression"></a><span data-ttu-id="d9169-136">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="d9169-136">BlockExpression</span></span>  
 <span data-ttu-id="d9169-137"><xref:System.Linq.Expressions.BlockExpression> 개체의 형식이 블록에 있는 마지막 식의 형식과 다를 경우 형식은 꺾쇠 괄호(\< 및 >) 안의 `DebugInfo` 속성에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9169-137">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="d9169-138">같을 경우 <xref:System.Linq.Expressions.BlockExpression> 개체의 형식이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9169-138">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="d9169-139">예제</span><span class="sxs-lookup"><span data-stu-id="d9169-139">Examples</span></span>  
  
|<span data-ttu-id="d9169-140">식</span><span class="sxs-lookup"><span data-stu-id="d9169-140">Expression</span></span>|<span data-ttu-id="d9169-141">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="d9169-141">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`BlockExpression block = Expression.Block(Expression.Constant("test"));`|`.Block() {`<br /><br /> `"test"`<br /><br /> `}`|  
|`BlockExpression block =  Expression.Block(typeof(Object), Expression.Constant("test"));`|`.Block<System.Object>() {`<br /><br /> `"test"`<br /><br /> `}`|  
  
## <a name="lambdaexpression"></a><span data-ttu-id="d9169-142">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="d9169-142">LambdaExpression</span></span>  
 <span data-ttu-id="d9169-143"><xref:System.Linq.Expressions.LambdaExpression> 개체는 대리자 형식과 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9169-143"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>  
  
 <span data-ttu-id="d9169-144">람다 식에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `#Lambda1` 또는 `#Lambda2`).</span><span class="sxs-lookup"><span data-stu-id="d9169-144">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="d9169-145">예제</span><span class="sxs-lookup"><span data-stu-id="d9169-145">Examples</span></span>  
  
|<span data-ttu-id="d9169-146">식</span><span class="sxs-lookup"><span data-stu-id="d9169-146">Expression</span></span>|<span data-ttu-id="d9169-147">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="d9169-147">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1));`|`.Lambda #Lambda1<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1), "SampleLambda", null);`|`.Lambda SampleLambda<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
  
## <a name="labelexpression"></a><span data-ttu-id="d9169-148">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="d9169-148">LabelExpression</span></span>  
 <span data-ttu-id="d9169-149"><xref:System.Linq.Expressions.LabelExpression> 개체의 기본값을 지정하면 이 값은 <xref:System.Linq.Expressions.LabelTarget> 개체 앞에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9169-149">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>  
  
 <span data-ttu-id="d9169-150">`.Label` 토큰은 레이블의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d9169-150">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="d9169-151">`.LabelTarget` 토큰은 이동할 대상의 목적지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d9169-151">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>  
  
 <span data-ttu-id="d9169-152">레이블에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `#Label1` 또는 `#Label2`).</span><span class="sxs-lookup"><span data-stu-id="d9169-152">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="d9169-153">예제</span><span class="sxs-lookup"><span data-stu-id="d9169-153">Examples</span></span>  
  
|<span data-ttu-id="d9169-154">식</span><span class="sxs-lookup"><span data-stu-id="d9169-154">Expression</span></span>|<span data-ttu-id="d9169-155">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="d9169-155">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`LabelTarget target = Expression.Label(typeof(int), "SampleLabel"); BlockExpression block = Expression.Block( Expression.Goto(target, Expression.Constant(0)), Expression.Label(target, Expression.Constant(-1)));`|`.Block() {`<br /><br /> `.Goto SampleLabel { 0 };`<br /><br /> `.Label`<br /><br /> `-1`<br /><br /> `.LabelTarget SampleLabel:`<br /><br /> `}`|  
|`LabelTarget target = Expression.Label(); BlockExpression block = Expression.Block( Expression.Goto(target5), Expression.Label(target5));`|`.Block() {`<br /><br /> `.Goto #Label1 { };`<br /><br /> `.Label`<br /><br /> `.LabelTarget #Label1:`<br /><br /> `}`|  
  
## <a name="checked-operators"></a><span data-ttu-id="d9169-156">확인된 연산자</span><span class="sxs-lookup"><span data-stu-id="d9169-156">Checked Operators</span></span>  
 <span data-ttu-id="d9169-157">확인된 연산자는 연산자 앞에 “#” 기호가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9169-157">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="d9169-158">예를 들어 확인된 더하기 연산자는 `#+`로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9169-158">For example, the checked addition operator is displayed as `#+`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="d9169-159">예제</span><span class="sxs-lookup"><span data-stu-id="d9169-159">Examples</span></span>  
  
|<span data-ttu-id="d9169-160">식</span><span class="sxs-lookup"><span data-stu-id="d9169-160">Expression</span></span>|<span data-ttu-id="d9169-161">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="d9169-161">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`Expression expr = Expression.AddChecked( Expression.Constant(1), Expression.Constant(2));`|`1 #+ 2`|  
|`Expression expr = Expression.ConvertChecked( Expression.Constant(10.0), typeof(int));`|`#(System.Int32)10D`|  
  
## <a name="see-also"></a><span data-ttu-id="d9169-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9169-162">See Also</span></span>  
 <span data-ttu-id="d9169-163">[식 트리(C#)](../../../../csharp/programming-guide/concepts/expression-trees/index.md) </span><span class="sxs-lookup"><span data-stu-id="d9169-163">[Expression Trees (C#)](../../../../csharp/programming-guide/concepts/expression-trees/index.md) </span></span>  
 <span data-ttu-id="d9169-164">[Visual Studio의 디버깅](/visualstudio/debugger/debugging-in-visual-studio) </span><span class="sxs-lookup"><span data-stu-id="d9169-164">[Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio) </span></span>  
 <span data-ttu-id="d9169-165">[Create Custom Visualizers of Data](/visualstudio/debugger/create-custom-visualizers-of-data)(데이터의 사용자 지정 시각화 도우미 만들기)</span><span class="sxs-lookup"><span data-stu-id="d9169-165">[Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data)</span></span>

