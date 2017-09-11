---
title: "long(C# 참조)"
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- long_CSharpKeyword
- long
dev_langs:
- CSharp
helpviewer_keywords:
- long keyword [C#]
ms.assetid: f9b24319-1f39-48be-a42b-d528ee28a7fd
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
ms.openlocfilehash: 5f7d2d6a3d5781b4e120b8399c7206d4429dd98e
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="long-c-reference"></a><span data-ttu-id="0ae4b-102">long(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="0ae4b-102">long (C# Reference)</span></span>

<span data-ttu-id="0ae4b-103">`long`은 다음 표에 나와 있는 크기와 범위에 따라 값을 저장하는 정수 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0ae4b-103">`long` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="0ae4b-104">형식</span><span class="sxs-lookup"><span data-stu-id="0ae4b-104">Type</span></span>|<span data-ttu-id="0ae4b-105">범위</span><span class="sxs-lookup"><span data-stu-id="0ae4b-105">Range</span></span>|<span data-ttu-id="0ae4b-106">크기</span><span class="sxs-lookup"><span data-stu-id="0ae4b-106">Size</span></span>|<span data-ttu-id="0ae4b-107">.NET Framework 형식</span><span class="sxs-lookup"><span data-stu-id="0ae4b-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`long`|<span data-ttu-id="0ae4b-108">–9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807</span><span class="sxs-lookup"><span data-stu-id="0ae4b-108">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="0ae4b-109">부호 있는 64비트 정수</span><span class="sxs-lookup"><span data-stu-id="0ae4b-109">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="0ae4b-110">리터럴</span><span class="sxs-lookup"><span data-stu-id="0ae4b-110">Literals</span></span> 

<span data-ttu-id="0ae4b-111">10진수 리터럴, 16진수 리터럴 또는 (C# 7부터) 이진 리터럴을 할당하여 `long` 변수를 선언하고 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ae4b-111">You can declare and initialize a `long` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span> 

<span data-ttu-id="0ae4b-112">다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 4,294,967,296과 같은 정수가 `long` 값에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ae4b-112">In the following example, integers equal to 4,294,967,296 that are represented as decimal, hexadecimal, and binary literals are assigned to `long` values.</span></span>  
  
<span data-ttu-id="0ae4b-113">[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Long)]</span><span class="sxs-lookup"><span data-stu-id="0ae4b-113">[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Long)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="0ae4b-114">`0x` 또는 `0X` 접두사를 사용하여 16진수 리터럴을 나타내고, `0b` 또는 `0B` 접두사를 사용하여 이진 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0ae4b-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="0ae4b-115">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ae4b-115">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="0ae4b-116">C# 7부터는 다음 예제와 같이 밑줄 문자 `_`를 자릿수 구분 기호로 사용하여 가독성을 향상할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ae4b-116">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="0ae4b-117">[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]</span><span class="sxs-lookup"><span data-stu-id="0ae4b-117">[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]</span></span>  
 
 <span data-ttu-id="0ae4b-118">형식을 나타내는 접미사가 정수 리터럴에 포함되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ae4b-118">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="0ae4b-119">`L` 접미사는 `long`을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0ae4b-119">The suffix `L` denotes a `long`.</span></span> <span data-ttu-id="0ae4b-120">다음 예제에서는 `L` 접미사를 사용하여 정수(long)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0ae4b-120">The following example uses the `L` suffix to denote a long integer:</span></span>
 
```csharp
long value = 4294967296L;  
```  

> [!NOTE]
>  <span data-ttu-id="0ae4b-121">소문자 "l"을 접미사로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ae4b-121">You can also use the lowercase letter "l" as a suffix.</span></span> <span data-ttu-id="0ae4b-122">그러나 이렇게 하면 문자 "l"과 숫자 "1"을 혼동하기 쉬우므로 컴파일러 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ae4b-122">However, this generates a compiler warning because the letter "l" is easily confused with the digit "1."</span></span> <span data-ttu-id="0ae4b-123">쉽게 구별할 수 있도록 "L"을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae4b-123">Use "L" for clarity.</span></span>  
  
 <span data-ttu-id="0ae4b-124">`L` 접미사를 사용하는 경우 리터럴 정수의 형식은 해당 크기에 따라 `long` 또는 [ulong](../../../csharp/language-reference/keywords/ulong.md)으로 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ae4b-124">When you use the suffix `L`, the type of the literal integer is determined to be either `long` or [ulong](../../../csharp/language-reference/keywords/ulong.md), depending on its size.</span></span> <span data-ttu-id="0ae4b-125">이 경우 [ulong](../../../csharp/language-reference/keywords/ulong.md)의 범위보다 작기 때문에 `long`입니다.</span><span class="sxs-lookup"><span data-stu-id="0ae4b-125">In this case, it is `long` because it less than the range of [ulong](../../../csharp/language-reference/keywords/ulong.md).</span></span>  
  
 <span data-ttu-id="0ae4b-126">접미사는 일반적으로 오버로드된 메서드를 호출할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ae4b-126">A common use of the suffix is to call overloaded methods.</span></span> <span data-ttu-id="0ae4b-127">예를 들어 다음 오버로드된 메서드에는 `long` 및 [int](../../../csharp/language-reference/keywords/int.md) 형식의 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ae4b-127">For example, the following overloaded methods have parameters of type `long` and [int](../../../csharp/language-reference/keywords/int.md):</span></span>  
  
```csharp
public static void SampleMethod(int i) {}  
public static void SampleMethod(long l) {}  
```  
  
 <span data-ttu-id="0ae4b-128">`L` 접미사를 사용하면 올바른 오버로드가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ae4b-128">The `L` suffix guarantees that the correct overload is called:</span></span>  
  
```csharp  
SampleMethod(5);    // Calls the method with the int parameter  
SampleMethod(5L);   // Calls the method with the long parameter  
```  
<span data-ttu-id="0ae4b-129">정수 리터럴에 접미사가 없는 경우 해당 형식은 값이 표현될 수 있는 다음 형식 중 첫 번째 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0ae4b-129">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. [<span data-ttu-id="0ae4b-130">int</span><span class="sxs-lookup"><span data-stu-id="0ae4b-130">int</span></span>](int.md)
2. [<span data-ttu-id="0ae4b-131">uint</span><span class="sxs-lookup"><span data-stu-id="0ae4b-131">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. `long`
4. [<span data-ttu-id="0ae4b-132">ulong</span><span class="sxs-lookup"><span data-stu-id="0ae4b-132">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 

<span data-ttu-id="0ae4b-133">앞의 예제에서 리터럴 4294967296은 [uint](../../../csharp/language-reference/keywords/uint.md)의 범위를 초과하기 때문에 `long` 형식입니다(정수 형식의 저장소 크기는 [정수 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="0ae4b-133">The literal 4294967296 in the previous examples is of type `long`, because it exceeds the range of [uint](../../../csharp/language-reference/keywords/uint.md) (see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) for the storage sizes of integral types).</span></span>  
  
 <span data-ttu-id="0ae4b-134">같은 식에서 다른 정수 형식과 함께 `long` 형식을 사용하는 경우에는 식이 `long`(또는 관계형 또는 부울 식의 경우 [bool](../../../csharp/language-reference/keywords/bool.md))으로 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ae4b-134">If you use the `long` type with other integral types in the same expression, the expression is evaluated as `long` (or [bool](../../../csharp/language-reference/keywords/bool.md) in the case of relational or Boolean expressions).</span></span> <span data-ttu-id="0ae4b-135">예를 들어 다음 식은 `long`으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ae4b-135">For example, the following expression evaluates as `long`:</span></span>  
  
```csharp  
898L + 88  
```  
  
 <span data-ttu-id="0ae4b-136">부동 소수점 형식 및 정수 형식이 혼합된 산술 식에 대한 자세한 내용은 [float](../../../csharp/language-reference/keywords/float.md) 및 [double](../../../csharp/language-reference/keywords/double.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0ae4b-136">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="0ae4b-137">변환</span><span class="sxs-lookup"><span data-stu-id="0ae4b-137">Conversions</span></span>  
 <span data-ttu-id="0ae4b-138">`long`에서 [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) 또는 [decimal](../../../csharp/language-reference/keywords/decimal.md)로 미리 정의된 암시적 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ae4b-138">There is a predefined implicit conversion from `long` to [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="0ae4b-139">없는 경우 캐스트를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae4b-139">Otherwise a cast must be used.</span></span> <span data-ttu-id="0ae4b-140">예를 들어 다음 문은 명시적 캐스트 없이 컴파일 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae4b-140">For example, the following statement will produce a compilation error without an explicit cast:</span></span>  
  
```csharp  
int x = 8L;        // Error: no implicit conversion from long to int  
int x = (int)8L;   // OK: explicit conversion to int  
```  
  
 <span data-ttu-id="0ae4b-141">[sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md) 또는 [char](../../../csharp/language-reference/keywords/char.md)에서 `long`으로 미리 정의된 암시적 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ae4b-141">There is a predefined implicit conversion from [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), or [char](../../../csharp/language-reference/keywords/char.md) to `long`.</span></span>  
  
 <span data-ttu-id="0ae4b-142">부동 소수점 형식에서 `long`로의 암시적 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ae4b-142">Notice also that there is no implicit conversion from floating-point types to `long`.</span></span> <span data-ttu-id="0ae4b-143">예를 들어 명시적 캐스트를 사용하지 않는 경우 다음 문은 컴파일러 오류를 일으킵니다.</span><span class="sxs-lookup"><span data-stu-id="0ae4b-143">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
long x = 3.0;         // Error: no implicit conversion from double  
long y = (long)3.0;   // OK: explicit conversion  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="0ae4b-144">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="0ae4b-144">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0ae4b-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0ae4b-145">See Also</span></span>  
 <span data-ttu-id="0ae4b-146"><xref:System.Int64></span><span class="sxs-lookup"><span data-stu-id="0ae4b-146"><xref:System.Int64></span></span>   
 <span data-ttu-id="0ae4b-147">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="0ae4b-147">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="0ae4b-148">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0ae4b-148">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="0ae4b-149">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="0ae4b-149">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="0ae4b-150">[정수 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="0ae4b-150">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="0ae4b-151">[기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="0ae4b-151">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="0ae4b-152">[암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="0ae4b-152">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="0ae4b-153">명시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="0ae4b-153">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

