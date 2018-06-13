---
title: () 연산자(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- ()_CSharpKeyword
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
ms.openlocfilehash: 2ded01ef3192e0f34d586cd63d93b894b5347e7e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33275027"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="1c626-102">() 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="1c626-102">() Operator (C# Reference)</span></span>
<span data-ttu-id="1c626-103">괄호는 식에서 연산의 순서를 지정하는 데 사용될 뿐만 아니라 다음 작업을 수행하는 데도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c626-103">In addition to being used to specify the order of operations in an expression, parentheses are used to perform the following tasks:</span></span>  
  
1.  <span data-ttu-id="1c626-104">캐스트 또는 형식 변환을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c626-104">Specify casts, or type conversions.</span></span>  
  
     [!code-csharp[csRefOperators#1](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_1.cs)]  
  
2.  <span data-ttu-id="1c626-105">메서드 또는 대리자를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1c626-105">Invoke methods or delegates.</span></span>  
  
     [!code-csharp[csRefOperators#2](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_2.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="1c626-106">설명</span><span class="sxs-lookup"><span data-stu-id="1c626-106">Remarks</span></span>  
 <span data-ttu-id="1c626-107">캐스트는 한 형식에서 다른 형식으로의 변환 연산자를 명시적으로 호출합니다. 이러한 변환 연산자가 정의되지 않은 경우 캐스트가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="1c626-107">A cast explicitly invokes the conversion operator from one type to another; the cast fails if no such conversion operator is defined.</span></span> <span data-ttu-id="1c626-108">변환 연산자를 정의하려면 [explicit](../../../csharp/language-reference/keywords/explicit.md) 및 [implicit](../../../csharp/language-reference/keywords/implicit.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c626-108">To define a conversion operator, see [explicit](../../../csharp/language-reference/keywords/explicit.md) and [implicit](../../../csharp/language-reference/keywords/implicit.md).</span></span>  
  
 <span data-ttu-id="1c626-109">`()` 연산자를 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c626-109">The `()` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="1c626-110">자세한 내용은 [캐스팅 및 형식 변환](../../../csharp/programming-guide/types/casting-and-type-conversions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c626-110">For more information, see [Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span></span>  
  
 <span data-ttu-id="1c626-111">캐스트 식은 모호한 구문이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c626-111">A cast expression could lead to ambiguous syntax.</span></span> <span data-ttu-id="1c626-112">예를 들어 `(x)–y` 식은 캐스트 식(-y를 형식 x로 캐스트) 또는 괄호로 묶은 식과 결합된 더하기 식으로 해석될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c626-112">For example, the expression `(x)–y` could be either interpreted as a cast expression (a cast of –y to type x) or as an additive expression combined with a parenthesized expression, which computes the value x – y.</span></span>  
  
 <span data-ttu-id="1c626-113">메서드 호출에 대한 자세한 내용은 [메서드](../../../csharp/programming-guide/classes-and-structs/methods.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c626-113">For more information about method invocation, see [Methods](../../../csharp/programming-guide/classes-and-structs/methods.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="1c626-114">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="1c626-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1c626-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1c626-115">See Also</span></span>  
 [<span data-ttu-id="1c626-116">C# 참조</span><span class="sxs-lookup"><span data-stu-id="1c626-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="1c626-117">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="1c626-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="1c626-118">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="1c626-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
