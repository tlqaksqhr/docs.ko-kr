---
title: "명령 및 매개 변수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b623f810-d871-49a5-b0f5-078cc3c34db6
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: f28f4ed728ee429a691a0a19b3fc143ac0e832ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="commands-and-parameters"></a><span data-ttu-id="6b95f-102">명령 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="6b95f-102">Commands and Parameters</span></span>
<span data-ttu-id="6b95f-103">데이터 소스에 대한 연결을 설정한 후에는 <xref:System.Data.Common.DbCommand> 개체를 사용하여 명령을 실행하고 데이터 소스에서 결과를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b95f-103">After establishing a connection to a data source, you can execute commands and return results from the data source using a <xref:System.Data.Common.DbCommand> object.</span></span> <span data-ttu-id="6b95f-104">명령은 현재 사용하는 .NET Framework 데이터 공급자의 명령 생성자 중 하나를 사용하여 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b95f-104">You can create a command using one of the command constructors for the .NET Framework data provider you are working with.</span></span> <span data-ttu-id="6b95f-105">생성자는 데이터 소스에서 실행하는 SQL 문, <xref:System.Data.Common.DbConnection> 개체 또는 <xref:System.Data.Common.DbTransaction> 개체와 같은 선택적 인수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b95f-105">Constructors can take optional arguments, such as an SQL statement to execute at the data source, a <xref:System.Data.Common.DbConnection> object, or a <xref:System.Data.Common.DbTransaction> object.</span></span> <span data-ttu-id="6b95f-106">이러한 개체를 명령의 속성으로 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b95f-106">You can also configure those objects as properties of the command.</span></span> <span data-ttu-id="6b95f-107">또한 <xref:System.Data.Common.DbConnection.CreateCommand%2A> 개체의 `DbConnection` 메서드를 사용하여 특정 연결에 대한 명령을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b95f-107">You can also create a command for a particular connection using the <xref:System.Data.Common.DbConnection.CreateCommand%2A> method of a `DbConnection` object.</span></span> <span data-ttu-id="6b95f-108">명령을 통해 실행되는 SQL 문은 <xref:System.Data.Common.DbCommand.CommandText%2A> 속성을 사용하여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b95f-108">The SQL statement being executed by the command can be configured using the <xref:System.Data.Common.DbCommand.CommandText%2A> property.</span></span>  
  
 <span data-ttu-id="6b95f-109">.NET Framework에 포함된 각 .NET Framework 데이터 공급자에는 `Command` 개체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b95f-109">Each .NET Framework data provider included with the .NET Framework has a `Command` object.</span></span> <span data-ttu-id="6b95f-110">.NET Framework Data Provider for OLE DB에는 <xref:System.Data.OleDb.OleDbCommand> 개체가 있고, .NET Framework Data Provider for SQL Server에는 <xref:System.Data.SqlClient.SqlCommand> 개체가 있으며, .NET Framework Data Provider for ODBC와 .NET Framework Data Provider for Oracle에는 각각 <xref:System.Data.Odbc.OdbcCommand> 개체와 <xref:System.Data.OracleClient.OracleCommand> 개체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b95f-110">The .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbCommand> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlCommand> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcCommand> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleCommand> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6b95f-111">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="6b95f-111">In This Section</span></span>  
 [<span data-ttu-id="6b95f-112">명령 실행</span><span class="sxs-lookup"><span data-stu-id="6b95f-112">Executing a Command</span></span>](../../../../docs/framework/data/adonet/executing-a-command.md)  
 <span data-ttu-id="6b95f-113">ADO.NET `Command` 개체 및 이 개체를 사용하여 데이터 소스에 대해 쿼리와 명령을 실행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6b95f-113">Describes the ADO.NET `Command` object and how to use it to execute queries and commands against a data source.</span></span>  
  
 [<span data-ttu-id="6b95f-114">매개 변수 및 매개 변수 데이터 형식 구성</span><span class="sxs-lookup"><span data-stu-id="6b95f-114">Configuring Parameters and Parameter Data Types</span></span>](../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 <span data-ttu-id="6b95f-115">방향, 데이터 형식 및 매개 변수 구문을 포함하여 `Command` 매개 변수로 작업하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6b95f-115">Describes working with `Command` parameters, including direction, data types, and parameter syntax.</span></span>  
  
 [<span data-ttu-id="6b95f-116">CommandBuilder를 사용하여 명령 생성</span><span class="sxs-lookup"><span data-stu-id="6b95f-116">Generating Commands with CommandBuilders</span></span>](../../../../docs/framework/data/adonet/generating-commands-with-commandbuilders.md)  
 <span data-ttu-id="6b95f-117">명령 작성기를 사용하여 단일 테이블 SELECT 명령이 들어 있는 `DataAdapter`에 대해 INSERT, UPDATE 및 DELETE 명령을 자동으로 생성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6b95f-117">Describes how to use command builders to automatically generate INSERT, UPDATE, and DELETE commands for a `DataAdapter` that has a single-table SELECT command.</span></span>  
  
 [<span data-ttu-id="6b95f-118">데이터베이스에서 단일 값 가져오기</span><span class="sxs-lookup"><span data-stu-id="6b95f-118">Obtaining a Single Value from a Database</span></span>](../../../../docs/framework/data/adonet/obtaining-a-single-value-from-a-database.md)  
 <span data-ttu-id="6b95f-119">`ExecuteScalar` 개체의 `Command` 메서드를 사용하여 데이터베이스 쿼리에서 단일 값을 반환하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6b95f-119">Describes how to use the `ExecuteScalar` method of a `Command` object to return a single value from a database query.</span></span>  
  
 [<span data-ttu-id="6b95f-120">명령을 사용하여 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="6b95f-120">Using Commands to Modify Data</span></span>](../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)  
 <span data-ttu-id="6b95f-121">데이터 공급자를 사용하여 저장 프로시저 또는 DDL(데이터 정의 언어) 문을 실행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6b95f-121">Describes how to use a data provider to execute stored procedures or data definition language (DDL) statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b95f-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b95f-122">See Also</span></span>  
 [<span data-ttu-id="6b95f-123">DataAdapter 및 DataReader</span><span class="sxs-lookup"><span data-stu-id="6b95f-123">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="6b95f-124">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="6b95f-124">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="6b95f-125">데이터 소스에 연결</span><span class="sxs-lookup"><span data-stu-id="6b95f-125">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [<span data-ttu-id="6b95f-126">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="6b95f-126">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
