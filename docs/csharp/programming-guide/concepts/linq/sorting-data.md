---
title: "데이터 정렬(C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: d93fa055-2f19-46d2-9898-e2aed628f1c9
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ff6ef81486074f2e738b62ce37e6cb58bff49bf8
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="sorting-data-c"></a><span data-ttu-id="26a85-102">데이터 정렬(C#)</span><span class="sxs-lookup"><span data-stu-id="26a85-102">Sorting Data (C#)</span></span>
<span data-ttu-id="26a85-103">정렬 작업은 하나 이상의 특성을 기준으로 시퀀스의 요소를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="26a85-103">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="26a85-104">첫 번째 정렬 기준은 요소에 대해 기본 정렬을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="26a85-104">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="26a85-105">두 번째 정렬 기준을 지정하면 각 기본 정렬 그룹 내의 요소를 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26a85-105">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="26a85-106">다음 그림은 문자 시퀀스에 대한 사전순 정렬 작업의 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="26a85-106">The following illustration shows the results of an alphabetical sort operation on a sequence of characters.</span></span>  
  
 <span data-ttu-id="26a85-107">![LINQ 정렬 작업](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span><span class="sxs-lookup"><span data-stu-id="26a85-107">![LINQ Sorting Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span></span>  
  
 <span data-ttu-id="26a85-108">다음 섹션에는 데이터를 정렬하는 표준 쿼리 연산자 메서드가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26a85-108">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="26a85-109">메서드</span><span class="sxs-lookup"><span data-stu-id="26a85-109">Methods</span></span>  
  
|<span data-ttu-id="26a85-110">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="26a85-110">Method Name</span></span>|<span data-ttu-id="26a85-111">설명</span><span class="sxs-lookup"><span data-stu-id="26a85-111">Description</span></span>|<span data-ttu-id="26a85-112">C# 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="26a85-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="26a85-113">추가 정보</span><span class="sxs-lookup"><span data-stu-id="26a85-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="26a85-114">OrderBy</span><span class="sxs-lookup"><span data-stu-id="26a85-114">OrderBy</span></span>|<span data-ttu-id="26a85-115">값을 오름차순으로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="26a85-115">Sorts values in ascending order.</span></span>|`orderby`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=fullName>|  
|<span data-ttu-id="26a85-116">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="26a85-116">OrderByDescending</span></span>|<span data-ttu-id="26a85-117">값을 내림차순으로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="26a85-117">Sorts values in descending order.</span></span>|`orderby … descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=fullName>|  
|<span data-ttu-id="26a85-118">ThenBy</span><span class="sxs-lookup"><span data-stu-id="26a85-118">ThenBy</span></span>|<span data-ttu-id="26a85-119">2차 정렬을 오름차순으로 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="26a85-119">Performs a secondary sort in ascending order.</span></span>|`orderby …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=fullName>|  
|<span data-ttu-id="26a85-120">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="26a85-120">ThenByDescending</span></span>|<span data-ttu-id="26a85-121">2차 정렬을 내림차순으로 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="26a85-121">Performs a secondary sort in descending order.</span></span>|`orderby …, … descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=fullName>|  
|<span data-ttu-id="26a85-122">Reverse</span><span class="sxs-lookup"><span data-stu-id="26a85-122">Reverse</span></span>|<span data-ttu-id="26a85-123">컬렉션에서 요소의 순서를 반대로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="26a85-123">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="26a85-124">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="26a85-124">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="26a85-125">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="26a85-125">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="26a85-126">1차 정렬 예제</span><span class="sxs-lookup"><span data-stu-id="26a85-126">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="26a85-127">1차 오름차순 정렬</span><span class="sxs-lookup"><span data-stu-id="26a85-127">Primary Ascending Sort</span></span>  
 <span data-ttu-id="26a85-128">다음 예제에서는 LINQ 쿼리에 `orderby` 절을 사용하여 배열의 문자열을 문자열 길이의 오름차순으로 정렬하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="26a85-128">The following example demonstrates how to use the `orderby` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
    quick  
    brown  
    jumps  
*/  
```  
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="26a85-129">1차 내림차순 정렬</span><span class="sxs-lookup"><span data-stu-id="26a85-129">Primary Descending Sort</span></span>  
 <span data-ttu-id="26a85-130">다음 예제에서는 LINQ 쿼리에 `orderby``descending` 절을 사용하여 문자열을 첫 글자의 내림차순으로 정렬하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="26a85-130">The next example demonstrates how to use the `orderby``descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Substring(0, 1) descending  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    quick  
    jumps  
    fox  
    brown  
*/  
```  
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="26a85-131">2차 정렬 예제</span><span class="sxs-lookup"><span data-stu-id="26a85-131">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="26a85-132">2차 오름차순 정렬</span><span class="sxs-lookup"><span data-stu-id="26a85-132">Secondary Ascending Sort</span></span>  
 <span data-ttu-id="26a85-133">다음 예제에서는 LINQ 쿼리에 `orderby` 절을 사용하여 배열의 문자열에 대해 1차 및 2차 정렬을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="26a85-133">The following example demonstrates how to use the `orderby` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="26a85-134">문자열은 길이의 오름차순으로 1차 정렬된 다음 문자열 첫 글자의 오름차순으로 2차 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="26a85-134">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length, word.Substring(0, 1)  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    fox  
    the  
    brown  
    jumps  
    quick  
*/  
```  
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="26a85-135">2차 내림차순 정렬</span><span class="sxs-lookup"><span data-stu-id="26a85-135">Secondary Descending Sort</span></span>  
 <span data-ttu-id="26a85-136">다음 예제에서는 LINQ 쿼리에 `orderby``descending` 절을 사용하여 1차 정렬을 오름차순으로 수행한 다음 2차 정렬을 내림차순으로 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="26a85-136">The next example demonstrates how to use the `orderby``descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="26a85-137">문자열은 길이순으로 1차 정렬된 다음 문자열 첫 글자순으로 2차 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="26a85-137">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length, word.Substring(0, 1) descending  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
    quick  
    jumps  
    brown  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="26a85-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="26a85-138">See Also</span></span>  
 <span data-ttu-id="26a85-139"><xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="26a85-139"><xref:System.Linq></span></span>   
 <span data-ttu-id="26a85-140">[표준 쿼리 연산자 개요(C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="26a85-140">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 <span data-ttu-id="26a85-141">[orderby 절](../../../../csharp/language-reference/keywords/orderby-clause.md) </span><span class="sxs-lookup"><span data-stu-id="26a85-141">[orderby clause](../../../../csharp/language-reference/keywords/orderby-clause.md) </span></span>  
 <span data-ttu-id="26a85-142">[방법: Join 절 결과를 순서대로 정렬](../../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md) </span><span class="sxs-lookup"><span data-stu-id="26a85-142">[How to: Order the Results of a Join Clause](../../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md) </span></span>  
 [<span data-ttu-id="26a85-143">방법: 단어 또는 필드에 따라 텍스트 데이터 정렬 또는 필터링(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="26a85-143">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)

