---
title: orderby 절(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- orderby
- orderby_CSharpKeyword
helpviewer_keywords:
- orderby clause [C#]
- orderby keyword [C#]
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
ms.openlocfilehash: 1fd0036e8bd3c838fe92ca27635cd7638d59ef1d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33268057"
---
# <a name="orderby-clause-c-reference"></a><span data-ttu-id="8e3a7-102">orderby 절(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="8e3a7-102">orderby clause (C# Reference)</span></span>
<span data-ttu-id="8e3a7-103">쿼리 식에서 `orderby` 절은 반환된 시퀀스 또는 하위 시퀀스(그룹)가 오름차순이나 내림차순으로 정렬되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e3a7-103">In a query expression, the `orderby` clause causes the returned sequence or subsequence (group) to be sorted in either ascending or descending order.</span></span> <span data-ttu-id="8e3a7-104">하나 이상의 보조 정렬 작업을 수행하기 위해 여러 키를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e3a7-104">Multiple keys can be specified in order to perform one or more secondary sort operations.</span></span> <span data-ttu-id="8e3a7-105">정렬은 요소 형식에 대한 기본 비교자에 의해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e3a7-105">The sorting is performed by the default comparer for the type of the element.</span></span> <span data-ttu-id="8e3a7-106">기본 정렬 순서는 오름차순입니다.</span><span class="sxs-lookup"><span data-stu-id="8e3a7-106">The default sort order is ascending.</span></span> <span data-ttu-id="8e3a7-107">사용자 지정 비교자를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e3a7-107">You can also specify a custom comparer.</span></span> <span data-ttu-id="8e3a7-108">그러나 메서드 기반 구문을 통해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e3a7-108">However, it is only available by using method-based syntax.</span></span> <span data-ttu-id="8e3a7-109">자세한 내용은 [데이터 정렬](../../programming-guide/concepts/linq/sorting-data.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e3a7-109">For more information, see [Sorting Data](../../programming-guide/concepts/linq/sorting-data.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e3a7-110">예</span><span class="sxs-lookup"><span data-stu-id="8e3a7-110">Example</span></span>  
 <span data-ttu-id="8e3a7-111">다음 예제에서 첫 번째 쿼리는 A부터 시작하여 사전순으로 단어를 정렬하고, 두 번째 쿼리는 동일한 단어를 내림차순으로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="8e3a7-111">In the following example, the first query sorts the words in alphabetical order starting from A, and second query sorts the same words in descending order.</span></span> <span data-ttu-id="8e3a7-112">`ascending` 키워드는 기본 정렬 값이며 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e3a7-112">(The `ascending` keyword is the default sort value and can be omitted.)</span></span>  
  
 [!code-csharp[cscsrefQueryKeywords#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="8e3a7-113">예</span><span class="sxs-lookup"><span data-stu-id="8e3a7-113">Example</span></span>  
 <span data-ttu-id="8e3a7-114">다음 예제에서는 학생의 성을 기준으로 1차 정렬을 수행한 다음 이름을 기준으로 2차 정렬을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8e3a7-114">The following example performs a primary sort on the students' last names, and then a secondary sort on their first names.</span></span>  
  
 [!code-csharp[cscsrefQueryKeywords#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_2.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="8e3a7-115">설명</span><span class="sxs-lookup"><span data-stu-id="8e3a7-115">Remarks</span></span>  
 <span data-ttu-id="8e3a7-116">컴파일 시간에 `orderby` 절은 <xref:System.Linq.Enumerable.OrderBy%2A> 메서드 호출로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e3a7-116">At compile time, the `orderby` clause is translated to a call to the <xref:System.Linq.Enumerable.OrderBy%2A> method.</span></span> <span data-ttu-id="8e3a7-117">`orderby` 절의 여러 키는 <xref:System.Linq.Enumerable.ThenBy%2A> 메서드 호출로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e3a7-117">Multiple keys in the `orderby` clause translate to <xref:System.Linq.Enumerable.ThenBy%2A> method calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e3a7-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e3a7-118">See Also</span></span>  
 [<span data-ttu-id="8e3a7-119">C# 참조</span><span class="sxs-lookup"><span data-stu-id="8e3a7-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8e3a7-120">쿼리 키워드(LINQ)</span><span class="sxs-lookup"><span data-stu-id="8e3a7-120">Query Keywords (LINQ)</span></span>](../../../csharp/language-reference/keywords/query-keywords.md)  
 [<span data-ttu-id="8e3a7-121">LINQ 쿼리 식</span><span class="sxs-lookup"><span data-stu-id="8e3a7-121">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="8e3a7-122">group 절</span><span class="sxs-lookup"><span data-stu-id="8e3a7-122">group clause</span></span>](../../../csharp/language-reference/keywords/group-clause.md)  
 [<span data-ttu-id="8e3a7-123">C#에서 LINQ 시작</span><span class="sxs-lookup"><span data-stu-id="8e3a7-123">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
