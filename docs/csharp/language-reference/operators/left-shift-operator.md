---
title: "&lt;&lt; 연산자(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: <<_CSharpKeyword
helpviewer_keywords:
- left shift operator (<<) [C#]
- << operator [C#]
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 400dbc799c68bb9e1bc00695954115f2eb6af7c6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltlt-operator-c-reference"></a><span data-ttu-id="02ca5-102">&lt;&lt; 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="02ca5-102">&lt;&lt; Operator (C# Reference)</span></span>
<span data-ttu-id="02ca5-103">왼쪽 시프트 연산자(`<<`)는 첫 번째 피연산자를 두 번째 피연산자로 지정된 비트 수만큼 왼쪽으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="02ca5-103">The left-shift operator (`<<`) shifts its first operand left by the number of bits specified by its second operand.</span></span> <span data-ttu-id="02ca5-104">두 번째 피연산자의 형식은 [int](../../../csharp/language-reference/keywords/int.md) 또는 `int`로의 미리 정의된 암시적 숫자 변환이 있는 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02ca5-104">The type of the second operand must be an [int](../../../csharp/language-reference/keywords/int.md) or a type that has a predefined implicit numeric conversion to `int`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02ca5-105">설명</span><span class="sxs-lookup"><span data-stu-id="02ca5-105">Remarks</span></span>  
 <span data-ttu-id="02ca5-106">첫 번째 피연산자가 [int](../../../csharp/language-reference/keywords/int.md) 또는 [uint](../../../csharp/language-reference/keywords/uint.md)(32비트 수량)이면 두 번째 피연산자의 하위 5비트로 시프트 수가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="02ca5-106">If the first operand is an [int](../../../csharp/language-reference/keywords/int.md) or [uint](../../../csharp/language-reference/keywords/uint.md) (32-bit quantity), the shift count is given by the low-order five bits of the second operand.</span></span> <span data-ttu-id="02ca5-107">즉, 실제 시프트 수는 0~31비트입니다.</span><span class="sxs-lookup"><span data-stu-id="02ca5-107">That is, the actual shift count is 0 to 31 bits.</span></span>  
  
 <span data-ttu-id="02ca5-108">첫 번째 피연산자가 [long](../../../csharp/language-reference/keywords/long.md) 또는 [ulong](../../../csharp/language-reference/keywords/ulong.md)(64비트 수량)이면 두 번째 피연산자의 하위 6비트로 시프트 수가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="02ca5-108">If the first operand is a [long](../../../csharp/language-reference/keywords/long.md) or [ulong](../../../csharp/language-reference/keywords/ulong.md) (64-bit quantity), the shift count is given by the low-order six bits of the second operand.</span></span> <span data-ttu-id="02ca5-109">즉, 실제 시프트 수는 0~63비트입니다.</span><span class="sxs-lookup"><span data-stu-id="02ca5-109">That is, the actual shift count is 0 to 63 bits.</span></span>  
  
 <span data-ttu-id="02ca5-110">시프트 후 첫 번째 피연산자의 형식 범위 내에 없는 상위 비트는 삭제되고, 비어 있는 하위 비트는 0으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="02ca5-110">Any high-order bits that are not within the range of the type of the first operand after the shift are discarded, and the low-order empty bits are zero-filled.</span></span> <span data-ttu-id="02ca5-111">시프트 작업은 오버플로를 일으키지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02ca5-111">Shift operations never cause overflows.</span></span>  
  
 <span data-ttu-id="02ca5-112">사용자 정의 형식은 `<<` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조). 첫 번째 피연산자의 형식은 사용자 정의 형식이어야 하고 두 번째 피연산자의 형식은 `int`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02ca5-112">User-defined types can overload the `<<` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)); the type of the first operand must be the user-defined type, and the type of the second operand must be `int`.</span></span> <span data-ttu-id="02ca5-113">이항 연산자가 오버로드되면 해당 대입 연산자도 암시적으로 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="02ca5-113">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02ca5-114">예제</span><span class="sxs-lookup"><span data-stu-id="02ca5-114">Example</span></span>  
 [!code-csharp[csRefOperators#14](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-operator_1.cs)]  
  
## <a name="comments"></a><span data-ttu-id="02ca5-115">설명</span><span class="sxs-lookup"><span data-stu-id="02ca5-115">Comments</span></span>  
 <span data-ttu-id="02ca5-116">`i<<1` 및 `i<<33`은 1과 33의 하위 5비트가 같기 때문에 동일한 결과를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="02ca5-116">Note that `i<<1` and `i<<33` give the same result, because 1 and 33 have the same low-order five bits.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02ca5-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="02ca5-117">See Also</span></span>  
 [<span data-ttu-id="02ca5-118">C# 참조</span><span class="sxs-lookup"><span data-stu-id="02ca5-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="02ca5-119">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="02ca5-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="02ca5-120">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="02ca5-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
