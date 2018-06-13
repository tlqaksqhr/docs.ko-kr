---
title: OrElse 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- OrElse
- vb.OrElse
helpviewer_keywords:
- short-circuiting
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], disjunction
- short-circuit evaluation
- OrElse operator [Visual Basic]
ms.assetid: 253803d8-05b0-47d7-b213-abd222847779
ms.openlocfilehash: 1ee3c1a5b6089f44742281eb40e2a7e9cb3e2812
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604824"
---
# <a name="orelse-operator-visual-basic"></a><span data-ttu-id="4134a-102">OrElse 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4134a-102">OrElse Operator (Visual Basic)</span></span>
<span data-ttu-id="4134a-103">두 식에 포함 논리합 단락 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4134a-103">Performs short-circuiting inclusive logical disjunction on two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4134a-104">구문</span><span class="sxs-lookup"><span data-stu-id="4134a-104">Syntax</span></span>  
  
```  
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="4134a-105">요소</span><span class="sxs-lookup"><span data-stu-id="4134a-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="4134a-106">필수.</span><span class="sxs-lookup"><span data-stu-id="4134a-106">Required.</span></span> <span data-ttu-id="4134a-107">임의의 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="4134a-107">Any `Boolean` expression.</span></span>  
  
 `expression1`  
 <span data-ttu-id="4134a-108">필수.</span><span class="sxs-lookup"><span data-stu-id="4134a-108">Required.</span></span> <span data-ttu-id="4134a-109">임의의 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="4134a-109">Any `Boolean` expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="4134a-110">필수.</span><span class="sxs-lookup"><span data-stu-id="4134a-110">Required.</span></span> <span data-ttu-id="4134a-111">임의의 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="4134a-111">Any `Boolean` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4134a-112">설명</span><span class="sxs-lookup"><span data-stu-id="4134a-112">Remarks</span></span>  
 <span data-ttu-id="4134a-113">하나의 논리 연산자를 라고 *단락 (short-circuiting)* 컴파일된 코드는 다른 식의 결과 따라 각 식의 평가 건너뛸 수 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="4134a-113">A logical operation is said to be *short-circuiting* if the compiled code can bypass the evaluation of one expression depending on the result of another expression.</span></span> <span data-ttu-id="4134a-114">작업의 최종 결과 결정 하는 평가 되는 첫 번째 식의 결과가 두 번째 식을 계산할 필요가 없습니다 때문에 최종 결과 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4134a-114">If the result of the first expression evaluated determines the final result of the operation, there is no need to evaluate the second expression, because it cannot change the final result.</span></span> <span data-ttu-id="4134a-115">단락 (short-circuiting) 건너뛸 식이 복잡 하거나 프로시저 호출이 포함 된 경우 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4134a-115">Short-circuiting can improve performance if the bypassed expression is complex, or if it involves procedure calls.</span></span>  
  
 <span data-ttu-id="4134a-116">식 중 하나 또는 둘 다로 계산 되 면 `True`, `result` 은 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="4134a-116">If either or both expressions evaluate to `True`, `result` is `True`.</span></span> <span data-ttu-id="4134a-117">다음 표에서 설명 방법을 `result` 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4134a-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="4134a-118">경우 `expression1` 은</span><span class="sxs-lookup"><span data-stu-id="4134a-118">If `expression1` is</span></span>|<span data-ttu-id="4134a-119">및 `expression2` 은</span><span class="sxs-lookup"><span data-stu-id="4134a-119">And `expression2` is</span></span>|<span data-ttu-id="4134a-120">값 `result` 은</span><span class="sxs-lookup"><span data-stu-id="4134a-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|<span data-ttu-id="4134a-121">(계산 되지 않음)</span><span class="sxs-lookup"><span data-stu-id="4134a-121">(not evaluated)</span></span>|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a><span data-ttu-id="4134a-122">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4134a-122">Data Types</span></span>  
 <span data-ttu-id="4134a-123">`OrElse` 연산자에 대해서만 정의 되는 [Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4134a-123">The `OrElse` operator is defined only for the [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md).</span></span> <span data-ttu-id="4134a-124">Visual Basic로 필요에 따라 각 피연산자를 변환 `Boolean` 에서 모든 작업을 수행 하 고 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="4134a-124">Visual Basic converts each operand as necessary to `Boolean` and performs the operation entirely in `Boolean`.</span></span> <span data-ttu-id="4134a-125">Visual Basic에서 변환 하는 숫자 형식으로 결과 할당 하는 경우 `Boolean` 해당 형식으로.</span><span class="sxs-lookup"><span data-stu-id="4134a-125">If you assign the result to a numeric type, Visual Basic converts it from `Boolean` to that type.</span></span> <span data-ttu-id="4134a-126">이 예기치 않은 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4134a-126">This could produce unexpected behavior.</span></span> <span data-ttu-id="4134a-127">예를 들어 `5 OrElse 12` 으로 인해 `–1` 변환할 때 `Integer`합니다.</span><span class="sxs-lookup"><span data-stu-id="4134a-127">For example, `5 OrElse 12` results in `–1` when converted to `Integer`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="4134a-128">오버로딩</span><span class="sxs-lookup"><span data-stu-id="4134a-128">Overloading</span></span>  
 <span data-ttu-id="4134a-129">[또는 연산자](../../../visual-basic/language-reference/operators/or-operator.md) 및 [IsTrue 연산자](../../../visual-basic/language-reference/operators/istrue-operator.md) 수 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스의 형식 또는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="4134a-129">The [Or Operator](../../../visual-basic/language-reference/operators/or-operator.md) and the [IsTrue Operator](../../../visual-basic/language-reference/operators/istrue-operator.md) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="4134a-130">오버 로드는 `Or` 및 `IsTrue` 연산자의 동작에 영향을 줍니다는 `OrElse` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="4134a-130">Overloading the `Or` and `IsTrue` operators affects the behavior of the `OrElse` operator.</span></span> <span data-ttu-id="4134a-131">코드에서 `OrElse` 클래스 또는 구조체에 오버 로드에서 `Or` 및 `IsTrue`, 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4134a-131">If your code uses `OrElse` on a class or structure that overloads `Or` and `IsTrue`, be sure you understand their redefined behavior.</span></span> <span data-ttu-id="4134a-132">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4134a-132">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4134a-133">예제</span><span class="sxs-lookup"><span data-stu-id="4134a-133">Example</span></span>  
 <span data-ttu-id="4134a-134">다음 예제에서는 `OrElse` 두 식에 논리 분리를 수행 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="4134a-134">The following example uses the `OrElse` operator to perform logical disjunction on two expressions.</span></span> <span data-ttu-id="4134a-135">결과는 `Boolean` 값을 나타내는 두 식 중 하나가 true 인지 여부를 합니다.</span><span class="sxs-lookup"><span data-stu-id="4134a-135">The result is a `Boolean` value that represents whether either of the two expressions is true.</span></span> <span data-ttu-id="4134a-136">첫 번째 식이 `True`, 두 번째는 평가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4134a-136">If the first expression is `True`, the second is not evaluated.</span></span>  
  
 [!code-vb[VbVbalrOperators#37](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/orelse-operator_1.vb)]  
  
 <span data-ttu-id="4134a-137">앞 예제의 결과는 `True`, `True`, 및 `False` 각각.</span><span class="sxs-lookup"><span data-stu-id="4134a-137">The preceding example produces results of `True`, `True`, and `False` respectively.</span></span> <span data-ttu-id="4134a-138">계산에 `firstCheck`, 첫 번째는 이미 때문에 두 번째 식을 계산 하지는 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="4134a-138">In the calculation of `firstCheck`, the second expression is not evaluated because the first is already `True`.</span></span> <span data-ttu-id="4134a-139">계산의 두 번째 식이 계산 되는 반면 `secondCheck`합니다.</span><span class="sxs-lookup"><span data-stu-id="4134a-139">However, the second expression is evaluated in the calculation of `secondCheck`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4134a-140">예제</span><span class="sxs-lookup"><span data-stu-id="4134a-140">Example</span></span>  
 <span data-ttu-id="4134a-141">다음 예제와 `If`... `Then` 두 프로시저 호출을 포함 하는 문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4134a-141">The following example shows an `If`...`Then` statement containing two procedure calls.</span></span> <span data-ttu-id="4134a-142">첫 번째 호출에서 반환 하는 경우 `True`, 두 번째 절차는 호출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4134a-142">If the first call returns `True`, the second procedure is not called.</span></span> <span data-ttu-id="4134a-143">이렇게 하면 두 번째 절차는이 섹션의 코드를 실행할 때 항상 수행 해야 하는 중요 한 작업을 수행 하는 경우 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4134a-143">This could produce unexpected results if the second procedure performs important tasks that should always be performed when this section of the code runs.</span></span>  
  
 [!code-vb[VbVbalrOperators#38](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/orelse-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4134a-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4134a-144">See Also</span></span>  
 [<span data-ttu-id="4134a-145">논리/비트 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4134a-145">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="4134a-146">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="4134a-146">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="4134a-147">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="4134a-147">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="4134a-148">Or 연산자</span><span class="sxs-lookup"><span data-stu-id="4134a-148">Or Operator</span></span>](../../../visual-basic/language-reference/operators/or-operator.md)  
 [<span data-ttu-id="4134a-149">IsTrue 연산자</span><span class="sxs-lookup"><span data-stu-id="4134a-149">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [<span data-ttu-id="4134a-150">Visual Basic의 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="4134a-150">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
