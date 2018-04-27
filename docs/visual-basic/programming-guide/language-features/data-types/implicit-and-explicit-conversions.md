---
title: 암시적 변환과 명시적 변환(Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- conversions [Visual Basic], type
- variables [Visual Basic], changing data type
- casting
- conversions [Visual Basic], data type
- type conversion [Visual Basic], implicit conversions
- CType function [Visual Basic], conversions
- casting, data types
- data type conversion [Visual Basic], explicit
- type conversion [Visual Basic], explicit conversions
- data types [Visual Basic], casting
- conversions [Visual Basic], implicit
- explicit data type conversions [Visual Basic]
- conversions [Visual Basic]
- changing data types [Visual Basic]
- conversions [Visual Basic], explicit
- data type conversion [Visual Basic], implicit
- implicit data type conversions [Visual Basic]
ms.assetid: 77de1659-af8a-492c-967e-e7ef60ccce66
caps.latest.revision: 25
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9827cecce0a15d37d2ffe3ccf691404149b156fb
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="implicit-and-explicit-conversions-visual-basic"></a><span data-ttu-id="4e96c-102">암시적 변환과 명시적 변환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e96c-102">Implicit and Explicit Conversions (Visual Basic)</span></span>
<span data-ttu-id="4e96c-103">*암시적 변환* 소스 코드에서 특수 구문이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e96c-103">An *implicit conversion* does not require any special syntax in the source code.</span></span> <span data-ttu-id="4e96c-104">다음 예제에서는 Visual Basic 암시적 변환의 값 `k` 을 단 정밀도 부동 소수점 값에 할당 하기 전에 `q`합니다.</span><span class="sxs-lookup"><span data-stu-id="4e96c-104">In the following example, Visual Basic implicitly converts the value of `k` to a single-precision floating-point value before assigning it to `q`.</span></span>  
  
```  
Dim k As Integer  
Dim q As Double  
' Integer widens to Double, so you can do this with Option Strict On.  
k = 432  
q = k  
```  
  
 <span data-ttu-id="4e96c-105">*명시적 변환* 형식 변환 키워드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e96c-105">An *explicit conversion* uses a type conversion keyword.</span></span> <span data-ttu-id="4e96c-106">Visual Basic에서 이러한는 여러 키워드를 원하는 데이터 형식으로는 괄호 안의 식을 강제로 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e96c-106">Visual Basic provides several such keywords, which coerce an expression in parentheses to the desired data type.</span></span> <span data-ttu-id="4e96c-107">이러한 키워드는 함수 처럼 동작 하지만 실행 함수 호출 보다 약간 더 빠르며 이므로 컴파일러 인라인 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e96c-107">These keywords act like functions, but the compiler generates the code inline, so execution is slightly faster than with a function call.</span></span>  
  
 <span data-ttu-id="4e96c-108">앞의 예에서의 다음 확장에는 `CInt` 키워드의 값을 변환 `q` 데 정수로에 할당 하기 전에 다시 `k`합니다.</span><span class="sxs-lookup"><span data-stu-id="4e96c-108">In the following extension of the preceding example, the `CInt` keyword converts the value of `q` back to an integer before assigning it to `k`.</span></span>  
  
```  
' q had been assigned the value 432 from k.  
q = Math.Sqrt(q)  
k = CInt(q)  
' k now has the value 21 (rounded square root of 432).  
```  
  
## <a name="conversion-keywords"></a><span data-ttu-id="4e96c-109">변환 키워드</span><span class="sxs-lookup"><span data-stu-id="4e96c-109">Conversion Keywords</span></span>  
 <span data-ttu-id="4e96c-110">다음 표에서 사용할 수 있는 변환 키워드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4e96c-110">The following table shows the available conversion keywords.</span></span>  
  
|<span data-ttu-id="4e96c-111">형식 변환 키워드</span><span class="sxs-lookup"><span data-stu-id="4e96c-111">Type conversion keyword</span></span>|<span data-ttu-id="4e96c-112">식 데이터 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="4e96c-112">Converts an expression to data type</span></span>|<span data-ttu-id="4e96c-113">변환할 식의 허용 가능한 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4e96c-113">Allowable data types of expression to be converted</span></span>|  
|---|---|---|  
|`CBool`|[<span data-ttu-id="4e96c-114">Boolean 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4e96c-114">Boolean Data Type</span></span>](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="4e96c-115">임의의 숫자 형식 (포함 하 여 `Byte`, `SByte`, 및 열거 형식), `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="4e96c-115">Any numeric type (including `Byte`, `SByte`, and enumerated types), `String`, `Object`</span></span>|  
|`CByte`|[<span data-ttu-id="4e96c-116">Byte 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4e96c-116">Byte Data Type</span></span>](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="4e96c-117">임의의 숫자 형식 (포함 하 여 `SByte` 및 열거 형식), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="4e96c-117">Any numeric type (including `SByte` and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CChar`|[<span data-ttu-id="4e96c-118">Char 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4e96c-118">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="4e96c-119">`String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="4e96c-119">`String`, `Object`</span></span>|  
|`CDate`|[<span data-ttu-id="4e96c-120">Date 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4e96c-120">Date Data Type</span></span>](../../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="4e96c-121">`String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="4e96c-121">`String`, `Object`</span></span>|  
|`CDbl`|[<span data-ttu-id="4e96c-122">Double 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4e96c-122">Double Data Type</span></span>](../../../../visual-basic/language-reference/data-types/double-data-type.md)|<span data-ttu-id="4e96c-123">임의의 숫자 형식 (포함 하 여 `Byte`, `SByte`, 및 열거 형식), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="4e96c-123">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CDec`|[<span data-ttu-id="4e96c-124">Decimal 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4e96c-124">Decimal Data Type</span></span>](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="4e96c-125">임의의 숫자 형식 (포함 하 여 `Byte`, `SByte`, 및 열거 형식), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="4e96c-125">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CInt`|[<span data-ttu-id="4e96c-126">Integer 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4e96c-126">Integer Data Type</span></span>](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="4e96c-127">임의의 숫자 형식 (포함 하 여 `Byte`, `SByte`, 및 열거 형식), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="4e96c-127">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CLng`|[<span data-ttu-id="4e96c-128">Long 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4e96c-128">Long Data Type</span></span>](../../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="4e96c-129">임의의 숫자 형식 (포함 하 여 `Byte`, `SByte`, 및 열거 형식), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="4e96c-129">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CObj`|[<span data-ttu-id="4e96c-130">Object 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4e96c-130">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)|<span data-ttu-id="4e96c-131">모든 형식</span><span class="sxs-lookup"><span data-stu-id="4e96c-131">Any type</span></span>|  
|`CSByte`|[<span data-ttu-id="4e96c-132">SByte 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4e96c-132">SByte Data Type</span></span>](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="4e96c-133">임의의 숫자 형식 (포함 하 여 `Byte` 및 열거 형식), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="4e96c-133">Any numeric type (including `Byte` and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CShort`|[<span data-ttu-id="4e96c-134">Short 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4e96c-134">Short Data Type</span></span>](../../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="4e96c-135">임의의 숫자 형식 (포함 하 여 `Byte`, `SByte`, 및 열거 형식), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="4e96c-135">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CSng`|[<span data-ttu-id="4e96c-136">Single 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4e96c-136">Single Data Type</span></span>](../../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="4e96c-137">임의의 숫자 형식 (포함 하 여 `Byte`, `SByte`, 및 열거 형식), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="4e96c-137">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CStr`|[<span data-ttu-id="4e96c-138">String 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4e96c-138">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)|<span data-ttu-id="4e96c-139">임의의 숫자 형식 (포함 하 여 `Byte`, `SByte`, 및 열거 형식), `Boolean`, `Char`, `Char` 배열 `Date`, `Object`</span><span class="sxs-lookup"><span data-stu-id="4e96c-139">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `Char`, `Char` array, `Date`, `Object`</span></span>|  
|`CType`|<span data-ttu-id="4e96c-140">쉼표 다음에 지정 된 형식 (`,`)</span><span class="sxs-lookup"><span data-stu-id="4e96c-140">Type specified following the comma (`,`)</span></span>|<span data-ttu-id="4e96c-141">변환할 때는 *기본 데이터 형식을* (기본 형식의 배열을 포함), 동일한 형식은 형식을 해당 하는 변환 키워드에 대 한 허용</span><span class="sxs-lookup"><span data-stu-id="4e96c-141">When converting to an *elementary data type* (including an array of an elementary type), the same types as allowed for the corresponding conversion keyword</span></span><br /><br /> <span data-ttu-id="4e96c-142">변환할 때는 *복합 데이터 형식을*를 구현 하는 인터페이스와 상속 된 클래스</span><span class="sxs-lookup"><span data-stu-id="4e96c-142">When converting to a *composite data type*, the interfaces it implements and the classes from which it inherits</span></span><br /><br /> <span data-ttu-id="4e96c-143">오버가 클래스 또는 구조체를 변환할 때 `CType`, 해당 클래스 또는 구조체</span><span class="sxs-lookup"><span data-stu-id="4e96c-143">When converting to a class or structure on which you have overloaded `CType`, that class or structure</span></span>|  
|`CUInt`|[<span data-ttu-id="4e96c-144">UInteger 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4e96c-144">UInteger Data Type</span></span>](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="4e96c-145">임의의 숫자 형식 (포함 하 여 `Byte`, `SByte`, 및 열거 형식), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="4e96c-145">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CULng`|[<span data-ttu-id="4e96c-146">ULong 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4e96c-146">ULong Data Type</span></span>](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="4e96c-147">임의의 숫자 형식 (포함 하 여 `Byte`, `SByte`, 및 열거 형식), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="4e96c-147">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CUShort`|[<span data-ttu-id="4e96c-148">UShort 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4e96c-148">UShort Data Type</span></span>](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="4e96c-149">임의의 숫자 형식 (포함 하 여 `Byte`, `SByte`, 및 열거 형식), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="4e96c-149">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
  
## <a name="the-ctype-function"></a><span data-ttu-id="4e96c-150">CType 함수</span><span class="sxs-lookup"><span data-stu-id="4e96c-150">The CType Function</span></span>  
 <span data-ttu-id="4e96c-151">[CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md) 두 개의 인수에 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e96c-151">The [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) operates on two arguments.</span></span> <span data-ttu-id="4e96c-152">첫 번째 변환 될 식이고 두 번째는 대상 데이터 형식 또는 개체 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4e96c-152">The first is the expression to be converted, and the second is the destination data type or object class.</span></span> <span data-ttu-id="4e96c-153">첫 번째 인수 형식이 아닌 식 이어야 합니다는 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e96c-153">Note that the first argument must be an expression, not a type.</span></span>  
  
 <span data-ttu-id="4e96c-154">`CType` 이 *인라인 함수*, 변환을 사용 하면 컴파일된 코드 이므로, 종종 함수를 생성 하지 않고 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e96c-154">`CType` is an *inline function*, meaning the compiled code makes the conversion, often without generating a function call.</span></span> <span data-ttu-id="4e96c-155">성능이 향상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e96c-155">This improves performance.</span></span>  
  
 <span data-ttu-id="4e96c-156">에 대 한 비교 `CType` 참조와 다른 형식 변환 키워드, [DirectCast 연산자](../../../../visual-basic/language-reference/operators/directcast-operator.md) 및 [TryCast 연산자](../../../../visual-basic/language-reference/operators/trycast-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4e96c-156">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../../../../visual-basic/language-reference/operators/directcast-operator.md) and [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span>  
  
### <a name="elementary-types"></a><span data-ttu-id="4e96c-157">기본 형식</span><span class="sxs-lookup"><span data-stu-id="4e96c-157">Elementary Types</span></span>  
 <span data-ttu-id="4e96c-158">다음 예에서는 `CType`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="4e96c-158">The following example demonstrates the use of `CType`.</span></span>  
  
```  
k = CType(q, Integer)  
' The following statement coerces w to the specific object class Label.  
f = CType(w, Label)  
```  
  
### <a name="composite-types"></a><span data-ttu-id="4e96c-159">복합 형식</span><span class="sxs-lookup"><span data-stu-id="4e96c-159">Composite Types</span></span>  
 <span data-ttu-id="4e96c-160">사용할 수 있습니다 `CType` 값을 복합 데이터도 기본 형식은 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e96c-160">You can use `CType` to convert values to composite data types as well as to elementary types.</span></span> <span data-ttu-id="4e96c-161">개체 클래스의 다음 예제와 같이 인터페이스 중 하나의 형식으로 강제 변환에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e96c-161">You can also use it to coerce an object class to the type of one of its interfaces, as in the following example.</span></span>  
  
```  
' Assume class cZone implements interface iZone.  
Dim h As Object  
' The first argument to CType must be an expression, not a type.  
Dim cZ As cZone  
' The following statement coerces a cZone object to its interface iZone.  
h = CType(cZ, iZone)  
```  
  
### <a name="array-types"></a><span data-ttu-id="4e96c-162">배열 형식</span><span class="sxs-lookup"><span data-stu-id="4e96c-162">Array Types</span></span>  
 <span data-ttu-id="4e96c-163">`CType` 다음 예제와 같이 배열 데이터 형식을 변환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e96c-163">`CType` can also convert array data types, as in the following example.</span></span>  
  
```  
Dim v() As classV  
Dim obArray() As Object  
' Assume some object array has been assigned to obArray.  
' Check for run-time type compatibility.  
If TypeOf obArray Is classV()  
    ' obArray can be converted to classV.  
    v = CType(obArray, classV())  
End If  
```  
  
 <span data-ttu-id="4e96c-164">자세한 내용 및 예제에 대 한 참조 [배열 변환](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4e96c-164">For more information and an example, see [Array Conversions](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md).</span></span>  
  
### <a name="types-defining-ctype"></a><span data-ttu-id="4e96c-165">CType 정의 형식</span><span class="sxs-lookup"><span data-stu-id="4e96c-165">Types Defining CType</span></span>  
 <span data-ttu-id="4e96c-166">정의한 `CType` 클래스 또는 구조체 정의에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e96c-166">You can define `CType` on a class or structure you have defined.</span></span> <span data-ttu-id="4e96c-167">이 클래스 또는 구조체의 형식에서 값을 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e96c-167">This allows you to convert values to and from the type of your class or structure.</span></span> <span data-ttu-id="4e96c-168">자세한 내용 및 예제에 대 한 참조 [하는 방법: 변환 연산자 정의](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4e96c-168">For more information and an example, see [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4e96c-169">변환 키워드와 함께 사용 되는 값은 대상 데이터 형식에 대해 유효 해야 합니다. 그렇지 않으면 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e96c-169">Values used with a conversion keyword must be valid for the destination data type, or an error occurs.</span></span> <span data-ttu-id="4e96c-170">변환 하려고 하는 경우 등는 `Long` 에 `Integer`의 값은 `Long` 에 대 한 유효한 범위 내에 있어야는 `Integer` 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4e96c-170">For example, if you attempt to convert a `Long` to an `Integer`, the value of the `Long` must be within the valid range for the `Integer` data type.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="4e96c-171">지정 `CType` 소스 형식이 대상 형식에서 파생 되지 경우 런타임 시 다른 실패 한 클래스 형식에서 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e96c-171">Specifying `CType` to convert from one class type to another fails at run time if the source type does not derive from the destination type.</span></span> <span data-ttu-id="4e96c-172">이러한 오류를 throw 한 <xref:System.InvalidCastException> 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="4e96c-172">Such a failure throws an <xref:System.InvalidCastException> exception.</span></span>  
  
 <span data-ttu-id="4e96c-173">그러나 구조체 또는 클래스를 정의한를 있으면 형식 중 하나를 정의한 경우 `CType` 해당 구조체 또는 클래스에는 변환의 요구 사항을 만족 하는 경우 성공할 수 있습니다 프로그램 `CType`합니다.</span><span class="sxs-lookup"><span data-stu-id="4e96c-173">However, if one of the types is a structure or class you have defined, and if you have defined `CType` on that structure or class, a conversion can succeed if it satisfies the requirements of your `CType`.</span></span> <span data-ttu-id="4e96c-174">참조 [하는 방법: 변환 연산자 정의](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4e96c-174">See [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
 <span data-ttu-id="4e96c-175">명시적 변환을 수행 라고도 *캐스팅* 식으로 지정 된 데이터 형식이 나 개체 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4e96c-175">Performing an explicit conversion is also known as *casting* an expression to a given data type or object class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e96c-176">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e96c-176">See Also</span></span>  
 [<span data-ttu-id="4e96c-177">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="4e96c-177">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="4e96c-178">문자열과 다른 형식 사이의 변환</span><span class="sxs-lookup"><span data-stu-id="4e96c-178">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [<span data-ttu-id="4e96c-179">방법: Visual Basic에서 다른 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="4e96c-179">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [<span data-ttu-id="4e96c-180">구조체</span><span class="sxs-lookup"><span data-stu-id="4e96c-180">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="4e96c-181">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4e96c-181">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="4e96c-182">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="4e96c-182">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="4e96c-183">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="4e96c-183">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
