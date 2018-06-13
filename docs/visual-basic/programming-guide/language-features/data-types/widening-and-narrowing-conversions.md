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
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655421"
---
# <a name="widening-and-narrowing-conversions-visual-basic"></a><span data-ttu-id="d739e-102">확대 변환과 축소 변환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d739e-102">Widening and Narrowing Conversions (Visual Basic)</span></span>
<span data-ttu-id="d739e-103">형식 변환에 중요 한 고려 사항은 변환 결과 대상 데이터 형식의 범위 이내 인지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-103">An important consideration with a type conversion is whether the result of the conversion is within the range of the destination data type.</span></span>  
  
 <span data-ttu-id="d739e-104">A *확대 변환* 원래 데이터의 모든 가능한 값에 대해 허용할 수 있는 데이터 형식으로 값을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-104">A *widening conversion* changes a value to a data type that can allow for any possible value of the original data.</span></span>  <span data-ttu-id="d739e-105">확대 변환 소스 값을 유지 하지만 표현 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-105">Widening conversions preserve the source value but can change its representation.</span></span> <span data-ttu-id="d739e-106">정수 계열 형식에서 변환 하는 경우이 경고가 발생 `Decimal`, 또는 `Char` 를 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-106">This occurs if you convert from an integral type to `Decimal`, or from `Char` to `String`.</span></span>  
  
 <span data-ttu-id="d739e-107">*축소 변환* 은 가능한 값의 일부를 저장하지 못할 수도 있는 데이터 형식으로 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-107">A *narrowing conversion* changes a value to a data type that might not be able to hold some of the possible values.</span></span> <span data-ttu-id="d739e-108">정수 계열 형식 및 숫자 형식으로 변환 되 고 변환 될 때 소수 자릿수 값은 반올림 하는 예를 들어 `Boolean` 로 `True` 또는 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-108">For example, a fractional value is rounded when it is converted to an integral type, and a numeric type being converted to `Boolean` is reduced to either `True` or `False`.</span></span>  
  
## <a name="widening-conversions"></a><span data-ttu-id="d739e-109">확대 변환</span><span class="sxs-lookup"><span data-stu-id="d739e-109">Widening Conversions</span></span>  
 <span data-ttu-id="d739e-110">다음 표에서 표준 확대 변환을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-110">The following table shows the standard widening conversions.</span></span>  
  
|<span data-ttu-id="d739e-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d739e-111">Data type</span></span>|<span data-ttu-id="d739e-112">데이터 형식 확장 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d739e-112">Widens to data types <sup>1</sup></span></span>|  
|---|---|  
|[<span data-ttu-id="d739e-113">SByte</span><span class="sxs-lookup"><span data-stu-id="d739e-113">SByte</span></span>](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="d739e-114">`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="d739e-114">`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="d739e-115">Byte</span><span class="sxs-lookup"><span data-stu-id="d739e-115">Byte</span></span>](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="d739e-116">`Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="d739e-116">`Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="d739e-117">Short</span><span class="sxs-lookup"><span data-stu-id="d739e-117">Short</span></span>](../../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="d739e-118">`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="d739e-118">`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="d739e-119">UShort</span><span class="sxs-lookup"><span data-stu-id="d739e-119">UShort</span></span>](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="d739e-120">`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="d739e-120">`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="d739e-121">Integer</span><span class="sxs-lookup"><span data-stu-id="d739e-121">Integer</span></span>](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="d739e-122">`Integer`, `Long`, `Decimal`, `Single`, `Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d739e-122">`Integer`, `Long`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="d739e-123">UInteger</span><span class="sxs-lookup"><span data-stu-id="d739e-123">UInteger</span></span>](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="d739e-124">`UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d739e-124">`UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="d739e-125">Long</span><span class="sxs-lookup"><span data-stu-id="d739e-125">Long</span></span>](../../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="d739e-126">`Long`, `Decimal`, `Single`, `Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d739e-126">`Long`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="d739e-127">ULong</span><span class="sxs-lookup"><span data-stu-id="d739e-127">ULong</span></span>](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="d739e-128">`ULong`, `Decimal`, `Single`, `Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d739e-128">`ULong`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="d739e-129">Decimal</span><span class="sxs-lookup"><span data-stu-id="d739e-129">Decimal</span></span>](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="d739e-130">`Decimal`, `Single`, `Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d739e-130">`Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="d739e-131">Single</span><span class="sxs-lookup"><span data-stu-id="d739e-131">Single</span></span>](../../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="d739e-132">`Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="d739e-132">`Single`, `Double`</span></span>|  
|[<span data-ttu-id="d739e-133">Double</span><span class="sxs-lookup"><span data-stu-id="d739e-133">Double</span></span>](../../../../visual-basic/language-reference/data-types/double-data-type.md)|`Double`|  
|<span data-ttu-id="d739e-134">모든 열거형 형식 ([Enum](../../../../visual-basic/language-reference/statements/enum-statement.md))</span><span class="sxs-lookup"><span data-stu-id="d739e-134">Any enumerated type ([Enum](../../../../visual-basic/language-reference/statements/enum-statement.md))</span></span>|<span data-ttu-id="d739e-135">내부 정수 계열 형식 및 모든 형식을 내부 형식 확대 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-135">Its underlying integral type and any type to which the underlying type widens.</span></span>|  
|[<span data-ttu-id="d739e-136">Char</span><span class="sxs-lookup"><span data-stu-id="d739e-136">Char</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="d739e-137">`Char`, `String`</span><span class="sxs-lookup"><span data-stu-id="d739e-137">`Char`, `String`</span></span>|  
|<span data-ttu-id="d739e-138">`Char` 배열</span><span class="sxs-lookup"><span data-stu-id="d739e-138">`Char` array</span></span>|<span data-ttu-id="d739e-139">`Char` 배열에 `String`</span><span class="sxs-lookup"><span data-stu-id="d739e-139">`Char` array, `String`</span></span>|  
|<span data-ttu-id="d739e-140">모든 형식</span><span class="sxs-lookup"><span data-stu-id="d739e-140">Any type</span></span>|[<span data-ttu-id="d739e-141">개체</span><span class="sxs-lookup"><span data-stu-id="d739e-141">Object</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)|  
|<span data-ttu-id="d739e-142">모든 파생된 형식</span><span class="sxs-lookup"><span data-stu-id="d739e-142">Any derived type</span></span>|<span data-ttu-id="d739e-143">파생 된 형식의 기본 <sup>3</sup>합니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-143">Any base type from which it is derived <sup>3</sup>.</span></span>|  
|<span data-ttu-id="d739e-144">모든 형식</span><span class="sxs-lookup"><span data-stu-id="d739e-144">Any type</span></span>|<span data-ttu-id="d739e-145">모든 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-145">Any interface it implements.</span></span>|  
|[<span data-ttu-id="d739e-146">Nothing</span><span class="sxs-lookup"><span data-stu-id="d739e-146">Nothing</span></span>](../../../../visual-basic/language-reference/nothing.md)|<span data-ttu-id="d739e-147">모든 데이터 형식이 나 개체 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-147">Any data type or object type.</span></span>|  
  
 <span data-ttu-id="d739e-148"><sup>1</sup> 정의 따라 모든 데이터 형식에 자신에 게 확대 하는 변환입니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-148"><sup>1</sup> By definition, every data type widens to itself.</span></span>  
  
 <span data-ttu-id="d739e-149"><sup>2</sup> 변환할 때 `Integer`, `UInteger`, `Long`, `ULong`, 또는 `Decimal` 를 `Single` 또는 `Double` 정밀도 손실에는 있지만 더 손실 되지에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-149"><sup>2</sup> Conversions from `Integer`, `UInteger`, `Long`, `ULong`, or `Decimal` to `Single` or `Double` might result in loss of precision, but never in loss of magnitude.</span></span> <span data-ttu-id="d739e-150">이런이 의미에서 정보 손실이 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-150">In this sense they do not incur information loss.</span></span>  
  
 <span data-ttu-id="d739e-151"><sup>3</sup> 파생된 된 형식 기본 형식 중 하나로 변환은 확대 처럼 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-151"><sup>3</sup> It might seem surprising that a conversion from a derived type to one of its base types is widening.</span></span> <span data-ttu-id="d739e-152">양쪽 맞춤을 파생된 형식이 기본 형식의 인스턴스로 한정 되므로 기본 형식의 모든 멤버를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-152">The justification is that the derived type contains all the members of the base type, so it qualifies as an instance of the base type.</span></span> <span data-ttu-id="d739e-153">반대 방향으로의 기본 형식에 파생된 형식에서 정의 된 모든 새 멤버</span><span class="sxs-lookup"><span data-stu-id="d739e-153">In the opposite direction, the base type does not contain any new members defined by the derived type.</span></span>  
  
 <span data-ttu-id="d739e-154">확대 변환 실행 시 항상 성공 하 고 데이터가 손실 되지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="d739e-154">Widening conversions always succeed at run time and never incur data loss.</span></span> <span data-ttu-id="d739e-155">암시적으로 항상 수행할 수 있는지 여부,는 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 형식 검사 스위치를 설정 하는 `On` 또는 `Off`합니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-155">You can always perform them implicitly, whether the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) sets the type checking switch to `On` or to `Off`.</span></span>  
  
## <a name="narrowing-conversions"></a><span data-ttu-id="d739e-156">축소 변환</span><span class="sxs-lookup"><span data-stu-id="d739e-156">Narrowing Conversions</span></span>  
 <span data-ttu-id="d739e-157">표준 축소 변환에는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-157">The standard narrowing conversions include the following:</span></span>  
  
-   <span data-ttu-id="d739e-158">앞의 확대 변환이의 역방향 테이블 (제외 하 고 자신에 게 모든 형식이 확장 되는지를)</span><span class="sxs-lookup"><span data-stu-id="d739e-158">The reverse directions of the widening conversions in the preceding table (except that every type widens to itself)</span></span>  
  
-   <span data-ttu-id="d739e-159">사이 변환 [부울](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) 모든 숫자 형식</span><span class="sxs-lookup"><span data-stu-id="d739e-159">Conversions in either direction between [Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) and any numeric type</span></span>  
  
-   <span data-ttu-id="d739e-160">열거 형식에 임의의 숫자 형식에서 변환 (`Enum`)</span><span class="sxs-lookup"><span data-stu-id="d739e-160">Conversions from any numeric type to any enumerated type (`Enum`)</span></span>  
  
-   <span data-ttu-id="d739e-161">사이 변환 [문자열](../../../../visual-basic/language-reference/data-types/string-data-type.md) 모든 숫자 형식 `Boolean`, 또는 [날짜](../../../../visual-basic/language-reference/data-types/date-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="d739e-161">Conversions in either direction between [String](../../../../visual-basic/language-reference/data-types/string-data-type.md) and any numeric type, `Boolean`, or [Date](../../../../visual-basic/language-reference/data-types/date-data-type.md)</span></span>  
  
-   <span data-ttu-id="d739e-162">파생 된 형식으로 입력 데이터 형식이 나 개체에서 변환</span><span class="sxs-lookup"><span data-stu-id="d739e-162">Conversions from a data type or object type to a type derived from it</span></span>  
  
 <span data-ttu-id="d739e-163">축소 변환 않는 항상 실행 시 성공 및 실패 하거나 하 데이터 손실이 발생할 합니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-163">Narrowing conversions do not always succeed at run time, and can fail or incur data loss.</span></span> <span data-ttu-id="d739e-164">오류가 대상 데이터 형식 변환 되는 값을 받을 수 없는 경우 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-164">An error occurs if the destination data type cannot receive the value being converted.</span></span> <span data-ttu-id="d739e-165">예를 들어 숫자 변환 하면 오버플로가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-165">For example, a numeric conversion can result in an overflow.</span></span> <span data-ttu-id="d739e-166">컴파일러 허용 하지 않는 한 축소 변환을 암시적으로 수행 하지 않습니다는 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 형식 검사 스위치를 설정 하는 `Off`합니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-166">The compiler does not allow you to perform narrowing conversions implicitly unless the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) sets the type checking switch to `Off`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d739e-167">요소에서 변환에 축소 변환 오류가 기록 됩니다는 `For Each…Next` 루프 제어 변수 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-167">The narrowing-conversion error is suppressed for conversions from the elements in a `For Each…Next` collection to the loop control variable.</span></span> <span data-ttu-id="d739e-168">자세한 내용과 예제는 "축소 변환" 섹션을 참조 [각각에 대해... 다음 문](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-168">For more information and examples, see the "Narrowing Conversions" section in [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
### <a name="when-to-use-narrowing-conversions"></a><span data-ttu-id="d739e-169">축소 변환을 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="d739e-169">When to Use Narrowing Conversions</span></span>  
 <span data-ttu-id="d739e-170">오류 또는 데이터 손실 없이 대상 데이터 형식으로 변환할 수 소스 값을 알고 있는 경우에 축소 변환을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-170">You use a narrowing conversion when you know the source value can be converted to the destination data type without error or data loss.</span></span> <span data-ttu-id="d739e-171">예를 들어 한 `String` 를 "True" 또는 "False"를 포함 하는 것이 알아야를 사용할 수 있습니다는 `CBool` 변환할 키워드 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-171">For example, if you have a `String` that you know contains either "True" or "False," you can use the `CBool` keyword to convert it to `Boolean`.</span></span>  
  
## <a name="exceptions-during-conversion"></a><span data-ttu-id="d739e-172">변환 중 예외</span><span class="sxs-lookup"><span data-stu-id="d739e-172">Exceptions During Conversion</span></span>  
 <span data-ttu-id="d739e-173">확대 변환은 항상 때문에 성공 하 고 예외를 throw 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-173">Because widening conversions always succeed, they do not throw exceptions.</span></span> <span data-ttu-id="d739e-174">실패할 경우에 축소 변환이 가장 일반적으로 다음과 같은 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-174">Narrowing conversions, when they fail, most commonly throw the following exceptions:</span></span>  
  
-   <span data-ttu-id="d739e-175"><xref:System.InvalidCastException> -두 형식 간의 정의 된 변환이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="d739e-175"><xref:System.InvalidCastException> — if no conversion is defined between the two types</span></span>  
  
-   <span data-ttu-id="d739e-176"><xref:System.OverflowException> -(정수 계열 형식만) 변환 된 값이 너무 커서 대상 유형에 적합 하지</span><span class="sxs-lookup"><span data-stu-id="d739e-176"><xref:System.OverflowException> — (integral types only) if the converted value is too large for the target type</span></span>  
  
 <span data-ttu-id="d739e-177">클래스 또는 구조체 정의 하는 경우는 [CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md) 변환 연산자 또는 해당 클래스 또는 구조체에서 역할을 하는 `CType` 적절 하다 고 판단 되는 모든 예외를 throw 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-177">If a class or structure defines a [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to serve as a conversion operator to or from that class or structure, that `CType` can throw any exception it deems appropriate.</span></span> <span data-ttu-id="d739e-178">또한 하 `CType` Visual Basic 함수를 호출할 수 있습니다 또는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 는 다양 한 예외를 throw 할 수 있는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-178">In addition, that `CType` might call Visual Basic functions or [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] methods, which in turn could throw a variety of exceptions.</span></span>  
  
## <a name="changes-during-reference-type-conversions"></a><span data-ttu-id="d739e-179">참조 형식 변환 하는 동안 변경 내용</span><span class="sxs-lookup"><span data-stu-id="d739e-179">Changes During Reference Type Conversions</span></span>  
 <span data-ttu-id="d739e-180">변환은 *유형을 참조* 포인터만 값으로 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-180">A conversion from a *reference type* copies only the pointer to the value.</span></span> <span data-ttu-id="d739e-181">값 자체 복사 아니고 어떤 식으로든에서 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-181">The value itself is neither copied nor changed in any way.</span></span> <span data-ttu-id="d739e-182">변경할 수 있는 유일한 항목에는 포인터를가지고 있는 변수의 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-182">The only thing that can change is the data type of the variable holding the pointer.</span></span> <span data-ttu-id="d739e-183">다음 예제에서는 데이터 형식은 해당 기본 클래스나 파생된 클래스에서 변환 됩니다 있지만 두 변수가 가리키는 개체는 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d739e-183">In the following example, the data type is converted from the derived class to its base class, but the object that both variables now point to is unchanged.</span></span>  
  
```  
' Assume class cSquare inherits from class cShape.  
Dim shape As cShape  
Dim square As cSquare = New cSquare  
' The following statement performs a widening  
' conversion from a derived class to its base class.  
shape = square  
```  
  
## <a name="see-also"></a><span data-ttu-id="d739e-184">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d739e-184">See Also</span></span>  
 [<span data-ttu-id="d739e-185">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d739e-185">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="d739e-186">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="d739e-186">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="d739e-187">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="d739e-187">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="d739e-188">문자열과 다른 형식 사이의 변환</span><span class="sxs-lookup"><span data-stu-id="d739e-188">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [<span data-ttu-id="d739e-189">방법: Visual Basic에서 다른 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="d739e-189">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [<span data-ttu-id="d739e-190">배열 규칙</span><span class="sxs-lookup"><span data-stu-id="d739e-190">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 [<span data-ttu-id="d739e-191">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d739e-191">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="d739e-192">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="d739e-192">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
