---
title: "|| 연산자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '||_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
caps.latest.revision: 25
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
ms.openlocfilehash: 57bcb25b0d453fa59855f40c3189eb4af2bb8b7f
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="9a5ff-102">|| 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="9a5ff-102">|| Operator (C# Reference)</span></span>
<span data-ttu-id="9a5ff-103">조건부 OR 연산자(`||`)는 해당 `bool` 피연산자의 논리적 OR을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5ff-103">The conditional-OR operator (`||`) performs a logical-OR of its `bool` operands.</span></span> <span data-ttu-id="9a5ff-104">첫 번째 피연산자가 `true`이면 두 번째 피연산자는 계산되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9a5ff-104">If the first operand evaluates to `true`, the second operand isn't evaluated.</span></span> <span data-ttu-id="9a5ff-105">첫 번째 피연산자가 `false`이면 두 번째 피연산자에 의해 OR 식 전체가 `true` 또는 `false`인지가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a5ff-105">If the first operand evaluates to `false`, the second operator determines whether the OR expression as a whole evaluates to `true` or `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a5ff-106">설명</span><span class="sxs-lookup"><span data-stu-id="9a5ff-106">Remarks</span></span>  
 <span data-ttu-id="9a5ff-107">이 작업은</span><span class="sxs-lookup"><span data-stu-id="9a5ff-107">The operation</span></span>  
  
```  
x || y  
```  
  
 <span data-ttu-id="9a5ff-108">연산에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5ff-108">corresponds to the operation</span></span>  
  
```  
x | y  
```  
  
 <span data-ttu-id="9a5ff-109">단, `x`가 `true`이면 `y`는 평가되지 않습니다. `y` 값과 관계없이 OR 연산이 `true`이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="9a5ff-109">except that if `x` is `true`, `y` is not evaluated because the OR operation is `true` regardless of the value of `y`.</span></span> <span data-ttu-id="9a5ff-110">이 개념을 “단락” 평가라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5ff-110">This concept is known as "short-circuit" evaluation.</span></span>  
  
 <span data-ttu-id="9a5ff-111">조건부 OR 연산자는 오버로드될 수 없지만 일반 논리 연산자와 [true](../../../csharp/language-reference/keywords/true.md) 및 [false](../../../csharp/language-reference/keywords/false.md) 연산자의 오버로드는 조건부 논리 연산자의 오버로드로 간주합니다(특정 제한 사항 있음).</span><span class="sxs-lookup"><span data-stu-id="9a5ff-111">The conditional-OR operator cannot be overloaded, but overloads of the regular logical operators and the [true](../../../csharp/language-reference/keywords/true.md) and [false](../../../csharp/language-reference/keywords/false.md) operators are, with certain restrictions, also considered to be overloads of the conditional logical operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a5ff-112">예제</span><span class="sxs-lookup"><span data-stu-id="9a5ff-112">Example</span></span>  
 <span data-ttu-id="9a5ff-113">다음 예제에서 `||`를 사용하는 식은 첫 번째 피연산자만 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5ff-113">In the following examples, the expression that uses `||` evaluates only the first operand.</span></span> <span data-ttu-id="9a5ff-114">`|`를 사용하는 식은 두 피연산자를 모두 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5ff-114">The expression that uses `|` evaluates both operands.</span></span> <span data-ttu-id="9a5ff-115">두 번째 예제에서 두 피연산자가 모두 계산되면 런타임 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9a5ff-115">In the second example, a run-time exception occurs if both operands are evaluated.</span></span>  
  
 <span data-ttu-id="9a5ff-116">[!code-cs[csRefOperators#52](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-or-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9a5ff-116">[!code-cs[csRefOperators#52](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-or-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a5ff-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a5ff-117">See Also</span></span>  
 <span data-ttu-id="9a5ff-118">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="9a5ff-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="9a5ff-119">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9a5ff-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="9a5ff-120">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="9a5ff-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

