---
title: int(C# 참조)
ms.date: 03/14/2017
f1_keywords:
- int_CSharpKeyword
- int
helpviewer_keywords:
- int keyword [C#]
ms.assetid: 212447b4-5d2a-41aa-88ab-84fe710bdb52
ms.openlocfilehash: 41ee5ecdae815eaddf8652a4873c060fb8f92bc3
ms.sourcegitcommit: f9e38d31288fe5962e6be5b0cc286da633482873
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37028268"
---
# <a name="int-c-reference"></a><span data-ttu-id="3e866-102">int(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="3e866-102">int (C# Reference)</span></span>

<span data-ttu-id="3e866-103">`int`는 다음 표에 나와 있는 크기와 범위에 따라 값을 저장하는 정수 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3e866-103">`int` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="3e866-104">형식</span><span class="sxs-lookup"><span data-stu-id="3e866-104">Type</span></span>|<span data-ttu-id="3e866-105">범위</span><span class="sxs-lookup"><span data-stu-id="3e866-105">Range</span></span>|<span data-ttu-id="3e866-106">크기</span><span class="sxs-lookup"><span data-stu-id="3e866-106">Size</span></span>|<span data-ttu-id="3e866-107">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="3e866-107">.NET type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`int`|<span data-ttu-id="3e866-108">–2,147,483,648 ~ 2,147,483,647</span><span class="sxs-lookup"><span data-stu-id="3e866-108">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="3e866-109">부호 있는 32비트 정수</span><span class="sxs-lookup"><span data-stu-id="3e866-109">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="3e866-110">리터럴</span><span class="sxs-lookup"><span data-stu-id="3e866-110">Literals</span></span>  
 
<span data-ttu-id="3e866-111">10진수 리터럴, 16진수 리터럴 또는 (C# 7.0부터) 이진 리터럴을 할당하여 `int` 변수를 선언하고 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e866-111">You can declare and initialize an `int` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span>  <span data-ttu-id="3e866-112">정수 리터럴이 `int` 범위를 벗어나는 경우(즉 <xref:System.Int32.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.Int32.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3e866-112">If the integer literal is outside the range of `int` (that is, if it is less than <xref:System.Int32.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int32.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span> 

<span data-ttu-id="3e866-113">다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 90,946와 같은 정수가 `int` 값에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e866-113">In the following example, integers equal to 90,946 that are represented as decimal, hexadecimal, and binary literals are assigned to `int` values.</span></span>  
  
[!code-csharp[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Int)]  

> [!NOTE] 
> <span data-ttu-id="3e866-114">`0x` 또는 `0X` 접두사를 사용하여 16진수 리터럴을 나타내고, `0b` 또는 `0B` 접두사를 사용하여 이진 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3e866-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="3e866-115">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e866-115">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="3e866-116">C# 7.0부터 가독성 향상을 위해 몇 가지 기능이 추가됐습니다.</span><span class="sxs-lookup"><span data-stu-id="3e866-116">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="3e866-117">C# 7.0은 숫자 구분 기호로 밑줄 문자 `_`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e866-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="3e866-118">C# 7.2는 접두사 뒤에 이진 또는 16진수 리터럴에 대한 자리 구분 기호로 `_`을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e866-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="3e866-119">10진수 리터럴에 선행 밑줄이 있는 것이 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e866-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="3e866-120">일부 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3e866-120">Some examples are shown below.</span></span>

[!code-csharp[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#IntS)]  
 
 <span data-ttu-id="3e866-121">`int` 형식을 나타내는 접미사는 없어도 형식을 나타내는 접미사가 정수 리터럴에 포함되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e866-121">Integer literals can also include a suffix that denotes the type, although there is no suffix that denotes the `int` type.</span></span> <span data-ttu-id="3e866-122">정수 리터럴에 접미사가 없는 경우 해당 형식은 값이 표현될 수 있는 다음 형식 중 첫 번째 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3e866-122">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. `int`
2. [<span data-ttu-id="3e866-123">uint</span><span class="sxs-lookup"><span data-stu-id="3e866-123">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. [<span data-ttu-id="3e866-124">long</span><span class="sxs-lookup"><span data-stu-id="3e866-124">long</span></span>](../../../csharp/language-reference/keywords/long.md)
4. [<span data-ttu-id="3e866-125">ulong</span><span class="sxs-lookup"><span data-stu-id="3e866-125">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 
 
<span data-ttu-id="3e866-126">이 예제에서 리터럴 90946은 `int` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3e866-126">In these examples, the literal 90946 is of type `int`.</span></span>
  
## <a name="conversions"></a><span data-ttu-id="3e866-127">변환</span><span class="sxs-lookup"><span data-stu-id="3e866-127">Conversions</span></span>  
 <span data-ttu-id="3e866-128">`int`에서 [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) 또는 [decimal](../../../csharp/language-reference/keywords/decimal.md)로 미리 정의된 암시적 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e866-128">There is a predefined implicit conversion from `int` to [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="3e866-129">예:</span><span class="sxs-lookup"><span data-stu-id="3e866-129">For example:</span></span>  
  
```csharp  
// '123' is an int, so an implicit conversion takes place here:  
float f = 123;  
```  
  
 <span data-ttu-id="3e866-130">[sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) 또는 [char](../../../csharp/language-reference/keywords/char.md)에서 `int`로 미리 정의된 암시적 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e866-130">There is a predefined implicit conversion from [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), or [char](../../../csharp/language-reference/keywords/char.md) to `int`.</span></span> <span data-ttu-id="3e866-131">예를 들어 다음 대입문은 캐스트 없이 컴파일 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3e866-131">For example, the following assignment statement will produce a compilation error without a cast:</span></span>  
  
```csharp  
long aLong = 22;  
int i1 = aLong;       // Error: no implicit conversion from long.  
int i2 = (int)aLong;  // OK: explicit conversion.  
```  
  
 <span data-ttu-id="3e866-132">부동 소수점 형식에서 `int`로의 암시적 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e866-132">Notice also that there is no implicit conversion from floating-point types to `int`.</span></span> <span data-ttu-id="3e866-133">예를 들어 명시적 캐스트를 사용하지 않는 경우 다음 문은 컴파일러 오류를 일으킵니다.</span><span class="sxs-lookup"><span data-stu-id="3e866-133">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
int x = 3.0;         // Error: no implicit conversion from double.  
int y = (int)3.0;    // OK: explicit conversion.  
```  
  
 <span data-ttu-id="3e866-134">부동 소수점 형식 및 정수 형식이 혼합된 산술 식에 대한 자세한 내용은 [float](../../../csharp/language-reference/keywords/float.md) 및 [double](../../../csharp/language-reference/keywords/double.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3e866-134">For more information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="3e866-135">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="3e866-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3e866-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3e866-136">See Also</span></span>  
 <xref:System.Int32>  
 [<span data-ttu-id="3e866-137">C# 참조</span><span class="sxs-lookup"><span data-stu-id="3e866-137">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="3e866-138">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="3e866-138">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="3e866-139">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="3e866-139">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="3e866-140">정수 계열 형식 표</span><span class="sxs-lookup"><span data-stu-id="3e866-140">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="3e866-141">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="3e866-141">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="3e866-142">암시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="3e866-142">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="3e866-143">명시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="3e866-143">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
