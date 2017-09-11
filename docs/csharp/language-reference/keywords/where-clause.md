---
title: "where 절(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- whereclause_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- where keyword [C#]
- where clause [C#]
ms.assetid: 7f9bf952-7744-4f91-b676-cddb55d107c3
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
ms.openlocfilehash: 97d7c16d6bf8048e621141fff52a47907881fd2f
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="where-clause-c-reference"></a><span data-ttu-id="aa9b0-102">where 절(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="aa9b0-102">where clause (C# Reference)</span></span>
<span data-ttu-id="aa9b0-103">`where` 절은 데이터 소스의 어떤 요소가 쿼리 식에서 반환될지를 지정하기 위해 쿼리 식에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa9b0-103">The `where` clause is used in a query expression to specify which elements from the data source will be returned in the query expression.</span></span> <span data-ttu-id="aa9b0-104">또한 각 소스 요소(범위 변수로 참조됨)에 부울 조건(*predicate*)을 적용하고 지정된 조건이 참인 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="aa9b0-104">It applies a Boolean condition (*predicate*) to each source element (referenced by the range variable) and returns those for which the specified condition is true.</span></span> <span data-ttu-id="aa9b0-105">단일 쿼리 식에는 여러 `where` 절을 포함할 수 있으며 단일 절에는 여러 조건부 하위 식을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa9b0-105">A single query expression may contain multiple `where` clauses and a single clause may contain multiple predicate subexpressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa9b0-106">예제</span><span class="sxs-lookup"><span data-stu-id="aa9b0-106">Example</span></span>  
 <span data-ttu-id="aa9b0-107">다음 예제에서 `where` 절은 5보다 작은 숫자를 제외한 모든 숫자를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="aa9b0-107">In the following example, the `where` clause filters out all numbers except those that are less than five.</span></span> <span data-ttu-id="aa9b0-108">`where` 절을 제거하면 데이터 소스의 모든 숫자가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa9b0-108">If you remove the `where` clause, all numbers from the data source would be returned.</span></span> <span data-ttu-id="aa9b0-109">`num < 5` 식은 각 요소에 적용되는 조건자입니다.</span><span class="sxs-lookup"><span data-stu-id="aa9b0-109">The expression `num < 5` is the predicate that is applied to each element.</span></span>  
  
 <span data-ttu-id="aa9b0-110">[!code-cs[cscsrefQueryKeywords#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="aa9b0-110">[!code-cs[cscsrefQueryKeywords#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa9b0-111">예제</span><span class="sxs-lookup"><span data-stu-id="aa9b0-111">Example</span></span>  
 <span data-ttu-id="aa9b0-112">단일 `where` 절 내에서 [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) 및 [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) 연산자를 사용하여 조건자를 필요한 만큼 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa9b0-112">Within a single `where` clause, you can specify as many predicates as necessary by using the [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) and [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) operators.</span></span> <span data-ttu-id="aa9b0-113">다음 예제에서 쿼리는 5 미만의 짝수만 선택하도록 두 개의 조건자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="aa9b0-113">In the following example, the query specifies two predicates in order to select only the even numbers that are less than five.</span></span>  
  
 <span data-ttu-id="aa9b0-114">[!code-cs[cscsrefQueryKeywords#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="aa9b0-114">[!code-cs[cscsrefQueryKeywords#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa9b0-115">예제</span><span class="sxs-lookup"><span data-stu-id="aa9b0-115">Example</span></span>  
 <span data-ttu-id="aa9b0-116">`where` 절에는 부울 값을 반환하는 메서드를 하나 이상 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa9b0-116">A `where` clause may contain one or more methods that return Boolean values.</span></span> <span data-ttu-id="aa9b0-117">다음 예제에서 `where` 절은 메서드를 사용하여 범위 변수의 현재 값이 짝수인지 홀수인지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="aa9b0-117">In the following example, the `where` clause uses a method to determine whether the current value of the range variable is even or odd.</span></span>  
  
 <span data-ttu-id="aa9b0-118">[!code-cs[cscsrefQueryKeywords#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="aa9b0-118">[!code-cs[cscsrefQueryKeywords#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_3.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa9b0-119">주의</span><span class="sxs-lookup"><span data-stu-id="aa9b0-119">Remarks</span></span>  
 <span data-ttu-id="aa9b0-120">`where` 절은 필터링 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="aa9b0-120">The `where` clause is a filtering mechanism.</span></span> <span data-ttu-id="aa9b0-121">첫 번째 또는 마지막 절이 될 수 없다는 점을 제외하고, 쿼리 식의 거의 모든 곳에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa9b0-121">It can be positioned almost anywhere in a query expression, except it cannot be the first or last clause.</span></span> <span data-ttu-id="aa9b0-122">소스 요소를 그룹화 전에 필터링할지, 그룹화 후에 필터링할지에 따라 `where` 절은 [group](../../../csharp/language-reference/keywords/group-clause.md) 절 앞 또는 뒤에 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa9b0-122">A `where` clause may appear either before or after a [group](../../../csharp/language-reference/keywords/group-clause.md) clause depending on whether you have to filter the source elements before or after they are grouped.</span></span>  
  
 <span data-ttu-id="aa9b0-123">지정된 조건자가 데이터 소스의 요소에 대해 유효하지 않은 경우, 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="aa9b0-123">If a specified predicate is not valid for the elements in the data source, a compile-time error will result.</span></span> <span data-ttu-id="aa9b0-124">이는 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]에서 제공하는 강력한 형식 검사의 이점 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="aa9b0-124">This is one benefit of the strong type-checking provided by [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span></span>  
  
 <span data-ttu-id="aa9b0-125">컴파일 시간에 `where` 키워드는 <xref:System.Linq.Enumerable.Where%2A> 표준 쿼리 연산자 메서드에 대한 호출로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa9b0-125">At compile time the `where` keyword is converted into a call to the <xref:System.Linq.Enumerable.Where%2A> Standard Query Operator method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa9b0-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aa9b0-126">See Also</span></span>  
 <span data-ttu-id="aa9b0-127">[쿼리 키워드(LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="aa9b0-127">[Query Keywords (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span></span>  
 <span data-ttu-id="aa9b0-128">[From 절](../../../csharp/language-reference/keywords/from-clause.md) </span><span class="sxs-lookup"><span data-stu-id="aa9b0-128">[from clause](../../../csharp/language-reference/keywords/from-clause.md) </span></span>  
 <span data-ttu-id="aa9b0-129">[Select 절](../../../csharp/language-reference/keywords/select-clause.md) </span><span class="sxs-lookup"><span data-stu-id="aa9b0-129">[select clause](../../../csharp/language-reference/keywords/select-clause.md) </span></span>  
 <span data-ttu-id="aa9b0-130">[데이터 필터링](http://msdn.microsoft.com/library/cee88d0f-31aa-4c60-9452-cc122ed0057d) </span><span class="sxs-lookup"><span data-stu-id="aa9b0-130">[Filtering Data](http://msdn.microsoft.com/library/cee88d0f-31aa-4c60-9452-cc122ed0057d) </span></span>  
 <span data-ttu-id="aa9b0-131">[LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="aa9b0-131">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 [<span data-ttu-id="aa9b0-132">C#에서 LINQ 시작</span><span class="sxs-lookup"><span data-stu-id="aa9b0-132">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)

