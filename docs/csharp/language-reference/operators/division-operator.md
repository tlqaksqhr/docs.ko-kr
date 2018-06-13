---
title: / 연산자(C# 참조)
ms.date: 04/04/2018
f1_keywords:
- /_CSharpKeyword
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
ms.openlocfilehash: 9d0bbff1fd9f4ab3c93c879d12ccd5fde1187b44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33272573"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="a465a-102">/ 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="a465a-102">/ Operator (C# Reference)</span></span>
<span data-ttu-id="a465a-103">나누기 연산자(`/`)는 두 번째 피연산자로 첫 번째 피연산자를 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="a465a-103">The division operator (`/`) divides its first operand by its second operand.</span></span> <span data-ttu-id="a465a-104">모든 숫자 형식에는 미리 정의된 나누기 연산자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a465a-104">All numeric types have predefined division operators.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="a465a-105">설명</span><span class="sxs-lookup"><span data-stu-id="a465a-105">Remarks</span></span>  
 <span data-ttu-id="a465a-106">사용자 정의 형식은 `/` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="a465a-106">User-defined types can overload the `/` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="a465a-107">`/` 연산자를 오버로드하면 [/= 연산자](division-assignment-operator.md)를 암시적으로 오버로드합니다.</span><span class="sxs-lookup"><span data-stu-id="a465a-107">An overload of the `/` operator implicitly overloads the [/= operator](division-assignment-operator.md).</span></span>  
  
 <span data-ttu-id="a465a-108">두 정수를 나누면 결과는 항상 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="a465a-108">When you divide two integers, the result is always an integer.</span></span> <span data-ttu-id="a465a-109">예를 들어 7 / 3의 결과는 2입니다.</span><span class="sxs-lookup"><span data-stu-id="a465a-109">For example, the result of 7 / 3 is 2.</span></span> <span data-ttu-id="a465a-110">이는 `/` 연산자가 0으로 반올림되므로(-7/3=-2) 정수 나누기와 혼동하지 않기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a465a-110">This is not to be confused with floored division, as the `/` operator rounds towards zero: -7 / 3 is -2.</span></span>  
  
 <span data-ttu-id="a465a-111">몫을 유리수로 구하려면 `float`, `double` 또는 `decimal` 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a465a-111">To obtain a quotient as a rational number, use the `float`, `double`, or `decimal` types.</span></span> <span data-ttu-id="a465a-112">[기본 제공 숫자 형식](../../../csharp/language-reference/keywords/reference-tables-for-types.md) 간에 변환하는 여러 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a465a-112">There are many ways to convert between [built in numeric types](../../../csharp/language-reference/keywords/reference-tables-for-types.md).</span></span>  
  
 <span data-ttu-id="a465a-113">나머지를 확인하려면 [나머지 연산자](../../../csharp/language-reference/operators/remainder-operator.md) `%`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a465a-113">To determine the remainder, use the [remainder operator](../../../csharp/language-reference/operators/remainder-operator.md) `%`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a465a-114">예</span><span class="sxs-lookup"><span data-stu-id="a465a-114">Example</span></span>  
 [!code-csharp[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="a465a-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a465a-115">See Also</span></span>  
 [<span data-ttu-id="a465a-116">C# 참조</span><span class="sxs-lookup"><span data-stu-id="a465a-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a465a-117">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="a465a-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a465a-118">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="a465a-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
