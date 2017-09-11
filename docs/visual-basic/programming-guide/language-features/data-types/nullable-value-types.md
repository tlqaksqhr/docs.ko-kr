---
title: "Nullable 값 형식 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Nullable
dev_langs:
- VB
helpviewer_keywords:
- nullable types [Visual Basic]
- '? [Visual Basic]'
- types [Visual Basic], nullable
- nullable types
- data types [Visual Basic], nullable
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 226ffb8a329e31576c9a8120940c683ad10a030b
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="nullable-value-types-visual-basic"></a><span data-ttu-id="8aec8-102">Nullable 값 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8aec8-102">Nullable Value Types (Visual Basic)</span></span>
<span data-ttu-id="8aec8-103">경우에 따라 상황에 따라 정의 된 값이 없는 값 형식으로 작업할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-103">Sometimes you work with a value type that does not have a defined value in certain circumstances.</span></span> <span data-ttu-id="8aec8-104">예를 들어 한 데이터베이스의 필드에에서 의미 있는 할당된 된 값 들이 없는 할당된 된 값을 구분 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-104">For example, a field in a database might have to distinguish between having an assigned value that is meaningful and not having an assigned value.</span></span> <span data-ttu-id="8aec8-105">값 형식 변수 정상 값 또는 null 값을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-105">Value types can be extended to take either their normal values or a null value.</span></span> <span data-ttu-id="8aec8-106">이러한 확장 이라고는 *nullable 형식*합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-106">Such an extension is called a *nullable type*.</span></span>  
  
 <span data-ttu-id="8aec8-107">각 nullable 형식이 제네릭에서 생성 된 <xref:System.Nullable%601>구조.</xref:System.Nullable%601></span><span class="sxs-lookup"><span data-stu-id="8aec8-107">Each nullable type is constructed from the generic <xref:System.Nullable%601> structure.</span></span> <span data-ttu-id="8aec8-108">작업 관련 작업을 추적 하는 데이터베이스를 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-108">Consider a database that tracks work-related activities.</span></span> <span data-ttu-id="8aec8-109">다음 구성 예제는 null을 허용 `Boolean` 입력 하 고 해당 형식의 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-109">The following example constructs a nullable `Boolean` type and declares a variable of that type.</span></span> <span data-ttu-id="8aec8-110">세 가지 방법으로 선언을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-110">You can write the declaration in three ways:</span></span>  
  
 <span data-ttu-id="8aec8-111">[!code-vb[VbVbalrNullableValue #&1;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8aec8-111">[!code-vb[VbVbalrNullableValue#1](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_1.vb)]</span></span>  
  
 <span data-ttu-id="8aec8-112">변수 `ridesBusToWork` 의 값을 보유할 수 `True`, 값이 `False`, 또는 모두에 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-112">The variable `ridesBusToWork` can hold a value of `True`, a value of `False`, or no value at all.</span></span> <span data-ttu-id="8aec8-113">초기 기본값은 값이 없는 전혀는 예제의 것을 의미할 수도이 사용자에 대 한 정보가 아직 획득 하지.</span><span class="sxs-lookup"><span data-stu-id="8aec8-113">Its initial default value is no value at all, which in this case could mean that the information has not yet been obtained for this person.</span></span> <span data-ttu-id="8aec8-114">반면, `False` 정보를 획득 한를 사람이 버스로 작동 하지 않음을 의미할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-114">In contrast, `False` could mean that the information has been obtained and the person does not ride the bus to work.</span></span>  
  
 <span data-ttu-id="8aec8-115">Nullable 형식의 변수 및 속성을 선언할 수 및 nullable 형식의 요소가 포함 된 배열을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-115">You can declare variables and properties with nullable types, and you can declare an array with elements of a nullable type.</span></span> <span data-ttu-id="8aec8-116">Nullable 형식의 매개 변수로 프로시저를 선언할 수 있고에서 null 허용 형식을 반환할 수는 `Function` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-116">You can declare procedures with nullable types as parameters, and you can return a nullable type from a `Function` procedure.</span></span>  
  
 <span data-ttu-id="8aec8-117">배열 등과 같이 참조 형식에는 nullable 형식을 구성할 수 없습니다. 한 `String`, 또는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-117">You cannot construct a nullable type on a reference type such as an array, a `String`, or a class.</span></span> <span data-ttu-id="8aec8-118">기본 형식이 값 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-118">The underlying type must be a value type.</span></span> <span data-ttu-id="8aec8-119">자세한 내용은 참조 [값 형식과 참조 형식이](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-119">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
## <a name="using-a-nullable-type-variable"></a><span data-ttu-id="8aec8-120">Nullable 형식 변수를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="8aec8-120">Using a Nullable Type Variable</span></span>  
 <span data-ttu-id="8aec8-121">Nullable 형식의 가장 중요 한 멤버는 해당 <xref:System.Nullable%601.HasValue%2A>및 <xref:System.Nullable%601.Value%2A>속성.</xref:System.Nullable%601.Value%2A> </xref:System.Nullable%601.HasValue%2A></span><span class="sxs-lookup"><span data-stu-id="8aec8-121">The most important members of a nullable type are its <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> properties.</span></span> <span data-ttu-id="8aec8-122">Nullable 형식의 변수에 대 한 <xref:System.Nullable%601.HasValue%2A>변수에 정의 된 값을 포함 하는 여부를 알려줍니다.</xref:System.Nullable%601.HasValue%2A></span><span class="sxs-lookup"><span data-stu-id="8aec8-122">For a variable of a nullable type, <xref:System.Nullable%601.HasValue%2A> tells you whether the variable contains a defined value.</span></span> <span data-ttu-id="8aec8-123">경우 <xref:System.Nullable%601.HasValue%2A>은 `True`, <xref:System.Nullable%601.Value%2A>.</xref:System.Nullable%601.Value%2A> 에서 값을 읽을 수</xref:System.Nullable%601.HasValue%2A></span><span class="sxs-lookup"><span data-stu-id="8aec8-123">If <xref:System.Nullable%601.HasValue%2A> is `True`, you can read the value from <xref:System.Nullable%601.Value%2A>.</span></span> <span data-ttu-id="8aec8-124">모두 <xref:System.Nullable%601.HasValue%2A>및 <xref:System.Nullable%601.Value%2A>는 `ReadOnly` 속성.</xref:System.Nullable%601.Value%2A> </xref:System.Nullable%601.HasValue%2A></span><span class="sxs-lookup"><span data-stu-id="8aec8-124">Note that both <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> are `ReadOnly` properties.</span></span>  
  
### <a name="default-values"></a><span data-ttu-id="8aec8-125">기본값</span><span class="sxs-lookup"><span data-stu-id="8aec8-125">Default Values</span></span>  
 <span data-ttu-id="8aec8-126">Nullable 형식으로 변수를 선언 하는 경우 해당 <xref:System.Nullable%601.HasValue%2A>속성의 기본값은 `False`.</xref:System.Nullable%601.HasValue%2A></span><span class="sxs-lookup"><span data-stu-id="8aec8-126">When you declare a variable with a nullable type, its <xref:System.Nullable%601.HasValue%2A> property has a default value of `False`.</span></span> <span data-ttu-id="8aec8-127">즉, 기본적으로 변수에 있는 내부 값 형식의 기본값 대신 정의 된 값 없음.</span><span class="sxs-lookup"><span data-stu-id="8aec8-127">This means that by default the variable has no defined value, instead of the default value of its underlying value type.</span></span> <span data-ttu-id="8aec8-128">다음 예제에서는 변수에서에서 `numberOfChildren` 처음 정의 된 값이 없는 경우에 기본의 값이 고 `Integer` 유형 0입니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-128">In the following example, the variable `numberOfChildren` initially has no defined value, even though the default value of the `Integer` type is 0.</span></span>  
  
 <span data-ttu-id="8aec8-129">[!code-vb[VbVbalrNullableValue #&2;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="8aec8-129">[!code-vb[VbVbalrNullableValue#2](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_2.vb)]</span></span>  
  
 <span data-ttu-id="8aec8-130">Null 값이 정의 되지 않거나 알 수 없는 값을 나타내는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-130">A null value is useful to indicate an undefined or unknown value.</span></span> <span data-ttu-id="8aec8-131">경우 `numberOfChildren` 로 선언 `Integer`, 정보를 현재 사용할 수 없다는 나타낼 수 있는 값이 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-131">If `numberOfChildren` had been declared as `Integer`, there would be no value that could indicate that the information is not currently available.</span></span>  
  
### <a name="storing-values"></a><span data-ttu-id="8aec8-132">값 저장</span><span class="sxs-lookup"><span data-stu-id="8aec8-132">Storing Values</span></span>  
 <span data-ttu-id="8aec8-133">일반적인 방식으로 변수나 nullable 형식의 속성에 값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-133">You store a value in a variable or property of a nullable type in the typical way.</span></span> <span data-ttu-id="8aec8-134">다음 예제에서는 값을 변수에 할당 `numberOfChildren` 이전 예제의 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-134">The following example assigns a value to the variable `numberOfChildren` declared in the previous example.</span></span>  
  
 <span data-ttu-id="8aec8-135">[!code-vb[VbVbalrNullableValue #&3;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="8aec8-135">[!code-vb[VbVbalrNullableValue#3](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_3.vb)]</span></span>  
  
 <span data-ttu-id="8aec8-136">변수 또는 nullable 형식의 속성에 정의 된 값이 있으면 값이 할당 하지 않는 경우의 초기 상태로 되돌릴 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-136">If a variable or property of a nullable type contains a defined value, you can cause it to revert to its initial state of not having a value assigned.</span></span> <span data-ttu-id="8aec8-137">변수 또는 속성을 설정 하 여이 작업을 수행 `Nothing`다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-137">You do this by setting the variable or property to `Nothing`, as the following example shows.</span></span>  
  
 <span data-ttu-id="8aec8-138">[!code-vb[VbVbalrNullableValue #&4;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="8aec8-138">[!code-vb[VbVbalrNullableValue#4](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_4.vb)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8aec8-139">할당할 수 있지만 `Nothing` nullable 형식의 변수에 테스트할 수는 없습니다에 대 한 `Nothing` 등호를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-139">Although you can assign `Nothing` to a variable of a nullable type, you cannot test it for `Nothing` by using the equal sign.</span></span> <span data-ttu-id="8aec8-140">등호를 사용 하 여 비교 `someVar = Nothing`, 언제나 평가 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-140">Comparison that uses the equal sign, `someVar = Nothing`, always evaluates to `Nothing`.</span></span> <span data-ttu-id="8aec8-141">변수를 테스트할 수 <xref:System.Nullable%601.HasValue%2A>속성에 대 한 `False`, 또는 사용 하 여 테스트는 `Is` 또는 `IsNot` 연산자.</xref:System.Nullable%601.HasValue%2A></span><span class="sxs-lookup"><span data-stu-id="8aec8-141">You can test the variable's <xref:System.Nullable%601.HasValue%2A> property for `False`, or test by using the `Is` or `IsNot` operator.</span></span>  
  
### <a name="retrieving-values"></a><span data-ttu-id="8aec8-142">값 검색</span><span class="sxs-lookup"><span data-stu-id="8aec8-142">Retrieving Values</span></span>  
 <span data-ttu-id="8aec8-143">Nullable 형식의 변수 값을 검색 하려면 먼저을 테스트 해야 해당 <xref:System.Nullable%601.HasValue%2A>속성을 값이 있는지 확인 합니다.</xref:System.Nullable%601.HasValue%2A></span><span class="sxs-lookup"><span data-stu-id="8aec8-143">To retrieve the value of a variable of a nullable type, you should first test its <xref:System.Nullable%601.HasValue%2A> property to confirm that it has a value.</span></span> <span data-ttu-id="8aec8-144">값을 읽고 하려고 하면 때 <xref:System.Nullable%601.HasValue%2A>은 `False`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] throw는 <xref:System.InvalidOperationException>예외가.</xref:System.InvalidOperationException> </xref:System.Nullable%601.HasValue%2A></span><span class="sxs-lookup"><span data-stu-id="8aec8-144">If you try to read the value when <xref:System.Nullable%601.HasValue%2A> is `False`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] throws an <xref:System.InvalidOperationException> exception.</span></span> <span data-ttu-id="8aec8-145">다음 예에서는 변수를 읽은 하는 권장된 방법은 `numberOfChildren` 앞의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-145">The following example shows the recommended way to read the variable `numberOfChildren` of the previous examples.</span></span>  
  
 <span data-ttu-id="8aec8-146">[!code-vb[VbVbalrNullableValue #&5;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="8aec8-146">[!code-vb[VbVbalrNullableValue#5](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_5.vb)]</span></span>  
  
## <a name="comparing-nullable-types"></a><span data-ttu-id="8aec8-147">Nullable 형식 비교</span><span class="sxs-lookup"><span data-stu-id="8aec8-147">Comparing Nullable Types</span></span>  
 <span data-ttu-id="8aec8-148">Null을 허용 하는 경우 `Boolean` 변수는 부울 식에 사용 될 수 있습니다, `True`, `False`, 또는 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-148">When nullable `Boolean` variables are used in Boolean expressions, the result can be `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="8aec8-149">다음은 truth 테이블에 대 한 `And` 및 `Or`합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-149">The following is the truth table for `And` and `Or`.</span></span> <span data-ttu-id="8aec8-150">때문에 `b1` 및 `b2` 만들었습니다 다음&3; 가지 값을&9; 개 조합을 평가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-150">Because `b1` and `b2` now have three possible values, there are nine combinations to evaluate.</span></span>  
  
|<span data-ttu-id="8aec8-151">b1</span><span class="sxs-lookup"><span data-stu-id="8aec8-151">b1</span></span>|<span data-ttu-id="8aec8-152">b&2;</span><span class="sxs-lookup"><span data-stu-id="8aec8-152">b2</span></span>|<span data-ttu-id="8aec8-153">b1 및 b&2;</span><span class="sxs-lookup"><span data-stu-id="8aec8-153">b1 And b2</span></span>|<span data-ttu-id="8aec8-154">b1 또는 b&2;</span><span class="sxs-lookup"><span data-stu-id="8aec8-154">b1 Or b2</span></span>|  
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
  
 <span data-ttu-id="8aec8-155">부울 변수 또는 식의 값이 `Nothing`가 아닌 `true` 나 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-155">When the value of a Boolean variable or expression is `Nothing`, it is neither `true` nor `false`.</span></span> <span data-ttu-id="8aec8-156">다음 예제를 살펴보십시오.</span><span class="sxs-lookup"><span data-stu-id="8aec8-156">Consider the following example.</span></span>  
  
 <span data-ttu-id="8aec8-157">[!code-vb[VbVbalrNullableValue #&6;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="8aec8-157">[!code-vb[VbVbalrNullableValue#6](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_6.vb)]</span></span>  
  
 <span data-ttu-id="8aec8-158">이 예제에서는 `b1 And b2` 계산 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-158">In this example, `b1 And b2` evaluates to `Nothing`.</span></span> <span data-ttu-id="8aec8-159">결과적으로 `Else` 각 절이 실행 `If` 문과 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-159">As a result, the `Else` clause is executed in each `If` statement, and the output is as follows:</span></span>  
  
 `Expression is not true`  
  
 `Expression is not false`  
  
> [!NOTE]
> <span data-ttu-id="8aec8-160"> `AndAlso`및 `OrElse`, 단락 계산을 사용 하는 계산 되어야 두 번째 피연산자는 첫 번째 일 때 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-160"> `AndAlso` and `OrElse`, which use short-circuit evaluation, must evaluate their second operands when the first evaluates to `Nothing`.</span></span>  
  
## <a name="propagation"></a><span data-ttu-id="8aec8-161">전파</span><span class="sxs-lookup"><span data-stu-id="8aec8-161">Propagation</span></span>  
 <span data-ttu-id="8aec8-162">산술, 비교, 시프트 또는 형식 작업의 피연산자 중 하나 또는 모두 이면 null을 허용 연산의 결과가 null을 허용 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-162">If one or both of the operands of an arithmetic, comparison, shift, or type operation is nullable, the result of the operation is also nullable.</span></span> <span data-ttu-id="8aec8-163">두 피연산자 값이 없는 경우 `Nothing`, 작업은 피연산자의 내부 값에 것 처럼 수행 모두 nullable 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-163">If both operands have values that are not `Nothing`, the operation is performed on the underlying values of the operands, as if neither were a nullable type.</span></span> <span data-ttu-id="8aec8-164">다음 예제에서 변수 `compare1` 및 `sum1` 는 암시적으로 형식화 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-164">In the following example, variables `compare1` and `sum1` are implicitly typed.</span></span> <span data-ttu-id="8aec8-165">위로 마우스 포인터를 놓으면 컴파일러 둘 다에 대 한 null 허용 형식 유추는 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-165">If you rest the mouse pointer over them, you will see that the compiler infers nullable types for both of them.</span></span>  
  
 <span data-ttu-id="8aec8-166">[!code-vb[VbVbalrNullableValue #&7;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="8aec8-166">[!code-vb[VbVbalrNullableValue#7](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_7.vb)]</span></span>  
  
 <span data-ttu-id="8aec8-167">하나 또는 두 피연산자의 값이 없는 경우 `Nothing`, 결과 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-167">If one or both operands have a value of `Nothing`, the result will be `Nothing`.</span></span>  
  
 <span data-ttu-id="8aec8-168">[!code-vb[VbVbalrNullableValue #&8;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="8aec8-168">[!code-vb[VbVbalrNullableValue#8](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_8.vb)]</span></span>  
  
## <a name="using-nullable-types-with-data"></a><span data-ttu-id="8aec8-169">데이터와 Nullable 형식 사용</span><span class="sxs-lookup"><span data-stu-id="8aec8-169">Using Nullable Types with Data</span></span>  
 <span data-ttu-id="8aec8-170">데이터베이스에는 nullable 형식을 사용 하 여 가장 중요 한 위치 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-170">A database is one of the most important places to use nullable types.</span></span> <span data-ttu-id="8aec8-171">모든 데이터베이스 개체에는 현재 nullable 형식 지원 않지만 테이블 디자이너에서 생성 된 어댑터입니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-171">Not all database objects currently support nullable types, but the designer-generated table adapters do.</span></span> <span data-ttu-id="8aec8-172">"Nullable 형식에 대 한 TableAdapter 지원"을 참조 [TableAdapter 개요](https://docs.microsoft.com/visualstudio/data-tools/tableadapter-overview)합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec8-172">See "TableAdapter Support for Nullable Types" in [TableAdapter Overview](https://docs.microsoft.com/visualstudio/data-tools/tableadapter-overview).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aec8-173">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8aec8-173">See Also</span></span>  
 <span data-ttu-id="8aec8-174"><xref:System.InvalidOperationException></xref:System.InvalidOperationException></span><span class="sxs-lookup"><span data-stu-id="8aec8-174"><xref:System.InvalidOperationException></span></span>   
 <span data-ttu-id="8aec8-175"><xref:System.Nullable%601.HasValue%2A></xref:System.Nullable%601.HasValue%2A></span><span class="sxs-lookup"><span data-stu-id="8aec8-175"><xref:System.Nullable%601.HasValue%2A></span></span>   
<span data-ttu-id="8aec8-176"> [Nullable 형식 사용](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md) </span><span class="sxs-lookup"><span data-stu-id="8aec8-176"> [Using Nullable Types](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md) </span></span>  
<span data-ttu-id="8aec8-177"> [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="8aec8-177"> [Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span></span>  
<span data-ttu-id="8aec8-178"> [값 형식과 참조 형식](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="8aec8-178"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
<span data-ttu-id="8aec8-179"> [데이터 형식 문제 해결](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="8aec8-179"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
<span data-ttu-id="8aec8-180"> [TableAdapter 개요](https://docs.microsoft.com/visualstudio/data-tools/tableadapter-overview) </span><span class="sxs-lookup"><span data-stu-id="8aec8-180"> [TableAdapter Overview](https://docs.microsoft.com/visualstudio/data-tools/tableadapter-overview) </span></span>  
<span data-ttu-id="8aec8-181"> [경우 연산자](../../../../visual-basic/language-reference/operators/if-operator.md) </span><span class="sxs-lookup"><span data-stu-id="8aec8-181"> [If Operator](../../../../visual-basic/language-reference/operators/if-operator.md) </span></span>  
<span data-ttu-id="8aec8-182"> [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span><span class="sxs-lookup"><span data-stu-id="8aec8-182"> [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span></span>  
<span data-ttu-id="8aec8-183"> [Is 연산자](../../../../visual-basic/language-reference/operators/is-operator.md) </span><span class="sxs-lookup"><span data-stu-id="8aec8-183"> [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) </span></span>  
<span data-ttu-id="8aec8-184"> [IsNot 연산자](../../../../visual-basic/language-reference/operators/isnot-operator.md)</span><span class="sxs-lookup"><span data-stu-id="8aec8-184"> [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md)</span></span>
