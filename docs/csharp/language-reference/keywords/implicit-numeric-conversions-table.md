---
title: 암시적 숫자 변환 표(C# 참조)
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#], implicit numeric
- implicit numeric conversions [C#]
- numeric conversions [C#], implicit
- types [C#], implicit numeric conversions
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
ms.openlocfilehash: 2d417a2020656f300de0517526742679388f262e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="implicit-numeric-conversions-table-c-reference"></a><span data-ttu-id="e3528-102">암시적 숫자 변환 표(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="e3528-102">Implicit Numeric Conversions Table (C# Reference)</span></span>
<span data-ttu-id="e3528-103">다음 표에서는 미리 정의된 암시적 숫자 변환을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e3528-103">The following table shows the predefined implicit numeric conversions.</span></span> <span data-ttu-id="e3528-104">암시적 변환은 메서드 호출, 할당 문을 비롯한 대부분의 경우에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3528-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
|<span data-ttu-id="e3528-105">시작</span><span class="sxs-lookup"><span data-stu-id="e3528-105">From</span></span>|<span data-ttu-id="e3528-106">대상</span><span class="sxs-lookup"><span data-stu-id="e3528-106">To</span></span>|  
|----------|--------|  
|[<span data-ttu-id="e3528-107">sbyte</span><span class="sxs-lookup"><span data-stu-id="e3528-107">sbyte</span></span>](../../../csharp/language-reference/keywords/sbyte.md)|<span data-ttu-id="e3528-108">`short`, `int`, `long`, `float`, `double` 또는 `decimal`</span><span class="sxs-lookup"><span data-stu-id="e3528-108">`short`, `int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="e3528-109">byte</span><span class="sxs-lookup"><span data-stu-id="e3528-109">byte</span></span>](../../../csharp/language-reference/keywords/byte.md)|<span data-ttu-id="e3528-110">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` 또는 `decimal`</span><span class="sxs-lookup"><span data-stu-id="e3528-110">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="e3528-111">short</span><span class="sxs-lookup"><span data-stu-id="e3528-111">short</span></span>](../../../csharp/language-reference/keywords/short.md)|<span data-ttu-id="e3528-112">`int`, `long`, `float`, `double` 또는 `decimal`</span><span class="sxs-lookup"><span data-stu-id="e3528-112">`int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="e3528-113">ushort</span><span class="sxs-lookup"><span data-stu-id="e3528-113">ushort</span></span>](../../../csharp/language-reference/keywords/ushort.md)|<span data-ttu-id="e3528-114">`int`, `uint`, `long`, `ulong`, `float`, `double` 또는 `decimal`</span><span class="sxs-lookup"><span data-stu-id="e3528-114">`int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="e3528-115">int</span><span class="sxs-lookup"><span data-stu-id="e3528-115">int</span></span>](../../../csharp/language-reference/keywords/int.md)|<span data-ttu-id="e3528-116">`long`, `float`, `double` 또는 `decimal`</span><span class="sxs-lookup"><span data-stu-id="e3528-116">`long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="e3528-117">uint</span><span class="sxs-lookup"><span data-stu-id="e3528-117">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)|<span data-ttu-id="e3528-118">`long`, `ulong`, `float`, `double` 또는 `decimal`</span><span class="sxs-lookup"><span data-stu-id="e3528-118">`long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="e3528-119">long</span><span class="sxs-lookup"><span data-stu-id="e3528-119">long</span></span>](../../../csharp/language-reference/keywords/long.md)|<span data-ttu-id="e3528-120">`float`, `double`또는 `decimal`</span><span class="sxs-lookup"><span data-stu-id="e3528-120">`float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="e3528-121">char</span><span class="sxs-lookup"><span data-stu-id="e3528-121">char</span></span>](../../../csharp/language-reference/keywords/char.md)|<span data-ttu-id="e3528-122">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` 또는 `decimal`</span><span class="sxs-lookup"><span data-stu-id="e3528-122">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="e3528-123">float</span><span class="sxs-lookup"><span data-stu-id="e3528-123">float</span></span>](../../../csharp/language-reference/keywords/float.md)|`double`|  
|[<span data-ttu-id="e3528-124">ulong</span><span class="sxs-lookup"><span data-stu-id="e3528-124">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)|<span data-ttu-id="e3528-125">`float`, `double`또는 `decimal`</span><span class="sxs-lookup"><span data-stu-id="e3528-125">`float`, `double`, or `decimal`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3528-126">설명</span><span class="sxs-lookup"><span data-stu-id="e3528-126">Remarks</span></span>  
  
-   <span data-ttu-id="e3528-127">`int`, `uint`, `long` 또는 `ulong`에서 `float`로 변환하고 `long` 또는 `ulong`에서 `double`로 변환하는 동안 전체 자릿수가 손실될 수도 있지만 크기는 손실되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3528-127">Precision but not magnitude might be lost in the conversions from `int`, `uint`,  `long`, or `ulong` to `float` and from `long` or `ulong` to `double`.</span></span>  
  
-   <span data-ttu-id="e3528-128">`char` 형식으로의 암시적 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3528-128">There are no implicit conversions to the `char` type.</span></span>  
  
-   <span data-ttu-id="e3528-129">부동 소수점 형식과 `decimal` 형식 간의 암시적 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3528-129">There are no implicit conversions between floating-point types and the `decimal` type.</span></span>  
  
-   <span data-ttu-id="e3528-130">상수 식의 값이 대상 형식의 범위 내에 있는 경우 `int` 형식의 상수 식을 `sbyte`, `byte`, `short`, `ushort`, `uint` 또는 `ulong`으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3528-130">A constant expression of type `int` can be converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`, provided the value of the constant expression is within the range of the destination type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="e3528-131">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="e3528-131">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e3528-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e3528-132">See Also</span></span>  
 [<span data-ttu-id="e3528-133">C# 참조</span><span class="sxs-lookup"><span data-stu-id="e3528-133">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e3528-134">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="e3528-134">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e3528-135">정수 계열 형식 표</span><span class="sxs-lookup"><span data-stu-id="e3528-135">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="e3528-136">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="e3528-136">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="e3528-137">명시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="e3528-137">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
 [<span data-ttu-id="e3528-138">캐스팅 및 형식 변환</span><span class="sxs-lookup"><span data-stu-id="e3528-138">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)
