---
title: "! 연산자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '!_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- '! operator [C#]'
- logical negation operator (!) [C#]
- NOT operator [C#]
ms.assetid: f5ae133f-8f64-4560-b34f-cd9cd5eed4ad
caps.latest.revision: 13
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
ms.openlocfilehash: a040af8724240258b74a39c937a6a321499c3447
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="06c9d-103">!</span><span class="sxs-lookup"><span data-stu-id="06c9d-103">!</span></span> <span data-ttu-id="06c9d-104">연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="06c9d-104">Operator (C# Reference)</span></span>
<span data-ttu-id="06c9d-105">논리적 부정 연산자(`!`)는 해당 피연산자를 부정하는 단항 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="06c9d-105">The logical negation operator (`!`) is a unary operator that negates its operand.</span></span> <span data-ttu-id="06c9d-106">`bool`에 대해 정의되며, 해당 피연산자가 `false`인 경우에만 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="06c9d-106">It is defined for `bool` and returns `true` if and only if its operand is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06c9d-107">설명</span><span class="sxs-lookup"><span data-stu-id="06c9d-107">Remarks</span></span>  
 <span data-ttu-id="06c9d-108">사용자 정의 형식은 `!` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="06c9d-108">User-defined types can overload the `!` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="06c9d-109">예제</span><span class="sxs-lookup"><span data-stu-id="06c9d-109">Example</span></span>  
 <span data-ttu-id="06c9d-110">[!code-cs[csRefOperators#7](../../../csharp/language-reference/operators/codesnippet/CSharp/logical-negation-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="06c9d-110">[!code-cs[csRefOperators#7](../../../csharp/language-reference/operators/codesnippet/CSharp/logical-negation-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06c9d-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06c9d-111">See Also</span></span>  
 <span data-ttu-id="06c9d-112">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="06c9d-112">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="06c9d-113">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="06c9d-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="06c9d-114">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="06c9d-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

