---
title: 기본값 식(C# 프로그래밍 가이드)
description: 기본값 식은 참조 형식 또는 값 형식에 대해 기본값을 생성합니다.
ms.date: 04/25/2018
helpviewer_keywords:
- generics [C#], default keyword
- default keyword [C#], generic programming
ms.openlocfilehash: be51ad253a2939f538144caf4500f39e144c1664
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33336803"
---
# <a name="default-value-expressions-c-programming-guide"></a><span data-ttu-id="37404-103">기본값 식(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="37404-103">default value expressions (C# programming guide)</span></span>

<span data-ttu-id="37404-104">기본값 식 `default(T)`은 형식 `T`의 기본값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="37404-104">A default value expression `default(T)` produces the default value of a type `T`.</span></span> <span data-ttu-id="37404-105">다음 표에서는 다양한 형식에 대해 생성되는 값을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="37404-105">The following table shows which values are produced for various types:</span></span>

|<span data-ttu-id="37404-106">형식</span><span class="sxs-lookup"><span data-stu-id="37404-106">Type</span></span>|<span data-ttu-id="37404-107">기본값</span><span class="sxs-lookup"><span data-stu-id="37404-107">Default value</span></span>|
|---------|---------|
|<span data-ttu-id="37404-108">임의 참조 형식</span><span class="sxs-lookup"><span data-stu-id="37404-108">Any reference type</span></span>|`null`|
|<span data-ttu-id="37404-109">숫자 값 형식</span><span class="sxs-lookup"><span data-stu-id="37404-109">Numeric value type</span></span>|<span data-ttu-id="37404-110">0</span><span class="sxs-lookup"><span data-stu-id="37404-110">Zero</span></span>|
|[<span data-ttu-id="37404-111">bool</span><span class="sxs-lookup"><span data-stu-id="37404-111">bool</span></span>](../../language-reference/keywords/bool.md)|`false`|
|[<span data-ttu-id="37404-112">char</span><span class="sxs-lookup"><span data-stu-id="37404-112">char</span></span>](../../language-reference/keywords/char.md)|`'\0'`|
|[<span data-ttu-id="37404-113">enum</span><span class="sxs-lookup"><span data-stu-id="37404-113">enum</span></span>](../../language-reference/keywords/enum.md)|<span data-ttu-id="37404-114">식 `(E)0`로 생성한 값이며 여기서 `E`는 열거형 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="37404-114">The value produced by the expression `(E)0`, where `E` is the enum identifier.</span></span>|
|[<span data-ttu-id="37404-115">struct</span><span class="sxs-lookup"><span data-stu-id="37404-115">struct</span></span>](../../language-reference/keywords/struct.md)|<span data-ttu-id="37404-116">모든 값 형식 필드를 기본값으로 설정하고 모든 참조 형식 필드를 `null`로 설정하여 생성한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="37404-116">The value produced by setting all value type fields to their default value and all reference type fields to `null`.</span></span>|
|<span data-ttu-id="37404-117">nullable 형식</span><span class="sxs-lookup"><span data-stu-id="37404-117">Nullable type</span></span>|<span data-ttu-id="37404-118"><xref:System.Nullable%601.HasValue%2A> 속성은 `false`이고 <xref:System.Nullable%601.Value%2A> 속성은 정의되지 않은 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="37404-118">An instance for which the <xref:System.Nullable%601.HasValue%2A> property is `false` and the <xref:System.Nullable%601.Value%2A> property is undefined.</span></span>|

<span data-ttu-id="37404-119">기본값 식은 특히 제네릭 클래스와 메서드에서 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="37404-119">Default value expressions are particularly useful in generic classes and methods.</span></span> <span data-ttu-id="37404-120">제네릭 사용으로 발생하는 한 가지 문제는 다음과 같은 내용을 미리 알지 못하는 경우 매개 변수가 있는 형식 `T`에 기본값을 할당하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="37404-120">One issue that arises using generics is how to assign a default value of a parameterized type `T` when you don't know the following in advance:</span></span>

- <span data-ttu-id="37404-121">`T`가 참조 형식인지 값 형식인지 여부</span><span class="sxs-lookup"><span data-stu-id="37404-121">Whether `T` is a reference type or a value type.</span></span>
- <span data-ttu-id="37404-122">`T`이 값 형식인 경우 숫자 값인지 구조체인지 여부를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="37404-122">If `T` is a value type, whether it's a numeric value or a struct.</span></span>

 <span data-ttu-id="37404-123">매개 변수가 있는 형식 `T`의 변수 `t`가 제공되었을 때 `t = null` 문은 `T`가 참조 형식인 경우에만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="37404-123">Given a variable `t` of a parameterized type `T`, the statement `t = null` is only valid if `T` is a reference type.</span></span> <span data-ttu-id="37404-124">할당 `t = 0`은 숫자 값 형식에만 작동하고 구조체에는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37404-124">The assignment `t = 0` only works for numeric value types but not for structs.</span></span> <span data-ttu-id="37404-125">이를 해결하려면 기본값 식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="37404-125">To solve that, use a default value expression:</span></span>

```csharp
T t = default(T);
```

<span data-ttu-id="37404-126">`default(T)` 식은 제네릭 클래스와 메서드로 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37404-126">The `default(T)` expression is not limited to generic classes and methods.</span></span> <span data-ttu-id="37404-127">기본값 식은 모든 관리되는 형식과 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37404-127">Default value expressions can be used with any managed type.</span></span> <span data-ttu-id="37404-128">이러한 식은 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="37404-128">Any of these expressions are valid:</span></span>

 [!code-csharp[csProgGuideGenerics#1](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-value-expressions.cs)]

 <span data-ttu-id="37404-129">`GenericList<T>` 클래스에 있는 다음 예제에서는 제네릭 클래스에서 `default(T)` 연산자를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="37404-129">The following example from the `GenericList<T>` class shows how to use the `default(T)` operator in a generic class.</span></span> <span data-ttu-id="37404-130">자세한 내용은 [제네릭 소개](../generics/introduction-to-generics.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="37404-130">For more information, see [Introduction to Generics](../generics/introduction-to-generics.md).</span></span>

 [!code-csharp[csProgGuideGenerics#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#Snippet41)]

## <a name="default-literal-and-type-inference"></a><span data-ttu-id="37404-131">기본 리터럴 및 형식 유추</span><span class="sxs-lookup"><span data-stu-id="37404-131">default literal and type inference</span></span>

<span data-ttu-id="37404-132">C# 7.1부터 컴파일러에서 식의 형식을 유추할 수 있을 때 기본값 식에 대해 `default` 리터럴을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37404-132">Beginning with C# 7.1, the `default` literal can be used for default value expressions when the compiler can infer the type of the expression.</span></span> <span data-ttu-id="37404-133">`default` 리터럴은 `T`가 유추된 형식인 경우 해당 `default(T)`와 동일한 값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="37404-133">The `default` literal produces the same value as the equivalent `default(T)` where `T` is the inferred type.</span></span> <span data-ttu-id="37404-134">그러면 형식 선언의 중복성을 두 번 이상 줄여 코드가 더 간결해집니다.</span><span class="sxs-lookup"><span data-stu-id="37404-134">This can make code more concise by reducing the redundancy of declaring a type more than once.</span></span> <span data-ttu-id="37404-135">`default` 리터럴은 다음 위치에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37404-135">The `default` literal can be used in any of the following locations:</span></span>

- <span data-ttu-id="37404-136">변수 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="37404-136">variable initializer</span></span>
- <span data-ttu-id="37404-137">변수 대입</span><span class="sxs-lookup"><span data-stu-id="37404-137">variable assignment</span></span>
- <span data-ttu-id="37404-138">선택적 매개 변수의 기본값 선언</span><span class="sxs-lookup"><span data-stu-id="37404-138">declaring the default value for an optional parameter</span></span>
- <span data-ttu-id="37404-139">메서드 호출 인수에 대한 값 제공</span><span class="sxs-lookup"><span data-stu-id="37404-139">providing the value for a method call argument</span></span>
- <span data-ttu-id="37404-140">문(또는 식 본문 멤버의 식) 반환</span><span class="sxs-lookup"><span data-stu-id="37404-140">return statement (or expression in an expression bodied member)</span></span>

<span data-ttu-id="37404-141">다음 예제에서는 기본값 식에서 많은 `default` 리터럴 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="37404-141">The following example shows many usages of the `default` literal in a default value expression:</span></span>

[!code-csharp[csProgGuideGenerics#3](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-literal.cs)]

## <a name="see-also"></a><span data-ttu-id="37404-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="37404-142">See also</span></span>

 <xref:System.Collections.Generic>  
 [<span data-ttu-id="37404-143">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="37404-143">C# Programming Guide</span></span>](../index.md)  
 [<span data-ttu-id="37404-144">제네릭(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="37404-144">Generics (C# Programming Guide)</span></span>](../generics/index.md)  
 [<span data-ttu-id="37404-145">제네릭 메서드</span><span class="sxs-lookup"><span data-stu-id="37404-145">Generic Methods</span></span>](../generics/generic-methods.md)  
 [<span data-ttu-id="37404-146">.NET의 제네릭</span><span class="sxs-lookup"><span data-stu-id="37404-146">Generics in .NET</span></span>](~/docs/standard/generics/index.md)  
 [<span data-ttu-id="37404-147">기본값 표</span><span class="sxs-lookup"><span data-stu-id="37404-147">Default values table</span></span>](../../language-reference/keywords/default-values-table.md)
