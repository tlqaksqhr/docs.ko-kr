---
title: "암시적 변환과 명시적 변환 (Visual Basic) | Microsoft 문서"
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
- conversions, type
- variables [Visual Basic], changing data type
- casting
- conversions, data type
- type conversion, implicit conversions
- CType function, conversions
- casting, data types
- data type conversion, explicit
- type conversion, explicit conversions
- data types [Visual Basic], casting
- conversions, implicit
- explicit data type conversions
- conversions
- changing data types
- conversions, explicit
- data type conversion, implicit
- implicit data type conversions
ms.assetid: 77de1659-af8a-492c-967e-e7ef60ccce66
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
ms.openlocfilehash: 76f32fc4c8e26470c77e1415d96ed9035a4d9165
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="implicit-and-explicit-conversions-visual-basic"></a><span data-ttu-id="83148-102">암시적 변환과 명시적 변환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83148-102">Implicit and Explicit Conversions (Visual Basic)</span></span>
<span data-ttu-id="83148-103">*암시적 변환* 소스 코드에 특별 한 구문이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83148-103">An *implicit conversion* does not require any special syntax in the source code.</span></span> <span data-ttu-id="83148-104">다음 예에서 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 의 값을 암시적으로 변환 `k` 을 단 정밀도 부동 소수점 값에 할당 하기 전에 `q`합니다.</span><span class="sxs-lookup"><span data-stu-id="83148-104">In the following example, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] implicitly converts the value of `k` to a single-precision floating-point value before assigning it to `q`.</span></span>  
  
```  
Dim k As Integer  
Dim q As Double  
' Integer widens to Double, so you can do this with Option Strict On.  
k = 432  
q = k  
```  
  
 <span data-ttu-id="83148-105">*명시적 변환* 형식 변환 키워드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="83148-105">An *explicit conversion* uses a type conversion keyword.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="83148-106">이러한는 여러 키워드를 강제 원하는 데이터 형식으로 괄호 안의 식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="83148-106"> provides several such keywords, which coerce an expression in parentheses to the desired data type.</span></span> <span data-ttu-id="83148-107">이러한 키워드는 함수 처럼 동작 하지만 실행이 함수 호출 보다 약간 빠릅니다 하므로 컴파일러 코드 인라인을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="83148-107">These keywords act like functions, but the compiler generates the code inline, so execution is slightly faster than with a function call.</span></span>  
  
 <span data-ttu-id="83148-108">앞의 예에서의 다음 확장에는 `CInt` 키워드의 값을 변환 `q` 에 할당 하기 전에 정수에 다시 `k`합니다.</span><span class="sxs-lookup"><span data-stu-id="83148-108">In the following extension of the preceding example, the `CInt` keyword converts the value of `q` back to an integer before assigning it to `k`.</span></span>  
  
```  
' q had been assigned the value 432 from k.  
q = Math.Sqrt(q)  
k = CInt(q)  
' k now has the value 21 (rounded square root of 432).  
```  
  
## <a name="conversion-keywords"></a><span data-ttu-id="83148-109">변환 키워드</span><span class="sxs-lookup"><span data-stu-id="83148-109">Conversion Keywords</span></span>  
 <span data-ttu-id="83148-110">다음 표에서 사용할 수 있는 변환 키워드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="83148-110">The following table shows the available conversion keywords.</span></span>  
  
|<span data-ttu-id="83148-111">형식 변환 키워드</span><span class="sxs-lookup"><span data-stu-id="83148-111">Type conversion keyword</span></span>|<span data-ttu-id="83148-112">식 데이터 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="83148-112">Converts an expression to data type</span></span>|<span data-ttu-id="83148-113">변환할 식의 허용 가능한 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="83148-113">Allowable data types of expression to be converted</span></span>|  
|---|---|---|  
|`CBool`|[<span data-ttu-id="83148-114">Boolean 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="83148-114">Boolean Data Type</span></span>](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="83148-115">임의의 숫자 형식 (포함 하 여 `Byte`, `SByte`, 열거 형식 및), `String`,`Object`</span><span class="sxs-lookup"><span data-stu-id="83148-115">Any numeric type (including `Byte`, `SByte`, and enumerated types), `String`, `Object`</span></span>|  
|`CByte`|[<span data-ttu-id="83148-116">Byte 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="83148-116">Byte Data Type</span></span>](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="83148-117">임의의 숫자 형식 (포함 하 여 `SByte` 및 열거 형식), `Boolean`, `String`,`Object`</span><span class="sxs-lookup"><span data-stu-id="83148-117">Any numeric type (including `SByte` and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CChar`|[<span data-ttu-id="83148-118">Char 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="83148-118">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="83148-119">`String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="83148-119">`String`, `Object`</span></span>|  
|`CDate`|[<span data-ttu-id="83148-120">Date 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="83148-120">Date Data Type</span></span>](../../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="83148-121">`String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="83148-121">`String`, `Object`</span></span>|  
|`CDbl`|[<span data-ttu-id="83148-122">Double 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="83148-122">Double Data Type</span></span>](../../../../visual-basic/language-reference/data-types/double-data-type.md)|<span data-ttu-id="83148-123">임의의 숫자 형식 (포함 하 여 `Byte`, `SByte`, 열거 형식 및), `Boolean`, `String`,`Object`</span><span class="sxs-lookup"><span data-stu-id="83148-123">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CDec`|[<span data-ttu-id="83148-124">Decimal 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="83148-124">Decimal Data Type</span></span>](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="83148-125">임의의 숫자 형식 (포함 하 여 `Byte`, `SByte`, 열거 형식 및), `Boolean`, `String`,`Object`</span><span class="sxs-lookup"><span data-stu-id="83148-125">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CInt`|[<span data-ttu-id="83148-126">Integer 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="83148-126">Integer Data Type</span></span>](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="83148-127">임의의 숫자 형식 (포함 하 여 `Byte`, `SByte`, 열거 형식 및), `Boolean`, `String`,`Object`</span><span class="sxs-lookup"><span data-stu-id="83148-127">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CLng`|[<span data-ttu-id="83148-128">Long 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="83148-128">Long Data Type</span></span>](../../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="83148-129">임의의 숫자 형식 (포함 하 여 `Byte`, `SByte`, 열거 형식 및), `Boolean`, `String`,`Object`</span><span class="sxs-lookup"><span data-stu-id="83148-129">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CObj`|[<span data-ttu-id="83148-130">Object 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="83148-130">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)|<span data-ttu-id="83148-131">모든 형식</span><span class="sxs-lookup"><span data-stu-id="83148-131">Any type</span></span>|  
|`CSByte`|[<span data-ttu-id="83148-132">SByte 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="83148-132">SByte Data Type</span></span>](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="83148-133">임의의 숫자 형식 (포함 하 여 `Byte` 및 열거 형식), `Boolean`, `String`,`Object`</span><span class="sxs-lookup"><span data-stu-id="83148-133">Any numeric type (including `Byte` and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CShort`|[<span data-ttu-id="83148-134">Short 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="83148-134">Short Data Type</span></span>](../../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="83148-135">임의의 숫자 형식 (포함 하 여 `Byte`, `SByte`, 열거 형식 및), `Boolean`, `String`,`Object`</span><span class="sxs-lookup"><span data-stu-id="83148-135">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CSng`|[<span data-ttu-id="83148-136">Single 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="83148-136">Single Data Type</span></span>](../../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="83148-137">임의의 숫자 형식 (포함 하 여 `Byte`, `SByte`, 열거 형식 및), `Boolean`, `String`,`Object`</span><span class="sxs-lookup"><span data-stu-id="83148-137">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CStr`|[<span data-ttu-id="83148-138">String 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="83148-138">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)|<span data-ttu-id="83148-139">임의의 숫자 형식 (포함 하 여 `Byte`, `SByte`, 열거 형식 및), `Boolean`, `Char`, `Char` 배열 `Date`,`Object`</span><span class="sxs-lookup"><span data-stu-id="83148-139">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `Char`, `Char` array, `Date`, `Object`</span></span>|  
|`CType`|<span data-ttu-id="83148-140">쉼표 다음에 지정 된 형식 (`,`)</span><span class="sxs-lookup"><span data-stu-id="83148-140">Type specified following the comma (`,`)</span></span>|<span data-ttu-id="83148-141">변환할 때는 *기본 데이터 형식* 해당 하는 변환 키워드에 허용 된 대로 형식을 동일한 (기본 형식의 배열을 포함)</span><span class="sxs-lookup"><span data-stu-id="83148-141">When converting to an *elementary data type* (including an array of an elementary type), the same types as allowed for the corresponding conversion keyword</span></span><br /><br /> <span data-ttu-id="83148-142">변환할 때는 *복합 데이터 형식을*를 구현 하는 인터페이스 및 상속 된 클래스</span><span class="sxs-lookup"><span data-stu-id="83148-142">When converting to a *composite data type*, the interfaces it implements and the classes from which it inherits</span></span><br /><br /> <span data-ttu-id="83148-143">오버 로드는 있는 클래스 또는 구조체를 변환할 때 `CType`, 해당 클래스 또는 구조체</span><span class="sxs-lookup"><span data-stu-id="83148-143">When converting to a class or structure on which you have overloaded `CType`, that class or structure</span></span>|  
|`CUInt`|[<span data-ttu-id="83148-144">UInteger 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="83148-144">UInteger Data Type</span></span>](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="83148-145">임의의 숫자 형식 (포함 하 여 `Byte`, `SByte`, 열거 형식 및), `Boolean`, `String`,`Object`</span><span class="sxs-lookup"><span data-stu-id="83148-145">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CULng`|[<span data-ttu-id="83148-146">ULong 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="83148-146">ULong Data Type</span></span>](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="83148-147">임의의 숫자 형식 (포함 하 여 `Byte`, `SByte`, 열거 형식 및), `Boolean`, `String`,`Object`</span><span class="sxs-lookup"><span data-stu-id="83148-147">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CUShort`|[<span data-ttu-id="83148-148">UShort 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="83148-148">UShort Data Type</span></span>](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="83148-149">임의의 숫자 형식 (포함 하 여 `Byte`, `SByte`, 열거 형식 및), `Boolean`, `String`,`Object`</span><span class="sxs-lookup"><span data-stu-id="83148-149">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
  
## <a name="the-ctype-function"></a><span data-ttu-id="83148-150">CType 함수</span><span class="sxs-lookup"><span data-stu-id="83148-150">The CType Function</span></span>  
 <span data-ttu-id="83148-151">[CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md) 두 인수에 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="83148-151">The [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) operates on two arguments.</span></span> <span data-ttu-id="83148-152">첫 번째 변환 될 식이고 두 번째는 대상 데이터 형식이 나 개체 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="83148-152">The first is the expression to be converted, and the second is the destination data type or object class.</span></span> <span data-ttu-id="83148-153">참고 첫 번째 인수는 식의 형식이 아닌를 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83148-153">Note that the first argument must be an expression, not a type.</span></span>  
  
 <span data-ttu-id="83148-154">`CType`한 *인라인 함수*, 변환을 사용 하면 컴파일된 코드 즉, 자주 하는 함수를 생성 하지 않고 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="83148-154">`CType` is an *inline function*, meaning the compiled code makes the conversion, often without generating a function call.</span></span> <span data-ttu-id="83148-155">성능이 향상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83148-155">This improves performance.</span></span>  
  
 <span data-ttu-id="83148-156">에 대 한 비교 `CType` 참조는 다른 키워드와 함께 형식 변환, [DirectCast 연산자](../../../../visual-basic/language-reference/operators/directcast-operator.md) 및 [TryCast 연산자](../../../../visual-basic/language-reference/operators/trycast-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="83148-156">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../../../../visual-basic/language-reference/operators/directcast-operator.md) and [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span>  
  
### <a name="elementary-types"></a><span data-ttu-id="83148-157">기본 형식</span><span class="sxs-lookup"><span data-stu-id="83148-157">Elementary Types</span></span>  
 <span data-ttu-id="83148-158">다음 예에서는 `CType`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="83148-158">The following example demonstrates the use of `CType`.</span></span>  
  
```  
k = CType(q, Integer)  
' The following statement coerces w to the specific object class Label.  
f = CType(w, Label)  
```  
  
### <a name="composite-types"></a><span data-ttu-id="83148-159">복합 형식</span><span class="sxs-lookup"><span data-stu-id="83148-159">Composite Types</span></span>  
 <span data-ttu-id="83148-160">사용할 수 있습니다 `CType` 값 복합 데이터도 기본 형식은 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="83148-160">You can use `CType` to convert values to composite data types as well as to elementary types.</span></span> <span data-ttu-id="83148-161">개체 클래스는 다음 예와 같이 해당 인터페이스 중 하나의 형식으로 강제 변환에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83148-161">You can also use it to coerce an object class to the type of one of its interfaces, as in the following example.</span></span>  
  
```  
' Assume class cZone implements interface iZone.  
Dim h As Object  
' The first argument to CType must be an expression, not a type.  
Dim cZ As cZone  
' The following statement coerces a cZone object to its interface iZone.  
h = CType(cZ, iZone)  
```  
  
### <a name="array-types"></a><span data-ttu-id="83148-162">배열 형식</span><span class="sxs-lookup"><span data-stu-id="83148-162">Array Types</span></span>  
 <span data-ttu-id="83148-163">`CType`다음 예제와 같이 배열 데이터 형식을 변환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83148-163">`CType` can also convert array data types, as in the following example.</span></span>  
  
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
  
 <span data-ttu-id="83148-164">자세한 내용 및 예제에 대 한 참조 [배열 변환](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="83148-164">For more information and an example, see [Array Conversions](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md).</span></span>  
  
### <a name="types-defining-ctype"></a><span data-ttu-id="83148-165">CType를 정의 하는 형식</span><span class="sxs-lookup"><span data-stu-id="83148-165">Types Defining CType</span></span>  
 <span data-ttu-id="83148-166">정의할 수 있습니다 `CType` 클래스 또는 구조를 정의한 경우.</span><span class="sxs-lookup"><span data-stu-id="83148-166">You can define `CType` on a class or structure you have defined.</span></span> <span data-ttu-id="83148-167">이 클래스 또는 구조체의 형식에서 값을 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83148-167">This allows you to convert values to and from the type of your class or structure.</span></span> <span data-ttu-id="83148-168">자세한 내용 및 예제에 대 한 참조 [하는 방법: 변환 연산자 정의](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="83148-168">For more information and an example, see [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83148-169">변환 키워드와 함께 사용 되는 값은 대상 데이터 형식에 대 한 유효 해야 합니다. 그렇지 않으면 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="83148-169">Values used with a conversion keyword must be valid for the destination data type, or an error occurs.</span></span> <span data-ttu-id="83148-170">예를 들어 변환 하려고 하면는 `Long` 에 `Integer`의 값은 `Long` 의 유효 범위 내에 있어야는 `Integer` 데이터 형식.</span><span class="sxs-lookup"><span data-stu-id="83148-170">For example, if you attempt to convert a `Long` to an `Integer`, the value of the `Long` must be within the valid range for the `Integer` data type.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="83148-171">지정 `CType` 변환할 하나의 클래스 형식에서 런타임에 다른 오류가 발생 하는 경우 원본 유형을 대상 형식에서 파생 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83148-171">Specifying `CType` to convert from one class type to another fails at run time if the source type does not derive from the destination type.</span></span> <span data-ttu-id="83148-172">이러한 오류를 throw 한 <xref:System.InvalidCastException>예외.</xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="83148-172">Such a failure throws an <xref:System.InvalidCastException> exception.</span></span>  
  
 <span data-ttu-id="83148-173">그러나 형식 중 하나는 구조체 또는 클래스를 정의한 경우 및 정의 하는 경우 `CType` 해당 구조체 또는 클래스에는 변환의 요구 사항을 만족 하는 경우 성공할 수 있습니다 프로그램 `CType`합니다.</span><span class="sxs-lookup"><span data-stu-id="83148-173">However, if one of the types is a structure or class you have defined, and if you have defined `CType` on that structure or class, a conversion can succeed if it satisfies the requirements of your `CType`.</span></span> <span data-ttu-id="83148-174">참조 [하는 방법: 변환 연산자 정의](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="83148-174">See [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
 <span data-ttu-id="83148-175">명시적 변환을 수행이 라고도 *캐스팅* 지정 된 데이터 형식이 나 개체 클래스에는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="83148-175">Performing an explicit conversion is also known as *casting* an expression to a given data type or object class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83148-176">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83148-176">See Also</span></span>  
 <span data-ttu-id="83148-177">[Visual Basic의 형식 변환](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="83148-177">[Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="83148-178"> [문자열과 다른 형식 간의 변환](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md) </span><span class="sxs-lookup"><span data-stu-id="83148-178"> [Conversions Between Strings and Other Types](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md) </span></span>  
<span data-ttu-id="83148-179"> [방법: Visual Basic에서 다른 형식으로 변환](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md) </span><span class="sxs-lookup"><span data-stu-id="83148-179"> [How to: Convert an Object to Another Type in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md) </span></span>  
<span data-ttu-id="83148-180"> [구조](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span><span class="sxs-lookup"><span data-stu-id="83148-180"> [Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span></span>  
<span data-ttu-id="83148-181"> [데이터 형식](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="83148-181"> [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
<span data-ttu-id="83148-182"> [형식 변환 함수](../../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span><span class="sxs-lookup"><span data-stu-id="83148-182"> [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span></span>  
<span data-ttu-id="83148-183"> [데이터 형식 문제 해결](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)</span><span class="sxs-lookup"><span data-stu-id="83148-183"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)</span></span>
