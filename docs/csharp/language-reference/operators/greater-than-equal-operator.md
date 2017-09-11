---
title: "&gt;= 연산자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '>=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- greater than or equal to operator (>=) [C#]
- '>= operator [C#]'
ms.assetid: 0db4dcaf-56a3-4884-a7ad-35f64978a58d
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 59b134ce1e1169b0a5f4583374148d39ceb8326a
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="a4b25-102">&gt;= 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="a4b25-102">&gt;= Operator (C# Reference)</span></span>
<span data-ttu-id="a4b25-103">모든 숫자 형식과 열거형은 첫 번째 피연산자가 두 번째 피연산자보다 크거나 같을 경우에 `true`를 반환하고, 그렇지 않으면 `false`를 반환하는 “크거나 같음" 관계 연산자(`>=`)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b25-103">All numeric and enumeration types define a "greater than or equal" relational operator, `>=` that returns `true` if the first operand is greater than or equal to the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4b25-104">설명</span><span class="sxs-lookup"><span data-stu-id="a4b25-104">Remarks</span></span>  
 <span data-ttu-id="a4b25-105">사용자 정의 형식은 `>=` 연산자를 오버로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b25-105">User-defined types can overload the `>=` operator.</span></span> <span data-ttu-id="a4b25-106">자세한 내용은 [operator](../../../csharp/language-reference/keywords/operator.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4b25-106">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="a4b25-107">`>=` 연산자가 오버로드되면 [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md) 또한 오버로드되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b25-107">If `>=` is overloaded, [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="a4b25-108">정수 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4b25-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4b25-109">예제</span><span class="sxs-lookup"><span data-stu-id="a4b25-109">Example</span></span>  
 <span data-ttu-id="a4b25-110">[!code-cs[csRefOperators#39](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-equal-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a4b25-110">[!code-cs[csRefOperators#39](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-equal-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4b25-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a4b25-111">See Also</span></span>  
 <span data-ttu-id="a4b25-112">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="a4b25-112">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="a4b25-113">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a4b25-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="a4b25-114">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="a4b25-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

