---
title: "== 연산자(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ==_CSharpKeyword
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ca22846325968519a1f7625461867c0d83a1a9f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="39c85-102">== 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="39c85-102">== Operator (C# Reference)</span></span>
<span data-ttu-id="39c85-103">미리 정의된 값 형식의 경우 같음 연산자(`==`)는 피연산자의 값이 같으면 true, 같지 않으면 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="39c85-103">For predefined value types, the equality operator (`==`) returns true if the values of its operands are equal, `false` otherwise.</span></span> <span data-ttu-id="39c85-104">[string](../../../csharp/language-reference/keywords/string.md)을 제외한 참조 형식의 경우 `==`은 두 피연산자가 동일한 개체를 참조하면 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="39c85-104">For reference types other than [string](../../../csharp/language-reference/keywords/string.md), `==` returns `true` if its two operands refer to the same object.</span></span> <span data-ttu-id="39c85-105">`string` 형식의 경우 `==`은 문자열의 값을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="39c85-105">For the `string` type, `==` compares the values of the strings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39c85-106">설명</span><span class="sxs-lookup"><span data-stu-id="39c85-106">Remarks</span></span>  
 <span data-ttu-id="39c85-107">사용자 정의 값 형식은 `==` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="39c85-107">User-defined value types can overload the `==` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="39c85-108">사용자 정의 참조 형식의 경우도 마찬가지입니다. 하지만 기본적으로 `==`은 미리 정의된 참조 형식과 사용자 정의 참조 형식 모두에 대해 위에서 설명한 대로 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="39c85-108">So can user-defined reference types, although by default `==` behaves as described above for both predefined and user-defined reference types.</span></span> <span data-ttu-id="39c85-109">`==` 연산자가 오버로드되면 [!=](../../../csharp/language-reference/operators/not-equal-operator.md) 또한 오버로드되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39c85-109">If `==` is overloaded, [!=](../../../csharp/language-reference/operators/not-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="39c85-110">정수 계열 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="39c85-110">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39c85-111">예제</span><span class="sxs-lookup"><span data-stu-id="39c85-111">Example</span></span>  
 [!code-csharp[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="39c85-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="39c85-112">See Also</span></span>  
 [<span data-ttu-id="39c85-113">C# 참조</span><span class="sxs-lookup"><span data-stu-id="39c85-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="39c85-114">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="39c85-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="39c85-115">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="39c85-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
