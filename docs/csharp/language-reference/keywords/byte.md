---
title: byte(C# 참조)
ms.date: 03/14/2017
f1_keywords:
- byte
- byte_CSharpKeyword
helpviewer_keywords:
- byte keyword [C#]
ms.assetid: 111f1db9-ca32-4f0e-b497-4783517eda47
ms.openlocfilehash: 28acbe67b85637550fdb1f5e290a9abb60bf5c65
ms.sourcegitcommit: f9e38d31288fe5962e6be5b0cc286da633482873
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37027891"
---
# <a name="byte-c-reference"></a><span data-ttu-id="618f4-102">byte(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="618f4-102">byte (C# Reference)</span></span>

<span data-ttu-id="618f4-103">`byte`는 다음 표에 나와 있는 값을 저장하는 정수 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="618f4-103">`byte` denotes an integral type that stores values as indicated in the following table.</span></span>  
  
|<span data-ttu-id="618f4-104">형식</span><span class="sxs-lookup"><span data-stu-id="618f4-104">Type</span></span>|<span data-ttu-id="618f4-105">범위</span><span class="sxs-lookup"><span data-stu-id="618f4-105">Range</span></span>|<span data-ttu-id="618f4-106">크기</span><span class="sxs-lookup"><span data-stu-id="618f4-106">Size</span></span>|<span data-ttu-id="618f4-107">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="618f4-107">.NET type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`byte`|<span data-ttu-id="618f4-108">0 ~ 255</span><span class="sxs-lookup"><span data-stu-id="618f4-108">0 to 255</span></span>|<span data-ttu-id="618f4-109">부호 없는 8비트 정수</span><span class="sxs-lookup"><span data-stu-id="618f4-109">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="618f4-110">리터럴</span><span class="sxs-lookup"><span data-stu-id="618f4-110">Literals</span></span>  

 <span data-ttu-id="618f4-111">10진수 리터럴, 16진수 리터럴 또는 (C# 7.0부터) 이진 리터럴을 할당하여 `byte` 변수를 선언하고 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="618f4-111">You can declare and initialize a `byte` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span> <span data-ttu-id="618f4-112">정수 리터럴이 `byte` 범위를 벗어나는 경우(즉 <xref:System.Byte.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.Byte.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="618f4-112">If the integer literal is outside the range of `byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="618f4-113">다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 201과 같은 정수가 [int](../../../csharp/language-reference/keywords/int.md)에서 `byte` 값으로 암시적으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="618f4-113">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](../../../csharp/language-reference/keywords/int.md) to `byte` values.</span></span>    
  
[!code-csharp[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Byte)]  

> [!NOTE] 
> <span data-ttu-id="618f4-114">`0x` 또는 `0X` 접두사를 사용하여 16진수 리터럴을 나타내고, `0b` 또는 `0B` 접두사를 사용하여 이진 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="618f4-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="618f4-115">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="618f4-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="618f4-116">C# 7.0부터 가독성 향상을 위해 몇 가지 기능이 추가됐습니다.</span><span class="sxs-lookup"><span data-stu-id="618f4-116">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="618f4-117">C# 7.0은 숫자 구분 기호로 밑줄 문자 `_`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="618f4-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="618f4-118">C# 7.2는 접두사 뒤에 이진 또는 16진수 리터럴에 대한 자리 구분 기호로 `_`을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="618f4-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="618f4-119">10진수 리터럴에 선행 밑줄이 있는 것이 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="618f4-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="618f4-120">일부 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="618f4-120">Some examples are shown below.</span></span>

[!code-csharp[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ByteS)]  
 
## <a name="conversions"></a><span data-ttu-id="618f4-121">변환</span><span class="sxs-lookup"><span data-stu-id="618f4-121">Conversions</span></span>  
 <span data-ttu-id="618f4-122">`byte`에서 [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) 또는 [decimal](../../../csharp/language-reference/keywords/decimal.md)로의 미리 정의된 암시적 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="618f4-122">There is a predefined implicit conversion from `byte` to [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="618f4-123">더 큰 저장소 크기의 비리터럴 숫자 형식을 `byte`로 암시적으로 변환할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="618f4-123">You cannot implicitly convert non-literal numeric types of larger storage size to `byte`.</span></span> <span data-ttu-id="618f4-124">정수 형식의 저장소 크기에 대한 자세한 내용은 [정수 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="618f4-124">For more information on the storage sizes of integral types, see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md).</span></span> <span data-ttu-id="618f4-125">예를 들어 다음 두 가지 `byte` 변수 `x` 및 `y`를 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="618f4-125">Consider, for example, the following two `byte` variables `x` and `y`:</span></span>  
  
```csharp  
byte x = 10, y = 20;  
```  
  
 <span data-ttu-id="618f4-126">다음 대입문은 대입 연산자의 오른쪽에 있는 산술 식이 기본적으로 `int`로 계산되므로 컴파일 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="618f4-126">The following assignment statement will produce a compilation error, because the arithmetic expression on the right-hand side of the assignment operator evaluates to `int` by default.</span></span>  
  
```csharp  
// Error: conversion from int to byte:  
byte z = x + y;  
```  
  
 <span data-ttu-id="618f4-127">이 문제를 해결하려면 다음 캐스트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="618f4-127">To fix this problem, use a cast:</span></span>  
  
```csharp  
// OK: explicit conversion:  
byte z = (byte)(x + y);  
```  
  
 <span data-ttu-id="618f4-128">그러나 대상 변수에 동일한 저장소 크기 또는 더 큰 저장소 크기가 있는 다음 문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="618f4-128">It is possible though, to use the following statements where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp  
int x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="618f4-129">또한 부동 소수점 형식에서 `byte`로의 암시적 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="618f4-129">Also, there is no implicit conversion from floating-point types to `byte`.</span></span> <span data-ttu-id="618f4-130">예를 들어 명시적 캐스트를 사용하지 않는 경우 다음 문은 컴파일러 오류를 일으킵니다.</span><span class="sxs-lookup"><span data-stu-id="618f4-130">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error: no implicit conversion from double:  
byte x = 3.0;   
// OK: explicit conversion:  
byte y = (byte)3.0;  
```  
  
 <span data-ttu-id="618f4-131">오버로드된 메서드를 호출할 때 캐스트를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="618f4-131">When calling overloaded methods, a cast must be used.</span></span> <span data-ttu-id="618f4-132">예를 들어 `byte` 및 [int](../../../csharp/language-reference/keywords/int.md) 매개 변수를 사용하는 다음의 오버로드된 메서드를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="618f4-132">Consider, for example, the following overloaded methods that use `byte` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(byte b) {}  
```  
  
 <span data-ttu-id="618f4-133">`byte` 캐스트를 사용하면 올바른 형식이 호출됩니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="618f4-133">Using the `byte` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the byte parameter:  
SampleMethod((byte)5);  
```  
  
 <span data-ttu-id="618f4-134">부동 소수점 형식 및 정수 형식이 혼합된 산술 식에 대한 자세한 내용은 [float](../../../csharp/language-reference/keywords/float.md) 및 [double](../../../csharp/language-reference/keywords/double.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="618f4-134">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="618f4-135">암시적 숫자 변환 규칙에 대한 자세한 내용은 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="618f4-135">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="618f4-136">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="618f4-136">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="618f4-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="618f4-137">See Also</span></span>  
 <xref:System.Byte>  
 [<span data-ttu-id="618f4-138">C# 참조</span><span class="sxs-lookup"><span data-stu-id="618f4-138">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="618f4-139">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="618f4-139">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="618f4-140">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="618f4-140">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="618f4-141">정수 계열 형식 표</span><span class="sxs-lookup"><span data-stu-id="618f4-141">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="618f4-142">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="618f4-142">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="618f4-143">암시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="618f4-143">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="618f4-144">명시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="618f4-144">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
