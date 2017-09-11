---
title: "% 연산자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '%_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- modulus operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
caps.latest.revision: 15
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
ms.openlocfilehash: 658b04f4bee952a20a7b0a740aa931fe4fad9cdf
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="77c16-102">% 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="77c16-102">% Operator (C# Reference)</span></span>
<span data-ttu-id="77c16-103">`%` 연산자는 첫 번째 피연산자를 두 번째 피연산자로 나눈 후 나머지를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="77c16-103">The `%` operator computes the remainder after dividing its first operand by its second.</span></span> <span data-ttu-id="77c16-104">모든 숫자 형식에는 미리 정의된 나머지 연산자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77c16-104">All numeric types have predefined remainder operators.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77c16-105">설명</span><span class="sxs-lookup"><span data-stu-id="77c16-105">Remarks</span></span>  
 <span data-ttu-id="77c16-106">사용자 정의 형식은 `%` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="77c16-106">User-defined types can overload the `%` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="77c16-107">이항 연산자가 오버로드되면 해당 대입 연산자도 암시적으로 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="77c16-107">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77c16-108">예제</span><span class="sxs-lookup"><span data-stu-id="77c16-108">Example</span></span>  
 <span data-ttu-id="77c16-109">[!code-cs[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="77c16-109">[!code-cs[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-operator_1.cs)]</span></span>  
  
## <a name="comments"></a><span data-ttu-id="77c16-110">설명</span><span class="sxs-lookup"><span data-stu-id="77c16-110">Comments</span></span>  
 <span data-ttu-id="77c16-111">double 형식과 연결된 반올림 오류를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="77c16-111">Note the round-off errors associated with the double type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77c16-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="77c16-112">See Also</span></span>  
 <span data-ttu-id="77c16-113">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="77c16-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="77c16-114">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="77c16-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="77c16-115">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="77c16-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

