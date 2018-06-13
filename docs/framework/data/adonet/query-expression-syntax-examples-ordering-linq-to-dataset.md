---
title: '쿼리 식 구문 예제: 정렬(LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 653a4a97-1e4a-4b2d-8d24-7dbe1f2a5c84
ms.openlocfilehash: 6df3e5f08e6f6a2058c44079c15da37ace3752c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33352196"
---
# <a name="query-expression-syntax-examples-ordering-linq-to-dataset"></a><span data-ttu-id="18f98-102">쿼리 식 구문 예제: 정렬(LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="18f98-102">Query Expression Syntax Examples: Ordering (LINQ to DataSet)</span></span>
<span data-ttu-id="18f98-103">이 항목의 예제에서는 <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A> 및 <xref:System.Linq.Enumerable.ThenByDescending%2A> 메서드에서 쿼리 식 구문을 사용하여 <xref:System.Data.DataSet>을 쿼리하고 결과를 정렬하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="18f98-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A>, and <xref:System.Linq.Enumerable.ThenByDescending%2A> methods to query a <xref:System.Data.DataSet> and order the results using the query expression syntax.</span></span>  
  
 <span data-ttu-id="18f98-104">`FillDataSet` 에 이러한 예제에서 사용 하는 방법이 지정 되어 [로드 데이터에는 데이터 집합](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="18f98-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="18f98-105">이 항목의 예제에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="18f98-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="18f98-106">이 항목의 예제에서 다음을 사용 하 여 `using` / `Imports` 문:</span><span class="sxs-lookup"><span data-stu-id="18f98-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="18f98-107">자세한 내용은 참조 [하는 방법: Visual Studio에서 데이터 집합 프로젝트에 LINQ 만들기](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="18f98-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="orderby"></a><span data-ttu-id="18f98-108">OrderBy</span><span class="sxs-lookup"><span data-stu-id="18f98-108">OrderBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="18f98-109">예제</span><span class="sxs-lookup"><span data-stu-id="18f98-109">Example</span></span>  
 <span data-ttu-id="18f98-110">이 예제에서는 <xref:System.Linq.Enumerable.OrderBy%2A>를 사용하여 성을 기준으로 정렬된 연락처 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="18f98-110">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> to return a list of contacts ordered by last name.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderBySimple1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbysimple1)]
 [!code-vb[DP LINQ to DataSet Examples#OrderBySimple1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbysimple1)]  
  
### <a name="example"></a><span data-ttu-id="18f98-111">예제</span><span class="sxs-lookup"><span data-stu-id="18f98-111">Example</span></span>  
 <span data-ttu-id="18f98-112">이 예제에서는 <xref:System.Linq.Enumerable.OrderBy%2A>를 사용하여 성의 길이를 기준으로 연락처 목록을 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="18f98-112">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> to sort a list of contacts by length of last name.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderBySimple2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbysimple2)]
 [!code-vb[DP LINQ to DataSet Examples#OrderBySimple2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbysimple2)]  
  
## <a name="orderbydescending"></a><span data-ttu-id="18f98-113">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="18f98-113">OrderByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="18f98-114">예제</span><span class="sxs-lookup"><span data-stu-id="18f98-114">Example</span></span>  
 <span data-ttu-id="18f98-115">이 예제에서는 `orderby… descending` 메서드와 같은 `Order By … Descending`(<xref:System.Linq.Enumerable.OrderByDescending%2A>)을 사용하여 가격 목록을 내림차순으로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="18f98-115">This example uses `orderby… descending` (`Order By … Descending`), which is equivalent to the <xref:System.Linq.Enumerable.OrderByDescending%2A> method, to sort the price list from highest to lowest.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderByDescendingSimple1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbydescendingsimple1)]
 [!code-vb[DP LINQ to DataSet Examples#OrderByDescendingSimple1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbydescendingsimple1)]  
  
## <a name="reverse"></a><span data-ttu-id="18f98-116">Reverse</span><span class="sxs-lookup"><span data-stu-id="18f98-116">Reverse</span></span>  
  
### <a name="example"></a><span data-ttu-id="18f98-117">예제</span><span class="sxs-lookup"><span data-stu-id="18f98-117">Example</span></span>  
 <span data-ttu-id="18f98-118">이 예제에서는 <xref:System.Linq.Enumerable.Reverse%2A>을 사용하여 `OrderDate`가 2002년 2월 20일 이전인 주문 목록을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="18f98-118">This example uses <xref:System.Linq.Enumerable.Reverse%2A> to create a list of orders where `OrderDate` is earlier than Feb 20, 2002.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#reverse)]
 [!code-vb[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#reverse)]  
  
## <a name="thenbydescending"></a><span data-ttu-id="18f98-119">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="18f98-119">ThenByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="18f98-120">예제</span><span class="sxs-lookup"><span data-stu-id="18f98-120">Example</span></span>  
 <span data-ttu-id="18f98-121">이 예제에서는 `OrderBy… Descending` 메서드와 같은 <xref:System.Linq.Enumerable.ThenByDescending%2A>을 사용하여 이름과 가격별 내림차순으로 제품 목록을 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="18f98-121">This example uses `OrderBy… Descending` , which is equivalent to the <xref:System.Linq.Enumerable.ThenByDescending%2A> method, to sort a list of products, first by name and then by list price, from highest to lowest.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ThenByDescendingSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#thenbydescendingsimple)]
 [!code-vb[DP LINQ to DataSet Examples#ThenByDescendingSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#thenbydescendingsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="18f98-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18f98-122">See Also</span></span>  
 [<span data-ttu-id="18f98-123">데이터를 데이터 집합에 로드</span><span class="sxs-lookup"><span data-stu-id="18f98-123">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="18f98-124">LINQ to DataSet 예제</span><span class="sxs-lookup"><span data-stu-id="18f98-124">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="18f98-125">표준 쿼리 연산자 개요</span><span class="sxs-lookup"><span data-stu-id="18f98-125">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
