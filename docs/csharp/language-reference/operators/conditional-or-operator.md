---
title: '|| 연산자(C# 참조)'
ms.date: 07/20/2015
f1_keywords:
- '||_CSharpKeyword'
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
ms.openlocfilehash: d22e57d097edb0fe52b604e9c6431e167c410f0b
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171808"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="b2ff6-102">|| 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="b2ff6-102">|| Operator (C# Reference)</span></span>
<span data-ttu-id="b2ff6-103">조건부 OR 연산자(`||`)는 해당 `bool` 피연산자의 논리적 OR을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ff6-103">The conditional-OR operator (`||`) performs a logical-OR of its `bool` operands.</span></span> <span data-ttu-id="b2ff6-104">첫 번째 피연산자가 `true`이면 두 번째 피연산자는 계산되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b2ff6-104">If the first operand evaluates to `true`, the second operand isn't evaluated.</span></span> <span data-ttu-id="b2ff6-105">첫 번째 피연산자가 `false`이면 두 번째 피연산자에 의해 OR 식 전체가 `true` 또는 `false`인지가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2ff6-105">If the first operand evaluates to `false`, the second operator determines whether the OR expression as a whole evaluates to `true` or `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2ff6-106">설명</span><span class="sxs-lookup"><span data-stu-id="b2ff6-106">Remarks</span></span>  
 <span data-ttu-id="b2ff6-107">이 작업은</span><span class="sxs-lookup"><span data-stu-id="b2ff6-107">The operation</span></span>  
  
```csharp  
x || y  
```  
  
 <span data-ttu-id="b2ff6-108">연산에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ff6-108">corresponds to the operation</span></span>  
  
```csharp  
x | y  
```  
  
 <span data-ttu-id="b2ff6-109">단, `x`가 `true`이면 `y`는 평가되지 않습니다. `y` 값과 관계없이 OR 연산이 `true`이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="b2ff6-109">except that if `x` is `true`, `y` is not evaluated because the OR operation is `true` regardless of the value of `y`.</span></span> <span data-ttu-id="b2ff6-110">이 개념을 “단락” 평가라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ff6-110">This concept is known as "short-circuit" evaluation.</span></span>  
  
 <span data-ttu-id="b2ff6-111">조건부 OR 연산자는 오버로드될 수 없지만 일반 논리 연산자와 [true](../../../csharp/language-reference/keywords/true.md) 및 [false](../../../csharp/language-reference/keywords/false.md) 연산자의 오버로드는 조건부 논리 연산자의 오버로드로 간주합니다(특정 제한 사항 있음).</span><span class="sxs-lookup"><span data-stu-id="b2ff6-111">The conditional-OR operator cannot be overloaded, but overloads of the regular logical operators and the [true](../../../csharp/language-reference/keywords/true.md) and [false](../../../csharp/language-reference/keywords/false.md) operators are, with certain restrictions, also considered to be overloads of the conditional logical operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2ff6-112">예</span><span class="sxs-lookup"><span data-stu-id="b2ff6-112">Example</span></span>  
 <span data-ttu-id="b2ff6-113">다음 예제에서 `||`를 사용하는 식은 첫 번째 피연산자만 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ff6-113">In the following examples, the expression that uses `||` evaluates only the first operand.</span></span> <span data-ttu-id="b2ff6-114">`|`를 사용하는 식은 두 피연산자를 모두 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ff6-114">The expression that uses `|` evaluates both operands.</span></span> <span data-ttu-id="b2ff6-115">두 번째 예제에서 두 피연산자가 모두 계산되면 런타임 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ff6-115">In the second example, a run-time exception occurs if both operands are evaluated.</span></span>  
  
 [!code-csharp[csRefOperators#52](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-or-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="b2ff6-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2ff6-116">See Also</span></span>  
 [<span data-ttu-id="b2ff6-117">C# 참조</span><span class="sxs-lookup"><span data-stu-id="b2ff6-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="b2ff6-118">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="b2ff6-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b2ff6-119">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="b2ff6-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
