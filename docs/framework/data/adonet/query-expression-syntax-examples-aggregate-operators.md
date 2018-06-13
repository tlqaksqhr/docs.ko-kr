---
title: '쿼리 식 구문 예제: 집계 연산자(LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 85dafa07-e102-46e7-ab78-37bf06f257a6
ms.openlocfilehash: 899d059575bc08711d486eedfdfb61045bea833c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33359577"
---
# <a name="query-expression-syntax-examples-aggregate-operators-linq-to-dataset"></a><span data-ttu-id="6662c-102">쿼리 식 구문 예제: 집계 연산자(LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="6662c-102">Query Expression Syntax Examples: Aggregate Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="6662c-103">이 항목의 예제에서는 <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A> 및 <xref:System.Linq.Enumerable.Sum%2A> 메서드에서 쿼리 식 구문을 사용하여 <xref:System.Data.DataSet>을 쿼리하고 데이터를 집계하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6662c-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query a <xref:System.Data.DataSet> and aggregate data using query expression syntax.</span></span>  
  
 <span data-ttu-id="6662c-104">`FillDataSet` 에 이러한 예제에서 사용 하는 방법이 지정 되어 [로드 데이터에는 데이터 집합](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6662c-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="6662c-105">이 항목의 예제에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6662c-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="6662c-106">이 항목의 예제에서 다음을 사용 하 여 `using` / `Imports` 문:</span><span class="sxs-lookup"><span data-stu-id="6662c-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="6662c-107">자세한 내용은 참조 [하는 방법: Visual Studio에서 데이터 집합 프로젝트에 LINQ 만들기](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6662c-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="average"></a><span data-ttu-id="6662c-108">평균</span><span class="sxs-lookup"><span data-stu-id="6662c-108">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="6662c-109">예제</span><span class="sxs-lookup"><span data-stu-id="6662c-109">Example</span></span>  
 <span data-ttu-id="6662c-110">이 예제에서는 <xref:System.Linq.Enumerable.Average%2A> 메서드를 사용하여 각 스타일의 평균 제품 가격을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="6662c-110">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="6662c-111">예제</span><span class="sxs-lookup"><span data-stu-id="6662c-111">Example</span></span>  
 <span data-ttu-id="6662c-112">이 예제에서는 <xref:System.Linq.Enumerable.Average%2A>를 사용하여 각 연락처 ID의 평균 합계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6662c-112">This example uses <xref:System.Linq.Enumerable.Average%2A> to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="6662c-113">예제</span><span class="sxs-lookup"><span data-stu-id="6662c-113">Example</span></span>  
 <span data-ttu-id="6662c-114">이 예제에서는 <xref:System.Linq.Enumerable.Average%2A>를 사용하여 각 연락처의 평균 `TotalDue`를 가진 주문을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6662c-114">This example uses <xref:System.Linq.Enumerable.Average%2A> to get the orders with the average `TotalDue` for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="6662c-115">개수</span><span class="sxs-lookup"><span data-stu-id="6662c-115">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="6662c-116">예제</span><span class="sxs-lookup"><span data-stu-id="6662c-116">Example</span></span>  
 <span data-ttu-id="6662c-117">이 예제에서는 <xref:System.Linq.Enumerable.Count%2A>를 사용하여 연락처 ID와 각 연락처의 주문 수로 구성된 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6662c-117">This example uses <xref:System.Linq.Enumerable.Count%2A> to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countnested)]
 [!code-vb[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="6662c-118">예제</span><span class="sxs-lookup"><span data-stu-id="6662c-118">Example</span></span>  
 <span data-ttu-id="6662c-119">이 예제에서는 색으로 제품을 그룹화한 다음 <xref:System.Linq.Enumerable.Count%2A>를 사용하여 각 색 그룹의 제품 수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6662c-119">This example groups products by color and uses <xref:System.Linq.Enumerable.Count%2A> to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="max"></a><span data-ttu-id="6662c-120">최대값</span><span class="sxs-lookup"><span data-stu-id="6662c-120">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="6662c-121">예제</span><span class="sxs-lookup"><span data-stu-id="6662c-121">Example</span></span>  
 <span data-ttu-id="6662c-122">이 예제에서는 <xref:System.Linq.Enumerable.Max%2A> 메서드를 사용하여 각 연락처 ID의 최대 합계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6662c-122">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="6662c-123">예제</span><span class="sxs-lookup"><span data-stu-id="6662c-123">Example</span></span>  
 <span data-ttu-id="6662c-124">이 예제에서는 <xref:System.Linq.Enumerable.Max%2A> 메서드를 사용하여 각 연락처 ID에 대해 최대 `TotalDue`를 가진 주문을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6662c-124">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest `TotalDue` for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="6662c-125">최소값</span><span class="sxs-lookup"><span data-stu-id="6662c-125">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="6662c-126">예제</span><span class="sxs-lookup"><span data-stu-id="6662c-126">Example</span></span>  
 <span data-ttu-id="6662c-127">이 예제에서는 <xref:System.Linq.Enumerable.Min%2A> 메서드를 사용하여 각 연락처 ID의 최소 합계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6662c-127">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="6662c-128">예제</span><span class="sxs-lookup"><span data-stu-id="6662c-128">Example</span></span>  
 <span data-ttu-id="6662c-129">이 예제에서는 <xref:System.Linq.Enumerable.Min%2A> 메서드를 사용하여 각 연락처 ID에 대해 최소 합계를 가진 주문을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6662c-129">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="6662c-130">Sum</span><span class="sxs-lookup"><span data-stu-id="6662c-130">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="6662c-131">예제</span><span class="sxs-lookup"><span data-stu-id="6662c-131">Example</span></span>  
 <span data-ttu-id="6662c-132">이 예제에서는 <xref:System.Linq.Enumerable.Sum%2A> 메서드를 사용하여 각 연락처 ID의 합계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6662c-132">This example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="6662c-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6662c-133">See Also</span></span>  
 [<span data-ttu-id="6662c-134">데이터를 데이터 집합에 로드</span><span class="sxs-lookup"><span data-stu-id="6662c-134">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="6662c-135">LINQ to DataSet 예제</span><span class="sxs-lookup"><span data-stu-id="6662c-135">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="6662c-136">표준 쿼리 연산자 개요</span><span class="sxs-lookup"><span data-stu-id="6662c-136">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
