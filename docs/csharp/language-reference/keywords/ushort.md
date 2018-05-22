---
title: ushort(C# 참조)
ms.date: 03/14/2017
f1_keywords:
- ushort
- ushort_CSharpKeyword
helpviewer_keywords:
- ushort keyword [C#]
ms.assetid: 1a7dbaae-b7a0-4111-872a-c88a6d3981ac
ms.openlocfilehash: 03638893978779fcfd34544363d935fa5e609481
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ushort-c-reference"></a><span data-ttu-id="11f8b-102">ushort(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="11f8b-102">ushort (C# Reference)</span></span>

<span data-ttu-id="11f8b-103">`ushort` 키워드는 다음 표에 나와 있는 크기와 범위에 따라 값을 저장하는 정수 데이터 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="11f8b-103">The `ushort` keyword indicates an integral data type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="11f8b-104">형식</span><span class="sxs-lookup"><span data-stu-id="11f8b-104">Type</span></span>|<span data-ttu-id="11f8b-105">범위</span><span class="sxs-lookup"><span data-stu-id="11f8b-105">Range</span></span>|<span data-ttu-id="11f8b-106">크기</span><span class="sxs-lookup"><span data-stu-id="11f8b-106">Size</span></span>|<span data-ttu-id="11f8b-107">.NET Framework 형식</span><span class="sxs-lookup"><span data-stu-id="11f8b-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`ushort`|<span data-ttu-id="11f8b-108">0 ~ 65,535</span><span class="sxs-lookup"><span data-stu-id="11f8b-108">0 to 65,535</span></span>|<span data-ttu-id="11f8b-109">부호 없는 16비트 정수</span><span class="sxs-lookup"><span data-stu-id="11f8b-109">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="11f8b-110">리터럴</span><span class="sxs-lookup"><span data-stu-id="11f8b-110">Literals</span></span>  

<span data-ttu-id="11f8b-111">10진수 리터럴, 16진수 리터럴 또는 (C# 7.0부터) 이진 리터럴을 할당하여 `ushort` 변수를 선언하고 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11f8b-111">You can declare and initialize a `ushort` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span> <span data-ttu-id="11f8b-112">정수 리터럴이 `ushort` 범위를 벗어나는 경우(즉 <xref:System.UInt16.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.UInt16.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="11f8b-112">If the integer literal is outside the range of `ushort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt16.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="11f8b-113">다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 65,034와 같은 정수가 [int](../../../csharp/language-reference/keywords/int.md)에서 `ushort` 값으로 암시적으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="11f8b-113">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](../../../csharp/language-reference/keywords/int.md) to `ushort` values.</span></span>    
  
[!code-csharp[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShort)]  

> [!NOTE] 
> <span data-ttu-id="11f8b-114">`0x` 또는 `0X` 접두사를 사용하여 16진수 리터럴을 나타내고, `0b` 또는 `0B` 접두사를 사용하여 이진 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="11f8b-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="11f8b-115">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11f8b-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="11f8b-116">C# 7.0부터 가독성 향상을 위해 몇 가지 기능이 추가됐습니다.</span><span class="sxs-lookup"><span data-stu-id="11f8b-116">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="11f8b-117">C# 7.0은 숫자 구분 기호로 밑줄 문자 `_`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11f8b-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="11f8b-118">C# 7.2는 접두사 뒤에 이진 또는 16진수 리터럴에 대한 자리 구분 기호로 `_`을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11f8b-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="11f8b-119">10진수 리터럴에 선행 밑줄이 있는 것이 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11f8b-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="11f8b-120">일부 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="11f8b-120">Some examples are shown below.</span></span>

[!code-csharp[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShortS)]  
 
## <a name="compiler-overload-resolution"></a><span data-ttu-id="11f8b-121">컴파일러 오버로드 확인</span><span class="sxs-lookup"><span data-stu-id="11f8b-121">Compiler overload resolution</span></span>
  
 <span data-ttu-id="11f8b-122">오버로드된 메서드를 호출할 때 캐스트를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11f8b-122">A cast must be used when you call overloaded methods.</span></span> <span data-ttu-id="11f8b-123">예를 들어 `ushort` 및 [int](../../../csharp/language-reference/keywords/int.md) 매개 변수를 사용하는 다음의 오버로드된 메서드를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="11f8b-123">Consider, for example, the following overloaded methods that use `ushort` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ushort s) {}  
```  
 
 <span data-ttu-id="11f8b-124">`ushort` 캐스트를 사용하면 올바른 형식이 호출됩니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="11f8b-124">Using the `ushort` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
// Calls the method with the int parameter:  
SampleMethod(5);  
// Calls the method with the ushort parameter:  
SampleMethod((ushort)5);    
```  
  
## <a name="conversions"></a><span data-ttu-id="11f8b-125">변환</span><span class="sxs-lookup"><span data-stu-id="11f8b-125">Conversions</span></span>  
 <span data-ttu-id="11f8b-126">`ushort`에서 [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) 또는 [decimal](../../../csharp/language-reference/keywords/decimal.md)로의 미리 정의된 암시적 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11f8b-126">There is a predefined implicit conversion from `ushort` to [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="11f8b-127">[byte](../../../csharp/language-reference/keywords/byte.md) 또는 [char](../../../csharp/language-reference/keywords/char.md)에서 `ushort`로 미리 정의된 암시적 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11f8b-127">There is a predefined implicit conversion from [byte](../../../csharp/language-reference/keywords/byte.md) or [char](../../../csharp/language-reference/keywords/char.md) to `ushort`.</span></span> <span data-ttu-id="11f8b-128">아니면 캐스트를 사용해 명시적 변환을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11f8b-128">Otherwise a cast must be used to perform an explicit conversion.</span></span> <span data-ttu-id="11f8b-129">예를 들어 다음 두 가지 `ushort` 변수 `x` 및 `y`를 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="11f8b-129">Consider, for example, the following two `ushort` variables `x` and `y`:</span></span>  
  
```csharp 
ushort x = 5, y = 12;  
```  
  
 <span data-ttu-id="11f8b-130">다음 대입문은 대입 연산자의 오른쪽에 있는 산술 식이 기본적으로 `int`로 계산되므로 컴파일 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="11f8b-130">The following assignment statement will produce a compilation error, because the arithmetic expression on the right side of the assignment operator evaluates to `int` by default.</span></span>  
  
```csharp  
ushort z = x + y;   // Error: conversion from int to ushort  
```  
  
 <span data-ttu-id="11f8b-131">이 문제를 해결하려면 다음 캐스트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="11f8b-131">To fix this problem, use a cast:</span></span>  
  
```csharp 
ushort z = (ushort)(x + y);   // OK: explicit conversion   
```  
  
 <span data-ttu-id="11f8b-132">그러나 대상 변수에 동일한 저장소 크기 또는 더 큰 저장소 크기가 있는 다음 문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11f8b-132">It is possible though to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="11f8b-133">부동 소수점 형식에서 `ushort`로의 암시적 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11f8b-133">Notice also that there is no implicit conversion from floating-point types to `ushort`.</span></span> <span data-ttu-id="11f8b-134">예를 들어 명시적 캐스트를 사용하지 않는 경우 다음 문은 컴파일러 오류를 일으킵니다.</span><span class="sxs-lookup"><span data-stu-id="11f8b-134">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error -- no implicit conversion from double:  
ushort x = 3.0;   
// OK -- explicit conversion:  
ushort y = (ushort)3.0;  
```  
  
 <span data-ttu-id="11f8b-135">부동 소수점 형식 및 정수 형식이 혼합된 산술 식에 대한 자세한 내용은 [float](../../../csharp/language-reference/keywords/float.md) 및 [double](../../../csharp/language-reference/keywords/double.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="11f8b-135">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="11f8b-136">암시적 숫자 변환 규칙에 대한 자세한 내용은 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="11f8b-136">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="11f8b-137">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="11f8b-137">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="11f8b-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11f8b-138">See Also</span></span>  
 <xref:System.UInt16>  
 [<span data-ttu-id="11f8b-139">C# 참조</span><span class="sxs-lookup"><span data-stu-id="11f8b-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="11f8b-140">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="11f8b-140">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="11f8b-141">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="11f8b-141">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="11f8b-142">정수 계열 형식 표</span><span class="sxs-lookup"><span data-stu-id="11f8b-142">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="11f8b-143">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="11f8b-143">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="11f8b-144">암시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="11f8b-144">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="11f8b-145">명시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="11f8b-145">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
