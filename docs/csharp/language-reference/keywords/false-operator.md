---
title: false 연산자(C# 참조)
ms.date: 07/20/2015
helpviewer_keywords:
- false operator keyword [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
ms.openlocfilehash: e1c6da604f35031dd9d712125356243e1735f452
ms.sourcegitcommit: f9e38d31288fe5962e6be5b0cc286da633482873
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37027839"
---
# <a name="false-operator-c-reference"></a><span data-ttu-id="f2521-102">false 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="f2521-102">false operator (C# Reference)</span></span>

<span data-ttu-id="f2521-103">[bool](bool.md) 값 `true`를 반환하여 피연산자가 `false`임을 나타내고, false가 아니면 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f2521-103">Returns the [bool](bool.md) value `true` to indicate that an operand is `false` and returns `false` otherwise.</span></span>

<span data-ttu-id="f2521-104">C# 2.0 이전에는 `true` 및 `false` 연산자를 사용하여 `SqlBool` 등의 형식과 호환되는 사용자 정의 nullable 값 형식을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="f2521-104">Prior to C# 2.0, the `true` and `false` operators were used to create user-defined nullable value types that were compatible with types such as `SqlBool`.</span></span> <span data-ttu-id="f2521-105">그러나 이제 언어에서 nullable 값 형식에 대한 기본 제공 지원을 제공하며, 가능한 한 `true` 및 `false` 연산자를 오버로드하는 대신 이러한 형식을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2521-105">However, the language now provides built-in support for nullable value types, and whenever possible you should use those instead of overloading the `true` and `false` operators.</span></span> <span data-ttu-id="f2521-106">자세한 내용은 [Nullable 형식](../../programming-guide/nullable-types/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f2521-106">For more information, see [Nullable Types](../../programming-guide/nullable-types/index.md).</span></span>

<span data-ttu-id="f2521-107">nullable 부울을 사용하는 경우 하나 또는 두 값이 모두 null일 수 있기 때문에 `a != b` 식이 `!(a == b)`와 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2521-107">With nullable Booleans, the expression `a != b` is not necessarily equal to `!(a == b)` because one or both of the values might be null.</span></span> <span data-ttu-id="f2521-108">식에서 null 값을 올바르게 처리하려면 `true` 및 `false` 연산자를 별도로 둘 다 오버로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2521-108">You have to overload both the `true` and `false` operators separately to correctly handle the null values in the expression.</span></span> <span data-ttu-id="f2521-109">다음 예제에서는 `true` 및 `false` 연산자를 오버로드하고 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f2521-109">The following example shows how to overload and use the `true` and `false` operators.</span></span>

[!code-csharp[csrefKeywordsOperator#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#16)]

<span data-ttu-id="f2521-110">[if](if-else.md), [do](do.md), [while](while.md) 및 [for](for.md) 문의 제어 식과 [조건식](../operators/conditional-operator.md)에서 `true` 및 `false` 연산자를 오버로드하는 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2521-110">A type that overloads the `true` and `false` operators can be used for the controlling expression in [if](if-else.md), [do](do.md), [while](while.md), and [for](for.md) statements and in [conditional expressions](../operators/conditional-operator.md).</span></span>

<span data-ttu-id="f2521-111">형식이 `false` 연산자를 정의하는 경우 [true](true.md) 연산자도 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2521-111">If a type defines operator `false`, it must also define operator [true](true.md).</span></span>

<span data-ttu-id="f2521-112">형식에서 직접 조건부 논리 연산자([&&](../operators/conditional-and-operator.md) 및 [&#124;&#124;](../operators/conditional-or-operator.md))를 오버로드할 수는 없지만 일반 논리 연산자와 `true` 및 `false` 연산자를 오버로드하면 동일한 효과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2521-112">A type cannot directly overload the conditional logical operators [&&](../operators/conditional-and-operator.md) and [&#124;&#124;](../operators/conditional-or-operator.md), but an equivalent effect can be achieved by overloading the regular logical operators and operators `true` and `false`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f2521-113">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="f2521-113">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f2521-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f2521-114">See also</span></span>

[<span data-ttu-id="f2521-115">C# 참조</span><span class="sxs-lookup"><span data-stu-id="f2521-115">C# Reference</span></span>](../index.md)  
[<span data-ttu-id="f2521-116">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="f2521-116">C# Programming Guide</span></span>](../../programming-guide/index.md)  
[<span data-ttu-id="f2521-117">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="f2521-117">C# Keywords</span></span>](index.md)  
[<span data-ttu-id="f2521-118">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="f2521-118">C# Operators</span></span>](../operators/index.md)  
[<span data-ttu-id="f2521-119">true</span><span class="sxs-lookup"><span data-stu-id="f2521-119">true</span></span>](true.md)  