---
title: '% 연산자(C# 참조)'
ms.date: 04/04/2018
f1_keywords:
- '%_CSharpKeyword'
helpviewer_keywords:
- remainder operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
ms.openlocfilehash: b906feb22aaec97e58da562b615baae01f3e0719
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33271075"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="b095b-102">% 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="b095b-102">% Operator (C# Reference)</span></span>
<span data-ttu-id="b095b-103">나머지 연산자(`%`)는 첫 번째 피연산자를 두 번째 피연산자로 나눈 후 나머지를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="b095b-103">The remainder operator (`%`) computes the remainder after dividing its first operand by its second.</span></span> <span data-ttu-id="b095b-104">모든 숫자 형식에는 미리 정의된 나머지 연산자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b095b-104">All numeric types have predefined remainder operators.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="b095b-105">설명</span><span class="sxs-lookup"><span data-stu-id="b095b-105">Remarks</span></span>  
 <span data-ttu-id="b095b-106">`a % b` 수식은 항상 `(-b, b)` 범위로만 값을 반환하고(`b` 또는 `-b`를 반환할 수 없음) 피제수의 부호를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="b095b-106">The formula `a % b` will always return a value on the range `(-b, b)`, exclusive (it can never return `b` or `-b`), keeping the sign of the dividend.</span></span> <span data-ttu-id="b095b-107">정수 나누기의 경우 나머지 연산자는 `a % b = a - (a / b) * b` 규칙을 충족합니다.</span><span class="sxs-lookup"><span data-stu-id="b095b-107">For integer division, the remainder operator satisfies the rule `a % b = a - (a / b) * b`.</span></span>
  
 <span data-ttu-id="b095b-108">이는 유사한 규칙을 충족하지만 정수 나누기를 사용하고 `[0, b)` 범위의 값을 반환하는 정식 모듈러스와 혼동하지 않기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b095b-108">This is not to be confused with canonical modulus, which satisfies a similar rule but with floored division and returns values on the range `[0, b)`.</span></span> <span data-ttu-id="b095b-109">C#에는 정식 모듈러스에 대한 연산자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b095b-109">C# does not have an operator for canonical modulus.</span></span> <span data-ttu-id="b095b-110">그러나 양의 피제수에 대한 동작은 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="b095b-110">However, the behavior is the same for positive dividends.</span></span>
  
 <span data-ttu-id="b095b-111">사용자 정의 형식은 `%` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="b095b-111">User-defined types can overload the `%` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="b095b-112">이항 연산자가 오버로드되면 해당 대입 연산자도 암시적으로 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="b095b-112">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b095b-113">예</span><span class="sxs-lookup"><span data-stu-id="b095b-113">Example</span></span>  
 [!code-csharp[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/CSharp/remainder-operator_1.cs)]  
  
## <a name="comments"></a><span data-ttu-id="b095b-114">설명</span><span class="sxs-lookup"><span data-stu-id="b095b-114">Comments</span></span>  
 <span data-ttu-id="b095b-115">double 형식과 연결된 반올림 오류를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b095b-115">Note the round-off errors associated with the double type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b095b-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b095b-116">See Also</span></span>  
 [<span data-ttu-id="b095b-117">C# 참조</span><span class="sxs-lookup"><span data-stu-id="b095b-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="b095b-118">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="b095b-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b095b-119">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="b095b-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
