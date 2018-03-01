---
title: "% 연산자(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '%_CSharpKeyword'
helpviewer_keywords:
- modulus operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: cea4aa03424e93f3ec144126d73c63931a737b54
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="450f5-102">% 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="450f5-102">% Operator (C# Reference)</span></span>
<span data-ttu-id="450f5-103">`%` 연산자는 첫 번째 피연산자를 두 번째 피연산자로 나눈 후 나머지를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="450f5-103">The `%` operator computes the remainder after dividing its first operand by its second.</span></span> <span data-ttu-id="450f5-104">모든 숫자 형식에는 미리 정의된 나머지 연산자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="450f5-104">All numeric types have predefined remainder operators.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="450f5-105">설명</span><span class="sxs-lookup"><span data-stu-id="450f5-105">Remarks</span></span>  
 <span data-ttu-id="450f5-106">사용자 정의 형식은 `%` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="450f5-106">User-defined types can overload the `%` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="450f5-107">이항 연산자가 오버로드되면 해당 대입 연산자도 암시적으로 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="450f5-107">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="450f5-108">예제</span><span class="sxs-lookup"><span data-stu-id="450f5-108">Example</span></span>  
 [!code-csharp[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-operator_1.cs)]  
  
## <a name="comments"></a><span data-ttu-id="450f5-109">설명</span><span class="sxs-lookup"><span data-stu-id="450f5-109">Comments</span></span>  
 <span data-ttu-id="450f5-110">double 형식과 연결된 반올림 오류를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="450f5-110">Note the round-off errors associated with the double type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="450f5-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="450f5-111">See Also</span></span>  
 [<span data-ttu-id="450f5-112">C# 참조</span><span class="sxs-lookup"><span data-stu-id="450f5-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="450f5-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="450f5-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="450f5-114">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="450f5-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
