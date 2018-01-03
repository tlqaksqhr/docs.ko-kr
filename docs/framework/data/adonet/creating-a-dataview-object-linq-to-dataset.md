---
title: "DataView 개체 만들기(LINQ to DataSet)"
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
ms.assetid: 76057508-e12d-4779-a707-06a4c2568acf
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 2b8a4a1f0dc004957b64e3adb5d106c2cd4f413a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="creating-a-dataview-object-linq-to-dataset"></a><span data-ttu-id="d60a5-102">DataView 개체 만들기(LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="d60a5-102">Creating a DataView Object (LINQ to DataSet)</span></span>
<span data-ttu-id="d60a5-103"><xref:System.Data.DataView> 컨텍스트에서 두 가지 방법으로 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d60a5-103">There are two ways to create a <xref:System.Data.DataView> in the [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] context.</span></span> <span data-ttu-id="d60a5-104"><xref:System.Data.DataView>에 대한 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 쿼리를 사용하거나 형식화되었거나 형식화되지 않은 <xref:System.Data.DataTable>을 사용하여 <xref:System.Data.DataTable>를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d60a5-104">You can create a <xref:System.Data.DataView> from a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query over a <xref:System.Data.DataTable>, or you can create it from a typed or un-typed <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="d60a5-105">두 경우 모두 만듭니다는 <xref:System.Data.DataView> 중 하나를 사용 하 여는 <xref:System.Data.DataTableExtensions.AsDataView%2A> ; 확장 메서드 <xref:System.Data.DataView> 는에서 직접 생성할 수는 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 컨텍스트.</span><span class="sxs-lookup"><span data-stu-id="d60a5-105">In both cases, you create the <xref:System.Data.DataView> by using one of the <xref:System.Data.DataTableExtensions.AsDataView%2A> extension methods; <xref:System.Data.DataView> is not directly constructible in the [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] context.</span></span>  
  
 <span data-ttu-id="d60a5-106"><xref:System.Data.DataView>를 만든 후에 Windows Forms 응용 프로그램 또는 ASP.NET 응용 프로그램의 UI 컨트롤에 바인딩하거나 필터링 및 정렬 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d60a5-106">After the <xref:System.Data.DataView> has been created, you can bind it to a UI control in a Windows forms application or an ASP.NET application, or change the filtering and sorting settings.</span></span>  
  
 <span data-ttu-id="d60a5-107"><xref:System.Data.DataView>에서 만든 인덱스는 필터링 및 정렬과 같이 인덱스를 사용할 수 있는 작업의 성능을 크게 높여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d60a5-107"><xref:System.Data.DataView> constructs an index, which significantly increases the performance of operations that can use the index, such as filtering and sorting.</span></span> <span data-ttu-id="d60a5-108"><xref:System.Data.DataView>의 인덱스는 <xref:System.Data.DataView>가 만들어지거나 정렬 또는 필터링 정보가 수정될 때 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d60a5-108">The index for a <xref:System.Data.DataView> is built both when the <xref:System.Data.DataView> is created and when any of the sorting or filtering information is modified.</span></span> <span data-ttu-id="d60a5-109"><xref:System.Data.DataView>를 만든 다음 정렬 또는 필터링 정보를 설정하면 <xref:System.Data.DataView>가 만들어질 때와 정렬 또는 필터 속성이 수정될 때 각각 한 번씩 인덱스가 작성되므로 적어도 두 개의 인덱스가 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d60a5-109">Creating a <xref:System.Data.DataView> and then setting the sorting or filtering information later causes the index to be built at least twice: once when the <xref:System.Data.DataView> is created, and again when any of the sort or filter properties are modified.</span></span>  
  
 <span data-ttu-id="d60a5-110">필터링 및 정렬 하는 방법에 대 한 자세한 내용은 <xref:System.Data.DataView>, 참조 [DataView로 필터링](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md) 및 [DataView로 정렬](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d60a5-110">For more information about filtering and sorting with <xref:System.Data.DataView>, see [Filtering with DataView](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md) and [Sorting with DataView](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md).</span></span>  
  
## <a name="creating-dataview-from-a-linq-to-dataset-query"></a><span data-ttu-id="d60a5-111">LINQ to DataSet 쿼리에서 DataView 만들기</span><span class="sxs-lookup"><span data-stu-id="d60a5-111">Creating DataView from a LINQ to DataSet Query</span></span>  
 <span data-ttu-id="d60a5-112"><xref:System.Data.DataView> 개체는 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 쿼리 결과에서 만들어집니다. 여기서 결과는 <xref:System.Data.DataRow> 개체의 프로젝션입니다.</span><span class="sxs-lookup"><span data-stu-id="d60a5-112">A <xref:System.Data.DataView> object can be created from the results of a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query, where the results are a projection of <xref:System.Data.DataRow> objects.</span></span> <span data-ttu-id="d60a5-113">새로 만들어진 <xref:System.Data.DataView>는 자신을 만든 쿼리의 필터링 및 정렬 정보를 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="d60a5-113">The newly created <xref:System.Data.DataView> inherits the filtering and sorting information from the query it is created from.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d60a5-114">대부분의 경우 필터링 및 정렬에 사용되는 식은 파생 효과가 없어야 하고 명확해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d60a5-114">In most cases, the expressions used for filtering and sorting should not have side effects and must be deterministic.</span></span> <span data-ttu-id="d60a5-115">또한 정렬 및 필터링 작업이 여러 번 실행될 수 있으므로 이러한 식에는 실행 집합 번호에 따라 달라지는 논리가 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d60a5-115">Also, the expressions should not contain any logic that depend on a set number of executions, as the sorting and filtering operations may be executed any number of times.</span></span>  
  
 <span data-ttu-id="d60a5-116">익명 형식을 반환하는 쿼리 또는 조인 연산을 수행하는 쿼리에서는 <xref:System.Data.DataView>를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d60a5-116">Creating a <xref:System.Data.DataView> from a query that returns anonymous types or queries that perform join operations is not supported.</span></span>  
  
 <span data-ttu-id="d60a5-117"><xref:System.Data.DataView>를 만드는 데 사용하는 쿼리에서는 다음과 같은 쿼리 연산자만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d60a5-117">Only the following query operators are supported in a query used to create <xref:System.Data.DataView>:</span></span>  
  
-   <xref:System.Data.EnumerableRowCollectionExtensions.Cast%2A>  
  
-   <xref:System.Data.EnumerableRowCollectionExtensions.OrderBy%2A>  
  
-   <xref:System.Data.EnumerableRowCollectionExtensions.OrderByDescending%2A>  
  
-   <xref:System.Data.EnumerableRowCollectionExtensions.Select%2A>  
  
-   <xref:System.Data.EnumerableRowCollectionExtensions.ThenBy%2A>  
  
-   <xref:System.Data.EnumerableRowCollectionExtensions.ThenByDescending%2A>  
  
-   <xref:System.Data.EnumerableRowCollectionExtensions.Where%2A>  
  
 <span data-ttu-id="d60a5-118">경우는 <xref:System.Data.DataView> 에서 만든는 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 쿼리는 <xref:System.Data.EnumerableRowCollectionExtensions.Select%2A> 메서드는 마지막 방법은 쿼리에서 호출 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d60a5-118">Note that when a <xref:System.Data.DataView> is created from a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query the <xref:System.Data.EnumerableRowCollectionExtensions.Select%2A> method must be the final method called in the query.</span></span> <span data-ttu-id="d60a5-119">이 만드는 다음 예에서 확인할 수는 <xref:System.Data.DataView> 의 온라인 주문을 기준으로 총 주문 금액이 정렬:</span><span class="sxs-lookup"><span data-stu-id="d60a5-119">This is shown in the following example, which creates a <xref:System.Data.DataView> of online orders sorted by total due:</span></span>  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQuery1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromquery1)]
 [!code-vb[DP DataView Samples#CreateLDVFromQuery1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromquery1)]  
  
 <span data-ttu-id="d60a5-120">문자열 기반을 사용할 수도 있습니다 <xref:System.Data.DataView.RowFilter%2A> 및 <xref:System.Data.DataView.Sort%2A> 속성 필터 및 정렬 하는 <xref:System.Data.DataView> 쿼리에서 만든 후 합니다.</span><span class="sxs-lookup"><span data-stu-id="d60a5-120">You can also use the string-based <xref:System.Data.DataView.RowFilter%2A> and <xref:System.Data.DataView.Sort%2A> properties to filter and sort a <xref:System.Data.DataView> after it has been created from a query.</span></span> <span data-ttu-id="d60a5-121">이렇게 하면 쿼리에서 상속된 정렬 및 필터링 정보가 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="d60a5-121">Note that this will clear the sorting and filtering information inherited from the query.</span></span> <span data-ttu-id="d60a5-122">다음 예제에서는 'S'로 시작하는 성을 기준으로 필터링하는 <xref:System.Data.DataView> 쿼리에서 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d60a5-122">The following example creates a <xref:System.Data.DataView> from a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query that filters by last names that start with 'S'.</span></span> <span data-ttu-id="d60a5-123">성을 기준으로 오름차순으로 정렬한 다음 이름을 기준으로 내림차순으로 정렬하도록 문자열 기반 <xref:System.Data.DataView.Sort%2A> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d60a5-123">The string-based <xref:System.Data.DataView.Sort%2A> property is set to sort on last names in ascending order and then first names in descending order:</span></span>  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromquerystringsort)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromquerystringsort)]  
  
## <a name="creating-a-dataview-from-a-datatable"></a><span data-ttu-id="d60a5-124">DataTable에서 DataView 만들기</span><span class="sxs-lookup"><span data-stu-id="d60a5-124">Creating a DataView from a DataTable</span></span>  
 <span data-ttu-id="d60a5-125">만드는 외에도 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 쿼리에서 <xref:System.Data.DataView> 에서 개체를 만들 수는 <xref:System.Data.DataTable> 를 사용 하 여는 <xref:System.Data.DataTableExtensions.AsDataView%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="d60a5-125">In addition to being created from a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query, a <xref:System.Data.DataView> object can be created from a <xref:System.Data.DataTable> by using the <xref:System.Data.DataTableExtensions.AsDataView%2A> method.</span></span>  
  
 <span data-ttu-id="d60a5-126">다음 예제에서는 SalesOrderDetail 테이블에서 <xref:System.Data.DataView>를 만든 다음 <xref:System.Windows.Forms.BindingSource> 개체의 데이터 소스로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d60a5-126">The following example creates a <xref:System.Data.DataView> from the SalesOrderDetail table and sets it as the data source of a <xref:System.Windows.Forms.BindingSource> object.</span></span> <span data-ttu-id="d60a5-127">이 개체는 <xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 프록시 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="d60a5-127">This object acts as a proxy for a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromTable](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromtable)]
 [!code-vb[DP DataView Samples#CreateLDVFromTable](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromtable)]  
  
 <span data-ttu-id="d60a5-128"><xref:System.Data.DataView>에서 만들어진 <xref:System.Data.DataTable>에 필터링 및 정렬을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d60a5-128">Filtering and sorting can be set on the <xref:System.Data.DataView> after it has been created from a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="d60a5-129">다음 예제에서는 Contact 테이블에서 <xref:System.Data.DataView>를 만든 다음 성을 기준으로 오름차순으로 정렬하고, 이름을 기준으로 내림차순으로 정렬하도록 <xref:System.Data.DataView.Sort%2A> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d60a5-129">The following example creates a <xref:System.Data.DataView> from the Contact table and sets the <xref:System.Data.DataView.Sort%2A> property to sort on last names in ascending order and then first names in descending order:</span></span>  
  
 [!code-csharp[DP DataView Samples#LDVStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvstringsort)]
 [!code-vb[DP DataView Samples#LDVStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvstringsort)]  
  
 <span data-ttu-id="d60a5-130">그러나 쿼리에서 <xref:System.Data.DataView.RowFilter%2A>를 만든 후에 <xref:System.Data.DataView.Sort%2A> 또는 <xref:System.Data.DataView> 속성을 설정하면 필터링 및 정렬 작업을 지원하기 위해 <xref:System.Data.DataView>에서 인덱스가 생성되므로 성능이 저하됩니다.</span><span class="sxs-lookup"><span data-stu-id="d60a5-130">However, there is a performance loss that comes with setting the <xref:System.Data.DataView.RowFilter%2A> or <xref:System.Data.DataView.Sort%2A> property after the <xref:System.Data.DataView> has been created from a query, because <xref:System.Data.DataView> constructs an index to support filtering and sorting operations.</span></span> <span data-ttu-id="d60a5-131"><xref:System.Data.DataView.RowFilter%2A> 또는 <xref:System.Data.DataView.Sort%2A> 속성을 설정하면 데이터에 대한 인덱스가 다시 작성되므로 응용 프로그램에 오버헤드가 발생하여 성능이 저하됩니다.</span><span class="sxs-lookup"><span data-stu-id="d60a5-131">Setting the <xref:System.Data.DataView.RowFilter%2A> or <xref:System.Data.DataView.Sort%2A> property rebuilds the index for the data, adding overhead to your application and decreasing performance.</span></span> <span data-ttu-id="d60a5-132">가능하면 <xref:System.Data.DataView>를 처음 만들 때 필터링 및 정렬 정보를 지정하고 이후에는 수정하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d60a5-132">When possible, it is better to specify the filtering and sorting information when you first create the <xref:System.Data.DataView> and avoid modifying it afterwards.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d60a5-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d60a5-133">See Also</span></span>  
 [<span data-ttu-id="d60a5-134">데이터 바인딩 및 LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="d60a5-134">Data Binding and LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)  
 [<span data-ttu-id="d60a5-135">DataView로 필터링</span><span class="sxs-lookup"><span data-stu-id="d60a5-135">Filtering with DataView</span></span>](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md)  
 [<span data-ttu-id="d60a5-136">DataView로 정렬</span><span class="sxs-lookup"><span data-stu-id="d60a5-136">Sorting with DataView</span></span>](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md)
