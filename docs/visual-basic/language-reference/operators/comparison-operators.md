---
title: "비교 연산자(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.<>
- vb.>=
- vb.<=
- vb.>
- vb.<
helpviewer_keywords:
- greater than or equal to operator [Visual Basic]
- '>= operator [Visual Basic]'
- = operator [Visual Basic]
- < operator [Visual Basic]
- less than operator [Visual Basic]
- relational operators [Visual Basic], syntax
- Like operator [Visual Basic]
- <> operator [Visual Basic]
- '> operator [Visual Basic]'
- equal operator [Visual Basic]
- less than or equal to operator [Visual Basic]
- symbols, operators
- greater than operator [Visual Basic]
- comparing values [Visual Basic]
- operators [Visual Basic], relational
- string comparison [Visual Basic]
- not equal to comparison operator [Visual Basic]
- <= operator [Visual Basic]
- operators [Visual Basic], comparison
- Is operator [Visual Basic]
- comparison operators [Visual Basic], Visual Basicl
ms.assetid: d6cb12a8-e52e-46a7-8aaf-f804d634a825
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: aa450f7978f46196663c7534b31597b04d80482a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="comparison-operators-visual-basic"></a><span data-ttu-id="21803-102">비교 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21803-102">Comparison Operators (Visual Basic)</span></span>
<span data-ttu-id="21803-103">Visual Basic에서 정의 하는 비교 연산자는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="21803-103">The following are the comparison operators defined in Visual Basic.</span></span>  
  
 <span data-ttu-id="21803-104">`<`연산자</span><span class="sxs-lookup"><span data-stu-id="21803-104">`<` operator</span></span>  
  
 <span data-ttu-id="21803-105">`<=`연산자</span><span class="sxs-lookup"><span data-stu-id="21803-105">`<=` operator</span></span>  
  
 <span data-ttu-id="21803-106">`>`연산자</span><span class="sxs-lookup"><span data-stu-id="21803-106">`>` operator</span></span>  
  
 <span data-ttu-id="21803-107">`>=`연산자</span><span class="sxs-lookup"><span data-stu-id="21803-107">`>=` operator</span></span>  
  
 <span data-ttu-id="21803-108">`=`연산자</span><span class="sxs-lookup"><span data-stu-id="21803-108">`=` operator</span></span>  
  
 <span data-ttu-id="21803-109">`<>`연산자</span><span class="sxs-lookup"><span data-stu-id="21803-109">`<>` operator</span></span>  
  
 [<span data-ttu-id="21803-110">Is 연산자</span><span class="sxs-lookup"><span data-stu-id="21803-110">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
  
 [<span data-ttu-id="21803-111">IsNot 연산자</span><span class="sxs-lookup"><span data-stu-id="21803-111">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
  
 [<span data-ttu-id="21803-112">Like 연산자</span><span class="sxs-lookup"><span data-stu-id="21803-112">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)  
  
 <span data-ttu-id="21803-113">이러한 연산자는 두 식이 같은지 하 고 그렇지 않은 경우 이러한 어떻게 다른 지 여부를 확인 하려면 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="21803-113">These operators compare two expressions to determine whether or not they are equal, and if not, how they differ.</span></span> <span data-ttu-id="21803-114">`Is``IsNot`, 및 `Like` 별도 도움말 페이지에 자세하게에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="21803-114">`Is`, `IsNot`, and `Like` are discussed in detail on separate Help pages.</span></span> <span data-ttu-id="21803-115">관계 비교 연산자는이 페이지에 자세히 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21803-115">The relational comparison operators are discussed in detail on this page.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21803-116">구문</span><span class="sxs-lookup"><span data-stu-id="21803-116">Syntax</span></span>  
  
```  
      result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="21803-117">요소</span><span class="sxs-lookup"><span data-stu-id="21803-117">Parts</span></span>  
 `result`  
 <span data-ttu-id="21803-118">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="21803-118">Required.</span></span> <span data-ttu-id="21803-119">A `Boolean` 비교 결과 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="21803-119">A `Boolean` value representing the result of the comparison.</span></span>  
  
 `expression`  
 <span data-ttu-id="21803-120">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="21803-120">Required.</span></span> <span data-ttu-id="21803-121">임의의 식입니다.</span><span class="sxs-lookup"><span data-stu-id="21803-121">Any expression.</span></span>  
  
 `comparisonoperator`  
 <span data-ttu-id="21803-122">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="21803-122">Required.</span></span> <span data-ttu-id="21803-123">모든 관계형 비교 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="21803-123">Any relational comparison operator.</span></span>  
  
 <span data-ttu-id="21803-124">`object1`, `object2`</span><span class="sxs-lookup"><span data-stu-id="21803-124">`object1`, `object2`</span></span>  
 <span data-ttu-id="21803-125">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="21803-125">Required.</span></span> <span data-ttu-id="21803-126">모든 개체 이름을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="21803-126">Any reference object names.</span></span>  
  
 `string`  
 <span data-ttu-id="21803-127">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="21803-127">Required.</span></span> <span data-ttu-id="21803-128">임의의 `String` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="21803-128">Any `String` expression.</span></span>  
  
 `pattern`  
 <span data-ttu-id="21803-129">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="21803-129">Required.</span></span> <span data-ttu-id="21803-130">모든 `String` 식 또는 문자 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="21803-130">Any `String` expression or range of characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21803-131">설명</span><span class="sxs-lookup"><span data-stu-id="21803-131">Remarks</span></span>  
 <span data-ttu-id="21803-132">다음 표에서 관계형 비교 연산자와 결정 하는 조건 목록을 여부 `result` 은 `True` 또는 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="21803-132">The following table contains a list of the relational comparison operators and the conditions that determine whether `result` is `True` or `False`.</span></span>  
  
|<span data-ttu-id="21803-133">연산자</span><span class="sxs-lookup"><span data-stu-id="21803-133">Operator</span></span>|<span data-ttu-id="21803-134">`True`if</span><span class="sxs-lookup"><span data-stu-id="21803-134">`True` if</span></span>|<span data-ttu-id="21803-135">`False`if</span><span class="sxs-lookup"><span data-stu-id="21803-135">`False` if</span></span>|  
|--------------|---------------|----------------|  
|<span data-ttu-id="21803-136">`<`(보다 작음)</span><span class="sxs-lookup"><span data-stu-id="21803-136">`<` (Less than)</span></span>|`expression1` < `expression2`|`expression1` >= `expression2`|  
|<span data-ttu-id="21803-137">`<=`(작거나 같음)</span><span class="sxs-lookup"><span data-stu-id="21803-137">`<=` (Less than or equal to)</span></span>|`expression1` <= `expression2`|`expression1` > `expression2`|  
|<span data-ttu-id="21803-138">`>`(보다 큼)</span><span class="sxs-lookup"><span data-stu-id="21803-138">`>` (Greater than)</span></span>|`expression1` > `expression2`|`expression1` <= `expression2`|  
|<span data-ttu-id="21803-139">`>=`(보다 크거나 같음)</span><span class="sxs-lookup"><span data-stu-id="21803-139">`>=` (Greater than or equal to)</span></span>|`expression1` >= `expression2`|`expression1` < `expression2`|  
|<span data-ttu-id="21803-140">`=`(같음)</span><span class="sxs-lookup"><span data-stu-id="21803-140">`=` (Equal to)</span></span>|`expression1` = `expression2`|`expression1` <> `expression2`|  
|<span data-ttu-id="21803-141">`<>`(같지 않음)</span><span class="sxs-lookup"><span data-stu-id="21803-141">`<>` (Not equal to)</span></span>|`expression1` <> `expression2`|`expression1` = `expression2`|  
  
> [!NOTE]
>  <span data-ttu-id="21803-142">[연산자 =](../../../visual-basic/language-reference/operators/assignment-operator.md) 할당 연산자로도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21803-142">The [= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) is also used as an assignment operator.</span></span>  
  
 <span data-ttu-id="21803-143">`Is` 연산자는 `IsNot` 연산자 및 `Like` 연산자 앞의 표에 연산자와 다른 특정 비교 기능을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="21803-143">The `Is` operator, the `IsNot` operator, and the `Like` operator have specific comparison functionalities that differ from the operators in the preceding table.</span></span>  
  
## <a name="comparing-numbers"></a><span data-ttu-id="21803-144">숫자를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="21803-144">Comparing Numbers</span></span>  
 <span data-ttu-id="21803-145">형식의 식은 비교할 때 `Single` 형식 중 하나로 `Double`, `Single` 식이 변환 되 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="21803-145">When you compare an expression of type `Single` to one of type `Double`, the `Single` expression is converted to `Double`.</span></span> <span data-ttu-id="21803-146">이 동작은 Visual Basic 6 동작 반대입니다.</span><span class="sxs-lookup"><span data-stu-id="21803-146">This behavior is opposite to the behavior found in Visual Basic 6.</span></span>  
  
 <span data-ttu-id="21803-147">마찬가지로, 형식의 식은 비교할 때 `Decimal` 형식의 식에 `Single` 또는 `Double`, `Decimal` 식이 변환 되 `Single` 또는 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="21803-147">Similarly, when you compare an expression of type `Decimal` to an expression of type `Single` or `Double`, the `Decimal` expression is converted to `Single` or `Double`.</span></span> <span data-ttu-id="21803-148">에 대 한 `Decimal` 식 소수 값 보다 작은 1E 28 손실 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21803-148">For `Decimal` expressions, any fractional value less than 1E-28 might be lost.</span></span> <span data-ttu-id="21803-149">이러한 소수 자릿수 값 손실 되지 않은 것으로 비교 하려면 두 값을 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21803-149">Such fractional value loss may cause two values to compare as equal when they are not.</span></span> <span data-ttu-id="21803-150">이러한 이유로 주의 해야 같음을 사용 하는 경우 (`=`) 부동 소수점 변수 두 개를 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="21803-150">For this reason, you should take care when using equality (`=`) to compare two floating-point variables.</span></span> <span data-ttu-id="21803-151">더 안전의 차이 두 숫자의 절대값 허용 오차 보다 작은지 여부를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="21803-151">It is safer to test whether the absolute value of the difference between the two numbers is less than a small acceptable tolerance.</span></span>  
  
### <a name="floating-point-imprecision"></a><span data-ttu-id="21803-152">부동 소수점 연산이</span><span class="sxs-lookup"><span data-stu-id="21803-152">Floating-point Imprecision</span></span>  
 <span data-ttu-id="21803-153">부동 소수점 숫자를 작업할 때는 항상 없는 정확한 표시 메모리에 염두에 둬야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21803-153">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="21803-154">값 비교 같은 특정 작업에서 예기치 않은 결과가 발생할 수 및 [Mod 연산자](../../../visual-basic/language-reference/operators/mod-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="21803-154">This could lead to unexpected results from certain operations, such as value comparison and the [Mod Operator](../../../visual-basic/language-reference/operators/mod-operator.md).</span></span> <span data-ttu-id="21803-155">자세한 내용은 참조 [데이터 형식 문제 해결](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="21803-155">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="comparing-strings"></a><span data-ttu-id="21803-156">문자열 비교</span><span class="sxs-lookup"><span data-stu-id="21803-156">Comparing Strings</span></span>  
 <span data-ttu-id="21803-157">문자열을 비교할 때 문자열 식이에 따라 달라 지는 사전순 정렬 순서에 따라 평가 되는 `Option Compare` 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21803-157">When you compare strings, the string expressions are evaluated based on their alphabetical sort order, which depends on the `Option Compare` setting.</span></span>  
  
 <span data-ttu-id="21803-158">`Option Compare Binary`문자열을 비교 문자의 내부 이진 표현에서 파생 된 정렬 순서입니다.</span><span class="sxs-lookup"><span data-stu-id="21803-158">`Option Compare Binary` bases string comparisons on a sort order derived from the internal binary representations of the characters.</span></span> <span data-ttu-id="21803-159">정렬 순서는 코드 페이지에 의해 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21803-159">The sort order is determined by the code page.</span></span> <span data-ttu-id="21803-160">다음 예제에서는 일반적인 이진 정렬 순서를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="21803-160">The following example shows a typical binary sort order.</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="21803-161">`Option Compare Text`응용 프로그램의 로캘에 따라 결정 되는 대/소문자 구분 텍스트 정렬 순서에 대 한 비교 문자열 합니다.</span><span class="sxs-lookup"><span data-stu-id="21803-161">`Option Compare Text` bases string comparisons on a case-insensitive, textual sort order determined by your application's locale.</span></span> <span data-ttu-id="21803-162">설정 하는 경우 `Option Compare Text` 앞의 예에서 문자를 정렬 하 고, 다음 텍스트 정렬 순서가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21803-162">When you set `Option Compare Text` and sort the characters in the preceding example, the following text sort order applies:</span></span>  
  
 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`  
  
### <a name="locale-dependence"></a><span data-ttu-id="21803-163">로캘 종속성</span><span class="sxs-lookup"><span data-stu-id="21803-163">Locale Dependence</span></span>  
 <span data-ttu-id="21803-164">설정 하는 경우 `Option Compare Text`, 문자열 비교 작업의 결과 응용 프로그램이 실행 되 고 있는 로캘에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21803-164">When you set `Option Compare Text`, the result of a string comparison can depend on the locale in which the application is running.</span></span> <span data-ttu-id="21803-165">두 개의 문자 1 개 로캘만에 동일한 것으로 비교 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21803-165">Two characters might compare as equal in one locale but not in another.</span></span> <span data-ttu-id="21803-166">로그온 시도를 허용할지 여부와 같은 중요 한 결정을 내릴 수 문자열 비교를 사용 하는 경우에 로캘 구분에 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21803-166">If you are using a string comparison to make important decisions, such as whether to accept an attempt to log on, you should be alert to locale sensitivity.</span></span> <span data-ttu-id="21803-167">설정 하거나 `Option Compare Binary` 호출 또는 <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, 하는 로캘의 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="21803-167">Consider either setting `Option Compare Binary` or calling the <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, which takes the locale into account.</span></span>  
  
## <a name="typeless-programming-with-relational-comparison-operators"></a><span data-ttu-id="21803-168">관대 한 형식의 프로그래밍 관계 비교 연산자</span><span class="sxs-lookup"><span data-stu-id="21803-168">Typeless Programming with Relational Comparison Operators</span></span>  
 <span data-ttu-id="21803-169">관계 비교 연산자를 사용 하 여 `Object` 식에서 허용 되지 않습니다 `Option Strict On`합니다.</span><span class="sxs-lookup"><span data-stu-id="21803-169">The use of relational comparison operators with `Object` expressions is not allowed under `Option Strict On`.</span></span> <span data-ttu-id="21803-170">때 `Option Strict` 은 `Off`, 고 `expression1` 또는 `expression2` 는 `Object` 식, 런타임 형식의 비교 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21803-170">When `Option Strict` is `Off`, and either `expression1` or `expression2` is an `Object` expression, the run-time types determine how they are compared.</span></span> <span data-ttu-id="21803-171">다음 표에서 식의 비교 방법 및 적용 한 결과 피연산자의 런타임 형식에 따라 비교를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="21803-171">The following table shows how the expressions are compared and the result from the comparison, depending on the runtime type of the operands.</span></span>  
  
|<span data-ttu-id="21803-172">피연산자가</span><span class="sxs-lookup"><span data-stu-id="21803-172">If operands are</span></span>|<span data-ttu-id="21803-173">비교는</span><span class="sxs-lookup"><span data-stu-id="21803-173">Comparison is</span></span>|  
|---------------------|-------------------|  
|<span data-ttu-id="21803-174">둘 다`String`</span><span class="sxs-lookup"><span data-stu-id="21803-174">Both `String`</span></span>|<span data-ttu-id="21803-175">문자열 정렬 특성에 따라 비교를 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="21803-175">Sort comparison based on string sorting characteristics.</span></span>|  
|<span data-ttu-id="21803-176">두 숫자</span><span class="sxs-lookup"><span data-stu-id="21803-176">Both numeric</span></span>|<span data-ttu-id="21803-177">개체 변환 `Double`, 숫자 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="21803-177">Objects converted to `Double`, numeric comparison.</span></span>|  
|<span data-ttu-id="21803-178">한 숫자가 고 하나`String`</span><span class="sxs-lookup"><span data-stu-id="21803-178">One numeric and one `String`</span></span>|<span data-ttu-id="21803-179">`String` 변환 되는 `Double` 숫자 비교가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21803-179">The `String` is converted to a `Double` and numeric comparison is performed.</span></span> <span data-ttu-id="21803-180">경우는 `String` 변환할 수 없습니다 `Double`, <xref:System.InvalidCastException> throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21803-180">If the `String` cannot be converted to `Double`, an <xref:System.InvalidCastException> is thrown.</span></span>|  
|<span data-ttu-id="21803-181">하나 또는 둘 다가 아닌 다른 참조 형식`String`</span><span class="sxs-lookup"><span data-stu-id="21803-181">Either or both are reference types other than `String`</span></span>|<span data-ttu-id="21803-182"><xref:System.InvalidCastException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="21803-182">An <xref:System.InvalidCastException> is thrown.</span></span>|  
  
 <span data-ttu-id="21803-183">숫자 비교 처리 `Nothing` 0으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="21803-183">Numeric comparisons treat `Nothing` as 0.</span></span> <span data-ttu-id="21803-184">문자열 비교 처리 `Nothing` 으로 `""` (빈 문자열)입니다.</span><span class="sxs-lookup"><span data-stu-id="21803-184">String comparisons treat `Nothing` as `""` (an empty string).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="21803-185">오버로딩</span><span class="sxs-lookup"><span data-stu-id="21803-185">Overloading</span></span>  
 <span data-ttu-id="21803-186">관계 비교 연산자 (`<`합니다.</span><span class="sxs-lookup"><span data-stu-id="21803-186">The relational comparison operators (`<`.</span></span> <span data-ttu-id="21803-187">`<=``>`, `>=`, `=`, `<>`) 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="21803-187">`<=`, `>`, `>=`, `=`, `<>`) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="21803-188">코드를 사용 하는 이러한 클래스 또는 구조체에서 이러한 연산자를 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21803-188">If your code uses any of these operators on such a class or structure, be sure you understand the redefined behavior.</span></span> <span data-ttu-id="21803-189">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="21803-189">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
 <span data-ttu-id="21803-190">에 [연산자 =](../../../visual-basic/language-reference/operators/assignment-operator.md) 할당 연산자가 아닌 비교 관계형 연산자로 오버 로드 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21803-190">Notice that the [= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21803-191">예제</span><span class="sxs-lookup"><span data-stu-id="21803-191">Example</span></span>  
 <span data-ttu-id="21803-192">다음 예제에서는 식을 비교 하는 데 사용할 수 있는 관계 비교 연산자의 다양 한 용도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="21803-192">The following example shows various uses of relational comparison operators, which you use to compare expressions.</span></span> <span data-ttu-id="21803-193">관계 비교 연산자는 반환 된 `Boolean` 명시 식이 있는지 여부를 나타내는 결과입니다 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="21803-193">Relational comparison operators return a `Boolean` result that represents whether or not the stated expression evaluates to `True`.</span></span> <span data-ttu-id="21803-194">적용 하는 경우는 `>` 및 `<` 연산자를 문자열 면 비교가 수행 되는 문자열의 일반 사전순 정렬 순서를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="21803-194">When you apply the `>` and `<` operators to strings, the comparison is made using the normal alphabetical sorting order of the strings.</span></span> <span data-ttu-id="21803-195">이 순서는 로캘 설정에 종속 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21803-195">This order can be dependent on your locale setting.</span></span> <span data-ttu-id="21803-196">정렬은 대/소문자 구분 여부에 따라 결정 된 [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21803-196">Whether the sort is case-sensitive or not depends on the [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) setting.</span></span>  
  
 [!code-vb[VbVbalrOperators#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_1.vb)]  
  
 <span data-ttu-id="21803-197">앞의 예제에서 첫 번째 비교 반환 `False` 나머지 비교 다음 다시 돌아와 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="21803-197">In the preceding example, the first comparison returns `False` and the remaining comparisons return `True`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21803-198">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21803-198">See Also</span></span>  
 <xref:System.InvalidCastException>  
 [<span data-ttu-id="21803-199">= 연산자</span><span class="sxs-lookup"><span data-stu-id="21803-199">= Operator</span></span>](../../../visual-basic/language-reference/operators/assignment-operator.md)  
 [<span data-ttu-id="21803-200">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="21803-200">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="21803-201">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="21803-201">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="21803-202">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="21803-202">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="21803-203">Visual Basic의 비교 연산자</span><span class="sxs-lookup"><span data-stu-id="21803-203">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
