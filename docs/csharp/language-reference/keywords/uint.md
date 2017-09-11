---
title: "uint(C# 참조)"
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- uint
- uint_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- uint keyword [C#]
ms.assetid: e93e42c6-ec72-4b0b-89df-2fd8d36f7a7b
caps.latest.revision: 18
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
ms.openlocfilehash: 4342c08ab536f45a2e3b5fa6fe94839436600a4a
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="uint-c-reference"></a><span data-ttu-id="26764-102">uint(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="26764-102">uint (C# Reference)</span></span>

<span data-ttu-id="26764-103">`uint` 키워드는 다음 표에 나와 있는 크기와 범위에 따라 값을 저장하는 정수 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="26764-103">The `uint` keyword signifies an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="26764-104">형식</span><span class="sxs-lookup"><span data-stu-id="26764-104">Type</span></span>|<span data-ttu-id="26764-105">범위</span><span class="sxs-lookup"><span data-stu-id="26764-105">Range</span></span>|<span data-ttu-id="26764-106">크기</span><span class="sxs-lookup"><span data-stu-id="26764-106">Size</span></span>|<span data-ttu-id="26764-107">.NET Framework 형식</span><span class="sxs-lookup"><span data-stu-id="26764-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`uint`|<span data-ttu-id="26764-108">0 ~ 4,294,967,295</span><span class="sxs-lookup"><span data-stu-id="26764-108">0 to 4,294,967,295</span></span>|<span data-ttu-id="26764-109">부호 없는 32비트 정수</span><span class="sxs-lookup"><span data-stu-id="26764-109">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=fullName>|  
  
 <span data-ttu-id="26764-110">**참고** `uint` 형식은 CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="26764-110">**Note** The `uint` type is not CLS-compliant.</span></span> <span data-ttu-id="26764-111">가능한 경우 항상 `int`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="26764-111">Use `int` whenever possible.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="26764-112">리터럴</span><span class="sxs-lookup"><span data-stu-id="26764-112">Literals</span></span>  

<span data-ttu-id="26764-113">10진수 리터럴, 16진수 리터럴 또는 (C# 7부터) 이진 리터럴을 할당하여 `uint` 변수를 선언하고 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26764-113">You can declare and initialize a `uint` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span> <span data-ttu-id="26764-114">정수 리터럴이 `uint` 범위를 벗어나는 경우(즉 <xref:System.UInt32.MinValue?displayProperty=fullName>보다 작거나 <xref:System.UInt32.MaxValue?displayProperty=fullName>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="26764-114">If the integer literal is outside the range of `uint` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=fullName> or greater than <xref:System.UInt32.MaxValue?displayProperty=fullName>), a compilation error occurs.</span></span>

<span data-ttu-id="26764-115">다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 3,000,000,000과 같은 정수가 `uint` 값에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="26764-115">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `uint` values.</span></span>  
  
<span data-ttu-id="26764-116">[!code-cs[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UInt)]</span><span class="sxs-lookup"><span data-stu-id="26764-116">[!code-cs[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UInt)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="26764-117">`0x` 또는 `0X` 접두사를 사용하여 16진수 리터럴을 나타내고, `0b` 또는 `0B` 접두사를 사용하여 이진 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="26764-117">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="26764-118">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="26764-118">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="26764-119">C# 7부터는 다음 예제와 같이 밑줄 문자 `_`를 자릿수 구분 기호로 사용하여 가독성을 향상할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26764-119">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="26764-120">[!code-cs[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UIntS)]</span><span class="sxs-lookup"><span data-stu-id="26764-120">[!code-cs[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UIntS)]</span></span>  
 
 <span data-ttu-id="26764-121">형식을 나타내는 접미사가 정수 리터럴에 포함되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26764-121">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="26764-122">`U` 또는 'u' 접미사는 리터럴의 숫자 값에 따라 `uint` 또는 `ulong`을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="26764-122">The suffix `U` or 'u' denotes either a `uint` or a `ulong`, depending on the numeric value of the literal.</span></span> <span data-ttu-id="26764-123">다음 예제에서는 `u` 접미사를 사용하여 두 형식의 부호 없는 정수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="26764-123">The following example uses the `u` suffix to denote an unsigned integer of both types.</span></span> <span data-ttu-id="26764-124">첫 번째 리터럴은 해당 값이 <xref:System.UInt32.MaxValue?displayProperty=fullName>보다 작기 때문에 `uint`인 반면, 두 번째 리터럴은 해당 값이 <xref:System.UInt32.MaxValue?displayProperty=fullName>보다 크기 때문에 `ulong`입니다.</span><span class="sxs-lookup"><span data-stu-id="26764-124">Note that the first literal is a `uint` because its value is less than <xref:System.UInt32.MaxValue?displayProperty=fullName>, while the second is a `ulong` because its value is greater than <xref:System.UInt32.MaxValue?displayProperty=fullName>.</span></span>

<span data-ttu-id="26764-125">[!code-cs[usuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="26764-125">[!code-cs[usuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#1)]</span></span>  
 
<span data-ttu-id="26764-126">정수 리터럴에 접미사가 없는 경우 해당 형식은 값이 표현될 수 있는 다음 형식 중 첫 번째 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="26764-126">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. [<span data-ttu-id="26764-127">int</span><span class="sxs-lookup"><span data-stu-id="26764-127">int</span></span>](int.md)
2. `uint`
3. [<span data-ttu-id="26764-128">long</span><span class="sxs-lookup"><span data-stu-id="26764-128">long</span></span>](../../../csharp/language-reference/keywords/long.md)
4. [<span data-ttu-id="26764-129">ulong</span><span class="sxs-lookup"><span data-stu-id="26764-129">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 
  
## <a name="conversions"></a><span data-ttu-id="26764-130">변환</span><span class="sxs-lookup"><span data-stu-id="26764-130">Conversions</span></span>  
 <span data-ttu-id="26764-131">`uint`에서 [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) 또는 [decimal](../../../csharp/language-reference/keywords/decimal.md)로 미리 정의된 암시적 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26764-131">There is a predefined implicit conversion from `uint` to [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="26764-132">예:</span><span class="sxs-lookup"><span data-stu-id="26764-132">For example:</span></span>  
  
```csharp  
float myFloat = 4294967290;   // OK: implicit conversion to float  
```  
  
 <span data-ttu-id="26764-133">[byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) 또는 [char](../../../csharp/language-reference/keywords/char.md)에서 `uint`로 미리 정의된 암시적 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26764-133">There is a predefined implicit conversion from [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), or [char](../../../csharp/language-reference/keywords/char.md) to `uint`.</span></span> <span data-ttu-id="26764-134">그렇지 않으면 캐스트를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26764-134">Otherwise you must use a cast.</span></span> <span data-ttu-id="26764-135">예를 들어 다음 대입문은 캐스트 없이 컴파일 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="26764-135">For example, the following assignment statement will produce a compilation error without a cast:</span></span>  
  
```csharp  
long aLong = 22;  
// Error -- no implicit conversion from long:  
uint uInt1 = aLong;   
// OK -- explicit conversion:  
uint uInt2 = (uint)aLong;  
```  
  
 <span data-ttu-id="26764-136">부동 소수점 형식에서 `uint`로의 암시적 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="26764-136">Notice also that there is no implicit conversion from floating-point types to `uint`.</span></span> <span data-ttu-id="26764-137">예를 들어 명시적 캐스트를 사용하지 않는 경우 다음 문은 컴파일러 오류를 일으킵니다.</span><span class="sxs-lookup"><span data-stu-id="26764-137">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error -- no implicit conversion from double:  
uint x = 3.0;  
// OK -- explicit conversion:  
uint y = (uint)3.0;   
```  
  
 <span data-ttu-id="26764-138">부동 소수점 형식 및 정수 형식이 혼합된 산술 식에 대한 자세한 내용은 [float](../../../csharp/language-reference/keywords/float.md) 및 [double](../../../csharp/language-reference/keywords/double.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="26764-138">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="26764-139">암시적 숫자 변환 규칙에 대한 자세한 내용은 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="26764-139">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="26764-140">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="26764-140">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="26764-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="26764-141">See Also</span></span>  
 <span data-ttu-id="26764-142"><xref:System.UInt32></span><span class="sxs-lookup"><span data-stu-id="26764-142"><xref:System.UInt32></span></span>   
 <span data-ttu-id="26764-143">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="26764-143">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="26764-144">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="26764-144">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="26764-145">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="26764-145">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="26764-146">[정수 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="26764-146">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="26764-147">[기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="26764-147">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="26764-148">[암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="26764-148">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="26764-149">명시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="26764-149">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

