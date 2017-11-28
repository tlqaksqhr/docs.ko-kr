---
title: "float(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- float
- float_CSharpKeyword
helpviewer_keywords:
- float keyword [C#]
- floating-point numbers [C#], float keyword
ms.assetid: 1e77db7b-dedb-48b7-8dd1-b055e96a9258
caps.latest.revision: "24"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 846f132812fe90a285c81a020d440fc846f88b5b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="float-c-reference"></a><span data-ttu-id="e5612-102">float(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="e5612-102">float (C# Reference)</span></span>
<span data-ttu-id="e5612-103">`float` 키워드는 32비트 부동 소수점 값을 저장하는 단순 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e5612-103">The `float` keyword signifies a simple type that stores 32-bit floating-point values.</span></span> <span data-ttu-id="e5612-104">다음 표에서는 `float` 형식의 전체 자릿수와 근사 범위를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e5612-104">The following table shows the precision and approximate range for the `float` type.</span></span>  
  
|<span data-ttu-id="e5612-105">형식</span><span class="sxs-lookup"><span data-stu-id="e5612-105">Type</span></span>|<span data-ttu-id="e5612-106">근사 범위</span><span class="sxs-lookup"><span data-stu-id="e5612-106">Approximate range</span></span>|<span data-ttu-id="e5612-107">전체 자릿수</span><span class="sxs-lookup"><span data-stu-id="e5612-107">Precision</span></span>|<span data-ttu-id="e5612-108">.NET Framework 형식</span><span class="sxs-lookup"><span data-stu-id="e5612-108">.NET Framework type</span></span>|  
|----------|-----------------------|---------------|-------------------------|  
|`float`|<span data-ttu-id="e5612-109">-3.4 × 10<sup>38</sup> ~ +3.4 × 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="e5612-109">-3.4 × 10<sup>38</sup>to +3.4 × 10<sup>38</sup></span></span>|<span data-ttu-id="e5612-110">7개의 자릿수</span><span class="sxs-lookup"><span data-stu-id="e5612-110">7 digits</span></span>|<xref:System.Single?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="e5612-111">리터럴</span><span class="sxs-lookup"><span data-stu-id="e5612-111">Literals</span></span>  
 <span data-ttu-id="e5612-112">기본적으로 대입 연산자 오른쪽의 실수 리터럴은 [double](double.md)로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5612-112">By default, a real numeric literal on the right side of the assignment operator is treated as [double](double.md).</span></span> <span data-ttu-id="e5612-113">따라서 부동 변수를 초기화하려면 다음 예제와 같이 접미사 `f` 또는 `F`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e5612-113">Therefore, to initialize a float variable, use the suffix `f` or `F`, as in the following example:</span></span>  
  
```csharp
float x = 3.5F;  
```
  
 <span data-ttu-id="e5612-114">이전 선언에서 접미사를 사용하지 않은 경우 [double](double.md) 값을 `float` 변수에 저장하려고 하기 때문에 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="e5612-114">If you do not use the suffix in the previous declaration, you will get a compilation error because you are trying to store a [double](double.md) value into a `float` variable.</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="e5612-115">변환</span><span class="sxs-lookup"><span data-stu-id="e5612-115">Conversions</span></span>  
 <span data-ttu-id="e5612-116">식에서 숫자 정수 형식과 부동 소수점 형식을 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5612-116">You can mix numeric integral types and floating-point types in an expression.</span></span> <span data-ttu-id="e5612-117">이 경우 정수 형식이 부동 소수점 형식으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5612-117">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="e5612-118">식의 계산은 다음 규칙에 따라 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5612-118">The evaluation of the expression is performed according to the following rules:</span></span>  
  
-   <span data-ttu-id="e5612-119">부동 소수점 형식 중 하나가 [double](double.md)이면 식은 [double](double.md) 또는 [bool](bool.md)(관계형 식이나 부울 식의 경우)로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5612-119">If one of the floating-point types is [double](double.md), the expression evaluates to [double](double.md) or [bool](bool.md) in relational or Boolean expressions.</span></span>  
  
-   <span data-ttu-id="e5612-120">식에 [double](double.md) 형식이 없으면 `float` 또는 [bool](bool.md)(관계형 식이나 부울 식의 경우)로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5612-120">If there is no [double](double.md) type in the expression, the expression evaluates to `float` or [bool](bool.md) in relational or Boolean expressions.</span></span>  
  
 <span data-ttu-id="e5612-121">부동 소수점 식에는 다음과 같은 값 집합이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5612-121">A floating-point expression can contain the following sets of values:</span></span>  
  
-   <span data-ttu-id="e5612-122">양수 및 음수 0</span><span class="sxs-lookup"><span data-stu-id="e5612-122">Positive and negative zero</span></span>  
  
-   <span data-ttu-id="e5612-123">양수 및 음수 무한대</span><span class="sxs-lookup"><span data-stu-id="e5612-123">Positive and negative infinity</span></span>  
  
-   <span data-ttu-id="e5612-124">NaN(Not-a-Number) 값</span><span class="sxs-lookup"><span data-stu-id="e5612-124">Not-a-Number value (NaN)</span></span>  
  
-   <span data-ttu-id="e5612-125">한정된 0이 아닌 값의 집합</span><span class="sxs-lookup"><span data-stu-id="e5612-125">The finite set of nonzero values</span></span>  
  
 <span data-ttu-id="e5612-126">이러한 값에 대한 자세한 내용은 [IEEE](http://www.ieee.org) 웹 사이트에서 제공되는 이진 부동 소수점 연산에 대한 IEEE 표준을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5612-126">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](http://www.ieee.org) Web site.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5612-127">예제</span><span class="sxs-lookup"><span data-stu-id="e5612-127">Example</span></span>  
 <span data-ttu-id="e5612-128">다음 예제에서는 [int](int.md), [short](short.md) 및 `float`가 수학 식에 포함되어 `float` 결과를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e5612-128">In the following example, an [int](int.md), a [short](short.md), and a `float` are included in a mathematical expression giving a `float` result.</span></span> <span data-ttu-id="e5612-129">(`float`는 <xref:System.Single?displayProperty=nameWithType> 형식의 별칭입니다.) 식에 [double](double.md)이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e5612-129">(Remember that `float` is an alias for the <xref:System.Single?displayProperty=nameWithType> type.) Notice that there is no [double](double.md) in the expression.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/float_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="e5612-130">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="e5612-130">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e5612-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5612-131">See Also</span></span>  
 <xref:System.Single>  
 [<span data-ttu-id="e5612-132">C# 참조</span><span class="sxs-lookup"><span data-stu-id="e5612-132">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e5612-133">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="e5612-133">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e5612-134">캐스팅 및 형식 변환</span><span class="sxs-lookup"><span data-stu-id="e5612-134">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
 [<span data-ttu-id="e5612-135">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="e5612-135">C# Keywords</span></span>](index.md)  
 [<span data-ttu-id="e5612-136">정수 계열 형식 표</span><span class="sxs-lookup"><span data-stu-id="e5612-136">Integral Types Table</span></span>](integral-types-table.md)  
 [<span data-ttu-id="e5612-137">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="e5612-137">Built-In Types Table</span></span>](built-in-types-table.md)  
 [<span data-ttu-id="e5612-138">암시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="e5612-138">Implicit Numeric Conversions Table</span></span>](implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="e5612-139">명시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="e5612-139">Explicit Numeric Conversions Table</span></span>](explicit-numeric-conversions-table.md)
