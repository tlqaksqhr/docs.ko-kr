---
title: "/ 연산자(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /_CSharpKeyword
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9e12e5c472266ea75d3f572a2091bd0784ea5dcf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="fd4ec-102">/ 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="fd4ec-102">/ Operator (C# Reference)</span></span>
<span data-ttu-id="fd4ec-103">나누기 연산자(`/`)는 두 번째 피연산자로 첫 번째 피연산자를 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="fd4ec-103">The division operator (`/`) divides its first operand by its second operand.</span></span> <span data-ttu-id="fd4ec-104">모든 숫자 형식에는 미리 정의된 나누기 연산자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd4ec-104">All numeric types have predefined division operators.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd4ec-105">주의</span><span class="sxs-lookup"><span data-stu-id="fd4ec-105">Remarks</span></span>  
 <span data-ttu-id="fd4ec-106">사용자 정의 형식은 `/` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="fd4ec-106">User-defined types can overload the `/` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="fd4ec-107">`/` 연산자를 오버로드하면 [/= 연산자](division-assignment-operator.md)를 암시적으로 오버로드합니다.</span><span class="sxs-lookup"><span data-stu-id="fd4ec-107">An overload of the `/` operator implicitly overloads the [/= operator](division-assignment-operator.md).</span></span>  
  
 <span data-ttu-id="fd4ec-108">두 정수를 나누면 결과는 항상 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="fd4ec-108">When you divide two integers, the result is always an integer.</span></span> <span data-ttu-id="fd4ec-109">예를 들어 7 / 3의 결과는 2입니다.</span><span class="sxs-lookup"><span data-stu-id="fd4ec-109">For example, the result of 7 / 3 is 2.</span></span> <span data-ttu-id="fd4ec-110">7 / 3의 나머지를 확인하려면 나머지 연산자([%](../../../csharp/language-reference/operators/modulus-operator.md))를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fd4ec-110">To determine the remainder of 7 / 3, use the remainder operator ([%](../../../csharp/language-reference/operators/modulus-operator.md)).</span></span> <span data-ttu-id="fd4ec-111">유리수나 분수로 몫을 가져오려면 피제수나 제수를 `float` 또는 `double` 형식으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fd4ec-111">To obtain a quotient as a rational number or fraction, give the dividend or divisor type `float` or type `double`.</span></span> <span data-ttu-id="fd4ec-112">다음 예제와 같이 소수점 오른쪽에 숫자를 입력하여 피제수나 제수를 10진수로 표현하는 경우 형식을 암시적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd4ec-112">You can assign the type implicitly if you express the dividend or divisor as a decimal by putting a digit to the right side of the decimal point, as the following example shows.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd4ec-113">예제</span><span class="sxs-lookup"><span data-stu-id="fd4ec-113">Example</span></span>  
 [!code-csharp[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="fd4ec-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fd4ec-114">See Also</span></span>  
 [<span data-ttu-id="fd4ec-115">C# 참조</span><span class="sxs-lookup"><span data-stu-id="fd4ec-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="fd4ec-116">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="fd4ec-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="fd4ec-117">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="fd4ec-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
