---
title: '&gt;&gt; 연산자(C# 참조)'
ms.date: 07/20/2015
f1_keywords:
- '>>_CSharpKeyword'
helpviewer_keywords:
- '>> operator [C#]'
- right shift operator (>>) [C#]
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
ms.openlocfilehash: 061a69250ef5524fa6b5f7bb4b9527057dd86e05
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="gtgt-operator-c-reference"></a><span data-ttu-id="9e200-102">&gt;&gt; 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="9e200-102">&gt;&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="9e200-103">오른쪽 시프트 연산자(`>>`)는 첫 번째 피연산자를 두 번째 피연산자로 지정된 비트 수만큼 오른쪽으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9e200-103">The right-shift operator (`>>`) shifts its first operand right by the number of bits specified by its second operand.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e200-104">설명</span><span class="sxs-lookup"><span data-stu-id="9e200-104">Remarks</span></span>  
 <span data-ttu-id="9e200-105">첫 번째 피연산자가 [int](../../../csharp/language-reference/keywords/int.md) 또는 [uint](../../../csharp/language-reference/keywords/uint.md)(32비트 수량)이면 두 번째 피연산자의 하위 5비트(두 번째 피연산자 & 0x1f)로 시프트 수가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e200-105">If the first operand is an [int](../../../csharp/language-reference/keywords/int.md) or [uint](../../../csharp/language-reference/keywords/uint.md) (32-bit quantity), the shift count is given by the low-order five bits of the second operand (second operand & 0x1f).</span></span>  
  
 <span data-ttu-id="9e200-106">첫 번째 피연산자가 [long](../../../csharp/language-reference/keywords/long.md) 또는 [ulong](../../../csharp/language-reference/keywords/ulong.md)(64비트 수량)이면 두 번째 피연산자의 하위 6비트(두 번째 피연산자 & 0x3f)로 시프트 수가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e200-106">If the first operand is a [long](../../../csharp/language-reference/keywords/long.md) or [ulong](../../../csharp/language-reference/keywords/ulong.md) (64-bit quantity), the shift count is given by the low-order six bits of the second operand (second operand & 0x3f).</span></span>  
  
 <span data-ttu-id="9e200-107">첫 번째 피연산자가 [int](../../../csharp/language-reference/keywords/int.md) 또는 [long](../../../csharp/language-reference/keywords/long.md)이면 오른쪽 시프트는 산술 시프트입니다(비어 있는 상위 비트가 부호 비트로 설정됨).</span><span class="sxs-lookup"><span data-stu-id="9e200-107">If the first operand is an [int](../../../csharp/language-reference/keywords/int.md) or [long](../../../csharp/language-reference/keywords/long.md), the right-shift is an arithmetic shift (high-order empty bits are set to the sign bit).</span></span> <span data-ttu-id="9e200-108">첫 번째 피연산자가 [uint](../../../csharp/language-reference/keywords/uint.md) 또는 [ulong](../../../csharp/language-reference/keywords/ulong.md) 형식이면 오른쪽 시프트는 논리적 시프트입니다(상위 비트가 0으로 채워짐).</span><span class="sxs-lookup"><span data-stu-id="9e200-108">If the first operand is of type [uint](../../../csharp/language-reference/keywords/uint.md) or [ulong](../../../csharp/language-reference/keywords/ulong.md), the right-shift is a logical shift (high-order bits are zero-filled).</span></span>  
  
 <span data-ttu-id="9e200-109">사용자 정의 형식은 `>>` 연산자를 오버로드할 수 있습니다. 첫 번째 피연산자의 형식은 사용자 정의 형식이어야 하고 두 번째 피연산자의 형식은 [int](../../../csharp/language-reference/keywords/int.md)여야 합니다. 자세한 내용은 [operator](../../../csharp/language-reference/keywords/operator.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e200-109">User-defined types can overload the `>>` operator; the type of the first operand must be the user-defined type, and the type of the second operand must be [int](../../../csharp/language-reference/keywords/int.md). For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="9e200-110">이항 연산자가 오버로드되면 해당 대입 연산자도 암시적으로 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e200-110">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e200-111">예</span><span class="sxs-lookup"><span data-stu-id="9e200-111">Example</span></span>  
 [!code-csharp[csRefOperators#26](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="9e200-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e200-112">See Also</span></span>  
 [<span data-ttu-id="9e200-113">C# 참조</span><span class="sxs-lookup"><span data-stu-id="9e200-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="9e200-114">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="9e200-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9e200-115">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="9e200-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
