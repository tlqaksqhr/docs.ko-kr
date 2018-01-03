---
title: "데이터를 데이터 집합에 로드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 471a13b5d209def227bf8bc57b1551550b76a0c8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="loading-data-into-a-dataset"></a><span data-ttu-id="dbf37-102">데이터를 데이터 집합에 로드</span><span class="sxs-lookup"><span data-stu-id="dbf37-102">Loading Data Into a DataSet</span></span>
<span data-ttu-id="dbf37-103"><xref:System.Data.DataSet> 개체를 먼저 채워야 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]을 사용하여 해당 개체를 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbf37-103">A <xref:System.Data.DataSet> object must first be populated before you can query over it with [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span> <span data-ttu-id="dbf37-104"><xref:System.Data.DataSet>은 여러 방법으로 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbf37-104">There are several different ways to populate the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="dbf37-105">예를 들어, [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)]를 사용하여 데이터베이스를 쿼리한 다음 그 결과를 <xref:System.Data.DataSet>에 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbf37-105">For example, you can use [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] to query the database and load the results into the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="dbf37-106">자세한 내용은 [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dbf37-106">For more information, see [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).</span></span>  
  
 <span data-ttu-id="dbf37-107"><xref:System.Data.DataSet>에 데이터를 로드하는 일반적인 방법 중에는 <xref:System.Data.Common.DataAdapter> 클래스를 사용하여 데이터베이스에서 데이터를 검색하는 방법도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbf37-107">Another common way to load data into a <xref:System.Data.DataSet> is to use the <xref:System.Data.Common.DataAdapter> class to retrieve data from the database.</span></span> <span data-ttu-id="dbf37-108">다음 예제에서 이 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dbf37-108">This is illustrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dbf37-109">예제</span><span class="sxs-lookup"><span data-stu-id="dbf37-109">Example</span></span>  
 <span data-ttu-id="dbf37-110">이 예제에서는 <xref:System.Data.Common.DataAdapter>를 사용하여 AdventureWorks 데이터베이스에서 2002년 판매 정보를 쿼리한 다음 그 결과를 <xref:System.Data.DataSet>에 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf37-110">This example uses a <xref:System.Data.Common.DataAdapter> to query the AdventureWorks database for sales information from the year 2002, and loads the results into a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="dbf37-111"><xref:System.Data.DataSet>이 채워지면 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]을 사용하여 쿼리를 다시 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbf37-111">After the <xref:System.Data.DataSet> has been populated, you can write queries against it by using [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span> <span data-ttu-id="dbf37-112">`FillDataSet` 에 쿼리 예에서이 예제의 메서드를 사용 하는 [LINQ to DataSet 예제](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf37-112">The `FillDataSet` method in this example is used in the example queries in [LINQ to DataSet Examples](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md).</span></span> <span data-ttu-id="dbf37-113">자세한 내용은 참조 [데이터 집합 쿼리](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dbf37-113">For more information, see [Querying DataSets](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md).</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a><span data-ttu-id="dbf37-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dbf37-114">See Also</span></span>  
 [<span data-ttu-id="dbf37-115">LINQ to DataSet 개요</span><span class="sxs-lookup"><span data-stu-id="dbf37-115">LINQ to DataSet Overview</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-overview.md)  
 [<span data-ttu-id="dbf37-116">데이터 집합 쿼리</span><span class="sxs-lookup"><span data-stu-id="dbf37-116">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 [<span data-ttu-id="dbf37-117">LINQ to DataSet 예제</span><span class="sxs-lookup"><span data-stu-id="dbf37-117">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
