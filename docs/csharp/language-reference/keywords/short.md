---
title: short(C# 참조)
ms.date: 03/14/2017
f1_keywords:
- short
- short_CSharpKeyword
helpviewer_keywords:
- short keyword [C#]
ms.assetid: 04c10688-e51a-4a87-bfec-83f7fb42ff11
ms.openlocfilehash: 657d5bb3866a3ad88226740ebf7ef12c3654e56b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="short-c-reference"></a><span data-ttu-id="7d998-102">short(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="7d998-102">short (C# Reference)</span></span>

<span data-ttu-id="7d998-103">`short`는 다음 표에 나와 있는 크기와 범위에 따라 값을 저장하는 정수 데이터 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7d998-103">`short` denotes an integral data type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="7d998-104">형식</span><span class="sxs-lookup"><span data-stu-id="7d998-104">Type</span></span>|<span data-ttu-id="7d998-105">범위</span><span class="sxs-lookup"><span data-stu-id="7d998-105">Range</span></span>|<span data-ttu-id="7d998-106">크기</span><span class="sxs-lookup"><span data-stu-id="7d998-106">Size</span></span>|<span data-ttu-id="7d998-107">.NET Framework 형식</span><span class="sxs-lookup"><span data-stu-id="7d998-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`short`|<span data-ttu-id="7d998-108">–32,768 ~ 32,767</span><span class="sxs-lookup"><span data-stu-id="7d998-108">-32,768 to 32,767</span></span>|<span data-ttu-id="7d998-109">부호 있는 16비트 정수</span><span class="sxs-lookup"><span data-stu-id="7d998-109">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="7d998-110">리터럴</span><span class="sxs-lookup"><span data-stu-id="7d998-110">Literals</span></span>  

<span data-ttu-id="7d998-111">10진수 리터럴, 16진수 리터럴 또는 (C# 7.0부터) 이진 리터럴을 할당하여 `short` 변수를 선언하고 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d998-111">You can declare and initialize a `short` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span>  <span data-ttu-id="7d998-112">정수 리터럴이 `short` 범위를 벗어나는 경우(즉 <xref:System.Int16.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.Int16.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7d998-112">If the integer literal is outside the range of `short` (that is, if it is less than <xref:System.Int16.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int16.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span> 

<span data-ttu-id="7d998-113">다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 1,034와 같은 정수가 [int](../../../csharp/language-reference/keywords/int.md)에서 `short` 값으로 암시적으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d998-113">In the following example, integers equal to 1,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](../../../csharp/language-reference/keywords/int.md) to `short` values.</span></span>  
  
[!code-csharp[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Short)]  

> [!NOTE] 
> <span data-ttu-id="7d998-114">`0x` 또는 `0X` 접두사를 사용하여 16진수 리터럴을 나타내고, `0b` 또는 `0B` 접두사를 사용하여 이진 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7d998-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="7d998-115">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d998-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="7d998-116">C# 7.0부터 가독성 향상을 위해 몇 가지 기능이 추가됐습니다.</span><span class="sxs-lookup"><span data-stu-id="7d998-116">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="7d998-117">C# 7.0은 숫자 구분 기호로 밑줄 문자 `_`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d998-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="7d998-118">C# 7.2는 접두사 뒤에 이진 또는 16진수 리터럴에 대한 자리 구분 기호로 `_`을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d998-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="7d998-119">10진수 리터럴에 선행 밑줄이 있는 것이 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d998-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="7d998-120">일부 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7d998-120">Some examples are shown below.</span></span>

[!code-csharp[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ShortS)]  
 
## <a name="compiler-overload-resolution"></a><span data-ttu-id="7d998-121">컴파일러 오버로드 확인</span><span class="sxs-lookup"><span data-stu-id="7d998-121">Compiler overload resolution</span></span>

 <span data-ttu-id="7d998-122">오버로드된 메서드를 호출할 때 캐스트를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d998-122">A cast must be used when calling overloaded methods.</span></span> <span data-ttu-id="7d998-123">예를 들어 `short` 및 [int](../../../csharp/language-reference/keywords/int.md) 매개 변수를 사용하는 다음의 오버로드된 메서드를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="7d998-123">Consider, for example, the following overloaded methods that use `short` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(short s) {}  
```  
  
 <span data-ttu-id="7d998-124">`short` 캐스트를 사용하면 올바른 형식이 호출됩니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7d998-124">Using the `short` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
SampleMethod(5);         // Calling the method with the int parameter  
SampleMethod((short)5);  // Calling the method with the short parameter  
```  
  
## <a name="conversions"></a><span data-ttu-id="7d998-125">변환</span><span class="sxs-lookup"><span data-stu-id="7d998-125">Conversions</span></span>  

 <span data-ttu-id="7d998-126">`short`에서 [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) 또는 [decimal](../../../csharp/language-reference/keywords/decimal.md)로 미리 정의된 암시적 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d998-126">There is a predefined implicit conversion from `short` to [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="7d998-127">더 큰 저장소 크기의 비리터럴 숫자 형식을 `short`로 암시적으로 변환할 수는 없습니다(정수 형식의 저장소 크기는 [정수 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="7d998-127">You cannot implicitly convert nonliteral numeric types of larger storage size to `short` (see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) for the storage sizes of integral types).</span></span> <span data-ttu-id="7d998-128">예를 들어 다음 두 가지 `short` 변수 `x` 및 `y`를 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="7d998-128">Consider, for example, the following two `short` variables `x` and `y`:</span></span>  
  
```csharp  
short x = 5, y = 12;  
```  
  
 <span data-ttu-id="7d998-129">다음 대입문은 대입 연산자의 오른쪽에 있는 산술 식이 기본적으로 [int](../../../csharp/language-reference/keywords/int.md)로 계산되므로 컴파일 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7d998-129">The following assignment statement produces a compilation error because the arithmetic expression on the right-hand side of the assignment operator evaluates to [int](../../../csharp/language-reference/keywords/int.md) by default.</span></span>  
  
```csharp
short z  = x + y;        // Compiler error CS0266: no conversion from int to short
```

 <span data-ttu-id="7d998-130">이 문제를 해결하려면 다음 캐스트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d998-130">To fix this problem, use a cast:</span></span>  
  
```csharp
short z  = (short)(x + y);   // Explicit conversion
```
  
 <span data-ttu-id="7d998-131">대상 변수에 동일한 저장소 크기 또는 더 큰 저장소 크기가 있는 다음 문을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d998-131">It is also possible to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp  
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="7d998-132">부동 소수점 형식에서 `short`로의 암시적 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d998-132">There is no implicit conversion from floating-point types to `short`.</span></span> <span data-ttu-id="7d998-133">예를 들어 명시적 캐스트를 사용하지 않는 경우 다음 문은 컴파일러 오류를 일으킵니다.</span><span class="sxs-lookup"><span data-stu-id="7d998-133">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
short x = 3.0;          // Error: no implicit conversion from double  
short y = (short)3.0;   // OK: explicit conversion  
```  
  
 <span data-ttu-id="7d998-134">부동 소수점 형식 및 정수 형식이 혼합된 산술 식에 대한 자세한 내용은 [float](../../../csharp/language-reference/keywords/float.md) 및 [double](../../../csharp/language-reference/keywords/double.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d998-134">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="7d998-135">암시적 숫자 변환 규칙에 대한 자세한 내용은 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d998-135">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="7d998-136">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="7d998-136">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7d998-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7d998-137">See Also</span></span>  
 <xref:System.Int16>  
 [<span data-ttu-id="7d998-138">C# 참조</span><span class="sxs-lookup"><span data-stu-id="7d998-138">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="7d998-139">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="7d998-139">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7d998-140">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="7d998-140">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="7d998-141">정수 계열 형식 표</span><span class="sxs-lookup"><span data-stu-id="7d998-141">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="7d998-142">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="7d998-142">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="7d998-143">암시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="7d998-143">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="7d998-144">명시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="7d998-144">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
