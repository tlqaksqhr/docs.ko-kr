---
title: "&gt; 연산자(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '>_CSharpKeyword'
helpviewer_keywords:
- '> operator [C#]'
- greater than operator (>) [C#]
ms.assetid: 26d3cb69-9c0b-4cc5-858b-5be1abd6659d
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: fc7c173ecc97bd3ca3b76a92ccbabc0f40062ac7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="6c478-102">&gt; 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="6c478-102">&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="6c478-103">모든 숫자 형식과 열거형은 첫 번째 피연산자가 두 번째 피연산자보다 크면 `true`를 반환하고 그렇지 않으면 `false`를 반환하는 “보다 큼” 관계 연산자(`>`)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6c478-103">All numeric and enumeration types define a "greater than" relational operator (`>`) that returns `true` if the first operand is greater than the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c478-104">설명</span><span class="sxs-lookup"><span data-stu-id="6c478-104">Remarks</span></span>  
 <span data-ttu-id="6c478-105">사용자 정의 형식은 `>` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="6c478-105">User-defined types can overload the `>` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="6c478-106">`>` 연산자가 오버로드되면 [<](../../../csharp/language-reference/operators/less-than-operator.md) 또한 오버로드되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c478-106">If `>` is overloaded, [<](../../../csharp/language-reference/operators/less-than-operator.md) must also be overloaded.</span></span> <span data-ttu-id="6c478-107">이항 연산자가 오버로드되면 해당 대입 연산자도 암시적으로 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c478-107">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c478-108">예제</span><span class="sxs-lookup"><span data-stu-id="6c478-108">Example</span></span>  
 [!code-csharp[csRefOperators#29](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="6c478-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6c478-109">See Also</span></span>  
 [<span data-ttu-id="6c478-110">C# 참조</span><span class="sxs-lookup"><span data-stu-id="6c478-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="6c478-111">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="6c478-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6c478-112">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="6c478-112">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="6c478-113">explicit</span><span class="sxs-lookup"><span data-stu-id="6c478-113">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)
