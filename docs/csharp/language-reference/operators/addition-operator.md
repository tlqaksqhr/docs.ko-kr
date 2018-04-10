---
title: + 연산자(C# 참조)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- +_CSharpKeyword
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b15d5d1a304569b92b2f811a9ea714e4b30d60d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="739c9-102">+ 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="739c9-102">+ Operator (C# Reference)</span></span>
<span data-ttu-id="739c9-103">`+` 연산자는 단항 또는 이항 연산자로 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="739c9-103">The `+` operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="739c9-104">주의</span><span class="sxs-lookup"><span data-stu-id="739c9-104">Remarks</span></span>  
 <span data-ttu-id="739c9-105">단항 `+` 연산자는 모든 숫자 형식에 대해 미리 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="739c9-105">Unary `+` operators are predefined for all numeric types.</span></span> <span data-ttu-id="739c9-106">숫자 형식에 대한 단항 `+` 연산의 결과는 피연산자의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="739c9-106">The result of a unary `+` operation on a numeric type is just the value of the operand.</span></span>  
  
 <span data-ttu-id="739c9-107">이항 `+` 연산자는 숫자 및 문자열 형식에 대해 미리 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="739c9-107">Binary `+` operators are predefined for numeric and string types.</span></span> <span data-ttu-id="739c9-108">숫자 형식의 경우 +는 두 피연산자의 합계를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="739c9-108">For numeric types, + computes the sum of its two operands.</span></span> <span data-ttu-id="739c9-109">피연산자 중 하나 또는 둘 다가 문자열 형식이면 +는 피연산자의 문자열 표현을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="739c9-109">When one or both operands are of type string, + concatenates the string representations of the operands.</span></span>  
  
 <span data-ttu-id="739c9-110">대리자 형식도 대리자 연결을 수행하는 이항 `+` 연산자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="739c9-110">Delegate types also provide a binary `+` operator, which performs delegate concatenation.</span></span>  
  
 <span data-ttu-id="739c9-111">사용자 정의 형식은 단항 `+` 및 이항 `+` 연산자를 오버로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="739c9-111">User-defined types can overload the unary `+` and binary `+` operators.</span></span> <span data-ttu-id="739c9-112">정수 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="739c9-112">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="739c9-113">자세한 내용은 [연산자(C# 참조)](../../../csharp/language-reference/keywords/operator.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="739c9-113">For more information, see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="739c9-114">예제</span><span class="sxs-lookup"><span data-stu-id="739c9-114">Example</span></span>  
 [!code-csharp[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-operator_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="739c9-115">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="739c9-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="739c9-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="739c9-116">See Also</span></span>  
 [<span data-ttu-id="739c9-117">C# 참조</span><span class="sxs-lookup"><span data-stu-id="739c9-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="739c9-118">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="739c9-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="739c9-119">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="739c9-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="739c9-120">연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="739c9-120">operator (C# Reference)</span></span>](../../../csharp/language-reference/keywords/operator.md)
