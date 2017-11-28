---
title: "DataAdapter 및 DataReader"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc952ca2-ec19-46ab-9189-15174b52cb74
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 3e7a0af0b5fabdfacfcc825258242868b0fbb513
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="dataadapters-and-datareaders"></a><span data-ttu-id="ec2ef-102">DataAdapter 및 DataReader</span><span class="sxs-lookup"><span data-stu-id="ec2ef-102">DataAdapters and DataReaders</span></span>
<span data-ttu-id="ec2ef-103">ADO.NET을 사용 하 여 **DataReader** 를 데이터베이스에서 데이터의 읽기 전용, 정방향 전용 스트림을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec2ef-103">You can use the ADO.NET **DataReader** to retrieve a read-only, forward-only stream of data from a database.</span></span> <span data-ttu-id="ec2ef-104">쿼리 실행 되 고 요청할 때까지 클라이언트의 네트워크 버퍼에 저장 된 결과 반환 합니다. 사용 하 여는 **읽기** 의 메서드는 **DataReader**합니다.</span><span class="sxs-lookup"><span data-stu-id="ec2ef-104">Results are returned as the query executes, and are stored in the network buffer on the client until you request them using the **Read** method of the **DataReader**.</span></span> <span data-ttu-id="ec2ef-105">사용 하는 **DataReader** 가능한 즉시 데이터를 검색 하 고 기본적으로 응용 프로그램 성능을 향상 시킬 수 시스템 오버 헤드를 줄여 메모리에 한 번에 하나의 행을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec2ef-105">Using the **DataReader** can increase application performance both by retrieving data as soon as it is available, and (by default) storing only one row at a time in memory, reducing system overhead.</span></span>  
  
 <span data-ttu-id="ec2ef-106"><xref:System.Data.Common.DataAdapter>는 데이터 소스에서 데이터를 검색하고 <xref:System.Data.DataSet> 내의 테이블을 채우는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec2ef-106">A <xref:System.Data.Common.DataAdapter> is used to retrieve data from a data source and populate tables within a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="ec2ef-107">`DataAdapter`는 `DataSet`의 변경 내용을 다시 데이터 소스에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ec2ef-107">The `DataAdapter` also resolves changes made to the `DataSet` back to the data source.</span></span> <span data-ttu-id="ec2ef-108">`DataAdapter`는 .NET Framework 데이터 공급자의 `Connection` 개체를 사용하여 데이터 소스에 연결하며 `Command` 개체를 사용하여 데이터 소스에서 데이터를 검색하고 변경 내용을 데이터 소스에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ec2ef-108">The `DataAdapter` uses the `Connection` object of the .NET Framework data provider to connect to a data source, and it uses `Command` objects to retrieve data from and resolve changes to the data source.</span></span>  
  
 <span data-ttu-id="ec2ef-109">.NET Framework에 포함된 각 .NET Framework 데이터 공급자에는 <xref:System.Data.Common.DbDataReader> 및 <xref:System.Data.Common.DbDataAdapter> 개체가 있습니다. .NET Framework Data Provider for OLE DB에는 <xref:System.Data.OleDb.OleDbDataReader> 및 <xref:System.Data.OleDb.OleDbDataAdapter> 개체가 있고 .NET Framework Data Provider for SQL Server에는 <xref:System.Data.SqlClient.SqlDataReader> 및 <xref:System.Data.SqlClient.SqlDataAdapter> 개체가 있으며 .NET Framework Data Provider for ODBC에는 <xref:System.Data.Odbc.OdbcDataReader> 및 <xref:System.Data.Odbc.OdbcDataAdapter> 개체가 있고 .NET Framework Data Provider for Oracle에는 <xref:System.Data.OracleClient.OracleDataReader> 및 <xref:System.Data.OracleClient.OracleDataAdapter> 개체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec2ef-109">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbDataReader> and a <xref:System.Data.Common.DbDataAdapter> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbDataReader> and an <xref:System.Data.OleDb.OleDbDataAdapter> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlDataReader> and a <xref:System.Data.SqlClient.SqlDataAdapter> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcDataReader> and an <xref:System.Data.Odbc.OdbcDataAdapter> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleDataReader> and an <xref:System.Data.OracleClient.OracleDataAdapter> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ec2ef-110">단원 내용</span><span class="sxs-lookup"><span data-stu-id="ec2ef-110">In This Section</span></span>  
 [<span data-ttu-id="ec2ef-111">DataReader를 사용 하 여 데이터를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec2ef-111">Retrieving Data Using a DataReader</span></span>](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md)  
 <span data-ttu-id="ec2ef-112">ADO.NET 설명 **DataReader** 개체 및 스트림을 반환 하는 결과의 데이터 원본에서 사용 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="ec2ef-112">Describes the ADO.NET **DataReader** object and how to use it to return a stream of results from a data source.</span></span>  
  
 [<span data-ttu-id="ec2ef-113">DataAdapter에서 데이터 집합 채우기</span><span class="sxs-lookup"><span data-stu-id="ec2ef-113">Populating a DataSet from a DataAdapter</span></span>](../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 <span data-ttu-id="ec2ef-114">`DataSet`를 사용하여 테이블, 열 및 행으로 `DataAdapter`을 채우는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec2ef-114">Describes how to fill a `DataSet` with tables, columns, and rows by using a `DataAdapter`.</span></span>  
  
 [<span data-ttu-id="ec2ef-115">DataAdapter 매개 변수</span><span class="sxs-lookup"><span data-stu-id="ec2ef-115">DataAdapter Parameters</span></span>](../../../../docs/framework/data/adonet/dataadapter-parameters.md)  
 <span data-ttu-id="ec2ef-116">`DataAdapter`의 열 내용을 명령 매개 변수에 매핑하는 방법을 비롯하여 `DataSet`의 명령 속성에 매개 변수를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec2ef-116">Describes how to use parameters with the command properties of a `DataAdapter` including how to map the contents of a column in a `DataSet` to a command parameter.</span></span>  
  
 [<span data-ttu-id="ec2ef-117">데이터 집합에 기존 제약 조건 추가</span><span class="sxs-lookup"><span data-stu-id="ec2ef-117">Adding Existing Constraints to a DataSet</span></span>](../../../../docs/framework/data/adonet/adding-existing-constraints-to-a-dataset.md)  
 <span data-ttu-id="ec2ef-118">`DataSet`에 기존 제약 조건을 추가하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec2ef-118">Describes how to add existing constraints to a `DataSet`.</span></span>  
  
 [<span data-ttu-id="ec2ef-119">DataAdapter DataTable 및 DataColumn 매핑</span><span class="sxs-lookup"><span data-stu-id="ec2ef-119">DataAdapter DataTable and DataColumn Mappings</span></span>](../../../../docs/framework/data/adonet/dataadapter-datatable-and-datacolumn-mappings.md)  
 <span data-ttu-id="ec2ef-120">`DataTableMappings`에 대해 `ColumnMappings` 및 `DataAdapter`를 설정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec2ef-120">Describes how to set up `DataTableMappings` and `ColumnMappings` for a `DataAdapter`.</span></span>  
  
 [<span data-ttu-id="ec2ef-121">쿼리 결과 통해 페이징</span><span class="sxs-lookup"><span data-stu-id="ec2ef-121">Paging Through a Query Result</span></span>](../../../../docs/framework/data/adonet/paging-through-a-query-result.md)  
 <span data-ttu-id="ec2ef-122">쿼리 결과를 데이터 페이지로 보는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ec2ef-122">Provides an example of viewing the results of a query as pages of data.</span></span>  
  
 [<span data-ttu-id="ec2ef-123">DataAdapter로 데이터 원본 업데이트</span><span class="sxs-lookup"><span data-stu-id="ec2ef-123">Updating Data Sources with DataAdapters</span></span>](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 <span data-ttu-id="ec2ef-124">`DataAdapter`를 사용하여 `DataSet`의 변경 내용을 데이터베이스에 적용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec2ef-124">Describes how to use a `DataAdapter` to resolve changes in a `DataSet` back to the database.</span></span>  
  
 [<span data-ttu-id="ec2ef-125">DataAdapter 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="ec2ef-125">Handling DataAdapter Events</span></span>](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)  
 <span data-ttu-id="ec2ef-126">`DataAdapter` 이벤트와 이벤트 사용 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec2ef-126">Describes `DataAdapter` events and how to use them.</span></span>  
  
 [<span data-ttu-id="ec2ef-127">Dataadapter를 사용 하 여 일괄 처리 작업 수행</span><span class="sxs-lookup"><span data-stu-id="ec2ef-127">Performing Batch Operations Using DataAdapters</span></span>](../../../../docs/framework/data/adonet/performing-batch-operations-using-dataadapters.md)  
 <span data-ttu-id="ec2ef-128">`DataSet`의 업데이트를 적용할 때 SQL Server로의 라운드트립 횟수를 줄여 응용 프로그램의 성능을 향상시키는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec2ef-128">Describes enhancing application performance by reducing the number of round trips to SQL Server when applying updates from the `DataSet`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec2ef-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ec2ef-129">See Also</span></span>  
 [<span data-ttu-id="ec2ef-130">데이터 소스에 연결</span><span class="sxs-lookup"><span data-stu-id="ec2ef-130">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [<span data-ttu-id="ec2ef-131">명령 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="ec2ef-131">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="ec2ef-132">트랜잭션 및 동시성</span><span class="sxs-lookup"><span data-stu-id="ec2ef-132">Transactions and Concurrency</span></span>](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [<span data-ttu-id="ec2ef-133">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="ec2ef-133">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="ec2ef-134">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="ec2ef-134">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
