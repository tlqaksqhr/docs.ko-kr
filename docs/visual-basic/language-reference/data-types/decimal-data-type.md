---
title: "Decimal 데이터 형식(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Decimal
helpviewer_keywords:
- literal type characters [Visual Basic], D
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- Decimal data type
- D literal type character [Visual Basic]
- decimals, Decimal data type
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- decimal keyword [Visual Basic]
- numbers [Visual Basic], real
- variable-precision numbers
- zeros, trailing
- '@ identifier type character'
- identifier type characters [Visual Basic], @
ms.assetid: 1d855b45-afe2-45b0-a623-96b6f63a43d5
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 55a9293fa680a7a04cff4099654d4d66790e8d3d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="decimal-data-type-visual-basic"></a><span data-ttu-id="020a2-102">Decimal 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="020a2-102">Decimal Data Type (Visual Basic)</span></span>
<span data-ttu-id="020a2-103">부호 있는 10의 거듭제곱으로 조정 된 96 비트 (12 바이트) 정수 숫자를 나타내는 128 비트 (16 바이트) 값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="020a2-103">Holds signed 128-bit (16-byte) values representing 96-bit (12-byte) integer numbers scaled by a variable power of 10.</span></span> <span data-ttu-id="020a2-104">소수점 오른쪽 자릿수의 수를 지정 하는 배율 인수 해당 범위는 0에서 28.</span><span class="sxs-lookup"><span data-stu-id="020a2-104">The scaling factor specifies the number of digits to the right of the decimal point; it ranges from 0 through 28.</span></span> <span data-ttu-id="020a2-105">가장 큰 가능한 값은 0 (소수 자릿수 없이) 배율로 79228162514264337593543950335 + /-(7 + /-.9228162514264337593543950335E + 28)입니다.</span><span class="sxs-lookup"><span data-stu-id="020a2-105">With a scale of 0 (no decimal places), the largest possible value is +/-79,228,162,514,264,337,593,543,950,335 (+/-7.9228162514264337593543950335E+28).</span></span> <span data-ttu-id="020a2-106">소수 자릿수가 28 인 + /-7.9228162514264337593543950335 사이, 가장 큰 값은 및 0.0000000000000000000000000001 1E-28) (+ + /-0이 아닌 값은입니다.</span><span class="sxs-lookup"><span data-stu-id="020a2-106">With 28 decimal places, the largest value is +/-7.9228162514264337593543950335, and the smallest nonzero value is +/-0.0000000000000000000000000001 (+/-1E-28).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="020a2-107">설명</span><span class="sxs-lookup"><span data-stu-id="020a2-107">Remarks</span></span>  
 <span data-ttu-id="020a2-108">`Decimal` 데이터 형식은 숫자에 대 한 최대 유효 자릿수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="020a2-108">The `Decimal` data type provides the greatest number of significant digits for a number.</span></span> <span data-ttu-id="020a2-109">최대 29 개의 유효 자릿수를 지원 하 고 7.9228 x 10도를 초과 하는 값을 나타낼 수 ^28입니다.</span><span class="sxs-lookup"><span data-stu-id="020a2-109">It supports up to 29 significant digits and can represent values in excess of 7.9228 x 10^28.</span></span> <span data-ttu-id="020a2-110">와 같은 계산에 특히 적합는 재무, 하는 많은 수의 자릿수를 필요로 하지만 반올림 오류를 허용할 수 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="020a2-110">It is particularly suitable for calculations, such as financial, that require a large number of digits but cannot tolerate rounding errors.</span></span>  
  
 <span data-ttu-id="020a2-111">`Decimal`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="020a2-111">The default value of `Decimal` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="020a2-112">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="020a2-112">Programming Tips</span></span>  
  
-   <span data-ttu-id="020a2-113">**전체 자릿수입니다.**</span><span class="sxs-lookup"><span data-stu-id="020a2-113">**Precision.**</span></span> <span data-ttu-id="020a2-114">`Decimal`부동 소수점 데이터 형식이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="020a2-114">`Decimal` is not a floating-point data type.</span></span> <span data-ttu-id="020a2-115">`Decimal` 구조 부호 비트 및 자릿수 소수 부분 값의 부분을 지정 하는 요소와 함께 이진 정수 값을 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="020a2-115">The `Decimal` structure holds a binary integer value, together with a sign bit and an integer scaling factor that specifies what portion of the value is a decimal fraction.</span></span> <span data-ttu-id="020a2-116">이 인해 `Decimal` 숫자가 부동 소수점 형식 보다 메모리에서 보다 정확 하 게 표현 (`Single` 및 `Double`).</span><span class="sxs-lookup"><span data-stu-id="020a2-116">Because of this, `Decimal` numbers have a more precise representation in memory than floating-point types (`Single` and `Double`).</span></span>  
  
-   <span data-ttu-id="020a2-117">**성능.**</span><span class="sxs-lookup"><span data-stu-id="020a2-117">**Performance.**</span></span> <span data-ttu-id="020a2-118">`Decimal` 데이터 형식은 가장 느린 모든 숫자 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="020a2-118">The `Decimal` data type is the slowest of all the numeric types.</span></span> <span data-ttu-id="020a2-119">데이터 형식을 선택 하기 전에 성능에 대 한 전체 자릿수의 중요성을 저울질 해봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="020a2-119">You should weigh the importance of precision against performance before choosing a data type.</span></span>  
  
-   <span data-ttu-id="020a2-120">**확대 합니다.**</span><span class="sxs-lookup"><span data-stu-id="020a2-120">**Widening.**</span></span> <span data-ttu-id="020a2-121">`Decimal` 데이터 형식으로 확대 되 `Single` 또는 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="020a2-121">The `Decimal` data type widens to `Single` or `Double`.</span></span> <span data-ttu-id="020a2-122">즉, 변환할 수 `Decimal` 발생 없이 이러한 형식 중 하나에 <xref:System.OverflowException?displayProperty=nameWithType> 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="020a2-122">This means you can convert `Decimal` to either of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="020a2-123">**뒤에 오는 0입니다.**</span><span class="sxs-lookup"><span data-stu-id="020a2-123">**Trailing Zeros.**</span></span> <span data-ttu-id="020a2-124">Visual Basic의 후행 0은 저장 되지 않습니다는 `Decimal` 리터럴.</span><span class="sxs-lookup"><span data-stu-id="020a2-124">Visual Basic does not store trailing zeros in a `Decimal` literal.</span></span> <span data-ttu-id="020a2-125">그러나 한 `Decimal` 변수 계산을 통해 얻은 후행 0 문자를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="020a2-125">However, a `Decimal` variable preserves any trailing zeros acquired computationally.</span></span> <span data-ttu-id="020a2-126">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="020a2-126">The following example illustrates this.</span></span>  
  
    ```  
    Dim d1, d2, d3, d4 As Decimal  
    d1 = 2.375D  
    d2 = 1.625D  
    d3 = d1 + d2  
    d4 = 4.000D  
    MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &  
          ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))  
    ```  
  
     <span data-ttu-id="020a2-127">출력 `MsgBox` 앞의 예제에는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="020a2-127">The output of `MsgBox` in the preceding example is as follows:</span></span>  
  
     <span data-ttu-id="020a2-128">d1 2.375, d2 = 1.625, d3 = 4.000, d4 = = 4</span><span class="sxs-lookup"><span data-stu-id="020a2-128">d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4</span></span>  
  
-   <span data-ttu-id="020a2-129">**형식 문자입니다.**</span><span class="sxs-lookup"><span data-stu-id="020a2-129">**Type Characters.**</span></span> <span data-ttu-id="020a2-130">리터럴 형식 문자 `D`를 리터럴에 추가하면 `Decimal` 데이터 형식이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="020a2-130">Appending the literal type character `D` to a literal forces it to the `Decimal` data type.</span></span> <span data-ttu-id="020a2-131">식별자 형식 문자 `@`를 식별자에 추가하면 `Decimal`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="020a2-131">Appending the identifier type character `@` to any identifier forces it to `Decimal`.</span></span>  
  
-   <span data-ttu-id="020a2-132">**Framework 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="020a2-132">**Framework Type.**</span></span> <span data-ttu-id="020a2-133">.NET Framework에서 해당하는 형식은 <xref:System.Decimal?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="020a2-133">The corresponding type in the .NET Framework is the <xref:System.Decimal?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="range"></a><span data-ttu-id="020a2-134">범위</span><span class="sxs-lookup"><span data-stu-id="020a2-134">Range</span></span>  
 <span data-ttu-id="020a2-135">사용 해야 할 수는 `D` 에 큰 값을 할당 하는 문자를 입력 한 `Decimal` 변수 또는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="020a2-135">You might need to use the `D` type character to assign a large value to a `Decimal` variable or constant.</span></span> <span data-ttu-id="020a2-136">컴파일러는 리터럴으로 해석 하기 때문에이 요구 사항은 `Long` 리터럴 형식 문자는 리터럴, 다음 예제와 같이 뒤 하지 않는 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="020a2-136">This requirement is because the compiler interprets a literal as `Long` unless a literal type character follows the literal, as the following example shows.</span></span>  
  
```  
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.  
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.  
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.  
```  
  
 <span data-ttu-id="020a2-137">에 대 한 선언을 `bigDec1` 에 할당 된 값에 대 한 범위 내에 있어야 하기 때문에 오버플로 생성 하지 않는 `Long`합니다.</span><span class="sxs-lookup"><span data-stu-id="020a2-137">The declaration for `bigDec1` doesn't produce an overflow because the value that's assigned to it falls within the range for `Long`.</span></span> <span data-ttu-id="020a2-138">`Long` 에 값을 지정할 수는 `Decimal` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="020a2-138">The `Long` value can be assigned to the `Decimal` variable.</span></span>  
  
 <span data-ttu-id="020a2-139">에 대 한 선언을 `bigDec2` 에 할당 된 값에 대 한 너무 크기 때문에 오버플로 오류가 `Long`합니다.</span><span class="sxs-lookup"><span data-stu-id="020a2-139">The declaration for `bigDec2` generates an overflow error because the value that's assigned to it is too large for `Long`.</span></span> <span data-ttu-id="020a2-140">숫자 리터럴으로 해석할 수 없는 먼저 때문에 `Long`에 할당할 수 없습니다는 `Decimal` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="020a2-140">Because the numeric literal can't first be interpreted as a `Long`, it can't be assigned to the `Decimal` variable.</span></span>  
  
 <span data-ttu-id="020a2-141">에 대 한 `bigDec3`, 리터럴 형식 문자 `D` 는 컴파일러가 리터럴을 해석 하 여 문제를 해결 한 `Decimal` 대신으로 `Long`합니다.</span><span class="sxs-lookup"><span data-stu-id="020a2-141">For `bigDec3`, the literal type character `D` solves the problem by forcing the compiler to interpret the literal as a `Decimal` instead of as a `Long`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="020a2-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="020a2-142">See Also</span></span>  
 <xref:System.Decimal?displayProperty=nameWithType>  
 <xref:System.Decimal.%23ctor%2A?displayProperty=nameWithType>  
 <xref:System.Math.Round%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="020a2-143">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="020a2-143">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="020a2-144">Single 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="020a2-144">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)  
 [<span data-ttu-id="020a2-145">Double 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="020a2-145">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)  
 [<span data-ttu-id="020a2-146">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="020a2-146">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="020a2-147">변환 요약</span><span class="sxs-lookup"><span data-stu-id="020a2-147">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="020a2-148">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="020a2-148">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
