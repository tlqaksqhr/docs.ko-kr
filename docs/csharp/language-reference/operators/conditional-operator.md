---
title: '?: 연산자(C# 참조)'
ms.date: 07/20/2015
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 68e7daac63a5f7d9bd1f48adfdee973bd695a13e
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457218"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="d842d-102">?: 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="d842d-102">?: Operator (C# Reference)</span></span>
<span data-ttu-id="d842d-103">일반적으로 3개로 구성된 조건 연산자로 알려진 조건 연산자(`?:`)는 부울 식의 값에 따라 두 값 중 하나를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d842d-103">The conditional operator (`?:`), commonly known as the ternary conditional operator, returns one of two values depending on the value of a Boolean expression.</span></span> <span data-ttu-id="d842d-104">다음은 조건 연산자의 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="d842d-104">Following is the syntax for the conditional operator.</span></span>  
  
```  
condition ? first_expression : second_expression;  
```  
  
## <a name="remarks"></a><span data-ttu-id="d842d-105">설명</span><span class="sxs-lookup"><span data-stu-id="d842d-105">Remarks</span></span>  
 <span data-ttu-id="d842d-106">`condition`은 `true` 또는 `false`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d842d-106">The `condition` must evaluate to `true` or `false`.</span></span> <span data-ttu-id="d842d-107">`condition`이 `true`인 경우 `first_expression`이 평가되고 결과가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d842d-107">If `condition` is `true`, `first_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="d842d-108">`condition`이 `false`인 경우 `second_expression`이 평가되고 결과가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d842d-108">If `condition` is `false`, `second_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="d842d-109">두 식 중 하나만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="d842d-109">Only one of the two expressions is evaluated.</span></span>  
  
 <span data-ttu-id="d842d-110">`first_expression` 및 `second_expression`의 형식이 동일하거나 한 형식에서 다른 형식으로 암시적 변환이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d842d-110">Either the type of `first_expression` and `second_expression` must be the same, or an implicit conversion must exist from one type to the other.</span></span>  
  
 <span data-ttu-id="d842d-111">조건 연산자를 사용하면 `if-else` 구성이 필요할 수 있는 계산을 더 간결하게 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d842d-111">You can express calculations that might otherwise require an `if-else` construction more concisely by using the conditional operator.</span></span> <span data-ttu-id="d842d-112">예를 들어, 다음 코드는 처음에 `if` 문을 사용한 다음 조건부 연산자를 사용하여 정수를 양 또는 음으로 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="d842d-112">For example, the following code uses first an `if` statement and then a conditional operator to classify an integer as positive or negative.</span></span>  
  
```csharp
int input = Convert.ToInt32(Console.ReadLine());  
string classify;  
  
// if-else construction.  
if (input > 0)  
    classify = "positive";  
else  
    classify = "negative";  
  
// ?: conditional operator.  
classify = (input > 0) ? "positive" : "negative";  
```  
  
 <span data-ttu-id="d842d-113">조건 연산자에는 오른쪽 결합성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d842d-113">The conditional operator is right-associative.</span></span> <span data-ttu-id="d842d-114">`a ? b : c ? d : e` 식은 `a ? b : (c ? d : e)`가 아닌 `(a ? b : c) ? d : e`로 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d842d-114">The expression `a ? b : c ? d : e` is evaluated as `a ? b : (c ? d : e)`, not as `(a ? b : c) ? d : e`.</span></span>  
  
 <span data-ttu-id="d842d-115">조건 연산자는 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d842d-115">The conditional operator cannot be overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d842d-116">예</span><span class="sxs-lookup"><span data-stu-id="d842d-116">Example</span></span>  
 [!code-csharp[csRefOperators#41](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="d842d-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d842d-117">See Also</span></span>  
 [<span data-ttu-id="d842d-118">C# 참조</span><span class="sxs-lookup"><span data-stu-id="d842d-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="d842d-119">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="d842d-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d842d-120">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="d842d-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="d842d-121">if-else</span><span class="sxs-lookup"><span data-stu-id="d842d-121">if-else</span></span>](../../../csharp/language-reference/keywords/if-else.md)  
 <span data-ttu-id="d842d-122">[?. 및 ?[] 연산자](../../../csharp/language-reference/operators/null-conditional-operators.md)</span><span class="sxs-lookup"><span data-stu-id="d842d-122">[?. and ?[] Operators](../../../csharp/language-reference/operators/null-conditional-operators.md)</span></span>  
 [<span data-ttu-id="d842d-123">?? 연산자</span><span class="sxs-lookup"><span data-stu-id="d842d-123">?? Operator</span></span>](../../../csharp/language-reference/operators/null-coalescing-operator.md)
