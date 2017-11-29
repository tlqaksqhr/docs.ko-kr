---
title: "Nullable 값 형식(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Nullable
helpviewer_keywords:
- nullable types [Visual Basic]
- '? [Visual Basic]'
- types [Visual Basic], nullable
- nullable types [Visual Basic]
- data types [Visual Basic], nullable
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8734114b9d657066a0ef0b2d648f0290c03b1cbf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="nullable-value-types-visual-basic"></a><span data-ttu-id="ad20f-102">Nullable 값 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ad20f-102">Nullable Value Types (Visual Basic)</span></span>
<span data-ttu-id="ad20f-103">경우에 따라 상황에 따라 정의 된 값이 없는 값 형식과 함께 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-103">Sometimes you work with a value type that does not have a defined value in certain circumstances.</span></span> <span data-ttu-id="ad20f-104">예를 들어 한 데이터베이스의 필드에에서 의미 있는 있는 할당 된 값이 있는 할당된 된 값 고 다니지 않아도 구분 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-104">For example, a field in a database might have to distinguish between having an assigned value that is meaningful and not having an assigned value.</span></span> <span data-ttu-id="ad20f-105">값 형식 매개 변수 정상 값 또는 null 값을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-105">Value types can be extended to take either their normal values or a null value.</span></span> <span data-ttu-id="ad20f-106">이러한 확장 라고는 *nullable 형식*합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-106">Such an extension is called a *nullable type*.</span></span>  
  
 <span data-ttu-id="ad20f-107">각 nullable 형식에서 제네릭 만들어집니다 <xref:System.Nullable%601> 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-107">Each nullable type is constructed from the generic <xref:System.Nullable%601> structure.</span></span> <span data-ttu-id="ad20f-108">작업 관련 작업을 추적 하는 데이터베이스를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-108">Consider a database that tracks work-related activities.</span></span> <span data-ttu-id="ad20f-109">다음 구성 예제에서 null을 허용 `Boolean` 입력 하 고 해당 형식의 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-109">The following example constructs a nullable `Boolean` type and declares a variable of that type.</span></span> <span data-ttu-id="ad20f-110">세 가지 방법으로 선언을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-110">You can write the declaration in three ways:</span></span>  
  
 [!code-vb[VbVbalrNullableValue#1](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_1.vb)]  
  
 <span data-ttu-id="ad20f-111">변수 `ridesBusToWork` 의 값을 보유할 수 `True`, 값이 `False`, 또는 모두에 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-111">The variable `ridesBusToWork` can hold a value of `True`, a value of `False`, or no value at all.</span></span> <span data-ttu-id="ad20f-112">초기 기본값은 값이 없는 전혀는 경우 것을 의미할 수도이 사용자에 대 한 정보가 아직 가져올 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-112">Its initial default value is no value at all, which in this case could mean that the information has not yet been obtained for this person.</span></span> <span data-ttu-id="ad20f-113">반면, `False` 정보를 가져올를 사람이 버스로 작동 하지 않음을 의미할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-113">In contrast, `False` could mean that the information has been obtained and the person does not ride the bus to work.</span></span>  
  
 <span data-ttu-id="ad20f-114">Nullable 형식의 변수 및 속성을 선언할 수 있습니다 하 고 nullable 형식의 요소가 있는 배열을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-114">You can declare variables and properties with nullable types, and you can declare an array with elements of a nullable type.</span></span> <span data-ttu-id="ad20f-115">프로시저를 매개 변수로 null 허용 형식으로 선언할 수 있습니다 및에서 null 허용 형식을 반환할 수 있습니다는 `Function` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-115">You can declare procedures with nullable types as parameters, and you can return a nullable type from a `Function` procedure.</span></span>  
  
 <span data-ttu-id="ad20f-116">배열에 같은 참조 형식에는 nullable 형식을 만들 수 없습니다는 `String`, 또는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-116">You cannot construct a nullable type on a reference type such as an array, a `String`, or a class.</span></span> <span data-ttu-id="ad20f-117">내부 형식에는 값 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-117">The underlying type must be a value type.</span></span> <span data-ttu-id="ad20f-118">자세한 내용은 참조 [값 형식과 참조 형식이](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-118">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
## <a name="using-a-nullable-type-variable"></a><span data-ttu-id="ad20f-119">Nullable 형식 변수를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="ad20f-119">Using a Nullable Type Variable</span></span>  
 <span data-ttu-id="ad20f-120">Nullable 형식의 가장 중요 한 멤버는 해당 <xref:System.Nullable%601.HasValue%2A> 및 <xref:System.Nullable%601.Value%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-120">The most important members of a nullable type are its <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> properties.</span></span> <span data-ttu-id="ad20f-121">Nullable 형식의 변수에 대 한 <xref:System.Nullable%601.HasValue%2A> 변수에 정의 된 값을 포함 하는지 여부를 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-121">For a variable of a nullable type, <xref:System.Nullable%601.HasValue%2A> tells you whether the variable contains a defined value.</span></span> <span data-ttu-id="ad20f-122">경우 <xref:System.Nullable%601.HasValue%2A> 은 `True`, 값을 읽을 수 <xref:System.Nullable%601.Value%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-122">If <xref:System.Nullable%601.HasValue%2A> is `True`, you can read the value from <xref:System.Nullable%601.Value%2A>.</span></span> <span data-ttu-id="ad20f-123">둘 다 <xref:System.Nullable%601.HasValue%2A> 및 <xref:System.Nullable%601.Value%2A> 는 `ReadOnly` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-123">Note that both <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> are `ReadOnly` properties.</span></span>  
  
### <a name="default-values"></a><span data-ttu-id="ad20f-124">기본값</span><span class="sxs-lookup"><span data-stu-id="ad20f-124">Default Values</span></span>  
 <span data-ttu-id="ad20f-125">Nullable 형식과 함께 변수를 선언 하는 경우 해당 <xref:System.Nullable%601.HasValue%2A> 속성의 기본값은 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-125">When you declare a variable with a nullable type, its <xref:System.Nullable%601.HasValue%2A> property has a default value of `False`.</span></span> <span data-ttu-id="ad20f-126">즉, 기본적으로 변수 값 없음-정의 된 내부 값 형식의 기본 값 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-126">This means that by default the variable has no defined value, instead of the default value of its underlying value type.</span></span> <span data-ttu-id="ad20f-127">다음 예에서 변수 `numberOfChildren` 초기에 정의 된 값이 없을 경우에의 기본값은 `Integer` 유형 0입니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-127">In the following example, the variable `numberOfChildren` initially has no defined value, even though the default value of the `Integer` type is 0.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#2](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_2.vb)]  
  
 <span data-ttu-id="ad20f-128">Null 값이 정의 되지 않거나 알 수 없는 값을 나타내는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-128">A null value is useful to indicate an undefined or unknown value.</span></span> <span data-ttu-id="ad20f-129">경우 `numberOfChildren` 로 선언 `Integer`, 정보를 현재 사용할 수 있는지를 나타낼 수 있는 값이 있을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-129">If `numberOfChildren` had been declared as `Integer`, there would be no value that could indicate that the information is not currently available.</span></span>  
  
### <a name="storing-values"></a><span data-ttu-id="ad20f-130">값 저장</span><span class="sxs-lookup"><span data-stu-id="ad20f-130">Storing Values</span></span>  
 <span data-ttu-id="ad20f-131">일반적인 방식으로 변수 또는 nullable 형식의 속성에 값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-131">You store a value in a variable or property of a nullable type in the typical way.</span></span> <span data-ttu-id="ad20f-132">다음 예제에서는 값을 변수에 할당 `numberOfChildren` 이전 예제의 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-132">The following example assigns a value to the variable `numberOfChildren` declared in the previous example.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#3](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_3.vb)]  
  
 <span data-ttu-id="ad20f-133">변수 또는 nullable 형식의 속성에 정의 된 값이 있으면 하지 않는 경우 할당 된 값의 초기 상태로 되돌리려면 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-133">If a variable or property of a nullable type contains a defined value, you can cause it to revert to its initial state of not having a value assigned.</span></span> <span data-ttu-id="ad20f-134">변수 또는 속성을 설정 하 여이 작업을 수행 `Nothing`다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-134">You do this by setting the variable or property to `Nothing`, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#4](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_4.vb)]  
  
> [!NOTE]
>  <span data-ttu-id="ad20f-135">할당할 수 있지만 `Nothing` nullable 형식의 변수에 테스트할 수는 없습니다에 대 한 `Nothing` 등호를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-135">Although you can assign `Nothing` to a variable of a nullable type, you cannot test it for `Nothing` by using the equal sign.</span></span> <span data-ttu-id="ad20f-136">등호 기호를 사용 하 여 비교 `someVar = Nothing`, 항상로 평가 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-136">Comparison that uses the equal sign, `someVar = Nothing`, always evaluates to `Nothing`.</span></span> <span data-ttu-id="ad20f-137">변수를 테스트할 수 <xref:System.Nullable%601.HasValue%2A> 속성에 대 한 `False`, 또는 사용 하 여 테스트는 `Is` 또는 `IsNot` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-137">You can test the variable's <xref:System.Nullable%601.HasValue%2A> property for `False`, or test by using the `Is` or `IsNot` operator.</span></span>  
  
### <a name="retrieving-values"></a><span data-ttu-id="ad20f-138">값 검색</span><span class="sxs-lookup"><span data-stu-id="ad20f-138">Retrieving Values</span></span>  
 <span data-ttu-id="ad20f-139">Nullable 형식의 변수 값을 검색 하려면 먼저을 테스트 해야 해당 <xref:System.Nullable%601.HasValue%2A> 속성을 값이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-139">To retrieve the value of a variable of a nullable type, you should first test its <xref:System.Nullable%601.HasValue%2A> property to confirm that it has a value.</span></span> <span data-ttu-id="ad20f-140">값을 읽으려고 하면 때 <xref:System.Nullable%601.HasValue%2A> 은 `False`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] throw 한 <xref:System.InvalidOperationException> 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-140">If you try to read the value when <xref:System.Nullable%601.HasValue%2A> is `False`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] throws an <xref:System.InvalidOperationException> exception.</span></span> <span data-ttu-id="ad20f-141">다음 예에서는 변수를 읽은 하는 권장된 방법은 `numberOfChildren` 앞의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-141">The following example shows the recommended way to read the variable `numberOfChildren` of the previous examples.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#5](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_5.vb)]  
  
## <a name="comparing-nullable-types"></a><span data-ttu-id="ad20f-142">Nullable 형식 비교</span><span class="sxs-lookup"><span data-stu-id="ad20f-142">Comparing Nullable Types</span></span>  
 <span data-ttu-id="ad20f-143">Null을 허용 하는 경우 `Boolean` 변수는 부울 식에 사용 될 수 있습니다, `True`, `False`, 또는 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-143">When nullable `Boolean` variables are used in Boolean expressions, the result can be `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="ad20f-144">다음은에 대 한 진리표 `And` 및 `Or`합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-144">The following is the truth table for `And` and `Or`.</span></span> <span data-ttu-id="ad20f-145">때문에 `b1` 및 `b2` 생깁니다 다음 3 가지 값을 9 개의 조합을 평가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-145">Because `b1` and `b2` now have three possible values, there are nine combinations to evaluate.</span></span>  
  
|<span data-ttu-id="ad20f-146">B1</span><span class="sxs-lookup"><span data-stu-id="ad20f-146">b1</span></span>|<span data-ttu-id="ad20f-147">B 2</span><span class="sxs-lookup"><span data-stu-id="ad20f-147">b2</span></span>|<span data-ttu-id="ad20f-148">b1 및 b 2</span><span class="sxs-lookup"><span data-stu-id="ad20f-148">b1 And b2</span></span>|<span data-ttu-id="ad20f-149">b1 또는 b 2</span><span class="sxs-lookup"><span data-stu-id="ad20f-149">b1 Or b2</span></span>|  
|--------|--------|---------------|--------------|  
|`Nothing`|`Nothing`|`Nothing`|`Nothing`|  
|`Nothing`|`True`|`Nothing`|`True`|  
|`Nothing`|`False`|`False`|`Nothing`|  
|`True`|`Nothing`|`Nothing`|`True`|  
|`True`|`True`|`True`|`True`|  
|`True`|`False`|`False`|`True`|  
|`False`|`Nothing`|`False`|`Nothing`|  
|`False`|`True`|`False`|`True`|  
|`False`|`False`|`False`|`False`|  
  
 <span data-ttu-id="ad20f-150">부울 변수 또는 식의 값이 `Nothing`가 아닌 `true` 나 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-150">When the value of a Boolean variable or expression is `Nothing`, it is neither `true` nor `false`.</span></span> <span data-ttu-id="ad20f-151">다음 예제를 살펴보십시오.</span><span class="sxs-lookup"><span data-stu-id="ad20f-151">Consider the following example.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#6](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_6.vb)]  
  
 <span data-ttu-id="ad20f-152">이 예제에서는 `b1 And b2` 계산 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-152">In this example, `b1 And b2` evaluates to `Nothing`.</span></span> <span data-ttu-id="ad20f-153">결과적으로 `Else` 각 절이 실행 `If` 문과 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-153">As a result, the `Else` clause is executed in each `If` statement, and the output is as follows:</span></span>  
  
 `Expression is not true`  
  
 `Expression is not false`  
  
> [!NOTE]
>  <span data-ttu-id="ad20f-154">`AndAlso`및 `OrElse`를 사용 하는 평가, 단락 (short-circuit) 계산 되어야 합니다는 두 번째 피연산자로 평가 되는 첫 번째 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-154">`AndAlso` and `OrElse`, which use short-circuit evaluation, must evaluate their second operands when the first evaluates to `Nothing`.</span></span>  
  
## <a name="propagation"></a><span data-ttu-id="ad20f-155">전파</span><span class="sxs-lookup"><span data-stu-id="ad20f-155">Propagation</span></span>  
 <span data-ttu-id="ad20f-156">산술, 비교, 시프트 또는 형식 작업의 피연산자 중 하나 또는 모두에서 null을 허용 하는 경우 연산의 결과가 null을 허용 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-156">If one or both of the operands of an arithmetic, comparison, shift, or type operation is nullable, the result of the operation is also nullable.</span></span> <span data-ttu-id="ad20f-157">두 피연산자는 아닌 값이 있으면 `Nothing`, 작업은 피연산자의 기본 값에 것 처럼 수행 모두 nullable 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-157">If both operands have values that are not `Nothing`, the operation is performed on the underlying values of the operands, as if neither were a nullable type.</span></span> <span data-ttu-id="ad20f-158">다음 예에서는 변수 `compare1` 및 `sum1` 는 암시적으로 형식화 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-158">In the following example, variables `compare1` and `sum1` are implicitly typed.</span></span> <span data-ttu-id="ad20f-159">위로 마우스 포인터를 놓으면 컴파일러가 둘 모두에 대 한 nullable 형식 유추는 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-159">If you rest the mouse pointer over them, you will see that the compiler infers nullable types for both of them.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#7](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_7.vb)]  
  
 <span data-ttu-id="ad20f-160">하나 또는 두 피연산자의 값이 있으면 `Nothing`, 결과 됩니다 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-160">If one or both operands have a value of `Nothing`, the result will be `Nothing`.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#8](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_8.vb)]  
  
## <a name="using-nullable-types-with-data"></a><span data-ttu-id="ad20f-161">데이터와 Nullable 형식 사용</span><span class="sxs-lookup"><span data-stu-id="ad20f-161">Using Nullable Types with Data</span></span>  
 <span data-ttu-id="ad20f-162">데이터베이스에는 nullable 형식을 사용 하는 가장 중요 한 위치 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-162">A database is one of the most important places to use nullable types.</span></span> <span data-ttu-id="ad20f-163">일부 데이터베이스 개체에서 현재 nullable 형식을 지원 하 하지만 테이블 디자이너에서 생성 된 어댑터 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-163">Not all database objects currently support nullable types, but the designer-generated table adapters do.</span></span> <span data-ttu-id="ad20f-164">"null 허용 형식에 대 한 지원 TableAdapter" 참조 [TableAdapter 개요](/visualstudio/data-tools/tableadapter-overview)합니다.</span><span class="sxs-lookup"><span data-stu-id="ad20f-164">See "TableAdapter Support for Nullable Types" in [TableAdapter Overview](/visualstudio/data-tools/tableadapter-overview).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad20f-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ad20f-165">See Also</span></span>  
 <xref:System.InvalidOperationException>  
 <xref:System.Nullable%601.HasValue%2A>  
 [<span data-ttu-id="ad20f-166">Nullable 형식 사용</span><span class="sxs-lookup"><span data-stu-id="ad20f-166">Using Nullable Types</span></span>](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)  
 [<span data-ttu-id="ad20f-167">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ad20f-167">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="ad20f-168">값 형식과 참조 형식</span><span class="sxs-lookup"><span data-stu-id="ad20f-168">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="ad20f-169">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="ad20f-169">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="ad20f-170">TableAdapter 개요</span><span class="sxs-lookup"><span data-stu-id="ad20f-170">TableAdapter Overview</span></span>](/visualstudio/data-tools/tableadapter-overview)  
 [<span data-ttu-id="ad20f-171">If 연산자</span><span class="sxs-lookup"><span data-stu-id="ad20f-171">If Operator</span></span>](../../../../visual-basic/language-reference/operators/if-operator.md)  
 [<span data-ttu-id="ad20f-172">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="ad20f-172">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="ad20f-173">Is 연산자</span><span class="sxs-lookup"><span data-stu-id="ad20f-173">Is Operator</span></span>](../../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="ad20f-174">IsNot 연산자</span><span class="sxs-lookup"><span data-stu-id="ad20f-174">IsNot Operator</span></span>](../../../../visual-basic/language-reference/operators/isnot-operator.md)
