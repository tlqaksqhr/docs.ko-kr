---
title: "명시적 숫자 변환 표(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- conversions [C#], explicit numeric
- numeric conversions [C#], explicit
- explicit numeric conversion [C#]
- numeric data types [C#]
- types [C#], explicit numeric conversions
- type conversion [C#], explicit numeric
ms.assetid: f3bb9e76-6b92-4df7-bc36-f866c24e1dfd
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0315810522be319a6bb565c99e1c8f7d1ba4701b
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="explicit-numeric-conversions-table-c-reference"></a><span data-ttu-id="7eac7-102">명시적 숫자 변환 표(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="7eac7-102">Explicit Numeric Conversions Table (C# Reference)</span></span>
<span data-ttu-id="7eac7-103">명시적 숫자 변환은 캐스트 식을 사용하여 숫자 형식을 암시적 변환이 없는 다른 숫자 형식으로 변환하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7eac7-103">Explicit numeric conversion is used to convert any numeric type to any other numeric type, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="7eac7-104">다음 표에는 이러한 변환이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7eac7-104">The following table shows these conversions.</span></span>  
  
 <span data-ttu-id="7eac7-105">변환에 대한 자세한 내용은 [캐스팅 및 형식 변환](../../../csharp/programming-guide/types/casting-and-type-conversions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7eac7-105">For more information about conversions, see [Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span></span>  
  
|<span data-ttu-id="7eac7-106">시작</span><span class="sxs-lookup"><span data-stu-id="7eac7-106">From</span></span>|<span data-ttu-id="7eac7-107">대상</span><span class="sxs-lookup"><span data-stu-id="7eac7-107">To</span></span>|  
|----------|--------|  
|[<span data-ttu-id="7eac7-108">sbyte</span><span class="sxs-lookup"><span data-stu-id="7eac7-108">sbyte</span></span>](../../../csharp/language-reference/keywords/sbyte.md)|<span data-ttu-id="7eac7-109">`byte`, `ushort`, `uint`, `ulong` 또는 `char`</span><span class="sxs-lookup"><span data-stu-id="7eac7-109">`byte`, `ushort`, `uint`, `ulong`, or `char`</span></span>|  
|[<span data-ttu-id="7eac7-110">byte</span><span class="sxs-lookup"><span data-stu-id="7eac7-110">byte</span></span>](../../../csharp/language-reference/keywords/byte.md)|<span data-ttu-id="7eac7-111">`Sbyte` 또는 `char`</span><span class="sxs-lookup"><span data-stu-id="7eac7-111">`Sbyte` or `char`</span></span>|  
|[<span data-ttu-id="7eac7-112">short</span><span class="sxs-lookup"><span data-stu-id="7eac7-112">short</span></span>](../../../csharp/language-reference/keywords/short.md)|<span data-ttu-id="7eac7-113">`sbyte`, `byte`, `ushort`, `uint`, `ulong` 또는 `char`</span><span class="sxs-lookup"><span data-stu-id="7eac7-113">`sbyte`, `byte`, `ushort`, `uint`, `ulong`, or `char`</span></span>|  
|[<span data-ttu-id="7eac7-114">ushort</span><span class="sxs-lookup"><span data-stu-id="7eac7-114">ushort</span></span>](../../../csharp/language-reference/keywords/ushort.md)|<span data-ttu-id="7eac7-115">`sbyte`, `byte`, `short` 또는 `char`</span><span class="sxs-lookup"><span data-stu-id="7eac7-115">`sbyte`, `byte`, `short`, or `char`</span></span>|  
|[<span data-ttu-id="7eac7-116">int</span><span class="sxs-lookup"><span data-stu-id="7eac7-116">int</span></span>](../../../csharp/language-reference/keywords/int.md)|<span data-ttu-id="7eac7-117">`sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong` 또는 `char`</span><span class="sxs-lookup"><span data-stu-id="7eac7-117">`sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong`,or `char`</span></span>|  
|[<span data-ttu-id="7eac7-118">uint</span><span class="sxs-lookup"><span data-stu-id="7eac7-118">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)|<span data-ttu-id="7eac7-119">`sbyte`, `byte`, `short`, `ushort`, `int` 또는 `char`</span><span class="sxs-lookup"><span data-stu-id="7eac7-119">`sbyte`, `byte`, `short`, `ushort`, `int`, or `char`</span></span>|  
|[<span data-ttu-id="7eac7-120">long</span><span class="sxs-lookup"><span data-stu-id="7eac7-120">long</span></span>](../../../csharp/language-reference/keywords/long.md)|<span data-ttu-id="7eac7-121">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `ulong` 또는 `char`</span><span class="sxs-lookup"><span data-stu-id="7eac7-121">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `ulong`, or `char`</span></span>|  
|[<span data-ttu-id="7eac7-122">ulong</span><span class="sxs-lookup"><span data-stu-id="7eac7-122">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)|<span data-ttu-id="7eac7-123">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long` 또는 `char`</span><span class="sxs-lookup"><span data-stu-id="7eac7-123">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, or `char`</span></span>|  
|[<span data-ttu-id="7eac7-124">char</span><span class="sxs-lookup"><span data-stu-id="7eac7-124">char</span></span>](../../../csharp/language-reference/keywords/char.md)|<span data-ttu-id="7eac7-125">`sbyte`, `byte` 또는 `short`</span><span class="sxs-lookup"><span data-stu-id="7eac7-125">`sbyte`, `byte`, or `short`</span></span>|  
|[<span data-ttu-id="7eac7-126">float</span><span class="sxs-lookup"><span data-stu-id="7eac7-126">float</span></span>](../../../csharp/language-reference/keywords/float.md)|<span data-ttu-id="7eac7-127">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char` 또는 `decimal`</span><span class="sxs-lookup"><span data-stu-id="7eac7-127">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`,or `decimal`</span></span>|  
|[<span data-ttu-id="7eac7-128">double</span><span class="sxs-lookup"><span data-stu-id="7eac7-128">double</span></span>](../../../csharp/language-reference/keywords/double.md)|<span data-ttu-id="7eac7-129">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` 또는 `decimal`</span><span class="sxs-lookup"><span data-stu-id="7eac7-129">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`,or `decimal`</span></span>|  
|[<span data-ttu-id="7eac7-130">decimal</span><span class="sxs-lookup"><span data-stu-id="7eac7-130">decimal</span></span>](../../../csharp/language-reference/keywords/decimal.md)|<span data-ttu-id="7eac7-131">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` 또는 `double`</span><span class="sxs-lookup"><span data-stu-id="7eac7-131">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, or `double`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7eac7-132">설명</span><span class="sxs-lookup"><span data-stu-id="7eac7-132">Remarks</span></span>  
  
-   <span data-ttu-id="7eac7-133">명시적 숫자 변환으로 인하여 자릿수 손실 또는 예외 throw가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7eac7-133">The explicit numeric conversion may cause loss of precision or result in throwing exceptions.</span></span>  
  
-   <span data-ttu-id="7eac7-134">`decimal` 값을 정수 형식으로 변환하면, 이 값은 0을 향한 방향으로 가장 가까운 정수값으로 반올림됩니다.</span><span class="sxs-lookup"><span data-stu-id="7eac7-134">When you convert a `decimal` value to an integral type, this value is rounded towards zero to the nearest integral value.</span></span> <span data-ttu-id="7eac7-135">결과 정수 값이 대상 형식 범위에서 벗어났을 경우 <xref:System.OverflowException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="7eac7-135">If the resulting integral value is outside the range of the destination type, an <xref:System.OverflowException> is thrown.</span></span>  
  
-   <span data-ttu-id="7eac7-136">`double` 또는 `float` 값을 정수 형식으로 변환할 경우 결과 값이 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="7eac7-136">When you convert from a `double` or `float` value to an integral type, the value is truncated.</span></span> <span data-ttu-id="7eac7-137">결과 정수 값이 대상 형식 범위에서 벗어났을 경우 결과 값은 오버플로 검사 컨텍스트에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7eac7-137">If the resulting integral value is outside the range of the destination value, the result depends on the overflow checking context.</span></span> <span data-ttu-id="7eac7-138">Checked 컨텍스트에서는 `OverflowException`이 throw됩니다. 반면 Unchecked 컨텍스트에서 결과는 지정되지 않은 대상 형식 값이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7eac7-138">In a checked context, an `OverflowException` is thrown, while in an unchecked context, the result is an unspecified value of the destination type.</span></span>  
  
-   <span data-ttu-id="7eac7-139">`double`을 `float`로 변환할 경우 `double` 값을 가장 가까운 `float` 값으로 반올림합니다.</span><span class="sxs-lookup"><span data-stu-id="7eac7-139">When you convert `double` to `float`, the `double` value is rounded to the nearest `float` value.</span></span> <span data-ttu-id="7eac7-140">`double` 값이 너무 크거나 작아서 대상 형식에 맞출 수 없을 경우 결과 값은 0 또는 무한대가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7eac7-140">If the `double` value is too small or too large to fit into the destination type, the result will be zero or infinity.</span></span>  
  
-   <span data-ttu-id="7eac7-141">`float` 또는 `double`을 `decimal`로 변환할 경우 소스 값을 `decimal` 표현으로 변환한 다음 필요한 경우 가장 가까운 소수점 이하 28번째 자리로 반올림합니다.</span><span class="sxs-lookup"><span data-stu-id="7eac7-141">When you convert `float` or `double` to `decimal`, the source value is converted to `decimal` representation and rounded to the nearest number after the 28th decimal place if required.</span></span> <span data-ttu-id="7eac7-142">소스 값에 따라 다음 결과 중 하나가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7eac7-142">Depending on the value of the source value, one of the following results may occur:</span></span>  
  
    -   <span data-ttu-id="7eac7-143">소스 값이 너무 작아서 `decimal`로 나타낼 수 없을 경우 결과 값은 0이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7eac7-143">If the source value is too small to be represented as a `decimal`, the result becomes zero.</span></span>  
  
    -   <span data-ttu-id="7eac7-144">소스 값이 NaN(숫자가 아님), 무한대 또는 너무 커서 `decimal`로 나타낼 수 없을 경우 `OverflowException`을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="7eac7-144">If the source value is NaN (not a number), infinity, or too large to be represented as a `decimal`, an `OverflowException` is thrown.</span></span>  
  
-   <span data-ttu-id="7eac7-145">`decimal`을 `float` 또는 `double`로 변환할 경우 `decimal` 값을 가장 가까운 `double` 또는 `float` 값으로 반올림합니다.</span><span class="sxs-lookup"><span data-stu-id="7eac7-145">When you convert `decimal` to `float` or `double`, the `decimal` value is rounded to the nearest `double` or `float` value.</span></span>  
  
 <span data-ttu-id="7eac7-146">명시적 변환에 대한 자세한 내용은 C# 언어 사양의 Explicit(명시적)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7eac7-146">For more information on explicit conversion, see Explicit in the C# Language Specification.</span></span> <span data-ttu-id="7eac7-147">사양에 액세스하는 방법에 대한 자세한 내용은 [C# 언어 사양](../../../csharp/language-reference/language-specification/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7eac7-147">For more information on how to access the spec, see [C# Language Specification](../../../csharp/language-reference/language-specification/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eac7-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7eac7-148">See Also</span></span>  
 <span data-ttu-id="7eac7-149">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="7eac7-149">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="7eac7-150">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="7eac7-150">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="7eac7-151">[캐스팅 및 형식 변환](../../../csharp/programming-guide/types/casting-and-type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="7eac7-151">[Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md) </span></span>  
 <span data-ttu-id="7eac7-152">[() 연산자](../../../csharp/language-reference/operators/invocation-operator.md) </span><span class="sxs-lookup"><span data-stu-id="7eac7-152">[() Operator](../../../csharp/language-reference/operators/invocation-operator.md) </span></span>  
 <span data-ttu-id="7eac7-153">[정수 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="7eac7-153">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="7eac7-154">[기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="7eac7-154">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 [<span data-ttu-id="7eac7-155">암시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="7eac7-155">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)

