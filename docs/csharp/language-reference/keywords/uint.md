---
title: uint(C# 참조)
ms.date: 03/14/2017
f1_keywords:
- uint
- uint_CSharpKeyword
helpviewer_keywords:
- uint keyword [C#]
ms.assetid: e93e42c6-ec72-4b0b-89df-2fd8d36f7a7b
ms.openlocfilehash: fa0169ad92819cee36832d6c928202eb0dd6733e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="uint-c-reference"></a><span data-ttu-id="05c65-102">uint(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="05c65-102">uint (C# Reference)</span></span>

<span data-ttu-id="05c65-103">`uint` 키워드는 다음 표에 나와 있는 크기와 범위에 따라 값을 저장하는 정수 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="05c65-103">The `uint` keyword signifies an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="05c65-104">형식</span><span class="sxs-lookup"><span data-stu-id="05c65-104">Type</span></span>|<span data-ttu-id="05c65-105">범위</span><span class="sxs-lookup"><span data-stu-id="05c65-105">Range</span></span>|<span data-ttu-id="05c65-106">크기</span><span class="sxs-lookup"><span data-stu-id="05c65-106">Size</span></span>|<span data-ttu-id="05c65-107">.NET Framework 형식</span><span class="sxs-lookup"><span data-stu-id="05c65-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`uint`|<span data-ttu-id="05c65-108">0 ~ 4,294,967,295</span><span class="sxs-lookup"><span data-stu-id="05c65-108">0 to 4,294,967,295</span></span>|<span data-ttu-id="05c65-109">부호 없는 32비트 정수</span><span class="sxs-lookup"><span data-stu-id="05c65-109">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|  
  
 <span data-ttu-id="05c65-110">**참고** `uint` 형식은 CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="05c65-110">**Note** The `uint` type is not CLS-compliant.</span></span> <span data-ttu-id="05c65-111">가능한 경우 항상 `int`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="05c65-111">Use `int` whenever possible.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="05c65-112">리터럴</span><span class="sxs-lookup"><span data-stu-id="05c65-112">Literals</span></span>  

<span data-ttu-id="05c65-113">10진수 리터럴, 16진수 리터럴 또는 (C# 7.0부터) 이진 리터럴을 할당하여 `uint` 변수를 선언하고 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05c65-113">You can declare and initialize a `uint` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span> <span data-ttu-id="05c65-114">정수 리터럴이 `uint` 범위를 벗어나는 경우(즉 <xref:System.UInt32.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="05c65-114">If the integer literal is outside the range of `uint` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="05c65-115">다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 3,000,000,000과 같은 정수가 `uint` 값에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="05c65-115">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `uint` values.</span></span>  
  
[!code-csharp[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UInt)]  

> [!NOTE] 
> <span data-ttu-id="05c65-116">`0x` 또는 `0X` 접두사를 사용하여 16진수 리터럴을 나타내고, `0b` 또는 `0B` 접두사를 사용하여 이진 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="05c65-116">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="05c65-117">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05c65-117">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="05c65-118">C# 7.0부터 가독성 향상을 위해 몇 가지 기능이 추가됐습니다.</span><span class="sxs-lookup"><span data-stu-id="05c65-118">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="05c65-119">C# 7.0은 숫자 구분 기호로 밑줄 문자 `_`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05c65-119">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="05c65-120">C# 7.2는 접두사 뒤에 이진 또는 16진수 리터럴에 대한 자리 구분 기호로 `_`을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05c65-120">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="05c65-121">10진수 리터럴에 선행 밑줄이 있는 것이 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05c65-121">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="05c65-122">일부 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="05c65-122">Some examples are shown below.</span></span>

[!code-csharp[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UIntS)]  
 
 <span data-ttu-id="05c65-123">형식을 나타내는 접미사가 정수 리터럴에 포함되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05c65-123">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="05c65-124">`U` 또는 'u' 접미사는 리터럴의 숫자 값에 따라 `uint` 또는 `ulong`을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="05c65-124">The suffix `U` or 'u' denotes either a `uint` or a `ulong`, depending on the numeric value of the literal.</span></span> <span data-ttu-id="05c65-125">다음 예제에서는 `u` 접미사를 사용하여 두 형식의 부호 없는 정수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="05c65-125">The following example uses the `u` suffix to denote an unsigned integer of both types.</span></span> <span data-ttu-id="05c65-126">첫 번째 리터럴은 해당 값이 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>보다 작기 때문에 `uint`인 반면, 두 번째 리터럴은 해당 값이 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>보다 크기 때문에 `ulong`입니다.</span><span class="sxs-lookup"><span data-stu-id="05c65-126">Note that the first literal is a `uint` because its value is less than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, while the second is a `ulong` because its value is greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>

[!code-csharp[usuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#1)]  
 
<span data-ttu-id="05c65-127">정수 리터럴에 접미사가 없는 경우 해당 형식은 값이 표현될 수 있는 다음 형식 중 첫 번째 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="05c65-127">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. [<span data-ttu-id="05c65-128">int</span><span class="sxs-lookup"><span data-stu-id="05c65-128">int</span></span>](int.md)
2. `uint`
3. [<span data-ttu-id="05c65-129">long</span><span class="sxs-lookup"><span data-stu-id="05c65-129">long</span></span>](../../../csharp/language-reference/keywords/long.md)
4. [<span data-ttu-id="05c65-130">ulong</span><span class="sxs-lookup"><span data-stu-id="05c65-130">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 
  
## <a name="conversions"></a><span data-ttu-id="05c65-131">변환</span><span class="sxs-lookup"><span data-stu-id="05c65-131">Conversions</span></span>  
 <span data-ttu-id="05c65-132">`uint`에서 [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) 또는 [decimal](../../../csharp/language-reference/keywords/decimal.md)로 미리 정의된 암시적 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05c65-132">There is a predefined implicit conversion from `uint` to [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="05c65-133">예:</span><span class="sxs-lookup"><span data-stu-id="05c65-133">For example:</span></span>  
  
```csharp  
float myFloat = 4294967290;   // OK: implicit conversion to float  
```  
  
 <span data-ttu-id="05c65-134">[byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) 또는 [char](../../../csharp/language-reference/keywords/char.md)에서 `uint`로 미리 정의된 암시적 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05c65-134">There is a predefined implicit conversion from [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), or [char](../../../csharp/language-reference/keywords/char.md) to `uint`.</span></span> <span data-ttu-id="05c65-135">그렇지 않으면 캐스트를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05c65-135">Otherwise you must use a cast.</span></span> <span data-ttu-id="05c65-136">예를 들어 다음 대입문은 캐스트 없이 컴파일 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="05c65-136">For example, the following assignment statement will produce a compilation error without a cast:</span></span>  
  
```csharp  
long aLong = 22;  
// Error -- no implicit conversion from long:  
uint uInt1 = aLong;   
// OK -- explicit conversion:  
uint uInt2 = (uint)aLong;  
```  
  
 <span data-ttu-id="05c65-137">부동 소수점 형식에서 `uint`로의 암시적 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05c65-137">Notice also that there is no implicit conversion from floating-point types to `uint`.</span></span> <span data-ttu-id="05c65-138">예를 들어 명시적 캐스트를 사용하지 않는 경우 다음 문은 컴파일러 오류를 일으킵니다.</span><span class="sxs-lookup"><span data-stu-id="05c65-138">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error -- no implicit conversion from double:  
uint x = 3.0;  
// OK -- explicit conversion:  
uint y = (uint)3.0;   
```  
  
 <span data-ttu-id="05c65-139">부동 소수점 형식 및 정수 형식이 혼합된 산술 식에 대한 자세한 내용은 [float](../../../csharp/language-reference/keywords/float.md) 및 [double](../../../csharp/language-reference/keywords/double.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05c65-139">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="05c65-140">암시적 숫자 변환 규칙에 대한 자세한 내용은 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05c65-140">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="05c65-141">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="05c65-141">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="05c65-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05c65-142">See Also</span></span>  
 <xref:System.UInt32>  
 [<span data-ttu-id="05c65-143">C# 참조</span><span class="sxs-lookup"><span data-stu-id="05c65-143">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="05c65-144">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="05c65-144">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="05c65-145">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="05c65-145">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="05c65-146">정수 계열 형식 표</span><span class="sxs-lookup"><span data-stu-id="05c65-146">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="05c65-147">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="05c65-147">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="05c65-148">암시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="05c65-148">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="05c65-149">명시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="05c65-149">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
