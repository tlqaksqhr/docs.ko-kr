---
title: 확대 변환과 축소 변환(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- widening conversions [Visual Basic]
- narrowing conversions [Visual Basic]
- conversions [Visual Basic], type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- conversions [Visual Basic], exceptions during conversion
- type conversion [Visual Basic], exceptions during conversion
- conversions [Visual Basic], data type
- conversions [Visual Basic], narrowing
- type conversion [Visual Basic], narrowing
- data type conversion [Visual Basic], widening
- data type conversion [Visual Basic], narrowing
- changing data types [Visual Basic]
- type conversion [Visual Basic], widening
- data type conversion [Visual Basic], exceptions during conversion
- conversions [Visual Basic], widening
ms.assetid: 058c3152-6c28-4268-af44-2209e774f0bd
ms.openlocfilehash: e574c20ec259953fea4b11d8f65e546373a4fe8c
ms.sourcegitcommit: 869b5832b667915ac4a5dd8c86b1109ed26b6c08
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2018
ms.locfileid: "39332576"
---
# <a name="widening-and-narrowing-conversions-visual-basic"></a><span data-ttu-id="a7c29-102">확대 변환과 축소 변환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7c29-102">Widening and Narrowing Conversions (Visual Basic)</span></span>
<span data-ttu-id="a7c29-103">형식 변환 사용 하 여 중요 한 고려 대상 데이터 형식의 범위 내에서 변환의 결과 인지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-103">An important consideration with a type conversion is whether the result of the conversion is within the range of the destination data type.</span></span>  
  
 <span data-ttu-id="a7c29-104">A *확대 변환* 원래 데이터의 모든 가능한 값에 대해 허용할 수 있는 데이터 형식으로 값을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-104">A *widening conversion* changes a value to a data type that can allow for any possible value of the original data.</span></span>  <span data-ttu-id="a7c29-105">확대 변환은 원본 값을 유지 하지만 표현 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-105">Widening conversions preserve the source value but can change its representation.</span></span> <span data-ttu-id="a7c29-106">정수 계열 형식에서 변환 하는 경우 이런 `Decimal`, 또는 `Char` 에 `String`입니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-106">This occurs if you convert from an integral type to `Decimal`, or from `Char` to `String`.</span></span>  
  
 <span data-ttu-id="a7c29-107">*축소 변환* 은 가능한 값의 일부를 저장하지 못할 수도 있는 데이터 형식으로 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-107">A *narrowing conversion* changes a value to a data type that might not be able to hold some of the possible values.</span></span> <span data-ttu-id="a7c29-108">변환할 대상 숫자 형식과 정수 계열 형식으로 변환할 때 소수 자릿수 값은 반올림 하는 예를 들어 `Boolean` 하나 줄어듭니다 `True` 또는 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-108">For example, a fractional value is rounded when it is converted to an integral type, and a numeric type being converted to `Boolean` is reduced to either `True` or `False`.</span></span>  
  
## <a name="widening-conversions"></a><span data-ttu-id="a7c29-109">확대 변환</span><span class="sxs-lookup"><span data-stu-id="a7c29-109">Widening Conversions</span></span>  
 <span data-ttu-id="a7c29-110">다음 표에서 표준 확대 변환을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-110">The following table shows the standard widening conversions.</span></span>  
  
|<span data-ttu-id="a7c29-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a7c29-111">Data type</span></span>|<span data-ttu-id="a7c29-112">데이터 형식 확장 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a7c29-112">Widens to data types <sup>1</sup></span></span>|  
|---|---|  
|[<span data-ttu-id="a7c29-113">SByte</span><span class="sxs-lookup"><span data-stu-id="a7c29-113">SByte</span></span>](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="a7c29-114">`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="a7c29-114">`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="a7c29-115">Byte</span><span class="sxs-lookup"><span data-stu-id="a7c29-115">Byte</span></span>](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="a7c29-116">`Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="a7c29-116">`Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="a7c29-117">Short</span><span class="sxs-lookup"><span data-stu-id="a7c29-117">Short</span></span>](../../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="a7c29-118">`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="a7c29-118">`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="a7c29-119">UShort</span><span class="sxs-lookup"><span data-stu-id="a7c29-119">UShort</span></span>](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="a7c29-120">`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="a7c29-120">`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="a7c29-121">Integer</span><span class="sxs-lookup"><span data-stu-id="a7c29-121">Integer</span></span>](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="a7c29-122">`Integer`, `Long`, `Decimal`, `Single`, `Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a7c29-122">`Integer`, `Long`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="a7c29-123">UInteger</span><span class="sxs-lookup"><span data-stu-id="a7c29-123">UInteger</span></span>](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="a7c29-124">`UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a7c29-124">`UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="a7c29-125">Long</span><span class="sxs-lookup"><span data-stu-id="a7c29-125">Long</span></span>](../../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="a7c29-126">`Long`, `Decimal`, `Single`, `Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a7c29-126">`Long`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="a7c29-127">ULong</span><span class="sxs-lookup"><span data-stu-id="a7c29-127">ULong</span></span>](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="a7c29-128">`ULong`, `Decimal`, `Single`, `Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a7c29-128">`ULong`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="a7c29-129">Decimal</span><span class="sxs-lookup"><span data-stu-id="a7c29-129">Decimal</span></span>](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="a7c29-130">`Decimal`, `Single`, `Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a7c29-130">`Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="a7c29-131">Single</span><span class="sxs-lookup"><span data-stu-id="a7c29-131">Single</span></span>](../../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="a7c29-132">`Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="a7c29-132">`Single`, `Double`</span></span>|  
|[<span data-ttu-id="a7c29-133">Double</span><span class="sxs-lookup"><span data-stu-id="a7c29-133">Double</span></span>](../../../../visual-basic/language-reference/data-types/double-data-type.md)|`Double`|  
|<span data-ttu-id="a7c29-134">모든 열거형 형식 ([Enum](../../../../visual-basic/language-reference/statements/enum-statement.md))</span><span class="sxs-lookup"><span data-stu-id="a7c29-134">Any enumerated type ([Enum](../../../../visual-basic/language-reference/statements/enum-statement.md))</span></span>|<span data-ttu-id="a7c29-135">내부 정수 계열 형식 및 기본 형식을 확대 하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-135">Its underlying integral type and any type to which the underlying type widens.</span></span>|  
|[<span data-ttu-id="a7c29-136">Char</span><span class="sxs-lookup"><span data-stu-id="a7c29-136">Char</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="a7c29-137">`Char`, `String`</span><span class="sxs-lookup"><span data-stu-id="a7c29-137">`Char`, `String`</span></span>|  
|<span data-ttu-id="a7c29-138">`Char` 배열</span><span class="sxs-lookup"><span data-stu-id="a7c29-138">`Char` array</span></span>|<span data-ttu-id="a7c29-139">`Char` 배열 `String`</span><span class="sxs-lookup"><span data-stu-id="a7c29-139">`Char` array, `String`</span></span>|  
|<span data-ttu-id="a7c29-140">모든 형식</span><span class="sxs-lookup"><span data-stu-id="a7c29-140">Any type</span></span>|[<span data-ttu-id="a7c29-141">개체</span><span class="sxs-lookup"><span data-stu-id="a7c29-141">Object</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)|  
|<span data-ttu-id="a7c29-142">모든 파생된 형식</span><span class="sxs-lookup"><span data-stu-id="a7c29-142">Any derived type</span></span>|<span data-ttu-id="a7c29-143">모든 기본 파생 된 형식 <sup>3</sup>합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-143">Any base type from which it is derived <sup>3</sup>.</span></span>|  
|<span data-ttu-id="a7c29-144">모든 형식</span><span class="sxs-lookup"><span data-stu-id="a7c29-144">Any type</span></span>|<span data-ttu-id="a7c29-145">모든 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-145">Any interface it implements.</span></span>|  
|[<span data-ttu-id="a7c29-146">Nothing</span><span class="sxs-lookup"><span data-stu-id="a7c29-146">Nothing</span></span>](../../../../visual-basic/language-reference/nothing.md)|<span data-ttu-id="a7c29-147">모든 데이터 형식 또는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-147">Any data type or object type.</span></span>|  
  
 <span data-ttu-id="a7c29-148"><sup>1</sup> 정의 따라 모든 데이터 형식 자체를 확대 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-148"><sup>1</sup> By definition, every data type widens to itself.</span></span>  
  
 <span data-ttu-id="a7c29-149"><sup>2</sup> 변환할 `Integer`, `UInteger`, `Long`를 `ULong`, 또는 `Decimal` 에 `Single` 또는 `Double` 정밀도 손실 되지만 크기 손실 되지에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-149"><sup>2</sup> Conversions from `Integer`, `UInteger`, `Long`, `ULong`, or `Decimal` to `Single` or `Double` might result in loss of precision, but never in loss of magnitude.</span></span> <span data-ttu-id="a7c29-150">이런 점에서 정보 손실을 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-150">In this sense they do not incur information loss.</span></span>  
  
 <span data-ttu-id="a7c29-151"><sup>3</sup> 놀랍게 해당 기본 형식 중 하나에 파생된 형식에서 변환 확대 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-151"><sup>3</sup> It might seem surprising that a conversion from a derived type to one of its base types is widening.</span></span> <span data-ttu-id="a7c29-152">근거가 파생된 형식은 기본 형식의 모든 멤버는 포함 되므로 기본 형식의 인스턴스로 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-152">The justification is that the derived type contains all the members of the base type, so it qualifies as an instance of the base type.</span></span> <span data-ttu-id="a7c29-153">반대 방향에서 기본 형식이 파생된 형식에서 정의 된 모든 새 멤버를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-153">In the opposite direction, the base type does not contain any new members defined by the derived type.</span></span>  
  
 <span data-ttu-id="a7c29-154">확대 변환 런타임에 항상 실패 하 고 데이터가 손실 되지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="a7c29-154">Widening conversions always succeed at run time and never incur data loss.</span></span> <span data-ttu-id="a7c29-155">암시적으로 항상 수행할 수, 여부는 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 형식 검사 스위치를 설정 하는 `On` 또는 `Off`합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-155">You can always perform them implicitly, whether the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) sets the type checking switch to `On` or to `Off`.</span></span>  
  
## <a name="narrowing-conversions"></a><span data-ttu-id="a7c29-156">축소 변환</span><span class="sxs-lookup"><span data-stu-id="a7c29-156">Narrowing Conversions</span></span>  
 <span data-ttu-id="a7c29-157">표준 축소 변환에는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-157">The standard narrowing conversions include the following:</span></span>  
  
-   <span data-ttu-id="a7c29-158">앞의 확대 변환의 역방향 테이블 (한다는 점을 제외 하면 모든 형식은 자신에 게 확대)</span><span class="sxs-lookup"><span data-stu-id="a7c29-158">The reverse directions of the widening conversions in the preceding table (except that every type widens to itself)</span></span>  
  
-   <span data-ttu-id="a7c29-159">사이 변환 [부울](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) 및 숫자 형식</span><span class="sxs-lookup"><span data-stu-id="a7c29-159">Conversions in either direction between [Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) and any numeric type</span></span>  
  
-   <span data-ttu-id="a7c29-160">열거 형식에 임의의 숫자 형식에서 변환 (`Enum`)</span><span class="sxs-lookup"><span data-stu-id="a7c29-160">Conversions from any numeric type to any enumerated type (`Enum`)</span></span>  
  
-   <span data-ttu-id="a7c29-161">사이 변환 [문자열](../../../../visual-basic/language-reference/data-types/string-data-type.md) 모든 숫자 형식 `Boolean`, 또는 [날짜](../../../../visual-basic/language-reference/data-types/date-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="a7c29-161">Conversions in either direction between [String](../../../../visual-basic/language-reference/data-types/string-data-type.md) and any numeric type, `Boolean`, or [Date](../../../../visual-basic/language-reference/data-types/date-data-type.md)</span></span>  
  
-   <span data-ttu-id="a7c29-162">파생 된 형식으로 입력 데이터 형식 또는 개체에서 변환</span><span class="sxs-lookup"><span data-stu-id="a7c29-162">Conversions from a data type or object type to a type derived from it</span></span>  
  
 <span data-ttu-id="a7c29-163">축소 변환 수행 항상 런타임에 성공 및 실패 하거나 하 데이터 손실이 발생할 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-163">Narrowing conversions do not always succeed at run time, and can fail or incur data loss.</span></span> <span data-ttu-id="a7c29-164">대상 데이터 형식 변환 되는 값을 받을 수 없는 경우 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-164">An error occurs if the destination data type cannot receive the value being converted.</span></span> <span data-ttu-id="a7c29-165">예를 들어 숫자 변환 오버플로가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-165">For example, a numeric conversion can result in an overflow.</span></span> <span data-ttu-id="a7c29-166">컴파일러 없도록 하지 않은 경우 암시적 축소 변환을 수행 하는 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 형식 검사 스위치를 설정 하는 `Off`합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-166">The compiler does not allow you to perform narrowing conversions implicitly unless the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) sets the type checking switch to `Off`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7c29-167">축소 변환 오류 요소에서 변환에 대 한 표시 되지 않는지를 `For Each…Next` 루프 제어 변수 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-167">The narrowing-conversion error is suppressed for conversions from the elements in a `For Each…Next` collection to the loop control variable.</span></span> <span data-ttu-id="a7c29-168">자세한 내용 및 예제에 "Narrowing Conversions" 섹션을 참조 [각각에 대 한 중... 다음 문을](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-168">For more information and examples, see the "Narrowing Conversions" section in [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
### <a name="when-to-use-narrowing-conversions"></a><span data-ttu-id="a7c29-169">축소 변환을 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="a7c29-169">When to Use Narrowing Conversions</span></span>  
 <span data-ttu-id="a7c29-170">오류 또는 데이터 손실 없이 대상 데이터 형식으로 원본 값을 변환할 수를 알고 있는 경우에 축소 변환을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-170">You use a narrowing conversion when you know the source value can be converted to the destination data type without error or data loss.</span></span> <span data-ttu-id="a7c29-171">예를 들어 있는 경우는 `String` 는 "True" 또는 "False"를 포함 하는 것이 알고를 사용할 수는 `CBool` 변환할 키워드 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-171">For example, if you have a `String` that you know contains either "True" or "False," you can use the `CBool` keyword to convert it to `Boolean`.</span></span>  
  
## <a name="exceptions-during-conversion"></a><span data-ttu-id="a7c29-172">변환 중 예외</span><span class="sxs-lookup"><span data-stu-id="a7c29-172">Exceptions During Conversion</span></span>  
 <span data-ttu-id="a7c29-173">확대 변환은 항상 때문에 성공 하 고 예외를 throw 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-173">Because widening conversions always succeed, they do not throw exceptions.</span></span> <span data-ttu-id="a7c29-174">가장 일반적으로 축소 변환에 실패 하는 경우 다음 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-174">Narrowing conversions, when they fail, most commonly throw the following exceptions:</span></span>  
  
-   <span data-ttu-id="a7c29-175"><xref:System.InvalidCastException> -두 형식 간의 변환 작업 없이 정의 된 경우</span><span class="sxs-lookup"><span data-stu-id="a7c29-175"><xref:System.InvalidCastException> — if no conversion is defined between the two types</span></span>  
  
-   <span data-ttu-id="a7c29-176"><xref:System.OverflowException> -(정수 계열 형식만) 변환 된 값이 너무 커서 대상 유형에 적합 하지</span><span class="sxs-lookup"><span data-stu-id="a7c29-176"><xref:System.OverflowException> — (integral types only) if the converted value is too large for the target type</span></span>  
  
 <span data-ttu-id="a7c29-177">클래스 또는 구조를 정의 하는 경우는 [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) 변환 연산자와 해당 클래스 또는 구조체에서 역할을 하는 `CType` 적절 하다 고 판단 되는 모든 예외를 throw 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-177">If a class or structure defines a [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to serve as a conversion operator to or from that class or structure, that `CType` can throw any exception it deems appropriate.</span></span> <span data-ttu-id="a7c29-178">또한 하는 `CType` Visual Basic 함수를 호출할 수 있습니다 또는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 메서드를 다양 한 예외를 throw 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-178">In addition, that `CType` might call Visual Basic functions or [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] methods, which in turn could throw a variety of exceptions.</span></span>  
  
## <a name="changes-during-reference-type-conversions"></a><span data-ttu-id="a7c29-179">참조 형식 변환 중에 변경</span><span class="sxs-lookup"><span data-stu-id="a7c29-179">Changes During Reference Type Conversions</span></span>  
 <span data-ttu-id="a7c29-180">변환을 *유형을 참조* 포인터만 값을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-180">A conversion from a *reference type* copies only the pointer to the value.</span></span> <span data-ttu-id="a7c29-181">값 자체 복사 아니고 어떤 방식으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-181">The value itself is neither copied nor changed in any way.</span></span> <span data-ttu-id="a7c29-182">변경할 수 있는 유일한 항목은 포인터를가지고 있는 변수의 데이터 형식.</span><span class="sxs-lookup"><span data-stu-id="a7c29-182">The only thing that can change is the data type of the variable holding the pointer.</span></span> <span data-ttu-id="a7c29-183">다음 예제에서는 데이터 형식에서 파생된 클래스에서 클래스의 기본 클래스로 변환 됩니다 있지만 두 변수가 가리키는 개체는 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7c29-183">In the following example, the data type is converted from the derived class to its base class, but the object that both variables now point to is unchanged.</span></span>  
  
```  
' Assume class cSquare inherits from class cShape.  
Dim shape As cShape  
Dim square As cSquare = New cSquare  
' The following statement performs a widening  
' conversion from a derived class to its base class.  
shape = square  
```  
  
## <a name="see-also"></a><span data-ttu-id="a7c29-184">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7c29-184">See Also</span></span>  
 [<span data-ttu-id="a7c29-185">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a7c29-185">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="a7c29-186">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="a7c29-186">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="a7c29-187">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="a7c29-187">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="a7c29-188">문자열과 다른 형식 사이의 변환</span><span class="sxs-lookup"><span data-stu-id="a7c29-188">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [<span data-ttu-id="a7c29-189">방법: Visual Basic에서 다른 형식으로 변환할 개체</span><span class="sxs-lookup"><span data-stu-id="a7c29-189">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [<span data-ttu-id="a7c29-190">배열 규칙</span><span class="sxs-lookup"><span data-stu-id="a7c29-190">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 [<span data-ttu-id="a7c29-191">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a7c29-191">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="a7c29-192">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="a7c29-192">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
