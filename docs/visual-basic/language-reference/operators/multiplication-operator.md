---
title: '* 연산자 (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.*
helpviewer_keywords:
- arithmetic operators [Visual Basic], multiplication
- operators [Visual Basic], multiplication
- '* operator [Visual Basic]'
- multiplication operator [Visual Basic], syntax
- math operators [Visual Basic]
ms.assetid: 2b210382-99da-4195-89ba-b1d06f5e89ad
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 450d728e44ef5639d75369e05b47cb3009b4d769
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="a8594-102">\* 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8594-102">\* Operator (Visual Basic)</span></span>
<span data-ttu-id="a8594-103">두 숫자를 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="a8594-103">Multiplies two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8594-104">구문</span><span class="sxs-lookup"><span data-stu-id="a8594-104">Syntax</span></span>  
  
```  
number1 * number2  
```  
  
## <a name="parts"></a><span data-ttu-id="a8594-105">요소</span><span class="sxs-lookup"><span data-stu-id="a8594-105">Parts</span></span>  
  
|<span data-ttu-id="a8594-106">용어</span><span class="sxs-lookup"><span data-stu-id="a8594-106">Term</span></span>|<span data-ttu-id="a8594-107">정의</span><span class="sxs-lookup"><span data-stu-id="a8594-107">Definition</span></span>|  
|---|---|  
|`number1`|<span data-ttu-id="a8594-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a8594-108">Required.</span></span> <span data-ttu-id="a8594-109">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a8594-109">Any numeric expression.</span></span>|  
|`number2`|<span data-ttu-id="a8594-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a8594-110">Required.</span></span> <span data-ttu-id="a8594-111">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a8594-111">Any numeric expression.</span></span>|  
  
## <a name="result"></a><span data-ttu-id="a8594-112">결과</span><span class="sxs-lookup"><span data-stu-id="a8594-112">Result</span></span>  
 <span data-ttu-id="a8594-113">결과의 제품 `number1` 및 `number2`합니다.</span><span class="sxs-lookup"><span data-stu-id="a8594-113">The result is the product of `number1` and `number2`.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="a8594-114">지원 형식</span><span class="sxs-lookup"><span data-stu-id="a8594-114">Supported Types</span></span>  
 <span data-ttu-id="a8594-115">부호 없는 및 부동 소수점 형식을 포함 한 모든 숫자 형식 및 `Decimal`합니다.</span><span class="sxs-lookup"><span data-stu-id="a8594-115">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8594-116">설명</span><span class="sxs-lookup"><span data-stu-id="a8594-116">Remarks</span></span>  
 <span data-ttu-id="a8594-117">데이터 형식의 결과 피연산자의 형식에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="a8594-117">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="a8594-118">다음 표에서 결과의 데이터 형식을 결정 하는 방법 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a8594-118">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="a8594-119">피연산자 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a8594-119">Operand data types</span></span>|<span data-ttu-id="a8594-120">결과 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a8594-120">Result data type</span></span>|  
|---|---|  
|<span data-ttu-id="a8594-121">두 식이 모두 정수 계열 데이터 형식 ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [바이트](../../../visual-basic/language-reference/data-types/byte-data-type.md), [짧은](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [정수](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [긴](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span><span class="sxs-lookup"><span data-stu-id="a8594-121">Both expressions are integral data types ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span></span>|<span data-ttu-id="a8594-122">데이터 형식에 적합 한 숫자 데이터 형식 `number1` 및 `number2`합니다.</span><span class="sxs-lookup"><span data-stu-id="a8594-122">A numeric data type appropriate for the data types of `number1` and `number2`.</span></span> <span data-ttu-id="a8594-123">"정수 연산" 표를 참조 하십시오. [연산자 결과의 데이터 형식을](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a8594-123">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>|  
|<span data-ttu-id="a8594-124">두 식이 모두 [10 진수](../../../visual-basic/language-reference/data-types/decimal-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="a8594-124">Both expressions are [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="a8594-125">두 식이 모두 [단일](../../../visual-basic/language-reference/data-types/single-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="a8594-125">Both expressions are [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="a8594-126">두 식 중 하나가 부동 소수점 데이터 형식 (`Single` 또는 [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)) 중 하나만 `Single` (참고 `Decimal` 부동 소수점 데이터 형식이 아닌)</span><span class="sxs-lookup"><span data-stu-id="a8594-126">Either expression is a floating-point data type (`Single` or [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)) but not both `Single` (note `Decimal` is not a floating-point data type)</span></span>|`Double`|  
  
 <span data-ttu-id="a8594-127">식이 계산 될 경우 [Nothing](../../../visual-basic/language-reference/nothing.md)를 0으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8594-127">If an expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="a8594-128">오버로딩</span><span class="sxs-lookup"><span data-stu-id="a8594-128">Overloading</span></span>  
 <span data-ttu-id="a8594-129">`*` 연산자 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a8594-129">The `*` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="a8594-130">이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8594-130">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="a8594-131">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a8594-131">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8594-132">예제</span><span class="sxs-lookup"><span data-stu-id="a8594-132">Example</span></span>  
 <span data-ttu-id="a8594-133">사용 하 여이 예제는 `*` 두 숫자를 곱하기 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="a8594-133">This example uses the `*` operator to multiply two numbers.</span></span> <span data-ttu-id="a8594-134">결과 두 피연산자의 제품입니다.</span><span class="sxs-lookup"><span data-stu-id="a8594-134">The result is the product of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#4](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/multiplication-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a8594-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a8594-135">See Also</span></span>  
 [<span data-ttu-id="a8594-136">\*= 연산자</span><span class="sxs-lookup"><span data-stu-id="a8594-136">\*= Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)  
 [<span data-ttu-id="a8594-137">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="a8594-137">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="a8594-138">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="a8594-138">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="a8594-139">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="a8594-139">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="a8594-140">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="a8594-140">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
