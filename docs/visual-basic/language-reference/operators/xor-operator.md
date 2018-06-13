---
title: 배타적 or 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Xor
helpviewer_keywords:
- exclusive OR operator [Visual Basic]
- logical exclusion
- operators [Visual Basic], exclusive or
- exclusion operator [Visual Basic]
- operators [Visual Basic], bitwise
- bitwise operators [Visual Basic], XOR operator
- Xor operator [Visual Basic]
- Xor keyword [Visual Basic]
- bitwise comparison [Visual Basic]
ms.assetid: 036000a9-3934-4e7f-a9d0-a816de3d84a6
ms.openlocfilehash: 34d317da5d85127e371c2df7229e0f0873972f50
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604798"
---
# <a name="xor-operator-visual-basic"></a><span data-ttu-id="0132b-102">배타적 or 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0132b-102">Xor Operator (Visual Basic)</span></span>
<span data-ttu-id="0132b-103">에 두 논리 제외를 수행 `Boolean` 식 또는 두 숫자 식에 비트 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="0132b-103">Performs a logical exclusion on two `Boolean` expressions, or a bitwise exclusion on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0132b-104">구문</span><span class="sxs-lookup"><span data-stu-id="0132b-104">Syntax</span></span>  
  
```  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="0132b-105">요소</span><span class="sxs-lookup"><span data-stu-id="0132b-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="0132b-106">필수.</span><span class="sxs-lookup"><span data-stu-id="0132b-106">Required.</span></span> <span data-ttu-id="0132b-107">모든 `Boolean` 또는 숫자 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="0132b-107">Any `Boolean` or numeric variable.</span></span> <span data-ttu-id="0132b-108">부울 비교 `result` 는 두 논리 제외 (배타적 논리합) `Boolean` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0132b-108">For Boolean comparison, `result` is the logical exclusion (exclusive logical disjunction) of two `Boolean` values.</span></span> <span data-ttu-id="0132b-109">비트 연산에 대 한 `result` 는 두 개의 숫자 비트 패턴의 배타적 비트 연산 (배타적 비트 논리합)를 나타내는 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0132b-109">For bitwise operations, `result` is a numeric value that represents the bitwise exclusion (exclusive bitwise disjunction) of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="0132b-110">필수.</span><span class="sxs-lookup"><span data-stu-id="0132b-110">Required.</span></span> <span data-ttu-id="0132b-111">모든 `Boolean` 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="0132b-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="0132b-112">필수.</span><span class="sxs-lookup"><span data-stu-id="0132b-112">Required.</span></span> <span data-ttu-id="0132b-113">모든 `Boolean` 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="0132b-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0132b-114">설명</span><span class="sxs-lookup"><span data-stu-id="0132b-114">Remarks</span></span>  
 <span data-ttu-id="0132b-115">부울 비교 `result` 은 `True` 경우에 중 하나만 `expression1` 및 `expression2` 계산 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="0132b-115">For Boolean comparison, `result` is `True` if and only if exactly one of `expression1` and `expression2` evaluates to `True`.</span></span> <span data-ttu-id="0132b-116">즉, 경우에 `expression1` 및 `expression2` 평가 반대 `Boolean` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0132b-116">That is, if and only if `expression1` and `expression2` evaluate to opposite `Boolean` values.</span></span> <span data-ttu-id="0132b-117">다음 표에서 설명 방법을 `result` 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0132b-117">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="0132b-118">경우 `expression1` 은</span><span class="sxs-lookup"><span data-stu-id="0132b-118">If `expression1` is</span></span>|<span data-ttu-id="0132b-119">및 `expression2` 은</span><span class="sxs-lookup"><span data-stu-id="0132b-119">And `expression2` is</span></span>|<span data-ttu-id="0132b-120">값 `result` 은</span><span class="sxs-lookup"><span data-stu-id="0132b-120">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  <span data-ttu-id="0132b-121">부울 비교에는 `Xor` 연산자는 항상 프로시저 호출을 포함할 수 있는 두 식을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="0132b-121">In a Boolean comparison, the `Xor` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="0132b-122">에 해당 하는 단락 항목이 `Xor`, 결과 항상 두 피연산자 모두에 종속 되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="0132b-122">There is no short-circuiting counterpart to `Xor`, because the result always depends on both operands.</span></span> <span data-ttu-id="0132b-123">에 대 한 *단락 (short-circuiting)* 논리 연산자 참조 [AndAlso 연산자](../../../visual-basic/language-reference/operators/andalso-operator.md) 및 [OrElse 연산자](../../../visual-basic/language-reference/operators/orelse-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0132b-123">For *short-circuiting* logical operators, see [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) and [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>  
  
 <span data-ttu-id="0132b-124">비트 연산에 대 한는 `Xor` 연산자 두 숫자 식의 동일한 위치의 비트 비트 비교를 수행 하 고 해당 비트를 설정 `result` 다음 표에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="0132b-124">For bitwise operations, the `Xor` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="0132b-125">경우에 비트 `expression1` 은</span><span class="sxs-lookup"><span data-stu-id="0132b-125">If bit in `expression1` is</span></span>|<span data-ttu-id="0132b-126">비트 `expression2` 은</span><span class="sxs-lookup"><span data-stu-id="0132b-126">And bit in `expression2` is</span></span>|<span data-ttu-id="0132b-127">에 있는 비트 `result` 은</span><span class="sxs-lookup"><span data-stu-id="0132b-127">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="0132b-128">1</span><span class="sxs-lookup"><span data-stu-id="0132b-128">1</span></span>|<span data-ttu-id="0132b-129">1</span><span class="sxs-lookup"><span data-stu-id="0132b-129">1</span></span>|<span data-ttu-id="0132b-130">0</span><span class="sxs-lookup"><span data-stu-id="0132b-130">0</span></span>|  
|<span data-ttu-id="0132b-131">1</span><span class="sxs-lookup"><span data-stu-id="0132b-131">1</span></span>|<span data-ttu-id="0132b-132">0</span><span class="sxs-lookup"><span data-stu-id="0132b-132">0</span></span>|<span data-ttu-id="0132b-133">1</span><span class="sxs-lookup"><span data-stu-id="0132b-133">1</span></span>|  
|<span data-ttu-id="0132b-134">0</span><span class="sxs-lookup"><span data-stu-id="0132b-134">0</span></span>|<span data-ttu-id="0132b-135">1</span><span class="sxs-lookup"><span data-stu-id="0132b-135">1</span></span>|<span data-ttu-id="0132b-136">1</span><span class="sxs-lookup"><span data-stu-id="0132b-136">1</span></span>|  
|<span data-ttu-id="0132b-137">0</span><span class="sxs-lookup"><span data-stu-id="0132b-137">0</span></span>|<span data-ttu-id="0132b-138">0</span><span class="sxs-lookup"><span data-stu-id="0132b-138">0</span></span>|<span data-ttu-id="0132b-139">0</span><span class="sxs-lookup"><span data-stu-id="0132b-139">0</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="0132b-140">논리 및 비트 연산자는 산술 및 관계형 연산자 보다 우선 순위가, 모든 비트 연산은 정확 하 게 실행 되도록 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0132b-140">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
 <span data-ttu-id="0132b-141">예를 들어 5 `Xor` 3은 6입니다.</span><span class="sxs-lookup"><span data-stu-id="0132b-141">For example, 5 `Xor` 3 is 6.</span></span> <span data-ttu-id="0132b-142">그 이유를 확인 하려면, 101 및 011 해당 이진 표현으로 5와 3을 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0132b-142">To see why this is so, convert 5 and 3 to their binary representations, 101 and 011.</span></span> <span data-ttu-id="0132b-143">그런 다음 인지 확인할 수 101 Xor 011 110 6 10 진수 숫자의 이진 표현 되는 이전 표를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0132b-143">Then use the previous table to determine that 101 Xor 011 is 110, which is the binary representation of the decimal number 6.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="0132b-144">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="0132b-144">Data Types</span></span>  
 <span data-ttu-id="0132b-145">피연산자 중 하나의 구성 하는 경우 `Boolean` Visual Basic 변환 식과 하나의 숫자 식의 `Boolean` 식을 숫자 값 (-1에 대 한 `True` 하 고 0을 `False`) 연산을 수행 하 고 합니다.</span><span class="sxs-lookup"><span data-stu-id="0132b-145">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="0132b-146">에 대 한는 `Boolean` 비교 데이터의 결과 형식이 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="0132b-146">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="0132b-147">비트 비교 결과 데이터 형식은의 데이터 형식에 대 한 적합 한 숫자 형식 `expression1` 및 `expression2`합니다.</span><span class="sxs-lookup"><span data-stu-id="0132b-147">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="0132b-148">"관계 및 비트 비교" 표를 참조 [연산자 결과의 데이터 형식을](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0132b-148">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="0132b-149">오버로딩</span><span class="sxs-lookup"><span data-stu-id="0132b-149">Overloading</span></span>  
 <span data-ttu-id="0132b-150">`Xor` 연산자 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0132b-150">The `Xor` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="0132b-151">이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0132b-151">If your code uses this operator on such a class or structure, make sure you understand its redefined behavior.</span></span> <span data-ttu-id="0132b-152">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0132b-152">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0132b-153">예제</span><span class="sxs-lookup"><span data-stu-id="0132b-153">Example</span></span>  
 <span data-ttu-id="0132b-154">다음 예제에서는 `Xor` 두 식에 논리 제외 (배타적 논리합)를 수행 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="0132b-154">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on two expressions.</span></span> <span data-ttu-id="0132b-155">결과 한 `Boolean` 식 중 정확히 하나 인지 여부를 나타내는 값 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="0132b-155">The result is a `Boolean` value that represents whether exactly one of the expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#40](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xor-operator_1.vb)]  
  
 <span data-ttu-id="0132b-156">이전 예제의 결과는 `False`, `True`, 및 `False`각각.</span><span class="sxs-lookup"><span data-stu-id="0132b-156">The previous example produces results of `False`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0132b-157">예제</span><span class="sxs-lookup"><span data-stu-id="0132b-157">Example</span></span>  
 <span data-ttu-id="0132b-158">다음 예제에서는 `Xor` 두 숫자 식의 개별 비트에 논리 제외 (배타적 논리합)를 수행 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="0132b-158">The following example uses the `Xor` operator to perform logical exclusion (exclusive logical disjunction) on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="0132b-159">피연산자의 해당 비트 중 정확히 하나를 1로 설정 하는 경우 결과 패턴의 비트가 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0132b-159">The bit in the result pattern is set if exactly one of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#41](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xor-operator_2.vb)]  
  
 <span data-ttu-id="0132b-160">이전 예제의 결과는 2, 12, 및 14, 각각.</span><span class="sxs-lookup"><span data-stu-id="0132b-160">The previous example produces results of 2, 12, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0132b-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0132b-161">See Also</span></span>  
 [<span data-ttu-id="0132b-162">논리/비트 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0132b-162">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="0132b-163">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="0132b-163">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="0132b-164">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="0132b-164">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="0132b-165">Visual Basic의 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="0132b-165">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
