---
title: '&amp;&amp; 연산자(C# 참조)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '&&_CSharpKeyword'
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 16bc2fa650031d2b1f6cfaf7d128ba487963f707
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ampamp-operator-c-reference"></a><span data-ttu-id="e703f-102">&amp;&amp; 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="e703f-102">&amp;&amp; Operator (C# Reference)</span></span>
<span data-ttu-id="e703f-103">조건부 AND 연산자(`&&`)는 `bool` 피연산자의 논리적 AND를 수행하지만 필요할 경우 두 번째 피연산자만 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="e703f-103">The conditional-AND operator (`&&`) performs a logical-AND of its `bool` operands, but only evaluates its second operand if necessary.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e703f-104">주의</span><span class="sxs-lookup"><span data-stu-id="e703f-104">Remarks</span></span>  
 <span data-ttu-id="e703f-105">이 작업은</span><span class="sxs-lookup"><span data-stu-id="e703f-105">The operation</span></span>  
  
```  
x && y  
```  
  
 <span data-ttu-id="e703f-106">연산에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="e703f-106">corresponds to the operation</span></span>  
  
```  
x & y  
```  
  
 <span data-ttu-id="e703f-107">단, `x`가 `false`일 경우 `y`는 계산되지 않습니다. `y` 값이 무엇이든지 AND 연산의 결과는 `false`이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="e703f-107">except that if `x` is `false`, `y` is not evaluated, because the result of the AND operation is `false` no matter what the value of `y`  is.</span></span> <span data-ttu-id="e703f-108">이것을 "단락" 계산이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e703f-108">This is known as "short-circuit" evaluation.</span></span>  
  
 <span data-ttu-id="e703f-109">조건부 AND 연산자는 오버로드될 수 없지만 일반 논리 연산자와 [true](../../../csharp/language-reference/keywords/true.md) 및 [false](../../../csharp/language-reference/keywords/false.md) 연산자의 오버로드는 조건부 논리 연산자의 오버로드로 간주합니다(특정 제한 사항 있음).</span><span class="sxs-lookup"><span data-stu-id="e703f-109">The conditional-AND operator cannot be overloaded, but overloads of the regular logical operators and operators [true](../../../csharp/language-reference/keywords/true.md) and [false](../../../csharp/language-reference/keywords/false.md) are, with certain restrictions, also considered overloads of the conditional logical operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e703f-110">예제</span><span class="sxs-lookup"><span data-stu-id="e703f-110">Example</span></span>  
 <span data-ttu-id="e703f-111">다음 예제에서는 피연산자가 `false`를 반환하므로 두 번째 `if` 문의 조건식은 첫 번째 피연산자만 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="e703f-111">In the following example, the conditional expression in the second `if` statement evaluates only the first operand because the operand returns `false`.</span></span>  
  
 [!code-csharp[csRefOperators#48](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-and-operator_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="e703f-112">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="e703f-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e703f-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e703f-113">See Also</span></span>  
 [<span data-ttu-id="e703f-114">C# 참조</span><span class="sxs-lookup"><span data-stu-id="e703f-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e703f-115">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="e703f-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e703f-116">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="e703f-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
