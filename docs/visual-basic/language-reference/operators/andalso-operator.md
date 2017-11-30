---
title: "AndAlso 연산자(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.AndAlso
- AndAlso
helpviewer_keywords:
- short-circuiting
- AndAlso operator [Visual Basic]
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], conjunction
- short-circuit evaluation
ms.assetid: bbc15191-b374-495b-9b8f-7b8c2f4388eb
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5f92f4ed226c2923c3d95a7b80db3872b7ac33dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="andalso-operator-visual-basic"></a><span data-ttu-id="c9d42-102">AndAlso 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9d42-102">AndAlso Operator (Visual Basic)</span></span>
<span data-ttu-id="c9d42-103">두 식에 논리 결합을 단락 (short-circuiting)를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d42-103">Performs short-circuiting logical conjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9d42-104">구문</span><span class="sxs-lookup"><span data-stu-id="c9d42-104">Syntax</span></span>  
  
```  
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="c9d42-105">요소</span><span class="sxs-lookup"><span data-stu-id="c9d42-105">Parts</span></span>  
  
|<span data-ttu-id="c9d42-106">용어</span><span class="sxs-lookup"><span data-stu-id="c9d42-106">Term</span></span>|<span data-ttu-id="c9d42-107">정의</span><span class="sxs-lookup"><span data-stu-id="c9d42-107">Definition</span></span>|  
|---|---|  
|`result`|<span data-ttu-id="c9d42-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="c9d42-108">Required.</span></span> <span data-ttu-id="c9d42-109">임의의 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c9d42-109">Any `Boolean` expression.</span></span> <span data-ttu-id="c9d42-110">결과는 `Boolean` 두 식의 비교의 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="c9d42-110">The result is the `Boolean` result of comparison of the two expressions.</span></span>|  
|`expression1`|<span data-ttu-id="c9d42-111">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="c9d42-111">Required.</span></span> <span data-ttu-id="c9d42-112">임의의 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c9d42-112">Any `Boolean` expression.</span></span>|  
|`expression2`|<span data-ttu-id="c9d42-113">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="c9d42-113">Required.</span></span> <span data-ttu-id="c9d42-114">임의의 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c9d42-114">Any `Boolean` expression.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9d42-115">설명</span><span class="sxs-lookup"><span data-stu-id="c9d42-115">Remarks</span></span>  
 <span data-ttu-id="c9d42-116">하나의 논리 연산자를 라고 *단락 (short-circuiting)* 컴파일된 코드는 다른 식의 결과 따라 각 식의 평가 건너뛸 수 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="c9d42-116">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="c9d42-117">작업의 최종 결과 결정 하는 평가 되는 첫 번째 식의 결과가 두 번째 식을 계산할 필요가 없습니다 때문에 최종 결과 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d42-117">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="c9d42-118">단락 (short-circuiting) 건너뛸 식이 복잡 하거나 프로시저 호출이 포함 된 경우 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d42-118">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="c9d42-119">두 식이 모두 `True`, `result` 은 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d42-119">If both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="c9d42-120">다음 표에서 설명 방법을 `result` 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9d42-120">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="c9d42-121">경우 `expression1` 은</span><span class="sxs-lookup"><span data-stu-id="c9d42-121">If `expression1` is</span></span>|<span data-ttu-id="c9d42-122">및 `expression2` 은</span><span class="sxs-lookup"><span data-stu-id="c9d42-122">And `expression2` is</span></span>|<span data-ttu-id="c9d42-123">값 `result` 은</span><span class="sxs-lookup"><span data-stu-id="c9d42-123">The value of `result` is</span></span>|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|<span data-ttu-id="c9d42-124">(계산 되지 않음)</span><span class="sxs-lookup"><span data-stu-id="c9d42-124">(not evaluated)</span></span>|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="c9d42-125">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c9d42-125">Data Types</span></span>  
 <span data-ttu-id="c9d42-126">`AndAlso` 연산자에 대해서만 정의 되는 [Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d42-126">The `AndAlso` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="c9d42-127">Visual Basic로 필요에 따라 각 피연산자를 변환 `Boolean` 에서 모든 작업을 수행 하 고 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d42-127">Visual Basic converts each operand as necessary to `Boolean` and performs the operation entirely in `Boolean`.</span></span> <span data-ttu-id="c9d42-128">Visual Basic에서 변환 하는 숫자 형식으로 결과 할당 하는 경우 `Boolean` 해당 형식으로.</span><span class="sxs-lookup"><span data-stu-id="c9d42-128">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type.</span></span> <span data-ttu-id="c9d42-129">이 예기치 않은 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d42-129">This could produce unexpected behavior.</span></span> <span data-ttu-id="c9d42-130">예를 들어 `5 AndAlso 12` 으로 인해 `–1` 변환할 때 `Integer`합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d42-130">For example, `5 AndAlso 12` results in `–1` when converted to `Integer`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="c9d42-131">오버로딩</span><span class="sxs-lookup"><span data-stu-id="c9d42-131">Overloading</span></span>  
 <span data-ttu-id="c9d42-132">[및 연산자](../../../visual-basic/language-reference/operators/and-operator.md) 및 [IsFalse 연산자](../../../visual-basic/language-reference/operators/isfalse-operator.md) 수 *오버 로드 된*, 클래스 또는 구조체 수 할 해당 명령의 동작은 피연산자의 형식이 있을 때 클래스 또는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="c9d42-132">The [And Operator](../../../visual-basic/language-reference/operators/and-operator.md) and the [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="c9d42-133">오버 로드는 `And` 및 `IsFalse` 연산자의 동작에 영향을 줍니다는 `AndAlso` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="c9d42-133">Overloading the `And` and `IsFalse` operators affects the behavior of the `AndAlso` operator.</span></span> <span data-ttu-id="c9d42-134">코드에서 `AndAlso` 클래스 또는 구조체에 오버 로드에서 `And` 및 `IsFalse`, 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d42-134">If your code uses `AndAlso` on a class or structure that overloads `And` and `IsFalse`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="c9d42-135">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d42-135">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9d42-136">예제</span><span class="sxs-lookup"><span data-stu-id="c9d42-136">Example</span></span>  
 <span data-ttu-id="c9d42-137">다음 예제에서는 `AndAlso` 두 식에 논리 결합을 수행 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="c9d42-137">The following example uses the `AndAlso` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="c9d42-138">결과는 `Boolean` 전체 식이 있는지 여부를 나타내는 값이 true입니다.</span><span class="sxs-lookup"><span data-stu-id="c9d42-138">The result is a `Boolean` value that represents whether the entire conjoined expression is true.</span></span> <span data-ttu-id="c9d42-139">첫 번째 식이 `False`, 두 번째는 평가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d42-139">If the first expression is `False`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_1.vb)]  
  
 <span data-ttu-id="c9d42-140">앞 예제의 결과는 `True`, `False`, 및 `False`각각.</span><span class="sxs-lookup"><span data-stu-id="c9d42-140">The preceding example produces results of `True`, `False`, and `False`, respectively.</span></span> <span data-ttu-id="c9d42-141">계산에 `secondCheck`, 첫 번째는 이미 때문에 두 번째 식을 계산 하지는 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d42-141">In the calculation of `secondCheck`, the second expression is not evaluated because the first is already `False`.</span></span> <span data-ttu-id="c9d42-142">계산의 두 번째 식이 계산 되는 반면 `thirdCheck`합니다.</span><span class="sxs-lookup"><span data-stu-id="c9d42-142">However, the second expression is evaluated in the calculation of `thirdCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9d42-143">예제</span><span class="sxs-lookup"><span data-stu-id="c9d42-143">Example</span></span>  
 <span data-ttu-id="c9d42-144">다음 예제에서는 한 `Function` 배열 요소 사이 지정된 된 값을 검색 하는 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="c9d42-144">The following example shows a `Function` procedure that searches for a given value among the elements of an array.</span></span> <span data-ttu-id="c9d42-145">배열이 비어 또는 배열 길이 초과 된 경우는 `While` 문은 검색 값에 대해 배열 요소를 테스트 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9d42-145">If the array is empty, or if the array length has been exceeded, the `While` statement does not test the array element against the search value.</span></span>  
  
 [!code-vb[VbVbalrOperators#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c9d42-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9d42-146">See Also</span></span>  
 [<span data-ttu-id="c9d42-147">논리/비트 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9d42-147">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="c9d42-148">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="c9d42-148">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="c9d42-149">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="c9d42-149">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="c9d42-150">And 연산자</span><span class="sxs-lookup"><span data-stu-id="c9d42-150">And Operator</span></span>](../../../visual-basic/language-reference/operators/and-operator.md)  
 [<span data-ttu-id="c9d42-151">IsFalse 연산자</span><span class="sxs-lookup"><span data-stu-id="c9d42-151">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [<span data-ttu-id="c9d42-152">Visual Basic의 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="c9d42-152">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
