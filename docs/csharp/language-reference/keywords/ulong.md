---
title: "ulong(C# 참조)"
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ulong_CSharpKeyword
- ulong
dev_langs:
- CSharp
helpviewer_keywords:
- ulong keyword [C#]
ms.assetid: f2ece624-837a-40cf-92c5-343e7f33397c
caps.latest.revision: 16
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
ms.openlocfilehash: c2da253e4da7a5d6cfa71116e4fcba7816441e92
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="ulong-c-reference"></a><span data-ttu-id="a1d9b-102">ulong(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="a1d9b-102">ulong (C# Reference)</span></span>

<span data-ttu-id="a1d9b-103">`ulong` 키워드는 다음 표에 나와 있는 크기와 범위에 따라 값을 저장하는 정수 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-103">The `ulong` keyword denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="a1d9b-104">형식</span><span class="sxs-lookup"><span data-stu-id="a1d9b-104">Type</span></span>|<span data-ttu-id="a1d9b-105">범위</span><span class="sxs-lookup"><span data-stu-id="a1d9b-105">Range</span></span>|<span data-ttu-id="a1d9b-106">크기</span><span class="sxs-lookup"><span data-stu-id="a1d9b-106">Size</span></span>|<span data-ttu-id="a1d9b-107">.NET Framework 형식</span><span class="sxs-lookup"><span data-stu-id="a1d9b-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`ulong`|<span data-ttu-id="a1d9b-108">0 ~ 18,446,744,073,709,551,615</span><span class="sxs-lookup"><span data-stu-id="a1d9b-108">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="a1d9b-109">부호 없는 64비트 정수</span><span class="sxs-lookup"><span data-stu-id="a1d9b-109">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="a1d9b-110">리터럴</span><span class="sxs-lookup"><span data-stu-id="a1d9b-110">Literals</span></span>  

<span data-ttu-id="a1d9b-111">10진수 리터럴, 16진수 리터럴 또는 (C# 7부터) 이진 리터럴을 할당하여 `ulong` 변수를 선언하고 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-111">You can declare and initialize a `ulong` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span>  <span data-ttu-id="a1d9b-112">정수 리터럴이 `ulong` 범위를 벗어나는 경우(즉 <xref:System.UInt64.MinValue?displayProperty=fullName>보다 작거나 <xref:System.UInt64.MaxValue?displayProperty=fullName>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-112">If the integer literal is outside the range of `ulong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=fullName> or greater than <xref:System.UInt64.MaxValue?displayProperty=fullName>), a compilation error occurs.</span></span> 

<span data-ttu-id="a1d9b-113">다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 7,934,076,125와 같은 정수가 `ulong` 값에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-113">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ulong` values.</span></span>  
  
<span data-ttu-id="a1d9b-114">[!code-cs[ulong](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ULong)]</span><span class="sxs-lookup"><span data-stu-id="a1d9b-114">[!code-cs[ulong](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ULong)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="a1d9b-115">`0x` 또는 `0X` 접두사를 사용하여 16진수 리터럴을 나타내고, `0b` 또는 `0B` 접두사를 사용하여 이진 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-115">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="a1d9b-116">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-116">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="a1d9b-117">C# 7부터는 다음 예제와 같이 밑줄 문자 `_`를 자릿수 구분 기호로 사용하여 가독성을 향상할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-117">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="a1d9b-118">[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]</span><span class="sxs-lookup"><span data-stu-id="a1d9b-118">[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]</span></span>  
 
 <span data-ttu-id="a1d9b-119">형식을 나타내는 접미사가 정수 리터럴에 포함되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-119">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="a1d9b-120">`UL` 또는 `ul` 접미사는 숫자 리터럴을 `ulong` 값으로 명확하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-120">The suffix `UL` or `ul` unambiguously identifies a numeric literal as a `ulong` value.</span></span> <span data-ttu-id="a1d9b-121">리터럴 값이 <xref:System.Int64.MaxValue?displayProperty=fullName>를 초과할 경우 `L` 접미사는 `ulong`을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-121">The `L` suffix denotes a `ulong` if the literal value exceeds <xref:System.Int64.MaxValue?displayProperty=fullName>.</span></span> <span data-ttu-id="a1d9b-122">또한 리터럴 값이 <xref:System.UInt32.MaxValue?displayProperty=fullName>를 초과할 경우 `U` 또는 `ulong` 접미사는 `u`을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-122">And the `U` or `u` suffix denotes a `ulong` if the literal value exceeds <xref:System.UInt32.MaxValue?displayProperty=fullName>.</span></span> <span data-ttu-id="a1d9b-123">다음 예제에서는 `ul` 접미사를 사용하여 정수(long)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-123">The following example uses the `ul` suffix to denote a long integer:</span></span>
 
<span data-ttu-id="a1d9b-124">[!code-cs[ulsuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="a1d9b-124">[!code-cs[ulsuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#2)]</span></span>

<span data-ttu-id="a1d9b-125">정수 리터럴에 접미사가 없는 경우 해당 형식은 값이 표현될 수 있는 다음 형식 중 첫 번째 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-125">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. [<span data-ttu-id="a1d9b-126">int</span><span class="sxs-lookup"><span data-stu-id="a1d9b-126">int</span></span>](int.md)
2. [<span data-ttu-id="a1d9b-127">uint</span><span class="sxs-lookup"><span data-stu-id="a1d9b-127">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. [<span data-ttu-id="a1d9b-128">long</span><span class="sxs-lookup"><span data-stu-id="a1d9b-128">long</span></span>](long.md)
4. `ulong`

## <a name="compiler-overload-resolution"></a><span data-ttu-id="a1d9b-129">컴파일러 오버로드 확인</span><span class="sxs-lookup"><span data-stu-id="a1d9b-129">Compiler overload resolution</span></span>
  
 <span data-ttu-id="a1d9b-130">접미사는 일반적으로 오버로드된 메서드를 호출할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-130">A common use of the suffix is with calling overloaded methods.</span></span> <span data-ttu-id="a1d9b-131">예를 들어 `ulong` 및 [int](../../../csharp/language-reference/keywords/int.md) 매개 변수를 사용하는 다음의 오버로드된 메서드를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-131">Consider, for example, the following overloaded methods that use `ulong` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ulong l) {}  
```  
  
 <span data-ttu-id="a1d9b-132">`ulong` 매개 변수와 함께 접미사를 사용하면 올바른 형식이 호출됩니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-132">Using a suffix with the `ulong` parameter guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
SampleMethod(5);    // Calling the method with the int parameter  
SampleMethod(5UL);  // Calling the method with the ulong parameter  
```  
  
## <a name="conversions"></a><span data-ttu-id="a1d9b-133">변환</span><span class="sxs-lookup"><span data-stu-id="a1d9b-133">Conversions</span></span>  
 <span data-ttu-id="a1d9b-134">`ulong`에서 [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) 또는 [decimal](../../../csharp/language-reference/keywords/decimal.md)로 미리 정의된 암시적 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-134">There is a predefined implicit conversion from `ulong` to [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="a1d9b-135">`ulong`에서 정수 형식으로의 암시적 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-135">There is no implicit conversion from `ulong` to any integral type.</span></span> <span data-ttu-id="a1d9b-136">예를 들어 다음 문은 명시적 캐스트 없이 컴파일 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-136">For example, the following statement will produce a compilation error without an explicit cast:</span></span>  
  
```csharp  
long long1 = 8UL;   // Error: no implicit conversion from ulong  
```  
  
 <span data-ttu-id="a1d9b-137">[byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [uint](../../../csharp/language-reference/keywords/uint.md) 또는 [char](../../../csharp/language-reference/keywords/char.md)에서 `ulong`으로 미리 정의된 암시적 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-137">There is a predefined implicit conversion from [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [uint](../../../csharp/language-reference/keywords/uint.md), or [char](../../../csharp/language-reference/keywords/char.md) to `ulong`.</span></span>  
  
 <span data-ttu-id="a1d9b-138">또한 부동 소수점 형식에서 `ulong`로의 암시적 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-138">Also, there is no implicit conversion from floating-point types to `ulong`.</span></span> <span data-ttu-id="a1d9b-139">예를 들어 명시적 캐스트를 사용하지 않는 경우 다음 문은 컴파일러 오류를 일으킵니다.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-139">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error -- no implicit conversion from double:  
ulong x = 3.0;  
// OK -- explicit conversion:  
ulong y = (ulong)3.0;    
```  
  
 <span data-ttu-id="a1d9b-140">부동 소수점 형식 및 정수 형식이 혼합된 산술 식에 대한 자세한 내용은 [float](../../../csharp/language-reference/keywords/float.md) 및 [double](../../../csharp/language-reference/keywords/double.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-140">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="a1d9b-141">암시적 숫자 변환 규칙에 대한 자세한 내용은 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-141">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="a1d9b-142">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="a1d9b-142">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a1d9b-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a1d9b-143">See Also</span></span>  
 <span data-ttu-id="a1d9b-144"><xref:System.UInt64></span><span class="sxs-lookup"><span data-stu-id="a1d9b-144"><xref:System.UInt64></span></span>   
 <span data-ttu-id="a1d9b-145">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="a1d9b-145">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="a1d9b-146">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a1d9b-146">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a1d9b-147">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="a1d9b-147">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="a1d9b-148">[정수 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="a1d9b-148">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="a1d9b-149">[기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="a1d9b-149">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="a1d9b-150">[암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="a1d9b-150">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="a1d9b-151">명시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="a1d9b-151">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

