---
title: "/ 연산자 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb./
dev_langs:
- VB
helpviewer_keywords:
- division operator, floating point
- floating-point numbers, division operator
- slash (/) operator
- zero, division by zero
- operators [Visual Basic], arithmetic
- arithmetic operators, division
- division, by zero
- operators [Visual Basic], division
- division operator, syntax
- / operator [Visual Basic]
- math operators
ms.assetid: 335e97f2-c434-439e-9064-76973a051101
caps.latest.revision: 18
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
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 82255339c3bdab7f6e760de9bef073f463260877
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017

---
# <a name="-operator-visual-basic"></a><span data-ttu-id="909d5-102">/ 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="909d5-102">/ Operator (Visual Basic)</span></span>
<span data-ttu-id="909d5-103">두 수를 나누고 부동 소수점 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="909d5-103">Divides two numbers and returns a floating-point result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="909d5-104">구문</span><span class="sxs-lookup"><span data-stu-id="909d5-104">Syntax</span></span>  
  
```  
expression1 / expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="909d5-105">요소</span><span class="sxs-lookup"><span data-stu-id="909d5-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="909d5-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="909d5-106">Required.</span></span> <span data-ttu-id="909d5-107">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="909d5-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="909d5-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="909d5-108">Required.</span></span> <span data-ttu-id="909d5-109">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="909d5-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="909d5-110">지원 형식</span><span class="sxs-lookup"><span data-stu-id="909d5-110">Supported Types</span></span>  
 <span data-ttu-id="909d5-111">부호 없는 및 부동 소수점 형식을 비롯 한 모든 숫자 형식, 및 `Decimal`합니다.</span><span class="sxs-lookup"><span data-stu-id="909d5-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="909d5-112">결과</span><span class="sxs-lookup"><span data-stu-id="909d5-112">Result</span></span>  
 <span data-ttu-id="909d5-113">결과 전체 몫 `expression1` 나눈 `expression2`, 나머지 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="909d5-113">The result is the full quotient of `expression1` divided by `expression2`, including any remainder.</span></span>  
  
 <span data-ttu-id="909d5-114">[\ 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) 나머지 부분을 삭제 하는 정수 몫을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="909d5-114">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient, which drops the remainder.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="909d5-115">주의</span><span class="sxs-lookup"><span data-stu-id="909d5-115">Remarks</span></span>  
 <span data-ttu-id="909d5-116">결과의 데이터 형식 피연산자의 형식에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="909d5-116">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="909d5-117">다음 표에서 결과의 데이터 형식을 결정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="909d5-117">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="909d5-118">피연산자 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="909d5-118">Operand data types</span></span>|<span data-ttu-id="909d5-119">결과 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="909d5-119">Result data type</span></span>|  
|------------------------|----------------------|  
|<span data-ttu-id="909d5-120">두 식이 모두 정수 계열 데이터 형식 ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [바이트](../../../visual-basic/language-reference/data-types/byte-data-type.md), [짧은](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [정수](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [긴](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span><span class="sxs-lookup"><span data-stu-id="909d5-120">Both expressions are integral data types ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span></span>|`Double`|  
|<span data-ttu-id="909d5-121">한 식은 [단일](../../../visual-basic/language-reference/data-types/single-data-type.md) 데이터 형식을 지정 하 고 다른 한 [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="909d5-121">One expression is a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) data type and the other is not a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="909d5-122">한 식은 [10 진수](../../../visual-basic/language-reference/data-types/decimal-data-type.md) 데이터 형식을 지정 하 고 다른 한 [단일](../../../visual-basic/language-reference/data-types/single-data-type.md) 또는 [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="909d5-122">One expression is a [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) data type and the other is not a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) or a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="909d5-123">두 식 중 하나가 [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="909d5-123">Either expression is a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) data type</span></span>|`Double`|  
  
 <span data-ttu-id="909d5-124">정수 계열 숫자 식이 모두로 확장 됩니다 나누기를 수행 하기 전에 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="909d5-124">Before division is performed, any integral numeric expressions are widened to `Double`.</span></span> <span data-ttu-id="909d5-125">결과 정수 계열 데이터 형식에 할당 하면 Visual Basic에서 결과 변환 하려고 시도 `Double` 해당 형식에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="909d5-125">If you assign the result to an integral data type, Visual Basic attempts to convert the result from `Double` to that type.</span></span> <span data-ttu-id="909d5-126">이 결과 해당 형식에 맞지 않을 경우 예외가 throw 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="909d5-126">This can throw an exception if the result does not fit in that type.</span></span> <span data-ttu-id="909d5-127">이 도움말 페이지에 특히, "0으로 나누기"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="909d5-127">In particular, see "Attempted Division by Zero" on this Help page.</span></span>  
  
 <span data-ttu-id="909d5-128">경우 `expression1` 또는 `expression2` 계산 [Nothing](../../../visual-basic/language-reference/nothing.md),&0;으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="909d5-128">If `expression1` or `expression2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="909d5-129">0으로 나누기</span><span class="sxs-lookup"><span data-stu-id="909d5-129">Attempted Division by Zero</span></span>  
 <span data-ttu-id="909d5-130">경우 `expression2`&0;으로 계산 된 `/` 연산자는 여러 가지 피연산자 데이터 형식에 따라 다르게 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="909d5-130">If `expression2` evaluates to zero, the `/` operator behaves differently for different operand data types.</span></span> <span data-ttu-id="909d5-131">다음 표에서 가능한 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="909d5-131">The following table shows the possible behaviors.</span></span>  
  
|<span data-ttu-id="909d5-132">피연산자 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="909d5-132">Operand data types</span></span>|<span data-ttu-id="909d5-133">동작 하는 경우 `expression2`&0;</span><span class="sxs-lookup"><span data-stu-id="909d5-133">Behavior if `expression2` is zero</span></span>|  
|------------------------|---------------------------------------|  
|<span data-ttu-id="909d5-134">부동 소수점 (`Single` 또는 `Double`)</span><span class="sxs-lookup"><span data-stu-id="909d5-134">Floating-point (`Single` or `Double`)</span></span>|<span data-ttu-id="909d5-135">무한대를 반환 (<xref:System.Double.PositiveInfinity> 또는 <xref:System.Double.NegativeInfinity>), 또는 <xref:System.Double.NaN>(숫자가 아님) 하는 경우 `expression1` 도&0; 이면</xref:System.Double.NaN> </xref:System.Double.NegativeInfinity> </xref:System.Double.PositiveInfinity></span><span class="sxs-lookup"><span data-stu-id="909d5-135">Returns infinity (<xref:System.Double.PositiveInfinity> or <xref:System.Double.NegativeInfinity>), or <xref:System.Double.NaN> (not a number) if `expression1` is also zero</span></span>|  
|`Decimal`|<span data-ttu-id="909d5-136">Throw<xref:System.DivideByZeroException></xref:System.DivideByZeroException></span><span class="sxs-lookup"><span data-stu-id="909d5-136">Throws <xref:System.DivideByZeroException></span></span>|  
|<span data-ttu-id="909d5-137">정수 계열 (정수 또는 부호 없는)</span><span class="sxs-lookup"><span data-stu-id="909d5-137">Integral (signed or unsigned)</span></span>|<span data-ttu-id="909d5-138">Throw 정수 계열 형식으로 다시 변환 하려고 <xref:System.OverflowException>정수 계열 형식 받아들일 수 있기 때문에 <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, 또는 <xref:System.Double.NaN></xref:System.Double.NaN> </xref:System.Double.NegativeInfinity> </xref:System.Double.PositiveInfinity> </xref:System.OverflowException></span><span class="sxs-lookup"><span data-stu-id="909d5-138">Attempted conversion back to integral type throws <xref:System.OverflowException> because integral types cannot accept <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, or <xref:System.Double.NaN></span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="909d5-139">`/` 연산자 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="909d5-139">The `/` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="909d5-140">이 연산자를 사용 하 여 이러한 클래스 또는 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="909d5-140">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="909d5-141">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="909d5-141">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="909d5-142">예제</span><span class="sxs-lookup"><span data-stu-id="909d5-142">Example</span></span>  
 <span data-ttu-id="909d5-143">사용 하 여이 예제는 `/` 연산자를 부동 소수점 나누기 연산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="909d5-143">This example uses the `/` operator to perform floating-point division.</span></span> <span data-ttu-id="909d5-144">결과 두 피연산자의 몫입니다.</span><span class="sxs-lookup"><span data-stu-id="909d5-144">The result is the quotient of the two operands.</span></span>  
  
 <span data-ttu-id="909d5-145">[!code-vb[VbVbalrOperators #&16;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="909d5-145">[!code-vb[VbVbalrOperators#16](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-operator_1.vb)]</span></span>  
  
 <span data-ttu-id="909d5-146">앞의 예제에서 식에는 2.5 및 3.333333 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="909d5-146">The expressions in the preceding example return values of 2.5 and 3.333333.</span></span> <span data-ttu-id="909d5-147">결과 항상 부동 소수점 (`Double`) 피연산자가 모두 정수 상수는 경우에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="909d5-147">Note that the result is always floating-point (`Double`), even though both operands are integer constants.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="909d5-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="909d5-148">See Also</span></span>  
 <span data-ttu-id="909d5-149">[/ = 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="909d5-149">[/= Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md) </span></span>  
<span data-ttu-id="909d5-150"> [\ 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) </span><span class="sxs-lookup"><span data-stu-id="909d5-150"> [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) </span></span>  
<span data-ttu-id="909d5-151"> [연산자 결과의 데이터 형식](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md) </span><span class="sxs-lookup"><span data-stu-id="909d5-151"> [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md) </span></span>  
<span data-ttu-id="909d5-152"> [산술 연산자](../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span><span class="sxs-lookup"><span data-stu-id="909d5-152"> [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span></span>  
<span data-ttu-id="909d5-153"> [Visual Basic의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md) </span><span class="sxs-lookup"><span data-stu-id="909d5-153"> [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md) </span></span>  
<span data-ttu-id="909d5-154"> [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="909d5-154"> [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span></span>  
<span data-ttu-id="909d5-155"> [Visual Basic의 산술 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)</span><span class="sxs-lookup"><span data-stu-id="909d5-155"> [Arithmetic Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)</span></span>

