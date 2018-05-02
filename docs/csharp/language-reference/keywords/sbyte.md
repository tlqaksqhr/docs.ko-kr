---
title: sbyte(C# 참조)
ms.date: 03/14/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- sbyte_CSharpKeyword
- sbyte
helpviewer_keywords:
- sbyte keyword [C#]
ms.assetid: 1a9c7b48-73d1-4d33-b485-c4faf0a816bc
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1c3950e11e1a81cf7263e146705c351e3dd8a6e9
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="sbyte-c-reference"></a><span data-ttu-id="c7d87-102">sbyte(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="c7d87-102">sbyte (C# Reference)</span></span>

<span data-ttu-id="c7d87-103">`sbyte`는 다음 표에 나와 있는 크기와 범위에 따라 값을 저장하는 정수 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c7d87-103">`sbyte` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="c7d87-104">형식</span><span class="sxs-lookup"><span data-stu-id="c7d87-104">Type</span></span>|<span data-ttu-id="c7d87-105">범위</span><span class="sxs-lookup"><span data-stu-id="c7d87-105">Range</span></span>|<span data-ttu-id="c7d87-106">크기</span><span class="sxs-lookup"><span data-stu-id="c7d87-106">Size</span></span>|<span data-ttu-id="c7d87-107">.NET Framework 형식</span><span class="sxs-lookup"><span data-stu-id="c7d87-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`sbyte`|<span data-ttu-id="c7d87-108">-128 ~ 127</span><span class="sxs-lookup"><span data-stu-id="c7d87-108">-128 to 127</span></span>|<span data-ttu-id="c7d87-109">부호 있는 8비트 정수</span><span class="sxs-lookup"><span data-stu-id="c7d87-109">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="c7d87-110">리터럴</span><span class="sxs-lookup"><span data-stu-id="c7d87-110">Literals</span></span>  

<span data-ttu-id="c7d87-111">10진수 리터럴, 16진수 리터럴 또는 (C# 7.0부터) 이진 리터럴을 할당하여 `sbyte` 변수를 선언하고 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7d87-111">You can declare and initialize an `sbyte` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span> 

<span data-ttu-id="c7d87-112">다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 -102와 같은 정수가 [int](../../../csharp/language-reference/keywords/int.md)에서 `sbyte` 값으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7d87-112">In the following example, integers equal to -102 that are represented as decimal, hexadecimal, and binary literals are converted from [int](../../../csharp/language-reference/keywords/int.md) to `sbyte` values.</span></span>    
  
[!code-csharp[SByte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#SByte)]  

> [!NOTE] 
> <span data-ttu-id="c7d87-113">`0x` 또는 `0X` 접두사를 사용하여 16진수 리터럴을 나타내고, `0b` 또는 `0B` 접두사를 사용하여 이진 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c7d87-113">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="c7d87-114">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7d87-114">Decimal literals have no prefix.</span></span>

<span data-ttu-id="c7d87-115">C# 7.0부터 가독성 향상을 위해 몇 가지 기능이 추가됐습니다.</span><span class="sxs-lookup"><span data-stu-id="c7d87-115">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="c7d87-116">C# 7.0은 숫자 구분 기호로 밑줄 문자 `_`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7d87-116">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="c7d87-117">C# 7.2는 접두사 뒤에 이진 또는 16진수 리터럴에 대한 자리 구분 기호로 `_`을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7d87-117">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="c7d87-118">10진수 리터럴에 선행 밑줄이 있는 것이 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7d87-118">A decimal literal isn't permitted to have a leading underscore.</span></span>

 <span data-ttu-id="c7d87-119">일부 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c7d87-119">Some examples are shown below.</span></span>

[!code-csharp[SByteSeparator](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#SByteS)]  

<span data-ttu-id="c7d87-120">정수 리터럴이 `sbyte` 범위를 벗어나는 경우(즉 <xref:System.SByte.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.SByte.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c7d87-120">If the integer literal is outside the range of `sbyte` (that is, if it is less than <xref:System.SByte.MinValue?displayProperty=nameWithType> or greater than <xref:System.SByte.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span> <span data-ttu-id="c7d87-121">정수 리터럴에 접미사가 없는 경우 해당 형식은 값이 표현될 수 있는 [int](int.md), [uint](uint.md), [long](long.md), [ulong](ulong.md) 형식 중 첫 번째 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c7d87-121">When an integer literal has no suffix, its type is the first of these types in which its value can be represented: [int](int.md), [uint](uint.md), [long](long.md), [ulong](ulong.md).</span></span> <span data-ttu-id="c7d87-122">즉, 이 예제에서 숫자 리터럴 `0x9A` 및 `0b10011010`은 값이 <xref:System.SByte.MaxValue?displayProperty=nameWithType>을 초과하는 156인 부호 있는 32비트 정수로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7d87-122">This means that, in this example, the numeric literals `0x9A` and `0b10011010` are interpreted as 32-bit signed integers with a value of 156, which exceeds <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c7d87-123">이 때문에 캐스팅 연산자가 필요하며, [unchecked](unchecked.md) 컨텍스트에서 대입이 발생해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7d87-123">Because of this, the casting operator is needed, and the assignment must occur in an [unchecked](unchecked.md) context.</span></span> 

## <a name="compiler-overload-resolution"></a><span data-ttu-id="c7d87-124">컴파일러 오버로드 확인</span><span class="sxs-lookup"><span data-stu-id="c7d87-124">Compiler overload resolution</span></span>

 <span data-ttu-id="c7d87-125">오버로드된 메서드를 호출할 때 캐스트를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7d87-125">A cast must be used when calling overloaded methods.</span></span> <span data-ttu-id="c7d87-126">예를 들어 `sbyte` 및 [int](../../../csharp/language-reference/keywords/int.md) 매개 변수를 사용하는 다음의 오버로드된 메서드를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="c7d87-126">Consider, for example, the following overloaded methods that use `sbyte` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(sbyte b) {}  
```  
  
 <span data-ttu-id="c7d87-127">`sbyte` 캐스트를 사용하면 올바른 형식이 호출됩니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c7d87-127">Using the `sbyte` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp 
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the sbyte parameter:  
SampleMethod((sbyte)5);  
```  
  
## <a name="conversions"></a><span data-ttu-id="c7d87-128">변환</span><span class="sxs-lookup"><span data-stu-id="c7d87-128">Conversions</span></span>  
 <span data-ttu-id="c7d87-129">`sbyte`에서 [short](../../../csharp/language-reference/keywords/short.md), [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) 또는 [decimal](../../../csharp/language-reference/keywords/decimal.md)로 미리 정의된 암시적 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7d87-129">There is a predefined implicit conversion from `sbyte` to [short](../../../csharp/language-reference/keywords/short.md), [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="c7d87-130">더 큰 저장소 크기의 비리터럴 숫자 형식을 `sbyte`로 암시적으로 변환할 수는 없습니다(정수 형식의 저장소 크기는 [정수 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="c7d87-130">You cannot implicitly convert nonliteral numeric types of larger storage size to `sbyte` (see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) for the storage sizes of integral types).</span></span> <span data-ttu-id="c7d87-131">예를 들어 다음 두 가지 `sbyte` 변수 `x` 및 `y`를 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="c7d87-131">Consider, for example, the following two `sbyte` variables `x` and `y`:</span></span>  
  
```csharp  
sbyte x = 10, y = 20;  
```  
  
 <span data-ttu-id="c7d87-132">대입 연산자의 오른쪽에 있는 산술 식은 기본적으로 [int](../../../csharp/language-reference/keywords/int.md)로 평가되므로 다음 대입문은 컴파일 오류를 일으킵니다.</span><span class="sxs-lookup"><span data-stu-id="c7d87-132">The following assignment statement will produce a compilation error, because the arithmetic expression on the right side of the assignment operator evaluates to [int](../../../csharp/language-reference/keywords/int.md) by default.</span></span>  
  
```csharp  
sbyte z = x + y;   // Error: conversion from int to sbyte  
```  
  
 <span data-ttu-id="c7d87-133">이 문제를 해결하려면 다음 예제와 같이 식을 캐스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="c7d87-133">To fix this problem, cast the expression as in the following example:</span></span>  
  
```csharp  
sbyte z = (sbyte)(x + y);   // OK: explicit conversion  
```  
  
 <span data-ttu-id="c7d87-134">그러나 대상 변수에 동일한 저장소 크기 또는 더 큰 저장소 크기가 있는 다음 문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7d87-134">It is possible though to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp
sbyte x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="c7d87-135">부동 소수점 형식에서 `sbyte`로의 암시적 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7d87-135">Notice also that there is no implicit conversion from floating-point types to `sbyte`.</span></span> <span data-ttu-id="c7d87-136">예를 들어 명시적 캐스트를 사용하지 않는 경우 다음 문은 컴파일러 오류를 일으킵니다.</span><span class="sxs-lookup"><span data-stu-id="c7d87-136">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
sbyte x = 3.0;         // Error: no implicit conversion from double  
sbyte y = (sbyte)3.0;  // OK: explicit conversion  
```  
  
 <span data-ttu-id="c7d87-137">부동 소수점 형식 및 정수 형식이 혼합된 산술 식에 대한 자세한 내용은 [float](../../../csharp/language-reference/keywords/float.md) 및 [double](../../../csharp/language-reference/keywords/double.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7d87-137">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="c7d87-138">암시적 숫자 변환 규칙에 대한 자세한 내용은 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7d87-138">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="c7d87-139">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="c7d87-139">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c7d87-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7d87-140">See Also</span></span>  
 <xref:System.SByte>  
 [<span data-ttu-id="c7d87-141">C# 참조</span><span class="sxs-lookup"><span data-stu-id="c7d87-141">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="c7d87-142">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="c7d87-142">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c7d87-143">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="c7d87-143">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="c7d87-144">정수 계열 형식 표</span><span class="sxs-lookup"><span data-stu-id="c7d87-144">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="c7d87-145">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="c7d87-145">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="c7d87-146">암시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="c7d87-146">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="c7d87-147">명시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="c7d87-147">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
