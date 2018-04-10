---
title: '&lt;= 연산자(C# 참조)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <=_CSharpKeyword
helpviewer_keywords:
- less than or equal to operator (<=) [C#]
- <= operator [C#]
ms.assetid: bb0caec9-d253-4105-b8bc-5252233251e4
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a74af852451a193aaee70fea2a68ca8ff29cc215
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="lt-operator-c-reference"></a><span data-ttu-id="eaeca-102">&lt;= 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="eaeca-102">&lt;= Operator (C# Reference)</span></span>
<span data-ttu-id="eaeca-103">모든 숫자 형식과 열거형은 첫 번째 피연산자가 두 번째 피연산자보다 작거나 같을 경우에 `true`를 반환하고 그렇지 않으면 `false`를 반환하는 “작거나 같음” 관계 연산자(`<=`)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="eaeca-103">All numeric and enumeration types define a "less than or equal" relational operator (`<=`) that returns `true` if the first operand is less than or equal to the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eaeca-104">설명</span><span class="sxs-lookup"><span data-stu-id="eaeca-104">Remarks</span></span>  
 <span data-ttu-id="eaeca-105">사용자 정의 형식은 `<=` 연산자를 오버로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaeca-105">User-defined types can overload the `<=` operator.</span></span> <span data-ttu-id="eaeca-106">자세한 내용은 [operator](../../../csharp/language-reference/keywords/operator.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eaeca-106">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="eaeca-107">`<=` 연산자가 오버로드되면 [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) 또한 오버로드되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaeca-107">If `<=` is overloaded, [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="eaeca-108">정수 계열 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaeca-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eaeca-109">예제</span><span class="sxs-lookup"><span data-stu-id="eaeca-109">Example</span></span>  
 [!code-csharp[csRefOperators#32](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-equal-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="eaeca-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eaeca-110">See Also</span></span>  
 [<span data-ttu-id="eaeca-111">C# 참조</span><span class="sxs-lookup"><span data-stu-id="eaeca-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="eaeca-112">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="eaeca-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="eaeca-113">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="eaeca-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="eaeca-114">explicit</span><span class="sxs-lookup"><span data-stu-id="eaeca-114">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)
