---
title: "decimal(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- decimal_CSharpKeyword
- decimal
helpviewer_keywords:
- decimal keyword [C#]
ms.assetid: b6522132-b5ee-4be3-ad13-3adfdb7de7a1
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0da001851c681fe4d698b920d9668b2f6b731e3a
ms.sourcegitcommit: 973a12d1e6962cd9a9c263fbfaad040ec8267fe9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2018
---
# <a name="decimal-c-reference"></a><span data-ttu-id="6cfda-102">decimal(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="6cfda-102">decimal (C# Reference)</span></span>
<span data-ttu-id="6cfda-103">`decimal` 키워드는 128비트 데이터 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6cfda-103">The `decimal` keyword indicates a 128-bit data type.</span></span> <span data-ttu-id="6cfda-104">`decimal` 형식은 부동 소수점 형식보다 전체 자릿수는 크고 범위는 작아서 재무 및 통화 계산에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="6cfda-104">Compared to other floating-point types, the `decimal` type has more precision and a smaller range, which makes it appropriate for financial and monetary calculations.</span></span> <span data-ttu-id="6cfda-105">다음 표에서는 `decimal` 형식의 대략적인 범위와 전체 자릿수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6cfda-105">The approximate range and precision for the `decimal` type are shown in the following table.</span></span>  
  
|<span data-ttu-id="6cfda-106">형식</span><span class="sxs-lookup"><span data-stu-id="6cfda-106">Type</span></span>|<span data-ttu-id="6cfda-107">근사 범위</span><span class="sxs-lookup"><span data-stu-id="6cfda-107">Approximate Range</span></span>|<span data-ttu-id="6cfda-108">전체 자릿수</span><span class="sxs-lookup"><span data-stu-id="6cfda-108">Precision</span></span>|<span data-ttu-id="6cfda-109">.NET Framework 형식</span><span class="sxs-lookup"><span data-stu-id="6cfda-109">.NET Framework type</span></span>|  
|----------|-----------------------|---------------|-------------------------|  
|`decimal`|<span data-ttu-id="6cfda-110">(-7.9 x 10<sup>28</sup> ~ 7.9 x 10<sup>28</sup>) / (10<sup>0</sup> ~ 10<sup>28</sup>)</span><span class="sxs-lookup"><span data-stu-id="6cfda-110">(-7.9 x 10<sup>28</sup> to 7.9 x 10<sup>28</sup>) / (10<sup>0</sup> to 10<sup>28</sup>)</span></span>|<span data-ttu-id="6cfda-111">28-29개의 유효 자릿수</span><span class="sxs-lookup"><span data-stu-id="6cfda-111">28-29 significant digits</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|  

<span data-ttu-id="6cfda-112">`decimal`의 기본값은 0m입니다.</span><span class="sxs-lookup"><span data-stu-id="6cfda-112">The default value of a `decimal` is 0m.</span></span>
  
## <a name="literals"></a><span data-ttu-id="6cfda-113">리터럴</span><span class="sxs-lookup"><span data-stu-id="6cfda-113">Literals</span></span>  
 <span data-ttu-id="6cfda-114">숫자 형식의 실수 리터럴이 `decimal`로 처리되게 하려면 다음과 같이 접미사 m 또는 M을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6cfda-114">If you want a numeric real literal to be treated as `decimal`, use the suffix m or M, for example:</span></span>  
  
```csharp
decimal myMoney = 300.5m;  
```  
  
 <span data-ttu-id="6cfda-115">m 접미사가 없으면 숫자가 [double](../../../csharp/language-reference/keywords/double.md)로 처리되어 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="6cfda-115">Without the suffix m, the number is treated as a [double](../../../csharp/language-reference/keywords/double.md) and generates a compiler error.</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="6cfda-116">변환</span><span class="sxs-lookup"><span data-stu-id="6cfda-116">Conversions</span></span>  
 <span data-ttu-id="6cfda-117">정수 형식은 암시적으로 `decimal`로 변환되어 계산 결과가 `decimal`로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="6cfda-117">The integral types are implicitly converted to `decimal` and the result evaluates to `decimal`.</span></span> <span data-ttu-id="6cfda-118">따라서 접미사를 붙이지 않고 정수 리터럴을 사용하여 decimal 변수를 초기화할 수 있습니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6cfda-118">Therefore you can initialize a decimal variable using an integer literal, without the suffix, as follows:</span></span>  
  
```csharp
decimal myMoney = 300;  
```  
  
 <span data-ttu-id="6cfda-119">다른 부동 소수점 형식과 `decimal` 형식 간의 암시적 변환은 없습니다. 따라서 이 두 형식 간의 변환에는 캐스트를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cfda-119">There is no implicit conversion between other floating-point types and the `decimal` type; therefore, a cast must be used to convert between these two types.</span></span> <span data-ttu-id="6cfda-120">예:</span><span class="sxs-lookup"><span data-stu-id="6cfda-120">For example:</span></span>  
  
```csharp
decimal myMoney = 99.9m;  
double x = (double)myMoney;  
myMoney = (decimal)x;  
```  
  
 <span data-ttu-id="6cfda-121">또한 같은 식에서 `decimal`과 숫자 정수 형식을 혼합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cfda-121">You can also mix `decimal` and numeric integral types in the same expression.</span></span> <span data-ttu-id="6cfda-122">그러나 캐스트를 사용하지 않고 `decimal`과 다른 부동 소수점 형식을 혼합하면 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="6cfda-122">However, mixing `decimal` and other floating-point types without a cast causes a compilation error.</span></span>  
  
 <span data-ttu-id="6cfda-123">암시적 숫자 변환에 대한 자세한 내용은 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6cfda-123">For more information about implicit numeric conversions, see [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
 <span data-ttu-id="6cfda-124">명시적 숫자 변환에 대한 자세한 내용은 [명시적 숫자 변환 표](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6cfda-124">For more information about explicit numeric conversions, see [Explicit Numeric Conversions Table](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).</span></span>  
  
## <a name="formatting-decimal-output"></a><span data-ttu-id="6cfda-125">Decimal 출력 서식 지정</span><span class="sxs-lookup"><span data-stu-id="6cfda-125">Formatting Decimal Output</span></span>  
 <span data-ttu-id="6cfda-126">`String.Format` 메서드를 사용하거나 <xref:System.Console.Write%2A?displayProperty=nameWithType>을 호출하는 `String.Format()` 메서드를 통해 결과의 서식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cfda-126">You can format the results by using the `String.Format` method, or through the <xref:System.Console.Write%2A?displayProperty=nameWithType> method, which calls `String.Format()`.</span></span> <span data-ttu-id="6cfda-127">통화 서식은 이 문서 뒷부분에 있는 두 번째 예제처럼 표준 통화 서식 문자열 "C" 또는 "c"를 사용하여 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6cfda-127">The currency format is specified by using the standard currency format string "C" or "c," as shown in the second example later in this article.</span></span> <span data-ttu-id="6cfda-128">`String.Format` 메서드에 대한 자세한 내용은 <xref:System.String.Format%2A?displayProperty=nameWithType>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6cfda-128">For more information about the `String.Format` method, see <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6cfda-129">예</span><span class="sxs-lookup"><span data-stu-id="6cfda-129">Example</span></span>  
 <span data-ttu-id="6cfda-130">다음은 [double](../../../csharp/language-reference/keywords/double.md) 및 `decimal` 변수를 추가하려고 시도하여 컴파일러 오류가 발생하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="6cfda-130">The following example causes a compiler error by trying to add [double](../../../csharp/language-reference/keywords/double.md) and `decimal` variables.</span></span>  
  
```csharp  
decimal dec = 0m;
double dub = 9;  
// The following line causes an error that reads "Operator '+' cannot be applied to   
// operands of type 'double' and 'decimal'"  
Console.WriteLine(dec + dub);   
  
// You can fix the error by using explicit casting of either operand.  
Console.WriteLine(dec + (decimal)dub);  
Console.WriteLine((double)dec + dub);  
```  
  
 <span data-ttu-id="6cfda-131">다음 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="6cfda-131">The result is the following error:</span></span>  
  
 `Operator '+' cannot be applied to operands of type 'double' and 'decimal'`  
  
 <span data-ttu-id="6cfda-132">이 예제에서는 같은 식에 `decimal`과 [int](../../../csharp/language-reference/keywords/int.md)가 혼합되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cfda-132">In this example, a `decimal` and an [int](../../../csharp/language-reference/keywords/int.md) are mixed in the same expression.</span></span> <span data-ttu-id="6cfda-133">계산 결과는 `decimal` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6cfda-133">The result evaluates to the `decimal` type.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/decimal_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="6cfda-134">예</span><span class="sxs-lookup"><span data-stu-id="6cfda-134">Example</span></span>  
 <span data-ttu-id="6cfda-135">이 예제에서는 통화 서식 문자열을 사용하여 출력 서식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6cfda-135">In this example, the output is formatted by using the currency format string.</span></span> <span data-ttu-id="6cfda-136">`x`는 소수 자릿수가 $0.99를 초과하기 때문에 반올림됩니다.</span><span class="sxs-lookup"><span data-stu-id="6cfda-136">Notice that `x` is rounded because the decimal places exceed $0.99.</span></span> <span data-ttu-id="6cfda-137">최대 자릿수를 나타내는 변수 `y`는 올바른 서식으로 정확하게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6cfda-137">The variable `y`, which represents the maximum exact digits, is displayed exactly in the correct format.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/decimal_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="6cfda-138">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="6cfda-138">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6cfda-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6cfda-139">See Also</span></span>  
 <xref:System.Decimal>  
 [<span data-ttu-id="6cfda-140">C# 참조</span><span class="sxs-lookup"><span data-stu-id="6cfda-140">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="6cfda-141">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="6cfda-141">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6cfda-142">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="6cfda-142">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="6cfda-143">정수 계열 형식 표</span><span class="sxs-lookup"><span data-stu-id="6cfda-143">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="6cfda-144">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="6cfda-144">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="6cfda-145">암시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="6cfda-145">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="6cfda-146">명시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="6cfda-146">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
 [<span data-ttu-id="6cfda-147">표준 숫자 형식 문자열</span><span class="sxs-lookup"><span data-stu-id="6cfda-147">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
