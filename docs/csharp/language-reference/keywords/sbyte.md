---
title: "sbyte(C# 참조)"
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- sbyte_CSharpKeyword
- sbyte
dev_langs:
- CSharp
helpviewer_keywords:
- sbyte keyword [C#]
ms.assetid: 1a9c7b48-73d1-4d33-b485-c4faf0a816bc
caps.latest.revision: 17
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
ms.openlocfilehash: 69741a5b9556c769156687584041667312550c17
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="sbyte-c-reference"></a><span data-ttu-id="fef73-102">sbyte(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="fef73-102">sbyte (C# Reference)</span></span>

<span data-ttu-id="fef73-103">`sbyte`는 다음 표에 나와 있는 크기와 범위에 따라 값을 저장하는 정수 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fef73-103">`sbyte` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="fef73-104">형식</span><span class="sxs-lookup"><span data-stu-id="fef73-104">Type</span></span>|<span data-ttu-id="fef73-105">범위</span><span class="sxs-lookup"><span data-stu-id="fef73-105">Range</span></span>|<span data-ttu-id="fef73-106">크기</span><span class="sxs-lookup"><span data-stu-id="fef73-106">Size</span></span>|<span data-ttu-id="fef73-107">.NET Framework 형식</span><span class="sxs-lookup"><span data-stu-id="fef73-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`sbyte`|<span data-ttu-id="fef73-108">-128 ~ 127</span><span class="sxs-lookup"><span data-stu-id="fef73-108">-128 to 127</span></span>|<span data-ttu-id="fef73-109">부호 있는 8비트 정수</span><span class="sxs-lookup"><span data-stu-id="fef73-109">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="fef73-110">리터럴</span><span class="sxs-lookup"><span data-stu-id="fef73-110">Literals</span></span>  

<span data-ttu-id="fef73-111">10진수 리터럴, 16진수 리터럴 또는 (C# 7부터) 이진 리터럴을 할당하여 `sbyte` 변수를 선언하고 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef73-111">You can declare and initialize an `sbyte` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span> 

<span data-ttu-id="fef73-112">다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 -102와 같은 정수가 [int](../../../csharp/language-reference/keywords/int.md)에서 `sbyte` 값으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="fef73-112">In the following example, integers equal to -102 that are represented as decimal, hexadecimal, and binary literals are converted from [int](../../../csharp/language-reference/keywords/int.md) to `sbyte` values.</span></span>    
  
<span data-ttu-id="fef73-113">[!code-cs[SByte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#SByte)]</span><span class="sxs-lookup"><span data-stu-id="fef73-113">[!code-cs[SByte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#SByte)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="fef73-114">`0x` 또는 `0X` 접두사를 사용하여 16진수 리터럴을 나타내고, `0b` 또는 `0B` 접두사를 사용하여 이진 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fef73-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="fef73-115">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fef73-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="fef73-116">C# 7부터는 다음 예제와 같이 밑줄 문자 `_`를 자릿수 구분 기호로 사용하여 가독성을 향상할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef73-116">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="fef73-117">[!code-cs[SByteSeparator](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#SByteS)]</span><span class="sxs-lookup"><span data-stu-id="fef73-117">[!code-cs[SByteSeparator](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#SByteS)]</span></span>  

<span data-ttu-id="fef73-118">정수 리터럴이 `sbyte` 범위를 벗어나는 경우(즉 <xref:System.SByte.MinValue?displayProperty=fullName>보다 작거나 <xref:System.SByte.MaxValue?displayProperty=fullName>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="fef73-118">If the integer literal is outside the range of `sbyte` (that is, if it is less than <xref:System.SByte.MinValue?displayProperty=fullName> or greater than <xref:System.SByte.MaxValue?displayProperty=fullName>, a compilation error occurs.</span></span> <span data-ttu-id="fef73-119">정수 리터럴에 접미사가 없는 경우 해당 형식은 값이 표현될 수 있는 [int](int.md), [uint](uint.md), [long](long.md), [ulong](ulong.md) 형식 중 첫 번째 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="fef73-119">When an integer literal has no suffix, its type is the first of these types in which its value can be represented: [int](int.md), [uint](uint.md), [long](long.md), [ulong](ulong.md).</span></span> <span data-ttu-id="fef73-120">즉, 이 예제에서 숫자 리터럴 `0x9A` 및 `0b10011010`은 값이 <xref:System.SByte.MaxValue?displayProperty=fullName>을 초과하는 156인 부호 있는 32비트 정수로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="fef73-120">This means that, in this example, the numeric literals `0x9A` and `0b10011010` are interpreted as 32-bit signed integers with a value of 156, which exceeds <xref:System.SByte.MaxValue?displayProperty=fullName>.</span></span> <span data-ttu-id="fef73-121">이 때문에 캐스팅 연산자가 필요하며, [unchecked](unchecked.md) 컨텍스트에서 대입이 발생해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef73-121">Because of this, the casting operator is needed, and the assignment must occur in an [unchecked](unchecked.md) context.</span></span> 

## <a name="compiler-overload-resolution"></a><span data-ttu-id="fef73-122">컴파일러 오버로드 확인</span><span class="sxs-lookup"><span data-stu-id="fef73-122">Compiler overload resolution</span></span>

 <span data-ttu-id="fef73-123">오버로드된 메서드를 호출할 때 캐스트를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef73-123">A cast must be used when calling overloaded methods.</span></span> <span data-ttu-id="fef73-124">예를 들어 `sbyte` 및 [int](../../../csharp/language-reference/keywords/int.md) 매개 변수를 사용하는 다음의 오버로드된 메서드를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="fef73-124">Consider, for example, the following overloaded methods that use `sbyte` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(sbyte b) {}  
```  
  
 <span data-ttu-id="fef73-125">`sbyte` 캐스트를 사용하면 올바른 형식이 호출됩니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fef73-125">Using the `sbyte` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp 
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the sbyte parameter:  
SampleMethod((sbyte)5);  
```  
  
## <a name="conversions"></a><span data-ttu-id="fef73-126">변환</span><span class="sxs-lookup"><span data-stu-id="fef73-126">Conversions</span></span>  
 <span data-ttu-id="fef73-127">`sbyte`에서 [short](../../../csharp/language-reference/keywords/short.md), [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) 또는 [decimal](../../../csharp/language-reference/keywords/decimal.md)로 미리 정의된 암시적 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef73-127">There is a predefined implicit conversion from `sbyte` to [short](../../../csharp/language-reference/keywords/short.md), [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="fef73-128">더 큰 저장소 크기의 비리터럴 숫자 형식을 `sbyte`로 암시적으로 변환할 수는 없습니다(정수 형식의 저장소 크기는 [정수 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="fef73-128">You cannot implicitly convert nonliteral numeric types of larger storage size to `sbyte` (see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) for the storage sizes of integral types).</span></span> <span data-ttu-id="fef73-129">예를 들어 다음 두 가지 `sbyte` 변수 `x` 및 `y`를 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="fef73-129">Consider, for example, the following two `sbyte` variables `x` and `y`:</span></span>  
  
```csharp  
sbyte x = 10, y = 20;  
```  
  
 <span data-ttu-id="fef73-130">대입 연산자의 오른쪽에 있는 산술 식은 기본적으로 [int](../../../csharp/language-reference/keywords/int.md)로 평가되므로 다음 대입문은 컴파일 오류를 일으킵니다.</span><span class="sxs-lookup"><span data-stu-id="fef73-130">The following assignment statement will produce a compilation error, because the arithmetic expression on the right side of the assignment operator evaluates to [int](../../../csharp/language-reference/keywords/int.md) by default.</span></span>  
  
```csharp  
sbyte z = x + y;   // Error: conversion from int to sbyte  
```  
  
 <span data-ttu-id="fef73-131">이 문제를 해결하려면 다음 예제와 같이 식을 캐스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="fef73-131">To fix this problem, cast the expression as in the following example:</span></span>  
  
```csharp  
sbyte z = (sbyte)(x + y);   // OK: explicit conversion  
```  
  
 <span data-ttu-id="fef73-132">그러나 대상 변수에 동일한 저장소 크기 또는 더 큰 저장소 크기가 있는 다음 문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef73-132">It is possible though to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp
sbyte x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="fef73-133">부동 소수점 형식에서 `sbyte`로의 암시적 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fef73-133">Notice also that there is no implicit conversion from floating-point types to `sbyte`.</span></span> <span data-ttu-id="fef73-134">예를 들어 명시적 캐스트를 사용하지 않는 경우 다음 문은 컴파일러 오류를 일으킵니다.</span><span class="sxs-lookup"><span data-stu-id="fef73-134">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
sbyte x = 3.0;         // Error: no implicit conversion from double  
sbyte y = (sbyte)3.0;  // OK: explicit conversion  
```  
  
 <span data-ttu-id="fef73-135">부동 소수점 형식 및 정수 형식이 혼합된 산술 식에 대한 자세한 내용은 [float](../../../csharp/language-reference/keywords/float.md) 및 [double](../../../csharp/language-reference/keywords/double.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fef73-135">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="fef73-136">암시적 숫자 변환 규칙에 대한 자세한 내용은 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fef73-136">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="fef73-137">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="fef73-137">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fef73-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fef73-138">See Also</span></span>  
 <span data-ttu-id="fef73-139"><xref:System.SByte></span><span class="sxs-lookup"><span data-stu-id="fef73-139"><xref:System.SByte></span></span>   
 <span data-ttu-id="fef73-140">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="fef73-140">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="fef73-141">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="fef73-141">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="fef73-142">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="fef73-142">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="fef73-143">[정수 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="fef73-143">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="fef73-144">[기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="fef73-144">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="fef73-145">[암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="fef73-145">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="fef73-146">명시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="fef73-146">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

