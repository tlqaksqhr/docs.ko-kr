---
title: 연결된 쿼리의 성능(LINQ to XML)(C#)
ms.date: 07/20/2015
ms.assetid: b2f1d715-8946-4dc0-8d56-fb3d1bba54a6
ms.openlocfilehash: dca2fa37a18209c5970172cb084151a58ea4ebc9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33336367"
---
# <a name="performance-of-chained-queries-linq-to-xml-c"></a><span data-ttu-id="5f898-102">연결된 쿼리의 성능(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="5f898-102">Performance of Chained Queries (LINQ to XML) (C#)</span></span>
<span data-ttu-id="5f898-103">LINQ(및 LINQ to XML)의 가장 큰 이점 중 하나는 연결된 쿼리가 보다 크고 복잡한 하나의 쿼리처럼 잘 수행될 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5f898-103">One of the most important benefits of LINQ (and LINQ to XML) is that chained queries can perform as well as a single larger, more complicated query.</span></span>  
  
 <span data-ttu-id="5f898-104">연결된 쿼리는 다른 쿼리를 소스로 사용하는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="5f898-104">A chained query is a query that uses another query as its source.</span></span> <span data-ttu-id="5f898-105">예를 들어 다음과 같은 간단한 코드에서 `query2`는 `query1`을 소스로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5f898-105">For example, in the following simple code, `query2` has `query1` as its source:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child", 1),  
    new XElement("Child", 2),  
    new XElement("Child", 3),  
    new XElement("Child", 4)  
);  
  
var query1 = from x in root.Elements("Child")  
             where (int)x >= 3  
             select x;  
  
var query2 = from e in query1  
             where (int)e % 2 == 0  
             select e;  
  
foreach (var i in query2)  
    Console.WriteLine("{0}", (int)i);  
```  
  
 <span data-ttu-id="5f898-106">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5f898-106">This example produces the following output:</span></span>  
  
```  
4  
```  
  
 <span data-ttu-id="5f898-107">이 연결된 쿼리는 연결된 목록을 반복하는 것과 같은 성능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5f898-107">This chained query provides the same performance profile as iterating through a linked list.</span></span>  
  
-   <span data-ttu-id="5f898-108"><xref:System.Xml.Linq.XContainer.Elements%2A> 축은 기본적으로 연결된 목록을 반복하는 것과 같은 성능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5f898-108">The <xref:System.Xml.Linq.XContainer.Elements%2A> axis has essentially the same performance as iterating through a linked list.</span></span> <span data-ttu-id="5f898-109"><xref:System.Xml.Linq.XContainer.Elements%2A>는 지연된 실행을 사용하는 반복기로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f898-109"><xref:System.Xml.Linq.XContainer.Elements%2A> is implemented as an iterator with deferred execution.</span></span> <span data-ttu-id="5f898-110">이는 연결된 목록을 반복하는 작업뿐만 아니라 반복기 개체 할당, 실행 상태 추적 등의 다른 작업도 수행함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="5f898-110">This means that it does some work in addition to iterating through the linked list, such as allocating the iterator object and keeping track of execution state.</span></span> <span data-ttu-id="5f898-111">이러한 작업은 두 가지 범주로 나눌 수 있습니다. 하나는 반복기가 설정될 때 수행되는 작업이며, 다른 하나는 각 반복에서 수행되는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="5f898-111">This work can be divided into two categories: the work that is done at the time the iterator is set up, and the work that is done during each iteration.</span></span> <span data-ttu-id="5f898-112">설정 작업은 그 양이 작고 정해져 있지만 각 반복에서 수행되는 작업의 양은 소스 컬렉션에 포함된 항목 수에 비례합니다.</span><span class="sxs-lookup"><span data-stu-id="5f898-112">The setup work is a small, fixed amount of work and the work done during each iteration is proportional to the number of items in the source collection.</span></span>  
  
-   <span data-ttu-id="5f898-113">`query1`의 `where` 절로 인해 쿼리는 <xref:System.Linq.Enumerable.Where%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="5f898-113">In `query1`, the `where` clause causes the query to call the <xref:System.Linq.Enumerable.Where%2A> method.</span></span> <span data-ttu-id="5f898-114">이 메서드는 또한 반복기로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f898-114">This method is also implemented as an iterator.</span></span> <span data-ttu-id="5f898-115">설정 작업은 람다 식을 참조하는 대리자에 대한 인스턴스화 작업과 반복기에 대한 일반 설정 작업으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f898-115">The setup work consists of instantiating the delegate that will reference the lambda expression, plus the normal setup for an iterator.</span></span> <span data-ttu-id="5f898-116">각 반복에서 대리자는 조건자를 실행하기 위해 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f898-116">With each iteration, the delegate is called to execute the predicate.</span></span> <span data-ttu-id="5f898-117">설정 작업과 각 반복에서 수행되는 작업은 축 반복에서 수행되는 작업과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="5f898-117">The setup work and the work done during each iteration is the similar to the work done while iterating through the axis.</span></span>  
  
-   <span data-ttu-id="5f898-118">`query1`의 select 절로 인해 쿼리는 <xref:System.Linq.Enumerable.Select%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="5f898-118">In `query1`, the select clause causes the query to call the <xref:System.Linq.Enumerable.Select%2A> method.</span></span> <span data-ttu-id="5f898-119">이 메서드는 <xref:System.Linq.Enumerable.Where%2A> 메서드와 같은 성능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5f898-119">This method has the same performance profile as the <xref:System.Linq.Enumerable.Where%2A> method.</span></span>  
  
-   <span data-ttu-id="5f898-120">`query2`의 `where` 절과 `select` 절은 모두 `query1`의 해당 절과 같은 성능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5f898-120">In `query2`, both the `where` clause and the `select` clause have the same performance profile as in `query1`.</span></span>  
  
 <span data-ttu-id="5f898-121">따라서 `query2`의 반복은 소스로 사용된 첫 번째 쿼리의 항목 수에 정비례합니다. 즉, 선형 시간으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f898-121">The iteration through `query2` is therefore directly proportional to the number of items in the source of the first query, in other words, linear time.</span></span> <span data-ttu-id="5f898-122">이에 해당하는 Visual Basic 예제도 같은 성능 프로필을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5f898-122">A corresponding Visual Basic example would have the same performance profile.</span></span>  
  
 <span data-ttu-id="5f898-123">반복기에 대한 자세한 내용은 [yield](../../../../csharp/language-reference/keywords/yield.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f898-123">For more information on iterators, see [yield](../../../../csharp/language-reference/keywords/yield.md).</span></span>  
  
 <span data-ttu-id="5f898-124">쿼리를 연결하는 방법을 설명하는 자세한 자습서를 보려면 [자습서: 여러 쿼리 연결](http://msdn.microsoft.com/library/c08d228a-f07a-4c98-810f-1bf0e8f2257c)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f898-124">For a more detailed tutorial on chaining queries together, see [Tutorial: Chaining Queries Together](http://msdn.microsoft.com/library/c08d228a-f07a-4c98-810f-1bf0e8f2257c).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f898-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5f898-125">See Also</span></span>  
 [<span data-ttu-id="5f898-126">성능(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="5f898-126">Performance (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/performance-linq-to-xml.md)
