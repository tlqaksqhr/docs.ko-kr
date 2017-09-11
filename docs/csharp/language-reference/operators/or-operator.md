---
title: "| 연산자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '|_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
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
ms.openlocfilehash: 7524e246df35154ac04e46f2b43edded71be34b1
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="8ec01-102">| 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="8ec01-102">| Operator (C# Reference)</span></span>
<span data-ttu-id="8ec01-103">이항 `|` 연산자는 정수 형식 및 `bool`에 대해 미리 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec01-103">Binary `|` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="8ec01-104">정수 형식의 경우 `|` 연산자는 해당 피연산자의 비트 OR 연산자를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="8ec01-104">For integral types, `|` computes the bitwise OR of its operands.</span></span> <span data-ttu-id="8ec01-105">`bool` 피연산자의 경우 `|` 연산자는 해당 피연산자의 논리적 OR 연산을 계산합니다. 즉, 피연산자가 둘 다 `false`일 경우에만 결과가 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="8ec01-105">For `bool` operands, `|` computes the logical OR of its operands; that is, the result is `false` if and only if both its operands are `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ec01-106">설명</span><span class="sxs-lookup"><span data-stu-id="8ec01-106">Remarks</span></span>  
 <span data-ttu-id="8ec01-107">사용자 정의 형식은 `|` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="8ec01-107">User-defined types can overload the `|` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ec01-108">예제</span><span class="sxs-lookup"><span data-stu-id="8ec01-108">Example</span></span>  
 <span data-ttu-id="8ec01-109">[!code-cs[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8ec01-109">[!code-cs[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ec01-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ec01-110">See Also</span></span>  
 <span data-ttu-id="8ec01-111">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="8ec01-111">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="8ec01-112">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8ec01-112">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="8ec01-113">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="8ec01-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

