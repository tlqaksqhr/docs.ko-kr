---
title: "기본값 식(C# 프로그래밍 가이드)"
description: "기본값 식은 참조 형식 또는 값 형식에 대해 기본값을 생성합니다."
ms.date: 08/23/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- generics [C#], default keyword
- default keyword [C#], generic programming
ms.assetid: b9daf449-4e64-496e-8592-6ed2c8875a98
caps.latest.revision: "22"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c2bb1c269e5347d615c47ab828506aef538c4761
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="default-value-expressions-c-programming-guide"></a><span data-ttu-id="b49f9-103">기본값 식(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="b49f9-103">default value expressions (C# programming guide)</span></span>

<span data-ttu-id="b49f9-104">기본값 식은 형식의 기본값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b49f9-104">A default value expression produces the default value for a type.</span></span> <span data-ttu-id="b49f9-105">기본값 식은 특히 제네릭 클래스와 메서드에서 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="b49f9-105">Default value expressions are particularly useful in generic classes and methods.</span></span> <span data-ttu-id="b49f9-106">제네릭 사용으로 발생하는 한 가지 문제는 다음과 같은 내용을 미리 알지 못하는 경우 매개 변수가 있는 형식 `T`에 기본값을 할당하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="b49f9-106">One issue that arises using generics is how to assign a default value to a parameterized type `T` when you do not know the following in advance:</span></span>

- <span data-ttu-id="b49f9-107">`T`가 참조 형식인지 값 형식인지 여부</span><span class="sxs-lookup"><span data-stu-id="b49f9-107">Whether `T` is a reference type or a value type.</span></span>
- <span data-ttu-id="b49f9-108">`T`가 값 형식인 경우 숫자 값인지 사용자 정의 구조체인지 여부</span><span class="sxs-lookup"><span data-stu-id="b49f9-108">If `T` is a value type, whether is a numeric value or a user-defined struct.</span></span>

 <span data-ttu-id="b49f9-109">매개 변수가 있는 형식 `T`의 변수 `t`가 제공되었을 때 `t = null` 문은 `T`가 참조 형식인 경우에만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="b49f9-109">Given a variable `t` of a parameterized type `T`, the statement `t = null` is only valid if `T` is a reference type.</span></span> <span data-ttu-id="b49f9-110">할당 `t = 0`은 숫자 값 형식에만 작동하고 구조체에는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b49f9-110">The assignment `t = 0` only works for numeric value types but not for structs.</span></span> <span data-ttu-id="b49f9-111">해결 방법은 참조 형식(클래스 형식 및 인터페이스 형식)에 대해 `null`을 반환하고 숫자 값 형식에 대해 0을 반환하는 기본값 식을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b49f9-111">The solution is to use a default value expression, which returns `null` for reference types (class types and interface types) and zero for numeric value types.</span></span> <span data-ttu-id="b49f9-112">사용자 정의 구조체의 경우 해당 멤버가 값인지 참조 형식인지에 따라 각 멤버에 대해 0 또는 `null`을 생성하는 0비트 패턴으로 초기화된 구조체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b49f9-112">For user-defined structs, it returns the struct initialized to the zero bit pattern, which produces 0 or `null` for each member depending on whether that member is a value or reference type.</span></span> <span data-ttu-id="b49f9-113">Nullable 값 형식의 경우, `default`는 <xref:System.Nullable%601?displayProperty=nameWithType>을 반환하며 이는 여느 구조체와 마찬가지로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b49f9-113">For nullable value types, `default` returns a <xref:System.Nullable%601?displayProperty=nameWithType>, which is initialized like any struct.</span></span>

<span data-ttu-id="b49f9-114">`default(T)` 식은 제네릭 클래스와 메서드로 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b49f9-114">The `default(T)` expression is not limited to generic classes and methods.</span></span> <span data-ttu-id="b49f9-115">기본값 식은 모든 관리되는 형식과 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b49f9-115">Default value expressions can be used with any managed type.</span></span> <span data-ttu-id="b49f9-116">이러한 식은 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="b49f9-116">Any of these expressions are valid:</span></span>

 [!code-csharp[csProgGuideGenerics#1](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-value-expressions.cs)]

 <span data-ttu-id="b49f9-117">`GenericList<T>` 클래스에 있는 다음 예제에서는 제네릭 클래스에서 `default(T)` 연산자를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b49f9-117">The following example from the `GenericList<T>` class shows how to use the `default(T)` operator in a generic class.</span></span> <span data-ttu-id="b49f9-118">자세한 내용은 [제네릭 개요](../generics/introduction-to-generics.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b49f9-118">For more information, see [Generics Overview](../generics/introduction-to-generics.md).</span></span>

 [!code-csharp[csProgGuideGenerics#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#Snippet41)]

## <a name="default-literal-and-type-inference"></a><span data-ttu-id="b49f9-119">기본 리터럴 및 형식 유추</span><span class="sxs-lookup"><span data-stu-id="b49f9-119">default literal and type inference</span></span>

<span data-ttu-id="b49f9-120">C# 7.1부터 컴파일러에서 식의 형식을 유추할 수 있을 때 기본값 식에 대해 `default` 리터럴을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b49f9-120">Beginning with C# 7.1, the `default` literal can be used for default value expressions when the compiler can infer the type of the expression.</span></span> <span data-ttu-id="b49f9-121">`default` 리터럴은 `T`가 유추된 형식인 경우 해당 `default(T)`와 동일한 값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b49f9-121">The `default` literal produces the same value as the equivalent `default(T)` where `T` is the inferred type.</span></span> <span data-ttu-id="b49f9-122">그러면 형식 선언의 중복성을 두 번 이상 줄여 코드가 더 간결해집니다.</span><span class="sxs-lookup"><span data-stu-id="b49f9-122">This can make code more concise by reducing the redundancy of declaring a type more than once.</span></span> <span data-ttu-id="b49f9-123">`default` 리터럴은 다음 위치에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b49f9-123">The `default` literal can be used in any of the following locations:</span></span>

- <span data-ttu-id="b49f9-124">변수 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="b49f9-124">variable initializer</span></span>
- <span data-ttu-id="b49f9-125">변수 대입</span><span class="sxs-lookup"><span data-stu-id="b49f9-125">variable assignment</span></span>
- <span data-ttu-id="b49f9-126">선택적 매개 변수의 기본값 선언</span><span class="sxs-lookup"><span data-stu-id="b49f9-126">declaring the default value for an optional parameter</span></span>
- <span data-ttu-id="b49f9-127">메서드 호출 인수에 대한 값 제공</span><span class="sxs-lookup"><span data-stu-id="b49f9-127">providing the value for a method call argument</span></span>
- <span data-ttu-id="b49f9-128">문(또는 식 본문 멤버의 식) 반환</span><span class="sxs-lookup"><span data-stu-id="b49f9-128">return statement (or expression in an expression bodied member)</span></span>

<span data-ttu-id="b49f9-129">다음 예제에서는 기본값 식에서 많은 `default` 리터럴 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b49f9-129">The following example shows many usages of the `default` literal in a default value expression:</span></span>

[!code-csharp[csProgGuideGenerics#3](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-literal.cs)]

## <a name="see-also"></a><span data-ttu-id="b49f9-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b49f9-130">See also</span></span>

 <span data-ttu-id="b49f9-131"><xref:System.Collections.Generic>[C# 프로그래밍 가이드](../index.md)</span><span class="sxs-lookup"><span data-stu-id="b49f9-131"><xref:System.Collections.Generic> [C# Programming Guide](../index.md)</span></span>  
 [<span data-ttu-id="b49f9-132">제네릭</span><span class="sxs-lookup"><span data-stu-id="b49f9-132">Generics</span></span>](../generics/index.md)  
 [<span data-ttu-id="b49f9-133">제네릭 메서드</span><span class="sxs-lookup"><span data-stu-id="b49f9-133">Generic Methods</span></span>](../generics/generic-methods.md)  
 [<span data-ttu-id="b49f9-134">제네릭</span><span class="sxs-lookup"><span data-stu-id="b49f9-134">Generics</span></span>](~/docs/standard/generics/index.md)  
