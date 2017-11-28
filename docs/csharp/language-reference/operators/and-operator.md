---
title: "&amp; 연산자(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '&_CSharpKeyword'
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: eceee8e01ba46f65c6b182a40d14e62aaba5dd53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="79c85-102">&amp; 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="79c85-102">&amp; Operator (C# Reference)</span></span>
<span data-ttu-id="79c85-103">& 연산자는 단항 또는 이항 연산자로 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79c85-103">The & operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79c85-104">설명</span><span class="sxs-lookup"><span data-stu-id="79c85-104">Remarks</span></span>  
 <span data-ttu-id="79c85-105">단항 & 연산자는 해당 피연산자의 주소를 반환합니다([안전하지 않은](../../../csharp/language-reference/keywords/unsafe.md) 컨텍스트 필요).</span><span class="sxs-lookup"><span data-stu-id="79c85-105">The unary & operator returns the address of its operand (requires [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context).</span></span>  
  
 <span data-ttu-id="79c85-106">이항 & 연산자는 정수 형식 및 `bool`에 대해 미리 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79c85-106">Binary & operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="79c85-107">정수 형식의 경우 & 연산자는 해당 피연산자의 논리적 비트 AND를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="79c85-107">For integral types, & computes the logical bitwise AND of its operands.</span></span> <span data-ttu-id="79c85-108">`bool` 피연산자의 경우 & 연산자는 해당 피연산자의 논리적 AND 연산을 계산합니다. 즉, 피연산자가 둘 다 `true`일 경우에만 결과가 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="79c85-108">For `bool` operands, & computes the logical AND of its operands; that is, the result is `true` if and only if both its operands are `true`.</span></span>  
  
 <span data-ttu-id="79c85-109">`&` 연산자는 첫 번째 피연산자의 값과 관계없이 두 피연산자를 모두 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="79c85-109">The `&` operator evaluates both operators regardless of the first one's value.</span></span> <span data-ttu-id="79c85-110">예:</span><span class="sxs-lookup"><span data-stu-id="79c85-110">For example:</span></span>  
  
 [!code-csharp[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]  
  
 <span data-ttu-id="79c85-111">사용자 정의 형식으로 이항 `&` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="79c85-111">User-defined types can overload the binary `&` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="79c85-112">정수 계열 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="79c85-112">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="79c85-113">이항 연산자가 오버로드되면 해당 대입 연산자도 암시적으로 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="79c85-113">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79c85-114">예제</span><span class="sxs-lookup"><span data-stu-id="79c85-114">Example</span></span>  
 [!code-csharp[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="79c85-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="79c85-115">See Also</span></span>  
 [<span data-ttu-id="79c85-116">C# 참조</span><span class="sxs-lookup"><span data-stu-id="79c85-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="79c85-117">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="79c85-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="79c85-118">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="79c85-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
