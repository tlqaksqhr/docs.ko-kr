---
title: "쿼리에서 DataTable 만들기(LINQ to DataSet)"
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
ms.assetid: 1b97afeb-03f8-41e2-8eb3-58aff65f7d18
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 2fb08240c1d3ad58b18733097d0dae10775c0cd5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="creating-a-datatable-from-a-query-linq-to-dataset"></a><span data-ttu-id="5fce1-102">쿼리에서 DataTable 만들기(LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="5fce1-102">Creating a DataTable From a Query (LINQ to DataSet)</span></span>
<span data-ttu-id="5fce1-103">데이터 바인딩에는 일반적으로 <xref:System.Data.DataTable> 개체가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-103">Data binding is a common use of <xref:System.Data.DataTable> object.</span></span> <span data-ttu-id="5fce1-104"><xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 메서드는 쿼리 결과를 받아서 나중에 데이터 바인딩에 사용할 수 있도록 데이터를 <xref:System.Data.DataTable>에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-104">The <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method takes the results of a query and copies the data into a <xref:System.Data.DataTable>, which can then be used for data binding.</span></span> <span data-ttu-id="5fce1-105">데이터 작업이 수행되면 새 <xref:System.Data.DataTable>이 소스 <xref:System.Data.DataTable>에 다시 병합됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-105">When the data operations have been performed, the new <xref:System.Data.DataTable> is merged back into the source <xref:System.Data.DataTable>.</span></span>  
  
 <span data-ttu-id="5fce1-106"><xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 메서드는 다음 프로세스를 사용하여 쿼리에서 <xref:System.Data.DataTable>을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-106">The <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method uses the following process to create a <xref:System.Data.DataTable> from a query:</span></span>  
  
1.  <span data-ttu-id="5fce1-107"><xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 메서드는 소스 테이블(<xref:System.Data.DataTable> 인터페이스를 구현한 <xref:System.Data.DataTable> 개체)에서 <xref:System.Linq.IQueryable%601>을 복제합니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-107">The <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method clones a <xref:System.Data.DataTable> from the source table (a <xref:System.Data.DataTable> object that implements the <xref:System.Linq.IQueryable%601> interface).</span></span> <span data-ttu-id="5fce1-108"><xref:System.Collections.IEnumerable> 소스는 일반적으로 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 식 또는 메서드 쿼리를 통해 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-108">The <xref:System.Collections.IEnumerable> source has generally originated from a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] expression or method query.</span></span>  
  
2.  <span data-ttu-id="5fce1-109">복제된 <xref:System.Data.DataTable>의 스키마는 소스 테이블의 첫 번째 열거된 <xref:System.Data.DataRow> 개체 열을 통해 작성되며 복제된 테이블의 이름은 소스 테이블 이름에 "query"라는 단어를 추가하여 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-109">The schema of the cloned <xref:System.Data.DataTable> is built from the columns of the first enumerated <xref:System.Data.DataRow> object in the source table and the name of the cloned table is the name of the source table with the word "query" appended to it.</span></span>  
  
3.  <span data-ttu-id="5fce1-110">소스 테이블에서 각 행의 내용은 새 <xref:System.Data.DataRow> 개체에 복사된 다음 복제 테이블에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-110">For each row in the source table, the content of the row is copied into a new <xref:System.Data.DataRow> object, which is then inserted into the cloned table.</span></span> <span data-ttu-id="5fce1-111"><xref:System.Data.DataRow.RowState%2A> 및 <xref:System.Data.DataRow.RowError%2A> 속성은 복사 작업 동안 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-111">The <xref:System.Data.DataRow.RowState%2A> and <xref:System.Data.DataRow.RowError%2A> properties are preserved across the copy operation.</span></span> <span data-ttu-id="5fce1-112">소스의 <xref:System.ArgumentException> 개체가 다른 테이블의 개체이면 <xref:System.Data.DataRow>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-112">An <xref:System.ArgumentException> is thrown if the <xref:System.Data.DataRow> objects in the source are from different tables.</span></span>  
  
4.  <span data-ttu-id="5fce1-113">쿼리 가능한 입력 테이블의 모든 <xref:System.Data.DataTable> 개체가 복사된 후 복제된 <xref:System.Data.DataRow>이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-113">The cloned <xref:System.Data.DataTable> is returned after all <xref:System.Data.DataRow> objects in the input queryable table have been copied.</span></span> <span data-ttu-id="5fce1-114">소스 시퀀스에 <xref:System.Data.DataRow> 개체가 없는 경우 이 메서드는 빈 <xref:System.Data.DataTable>을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-114">If the source sequence does not contain any <xref:System.Data.DataRow> objects, the method returns an empty <xref:System.Data.DataTable>.</span></span>  
  
 <span data-ttu-id="5fce1-115"><xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 메서드를 호출하면 실행할 소스 테이블에 쿼리가 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-115">Note that calling the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method will cause the query bound to the source table to execute.</span></span>  
  
 <span data-ttu-id="5fce1-116">소스 테이블의 행에 null 참조 또는 nullable 값 형식이 있으면 <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 메서드가 해당 값을 <xref:System.DBNull.Value>로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-116">When the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method encounters either a null reference or nullable value type in a row in the source table, it replaces the value with <xref:System.DBNull.Value>.</span></span> <span data-ttu-id="5fce1-117">이 방법을 통해 반환된 <xref:System.Data.DataTable>에서 null 값이 올바르게 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-117">This way, null values are handled correctly in the returned <xref:System.Data.DataTable>.</span></span>  
  
 <span data-ttu-id="5fce1-118">참고: <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 메서드는 여러 <xref:System.Data.DataTable> 또는 <xref:System.Data.DataSet> 개체에서 행을 반환할 수 있는 쿼리를 입력으로 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-118">Note: The <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method accepts as input a query that can return rows from multiple <xref:System.Data.DataTable> or <xref:System.Data.DataSet> objects.</span></span> <span data-ttu-id="5fce1-119"><xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 메서드는 소스 <xref:System.Data.DataTable> 또는 <xref:System.Data.DataSet> 개체의 데이터만 반환되는 <xref:System.Data.DataTable>에 복사하며 속성은 복사하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-119">The <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method will copy the data but not the properties from the source <xref:System.Data.DataTable> or <xref:System.Data.DataSet> objects to the returned <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="5fce1-120"><xref:System.Data.DataTable> 및 <xref:System.Data.DataTable.Locale%2A>과 같은 반환되는 <xref:System.Data.DataTable.TableName%2A>에 대한 속성은 명시적으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-120">You will need to explicitly set the properties on the returned <xref:System.Data.DataTable>, such as <xref:System.Data.DataTable.Locale%2A> and <xref:System.Data.DataTable.TableName%2A>.</span></span>  
  
 <span data-ttu-id="5fce1-121">다음 예제에서는 SalesOrderHeader 테이블에 2001년 8월 8일 이후 주문을 쿼리한 다음 <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 메서드를 사용하여 해당 쿼리에서 <xref:System.Data.DataTable>을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-121">The following example queries the SalesOrderHeader table for orders after August 8, 2001 and uses the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method to create a <xref:System.Data.DataTable> from that query.</span></span> <span data-ttu-id="5fce1-122">그런 다음 <xref:System.Data.DataTable>이 <xref:System.Windows.Forms.BindingSource>의 프록시 역할을 수행하는 <xref:System.Windows.Forms.DataGridView>에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-122">The <xref:System.Data.DataTable> is then bound to a <xref:System.Windows.Forms.BindingSource>, which acts as proxy for a <xref:System.Windows.Forms.DataGridView>.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CopyToDataTable1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#copytodatatable1)]
 [!code-vb[DP LINQ to DataSet Examples#CopyToDataTable1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#copytodatatable1)]  
  
## <a name="creating-a-custom-copytodatatablet-method"></a><span data-ttu-id="5fce1-123">사용자 지정 CopyToDataTable 만들기\<T > 메서드</span><span class="sxs-lookup"><span data-stu-id="5fce1-123">Creating a Custom CopyToDataTable\<T> Method</span></span>  
 <span data-ttu-id="5fce1-124">기존 <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 메서드는 제네릭 매개 변수 <xref:System.Collections.Generic.IEnumerable%601>가 `T` 형식인 <xref:System.Data.DataRow> 소스에서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-124">The existing <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> methods only operate on an <xref:System.Collections.Generic.IEnumerable%601> source where the generic parameter `T` is of type <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="5fce1-125">이 제한은 유용하지만 이로 인해 일련의 스칼라 형식, 익명 형식을 반환하는 쿼리 또는 테이블 조인을 수행하는 쿼리에서 테이블을 만들지 못하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-125">Although this is useful, it does not allow tables to be created from a sequence of scalar types, from queries that return anonymous types, or from queries that perform table joins.</span></span> <span data-ttu-id="5fce1-126">두 개의 사용자 지정을 구현 하는 방법의 예 `CopyToDataTable` 스칼라 또는 익명 형식의 시퀀스에서 테이블을 로드 하는 방법을 참조 [하는 방법: CopyToDataTable 구현\<T > 여기서는 제네릭 형식 T 일치 하지 않음 DataRow](../../../../docs/framework/data/adonet/implement-copytodatatable-where-type-not-a-datarow.md)s 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-126">For an example of how to implement two custom `CopyToDataTable` methods that load a table from a sequence of scalar or anonymous types, see [How to: Implement CopyToDataTable\<T> Where the Generic Type T Is Not a DataRow](../../../../docs/framework/data/adonet/implement-copytodatatable-where-type-not-a-datarow.md)s.</span></span>  
  
 <span data-ttu-id="5fce1-127">이 단원의 예제에서는 다음과 같은 사용자 지정 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-127">The examples in this section use the following custom types:</span></span>  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#ItemClass](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#itemclass)]
 [!code-vb[DP Custom CopyToDataTable Examples#ItemClass](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#itemclass)]  
  
### <a name="example"></a><span data-ttu-id="5fce1-128">예제</span><span class="sxs-lookup"><span data-stu-id="5fce1-128">Example</span></span>  
 <span data-ttu-id="5fce1-129">이 예제에서는 `SalesOrderHeader` 및 `SalesOrderDetail` 테이블에 대해 조인을 수행하여 8월의 온라인 주문을 가져오고 해당 쿼리에서 테이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-129">This example performs a join over the `SalesOrderHeader` and `SalesOrderDetail` tables to get online orders from the month of August and creates a table from the query.</span></span>  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#join)]
 [!code-vb[DP Custom CopyToDataTable Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#join)]  
  
### <a name="example"></a><span data-ttu-id="5fce1-130">예제</span><span class="sxs-lookup"><span data-stu-id="5fce1-130">Example</span></span>  
 <span data-ttu-id="5fce1-131">다음 예제에서는 가격이 9.99달러 이상인 항목의 컬렉션을 쿼리하고 쿼리 결과로부터 테이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-131">The following example queries a collection for items of price greater than $9.99 and creates a table from the query results.</span></span>  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#LoadItemsIntoTable](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#loaditemsintotable)]
 [!code-vb[DP Custom CopyToDataTable Examples#LoadItemsIntoTable](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#loaditemsintotable)]  
  
### <a name="example"></a><span data-ttu-id="5fce1-132">예제</span><span class="sxs-lookup"><span data-stu-id="5fce1-132">Example</span></span>  
 <span data-ttu-id="5fce1-133">다음 예제에서는 가격이 9.99달러 이상인 항목의 컬렉션을 쿼리하고 결과를 프로젝션합니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-133">The following example queries a collection for items of price greater than 9.99 and projects the results.</span></span> <span data-ttu-id="5fce1-134">반환된 일련의 익명 형식은 기존 테이블에 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-134">The returned sequence of anonymous types is loaded into an existing table.</span></span>  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#LoadItemsIntoExistingTable](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#loaditemsintoexistingtable)]
 [!code-vb[DP Custom CopyToDataTable Examples#LoadItemsIntoExistingTable](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#loaditemsintoexistingtable)]  
  
### <a name="example"></a><span data-ttu-id="5fce1-135">예제</span><span class="sxs-lookup"><span data-stu-id="5fce1-135">Example</span></span>  
 <span data-ttu-id="5fce1-136">다음 예제에서는 가격이 9.99달러 이상인 항목의 컬렉션을 쿼리하고 결과를 프로젝션합니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-136">The following example queries a collection for items of price greater than $9.99 and projects the results.</span></span> <span data-ttu-id="5fce1-137">반환된 일련의 익명 형식은 기존 테이블에 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-137">The returned sequence of anonymous types is loaded into an existing table.</span></span> <span data-ttu-id="5fce1-138">`Book` 및 `Movies` 형식은 `Item` 형식에서 파생되므로 테이블 스키마는 자동으로 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-138">The table schema is automatically expanded because the `Book` and `Movies` types are derived from the `Item` type.</span></span>  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#LoadItemsExpandSchema](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#loaditemsexpandschema)]
 [!code-vb[DP Custom CopyToDataTable Examples#LoadItemsExpandSchema](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#loaditemsexpandschema)]  
  
### <a name="example"></a><span data-ttu-id="5fce1-139">예제</span><span class="sxs-lookup"><span data-stu-id="5fce1-139">Example</span></span>  
 <span data-ttu-id="5fce1-140">다음 예제에서는 가격이 9.99달러 이상인 항목의 컬렉션을 쿼리하고 새 테이블에 로드되는 일련의 <xref:System.Double>을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5fce1-140">The following example queries a collection for items of price greater than $9.99 and returns a sequence of <xref:System.Double>, which is loaded into a new table.</span></span>  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#LoadScalarSequence](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#loadscalarsequence)]
 [!code-vb[DP Custom CopyToDataTable Examples#LoadScalarSequence](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#loadscalarsequence)]  
  
## <a name="see-also"></a><span data-ttu-id="5fce1-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5fce1-141">See Also</span></span>  
 [<span data-ttu-id="5fce1-142">프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="5fce1-142">Programming Guide</span></span>](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
 [<span data-ttu-id="5fce1-143">제네릭 Field 및 SetField 메서드</span><span class="sxs-lookup"><span data-stu-id="5fce1-143">Generic Field and SetField Methods</span></span>](../../../../docs/framework/data/adonet/generic-field-and-setfield-methods-linq-to-dataset.md)  
 [<span data-ttu-id="5fce1-144">LINQ to DataSet 예제</span><span class="sxs-lookup"><span data-stu-id="5fce1-144">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
