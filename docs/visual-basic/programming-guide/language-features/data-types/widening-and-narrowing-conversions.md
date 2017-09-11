---
title: "확대 변환과 축소 변환 (Visual Basic) | Microsoft 문서"
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
- widening conversions
- narrowing conversions
- conversions, type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- conversions, exceptions during conversion
- type conversion, exceptions during conversion
- conversions, data type
- conversions, narrowing
- type conversion, narrowing
- data type conversion, widening
- data type conversion, narrowing
- changing data types
- type conversion, widening
- data type conversion, exceptions during conversion
- conversions, widening
ms.assetid: 058c3152-6c28-4268-af44-2209e774f0bd
caps.latest.revision: 27
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
ms.openlocfilehash: c00db1c631e1cc71df856407e8646532a73c6d44
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="widening-and-narrowing-conversions-visual-basic"></a><span data-ttu-id="ae5da-102">확대 변환과 축소 변환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae5da-102">Widening and Narrowing Conversions (Visual Basic)</span></span>
<span data-ttu-id="ae5da-103">고려해 야 할 형식 변환 대상 데이터 형식의 범위 내에서 변환의 결과 인지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-103">An important consideration with a type conversion is whether the result of the conversion is within the range of the destination data type.</span></span>  
  
 <span data-ttu-id="ae5da-104">A *확대 변환* 원래 데이터의 모든 가능한 값에 대해 허용할 수 있는 데이터 형식으로 값을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-104">A *widening conversion* changes a value to a data type that can allow for any possible value of the original data.</span></span>  <span data-ttu-id="ae5da-105">확대 변환 소스 값을 유지 하지만 표현 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-105">Widening conversions preserve the source value but can change its representation.</span></span> <span data-ttu-id="ae5da-106">정수 계열 형식에서 변환 하는 경우이 경고가 발생 `Decimal`, 또는 `Char` 를 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-106">This occurs if you convert from an integral type to `Decimal`, or from `Char` to `String`.</span></span>  
  
 <span data-ttu-id="ae5da-107">*축소 변환* 은 가능한 값의 일부를 저장하지 못할 수도 있는 데이터 형식으로 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-107">A *narrowing conversion* changes a value to a data type that might not be able to hold some of the possible values.</span></span> <span data-ttu-id="ae5da-108">숫자 형식으로 변환 되 고 정수 계열 형식으로 변환할 때 소수 자릿수 값은 반올림 하는 예를 들어 `Boolean` 로 `True` 또는 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-108">For example, a fractional value is rounded when it is converted to an integral type, and a numeric type being converted to `Boolean` is reduced to either `True` or `False`.</span></span>  
  
## <a name="widening-conversions"></a><span data-ttu-id="ae5da-109">확대 변환</span><span class="sxs-lookup"><span data-stu-id="ae5da-109">Widening Conversions</span></span>  
 <span data-ttu-id="ae5da-110">다음 표에서 표준 확대 변환을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-110">The following table shows the standard widening conversions.</span></span>  
  
|<span data-ttu-id="ae5da-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ae5da-111">Data type</span></span>|<span data-ttu-id="ae5da-112">데이터 형식 확장 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ae5da-112">Widens to data types <sup>1</sup></span></span>|  
|---|---|  
|[<span data-ttu-id="ae5da-113">SByte</span><span class="sxs-lookup"><span data-stu-id="ae5da-113">SByte</span></span>](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="ae5da-114">`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="ae5da-114">`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="ae5da-115">Byte</span><span class="sxs-lookup"><span data-stu-id="ae5da-115">Byte</span></span>](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="ae5da-116">`Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="ae5da-116">`Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="ae5da-117">짧은</span><span class="sxs-lookup"><span data-stu-id="ae5da-117">Short</span></span>](../../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="ae5da-118">`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="ae5da-118">`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="ae5da-119">UShort</span><span class="sxs-lookup"><span data-stu-id="ae5da-119">UShort</span></span>](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="ae5da-120">`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="ae5da-120">`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="ae5da-121">정수</span><span class="sxs-lookup"><span data-stu-id="ae5da-121">Integer</span></span>](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="ae5da-122">`Integer`, `Long`, `Decimal`, `Single`, `Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ae5da-122">`Integer`, `Long`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="ae5da-123">UInteger</span><span class="sxs-lookup"><span data-stu-id="ae5da-123">UInteger</span></span>](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="ae5da-124">`UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ae5da-124">`UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="ae5da-125">긴</span><span class="sxs-lookup"><span data-stu-id="ae5da-125">Long</span></span>](../../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="ae5da-126">`Long`, `Decimal`, `Single`, `Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ae5da-126">`Long`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="ae5da-127">ULong</span><span class="sxs-lookup"><span data-stu-id="ae5da-127">ULong</span></span>](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="ae5da-128">`ULong`, `Decimal`, `Single`, `Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ae5da-128">`ULong`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="ae5da-129">Decimal</span><span class="sxs-lookup"><span data-stu-id="ae5da-129">Decimal</span></span>](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="ae5da-130">`Decimal`, `Single`, `Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ae5da-130">`Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="ae5da-131">Single</span><span class="sxs-lookup"><span data-stu-id="ae5da-131">Single</span></span>](../../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="ae5da-132">`Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="ae5da-132">`Single`, `Double`</span></span>|  
|[<span data-ttu-id="ae5da-133">Double</span><span class="sxs-lookup"><span data-stu-id="ae5da-133">Double</span></span>](../../../../visual-basic/language-reference/data-types/double-data-type.md)|`Double`|  
|<span data-ttu-id="ae5da-134">모든 열거형 형식 ([Enum](../../../../visual-basic/language-reference/statements/enum-statement.md))</span><span class="sxs-lookup"><span data-stu-id="ae5da-134">Any enumerated type ([Enum](../../../../visual-basic/language-reference/statements/enum-statement.md))</span></span>|<span data-ttu-id="ae5da-135">내부 정수 계열 형식 및 기본 형식 확대 변환 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-135">Its underlying integral type and any type to which the underlying type widens.</span></span>|  
|[<span data-ttu-id="ae5da-136">Char</span><span class="sxs-lookup"><span data-stu-id="ae5da-136">Char</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="ae5da-137">`Char`, `String`</span><span class="sxs-lookup"><span data-stu-id="ae5da-137">`Char`, `String`</span></span>|  
|<span data-ttu-id="ae5da-138">`Char` 배열</span><span class="sxs-lookup"><span data-stu-id="ae5da-138">`Char` array</span></span>|<span data-ttu-id="ae5da-139">`Char`배열,`String`</span><span class="sxs-lookup"><span data-stu-id="ae5da-139">`Char` array, `String`</span></span>|  
|<span data-ttu-id="ae5da-140">모든 형식</span><span class="sxs-lookup"><span data-stu-id="ae5da-140">Any type</span></span>|[<span data-ttu-id="ae5da-141">개체</span><span class="sxs-lookup"><span data-stu-id="ae5da-141">Object</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)|  
|<span data-ttu-id="ae5da-142">모든 파생된 형식</span><span class="sxs-lookup"><span data-stu-id="ae5da-142">Any derived type</span></span>|<span data-ttu-id="ae5da-143">파생 된 형식의 기본 <sup>3</sup>합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-143">Any base type from which it is derived <sup>3</sup>.</span></span>|  
|<span data-ttu-id="ae5da-144">모든 형식</span><span class="sxs-lookup"><span data-stu-id="ae5da-144">Any type</span></span>|<span data-ttu-id="ae5da-145">모든 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-145">Any interface it implements.</span></span>|  
|[<span data-ttu-id="ae5da-146">Nothing</span><span class="sxs-lookup"><span data-stu-id="ae5da-146">Nothing</span></span>](../../../../visual-basic/language-reference/nothing.md)|<span data-ttu-id="ae5da-147">모든 데이터 형식이 나 개체 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-147">Any data type or object type.</span></span>|  
  
 <span data-ttu-id="ae5da-148"><sup>1</sup> 정의 따라 모든 데이터 형식에 자신에 게 확대 하는 변환입니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-148"><sup>1</sup> By definition, every data type widens to itself.</span></span>  
  
 <span data-ttu-id="ae5da-149"><sup>2</sup> 변환할 때 `Integer`, `UInteger`, `Long`, `ULong`, 또는 `Decimal` 를 `Single` 또는 `Double` 정밀도 손실에는 있지만 더 손실 되지에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-149"><sup>2</sup> Conversions from `Integer`, `UInteger`, `Long`, `ULong`, or `Decimal` to `Single` or `Double` might result in loss of precision, but never in loss of magnitude.</span></span> <span data-ttu-id="ae5da-150">이런이 의미에서 정보 손실이 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-150">In this sense they do not incur information loss.</span></span>  
  
 <span data-ttu-id="ae5da-151"><sup>3</sup> 파생된 형식 해당 형식의 기본 형식 중 하나로 변환 확대는 놀랍게 느껴질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-151"><sup>3</sup> It might seem surprising that a conversion from a derived type to one of its base types is widening.</span></span> <span data-ttu-id="ae5da-152">양쪽 맞춤을 파생된 된 유형의 기본 형식의 인스턴스를 정규화 하도록 기본 형식의 모든 멤버를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-152">The justification is that the derived type contains all the members of the base type, so it qualifies as an instance of the base type.</span></span> <span data-ttu-id="ae5da-153">반대 방향으로 기본 형식이 파생된 형식에서 정의 된 모든 새 멤버를 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-153">In the opposite direction, the base type does not contain any new members defined by the derived type.</span></span>  
  
 <span data-ttu-id="ae5da-154">확대 변환을 수행 하면 런타임 시 항상 실패 하 고 데이터가 손실 되지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="ae5da-154">Widening conversions always succeed at run time and never incur data loss.</span></span> <span data-ttu-id="ae5da-155">암시적으로 항상 수행할 수 있는지 여부,는 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 형식 검사 스위치를 설정 하는 `On` 또는 `Off`합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-155">You can always perform them implicitly, whether the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) sets the type checking switch to `On` or to `Off`.</span></span>  
  
## <a name="narrowing-conversions"></a><span data-ttu-id="ae5da-156">축소 변환</span><span class="sxs-lookup"><span data-stu-id="ae5da-156">Narrowing Conversions</span></span>  
 <span data-ttu-id="ae5da-157">표준 축소 변환에는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-157">The standard narrowing conversions include the following:</span></span>  
  
-   <span data-ttu-id="ae5da-158">앞에 확대 변환의 역방향 테이블 (한다는 점을 제외 하면 모든 형식은 자체로 확대 변환)</span><span class="sxs-lookup"><span data-stu-id="ae5da-158">The reverse directions of the widening conversions in the preceding table (except that every type widens to itself)</span></span>  
  
-   <span data-ttu-id="ae5da-159">사이 변환 [부울](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) 및 숫자 형식</span><span class="sxs-lookup"><span data-stu-id="ae5da-159">Conversions in either direction between [Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) and any numeric type</span></span>  
  
-   <span data-ttu-id="ae5da-160">열거 형식에 임의의 숫자 형식에서 변환 (`Enum`)</span><span class="sxs-lookup"><span data-stu-id="ae5da-160">Conversions from any numeric type to any enumerated type (`Enum`)</span></span>  
  
-   <span data-ttu-id="ae5da-161">사이 변환 [문자열](../../../../visual-basic/language-reference/data-types/string-data-type.md) 및 숫자 형식, `Boolean`, 또는 [날짜](../../../../visual-basic/language-reference/data-types/date-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="ae5da-161">Conversions in either direction between [String](../../../../visual-basic/language-reference/data-types/string-data-type.md) and any numeric type, `Boolean`, or [Date](../../../../visual-basic/language-reference/data-types/date-data-type.md)</span></span>  
  
-   <span data-ttu-id="ae5da-162">파생 된 형식으로 입력 데이터 형식이 나 개체에서 변환</span><span class="sxs-lookup"><span data-stu-id="ae5da-162">Conversions from a data type or object type to a type derived from it</span></span>  
  
 <span data-ttu-id="ae5da-163">축소 변환을 항상 실행 시 성공 하 고 수 실패 하거나 데이터가 손실 될.</span><span class="sxs-lookup"><span data-stu-id="ae5da-163">Narrowing conversions do not always succeed at run time, and can fail or incur data loss.</span></span> <span data-ttu-id="ae5da-164">오류는 대상 데이터 형식 변환 되는 값을 받을 수 없는 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-164">An error occurs if the destination data type cannot receive the value being converted.</span></span> <span data-ttu-id="ae5da-165">예를 들어 숫자 변환 하면 오버플로가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-165">For example, a numeric conversion can result in an overflow.</span></span> <span data-ttu-id="ae5da-166">컴파일러 없도록 하지 않으면 암시적으로 축소 변환을 수행 하는 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 형식 검사 스위치를 설정 하는 `Off`합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-166">The compiler does not allow you to perform narrowing conversions implicitly unless the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) sets the type checking switch to `Off`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae5da-167">축소 변환 오류에 있는 요소에서 변환에 대해 무시 됩니다는 `For Each…Next` 루프 제어 변수 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-167">The narrowing-conversion error is suppressed for conversions from the elements in a `For Each…Next` collection to the loop control variable.</span></span> <span data-ttu-id="ae5da-168">자세한 내용과 예제는 "축소 변환" 섹션을 참조 [각각에 대해... 다음 문](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-168">For more information and examples, see the "Narrowing Conversions" section in [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
### <a name="when-to-use-narrowing-conversions"></a><span data-ttu-id="ae5da-169">축소 변환을 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="ae5da-169">When to Use Narrowing Conversions</span></span>  
 <span data-ttu-id="ae5da-170">오류 또는 데이터 손실 없이 대상 데이터 형식으로 변환할 수 소스 값을 알고 있는 경우에 축소 변환을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-170">You use a narrowing conversion when you know the source value can be converted to the destination data type without error or data loss.</span></span> <span data-ttu-id="ae5da-171">예를 들어 한 `String` 가진다는 사실을 알고 "True" 또는 "False"를 사용할 수 있습니다는 `CBool` 변환할 키워드 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-171">For example, if you have a `String` that you know contains either "True" or "False," you can use the `CBool` keyword to convert it to `Boolean`.</span></span>  
  
## <a name="exceptions-during-conversion"></a><span data-ttu-id="ae5da-172">변환 중 예외</span><span class="sxs-lookup"><span data-stu-id="ae5da-172">Exceptions During Conversion</span></span>  
 <span data-ttu-id="ae5da-173">확대 변환은 항상 때문에 성공 하 고 예외를 throw 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-173">Because widening conversions always succeed, they do not throw exceptions.</span></span> <span data-ttu-id="ae5da-174">가장 일반적으로 축소 변환을 실패할 경우 다음 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-174">Narrowing conversions, when they fail, most commonly throw the following exceptions:</span></span>  
  
-   <span data-ttu-id="ae5da-175"><xref:System.InvalidCastException>-두 형식 간의 정의 된 변환이 없는 경우</xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="ae5da-175"><xref:System.InvalidCastException> — if no conversion is defined between the two types</span></span>  
  
-   <span data-ttu-id="ae5da-176"><xref:System.OverflowException>-(정수 계열 형식만) 변환 된 값이 너무 커서 대상 유형에 적합 한 경우</xref:System.OverflowException></span><span class="sxs-lookup"><span data-stu-id="ae5da-176"><xref:System.OverflowException> — (integral types only) if the converted value is too large for the target type</span></span>  
  
 <span data-ttu-id="ae5da-177">클래스 또는 구조체 정의 하는 경우는 [CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md) 변환 연산자 또는 해당 클래스 또는 구조체를 제공 하는 `CType` 적절 하다 고 판단 되는 모든 예외를 throw 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-177">If a class or structure defines a [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to serve as a conversion operator to or from that class or structure, that `CType` can throw any exception it deems appropriate.</span></span> <span data-ttu-id="ae5da-178">또한는 `CType` 호출할 수 있는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 함수 또는 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] 다양 한 예외 throw 할 수 있는 메서드.</span><span class="sxs-lookup"><span data-stu-id="ae5da-178">In addition, that `CType` might call [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] functions or [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] methods, which in turn could throw a variety of exceptions.</span></span>  
  
## <a name="changes-during-reference-type-conversions"></a><span data-ttu-id="ae5da-179">참조 형식 변환 하는 동안 변경 내용</span><span class="sxs-lookup"><span data-stu-id="ae5da-179">Changes During Reference Type Conversions</span></span>  
 <span data-ttu-id="ae5da-180">변환은 *참조 형식* 포인터만 값에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-180">A conversion from a *reference type* copies only the pointer to the value.</span></span> <span data-ttu-id="ae5da-181">값 자체는 복사 되거나 어떤 식으로든에서 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-181">The value itself is neither copied nor changed in any way.</span></span> <span data-ttu-id="ae5da-182">변경할 수 있는 유일한 항목에 포인터를가지고 있는 변수의 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-182">The only thing that can change is the data type of the variable holding the pointer.</span></span> <span data-ttu-id="ae5da-183">다음 예제에서는 해당 기본 클래스를 파생된 클래스에서 데이터 형식을 변환 됩니다 되지만 두 변수가 가리키는 개체는 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae5da-183">In the following example, the data type is converted from the derived class to its base class, but the object that both variables now point to is unchanged.</span></span>  
  
```  
' Assume class cSquare inherits from class cShape.  
Dim shape As cShape  
Dim square As cSquare = New cSquare  
' The following statement performs a widening  
' conversion from a derived class to its base class.  
shape = square  
```  
  
## <a name="see-also"></a><span data-ttu-id="ae5da-184">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae5da-184">See Also</span></span>  
 <span data-ttu-id="ae5da-185">[데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="ae5da-185">[Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span></span>  
<span data-ttu-id="ae5da-186"> [Visual Basic의 형식 변환](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="ae5da-186"> [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="ae5da-187"> [암시적 변환과 명시적 변환](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="ae5da-187"> [Implicit and Explicit Conversions](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span></span>  
<span data-ttu-id="ae5da-188"> [문자열과 다른 형식 간의 변환](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md) </span><span class="sxs-lookup"><span data-stu-id="ae5da-188"> [Conversions Between Strings and Other Types](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md) </span></span>  
<span data-ttu-id="ae5da-189"> [방법: Visual Basic에서 다른 형식으로 변환](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md) </span><span class="sxs-lookup"><span data-stu-id="ae5da-189"> [How to: Convert an Object to Another Type in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md) </span></span>  
<span data-ttu-id="ae5da-190"> [배열 변환](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="ae5da-190"> [Array Conversions](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md) </span></span>  
<span data-ttu-id="ae5da-191"> [데이터 형식](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="ae5da-191"> [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
<span data-ttu-id="ae5da-192"> [형식 변환 함수](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)</span><span class="sxs-lookup"><span data-stu-id="ae5da-192"> [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)</span></span>
