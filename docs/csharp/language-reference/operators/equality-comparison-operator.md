---
title: == 연산자(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- ==_CSharpKeyword
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
ms.openlocfilehash: f8356320817771cb559192c1ce720a80bf33bbf9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="a2b80-102">== 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="a2b80-102">== Operator (C# Reference)</span></span>
<span data-ttu-id="a2b80-103">미리 정의된 값 형식의 경우 같음 연산자(`==`)는 피연산자의 값이 같으면 true, 같지 않으면 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b80-103">For predefined value types, the equality operator (`==`) returns true if the values of its operands are equal, `false` otherwise.</span></span> <span data-ttu-id="a2b80-104">[string](../../../csharp/language-reference/keywords/string.md)을 제외한 참조 형식의 경우 `==`은 두 피연산자가 동일한 개체를 참조하면 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b80-104">For reference types other than [string](../../../csharp/language-reference/keywords/string.md), `==` returns `true` if its two operands refer to the same object.</span></span> <span data-ttu-id="a2b80-105">`string` 형식의 경우 `==`은 문자열의 값을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b80-105">For the `string` type, `==` compares the values of the strings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2b80-106">설명</span><span class="sxs-lookup"><span data-stu-id="a2b80-106">Remarks</span></span>  
 <span data-ttu-id="a2b80-107">사용자 정의 값 형식은 `==` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="a2b80-107">User-defined value types can overload the `==` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="a2b80-108">사용자 정의 참조 형식의 경우도 마찬가지입니다. 하지만 기본적으로 `==`은 미리 정의된 참조 형식과 사용자 정의 참조 형식 모두에 대해 위에서 설명한 대로 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b80-108">So can user-defined reference types, although by default `==` behaves as described above for both predefined and user-defined reference types.</span></span> <span data-ttu-id="a2b80-109">`==` 연산자가 오버로드되면 [!=](../../../csharp/language-reference/operators/not-equal-operator.md) 또한 오버로드되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b80-109">If `==` is overloaded, [!=](../../../csharp/language-reference/operators/not-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="a2b80-110">정수 계열 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2b80-110">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2b80-111">예</span><span class="sxs-lookup"><span data-stu-id="a2b80-111">Example</span></span>  
 [!code-csharp[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="a2b80-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a2b80-112">See Also</span></span>  
 [<span data-ttu-id="a2b80-113">C# 참조</span><span class="sxs-lookup"><span data-stu-id="a2b80-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a2b80-114">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="a2b80-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a2b80-115">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="a2b80-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
