---
title: "orderby 절(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- orderby
- orderby_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- orderby clause [C#]
- orderby keyword [C#]
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
caps.latest.revision: 17
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
ms.openlocfilehash: ec9507e4c1d9691d90d47cdbb20fdb22fc281d24
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="orderby-clause-c-reference"></a><span data-ttu-id="6ff0e-102">orderby 절(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="6ff0e-102">orderby clause (C# Reference)</span></span>
<span data-ttu-id="6ff0e-103">쿼리 식에서 `orderby` 절은 반환된 시퀀스 또는 하위 시퀀스(그룹)가 오름차순이나 내림차순으로 정렬되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff0e-103">In a query expression, the `orderby` clause causes the returned sequence or subsequence (group) to be sorted in either ascending or descending order.</span></span> <span data-ttu-id="6ff0e-104">하나 이상의 보조 정렬 작업을 수행하기 위해 여러 키를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ff0e-104">Multiple keys can be specified in order to perform one or more secondary sort operations.</span></span> <span data-ttu-id="6ff0e-105">정렬은 요소 형식에 대한 기본 비교자에 의해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ff0e-105">The sorting is performed by the default comparer for the type of the element.</span></span> <span data-ttu-id="6ff0e-106">기본 정렬 순서는 오름차순입니다.</span><span class="sxs-lookup"><span data-stu-id="6ff0e-106">The default sort order is ascending.</span></span> <span data-ttu-id="6ff0e-107">사용자 지정 비교자를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ff0e-107">You can also specify a custom comparer.</span></span> <span data-ttu-id="6ff0e-108">그러나 메서드 기반 구문을 통해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ff0e-108">However, it is only available by using method-based syntax.</span></span> <span data-ttu-id="6ff0e-109">자세한 내용은 [데이터 정렬](http://msdn.microsoft.com/library/6d76e2d7-b418-49b5-ac78-2bcd61169c48)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ff0e-109">For more information, see [Sorting Data](http://msdn.microsoft.com/library/6d76e2d7-b418-49b5-ac78-2bcd61169c48).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ff0e-110">예제</span><span class="sxs-lookup"><span data-stu-id="6ff0e-110">Example</span></span>  
 <span data-ttu-id="6ff0e-111">다음 예제에서 첫 번째 쿼리는 A부터 시작하여 사전순으로 단어를 정렬하고, 두 번째 쿼리는 동일한 단어를 내림차순으로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff0e-111">In the following example, the first query sorts the words in alphabetical order starting from A, and second query sorts the same words in descending order.</span></span> <span data-ttu-id="6ff0e-112">`ascending` 키워드는 기본 정렬 값이며 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ff0e-112">(The `ascending` keyword is the default sort value and can be omitted.)</span></span>  
  
 <span data-ttu-id="6ff0e-113">[!code-cs[cscsrefQueryKeywords#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6ff0e-113">[!code-cs[cscsrefQueryKeywords#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ff0e-114">예제</span><span class="sxs-lookup"><span data-stu-id="6ff0e-114">Example</span></span>  
 <span data-ttu-id="6ff0e-115">다음 예제에서는 학생의 성을 기준으로 1차 정렬을 수행한 다음 이름을 기준으로 2차 정렬을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6ff0e-115">The following example performs a primary sort on the students' last names, and then a secondary sort on their first names.</span></span>  
  
 <span data-ttu-id="6ff0e-116">[!code-cs[cscsrefQueryKeywords#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="6ff0e-116">[!code-cs[cscsrefQueryKeywords#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_2.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ff0e-117">설명</span><span class="sxs-lookup"><span data-stu-id="6ff0e-117">Remarks</span></span>  
 <span data-ttu-id="6ff0e-118">컴파일 시간에 `orderby` 절은 <xref:System.Linq.Enumerable.OrderBy%2A> 메서드 호출로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ff0e-118">At compile time, the `orderby` clause is translated to a call to the <xref:System.Linq.Enumerable.OrderBy%2A> method.</span></span> <span data-ttu-id="6ff0e-119">`orderby` 절의 여러 키는 <xref:System.Linq.Enumerable.ThenBy%2A> 메서드 호출로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ff0e-119">Multiple keys in the `orderby` clause translate to <xref:System.Linq.Enumerable.ThenBy%2A> method calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ff0e-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ff0e-120">See Also</span></span>  
 <span data-ttu-id="6ff0e-121">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="6ff0e-121">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="6ff0e-122">[쿼리 키워드(LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="6ff0e-122">[Query Keywords (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span></span>  
 <span data-ttu-id="6ff0e-123">[LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="6ff0e-123">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 <span data-ttu-id="6ff0e-124">[group 절](../../../csharp/language-reference/keywords/group-clause.md) </span><span class="sxs-lookup"><span data-stu-id="6ff0e-124">[group clause](../../../csharp/language-reference/keywords/group-clause.md) </span></span>  
 [<span data-ttu-id="6ff0e-125">C#에서 LINQ 시작</span><span class="sxs-lookup"><span data-stu-id="6ff0e-125">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)

