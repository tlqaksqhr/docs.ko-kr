---
title: Mod 연산자(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Mod
helpviewer_keywords:
- remainder (Mod operator)
- division operator [Visual Basic], Mod operator
- modulus operator [Visual Basic], Visual Basic
- Mod operator [Visual Basic]
- operators [Visual Basic], division
- arithmetic operators [Visual Basic], Mod
- math operators [Visual Basic]
ms.assetid: 6ff7e40e-cec8-4c77-bff6-8ddd2791c25b
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5464b57c993e5703c09529b527a7bc714e045870
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="mod-operator-visual-basic"></a><span data-ttu-id="59f33-102">Mod 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="59f33-102">Mod Operator (Visual Basic)</span></span>
<span data-ttu-id="59f33-103">두 숫자를 나누고 나머지만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="59f33-103">Divides two numbers and returns only the remainder.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59f33-104">구문</span><span class="sxs-lookup"><span data-stu-id="59f33-104">Syntax</span></span>  
  
```  
number1 Mod number2  
```  
  
## <a name="parts"></a><span data-ttu-id="59f33-105">요소</span><span class="sxs-lookup"><span data-stu-id="59f33-105">Parts</span></span>  
 `number1`  
 <span data-ttu-id="59f33-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="59f33-106">Required.</span></span> <span data-ttu-id="59f33-107">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="59f33-107">Any numeric expression.</span></span>  
  
 `number2`  
 <span data-ttu-id="59f33-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="59f33-108">Required.</span></span> <span data-ttu-id="59f33-109">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="59f33-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="59f33-110">지원 형식</span><span class="sxs-lookup"><span data-stu-id="59f33-110">Supported Types</span></span>  
 <span data-ttu-id="59f33-111">모든 숫자 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="59f33-111">All numeric types.</span></span> <span data-ttu-id="59f33-112">여기에 서명 되지 않은 부동 소수점 형식과 및 `Decimal`합니다.</span><span class="sxs-lookup"><span data-stu-id="59f33-112">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="59f33-113">결과</span><span class="sxs-lookup"><span data-stu-id="59f33-113">Result</span></span>  
 <span data-ttu-id="59f33-114">결과 나머지 `number1` 나눈 `number2`합니다.</span><span class="sxs-lookup"><span data-stu-id="59f33-114">The result is the remainder after `number1` is divided by `number2`.</span></span> <span data-ttu-id="59f33-115">예를 들어 식 `14 Mod 4` 계산 결과 2입니다.</span><span class="sxs-lookup"><span data-stu-id="59f33-115">For example, the expression `14 Mod 4` evaluates to 2.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59f33-116">설명</span><span class="sxs-lookup"><span data-stu-id="59f33-116">Remarks</span></span>  
 <span data-ttu-id="59f33-117">어느 경우 `number1` 또는 `number2` 는 부동 소수점 값, 부동 소수점 나누기의 나머지가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59f33-117">If either `number1` or `number2` is a floating-point value, the floating-point remainder of the division is returned.</span></span> <span data-ttu-id="59f33-118">결과의 데이터 형식이 데이터 형식으로 나눈 결과인 가능한 모든 값을 보유할 수 있는 가장 작은 데이터 형식 `number1` 및 `number2`합니다.</span><span class="sxs-lookup"><span data-stu-id="59f33-118">The data type of the result is the smallest data type that can hold all possible values that result from division with the data types of `number1` and `number2`.</span></span>  
  
 <span data-ttu-id="59f33-119">경우 `number1` 또는 `number2` 계산 [Nothing](../../../visual-basic/language-reference/nothing.md), 0으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59f33-119">If `number1` or `number2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
 <span data-ttu-id="59f33-120">관련 된 연산자는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="59f33-120">Related operators include the following:</span></span>  
  
-   <span data-ttu-id="59f33-121">[\ 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) 나누기의 몫을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="59f33-121">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient of a division.</span></span> <span data-ttu-id="59f33-122">예를 들어 식 `14 \ 4` 3으로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="59f33-122">For example, the expression `14 \ 4` evaluates to 3.</span></span>  
  
-   <span data-ttu-id="59f33-123">[/ 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) 부동 소수점 숫자로 나머지를 포함 하 여 전체 몫을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="59f33-123">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, including the remainder, as a floating-point number.</span></span> <span data-ttu-id="59f33-124">예를 들어 식 `14 / 4` 3.5로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="59f33-124">For example, the expression `14 / 4` evaluates to 3.5.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="59f33-125">0으로 나누기</span><span class="sxs-lookup"><span data-stu-id="59f33-125">Attempted Division by Zero</span></span>  
 <span data-ttu-id="59f33-126">경우 `number2` 의 동작을 0으로 계산 되는 `Mod` 연산자는 피연산자의 데이터 형식에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="59f33-126">If `number2` evaluates to zero, the behavior of the `Mod` operator depends on the data type of the operands.</span></span> <span data-ttu-id="59f33-127">이 정수 나누기를 throw 한 <xref:System.DivideByZeroException> 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="59f33-127">An integral division throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="59f33-128">부동 소수점 나누기 반환 <xref:System.Double.NaN>합니다.</span><span class="sxs-lookup"><span data-stu-id="59f33-128">A floating-point division returns <xref:System.Double.NaN>.</span></span>  
  
## <a name="equivalent-formula"></a><span data-ttu-id="59f33-129">해당 하는 수식</span><span class="sxs-lookup"><span data-stu-id="59f33-129">Equivalent Formula</span></span>  
 <span data-ttu-id="59f33-130">식 `a Mod b` 다음 수식을 중 하나에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="59f33-130">The expression `a Mod b` is equivalent to either of the following formulas:</span></span>  
  
 `a - (b * (a \ b))`  
  
 `a - (b * Fix(a / b))`  
  
## <a name="floating-point-imprecision"></a><span data-ttu-id="59f33-131">부동 소수점 연산이</span><span class="sxs-lookup"><span data-stu-id="59f33-131">Floating-Point Imprecision</span></span>  
 <span data-ttu-id="59f33-132">부동 소수점 숫자를 작업할 때에 항상 없는 정확한 표시 메모리에 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59f33-132">When you work with floating-point numbers, remember that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="59f33-133">값 비교 같은 특정 작업에서 예기치 않은 결과가 발생할 수 및 `Mod` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="59f33-133">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="59f33-134">자세한 내용은 참조 [데이터 형식 문제 해결](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="59f33-134">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="59f33-135">오버로딩</span><span class="sxs-lookup"><span data-stu-id="59f33-135">Overloading</span></span>  
 <span data-ttu-id="59f33-136">`Mod` 연산자 *오버 로드 된*, 클래스 또는 구조체의 동작 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59f33-136">The `Mod` operator can be *overloaded*, which means that a class or structure can redefine its behavior.</span></span> <span data-ttu-id="59f33-137">코드에 적용 되는 경우 `Mod` 클래스 또는 이러한 오버 로드를 포함 하는 구조체의 인스턴스로 사용할 다시 정의 된 동작을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59f33-137">If your code applies `Mod` to an instance of a class or structure that includes such an overload, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="59f33-138">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="59f33-138">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="59f33-139">예제</span><span class="sxs-lookup"><span data-stu-id="59f33-139">Example</span></span>  
 <span data-ttu-id="59f33-140">다음 예제에서는 `Mod` 연산자를 두 개의 숫자를 나누고 나머지만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="59f33-140">The following example uses the `Mod` operator to divide two numbers and return only the remainder.</span></span> <span data-ttu-id="59f33-141">중 하나가 숫자가 부동 소수점 숫자 이면의 결과 나머지를 나타내는 부동 소수점 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="59f33-141">If either number is a floating-point number, the result is a floating-point number that represents the remainder.</span></span>  
  
 [!code-vb[VbVbalrOperators#31](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/mod-operator_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="59f33-142">예제</span><span class="sxs-lookup"><span data-stu-id="59f33-142">Example</span></span>  
 <span data-ttu-id="59f33-143">다음 예제에서는 부동 소수점 피연산자의 잠재적 부정확성 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="59f33-143">The following example demonstrates the potential imprecision of floating-point operands.</span></span> <span data-ttu-id="59f33-144">피연산자는 첫 번째 문에서 `Double`, 0.2는 저장 된 값이 0.20000000000000001 인 무한 반복 이진 소수 및 합니다.</span><span class="sxs-lookup"><span data-stu-id="59f33-144">In the first statement, the operands are `Double`, and 0.2 is an infinitely repeating binary fraction with a stored value of 0.20000000000000001.</span></span> <span data-ttu-id="59f33-145">두 번째 문을 리터럴 형식 문자 `D` 두 피연산자 모두 강제로 `Decimal`, 0.2에 정확한 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="59f33-145">In the second statement, the literal type character `D` forces both operands to `Decimal`, and 0.2 has a precise representation.</span></span>  
  
 [!code-vb[VbVbalrOperators#32](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/mod-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="59f33-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59f33-146">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Conversion.Int%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Fix%2A>  
 [<span data-ttu-id="59f33-147">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="59f33-147">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="59f33-148">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="59f33-148">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="59f33-149">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="59f33-149">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="59f33-150">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="59f33-150">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="59f33-151">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="59f33-151">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [<span data-ttu-id="59f33-152">\ 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="59f33-152">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
