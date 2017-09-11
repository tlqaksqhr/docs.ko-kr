---
title: "기본값 식(C# 프로그래밍 가이드)"
description: "기본값 식은 참조 형식 또는 값 형식에 대해 기본값을 생성합니다."
ms.date: 2017-08-23
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- generics [C#], default keyword
- default keyword [C#], generic programming
ms.assetid: b9daf449-4e64-496e-8592-6ed2c8875a98
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 1e548df4de2c07934313311a7ffcfae82be76000
ms.openlocfilehash: 7b5b53d7ed92c6f6377a3e494daf1d02a4cf0934
ms.contentlocale: ko-kr
ms.lasthandoff: 08/29/2017

---
# <a name="default-value-expressions-c-programming-guide"></a><span data-ttu-id="db14c-103">기본값 식(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="db14c-103">default value expressions (C# programming guide)</span></span>

<span data-ttu-id="db14c-104">기본값 식은 형식의 기본값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="db14c-104">A default value expression produces the default value for a type.</span></span> <span data-ttu-id="db14c-105">기본값 식은 특히 제네릭 클래스와 메서드에서 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="db14c-105">Default value expressions are particularly useful in generic classes and methods.</span></span> <span data-ttu-id="db14c-106">제네릭 사용으로 발생하는 한 가지 문제는 다음과 같은 내용을 미리 알지 못하는 경우 매개 변수가 있는 형식 `T`에 기본값을 할당하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="db14c-106">One issue that arises using generics is how to assign a default value to a parameterized type `T` when you do not know the following in advance:</span></span>

- <span data-ttu-id="db14c-107">`T`가 참조 형식인지 값 형식인지 여부</span><span class="sxs-lookup"><span data-stu-id="db14c-107">Whether `T` is a reference type or a value type.</span></span>
- <span data-ttu-id="db14c-108">`T`가 값 형식인 경우 숫자 값인지 사용자 정의 구조체인지 여부</span><span class="sxs-lookup"><span data-stu-id="db14c-108">If `T` is a value type, whether is a numeric value or a user-defined struct.</span></span>

 <span data-ttu-id="db14c-109">매개 변수가 있는 형식 `T`의 변수 `t`가 제공되었을 때 `t = null` 문은 `T`가 참조 형식인 경우에만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="db14c-109">Given a variable `t` of a parameterized type `T`, the statement `t = null` is only valid if `T` is a reference type.</span></span> <span data-ttu-id="db14c-110">할당 `t = 0`은 숫자 값 형식에만 작동하고 구조체에는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db14c-110">The assignment `t = 0` only works for numeric value types but not for structs.</span></span> <span data-ttu-id="db14c-111">해결 방법은 참조 형식(클래스 형식 및 인터페이스 형식)에 대해 `null`을 반환하고 숫자 값 형식에 대해 0을 반환하는 기본값 식을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="db14c-111">The solution is to use a default value expression, which returns `null` for reference types (class types and interface types) and zero for numeric value types.</span></span> <span data-ttu-id="db14c-112">사용자 정의 구조체의 경우 해당 멤버가 값인지 참조 형식인지에 따라 각 멤버에 대해 0 또는 `null`을 생성하는 0비트 패턴으로 초기화된 구조체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="db14c-112">For user-defined structs, it returns the struct initialized to the zero bit pattern, which produces 0 or `null` for each member depending on whether that member is a value or reference type.</span></span> <span data-ttu-id="db14c-113">Nullable 값 형식의 경우, `default`는 <xref:System.Nullable%601?displayProperty=fullName>을 반환하며 이는 여느 구조체와 마찬가지로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="db14c-113">For nullable value types, `default` returns a <xref:System.Nullable%601?displayProperty=fullName>, which is initialized like any struct.</span></span>

<span data-ttu-id="db14c-114">`default(T)` 식은 제네릭 클래스와 메서드로 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db14c-114">The `default(T)` expression is not limited to generic classes and methods.</span></span> <span data-ttu-id="db14c-115">기본값 식은 모든 관리되는 형식과 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db14c-115">Default value expressions can be used with any managed type.</span></span> <span data-ttu-id="db14c-116">이러한 식은 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="db14c-116">Any of these expressions are valid:</span></span>

 <span data-ttu-id="db14c-117">[!code-cs[csProgGuideGenerics#1](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-value-expressions.cs)]</span><span class="sxs-lookup"><span data-stu-id="db14c-117">[!code-cs[csProgGuideGenerics#1](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-value-expressions.cs)]</span></span>

 <span data-ttu-id="db14c-118">`GenericList<T>` 클래스에 있는 다음 예제에서는 제네릭 클래스에서 `default(T)` 연산자를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="db14c-118">The following example from the `GenericList<T>` class shows how to use the `default(T)` operator in a generic class.</span></span> <span data-ttu-id="db14c-119">자세한 내용은 [제네릭 개요](../generics/introduction-to-generics.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="db14c-119">For more information, see [Generics Overview](../generics/introduction-to-generics.md).</span></span>

 <span data-ttu-id="db14c-120">[!code-cs[csProgGuideGenerics#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#Snippet41)]</span><span class="sxs-lookup"><span data-stu-id="db14c-120">[!code-cs[csProgGuideGenerics#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#Snippet41)]</span></span>

## <a name="default-literal-and-type-inference"></a><span data-ttu-id="db14c-121">기본 리터럴 및 형식 유추</span><span class="sxs-lookup"><span data-stu-id="db14c-121">default literal and type inference</span></span>

<span data-ttu-id="db14c-122">C# 7.1부터 컴파일러에서 식의 형식을 유추할 수 있을 때 기본값 식에 대해 `default` 리터럴을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db14c-122">Beginning with C# 7.1, the `default` literal can be used for default value expressions when the compiler can infer the type of the expression.</span></span> <span data-ttu-id="db14c-123">`default` 리터럴은 `T`가 유추된 형식인 경우 해당 `default(T)`와 동일한 값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="db14c-123">The `default` literal produces the same value as the equivalent `default(T)` where `T` is the inferred type.</span></span> <span data-ttu-id="db14c-124">그러면 형식 선언의 중복성을 두 번 이상 줄여 코드가 더 간결해집니다.</span><span class="sxs-lookup"><span data-stu-id="db14c-124">This can make code more concise by reducing the redundancy of declaring a type more than once.</span></span> <span data-ttu-id="db14c-125">`default` 리터럴은 다음 위치에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db14c-125">The `default` literal can be used in any of the following locations:</span></span>

- <span data-ttu-id="db14c-126">변수 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="db14c-126">variable initializer</span></span>
- <span data-ttu-id="db14c-127">변수 대입</span><span class="sxs-lookup"><span data-stu-id="db14c-127">variable assignment</span></span>
- <span data-ttu-id="db14c-128">선택적 매개 변수의 기본값 선언</span><span class="sxs-lookup"><span data-stu-id="db14c-128">declaring the default value for an optional parameter</span></span>
- <span data-ttu-id="db14c-129">메서드 호출 인수에 대한 값 제공</span><span class="sxs-lookup"><span data-stu-id="db14c-129">providing the value for a method call argument</span></span>
- <span data-ttu-id="db14c-130">문(또는 식 본문 멤버의 식) 반환</span><span class="sxs-lookup"><span data-stu-id="db14c-130">return statement (or expression in an expression bodied member)</span></span>

<span data-ttu-id="db14c-131">다음 예제에서는 기본값 식에서 많은 `default` 리터럴 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="db14c-131">The following example shows many usages of the `default` literal in a default value expression:</span></span>

<span data-ttu-id="db14c-132">[!code-cs[csProgGuideGenerics#3](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-literal.cs)]</span><span class="sxs-lookup"><span data-stu-id="db14c-132">[!code-cs[csProgGuideGenerics#3](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-literal.cs)]</span></span>

## <a name="see-also"></a><span data-ttu-id="db14c-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="db14c-133">See also</span></span>

 <span data-ttu-id="db14c-134"><xref:System.Collections.Generic> [C# 프로그래밍 가이드](../index.md) </span><span class="sxs-lookup"><span data-stu-id="db14c-134"><xref:System.Collections.Generic> [C# Programming Guide](../index.md) </span></span>  
 <span data-ttu-id="db14c-135">[제네릭](../generics/index.md) </span><span class="sxs-lookup"><span data-stu-id="db14c-135">[Generics](../generics/index.md) </span></span>  
 <span data-ttu-id="db14c-136">[제네릭 메서드](../generics/generic-methods.md) </span><span class="sxs-lookup"><span data-stu-id="db14c-136">[Generic Methods](../generics/generic-methods.md) </span></span>  
 [<span data-ttu-id="db14c-137">제네릭</span><span class="sxs-lookup"><span data-stu-id="db14c-137">Generics</span></span>](~/docs/standard/generics/index.md)   

