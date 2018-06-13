---
title: And 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.And
helpviewer_keywords:
- operators [Visual Basic], bitwise
- logical conjunction
- bitwise AND operator [Visual Basic]
- conjunction operator [Visual Basic]
- And operator [Visual Basic]
- bitwise operators [Visual Basic], AND operator
- operators [Visual Basic], conjunction
- bitwise comparison [Visual Basic]
ms.assetid: 2ea711f3-439a-4c7c-9e3a-1ffe3b0d6046
ms.openlocfilehash: e14dfd8ba200598084cad04d1faa05f3561f8dab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604645"
---
# <a name="and-operator-visual-basic"></a><span data-ttu-id="c8424-102">And 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8424-102">And Operator (Visual Basic)</span></span>
<span data-ttu-id="c8424-103">두 개의에 논리 결합을 수행 `Boolean` 식 또는 두 숫자 식에 비트 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8424-103">Performs a logical conjunction on two `Boolean` expressions, or a bitwise conjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8424-104">구문</span><span class="sxs-lookup"><span data-stu-id="c8424-104">Syntax</span></span>  
  
```  
result = expression1 And expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="c8424-105">요소</span><span class="sxs-lookup"><span data-stu-id="c8424-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="c8424-106">필수.</span><span class="sxs-lookup"><span data-stu-id="c8424-106">Required.</span></span> <span data-ttu-id="c8424-107">모든 `Boolean` 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c8424-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="c8424-108">부울 비교 `result` 는 두 논리 결합 `Boolean` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c8424-108">For Boolean comparison, `result` is the logical conjunction of two `Boolean` values.</span></span> <span data-ttu-id="c8424-109">비트 연산에 대 한 `result` 는 두 개의 숫자 비트 패턴의 비트 결합을 나타내는 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c8424-109">For bitwise operations, `result` is a numeric value representing the bitwise conjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="c8424-110">필수.</span><span class="sxs-lookup"><span data-stu-id="c8424-110">Required.</span></span> <span data-ttu-id="c8424-111">모든 `Boolean` 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c8424-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="c8424-112">필수.</span><span class="sxs-lookup"><span data-stu-id="c8424-112">Required.</span></span> <span data-ttu-id="c8424-113">모든 `Boolean` 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c8424-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8424-114">설명</span><span class="sxs-lookup"><span data-stu-id="c8424-114">Remarks</span></span>  
 <span data-ttu-id="c8424-115">부울 비교 `result` 은 `True` 두 경우에 `expression1` 및 `expression2` 로 평가 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="c8424-115">For Boolean comparison, `result` is `True` if and only if both `expression1` and `expression2` evaluate to `True`.</span></span> <span data-ttu-id="c8424-116">다음 표에서 설명 방법을 `result` 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8424-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="c8424-117">경우 `expression1` 은</span><span class="sxs-lookup"><span data-stu-id="c8424-117">If `expression1` is</span></span>|<span data-ttu-id="c8424-118">및 `expression2` 은</span><span class="sxs-lookup"><span data-stu-id="c8424-118">And `expression2` is</span></span>|<span data-ttu-id="c8424-119">값 `result` 은</span><span class="sxs-lookup"><span data-stu-id="c8424-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  <span data-ttu-id="c8424-120">부울 비교에는 `And` 연산자는 항상 프로시저 호출을 포함할 수 있는 두 식을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8424-120">In a Boolean comparison, the `And` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="c8424-121">[AndAlso 연산자](../../../visual-basic/language-reference/operators/andalso-operator.md) 수행 *단락 (short-circuiting)*, 즉 `expression1` 은 `False`, 다음 `expression2` 평가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8424-121">The [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) performs *short-circuiting*, which means that if `expression1` is `False`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="c8424-122">숫자 값에 적용할 경우의 `And` 연산자 두 숫자 식의 동일한 위치의 비트 비트 비교를 수행 하 고 해당 비트를 설정 `result` 다음 표에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8424-122">When applied to numeric values, the `And` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="c8424-123">경우에 비트 `expression1` 은</span><span class="sxs-lookup"><span data-stu-id="c8424-123">If bit in `expression1` is</span></span>|<span data-ttu-id="c8424-124">비트 `expression2` 은</span><span class="sxs-lookup"><span data-stu-id="c8424-124">And bit in `expression2` is</span></span>|<span data-ttu-id="c8424-125">에 있는 비트 `result` 은</span><span class="sxs-lookup"><span data-stu-id="c8424-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="c8424-126">1</span><span class="sxs-lookup"><span data-stu-id="c8424-126">1</span></span>|<span data-ttu-id="c8424-127">1</span><span class="sxs-lookup"><span data-stu-id="c8424-127">1</span></span>|<span data-ttu-id="c8424-128">1</span><span class="sxs-lookup"><span data-stu-id="c8424-128">1</span></span>|  
|<span data-ttu-id="c8424-129">1</span><span class="sxs-lookup"><span data-stu-id="c8424-129">1</span></span>|<span data-ttu-id="c8424-130">0</span><span class="sxs-lookup"><span data-stu-id="c8424-130">0</span></span>|<span data-ttu-id="c8424-131">0</span><span class="sxs-lookup"><span data-stu-id="c8424-131">0</span></span>|  
|<span data-ttu-id="c8424-132">0</span><span class="sxs-lookup"><span data-stu-id="c8424-132">0</span></span>|<span data-ttu-id="c8424-133">1</span><span class="sxs-lookup"><span data-stu-id="c8424-133">1</span></span>|<span data-ttu-id="c8424-134">0</span><span class="sxs-lookup"><span data-stu-id="c8424-134">0</span></span>|  
|<span data-ttu-id="c8424-135">0</span><span class="sxs-lookup"><span data-stu-id="c8424-135">0</span></span>|<span data-ttu-id="c8424-136">0</span><span class="sxs-lookup"><span data-stu-id="c8424-136">0</span></span>|<span data-ttu-id="c8424-137">0</span><span class="sxs-lookup"><span data-stu-id="c8424-137">0</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="c8424-138">논리 및 비트 연산자는 산술 및 관계형 연산자 보다 우선 순위가, 모든 비트 연산은 정확한 결과를 얻으려면 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8424-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate results.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="c8424-139">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c8424-139">Data Types</span></span>  
 <span data-ttu-id="c8424-140">피연산자 중 하나의 구성 하는 경우 `Boolean` Visual Basic 변환 식과 하나의 숫자 식의 `Boolean` 식을 숫자 값 (-1에 대 한 `True` 하 고 0을 `False`) 연산을 수행 하 고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8424-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="c8424-141">부울 비교에 대 한 데이터의 결과 형식이 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="c8424-141">For a Boolean comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="c8424-142">비트 비교 결과 데이터 형식은의 데이터 형식에 대 한 적합 한 숫자 형식 `expression1` 및 `expression2`합니다.</span><span class="sxs-lookup"><span data-stu-id="c8424-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="c8424-143">"관계 및 비트 비교" 표를 참조 [연산자 결과의 데이터 형식을](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c8424-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8424-144">`And` 연산자 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c8424-144">The `And` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="c8424-145">이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8424-145">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="c8424-146">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c8424-146">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8424-147">예제</span><span class="sxs-lookup"><span data-stu-id="c8424-147">Example</span></span>  
 <span data-ttu-id="c8424-148">다음 예제에서는 `And` 두 식에 논리 결합을 수행 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="c8424-148">The following example uses the `And` operator to perform a logical conjunction on two expressions.</span></span> <span data-ttu-id="c8424-149">결과 한 `Boolean` 두 식이 모두 되는지 여부를 나타내는 값 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="c8424-149">The result is a `Boolean` value that represents whether both of the expressions are `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-operator_1.vb)]  
  
 <span data-ttu-id="c8424-150">앞 예제의 결과는 `True` 및 `False`각각.</span><span class="sxs-lookup"><span data-stu-id="c8424-150">The preceding example produces results of `True` and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8424-151">예제</span><span class="sxs-lookup"><span data-stu-id="c8424-151">Example</span></span>  
 <span data-ttu-id="c8424-152">다음 예제에서는 `And` 두 숫자 식의 개별 비트에 논리 결합을 수행 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="c8424-152">The following example uses the `And` operator to perform logical conjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="c8424-153">피연산자의 해당 비트가 모두 1로 설정 된 경우 결과 패턴의 비트가 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8424-153">The bit in the result pattern is set if the corresponding bits in the operands are both set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-operator_2.vb)]  
  
 <span data-ttu-id="c8424-154">앞의 예제는 각각 8, 2 및 0의 결과 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c8424-154">The preceding example produces results of 8, 2, and 0, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8424-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c8424-155">See Also</span></span>  
 [<span data-ttu-id="c8424-156">논리/비트 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8424-156">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="c8424-157">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="c8424-157">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="c8424-158">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="c8424-158">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="c8424-159">AndAlso 연산자</span><span class="sxs-lookup"><span data-stu-id="c8424-159">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)  
 [<span data-ttu-id="c8424-160">Visual Basic의 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="c8424-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
