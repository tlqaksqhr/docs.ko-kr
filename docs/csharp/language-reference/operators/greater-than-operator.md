---
title: "&gt; 연산자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '>_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- '> operator [C#]'
- greater than operator (>) [C#]
ms.assetid: 26d3cb69-9c0b-4cc5-858b-5be1abd6659d
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
ms.openlocfilehash: 5b4eb1f6fcca311fc772e4dbe0ce0391201af3de
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="69b53-102">&gt; 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="69b53-102">&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="69b53-103">모든 숫자 형식과 열거형은 첫 번째 피연산자가 두 번째 피연산자보다 크면 `true`를 반환하고 그렇지 않으면 `false`를 반환하는 “보다 큼” 관계 연산자(`>`)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="69b53-103">All numeric and enumeration types define a "greater than" relational operator (`>`) that returns `true` if the first operand is greater than the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69b53-104">설명</span><span class="sxs-lookup"><span data-stu-id="69b53-104">Remarks</span></span>  
 <span data-ttu-id="69b53-105">사용자 정의 형식은 `>` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="69b53-105">User-defined types can overload the `>` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="69b53-106">`>` 연산자가 오버로드되면 [<](../../../csharp/language-reference/operators/less-than-operator.md) 또한 오버로드되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69b53-106">If `>` is overloaded, [<](../../../csharp/language-reference/operators/less-than-operator.md) must also be overloaded.</span></span> <span data-ttu-id="69b53-107">이항 연산자가 오버로드되면 해당 대입 연산자도 암시적으로 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="69b53-107">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69b53-108">예제</span><span class="sxs-lookup"><span data-stu-id="69b53-108">Example</span></span>  
 <span data-ttu-id="69b53-109">[!code-cs[csRefOperators#29](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="69b53-109">[!code-cs[csRefOperators#29](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69b53-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="69b53-110">See Also</span></span>  
 <span data-ttu-id="69b53-111">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="69b53-111">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="69b53-112">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="69b53-112">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="69b53-113">[C# 연산자](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="69b53-113">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 [<span data-ttu-id="69b53-114">explicit</span><span class="sxs-lookup"><span data-stu-id="69b53-114">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)

