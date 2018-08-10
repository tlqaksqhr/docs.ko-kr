---
title: nullable 형식(C# 프로그래밍 가이드)
description: C# nullable 형식 및 사용 방법 알아보기
ms.date: 07/30/2018
helpviewer_keywords:
- nullable types [C#]
- C# language, nullable types
- types [C#], nullable
ms.assetid: e473cb01-28ca-42be-9cea-f717055d72c6
ms.openlocfilehash: 64b326b82cd022ed6590a232546690e2ec2a5c78
ms.sourcegitcommit: 78bcb629abdbdbde0e295b4e81f350a477864aba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39245594"
---
# <a name="nullable-types-c-programming-guide"></a><span data-ttu-id="84bae-103">nullable 형식(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="84bae-103">Nullable types (C# Programming Guide)</span></span>

<span data-ttu-id="84bae-104">Nullable 형식은 <xref:System.Nullable%601?displayProperty=nameWithType> 구조체의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="84bae-104">Nullable types are instances of the <xref:System.Nullable%601?displayProperty=nameWithType> struct.</span></span> <span data-ttu-id="84bae-105">nullable 형식은 기본 형식 `T`의 모든 값과 추가 [null](../../language-reference/keywords/null.md) 값을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84bae-105">Nullable types can represent all the values of an underlying type `T`, and an additional [null](../../language-reference/keywords/null.md) value.</span></span> <span data-ttu-id="84bae-106">기본 형식 `T`는 nullable이 아닌 [값 형식](../../language-reference/keywords/value-types.md)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84bae-106">The underlying type `T` can be any non-nullable [value type](../../language-reference/keywords/value-types.md).</span></span> <span data-ttu-id="84bae-107">`T`는 참조 형식이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="84bae-107">`T` cannot be a reference type.</span></span>

<span data-ttu-id="84bae-108">예를 들어 <xref:System.Int32.MinValue?displayProperty=nameWithType>부터 <xref:System.Int32.MaxValue?displayProperty=nameWithType>까지의 `null` 또는 정수 값을 `Nullable<int>`에 할당하고, [true](../../language-reference/keywords/true-literal.md), [false](../../language-reference/keywords/false-literal.md) 또는 `null`을 `Nullable<bool>`에 할당할 수 있습니다</span><span class="sxs-lookup"><span data-stu-id="84bae-108">For example, you can assign `null` or any integer value from <xref:System.Int32.MinValue?displayProperty=nameWithType> to <xref:System.Int32.MaxValue?displayProperty=nameWithType> to a `Nullable<int>` and [true](../../language-reference/keywords/true-literal.md), [false](../../language-reference/keywords/false-literal.md), or `null` to a `Nullable<bool>`.</span></span>

<span data-ttu-id="84bae-109">기본 형식의 정의되지 않은 값을 표시해야 하는 경우 nullable 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="84bae-109">You use a nullable type when you need to represent the undefined value of an underlying type.</span></span> <span data-ttu-id="84bae-110">부울 변수에는 true와 false라는 두 개의 값만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84bae-110">A Boolean variable can have only two values: true and false.</span></span> <span data-ttu-id="84bae-111">"정의되지 않은" 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84bae-111">There is no "undefined" value.</span></span> <span data-ttu-id="84bae-112">많은 프로그래밍 응용 프로그램(특히, 데이터베이스 상호 작용)에서 변수는 정의되지 않거나 누락될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84bae-112">In many programming applications, most notably database interactions, a variable value can be undefined or missing.</span></span> <span data-ttu-id="84bae-113">예를 들어 데이터베이스의 필드는 true 또는 false 값을 포함하거나 값을 전혀 포함하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84bae-113">For example, a field in a database may contain the values true or false, or it may contain no value at all.</span></span> <span data-ttu-id="84bae-114">해당 경우에 `Nullable<bool>` 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="84bae-114">You use a `Nullable<bool>` type in that case.</span></span>

<span data-ttu-id="84bae-115">null 허용 형식은 다음 특성을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="84bae-115">Nullable types have the following characteristics:</span></span>
  
- <span data-ttu-id="84bae-116">nullable 형식은 `null` 값이 할당될 수 있는 값-형식 변수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="84bae-116">Nullable types represent value-type variables that can be assigned the `null` value.</span></span> <span data-ttu-id="84bae-117">참조 형식에 따라 null 허용 형식을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84bae-117">You cannot create a nullable type based on a reference type.</span></span> <span data-ttu-id="84bae-118">(참조 형식은 `null` 값을 이미 지원합니다.)</span><span class="sxs-lookup"><span data-stu-id="84bae-118">(Reference types already support the `null` value.)</span></span>  
  
- <span data-ttu-id="84bae-119">`T?` 구문은 `Nullable<T>`의 축약형입니다.</span><span class="sxs-lookup"><span data-stu-id="84bae-119">The syntax `T?` is shorthand for `Nullable<T>`.</span></span> <span data-ttu-id="84bae-120">두 가지 형태는 동일하게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84bae-120">The two forms are interchangeable.</span></span>  
  
- <span data-ttu-id="84bae-121">일반 값 형식의 경우처럼 nullable 형식에 값을 할당합니다(`int? x = 10;` 또는 `double? d = 4.108;`).</span><span class="sxs-lookup"><span data-stu-id="84bae-121">Assign a value to a nullable type just as you would for an underlying value type: `int? x = 10;` or `double? d = 4.108;`.</span></span> <span data-ttu-id="84bae-122">`null` 값을 할당할 수도 있습니다(`int? x = null;`).</span><span class="sxs-lookup"><span data-stu-id="84bae-122">You also can assign the `null` value: `int? x = null;`.</span></span>  
  
- <span data-ttu-id="84bae-123">다음 예제와 같이 <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> 및 <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> 읽기 전용 속성을 사용하여 null인지 테스트하고 값을 검색합니다. `if (x.HasValue) y = x.Value;`</span><span class="sxs-lookup"><span data-stu-id="84bae-123">Use the <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> and <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> readonly properties to test for null and retrieve the value, as shown in the following example: `if (x.HasValue) y = x.Value;`</span></span>  
  
  - <span data-ttu-id="84bae-124"><xref:System.Nullable%601.HasValue%2A> 속성은 변수에 값이 있으면 `true`를 반환하고, `null`이면 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="84bae-124">The <xref:System.Nullable%601.HasValue%2A> property returns `true` if the variable contains a value, or `false` if it's `null`.</span></span>
  
  - <span data-ttu-id="84bae-125"><xref:System.Nullable%601.Value%2A> 속성은 <xref:System.Nullable%601.HasValue%2A>가 `true`를 반환하는 경우 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="84bae-125">The <xref:System.Nullable%601.Value%2A> property returns a value if <xref:System.Nullable%601.HasValue%2A> returns `true`.</span></span> <span data-ttu-id="84bae-126">그렇지 않으면 <xref:System.InvalidOperationException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="84bae-126">Otherwise, an <xref:System.InvalidOperationException> is thrown.</span></span>  
  
- <span data-ttu-id="84bae-127">다음 예제와 같이 nullable 형식에서 `==` 및 `!=` 연산자를 사용할 수도 있습니다. `if (x != null) y = x.Value;`</span><span class="sxs-lookup"><span data-stu-id="84bae-127">You can also use the `==` and `!=` operators with a nullable type, as shown in the following example: `if (x != null) y = x.Value;`.</span></span> <span data-ttu-id="84bae-128">`a` 및 `b`가 둘 다 null인 경우 `a == b`는 `true`로 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="84bae-128">If `a` and `b` are both null, `a == b` evaluates to `true`.</span></span>  

- <span data-ttu-id="84bae-129">C# 7.0부터는 패턴 일치를 사용하여 nullable 형식의 값을 검사하고 가져올 수 있습니다. `if (x is int xValue) y = xValue;`</span><span class="sxs-lookup"><span data-stu-id="84bae-129">Beginning with C# 7.0, you can use pattern matching to both examine and get a value of a nullable type: `if (x is int xValue) y = xValue;`.</span></span>
  
- <span data-ttu-id="84bae-130">기본값인 `T?`는 <xref:System.Nullable%601.HasValue%2A> 속성이 `false`를 반환하는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="84bae-130">The default value of `T?` is an instance whose <xref:System.Nullable%601.HasValue%2A> property returns `false`.</span></span>  

- <span data-ttu-id="84bae-131">nullable 형식 값이 `null`인 경우 <xref:System.Nullable%601.GetValueOrDefault> 메서드를 사용하여 할당된 값 또는 기본 값 형식의 [기본값](../../language-reference/keywords/default-values-table.md) 중 하나를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="84bae-131">Use the <xref:System.Nullable%601.GetValueOrDefault> method to return either the assigned value, or the [default](../../language-reference/keywords/default-values-table.md) value of the underlying value type if the value of the nullable type is `null`.</span></span>  

- <span data-ttu-id="84bae-132">nullable 형식 값이 `null`인 경우 <xref:System.Nullable%601.GetValueOrDefault(%600)> 메서드를 사용하여 할당된 값 또는 제공된 기본값 중 하나를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="84bae-132">Use the <xref:System.Nullable%601.GetValueOrDefault(%600)> method to return either the assigned value, or the provided default value if the value of the nullable type is `null`.</span></span>
  
- <span data-ttu-id="84bae-133">[null 결합 연산자](../../language-reference/operators/null-coalescing-operator.md)인 `??`를 사용하여 nullable 형식의 값을 기반으로 하는 기본 형식에 값을 할당합니다. `int? x = null; int y = x ?? -1;`</span><span class="sxs-lookup"><span data-stu-id="84bae-133">Use the [null-coalescing operator](../../language-reference/operators/null-coalescing-operator.md), `??`, to assign a value to an underlying type based on a value of the nullable type: `int? x = null; int y = x ?? -1;`.</span></span> <span data-ttu-id="84bae-134">예제에서 `x`가 null이므로 결과 값인 `y`는 `-1`입니다.</span><span class="sxs-lookup"><span data-stu-id="84bae-134">In the example, since `x` is null, the result value of `y` is `-1`.</span></span>

- <span data-ttu-id="84bae-135">두 데이터 형식 간에 사용자 정의 변환이 정의된 경우 이러한 데이터 형식의 nullable 버전에도 같은 변환을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84bae-135">If a user-defined conversion is defined between two data types, the same conversion can also be used with the nullable versions of these data types.</span></span>
  
- <span data-ttu-id="84bae-136">중첩된 null 허용 형식은 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84bae-136">Nested nullable types are not allowed.</span></span> <span data-ttu-id="84bae-137">다음 줄은 컴파일되지 않습니다. `Nullable<Nullable<int>> n;`</span><span class="sxs-lookup"><span data-stu-id="84bae-137">The following line doesn't compile: `Nullable<Nullable<int>> n;`</span></span>  

<span data-ttu-id="84bae-138">자세한 내용은 [nullable 형식 사용](using-nullable-types.md) 및 [방법: nullable 형식 식별](how-to-identify-a-nullable-type.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84bae-138">For more information, see the [Using nullable types](using-nullable-types.md) and [How to: Identify a nullable type](how-to-identify-a-nullable-type.md) topics.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="84bae-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="84bae-139">See also</span></span>

 <xref:System.Nullable%601?displayProperty=nameWithType>  
 <xref:System.Nullable?displayProperty=nameWithType>  
 [<span data-ttu-id="84bae-140">?? 연산자</span><span class="sxs-lookup"><span data-stu-id="84bae-140">?? Operator</span></span>](../../language-reference/operators/null-coalescing-operator.md)  
 [<span data-ttu-id="84bae-141">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="84bae-141">C# Programming Guide</span></span>](../index.md)  
 [<span data-ttu-id="84bae-142">C# 가이드</span><span class="sxs-lookup"><span data-stu-id="84bae-142">C# Guide</span></span>](../../index.md)  
 [<span data-ttu-id="84bae-143">C# 참조</span><span class="sxs-lookup"><span data-stu-id="84bae-143">C# Reference</span></span>](../../language-reference/index.md)  
 [<span data-ttu-id="84bae-144">Nullable 값 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="84bae-144">Nullable Value Types (Visual Basic)</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
