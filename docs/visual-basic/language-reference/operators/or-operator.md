---
title: "Or 연산자(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Or
helpviewer_keywords:
- Or operator [Visual Basic]
- operators [Visual Basic], bitwise
- inclusive Or operator [Visual Basic]
- bitwise operators [Visual Basic], OR operator
- Or keyword [Visual Basic]
- operators [Visual Basic], inclusive or
- operators [Visual Basic], disjunction
- bitwise comparison [Visual Basic]
- logical disjunction
- disjunction operator [Visual Basic]
ms.assetid: 41ed6905-bf3d-468a-9e3b-03c10d461891
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4c9429eb2bdeb86bfa73786433231fdc22a230d9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="or-operator-visual-basic"></a><span data-ttu-id="a06cf-102">Or 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a06cf-102">Or Operator (Visual Basic)</span></span>
<span data-ttu-id="a06cf-103">에 두 논리 분리를 수행 `Boolean` 식 또는 두 숫자 식에 비트 분리 합니다.</span><span class="sxs-lookup"><span data-stu-id="a06cf-103">Performs a logical disjunction on two `Boolean` expressions, or a bitwise disjunction on two numeric expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a06cf-104">구문</span><span class="sxs-lookup"><span data-stu-id="a06cf-104">Syntax</span></span>  
  
```  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="a06cf-105">요소</span><span class="sxs-lookup"><span data-stu-id="a06cf-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="a06cf-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a06cf-106">Required.</span></span> <span data-ttu-id="a06cf-107">모든 `Boolean` 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a06cf-107">Any `Boolean` or numeric expression.</span></span> <span data-ttu-id="a06cf-108">에 대 한 `Boolean` 반면 `result` 은 2의 포함 논리합 `Boolean` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a06cf-108">For `Boolean` comparison, `result` is the inclusive logical disjunction of two `Boolean` values.</span></span> <span data-ttu-id="a06cf-109">비트 연산에 대 한 `result` 는 두 개의 숫자 비트 패턴의 비트 포함 논리합을 나타내는 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a06cf-109">For bitwise operations, `result` is a numeric value representing the inclusive bitwise disjunction of two numeric bit patterns.</span></span>  
  
 `expression1`  
 <span data-ttu-id="a06cf-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a06cf-110">Required.</span></span> <span data-ttu-id="a06cf-111">모든 `Boolean` 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a06cf-111">Any `Boolean` or numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="a06cf-112">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a06cf-112">Required.</span></span> <span data-ttu-id="a06cf-113">모든 `Boolean` 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a06cf-113">Any `Boolean` or numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a06cf-114">설명</span><span class="sxs-lookup"><span data-stu-id="a06cf-114">Remarks</span></span>  
 <span data-ttu-id="a06cf-115">에 대 한 `Boolean` 반면 `result` 은 `False` 두 경우에 `expression1` 및 `expression2` 로 평가 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="a06cf-115">For `Boolean` comparison, `result` is `False` if and only if both `expression1` and `expression2` evaluate to `False`.</span></span> <span data-ttu-id="a06cf-116">다음 표에서 설명 방법을 `result` 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a06cf-116">The following table illustrates how `result` is determined.</span></span>  
  
|<span data-ttu-id="a06cf-117">경우 `expression1` 은</span><span class="sxs-lookup"><span data-stu-id="a06cf-117">If `expression1` is</span></span>|<span data-ttu-id="a06cf-118">및 `expression2` 은</span><span class="sxs-lookup"><span data-stu-id="a06cf-118">And `expression2` is</span></span>|<span data-ttu-id="a06cf-119">값 `result` 은</span><span class="sxs-lookup"><span data-stu-id="a06cf-119">The value of `result` is</span></span>|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  <span data-ttu-id="a06cf-120">에 `Boolean` 비교는 `Or` 연산자는 항상 프로시저 호출을 포함할 수 있는 두 식을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="a06cf-120">In a `Boolean` comparison, the `Or` operator always evaluates both expressions, which could include making procedure calls.</span></span> <span data-ttu-id="a06cf-121">[OrElse 연산자](../../../visual-basic/language-reference/operators/orelse-operator.md) 수행 *단락 (short-circuiting)*, 즉 `expression1` 은 `True`, 다음 `expression2` 평가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a06cf-121">The [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) performs *short-circuiting*, which means that if `expression1` is `True`, then `expression2` is not evaluated.</span></span>  
  
 <span data-ttu-id="a06cf-122">비트 연산에 대 한는 `Or` 연산자 두 숫자 식의 동일한 위치의 비트 비트 비교를 수행 하 고 해당 비트를 설정 `result` 다음 표에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="a06cf-122">For bitwise operations, the `Or` operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in `result` according to the following table.</span></span>  
  
|<span data-ttu-id="a06cf-123">경우에 비트 `expression1` 은</span><span class="sxs-lookup"><span data-stu-id="a06cf-123">If bit in `expression1` is</span></span>|<span data-ttu-id="a06cf-124">비트 `expression2` 은</span><span class="sxs-lookup"><span data-stu-id="a06cf-124">And bit in `expression2` is</span></span>|<span data-ttu-id="a06cf-125">에 있는 비트 `result` 은</span><span class="sxs-lookup"><span data-stu-id="a06cf-125">The bit in `result` is</span></span>|  
|--------------------------------|---------------------------------|----------------------------|  
|<span data-ttu-id="a06cf-126">1</span><span class="sxs-lookup"><span data-stu-id="a06cf-126">1</span></span>|<span data-ttu-id="a06cf-127">1</span><span class="sxs-lookup"><span data-stu-id="a06cf-127">1</span></span>|<span data-ttu-id="a06cf-128">1</span><span class="sxs-lookup"><span data-stu-id="a06cf-128">1</span></span>|  
|<span data-ttu-id="a06cf-129">1</span><span class="sxs-lookup"><span data-stu-id="a06cf-129">1</span></span>|<span data-ttu-id="a06cf-130">0</span><span class="sxs-lookup"><span data-stu-id="a06cf-130">0</span></span>|<span data-ttu-id="a06cf-131">1</span><span class="sxs-lookup"><span data-stu-id="a06cf-131">1</span></span>|  
|<span data-ttu-id="a06cf-132">0</span><span class="sxs-lookup"><span data-stu-id="a06cf-132">0</span></span>|<span data-ttu-id="a06cf-133">1</span><span class="sxs-lookup"><span data-stu-id="a06cf-133">1</span></span>|<span data-ttu-id="a06cf-134">1</span><span class="sxs-lookup"><span data-stu-id="a06cf-134">1</span></span>|  
|<span data-ttu-id="a06cf-135">0</span><span class="sxs-lookup"><span data-stu-id="a06cf-135">0</span></span>|<span data-ttu-id="a06cf-136">0</span><span class="sxs-lookup"><span data-stu-id="a06cf-136">0</span></span>|<span data-ttu-id="a06cf-137">0</span><span class="sxs-lookup"><span data-stu-id="a06cf-137">0</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="a06cf-138">논리 및 비트 연산자는 산술 및 관계형 연산자 보다 우선 순위가, 모든 비트 연산은 정확 하 게 실행 되도록 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a06cf-138">Since the logical and bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="a06cf-139">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a06cf-139">Data Types</span></span>  
 <span data-ttu-id="a06cf-140">피연산자 중 하나의 구성 하는 경우 `Boolean` Visual Basic 변환 식과 하나의 숫자 식의 `Boolean` 식을 숫자 값 (-1에 대 한 `True` 하 고 0을 `False`) 연산을 수행 하 고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a06cf-140">If the operands consist of one `Boolean` expression and one numeric expression, Visual Basic converts the `Boolean` expression to a numeric value (–1 for `True` and 0 for `False`) and performs a bitwise operation.</span></span>  
  
 <span data-ttu-id="a06cf-141">에 대 한는 `Boolean` 비교 데이터의 결과 형식이 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="a06cf-141">For a `Boolean` comparison, the data type of the result is `Boolean`.</span></span> <span data-ttu-id="a06cf-142">비트 비교 결과 데이터 형식은의 데이터 형식에 대 한 적합 한 숫자 형식 `expression1` 및 `expression2`합니다.</span><span class="sxs-lookup"><span data-stu-id="a06cf-142">For a bitwise comparison, the result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="a06cf-143">"관계 및 비트 비교" 표를 참조 [연산자 결과의 데이터 형식을](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a06cf-143">See the "Relational and Bitwise Comparisons" table in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="a06cf-144">오버로딩</span><span class="sxs-lookup"><span data-stu-id="a06cf-144">Overloading</span></span>  
 <span data-ttu-id="a06cf-145">`Or` 연산자 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a06cf-145">The `Or` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="a06cf-146">이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a06cf-146">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="a06cf-147">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a06cf-147">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a06cf-148">예제</span><span class="sxs-lookup"><span data-stu-id="a06cf-148">Example</span></span>  
 <span data-ttu-id="a06cf-149">다음 예제에서는 `Or` 두 식에 포함 논리합 연산을 수행 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="a06cf-149">The following example uses the `Or` operator to perform an inclusive logical disjunction on two expressions.</span></span> <span data-ttu-id="a06cf-150">결과는 `Boolean` 를 나타내는 값은 두 식 중 하나가 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="a06cf-150">The result is a `Boolean` value that represents whether either of the two expressions is `True`.</span></span>  
  
 [!code-vb[VbVbalrOperators#35](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/or-operator_1.vb)]  
  
 <span data-ttu-id="a06cf-151">앞 예제의 결과는 `True`, `True`, 및 `False`각각.</span><span class="sxs-lookup"><span data-stu-id="a06cf-151">The preceding example produces results of `True`, `True`, and `False`, respectively.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a06cf-152">예제</span><span class="sxs-lookup"><span data-stu-id="a06cf-152">Example</span></span>  
 <span data-ttu-id="a06cf-153">다음 예제에서는 `Or` 포함 논리합 두 숫자 식의 개별 비트를 수행 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="a06cf-153">The following example uses the `Or` operator to perform inclusive logical disjunction on the individual bits of two numeric expressions.</span></span> <span data-ttu-id="a06cf-154">피연산자의 해당 비트 중 하나가 1로 설정 되어 있으면 결과 패턴의 비트가 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a06cf-154">The bit in the result pattern is set if either of the corresponding bits in the operands is set to 1.</span></span>  
  
 [!code-vb[VbVbalrOperators#36](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/or-operator_2.vb)]  
  
 <span data-ttu-id="a06cf-155">앞의 예제는 각각 10, 14, 및 14의 결과 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a06cf-155">The preceding example produces results of 10, 14, and 14, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a06cf-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a06cf-156">See Also</span></span>  
 [<span data-ttu-id="a06cf-157">논리/비트 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a06cf-157">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="a06cf-158">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="a06cf-158">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="a06cf-159">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="a06cf-159">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="a06cf-160">OrElse 연산자</span><span class="sxs-lookup"><span data-stu-id="a06cf-160">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)  
 [<span data-ttu-id="a06cf-161">Visual Basic의 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="a06cf-161">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
