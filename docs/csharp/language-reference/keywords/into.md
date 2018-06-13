---
title: into(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- into_CSharpKeyword
- into
helpviewer_keywords:
- into keyword [C#]
ms.assetid: 81ec62c1-f0b1-4755-8a31-959876e77f65
ms.openlocfilehash: 9bc7d50b77fe42861f92cc5bec946678d11d73d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33266866"
---
# <a name="into-c-reference"></a><span data-ttu-id="f379a-102">into(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="f379a-102">into (C# Reference)</span></span>
<span data-ttu-id="f379a-103">`into` 상황별 키워드를 사용하여 [group](../../../csharp/language-reference/keywords/group-clause.md), [join](../../../csharp/language-reference/keywords/join-clause.md), [select](../../../csharp/language-reference/keywords/select-clause.md) 절의 결과를 새 식별자에 저장하기 위한 임시 식별자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f379a-103">The `into` contextual keyword can be used to create a temporary identifier to store the results of a [group](../../../csharp/language-reference/keywords/group-clause.md), [join](../../../csharp/language-reference/keywords/join-clause.md) or [select](../../../csharp/language-reference/keywords/select-clause.md) clause into a new identifier.</span></span> <span data-ttu-id="f379a-104">이 식별자 자체는 추가 쿼리 명령의 생성기일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f379a-104">This identifier can itself be a generator for additional query commands.</span></span> <span data-ttu-id="f379a-105">`group` 또는 `select` 절에 사용할 경우 새 식별자의 사용을 *연속*이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="f379a-105">When used in a `group` or `select` clause, the use of the new identifier is sometimes referred to as a *continuation*.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f379a-106">예</span><span class="sxs-lookup"><span data-stu-id="f379a-106">Example</span></span>  
 <span data-ttu-id="f379a-107">다음 예제에서는 `into` 키워드를 사용하여 임시 식별자 `fruitGroup`을 활성화하는 방법을 보여 줍니다. 이 식별자는 `IGrouping`의 유추된 형식을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="f379a-107">The following example shows the use of the `into` keyword to enable a temporary identifier `fruitGroup` which has an inferred type of `IGrouping`.</span></span> <span data-ttu-id="f379a-108">식별자를 사용하여 각 그룹에서 <xref:System.Linq.Enumerable.Count%2A> 메서드를 호출하고 둘 이상의 단어를 포함하는 그룹만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f379a-108">By using the identifier, you can invoke the <xref:System.Linq.Enumerable.Count%2A> method on each group and select only those groups that contain two or more words.</span></span>  
  
 [!code-csharp[cscsrefQueryKeywords#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/into_1.cs)]  
  
 <span data-ttu-id="f379a-109">각 그룹에서 추가 쿼리 작업을 수행하려는 경우에만 `group` 절에 `into`를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f379a-109">The use of `into` in a `group` clause is only necessary when you want to perform additional query operations on each group.</span></span> <span data-ttu-id="f379a-110">자세한 내용은 [group 절](../../../csharp/language-reference/keywords/group-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f379a-110">For more information, see [group clause](../../../csharp/language-reference/keywords/group-clause.md).</span></span>  
  
 <span data-ttu-id="f379a-111">`join` 절에 `into`를 사용하는 방법의 예는 [join 절](../../../csharp/language-reference/keywords/join-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f379a-111">For an example of the use of `into` in a `join` clause, see [join clause](../../../csharp/language-reference/keywords/join-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f379a-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f379a-112">See Also</span></span>  
 [<span data-ttu-id="f379a-113">쿼리 키워드(LINQ)</span><span class="sxs-lookup"><span data-stu-id="f379a-113">Query Keywords (LINQ)</span></span>](../../../csharp/language-reference/keywords/query-keywords.md)  
 [<span data-ttu-id="f379a-114">LINQ 쿼리 식</span><span class="sxs-lookup"><span data-stu-id="f379a-114">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="f379a-115">group 절</span><span class="sxs-lookup"><span data-stu-id="f379a-115">group clause</span></span>](../../../csharp/language-reference/keywords/group-clause.md)
