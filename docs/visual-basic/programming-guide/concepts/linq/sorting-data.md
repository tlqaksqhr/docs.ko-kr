---
title: "데이터 정렬 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 6f81065c-0c89-4bf3-a6d8-442273f8810e
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 1870d401ffdeeb2452ace1b74a8fb70e19c9b9ed
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="sorting-data-visual-basic"></a><span data-ttu-id="aa07c-102">데이터 정렬 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aa07c-102">Sorting Data (Visual Basic)</span></span>
<span data-ttu-id="aa07c-103">정렬 작업에는 하나 이상의 특성에 따라 시퀀스의 요소를 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa07c-103">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="aa07c-104">첫 번째 정렬 기준은 요소에 대해 기본 정렬을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="aa07c-104">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="aa07c-105">두 번째 정렬 기준을 지정하면 각 기본 정렬 그룹 내의 요소를 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa07c-105">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="aa07c-106">다음 그림에서는 문자 시퀀스에서 사전순 정렬 작업의 결과 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aa07c-106">The following illustration shows the results of an alphabetical sort operation on a sequence of characters.</span></span>  
  
 <span data-ttu-id="aa07c-107">![LINQ 정렬 작업](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span><span class="sxs-lookup"><span data-stu-id="aa07c-107">![LINQ Sorting Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span></span>  
  
 <span data-ttu-id="aa07c-108">데이터를 정렬 하는 표준 쿼리 연산자 메서드는 다음 섹션에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa07c-108">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aa07c-109">메서드</span><span class="sxs-lookup"><span data-stu-id="aa07c-109">Methods</span></span>  
  
|<span data-ttu-id="aa07c-110">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="aa07c-110">Method Name</span></span>|<span data-ttu-id="aa07c-111">설명</span><span class="sxs-lookup"><span data-stu-id="aa07c-111">Description</span></span>|<span data-ttu-id="aa07c-112">Visual Basic 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="aa07c-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="aa07c-113">추가 정보</span><span class="sxs-lookup"><span data-stu-id="aa07c-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="aa07c-114">OrderBy</span><span class="sxs-lookup"><span data-stu-id="aa07c-114">OrderBy</span></span>|<span data-ttu-id="aa07c-115">값을 오름차순으로 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa07c-115">Sorts values in ascending order.</span></span>|`Order By`|<span data-ttu-id="aa07c-116"><xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName></xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="aa07c-116"><xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="aa07c-117"><xref:System.Linq.Queryable.OrderBy%2A?displayProperty=fullName></xref:System.Linq.Queryable.OrderBy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="aa07c-117"><xref:System.Linq.Queryable.OrderBy%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="aa07c-118">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="aa07c-118">OrderByDescending</span></span>|<span data-ttu-id="aa07c-119">값을 내림차순으로 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa07c-119">Sorts values in descending order.</span></span>|`Order By … Descending`|<span data-ttu-id="aa07c-120"><xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName></xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="aa07c-120"><xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="aa07c-121"><xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=fullName></xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="aa07c-121"><xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="aa07c-122">ThenBy</span><span class="sxs-lookup"><span data-stu-id="aa07c-122">ThenBy</span></span>|<span data-ttu-id="aa07c-123">오름차순 보조 정렬을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa07c-123">Performs a secondary sort in ascending order.</span></span>|`Order By …, …`|<span data-ttu-id="aa07c-124"><xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="aa07c-124"><xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="aa07c-125"><xref:System.Linq.Queryable.ThenBy%2A?displayProperty=fullName></xref:System.Linq.Queryable.ThenBy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="aa07c-125"><xref:System.Linq.Queryable.ThenBy%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="aa07c-126">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="aa07c-126">ThenByDescending</span></span>|<span data-ttu-id="aa07c-127">내림차순으로 정렬 한 보조 정렬을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa07c-127">Performs a secondary sort in descending order.</span></span>|`Order By …, … Descending`|<span data-ttu-id="aa07c-128"><xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="aa07c-128"><xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="aa07c-129"><xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=fullName></xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="aa07c-129"><xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="aa07c-130">Reverse</span><span class="sxs-lookup"><span data-stu-id="aa07c-130">Reverse</span></span>|<span data-ttu-id="aa07c-131">컬렉션에 있는 요소의 순서를 반대로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="aa07c-131">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="aa07c-132">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="aa07c-132">Not applicable.</span></span>|<span data-ttu-id="aa07c-133"><xref:System.Linq.Enumerable.Reverse%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Reverse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="aa07c-133"><xref:System.Linq.Enumerable.Reverse%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="aa07c-134"><xref:System.Linq.Queryable.Reverse%2A?displayProperty=fullName></xref:System.Linq.Queryable.Reverse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="aa07c-134"><xref:System.Linq.Queryable.Reverse%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="aa07c-135">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="aa07c-135">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="aa07c-136">기본 정렬 예제</span><span class="sxs-lookup"><span data-stu-id="aa07c-136">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="aa07c-137">기본 오름차순 정렬</span><span class="sxs-lookup"><span data-stu-id="aa07c-137">Primary Ascending Sort</span></span>  
 <span data-ttu-id="aa07c-138">다음 예제에 사용 하는 방법을 보여 줍니다는 `Order By` 배열에서 문자열 문자열 길이 오름차순으로 정렬 하는 LINQ 쿼리에서 절.</span><span class="sxs-lookup"><span data-stu-id="aa07c-138">The following example demonstrates how to use the `Order By` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
```vb  
Dim words = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim sortQuery = From word In words   
                Order By word.Length   
                Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In sortQuery  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' the  
' fox  
' quick  
' brown  
' jumps  
```  
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="aa07c-139">기본 내림차순 정렬</span><span class="sxs-lookup"><span data-stu-id="aa07c-139">Primary Descending Sort</span></span>  
 <span data-ttu-id="aa07c-140">다음 예제에 사용 하는 방법을 보여 줍니다는 `Order By Descending` 해당 첫 문자를 내림차순으로 정렬 하 여 문자열을 정렬 하는 LINQ 쿼리 절.</span><span class="sxs-lookup"><span data-stu-id="aa07c-140">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
```vb  
Dim words = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim sortQuery = From word In words   
                Order By word.Substring(0, 1) Descending   
                Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In sortQuery  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' the  
' quick  
' jumps  
' fox  
' brown  
```  
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="aa07c-141">2 차 정렬 예제</span><span class="sxs-lookup"><span data-stu-id="aa07c-141">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="aa07c-142">2 차 오름차순 정렬</span><span class="sxs-lookup"><span data-stu-id="aa07c-142">Secondary Ascending Sort</span></span>  
 <span data-ttu-id="aa07c-143">다음 예제에 사용 하는 방법을 보여 줍니다는 `Order By` 배열에는 문자열의 기본 및 보조 정렬을 수행 하는 LINQ 쿼리에서 절.</span><span class="sxs-lookup"><span data-stu-id="aa07c-143">The following example demonstrates how to use the `Order By` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="aa07c-144">문자열에는 기본적으로 길이 및 차적 모두 오름차순 문자열의 첫 글자를 기준으로 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa07c-144">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
```vb  
Dim words = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim sortQuery = From word In words   
                Order By word.Length, word.Substring(0, 1)   
                Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In sortQuery  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' fox  
' the  
' brown  
' jumps  
' quick  
```  
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="aa07c-145">2 차 내림차순 정렬</span><span class="sxs-lookup"><span data-stu-id="aa07c-145">Secondary Descending Sort</span></span>  
 <span data-ttu-id="aa07c-146">다음 예제에 사용 하는 방법을 보여 줍니다는 `Order By Descending` 오름차순으로 정렬 순서 및 내림차순의&2; 차 정렬 기본 정렬을 수행 하는 LINQ 쿼리에서 절.</span><span class="sxs-lookup"><span data-stu-id="aa07c-146">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="aa07c-147">문자열에는 기본적으로 길이 및 차적 문자열의 첫 글자를 기준으로 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa07c-147">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
```vb  
Dim words = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim sortQuery = From word In words   
                Order By word.Length, word.Substring(0, 1) Descending   
                Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In sortQuery  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' fox  
' the  
' quick  
' jumps  
' brown  
```  
  
## <a name="see-also"></a><span data-ttu-id="aa07c-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aa07c-148">See Also</span></span>  
 <span data-ttu-id="aa07c-149"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="aa07c-149"><xref:System.Linq></span></span>   
<span data-ttu-id="aa07c-150"> [표준 쿼리 연산자 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="aa07c-150"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="aa07c-151"> [Order By 절](../../../../visual-basic/language-reference/queries/order-by-clause.md) </span><span class="sxs-lookup"><span data-stu-id="aa07c-151"> [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md) </span></span>  
<span data-ttu-id="aa07c-152"> [방법: 쿼리 결과 정렬](../../../../visual-basic/programming-guide/language-features/linq/how-to-sort-query-results-by-using-linq.md) </span><span class="sxs-lookup"><span data-stu-id="aa07c-152"> [How to: Sort Query Results](../../../../visual-basic/programming-guide/language-features/linq/how-to-sort-query-results-by-using-linq.md) </span></span>  
<span data-ttu-id="aa07c-153"> [방법: 데이터 정렬 또는 필터링 텍스트에서 단어 또는 필드 (Visual Basic) (LINQ)](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)</span><span class="sxs-lookup"><span data-stu-id="aa07c-153"> [How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)</span></span>
