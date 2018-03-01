---
title: "true 연산자(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- true operator [C#]
ms.assetid: acaba817-5da5-4364-b3b2-2e5c75ec1839
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 96ab7679862959f3c99e31beac0bd5514228bd8d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="true-operator-c-reference"></a><span data-ttu-id="fa02d-102">true 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="fa02d-102">true Operator (C# Reference)</span></span>
<span data-ttu-id="fa02d-103">[bool](../../../csharp/language-reference/keywords/bool.md) 값 `true`를 반환하여 피연산자가 true임을 나타내고, true가 아니면 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fa02d-103">Returns the [bool](../../../csharp/language-reference/keywords/bool.md) value `true` to indicate that an operand is true and returns `false` otherwise.</span></span>  
  
 <span data-ttu-id="fa02d-104">C# 2.0 이전에는 `true` 및 `false` 연산자를 사용하여 `SqlBool` 등의 형식과 호환되는 사용자 정의 nullable 값 형식을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="fa02d-104">Prior to C# 2.0, the `true` and `false` operators were used to create user-defined nullable value types that were compatible with types such as `SqlBool`.</span></span> <span data-ttu-id="fa02d-105">그러나 이제 언어에서 nullable 값 형식에 대한 기본 제공 지원을 제공하며, 가능한 한 `true` 및 `false` 연산자를 오버로드하는 대신 이러한 형식을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa02d-105">However, the language now provides built-in support for nullable value types, and whenever possible you should use those instead of overloading the `true` and `false` operators.</span></span> <span data-ttu-id="fa02d-106">자세한 내용은 [Nullable 형식](../../../csharp/programming-guide/nullable-types/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa02d-106">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
 <span data-ttu-id="fa02d-107">nullable 부울을 사용하는 경우 하나 또는 두 값이 모두 null일 수 있기 때문에 `a != b` 식이 `!(a == b)`와 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa02d-107">With nullable Booleans, the expression `a != b` is not necessarily equal to `!(a == b)` because one or both of the values might be null.</span></span> <span data-ttu-id="fa02d-108">식에서 null 값을 올바르게 식별하려면 `true` 및 `false` 연산자를 별도로 둘 다 오버로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa02d-108">You need to overload both the `true` and `false` operators separately to correctly identify the null values in the expression.</span></span> <span data-ttu-id="fa02d-109">다음 예제에서는 `true` 및 `false` 연산자를 오버로드하고 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fa02d-109">The following example shows how to overload and use the `true` and `false` operators.</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/true-operator_1.cs)]  
  
 <span data-ttu-id="fa02d-110">[if](../../../csharp/language-reference/keywords/if-else.md), [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md) 및 [for](../../../csharp/language-reference/keywords/for.md) 문의 제어 식과 [조건식](../../../csharp/language-reference/operators/conditional-operator.md)에서 `true` 및 `false` 연산자를 오버로드하는 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa02d-110">A type that overloads the `true` and `false` operators can be used for the controlling expression in [if](../../../csharp/language-reference/keywords/if-else.md), [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md), and [for](../../../csharp/language-reference/keywords/for.md) statements and in [conditional expressions](../../../csharp/language-reference/operators/conditional-operator.md).</span></span>  
  
 <span data-ttu-id="fa02d-111">형식이 `true` 연산자를 정의하는 경우 [false](../../../csharp/language-reference/keywords/false.md) 연산자도 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa02d-111">If a type defines operator `true`, it must also define operator [false](../../../csharp/language-reference/keywords/false.md).</span></span>  
  
 <span data-ttu-id="fa02d-112">형식에서 직접 조건부 논리 연산자([&&](../../../csharp/language-reference/operators/conditional-and-operator.md) 및 [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md))를 오버로드할 수는 없지만 일반 논리 연산자와 `true` 및 `false` 연산자를 오버로드하면 동일한 효과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa02d-112">A type cannot directly overload the conditional logical operators ([&&](../../../csharp/language-reference/operators/conditional-and-operator.md) and [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md)), but an equivalent effect can be achieved by overloading the regular logical operators and operators `true` and `false`.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="fa02d-113">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="fa02d-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fa02d-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa02d-114">See Also</span></span>  
 [<span data-ttu-id="fa02d-115">C# 참조</span><span class="sxs-lookup"><span data-stu-id="fa02d-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="fa02d-116">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="fa02d-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="fa02d-117">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="fa02d-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="fa02d-118">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="fa02d-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="fa02d-119">false</span><span class="sxs-lookup"><span data-stu-id="fa02d-119">false</span></span>](../../../csharp/language-reference/keywords/false.md)
