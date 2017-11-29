---
title: "\\ 연산자(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.\
- '\'
helpviewer_keywords:
- division operator [Visual Basic], integer
- integer division operator [Visual Basic]
- zero, division by zero
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- backslash (\) [Visual Basic]
- '\ operator [Visual Basic]'
- integer quotient
- math operators [Visual Basic]
- quotients, integer
- truncation [Visual Basic], integer division
ms.assetid: 4b0ee347-950c-45c9-8e23-54bc85df208e
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 38718b109b4b3865238267039908ea1d51d06229
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="ec52f-102">\ 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ec52f-102">\ Operator (Visual Basic)</span></span>
<span data-ttu-id="ec52f-103">두 숫자를 나누고 정수 결과 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec52f-103">Divides two numbers and returns an integer result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec52f-104">구문</span><span class="sxs-lookup"><span data-stu-id="ec52f-104">Syntax</span></span>  
  
```  
expression1 \ expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="ec52f-105">요소</span><span class="sxs-lookup"><span data-stu-id="ec52f-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="ec52f-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="ec52f-106">Required.</span></span> <span data-ttu-id="ec52f-107">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="ec52f-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="ec52f-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="ec52f-108">Required.</span></span> <span data-ttu-id="ec52f-109">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="ec52f-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="ec52f-110">지원 형식</span><span class="sxs-lookup"><span data-stu-id="ec52f-110">Supported Types</span></span>  
 <span data-ttu-id="ec52f-111">부호 없는 및 부동 소수점 형식을 포함 한 모든 숫자 형식 및 `Decimal`합니다.</span><span class="sxs-lookup"><span data-stu-id="ec52f-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="ec52f-112">결과</span><span class="sxs-lookup"><span data-stu-id="ec52f-112">Result</span></span>  
 <span data-ttu-id="ec52f-113">결과의 정수 몫은 `expression1` 나눈 `expression2`, 나머지는 버리고 정수 부분만 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec52f-113">The result is the integer quotient of `expression1` divided by `expression2`, which discards any remainder and retains only the integer portion.</span></span> <span data-ttu-id="ec52f-114">로 알려져 *잘림*합니다.</span><span class="sxs-lookup"><span data-stu-id="ec52f-114">This is known as *truncation*.</span></span>  
  
 <span data-ttu-id="ec52f-115">결과 데이터 형식이 데이터 형식에 대 한 적합 한 숫자 형식 `expression1` 및 `expression2`합니다.</span><span class="sxs-lookup"><span data-stu-id="ec52f-115">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="ec52f-116">"정수 연산" 표를 참조 하십시오. [연산자 결과의 데이터 형식을](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ec52f-116">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
 <span data-ttu-id="ec52f-117">[/ 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) 소수 부분에 있는 나머지를 유지 하면서 전체 몫을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec52f-117">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, which retains the remainder in the fractional portion.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec52f-118">설명</span><span class="sxs-lookup"><span data-stu-id="ec52f-118">Remarks</span></span>  
 <span data-ttu-id="ec52f-119">나누기를 수행 하기 전에 Visual Basic에 임의의 부동 소수점 숫자 식으로 변환 하려고 `Long`합니다.</span><span class="sxs-lookup"><span data-stu-id="ec52f-119">Before performing the division, Visual Basic attempts to convert any floating-point numeric expression to `Long`.</span></span> <span data-ttu-id="ec52f-120">경우 `Option Strict` 은 `On`, 컴파일러 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec52f-120">If `Option Strict` is `On`, a compiler error occurs.</span></span> <span data-ttu-id="ec52f-121">경우 `Option Strict` 은 `Off`, <xref:System.OverflowException> 값의 범위를 벗어납니다.이 경우에 [Long 데이터 형식](../../../visual-basic/language-reference/data-types/long-data-type.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ec52f-121">If `Option Strict` is `Off`, an <xref:System.OverflowException> is possible if the value is outside the range of the [Long Data Type](../../../visual-basic/language-reference/data-types/long-data-type.md).</span></span> <span data-ttu-id="ec52f-122">변환할 `Long` 를 일으키는 이기도 *banker rounding*합니다.</span><span class="sxs-lookup"><span data-stu-id="ec52f-122">The conversion to `Long` is also subject to *banker's rounding*.</span></span> <span data-ttu-id="ec52f-123">자세한 내용은의 "소수 부분이" 참조 [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ec52f-123">For more information, see "Fractional Parts" in [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="ec52f-124">경우 `expression1` 또는 `expression2` 계산 [Nothing](../../../visual-basic/language-reference/nothing.md), 0으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec52f-124">If `expression1` or `expression2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="ec52f-125">0으로 나누기</span><span class="sxs-lookup"><span data-stu-id="ec52f-125">Attempted Division by Zero</span></span>  
 <span data-ttu-id="ec52f-126">경우 `expression2` 가 0 이면는 `\` 연산자를 throw 한 <xref:System.DivideByZeroException> 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="ec52f-126">If `expression2` evaluates to zero, the `\` operator throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="ec52f-127">이 피연산자의 모든 숫자 데이터 형식에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec52f-127">This is true for all numeric data types of the operands.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec52f-128">`\` 연산자 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ec52f-128">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="ec52f-129">이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec52f-129">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="ec52f-130">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ec52f-130">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec52f-131">예제</span><span class="sxs-lookup"><span data-stu-id="ec52f-131">Example</span></span>  
 <span data-ttu-id="ec52f-132">다음 예제에서는 `\` 정수 나누기를 수행 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="ec52f-132">The following example uses the `\` operator to perform integer division.</span></span> <span data-ttu-id="ec52f-133">결과 나머지 삭제는 두 피연산자의 몫을 나타내는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="ec52f-133">The result is an integer that represents the integer quotient of the two operands, with the remainder discarded.</span></span>  
  
 [!code-vb[VbVbalrOperators#18](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/integer-division-operator_1.vb)]  
  
 <span data-ttu-id="ec52f-134">앞의 예제에 있는 식은 각각 2, 3, 33,-22의 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ec52f-134">The expressions in the preceding example return values of 2, 3, 33, and -22, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec52f-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ec52f-135">See Also</span></span>  
 [<span data-ttu-id="ec52f-136">\\= 연산자</span><span class="sxs-lookup"><span data-stu-id="ec52f-136">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)  
 [<span data-ttu-id="ec52f-137">/ 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ec52f-137">/ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)  
 [<span data-ttu-id="ec52f-138">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="ec52f-138">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="ec52f-139">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="ec52f-139">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="ec52f-140">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="ec52f-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="ec52f-141">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="ec52f-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="ec52f-142">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="ec52f-142">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
