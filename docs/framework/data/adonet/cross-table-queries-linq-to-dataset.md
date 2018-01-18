---
title: "크로스 테이블 쿼리(LINQ to DataSet)"
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
ms.assetid: 6819a16f-8656-41af-a54d-dfec0cb66366
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 0ede3cef32fc752239dfbed6a05adbdb1cc5bfbe
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="cross-table-queries-linq-to-dataset"></a><span data-ttu-id="83934-102">크로스 테이블 쿼리(LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="83934-102">Cross-Table Queries (LINQ to DataSet)</span></span>
<span data-ttu-id="83934-103">[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]에서는 단일 테이블 쿼리뿐 아니라 크로스 테이블 쿼리도 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83934-103">In addition to querying a single table, you can also perform cross-table queries in [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span> <span data-ttu-id="83934-104">사용 하 여 이렇게는 *조인*합니다.</span><span class="sxs-lookup"><span data-stu-id="83934-104">This is done by using a *join*.</span></span> <span data-ttu-id="83934-105">조인은 한 데이터 소스의 개체를 공통 특성(예: 제품 또는 연락처 ID)을 공유하는 다른 데이터 소스의 개체와 연결하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="83934-105">A join is the association of objects in one data source with objects that share a common attribute in another data source, such as a product or contact ID.</span></span> <span data-ttu-id="83934-106">개체 지향적 프로그래밍의 경우 각 개체에 다른 개체를 참조하는 멤버가 있으므로 개체 간의 관계를 탐색하기가 비교적 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="83934-106">In object-oriented programming, relationships between objects are relatively easy to navigate because each object has a member that references another object.</span></span> <span data-ttu-id="83934-107">그러나 외부 데이터베이스 테이블에서는 관계를 탐색하기가 쉽지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83934-107">In external database tables, however, navigating relationships is not as straightforward.</span></span> <span data-ttu-id="83934-108">데이터베이스 테이블에는 기본 제공 관계가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83934-108">Database tables do not contain built-in relationships.</span></span> <span data-ttu-id="83934-109">이러한 경우 조인 연산을 사용하여 각 소스의 요소를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83934-109">In these cases, the join operation can be used to match elements from each source.</span></span> <span data-ttu-id="83934-110">예를 들어 제품 정보와 판매 정보가 들어 있는 두 테이블이 있는 경우 조인 연산을 사용하여 동일한 판매 주문에 대한 판매 정보와 제품을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83934-110">For example, given two tables that contain product information and sales information, you could use a join operation to match sales information and products for the same sales order.</span></span>  
  
 <span data-ttu-id="83934-111">[!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] 프레임 워크는 두 개의 조인 연산자를 제공 <xref:System.Linq.Enumerable.Join%2A> 및 <xref:System.Linq.Enumerable.GroupJoin%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="83934-111">The [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] framework provides two join operators, <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A>.</span></span> <span data-ttu-id="83934-112">이러한 연산자는 수행 *동등 조인*: 즉, 두 개의 데이터와 일치 하는 조인 원본만 때 해당 키가 같은 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="83934-112">These operators perform *equi-joins*: that is, joins that match two data sources only when their keys are equal.</span></span> <span data-ttu-id="83934-113">반면 [!INCLUDE[tsql](../../../../includes/tsql-md.md)]은 `equals` 이외의 조인 연산자(예: `less than` 연산자)를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="83934-113">(By contrast, [!INCLUDE[tsql](../../../../includes/tsql-md.md)] supports join operators other than `equals`, such as the `less than` operator.)</span></span>  
  
 <span data-ttu-id="83934-114">관계형 데이터베이스 용어에서 <xref:System.Linq.Enumerable.Join%2A>은 내부 조인을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="83934-114">In relational database terms, <xref:System.Linq.Enumerable.Join%2A> implements an inner join.</span></span> <span data-ttu-id="83934-115">내부 조인은 상대 데이터 집합에 일치하는 항목이 있는 개체만 반환되는 조인입니다.</span><span class="sxs-lookup"><span data-stu-id="83934-115">An inner join is a type of join in which only those objects that have a match in the opposite data set are returned.</span></span>  
  
 <span data-ttu-id="83934-116"><xref:System.Linq.Enumerable.GroupJoin%2A> 연산자는 관계형 데이터베이스 용어에서 직접적으로 대응; 내부 조인 및 왼쪽된 우선 외부 조인의 상위 집합을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="83934-116">The <xref:System.Linq.Enumerable.GroupJoin%2A> operators have no direct equivalent in relational database terms; they implement a superset of inner joins and left outer joins.</span></span> <span data-ttu-id="83934-117">왼쪽된 우선 외부 조인 두 번째 컬렉션에서 연관 된 요소가 없는 경우에 첫 번째 (왼쪽된) 컬렉션의 각 요소를 반환 하는 조인이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83934-117">A left outer join is a join that returns each element of the first (left) collection, even if it has no correlated elements in the second collection.</span></span>  
  
 <span data-ttu-id="83934-118">조인에 대 한 자세한 내용은 참조 [Join 작업](http://msdn.microsoft.com/library/442d176d-028c-4beb-8d22-407d4ef89107)합니다.</span><span class="sxs-lookup"><span data-stu-id="83934-118">For more information about joins, see [Join Operations](http://msdn.microsoft.com/library/442d176d-028c-4beb-8d22-407d4ef89107).</span></span>  
  
## <a name="example"></a><span data-ttu-id="83934-119">예</span><span class="sxs-lookup"><span data-stu-id="83934-119">Example</span></span>  
 <span data-ttu-id="83934-120">다음 예제에서는 AdventureWorks 샘플 데이터베이스의 `SalesOrderHeader` 및 `SalesOrderDetail` 테이블에 대해 기존 방식의 조인을 수행하여 8월의 온라인 주문을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="83934-120">The following example performs a traditional join of the `SalesOrderHeader` and `SalesOrderDetail` tables from the AdventureWorks sample database to obtain online orders from the month of August.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#join)]
 [!code-vb[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a><span data-ttu-id="83934-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83934-121">See Also</span></span>  
 [<span data-ttu-id="83934-122">데이터 집합 쿼리</span><span class="sxs-lookup"><span data-stu-id="83934-122">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 [<span data-ttu-id="83934-123">단일 테이블 쿼리</span><span class="sxs-lookup"><span data-stu-id="83934-123">Single-Table Queries</span></span>](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)  
 [<span data-ttu-id="83934-124">형식화된 데이터 집합 쿼리</span><span class="sxs-lookup"><span data-stu-id="83934-124">Querying Typed DataSets</span></span>](../../../../docs/framework/data/adonet/querying-typed-datasets.md)  
 [<span data-ttu-id="83934-125">조인 작업</span><span class="sxs-lookup"><span data-stu-id="83934-125">Join Operations</span></span>](http://msdn.microsoft.com/library/442d176d-028c-4beb-8d22-407d4ef89107)  
 [<span data-ttu-id="83934-126">LINQ to DataSet 예제</span><span class="sxs-lookup"><span data-stu-id="83934-126">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
