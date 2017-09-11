---
title: "숫자 데이터 형식 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- integral types, Visual Basic
- Short data type, numeric data types
- Double data type, numeric data types
- Long data type, Visual Basic numeric data types
- numbers, whole
- fractions
- numbers
- whole numbers
- integer numbers
- numbers, integer
- fractional data types
- mantissas, of fractional numbers
- mantissas
- data types [Visual Basic], numeric
- Integer data type, numeric data types
- exponent, of fractional numbers
- integers
- numeric data types, Visual Basic
- Single data type, numeric types
- Decimal data type, numeric data types
ms.assetid: a27bd4d0-7e14-43eb-9cc4-b42eaab323c9
caps.latest.revision: 25
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
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: af87b895c04cf89ba217c9c3a46dc259103d50b4
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="numeric-data-types-visual-basic"></a><span data-ttu-id="71f5a-102">숫자 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="71f5a-102">Numeric Data Types (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="71f5a-103">몇 가지 제공 *숫자 데이터 형식* 다양 한 표현에서 숫자 처리할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-103"> supplies several *numeric data types* for handling numbers in various representations.</span></span> <span data-ttu-id="71f5a-104">*정수 계열* 형식은 나타냅니다 정수만 (양수, 음수 및&0;) 및 *비정 수 계열* 형식은 정수 부분과 소수 부분을 모두 있는 숫자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-104">*Integral* types represent only whole numbers (positive, negative, and zero), and *nonintegral* types represent numbers with both integer and fractional parts.</span></span>  
  
 <span data-ttu-id="71f5a-105">나란히 비교를 보여 주는 표는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 데이터 형식 참조 [데이터 형식](../../../../visual-basic/language-reference/data-types/data-type-summary.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-105">For a table showing a side-by-side comparison of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types, see [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span></span>  
  
## <a name="integral-numeric-types"></a><span data-ttu-id="71f5a-106">정수 계열 숫자 형식</span><span class="sxs-lookup"><span data-stu-id="71f5a-106">Integral Numeric Types</span></span>  
 <span data-ttu-id="71f5a-107">*정수 계열 데이터 형식* 는 소수 부분 없이 유일한 숫자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-107">*Integral data types* are those that represent only numbers without fractional parts.</span></span>  
  
 <span data-ttu-id="71f5a-108">*서명* 정수 데이터 형식이 [SByte 데이터 형식](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md) (8 비트), [Short 데이터 형식](../../../../visual-basic/language-reference/data-types/short-data-type.md) (16 비트), [정수 데이터 형식](../../../../visual-basic/language-reference/data-types/integer-data-type.md) (32 비트) 및 [Long 데이터 형식](../../../../visual-basic/language-reference/data-types/long-data-type.md) (64 비트)입니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-108">The *signed* integral data types are [SByte Data Type](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md) (8-bit), [Short Data Type](../../../../visual-basic/language-reference/data-types/short-data-type.md) (16-bit), [Integer Data Type](../../../../visual-basic/language-reference/data-types/integer-data-type.md) (32-bit), and [Long Data Type](../../../../visual-basic/language-reference/data-types/long-data-type.md) (64-bit).</span></span> <span data-ttu-id="71f5a-109">변수는 항상 소수 자릿수 숫자 대신 정수를 저장, 경우에 이러한 형식 중 하나로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-109">If a variable always stores integers rather than fractional numbers, declare it as one of these types.</span></span>  
  
 <span data-ttu-id="71f5a-110">*서명 되지 않은* 정수 계열 형식은 [Byte 데이터 형식](../../../../visual-basic/language-reference/data-types/byte-data-type.md) (8 비트), [UShort 데이터 형식](../../../../visual-basic/language-reference/data-types/ushort-data-type.md) (16 비트), [UInteger 데이터 형식](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md) (32 비트) 및 [ULong 데이터 형식](../../../../visual-basic/language-reference/data-types/ulong-data-type.md) (64 비트)입니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-110">The *unsigned* integral types are [Byte Data Type](../../../../visual-basic/language-reference/data-types/byte-data-type.md) (8-bit), [UShort Data Type](../../../../visual-basic/language-reference/data-types/ushort-data-type.md) (16-bit), [UInteger Data Type](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md) (32-bit), and [ULong Data Type](../../../../visual-basic/language-reference/data-types/ulong-data-type.md) (64-bit).</span></span> <span data-ttu-id="71f5a-111">이진 데이터 또는 알 수 없는 특성의 데이터를 포함 하는 변수, 경우에 이러한 형식 중 하나로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-111">If a variable contains binary data, or data of unknown nature, declare it as one of these types.</span></span>  
  
### <a name="performance"></a><span data-ttu-id="71f5a-112">성능</span><span class="sxs-lookup"><span data-stu-id="71f5a-112">Performance</span></span>  
 <span data-ttu-id="71f5a-113">산술 연산에는 다른 데이터 형식과 정수 계열 형식 보다 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-113">Arithmetic operations are faster with integral types than with other data types.</span></span> <span data-ttu-id="71f5a-114">이들은와 가장 빠른는 `Integer` 및 `UInteger` 의 형식은 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-114">They are fastest with the `Integer` and `UInteger` types in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
### <a name="large-integers"></a><span data-ttu-id="71f5a-115">큰 정수</span><span class="sxs-lookup"><span data-stu-id="71f5a-115">Large Integers</span></span>  
 <span data-ttu-id="71f5a-116">보다 큰 정수를 저장 해야 하는 경우는 `Integer` 데이터 형식을 저장할 수 있는, 사용할 수는 `Long` 데이터 형식을 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-116">If you need to hold an integer larger than the `Integer` data type can hold, you can use the `Long` data type instead.</span></span> <span data-ttu-id="71f5a-117">`Long`변수는-9223372036854775808에서 9223372036854775807 까지의 숫자를 보유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-117">`Long` variables can hold numbers from -9,223,372,036,854,775,808 through 9,223,372,036,854,775,807.</span></span> <span data-ttu-id="71f5a-118">작업과 `Long` 와 보다 약간 더 느려집니다 `Integer`합니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-118">Operations with `Long` are slightly slower than with `Integer`.</span></span>  
  
 <span data-ttu-id="71f5a-119">이보다 훨씬 더 큰 값을 해야 하는 경우 사용할 수 있습니다는 [Decimal 데이터 형식](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-119">If you need even larger values, you can use the [Decimal Data Type](../../../../visual-basic/language-reference/data-types/decimal-data-type.md).</span></span> <span data-ttu-id="71f5a-120">79228162514264337593543950335 79228162514264337593543950335 ~ 까지의 숫자를 보유할 수는 `Decimal` 소수 자릿수를 사용 하지 않는 경우에 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-120">You can hold numbers from -79,228,162,514,264,337,593,543,950,335 through 79,228,162,514,264,337,593,543,950,335 in a `Decimal` variable if you do not use any decimal places.</span></span> <span data-ttu-id="71f5a-121">그러나 작업과 `Decimal` 번호는 다른 숫자 데이터 형식 보다 상당히 느립니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-121">However, operations with `Decimal` numbers are considerably slower than with any other numeric data type.</span></span>  
  
### <a name="small-integers"></a><span data-ttu-id="71f5a-122">작은 정수</span><span class="sxs-lookup"><span data-stu-id="71f5a-122">Small Integers</span></span>  
 <span data-ttu-id="71f5a-123">전체 범위를 필요 하지 않은 경우는 `Integer` 사용할 수 있는 데이터 형식는 `Short` -32, 768 32, 767 까지의 정수를 포함할 수 있는 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-123">If you do not need the full range of the `Integer` data type, you can use the `Short` data type, which can hold integers from -32,768 through 32,767.</span></span> <span data-ttu-id="71f5a-124">가장 작은 정수 범위는 `SByte` -128에서 127 까지의 정수를 저장 하는 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-124">For the smallest integer range, the `SByte` data type holds integers from -128 through 127.</span></span> <span data-ttu-id="71f5a-125">공용 언어 런타임 저장할 수 있습니다 작은 정수를 포함 하는 변수가 매우 많은 경우 프로그램 `Short` 및 `SByte` 변수 보다 효율적이 고 메모리 사용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-125">If you have a very large number of variables that hold small integers, the common language runtime can sometimes store your `Short` and `SByte` variables more efficiently and save memory consumption.</span></span> <span data-ttu-id="71f5a-126">그러나 작업과 `Short` 및 `SByte` 는와 보다 다소 느립니다 `Integer`합니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-126">However, operations with `Short` and `SByte` are somewhat slower than with `Integer`.</span></span>  
  
### <a name="unsigned-integers"></a><span data-ttu-id="71f5a-127">부호 없는 정수</span><span class="sxs-lookup"><span data-stu-id="71f5a-127">Unsigned Integers</span></span>  
 <span data-ttu-id="71f5a-128">변수는 음수를 포함할 필요가 사용할 수 있습니다 알고 있는 경우는 *부호 없는 형식*`Byte`, `UShort`, `UInteger`, 및 `ULong`합니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-128">If you know that your variable never needs to hold a negative number, you can use the *unsigned types*`Byte`, `UShort`, `UInteger`, and `ULong`.</span></span> <span data-ttu-id="71f5a-129">양의 정수를 크기의 두 배 해당 부호 있는 형식으로 저장할 수 있는 이러한 각 유형의 데이터 (`SByte`, `Short`, `Integer`, 및 `Long`).</span><span class="sxs-lookup"><span data-stu-id="71f5a-129">Each of these data types can hold a positive integer twice as large as its corresponding signed type (`SByte`, `Short`, `Integer`, and `Long`).</span></span> <span data-ttu-id="71f5a-130">성능의 측면에서 서명 되지 않은 각 유형은 해당 부호 있는 형식으로 정확 하 게 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-130">In terms of performance, each unsigned type is exactly as efficient as its corresponding signed type.</span></span> <span data-ttu-id="71f5a-131">특히, `UInteger` 와 공유 `Integer` 구별할 모든 기본 숫자 데이터 형식 중에서 가장 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-131">In particular, `UInteger` shares with `Integer` the distinction of being the most efficient of all the elementary numeric data types.</span></span>  
  
## <a name="nonintegral-numeric-types"></a><span data-ttu-id="71f5a-132">비정 수 숫자 형식</span><span class="sxs-lookup"><span data-stu-id="71f5a-132">Nonintegral Numeric Types</span></span>  
 <span data-ttu-id="71f5a-133">*비정 수 데이터 형식* 은 정수와 소수 부분을 사용 하 여 숫자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-133">*Nonintegral data types* are those that represent numbers with both integer and fractional parts.</span></span>  
  
 <span data-ttu-id="71f5a-134">비정 수 숫자 데이터 형식은 `Decimal` (128 비트 고정된 소수점) [단일 데이터 형식](../../../../visual-basic/language-reference/data-types/single-data-type.md) (32 비트 부동 소수점) 및 [Double 데이터 형식](../../../../visual-basic/language-reference/data-types/double-data-type.md) (64 비트 부동 소수점).</span><span class="sxs-lookup"><span data-stu-id="71f5a-134">The nonintegral numeric data types are `Decimal` (128-bit fixed point), [Single Data Type](../../../../visual-basic/language-reference/data-types/single-data-type.md) (32-bit floating point), and [Double Data Type](../../../../visual-basic/language-reference/data-types/double-data-type.md) (64-bit floating point).</span></span> <span data-ttu-id="71f5a-135">서명 된 전체 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-135">They are all signed types.</span></span> <span data-ttu-id="71f5a-136">변수 분수를 포함할 수 있으면 이러한 형식 중 하나로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-136">If a variable can contain a fraction, declare it as one of these types.</span></span>  
  
 <span data-ttu-id="71f5a-137">`Decimal`부동 소수점 데이터 형식이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-137">`Decimal` is not a floating-point data type.</span></span> <span data-ttu-id="71f5a-138">`Decimal`숫자에는 이진 정수 값 있고 소수 값의 부분을 지정 하는 정수 배율 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-138">`Decimal` numbers have a binary integer value and an integer scaling factor that specifies what portion of the value is a decimal fraction.</span></span>  
  
 <span data-ttu-id="71f5a-139">사용할 수 있습니다 `Decimal` money 값에 대 한 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-139">You can use `Decimal` variables for money values.</span></span> <span data-ttu-id="71f5a-140">장점은 값의 정밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-140">The advantage is the precision of the values.</span></span> <span data-ttu-id="71f5a-141">`Double` 데이터 형식은 빠릅니다 메모리를 적게 사용 하지만 반올림 오류 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-141">The `Double` data type is faster and requires less memory, but it is subject to rounding errors.</span></span> <span data-ttu-id="71f5a-142">`Decimal` 데이터 형식에 소수 자릿수가 28 정확성을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-142">The `Decimal` data type retains complete accuracy to 28 decimal places.</span></span>  
  
 <span data-ttu-id="71f5a-143">부동 소수점 (`Single` 및 `Double`) 보다 더 큰 범위를 포함 하는 숫자 `Decimal` 숫자 이지만 반올림 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-143">Floating-point (`Single` and `Double`) numbers have larger ranges than `Decimal` numbers but can be subject to rounding errors.</span></span> <span data-ttu-id="71f5a-144">부동 소수점 형식 지원 보다 적은 유효 자릿수 `Decimal` 하지만 더 큰 값을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-144">Floating-point types support fewer significant digits than `Decimal` but can represent values of greater magnitude.</span></span>  
  
 <span data-ttu-id="71f5a-145">비정 수 숫자 값으로 표현 될 수 mmmEeee에서 mmm 인는 *가 수* (유효 자릿수가)은 여 *지 수* (10의 거듭제곱).</span><span class="sxs-lookup"><span data-stu-id="71f5a-145">Nonintegral number values can be expressed as mmmEeee, in which mmm is the *mantissa* (the significant digits) and eee is the *exponent* (a power of 10).</span></span> <span data-ttu-id="71f5a-146">비정 수 형식의 가장 큰 양수 값은 7.9228162514264337593543950335 e + 28 `Decimal`, 3.4028235 e + 38 `Single`, 및에 대 한 1.79769313486231570 e + 308 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-146">The highest positive values of the nonintegral types are 7.9228162514264337593543950335E+28 for `Decimal`, 3.4028235E+38 for `Single`, and 1.79769313486231570E+308 for `Double`.</span></span>  
  
### <a name="performance"></a><span data-ttu-id="71f5a-147">성능</span><span class="sxs-lookup"><span data-stu-id="71f5a-147">Performance</span></span>  
 <span data-ttu-id="71f5a-148">`Double`소수 데이터 형식 중 가장 효율적인 이므로 현재 플랫폼의 프로세서 배정밀도의 부동 소수점 연산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-148">`Double` is the most efficient of the fractional data types, because the processors on current platforms perform floating-point operations in double precision.</span></span> <span data-ttu-id="71f5a-149">그러나 작업과 `Double` 과 같은 정수 계열 형식에서와 마찬가지로 빠르지 않습니다 `Integer`합니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-149">However, operations with `Double` are not as fast as with the integral types such as `Integer`.</span></span>  
  
### <a name="small-magnitudes"></a><span data-ttu-id="71f5a-150">작은 크기</span><span class="sxs-lookup"><span data-stu-id="71f5a-150">Small Magnitudes</span></span>  
 <span data-ttu-id="71f5a-151">(0에 가장 가까운), 가능한 가장 작은 크기를 사용 하 여 숫자에 대 한 `Double` 변수-4.94065645841246544E로 작은 숫자를 보유할 수 있습니다-음수 값과 4.94065645841246544E 324-324 양수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-151">For numbers with the smallest possible magnitude (closest to 0), `Double` variables can hold numbers as small as -4.94065645841246544E-324 for negative values and 4.94065645841246544E-324 for positive values.</span></span>  
  
### <a name="small-fractional-numbers"></a><span data-ttu-id="71f5a-152">작은 소수</span><span class="sxs-lookup"><span data-stu-id="71f5a-152">Small Fractional Numbers</span></span>  
 <span data-ttu-id="71f5a-153">전체 범위를 필요 하지 않은 경우는 `Double` 사용할 수 있는 데이터 형식는 `Single` -3.4028235 e + 38에서 3.4028235 e + 38 까지의 부동 소수점 숫자를 사용할 수 있는 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-153">If you do not need the full range of the `Double` data type, you can use the `Single` data type, which can hold floating-point numbers from -3.4028235E+38 through 3.4028235E+38.</span></span> <span data-ttu-id="71f5a-154">사용할 수 있는 가장 작은 크기 `Single` 변수는-1.401298 e-45 음수 값 및 1.401298 e-45 양수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-154">The smallest magnitudes for `Single` variables are -1.401298E-45 for negative values and 1.401298E-45 for positive values.</span></span> <span data-ttu-id="71f5a-155">공용 언어 런타임 저장할 수 있습니다 작은 부동 소수점 숫자를 포함 하는 변수가 매우 많은 경우 프로그램 `Single` 변수 보다 효율적이 고 메모리 사용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="71f5a-155">If you have a very large number of variables that hold small floating-point numbers, the common language runtime can sometimes store your `Single` variables more efficiently and save memory consumption.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71f5a-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="71f5a-156">See Also</span></span>  
 <span data-ttu-id="71f5a-157">[기본 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="71f5a-157">[Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span></span>  
<span data-ttu-id="71f5a-158"> [문자 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="71f5a-158"> [Character Data Types](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md) </span></span>  
<span data-ttu-id="71f5a-159"> [기타 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/miscellaneous-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="71f5a-159"> [Miscellaneous Data Types](../../../../visual-basic/programming-guide/language-features/data-types/miscellaneous-data-types.md) </span></span>  
<span data-ttu-id="71f5a-160"> [데이터 형식 문제 해결](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="71f5a-160"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
<span data-ttu-id="71f5a-161"> [방법: 부호 없는 형식을 사용하는 Windows 함수 호출](../../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)</span><span class="sxs-lookup"><span data-stu-id="71f5a-161"> [How to: Call a Windows Function that Takes Unsigned Types](../../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)</span></span>
