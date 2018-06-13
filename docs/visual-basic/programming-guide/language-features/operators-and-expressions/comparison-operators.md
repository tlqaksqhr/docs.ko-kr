---
title: Comparison Operators in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- comparison operators [Visual Basic], comparing strings
- comparison operators [Visual Basic], comparing objects
- strings [Visual Basic], comparing
- comparison operators [Visual Basic]
- string comparison [Visual Basic], operators
- objects [Visual Basic], comparing
- numbers [Visual Basic], comparing
- Visual Basic code, operators
- string comparison [Visual Basic]
- numeric values [Visual Basic], comparing
- comparison operators [Visual Basic], comparing numeric values
- operators [Visual Basic], comparison
ms.assetid: 0b570339-5407-474f-8421-e183a8b303ee
ms.openlocfilehash: 873ee31bf9c2ab195d66337d52e4a1bb7075ac76
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655144"
---
# <a name="comparison-operators-in-visual-basic"></a><span data-ttu-id="605cd-102">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="605cd-102">Comparison Operators in Visual Basic</span></span>
<span data-ttu-id="605cd-103">두 식을 비교 하 고 반환 하는 비교 연산자는 `Boolean` 값의 관계를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-103">Comparison operators compare two expressions and return a `Boolean` value that represents the relationship of their values.</span></span> <span data-ttu-id="605cd-104">숫자 값, 문자열, 비교 연산자 및 개체를 비교 연산자를 비교 하는 데는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-104">There are operators for comparing numeric values, operators for comparing strings, and operators for comparing objects.</span></span> <span data-ttu-id="605cd-105">세 가지 유형의 연산자를 모두 여기에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-105">All three types of operators are discussed herein.</span></span>  
  
## <a name="comparing-numeric-values"></a><span data-ttu-id="605cd-106">숫자 값 비교</span><span class="sxs-lookup"><span data-stu-id="605cd-106">Comparing Numeric Values</span></span>  
 <span data-ttu-id="605cd-107">Visual Basic 6 명의 숫자 비교 연산자를 사용 하 여 숫자 값을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-107">Visual Basic compares numeric values using six numeric comparison operators.</span></span> <span data-ttu-id="605cd-108">각 연산자는 숫자 값으로 계산 되는 두 식 피연산자 변수로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-108">Each operator takes as operands two expressions that evaluate to numeric values.</span></span> <span data-ttu-id="605cd-109">다음 표에서 연산자를 나열 하 고 각각의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-109">The following table lists the operators and shows examples of each.</span></span>  
  
|<span data-ttu-id="605cd-110">연산자</span><span class="sxs-lookup"><span data-stu-id="605cd-110">Operator</span></span>|<span data-ttu-id="605cd-111">테스트 조건</span><span class="sxs-lookup"><span data-stu-id="605cd-111">Condition tested</span></span>|<span data-ttu-id="605cd-112">예제</span><span class="sxs-lookup"><span data-stu-id="605cd-112">Examples</span></span>|  
|--------------|----------------------|--------------|  
|<span data-ttu-id="605cd-113">`=` (같음)</span><span class="sxs-lookup"><span data-stu-id="605cd-113">`=` (Equality)</span></span>|<span data-ttu-id="605cd-114">두 번째 값으로 첫 번째 식이 같음의 값은?</span><span class="sxs-lookup"><span data-stu-id="605cd-114">Is the value of the first expression equal to the value of the second?</span></span>|<span data-ttu-id="605cd-115">`23`   `=`   `33    ' False`</span><span class="sxs-lookup"><span data-stu-id="605cd-115">`23`   `=`   `33    ' False`</span></span><br /><br /> <span data-ttu-id="605cd-116">`23`   `=`   `23    ' True`</span><span class="sxs-lookup"><span data-stu-id="605cd-116">`23`   `=`   `23    ' True`</span></span><br /><br /> <span data-ttu-id="605cd-117">`23`   `=`   `12    ' False`</span><span class="sxs-lookup"><span data-stu-id="605cd-117">`23`   `=`   `12    ' False`</span></span>|  
|<span data-ttu-id="605cd-118">`<>` (같지 않음)</span><span class="sxs-lookup"><span data-stu-id="605cd-118">`<>` (Inequality)</span></span>|<span data-ttu-id="605cd-119">첫 번째 식의 값과 같지 않은 값의 두 번째?</span><span class="sxs-lookup"><span data-stu-id="605cd-119">Is the value of the first expression unequal to the value of the second?</span></span>|<span data-ttu-id="605cd-120">`23`   `<>`   `33    ' True`</span><span class="sxs-lookup"><span data-stu-id="605cd-120">`23`   `<>`   `33    ' True`</span></span><br /><br /> <span data-ttu-id="605cd-121">`23`   `<>`   `23    ' False`</span><span class="sxs-lookup"><span data-stu-id="605cd-121">`23`   `<>`   `23    ' False`</span></span><br /><br /> <span data-ttu-id="605cd-122">`23`   `<>`   `12    ' True`</span><span class="sxs-lookup"><span data-stu-id="605cd-122">`23`   `<>`   `12    ' True`</span></span>|  
|<span data-ttu-id="605cd-123">`<` (보다 작음)</span><span class="sxs-lookup"><span data-stu-id="605cd-123">`<` (Less than)</span></span>|<span data-ttu-id="605cd-124">첫 번째 식의 값 보다 작지의 두 번째 값은?</span><span class="sxs-lookup"><span data-stu-id="605cd-124">Is the value of the first expression less than the value of the second?</span></span>|<span data-ttu-id="605cd-125">`23`   `<`   `33    ' True`</span><span class="sxs-lookup"><span data-stu-id="605cd-125">`23`   `<`   `33    ' True`</span></span><br /><br /> <span data-ttu-id="605cd-126">`23`   `<`   `23    ' False`</span><span class="sxs-lookup"><span data-stu-id="605cd-126">`23`   `<`   `23    ' False`</span></span><br /><br /> <span data-ttu-id="605cd-127">`23`   `<`   `12    ' False`</span><span class="sxs-lookup"><span data-stu-id="605cd-127">`23`   `<`   `12    ' False`</span></span>|  
|<span data-ttu-id="605cd-128">`>` (보다 큼)</span><span class="sxs-lookup"><span data-stu-id="605cd-128">`>` (Greater than)</span></span>|<span data-ttu-id="605cd-129">첫 번째 식의 값이 두 번째 값 보다 크면?</span><span class="sxs-lookup"><span data-stu-id="605cd-129">Is the value of the first expression greater than the value of the second?</span></span>|<span data-ttu-id="605cd-130">`23`   `>`   `33    ' False`</span><span class="sxs-lookup"><span data-stu-id="605cd-130">`23`   `>`   `33    ' False`</span></span><br /><br /> <span data-ttu-id="605cd-131">`23`   `>`   `23    ' False`</span><span class="sxs-lookup"><span data-stu-id="605cd-131">`23`   `>`   `23    ' False`</span></span><br /><br /> <span data-ttu-id="605cd-132">`23`   `>`   `12    ' True`</span><span class="sxs-lookup"><span data-stu-id="605cd-132">`23`   `>`   `12    ' True`</span></span>|  
|<span data-ttu-id="605cd-133">`<=` (작거나 같음)</span><span class="sxs-lookup"><span data-stu-id="605cd-133">`<=` (Less than or equal to)</span></span>|<span data-ttu-id="605cd-134">두 번째 값 보다 작거나 같은 첫 번째 식의 값은?</span><span class="sxs-lookup"><span data-stu-id="605cd-134">Is the value of the first expression less than or equal to the value of the second?</span></span>|<span data-ttu-id="605cd-135">`23`   `<=`   `33    ' True`</span><span class="sxs-lookup"><span data-stu-id="605cd-135">`23`   `<=`   `33    ' True`</span></span><br /><br /> <span data-ttu-id="605cd-136">`23`   `<=`   `23    ' True`</span><span class="sxs-lookup"><span data-stu-id="605cd-136">`23`   `<=`   `23    ' True`</span></span><br /><br /> <span data-ttu-id="605cd-137">`23`   `<=`   `12    ' False`</span><span class="sxs-lookup"><span data-stu-id="605cd-137">`23`   `<=`   `12    ' False`</span></span>|  
|<span data-ttu-id="605cd-138">`>=` (보다 크거나 같음)</span><span class="sxs-lookup"><span data-stu-id="605cd-138">`>=` (Greater than or equal to)</span></span>|<span data-ttu-id="605cd-139">두 번째 값 보다 크거나 같은 경우 첫 번째 식의 값은?</span><span class="sxs-lookup"><span data-stu-id="605cd-139">Is the value of the first expression greater than or equal to the value of the second?</span></span>|<span data-ttu-id="605cd-140">`23`   `>=`   `33    ' False`</span><span class="sxs-lookup"><span data-stu-id="605cd-140">`23`   `>=`   `33    ' False`</span></span><br /><br /> <span data-ttu-id="605cd-141">`23`   `>=`   `23    ' True`</span><span class="sxs-lookup"><span data-stu-id="605cd-141">`23`   `>=`   `23    ' True`</span></span><br /><br /> <span data-ttu-id="605cd-142">`23`   `>=`   `12    ' True`</span><span class="sxs-lookup"><span data-stu-id="605cd-142">`23`   `>=`   `12    ' True`</span></span>|  
  
## <a name="comparing-strings"></a><span data-ttu-id="605cd-143">문자열 비교</span><span class="sxs-lookup"><span data-stu-id="605cd-143">Comparing Strings</span></span>  
 <span data-ttu-id="605cd-144">Visual Basic을 사용 하 여 문자열 비교는 [Like 연산자](../../../../visual-basic/language-reference/operators/like-operator.md) 숫자 비교 연산자 뿐 아니라 합니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-144">Visual Basic compares strings using the [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md) as well as the numeric comparison operators.</span></span> <span data-ttu-id="605cd-145">`Like` 연산자를 사용 하면 패턴을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-145">The `Like` operator allows you to specify a pattern.</span></span> <span data-ttu-id="605cd-146">문자열을 다음 패턴에 대해 비교 하 고, 일치 하는 경우 결과 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-146">The string is then compared against the pattern, and if it matches, the result is `True`.</span></span> <span data-ttu-id="605cd-147">그렇지 않으면 결과 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-147">Otherwise, the result is `False`.</span></span> <span data-ttu-id="605cd-148">숫자 연산자를 사용 하 여 비교할 수 `String` 다음 예제와 같이 정렬 순서에 따라 값입니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-148">The numeric operators allow you to compare `String` values based on their sort order, as the following example shows.</span></span>  
  
 `"73" < "9"`  
  
 `' The result of the preceding comparison is True.`  
  
 <span data-ttu-id="605cd-149">앞의 예제에서 결과 `True` 하므로 첫 번째 문자열의 첫 번째 문자는 두 번째 문자열의 첫 번째 문자 앞에 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-149">The result in the preceding example is `True` because the first character in the first string sorts before the first character in the second string.</span></span> <span data-ttu-id="605cd-150">첫 번째 문자가 같은 인 경우 비교는 두 문자열의 다음 문자가 계속 등에입니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-150">If the first characters were equal, the comparison would continue to the next character in both strings, and so on.</span></span> <span data-ttu-id="605cd-151">다음 예제와 같이 같음 연산자를 사용 하 여 문자열의 일치 여부를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-151">You can also test equality of strings using the equality operator, as the following example shows.</span></span>  
  
 `"734" = "734"`  
  
 `' The result of the preceding comparison is True.`  
  
 <span data-ttu-id="605cd-152">한 문자열 "aa" 및 "aaa"와 같은 다른 접두사의 형식이 더 긴 문자열 짧은 문자열 보다 큰 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-152">If one string is a prefix of another, such as "aa" and "aaa", the longer string is considered to be greater than the shorter string.</span></span> <span data-ttu-id="605cd-153">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-153">The following example illustrates this.</span></span>  
  
 `"aaa" > "aa"`  
  
 `' The result of the preceding comparison is True.`  
  
 <span data-ttu-id="605cd-154">정렬 순서는 이진 비교 또는의 설정에 따라 텍스트 비교를 기반으로 하며 `Option Compare`합니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-154">The sort order is based on either a binary comparison or a textual comparison depending on the setting of `Option Compare`.</span></span> <span data-ttu-id="605cd-155">자세한 내용은 참조 [옵션 비교 문](../../../../visual-basic/language-reference/statements/option-compare-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-155">For more information see [Option Compare Statement](../../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span>  
  
## <a name="comparing-objects"></a><span data-ttu-id="605cd-156">개체 비교</span><span class="sxs-lookup"><span data-stu-id="605cd-156">Comparing Objects</span></span>  
 <span data-ttu-id="605cd-157">Visual Basic 비교 된 두 개체 참조 변수는 [Is 연산자](../../../../visual-basic/language-reference/operators/is-operator.md) 및 [IsNot 연산자](../../../../visual-basic/language-reference/operators/isnot-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-157">Visual Basic compares two object reference variables with the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) and the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md).</span></span> <span data-ttu-id="605cd-158">동일한 개체 인스턴스를 두 개의 참조 변수 참조를 확인 하려면 이러한 연산자 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-158">You can use either of these operators to determine if two reference variables refer to the same object instance.</span></span> <span data-ttu-id="605cd-159">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-159">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#65](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_1.vb)]  
  
 <span data-ttu-id="605cd-160">앞의 예제에서 `x Is y` 계산 `True`두 변수가 같은 인스턴스를 참조 하므로, 합니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-160">In the preceding example, `x Is y` evaluates to `True`, because both variables refer to the same instance.</span></span> <span data-ttu-id="605cd-161">다음 예제로이 결과 대조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-161">Contrast this result with the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#66](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_2.vb)]  
  
 <span data-ttu-id="605cd-162">앞의 예제에서 `x Is y` 계산 `False`변수 동일한 유형의 개체를 참조 하지만 해당 형식의 다른 인스턴스를 참조 하기 때문에, 합니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-162">In the preceding example, `x Is y` evaluates to `False`, because although the variables refer to objects of the same type, they refer to different instances of that type.</span></span>  
  
 <span data-ttu-id="605cd-163">동일한 인스턴스를 가리키지 않는 두 개체에 대 한 테스트 하려는 경우는 `IsNot` 연산자를 사용 하면 문법적으로 어 색 하 게 조합 하지 않아도 `Not` 및 `Is`합니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-163">When you want to test for two objects not pointing to the same instance, the `IsNot` operator lets you avoid a grammatically clumsy combination of `Not` and `Is`.</span></span> <span data-ttu-id="605cd-164">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-164">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#67](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_3.vb)]  
  
 <span data-ttu-id="605cd-165">앞의 예제에서 `If a IsNot b` 같습니다 `If Not a Is b`합니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-165">In the preceding example, `If a IsNot b` is equivalent to `If Not a Is b`.</span></span>  
  
### <a name="comparing-object-type"></a><span data-ttu-id="605cd-166">개체 유형 비교</span><span class="sxs-lookup"><span data-stu-id="605cd-166">Comparing Object Type</span></span>  
 <span data-ttu-id="605cd-167">사용 하 여 특정 형식의 개체는 있는지 테스트할 수 있습니다는 `TypeOf`... `Is` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-167">You can test whether an object is of a particular type with the `TypeOf`...`Is` expression.</span></span> <span data-ttu-id="605cd-168">구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-168">The syntax is as follows:</span></span>  
  
 `TypeOf <objectexpression> Is <typename>`  
  
 <span data-ttu-id="605cd-169">때 `typename` 인터페이스 형식을 지정 하면 `TypeOf`... `Is` 식 반환 `True` 개체 인터페이스 형식을 구현 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="605cd-169">When `typename` specifies an interface type, then the `TypeOf`...`Is` expression returns `True` if the object implements the interface type.</span></span> <span data-ttu-id="605cd-170">때 `typename` 다음 식은 반환 형식이 있는 클래스 형식인 `True` 개체가 지정된 된 클래스에서 파생 되는 클래스 또는 지정된 된 클래스의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-170">When `typename` is a class type, then the expression returns `True` if the object is an instance of the specified class or of a class that derives from the specified class.</span></span> <span data-ttu-id="605cd-171">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-171">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#68](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_4.vb)]  
  
 <span data-ttu-id="605cd-172">앞의 예제에는 `TypeOf x Is Control` 식이 `True` 때문에 유형의 `x` 은 `Button`에서 상속 되 `Control`합니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-172">In the preceding example, the `TypeOf x Is Control` expression evaluates to `True` because the type of `x` is `Button`, which inherits from `Control`.</span></span>  
  
 <span data-ttu-id="605cd-173">자세한 내용은 참조 [TypeOf 연산자](../../../../visual-basic/language-reference/operators/typeof-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="605cd-173">For more information, see [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="605cd-174">참고 항목</span><span class="sxs-lookup"><span data-stu-id="605cd-174">See Also</span></span>  
 [<span data-ttu-id="605cd-175">값 비교</span><span class="sxs-lookup"><span data-stu-id="605cd-175">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [<span data-ttu-id="605cd-176">비교 연산자</span><span class="sxs-lookup"><span data-stu-id="605cd-176">Comparison Operators</span></span>](../../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [<span data-ttu-id="605cd-177">연산자</span><span class="sxs-lookup"><span data-stu-id="605cd-177">Operators</span></span>](../../../../visual-basic/language-reference/operators/index.md)  
 [<span data-ttu-id="605cd-178">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="605cd-178">Arithmetic Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [<span data-ttu-id="605cd-179">Visual Basic의 연결 연산자</span><span class="sxs-lookup"><span data-stu-id="605cd-179">Concatenation Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)  
 [<span data-ttu-id="605cd-180">Visual Basic의 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="605cd-180">Logical and Bitwise Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
