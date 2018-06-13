---
title: (LINQ to XML) 연결 된 쿼리의 성능 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 589f2adc-69f9-404d-b9d6-4c28dabea7f7
ms.openlocfilehash: d390fc0e45967cd98697320eb6f61a51cb1c19da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33645709"
---
# <a name="performance-of-chained-queries-linq-to-xml-visual-basic"></a><span data-ttu-id="3f489-102">(LINQ to XML) 연결 된 쿼리의 성능 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3f489-102">Performance of Chained Queries (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="3f489-103">LINQ(및 LINQ to XML)의 가장 큰 이점 중 하나는 연결된 쿼리가 보다 크고 복잡한 하나의 쿼리처럼 잘 수행될 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3f489-103">One of the most important benefits of LINQ (and LINQ to XML) is that chained queries can perform as well as a single larger, more complicated query.</span></span>  
  
 <span data-ttu-id="3f489-104">연결된 쿼리는 다른 쿼리를 소스로 사용하는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="3f489-104">A chained query is a query that uses another query as its source.</span></span> <span data-ttu-id="3f489-105">예를 들어 다음과 같은 간단한 코드에서 `query2`는 `query1`을 소스로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3f489-105">For example, in the following simple code, `query2` has `query1` as its source:</span></span>  
  
```vb  
Dim root As New XElement("Root", New XElement("Child", 1), New XElement("Child", 2), New XElement("Child", 3), New XElement("Child", 4))  
  
Dim query1 = From x In root.Elements("Child") Where CInt(x) >= 3x  
  
Dim query2 = From e In query1 Where CInt(e) Mod 2 = 0e  
  
For Each i As var In query2  
    Console.WriteLine("{0}", CInt(i))  
Next  
```  
  
 <span data-ttu-id="3f489-106">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3f489-106">This example produces the following output:</span></span>  
  
```  
4  
```  
  
 <span data-ttu-id="3f489-107">이 연결된 쿼리는 연결된 목록을 반복하는 것과 같은 성능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3f489-107">This chained query provides the same performance profile as iterating through a linked list.</span></span>  
  
-   <span data-ttu-id="3f489-108"><xref:System.Xml.Linq.XContainer.Elements%2A> 축은 기본적으로 연결된 목록을 반복하는 것과 같은 성능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3f489-108">The <xref:System.Xml.Linq.XContainer.Elements%2A> axis has essentially the same performance as iterating through a linked list.</span></span> <span data-ttu-id="3f489-109"><xref:System.Xml.Linq.XContainer.Elements%2A>는 지연된 실행을 사용하는 반복기로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f489-109"><xref:System.Xml.Linq.XContainer.Elements%2A> is implemented as an iterator with deferred execution.</span></span> <span data-ttu-id="3f489-110">이는 연결된 목록을 반복하는 작업뿐만 아니라 반복기 개체 할당, 실행 상태 추적 등의 다른 작업도 수행함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="3f489-110">This means that it does some work in addition to iterating through the linked list, such as allocating the iterator object and keeping track of execution state.</span></span> <span data-ttu-id="3f489-111">이러한 작업은 두 가지 범주로 나눌 수 있습니다. 하나는 반복기가 설정될 때 수행되는 작업이며, 다른 하나는 각 반복에서 수행되는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="3f489-111">This work can be divided into two categories: the work that is done at the time the iterator is set up, and the work that is done during each iteration.</span></span> <span data-ttu-id="3f489-112">설정 작업은 그 양이 작고 정해져 있지만 각 반복에서 수행되는 작업의 양은 소스 컬렉션에 포함된 항목 수에 비례합니다.</span><span class="sxs-lookup"><span data-stu-id="3f489-112">The setup work is a small, fixed amount of work and the work done during each iteration is proportional to the number of items in the source collection.</span></span>  
  
-   <span data-ttu-id="3f489-113">`query1`의 `Where` 절로 인해 쿼리는 <xref:System.Linq.Enumerable.Where%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="3f489-113">In `query1`, the `Where` clause causes the query to call the <xref:System.Linq.Enumerable.Where%2A> method.</span></span> <span data-ttu-id="3f489-114">이 메서드는 또한 반복기로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f489-114">This method is also implemented as an iterator.</span></span> <span data-ttu-id="3f489-115">설정 작업은 람다 식을 참조하는 대리자에 대한 인스턴스화 작업과 반복기에 대한 일반 설정 작업으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f489-115">The setup work consists of instantiating the delegate that will reference the lambda expression, plus the normal setup for an iterator.</span></span> <span data-ttu-id="3f489-116">각 반복에서 대리자는 조건자를 실행하기 위해 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f489-116">With each iteration, the delegate is called to execute the predicate.</span></span> <span data-ttu-id="3f489-117">설정 작업과 각 반복에서 수행되는 작업은 축 반복에서 수행되는 작업과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="3f489-117">The setup work and the work done during each iteration is the similar to the work done while iterating through the axis.</span></span>  
  
-   <span data-ttu-id="3f489-118">`query1`의 select 절로 인해 쿼리는 <xref:System.Linq.Enumerable.Select%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="3f489-118">In `query1`, the select clause causes the query to call the <xref:System.Linq.Enumerable.Select%2A> method.</span></span> <span data-ttu-id="3f489-119">이 메서드는 <xref:System.Linq.Enumerable.Where%2A> 메서드와 같은 성능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3f489-119">This method has the same performance profile as the <xref:System.Linq.Enumerable.Where%2A> method.</span></span>  
  
-   <span data-ttu-id="3f489-120">`query2`의 `Where` 절과 `Select` 절은 모두 `query1`의 해당 절과 같은 성능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3f489-120">In `query2`, both the `Where` clause and the `Select` clause have the same performance profile as in `query1`.</span></span>  
  
 <span data-ttu-id="3f489-121">따라서 `query2`의 반복은 소스로 사용된 첫 번째 쿼리의 항목 수에 정비례합니다. 즉, 선형 시간으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f489-121">The iteration through `query2` is therefore directly proportional to the number of items in the source of the first query, in other words, linear time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f489-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f489-122">See Also</span></span>  
 [<span data-ttu-id="3f489-123">성능 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3f489-123">Performance (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)
