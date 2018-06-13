---
title: 형식 변환 함수(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.CUShort
- vb.csng
- vb.CDate
- CByte
- CSng
- vb.CDec
- CBool
- CStr
- vb.CULng
- CDec
- CVErr
- CDbl
- CShort
- vb.CObj
- vb.CVErr
- CULng
- vb.cdbl
- vb.cbool
- CObj
- CDate
- CLng
- vb.cstr
- vb.cbyte
- vb.clng
- vb.CChar
- CUShort
- vb.CUInt
- vb.cint
- vb.CShort
- CInt
- CUInt
- CChar
helpviewer_keywords:
- CDate function
- CByte function
- Integer data type [Visual Basic], converting
- string conversion [Visual Basic], conversion functions
- fractions
- data types [Visual Basic], converting
- text, converting
- CDec function
- Char data type [Visual Basic], converting
- type conversion [Visual Basic], functions for
- Single data type [Visual Basic], converting
- numbers [Visual Basic], rounding
- rounding numbers [Visual Basic], type conversion
- CUShort function
- Long data type [Visual Basic], converting
- return values [Visual Basic], data types
- single-precision numbers [Visual Basic], converting
- data type conversion [Visual Basic], functions for
- CStr function
- times [Visual Basic], converting
- CSng function
- conversions [Visual Basic], type conversion functions
- CBool function
- CDbl function
- CUInt function
- Currency data type [Visual Basic], conversion functions
- numbers [Visual Basic], converting
- Double data type [Visual Basic], converting
- CLng function
- CSByte function
- double-precision numbers
- Decimal data type [Visual Basic], converting
- Boolean data type [Visual Basic], converting
- integers [Visual Basic], type conversion functions
- dates [Visual Basic], converting
- CULng function
- CInt function
- Date data type [Visual Basic], converting
- Byte data type [Visual Basic], converting
- String data type [Visual Basic], converting
- CChar function
- banker's rounding
- Short data type [Visual Basic], converting
- rounding numbers [Visual Basic], banker's rounding
- type conversion [Visual Basic], Visual Basic vs. .NET Framework
ms.assetid: d9d8d165-f967-44ff-a6cd-598e4740a99e
ms.openlocfilehash: c9222bdb31f4fd7c792d5a50c100067e29e9d537
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605084"
---
# <a name="type-conversion-functions-visual-basic"></a><span data-ttu-id="af4cd-102">형식 변환 함수(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af4cd-102">Type Conversion Functions (Visual Basic)</span></span>
<span data-ttu-id="af4cd-103">이러한 함수는 인라인으로 컴파일됩니다 변환 코드는 식을 계산 하는 코드의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-103">These functions are compiled inline, meaning the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="af4cd-104">경우에 따라 성능이 향상 되는 변환을 수행 하는 프로시저에 대 한 호출이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-104">Sometimes there is no call to a procedure to accomplish the conversion, which improves performance.</span></span> <span data-ttu-id="af4cd-105">각 함수는 식을 특정 데이터 형식으로 강제 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-105">Each function coerces an expression to a specific data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af4cd-106">구문</span><span class="sxs-lookup"><span data-stu-id="af4cd-106">Syntax</span></span>  
  
```  
CBool(expression)  
CByte(expression)  
CChar(expression)  
CDate(expression)  
CDbl(expression)  
CDec(expression)  
CInt(expression)  
CLng(expression)  
CObj(expression)  
CSByte(expression)  
CShort(expression)  
CSng(expression)  
CStr(expression)  
CUInt(expression)  
CULng(expression)  
CUShort(expression)  
```  
  
## <a name="part"></a><span data-ttu-id="af4cd-107">파트</span><span class="sxs-lookup"><span data-stu-id="af4cd-107">Part</span></span>  
 `expression`  
 <span data-ttu-id="af4cd-108">필수.</span><span class="sxs-lookup"><span data-stu-id="af4cd-108">Required.</span></span> <span data-ttu-id="af4cd-109">원본 데이터 형식의 모든 식입니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-109">Any expression of the source data type.</span></span>  
  
## <a name="return-value-data-type"></a><span data-ttu-id="af4cd-110">반환 값 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="af4cd-110">Return Value Data Type</span></span>  
 <span data-ttu-id="af4cd-111">다음 표에 나와 있는 것 처럼 반환 하는 값의 데이터 형식을 결정 하는 함수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-111">The function name determines the data type of the value it returns, as shown in the following table.</span></span>  
  
|<span data-ttu-id="af4cd-112">함수 이름</span><span class="sxs-lookup"><span data-stu-id="af4cd-112">Function name</span></span>|<span data-ttu-id="af4cd-113">반환 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="af4cd-113">Return data type</span></span>|<span data-ttu-id="af4cd-114">에 대 한 범위 `expression` 인수</span><span class="sxs-lookup"><span data-stu-id="af4cd-114">Range for `expression` argument</span></span>|  
|-------------------|----------------------|-------------------------------------|  
|`CBool`|[<span data-ttu-id="af4cd-115">Boolean 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="af4cd-115">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="af4cd-116">모든 유효한 `Char` 또는 `String` 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-116">Any valid `Char` or `String` or numeric expression.</span></span>|  
|`CByte`|[<span data-ttu-id="af4cd-117">Byte 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="af4cd-117">Byte Data Type</span></span>](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="af4cd-118">0부터 255 (부호 없음). 소수 부분이 반올림 됩니다. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="af4cd-118">0 through 255 (unsigned); fractional parts are rounded.<sup>1</sup></span></span>|  
|`CChar`|[<span data-ttu-id="af4cd-119">Char 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="af4cd-119">Char Data Type</span></span>](../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="af4cd-120">모든 유효한 `Char` 또는 `String` 식;의 첫 번째 문자만 `String` 변환 됩니다; 값 0 ~ 65535 (부호 없음) 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-120">Any valid `Char` or `String` expression; only first character of a `String` is converted; value can be 0 through 65535 (unsigned).</span></span>|  
|`CDate`|[<span data-ttu-id="af4cd-121">Date 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="af4cd-121">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="af4cd-122">날짜 및 시간의 유효한 표현을 합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-122">Any valid representation of a date and time.</span></span>|  
|`CDbl`|[<span data-ttu-id="af4cd-123">Double 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="af4cd-123">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)|<span data-ttu-id="af4cd-124">-1.79769313486231570 e + 308에서-4.94065645841246544E-소수점; 4.94065645841246544E-324 1.79769313486231570 e + 308 양수 값에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-124">-1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values; 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span>|  
|`CDec`|[<span data-ttu-id="af4cd-125">Decimal 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="af4cd-125">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="af4cd-126">+ /-79228162514264337593543950335-즉, 소수 자릿수가 없는 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-126">+/-79,228,162,514,264,337,593,543,950,335 for zero-scaled numbers, that is, numbers with no decimal places.</span></span> <span data-ttu-id="af4cd-127">소수 자릿수가 28 숫자에 대 한 범위는 + /-7.9228162514264337593543950335 사이입니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-127">For numbers with 28 decimal places, the range is +/-7.9228162514264337593543950335.</span></span> <span data-ttu-id="af4cd-128">0이 아닌 수를 최소로 0.0000000000000000000000000001 (+ 1E-28)입니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-128">The smallest possible non-zero number is 0.0000000000000000000000000001 (+/-1E-28).</span></span>|  
|`CInt`|[<span data-ttu-id="af4cd-129">Integer 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="af4cd-129">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="af4cd-130">-2147483648 ~ 2147483647; 소수 부분이 반올림 됩니다. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="af4cd-130">-2,147,483,648 through 2,147,483,647; fractional parts are rounded.<sup>1</sup></span></span>|  
|`CLng`|[<span data-ttu-id="af4cd-131">Long 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="af4cd-131">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="af4cd-132">-9223372036854775808에서 9223372036854775807; 소수 부분이 반올림 됩니다. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="af4cd-132">-9,223,372,036,854,775,808 through 9,223,372,036,854,775,807; fractional parts are rounded.<sup>1</sup></span></span>|  
|`CObj`|[<span data-ttu-id="af4cd-133">Object 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="af4cd-133">Object Data Type</span></span>](../../../visual-basic/language-reference/data-types/object-data-type.md)|<span data-ttu-id="af4cd-134">모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-134">Any valid expression.</span></span>|  
|`CSByte`|[<span data-ttu-id="af4cd-135">SByte 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="af4cd-135">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="af4cd-136">-128에서 127; 소수 부분이 반올림 됩니다. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="af4cd-136">-128 through 127; fractional parts are rounded.<sup>1</sup></span></span>|  
|`CShort`|[<span data-ttu-id="af4cd-137">Short 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="af4cd-137">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="af4cd-138">-32, 768 32, 767; 소수 부분이 반올림 됩니다. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="af4cd-138">-32,768 through 32,767; fractional parts are rounded.<sup>1</sup></span></span>|  
|`CSng`|[<span data-ttu-id="af4cd-139">Single 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="af4cd-139">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="af4cd-140">-3.402823E + 38에서-1.401298 e-45 음수 값이 있습니다. 1.401298 e-45 3.402823E + 38 양수 값에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-140">-3.402823E+38 through -1.401298E-45 for negative values; 1.401298E-45 through 3.402823E+38 for positive values.</span></span>|  
|`CStr`|[<span data-ttu-id="af4cd-141">String 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="af4cd-141">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)|<span data-ttu-id="af4cd-142">에 대 한 반환 `CStr` 에 종속 된 `expression` 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-142">Returns for `CStr` depend on the `expression` argument.</span></span> <span data-ttu-id="af4cd-143">참조 [CStr 함수의 반환 값](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-143">See [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span></span>|  
|`CUInt`|[<span data-ttu-id="af4cd-144">UInteger 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="af4cd-144">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="af4cd-145">0 ~ 4294967295 (부호 없음). 소수 부분이 반올림 됩니다. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="af4cd-145">0 through 4,294,967,295 (unsigned); fractional parts are rounded.<sup>1</sup></span></span>|  
|`CULng`|[<span data-ttu-id="af4cd-146">ULong 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="af4cd-146">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="af4cd-147">0에서 18446744073709551615 (부호 없음). 소수 부분이 반올림 됩니다. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="af4cd-147">0 through 18,446,744,073,709,551,615 (unsigned); fractional parts are rounded.<sup>1</sup></span></span>|  
|`CUShort`|[<span data-ttu-id="af4cd-148">UShort 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="af4cd-148">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="af4cd-149">0-65535 (부호 없음). 소수 부분이 반올림 됩니다. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="af4cd-149">0 through 65,535 (unsigned); fractional parts are rounded.<sup>1</sup></span></span>|  
  
 <span data-ttu-id="af4cd-150"><sup>1</sup> 소수 부분이 호출 반올림 하는 특수 한 유형의 영향을 받을 수 *banker rounding*합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-150"><sup>1</sup> Fractional parts can be subject to a special type of rounding called *banker's rounding*.</span></span> <span data-ttu-id="af4cd-151">자세한 내용은 "주의"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="af4cd-151">See "Remarks" for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af4cd-152">설명</span><span class="sxs-lookup"><span data-stu-id="af4cd-152">Remarks</span></span>  
 <span data-ttu-id="af4cd-153">일반적으로.NET Framework 메서드 대신 Visual Basic 형식 변환 함수를와 같은 사용 해야 `ToString()`, 중 하나에 <xref:System.Convert> 클래스 또는 개별 형식 구조체 또는 클래스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-153">As a rule, you should use the Visual Basic type conversion functions in preference to the .NET Framework methods such as `ToString()`, either on the <xref:System.Convert> class or on an individual type structure or class.</span></span> <span data-ttu-id="af4cd-154">Visual Basic 함수는 Visual Basic 코드와의 최적의 상호 작용을 위한 하 고 더 짧게 만들어 더 쉽게 읽을 수 소스 코드 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-154">The Visual Basic functions are designed for optimal interaction with Visual Basic code, and they also make your source code shorter and easier to read.</span></span> <span data-ttu-id="af4cd-155">또한.NET Framework의 변환 메서드는이 Visual Basic 함수 예를 들어 변환할 때와 동일한 결과 항상 생성 하지 않는 `Boolean` 를 `Integer`합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-155">In addition, the .NET Framework conversion methods do not always produce the same results as the Visual Basic functions, for example when converting `Boolean` to `Integer`.</span></span> <span data-ttu-id="af4cd-156">자세한 내용은 참조 [데이터 형식 문제 해결](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-156">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="af4cd-157">동작</span><span class="sxs-lookup"><span data-stu-id="af4cd-157">Behavior</span></span>  
  
-   <span data-ttu-id="af4cd-158">**강제 변환 합니다.**</span><span class="sxs-lookup"><span data-stu-id="af4cd-158">**Coercion.**</span></span> <span data-ttu-id="af4cd-159">일반적으로 기본 데이터 형식을 보다는 특정 데이터 형식에 대 한 작업의 결과 강제 변환할 데이터 형식 변환 함수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-159">In general, you can use the data type conversion functions to coerce the result of an operation to a particular data type rather than the default data type.</span></span> <span data-ttu-id="af4cd-160">예를 들어 사용 `CDec` 여기서 단 정밀도, 두 자리 또는 정수 산술이 정상적으로 수행 하는 경우에는 10 진수 연산을 합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-160">For example, use `CDec` to force decimal arithmetic in cases where single-precision, double-precision, or integer arithmetic would normally take place.</span></span>  
  
-   <span data-ttu-id="af4cd-161">**변환 실패입니다.**</span><span class="sxs-lookup"><span data-stu-id="af4cd-161">**Failed Conversions.**</span></span> <span data-ttu-id="af4cd-162">경우는 `expression` 함수에 전달 된 범위를 벗어났습니다 데이터 형식의 변환 될 수 있는는 <xref:System.OverflowException> 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-162">If the `expression` passed to the function is outside the range of the data type to which it is to be converted, an <xref:System.OverflowException> occurs.</span></span>  
  
-   <span data-ttu-id="af4cd-163">**소수 부분입니다.**</span><span class="sxs-lookup"><span data-stu-id="af4cd-163">**Fractional Parts.**</span></span> <span data-ttu-id="af4cd-164">정수 계열에 정수가 아닌 값을 변환 하는 경우 입력, 정수 변환 함수 (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, 및 `CUShort`) 제거는 소수 부분 및 값을 가장 가까운 정수로 반올림 합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-164">When you convert a nonintegral value to an integral type, the integer conversion functions (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, and `CUShort`) remove the fractional part and round the value to the closest integer.</span></span>  
  
     <span data-ttu-id="af4cd-165">소수 부분이 정확 하 게 하는 경우 0.5 정수 변환 함수 반올림 하는 가장 근사한 짝수 정수로 합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-165">If the fractional part is exactly 0.5, the integer conversion functions round it to the nearest even integer.</span></span> <span data-ttu-id="af4cd-166">예를 들어 0.5 0 및 1.5와 2.5는 2로 반올림을 반올림 합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-166">For example, 0.5 rounds to 0, and 1.5 and 2.5 both round to 2.</span></span> <span data-ttu-id="af4cd-167">이 라고도 *banker rounding*와 함께 이러한 많은 숫자를 추가 하는 경우 누적 될 수 있는 편차에 대 한 보정 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-167">This is sometimes called *banker's rounding*, and its purpose is to compensate for a bias that could accumulate when adding many such numbers together.</span></span>  
  
     <span data-ttu-id="af4cd-168">`CInt` 및 `CLng` 에서 다는 <xref:Microsoft.VisualBasic.Conversion.Int%2A> 및 <xref:Microsoft.VisualBasic.Conversion.Fix%2A> 숫자의 소수 부분을 반올림 하지 않고, truncate는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-168">`CInt` and `CLng` differ from the <xref:Microsoft.VisualBasic.Conversion.Int%2A> and <xref:Microsoft.VisualBasic.Conversion.Fix%2A> functions, which truncate, rather than round, the fractional part of a number.</span></span> <span data-ttu-id="af4cd-169">또한 `Fix` 및 `Int` 에서 전달 항상 동일한 데이터 형식의 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-169">Also, `Fix` and `Int` always return a value of the same data type as you pass in.</span></span>  
  
-   <span data-ttu-id="af4cd-170">**날짜/시간 변환 합니다.**</span><span class="sxs-lookup"><span data-stu-id="af4cd-170">**Date/Time Conversions.**</span></span> <span data-ttu-id="af4cd-171">사용 된 <xref:Microsoft.VisualBasic.Information.IsDate%2A> 을 날짜 및 시간 값을 변환할 수 있는지 확인 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-171">Use the <xref:Microsoft.VisualBasic.Information.IsDate%2A> function to determine if a value can be converted to a date and time.</span></span> <span data-ttu-id="af4cd-172">`CDate` 리터럴 날짜 및 시간 리터럴 하지만 숫자 값이 아니라 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-172">`CDate` recognizes date literals and time literals but not numeric values.</span></span> <span data-ttu-id="af4cd-173">Visual Basic 6.0 변환할 `Date` 값을 한 `Date` Visual Basic 2005에서에서 값 또는 이상 버전을 사용할 수 있습니다는 <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="af4cd-173">To convert a Visual Basic 6.0 `Date` value to a `Date` value in Visual Basic 2005 or later versions, you can use the <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="af4cd-174">**중립 날짜/시간 값입니다.**</span><span class="sxs-lookup"><span data-stu-id="af4cd-174">**Neutral Date/Time Values.**</span></span> <span data-ttu-id="af4cd-175">[Date 데이터 형식](../../../visual-basic/language-reference/data-types/date-data-type.md) 항상 날짜와 시간 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-175">The [Date Data Type](../../../visual-basic/language-reference/data-types/date-data-type.md) always contains both date and time information.</span></span> <span data-ttu-id="af4cd-176">형식 변환을 위해 Visual Basic 간주 1/1/0001 (1 1 년 1 월)는 *기본값으로* 시간에 대 한 기본값으로 간주 00시: 00 (자정) 및 날짜,입니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-176">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="af4cd-177">변환 하는 경우는 `Date` 값을 문자열로, `CStr` 기본값이 결과 문자열에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-177">If you convert a `Date` value to a string, `CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="af4cd-178">예를 들어, 변환 하면 `#January 1, 0001 9:30:00#` 문자열로 결과 "오전 9시 30분: 00" 하 고 날짜 정보는 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-178">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="af4cd-179">그러나 날짜 정보에에서는 아직 있는 원래 `Date` 값 및와 같은 함수를 사용 하 여 복구할 수 수 <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-179">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> function.</span></span>  
  
-   <span data-ttu-id="af4cd-180">**문화권 구분 합니다.**</span><span class="sxs-lookup"><span data-stu-id="af4cd-180">**Culture Sensitivity.**</span></span> <span data-ttu-id="af4cd-181">응용 프로그램에 대 한 현재 문화권 설정에 따라 변환을 수행 하는 문자열을 포함 하는 형식 변환 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-181">The type conversion functions involving strings perform conversions based on the current culture settings for the application.</span></span> <span data-ttu-id="af4cd-182">예를 들어 `CDate` 시스템의 로캘 설정에 따라 날짜 형식을 인식 합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-182">For example, `CDate` recognizes date formats according to the locale setting of your system.</span></span> <span data-ttu-id="af4cd-183">일, 월 및 연도 사용자 로캘에 대 한 올바른 순서로 제공 해야 하거나 날짜 올바르게 해석 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-183">You must provide the day, month, and year in the correct order for your locale, or the date might not be interpreted correctly.</span></span> <span data-ttu-id="af4cd-184">자세한 날짜 형식에는 "수요일" 등의 주 일 문자열을 포함 하는 경우 인식 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-184">A long date format is not recognized if it contains a day-of-the-week string, such as "Wednesday".</span></span>  
  
     <span data-ttu-id="af4cd-185">사용자의 로캘에 따라 지정 되어 있지 않은 형식에 있는 값의 문자열 표현으로 변환 하는 경우 Visual Basic 형식 변환 함수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-185">If you need to convert to or from a string representation of a value in a format other than the one specified by your locale, you cannot use the Visual Basic type conversion functions.</span></span> <span data-ttu-id="af4cd-186">이 위해 사용 하 여는 `ToString(IFormatProvider)` 및 `Parse(String, IFormatProvider)` 해당 값 형식의 메서드.</span><span class="sxs-lookup"><span data-stu-id="af4cd-186">To do this, use the `ToString(IFormatProvider)` and `Parse(String, IFormatProvider)` methods of that value's type.</span></span> <span data-ttu-id="af4cd-187">사용 예를 들어 <xref:System.Double.Parse%2A?displayProperty=nameWithType> 문자열을 변환 하는 경우는 `Double`를 사용 하 여 <xref:System.Double.ToString%2A?displayProperty=nameWithType> 형식의 값을 변환할 때 `Double` 문자열로 합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-187">For example, use <xref:System.Double.Parse%2A?displayProperty=nameWithType> when converting a string to a `Double`, and use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a string.</span></span>  
  
## <a name="ctype-function"></a><span data-ttu-id="af4cd-188">CType Function</span><span class="sxs-lookup"><span data-stu-id="af4cd-188">CType Function</span></span>  
 <span data-ttu-id="af4cd-189">[CType 함수](../../../visual-basic/language-reference/functions/ctype-function.md) 두 번째 인수를 받으며 `typename`, 강제 `expression` 를 `typename`여기서 `typename` 데이터 형식, 구조체, 클래스 또는 인터페이스에 있는 유효한 변환 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-189">The [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) takes a second argument, `typename`, and coerces `expression` to `typename`, where `typename` can be any data type, structure, class, or interface to which there exists a valid conversion.</span></span>  
  
 <span data-ttu-id="af4cd-190">에 대 한 비교 `CType` 참조와 다른 형식 변환 키워드, [DirectCast 연산자](../../../visual-basic/language-reference/operators/directcast-operator.md) 및 [TryCast 연산자](../../../visual-basic/language-reference/operators/trycast-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-190">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) and [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span>  
  
## <a name="cbool-example"></a><span data-ttu-id="af4cd-191">CBool 예제</span><span class="sxs-lookup"><span data-stu-id="af4cd-191">CBool Example</span></span>  
 <span data-ttu-id="af4cd-192">다음 예제에서는 `CBool` 식을 변환 하는 함수 `Boolean` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-192">The following example uses the `CBool` function to convert expressions to `Boolean` values.</span></span> <span data-ttu-id="af4cd-193">식이 0이 아닌 값으로 계산 될 경우 `CBool` 반환 `True`, 그렇지 않으면 반환 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-193">If an expression evaluates to a nonzero value, `CBool` returns `True`; otherwise, it returns `False`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#1](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_1.vb)]  
  
## <a name="cbyte-example"></a><span data-ttu-id="af4cd-194">CByte 예제</span><span class="sxs-lookup"><span data-stu-id="af4cd-194">CByte Example</span></span>  
 <span data-ttu-id="af4cd-195">다음 예제에서는 `CByte` 식으로 변환 하는 함수는 `Byte`합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-195">The following example uses the `CByte` function to convert an expression to a `Byte`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#2](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_2.vb)]  
  
## <a name="cchar-example"></a><span data-ttu-id="af4cd-196">CChar 예제</span><span class="sxs-lookup"><span data-stu-id="af4cd-196">CChar Example</span></span>  
 <span data-ttu-id="af4cd-197">사용 하 여 다음 예제는 `CChar` 의 첫 번째 문자를 변환 하는 함수는 `String` 식을 `Char` 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-197">The following example uses the `CChar` function to convert the first character of a `String` expression to a `Char` type.</span></span>  
  
 [!code-vb[VbVbalrFunctions#3](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_3.vb)]  
  
 <span data-ttu-id="af4cd-198">입력된 인수 `CChar` 데이터 형식 이어야 합니다 `Char` 또는 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-198">The input argument to `CChar` must be of data type `Char` or `String`.</span></span> <span data-ttu-id="af4cd-199">사용할 수 없는 `CChar` 때문에 숫자를 문자로 변환할 `CChar` 숫자 데이터 형식을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-199">You cannot use `CChar` to convert a number to a character, because `CChar` cannot accept a numeric data type.</span></span> <span data-ttu-id="af4cd-200">다음 예제에서는 코드 포인트 (문자 코드)를 나타내는 숫자를 구하여 해당 문자로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-200">The following example obtains a number representing a code point (character code) and converts it to the corresponding character.</span></span> <span data-ttu-id="af4cd-201">사용 하 여는 <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> 함수는 숫자, 문자열입니다. `CInt` 문자열 입력을 변환할 `Integer`, 및 `ChrW` 숫자 형식으로 변환 `Char`합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-201">It uses the <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> function to obtain the string of digits, `CInt` to convert the string to type `Integer`, and `ChrW` to convert the number to type `Char`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#4](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_4.vb)]  
  
## <a name="cdate-example"></a><span data-ttu-id="af4cd-202">CDate 예제</span><span class="sxs-lookup"><span data-stu-id="af4cd-202">CDate Example</span></span>  
 <span data-ttu-id="af4cd-203">다음 예제에서는 `CDate` 문자열을 변환 하는 함수 `Date` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-203">The following example uses the `CDate` function to convert strings to `Date` values.</span></span> <span data-ttu-id="af4cd-204">일반적으로 하드 코딩 된 날짜 및 시간 문자열 (이 예제 에서처럼)로 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-204">In general, hard-coding dates and times as strings (as shown in this example) is not recommended.</span></span> <span data-ttu-id="af4cd-205">날짜 리터럴과 1969 # #Feb 12, 같은 시간 리터럴을 사용 하 여 및 # 4시 45분: 23 PM #를 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-205">Use date literals and time literals, such as #Feb 12, 1969# and #4:45:23 PM#, instead.</span></span>  
  
 [!code-vb[VbVbalrFunctions#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_5.vb)]  
  
## <a name="cdbl-example"></a><span data-ttu-id="af4cd-206">CDbl 예제</span><span class="sxs-lookup"><span data-stu-id="af4cd-206">CDbl Example</span></span>  
 [!code-vb[VbVbalrFunctions#6](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_6.vb)]  
  
## <a name="cdec-example"></a><span data-ttu-id="af4cd-207">CDec 예제</span><span class="sxs-lookup"><span data-stu-id="af4cd-207">CDec Example</span></span>  
 <span data-ttu-id="af4cd-208">다음 예제에서는 `CDec` 숫자 값을 변환 하려면 함수 `Decimal`합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-208">The following example uses the `CDec` function to convert a numeric value to `Decimal`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#7](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_7.vb)]  
  
## <a name="cint-example"></a><span data-ttu-id="af4cd-209">CInt 예제</span><span class="sxs-lookup"><span data-stu-id="af4cd-209">CInt Example</span></span>  
 <span data-ttu-id="af4cd-210">다음 예제에서는 `CInt` 함수에 값을 변환할 `Integer`합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-210">The following example uses the `CInt` function to convert a value to `Integer`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#8](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_8.vb)]  
  
## <a name="clng-example"></a><span data-ttu-id="af4cd-211">CLng 예제</span><span class="sxs-lookup"><span data-stu-id="af4cd-211">CLng Example</span></span>  
 <span data-ttu-id="af4cd-212">다음 예제에서는 `CLng` 값을 변환 하는 함수 `Long`합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-212">The following example uses the `CLng` function to convert values to `Long`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#9](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_9.vb)]  
  
## <a name="cobj-example"></a><span data-ttu-id="af4cd-213">CObj 예제</span><span class="sxs-lookup"><span data-stu-id="af4cd-213">CObj Example</span></span>  
 <span data-ttu-id="af4cd-214">다음 예제에서는 `CObj` 숫자 값을 변환 하려면 함수 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-214">The following example uses the `CObj` function to convert a numeric value to `Object`.</span></span> <span data-ttu-id="af4cd-215">`Object` 변수 자체에 가리키는 4 바이트 포인터만 포함 된 `Double` 할당 한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-215">The `Object` variable itself contains only a four-byte pointer, which points to the `Double` value assigned to it.</span></span>  
  
 [!code-vb[VbVbalrFunctions#10](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_10.vb)]  
  
## <a name="csbyte-example"></a><span data-ttu-id="af4cd-216">CSByte 예제</span><span class="sxs-lookup"><span data-stu-id="af4cd-216">CSByte Example</span></span>  
 <span data-ttu-id="af4cd-217">다음 예제에서는 `CSByte` 숫자 값을 변환 하려면 함수 `SByte`합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-217">The following example uses the `CSByte` function to convert a numeric value to `SByte`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#11](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_11.vb)]  
  
## <a name="cshort-example"></a><span data-ttu-id="af4cd-218">CShort 예제</span><span class="sxs-lookup"><span data-stu-id="af4cd-218">CShort Example</span></span>  
 <span data-ttu-id="af4cd-219">다음 예제에서는 `CShort` 숫자 값을 변환 하려면 함수 `Short`합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-219">The following example uses the `CShort` function to convert a numeric value to `Short`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#12](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_12.vb)]  
  
## <a name="csng-example"></a><span data-ttu-id="af4cd-220">CSng 예제</span><span class="sxs-lookup"><span data-stu-id="af4cd-220">CSng Example</span></span>  
 <span data-ttu-id="af4cd-221">다음 예제에서는 `CSng` 값을 변환 하는 함수 `Single`합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-221">The following example uses the `CSng` function to convert values to `Single`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#13](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_13.vb)]  
  
## <a name="cstr-example"></a><span data-ttu-id="af4cd-222">CStr 예제</span><span class="sxs-lookup"><span data-stu-id="af4cd-222">CStr Example</span></span>  
 <span data-ttu-id="af4cd-223">다음 예제에서는 `CStr` 숫자 값을 변환 하려면 함수 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-223">The following example uses the `CStr` function to convert a numeric value to `String`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#14](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_14.vb)]  
  
 <span data-ttu-id="af4cd-224">다음 예제에서는 `CStr` 변환 하려면 함수를 `Date` 값을 `String` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-224">The following example uses the `CStr` function to convert `Date` values to `String` values.</span></span>  
  
 [!code-vb[VbVbalrFunctions#15](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_15.vb)]  
  
 <span data-ttu-id="af4cd-225">`CStr` 항상를 렌더링 한 `Date` 예를 들어 현재 로캘에 대 한 표준 짧은 형식 값 "6/15/2003 오후 4시 35분: 47"입니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-225">`CStr` always renders a `Date` value in the standard short format for the current locale, for example, "6/15/2003 4:35:47 PM".</span></span> <span data-ttu-id="af4cd-226">그러나 `CStr` 표시 하지 않습니다는 *중립 값* 의 1/1/0001 한 날짜와 시간에 대 한 00시: 00입니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-226">However, `CStr` suppresses the *neutral values* of 1/1/0001 for the date and 00:00:00 for the time.</span></span>  
  
 <span data-ttu-id="af4cd-227">반환 값에 대 한 세부 `CStr`, 참조 [CStr 함수의 반환 값](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-227">For more detail on the values returned by `CStr`, see [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span></span>  
  
## <a name="cuint-example"></a><span data-ttu-id="af4cd-228">CUInt 예제</span><span class="sxs-lookup"><span data-stu-id="af4cd-228">CUInt Example</span></span>  
 <span data-ttu-id="af4cd-229">다음 예제에서는 `CUInt` 숫자 값을 변환 하려면 함수 `UInteger`합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-229">The following example uses the `CUInt` function to convert a numeric value to `UInteger`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#16](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_16.vb)]  
  
## <a name="culng-example"></a><span data-ttu-id="af4cd-230">CULng 예제</span><span class="sxs-lookup"><span data-stu-id="af4cd-230">CULng Example</span></span>  
 <span data-ttu-id="af4cd-231">다음 예제에서는 `CULng` 숫자 값을 변환 하려면 함수 `ULong`합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-231">The following example uses the `CULng` function to convert a numeric value to `ULong`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#17](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_17.vb)]  
  
## <a name="cushort-example"></a><span data-ttu-id="af4cd-232">CUShort 예제</span><span class="sxs-lookup"><span data-stu-id="af4cd-232">CUShort Example</span></span>  
 <span data-ttu-id="af4cd-233">다음 예제에서는 `CUShort` 숫자 값을 변환 하려면 함수 `UShort`합니다.</span><span class="sxs-lookup"><span data-stu-id="af4cd-233">The following example uses the `CUShort` function to convert a numeric value to `UShort`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#18](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_18.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="af4cd-234">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af4cd-234">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Int%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Fix%2A>  
 <xref:Microsoft.VisualBasic.Strings.Format%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Oct%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Str%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Val%2A>  
 [<span data-ttu-id="af4cd-235">변환 함수</span><span class="sxs-lookup"><span data-stu-id="af4cd-235">Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/conversion-functions.md)  
 [<span data-ttu-id="af4cd-236">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="af4cd-236">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
