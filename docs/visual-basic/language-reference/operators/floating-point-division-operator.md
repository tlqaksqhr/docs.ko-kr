---
title: / 연산자(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb./
helpviewer_keywords:
- division operator [Visual Basic], floating point
- floating-point numbers [Visual Basic], division operator
- slash (/) operator
- zero, division by zero
- operators [Visual Basic], arithmetic
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- operators [Visual Basic], division
- division operator [Visual Basic], syntax
- / operator [Visual Basic]
- math operators [Visual Basic]
ms.assetid: 335e97f2-c434-439e-9064-76973a051101
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2f221e863725b9aeb0b3fa3219b3a881541e2be0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="55ba7-102">/ 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55ba7-102">/ Operator (Visual Basic)</span></span>
<span data-ttu-id="55ba7-103">두 숫자를 나누고 부동 소수점 결과 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="55ba7-103">Divides two numbers and returns a floating-point result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55ba7-104">구문</span><span class="sxs-lookup"><span data-stu-id="55ba7-104">Syntax</span></span>  
  
```  
expression1 / expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="55ba7-105">요소</span><span class="sxs-lookup"><span data-stu-id="55ba7-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="55ba7-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="55ba7-106">Required.</span></span> <span data-ttu-id="55ba7-107">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="55ba7-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="55ba7-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="55ba7-108">Required.</span></span> <span data-ttu-id="55ba7-109">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="55ba7-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="55ba7-110">지원 형식</span><span class="sxs-lookup"><span data-stu-id="55ba7-110">Supported Types</span></span>  
 <span data-ttu-id="55ba7-111">부호 없는 및 부동 소수점 형식을 포함 한 모든 숫자 형식 및 `Decimal`합니다.</span><span class="sxs-lookup"><span data-stu-id="55ba7-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="55ba7-112">결과</span><span class="sxs-lookup"><span data-stu-id="55ba7-112">Result</span></span>  
 <span data-ttu-id="55ba7-113">결과 전체 몫 `expression1` 나눈 `expression2`, 나머지 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="55ba7-113">The result is the full quotient of `expression1` divided by `expression2`, including any remainder.</span></span>  
  
 <span data-ttu-id="55ba7-114">[\ 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) 나머지 부분을 삭제 하는 정수 몫을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="55ba7-114">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient, which drops the remainder.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55ba7-115">설명</span><span class="sxs-lookup"><span data-stu-id="55ba7-115">Remarks</span></span>  
 <span data-ttu-id="55ba7-116">데이터 형식의 결과 피연산자의 형식에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="55ba7-116">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="55ba7-117">다음 표에서 결과의 데이터 형식을 결정 하는 방법 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="55ba7-117">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="55ba7-118">피연산자 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="55ba7-118">Operand data types</span></span>|<span data-ttu-id="55ba7-119">결과 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="55ba7-119">Result data type</span></span>|  
|------------------------|----------------------|  
|<span data-ttu-id="55ba7-120">두 식이 모두 정수 계열 데이터 형식 ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [바이트](../../../visual-basic/language-reference/data-types/byte-data-type.md), [짧은](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [정수](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [긴](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span><span class="sxs-lookup"><span data-stu-id="55ba7-120">Both expressions are integral data types ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span></span>|`Double`|  
|<span data-ttu-id="55ba7-121">하나의 식이 [단일](../../../visual-basic/language-reference/data-types/single-data-type.md) 데이터 형식과 다른 않습니다는 [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="55ba7-121">One expression is a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) data type and the other is not a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="55ba7-122">하나의 식이 [10 진수](../../../visual-basic/language-reference/data-types/decimal-data-type.md) 데이터 형식과 다른 않습니다는 [단일](../../../visual-basic/language-reference/data-types/single-data-type.md) 또는 [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="55ba7-122">One expression is a [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) data type and the other is not a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) or a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="55ba7-123">두 식 중 하나가 한 [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="55ba7-123">Either expression is a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) data type</span></span>|`Double`|  
  
 <span data-ttu-id="55ba7-124">정수 계열 숫자 식이 모두는 확장 나누기를 수행 하기 전에 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="55ba7-124">Before division is performed, any integral numeric expressions are widened to `Double`.</span></span> <span data-ttu-id="55ba7-125">Visual Basic에서 결과 변환 하려고 정수 데이터 형식으로 결과 할당 하는 경우 `Double` 해당 형식으로.</span><span class="sxs-lookup"><span data-stu-id="55ba7-125">If you assign the result to an integral data type, Visual Basic attempts to convert the result from `Double` to that type.</span></span> <span data-ttu-id="55ba7-126">이 결과 해당 형식에 맞지 않는 경우 예외가 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="55ba7-126">This can throw an exception if the result does not fit in that type.</span></span> <span data-ttu-id="55ba7-127">특히이 도움말 페이지에 "0으로 나누기"을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="55ba7-127">In particular, see "Attempted Division by Zero" on this Help page.</span></span>  
  
 <span data-ttu-id="55ba7-128">경우 `expression1` 또는 `expression2` 계산 [Nothing](../../../visual-basic/language-reference/nothing.md), 0으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55ba7-128">If `expression1` or `expression2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="55ba7-129">0으로 나누기</span><span class="sxs-lookup"><span data-stu-id="55ba7-129">Attempted Division by Zero</span></span>  
 <span data-ttu-id="55ba7-130">경우 `expression2` 가 0 이면는 `/` 연산자는 피연산자를 다른 데이터 형식에 따라 다르게 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="55ba7-130">If `expression2` evaluates to zero, the `/` operator behaves differently for different operand data types.</span></span> <span data-ttu-id="55ba7-131">다음 표에서 가능한 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="55ba7-131">The following table shows the possible behaviors.</span></span>  
  
|<span data-ttu-id="55ba7-132">피연산자 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="55ba7-132">Operand data types</span></span>|<span data-ttu-id="55ba7-133">동작 하는 경우 `expression2` 0</span><span class="sxs-lookup"><span data-stu-id="55ba7-133">Behavior if `expression2` is zero</span></span>|  
|------------------------|---------------------------------------|  
|<span data-ttu-id="55ba7-134">부동 소수점 (`Single` 또는 `Double`)</span><span class="sxs-lookup"><span data-stu-id="55ba7-134">Floating-point (`Single` or `Double`)</span></span>|<span data-ttu-id="55ba7-135">무한대를 반환 (<xref:System.Double.PositiveInfinity> 또는 <xref:System.Double.NegativeInfinity>), 또는 <xref:System.Double.NaN> (숫자가 아님) 하는 경우 `expression1` 0입니다</span><span class="sxs-lookup"><span data-stu-id="55ba7-135">Returns infinity (<xref:System.Double.PositiveInfinity> or <xref:System.Double.NegativeInfinity>), or <xref:System.Double.NaN> (not a number) if `expression1` is also zero</span></span>|  
|`Decimal`|<span data-ttu-id="55ba7-136">Throw<xref:System.DivideByZeroException></span><span class="sxs-lookup"><span data-stu-id="55ba7-136">Throws <xref:System.DivideByZeroException></span></span>|  
|<span data-ttu-id="55ba7-137">정수 계열 (정수 또는 부호 없는)</span><span class="sxs-lookup"><span data-stu-id="55ba7-137">Integral (signed or unsigned)</span></span>|<span data-ttu-id="55ba7-138">정수 계열 형식 throw로 다시 변환 하려고 <xref:System.OverflowException> 정수 계열 형식 받아들일 수 있기 때문에 <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, 또는<xref:System.Double.NaN></span><span class="sxs-lookup"><span data-stu-id="55ba7-138">Attempted conversion back to integral type throws <xref:System.OverflowException> because integral types cannot accept <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, or <xref:System.Double.NaN></span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="55ba7-139">`/` 연산자 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="55ba7-139">The `/` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="55ba7-140">이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55ba7-140">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="55ba7-141">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="55ba7-141">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="55ba7-142">예제</span><span class="sxs-lookup"><span data-stu-id="55ba7-142">Example</span></span>  
 <span data-ttu-id="55ba7-143">사용 하 여이 예제는 `/` 부동 소수점 나누기를 수행 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="55ba7-143">This example uses the `/` operator to perform floating-point division.</span></span> <span data-ttu-id="55ba7-144">결과 두 피연산자의 몫입니다.</span><span class="sxs-lookup"><span data-stu-id="55ba7-144">The result is the quotient of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#16](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-operator_1.vb)]  
  
 <span data-ttu-id="55ba7-145">앞의 예제에서 식에는 2.5 및 3.333333 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="55ba7-145">The expressions in the preceding example return values of 2.5 and 3.333333.</span></span> <span data-ttu-id="55ba7-146">결과 항상 부동 소수점 (`Double`) 두 피연산자는 정수 상수는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="55ba7-146">Note that the result is always floating-point (`Double`), even though both operands are integer constants.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55ba7-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="55ba7-147">See Also</span></span>  
 [<span data-ttu-id="55ba7-148">/ = 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55ba7-148">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [<span data-ttu-id="55ba7-149">\ 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55ba7-149">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
 [<span data-ttu-id="55ba7-150">연산자 결과의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="55ba7-150">Data Types of Operator Results</span></span>](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)  
 [<span data-ttu-id="55ba7-151">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="55ba7-151">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="55ba7-152">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="55ba7-152">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="55ba7-153">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="55ba7-153">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="55ba7-154">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="55ba7-154">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
