---
title: ADO.NET 코드 예제
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology:
- dotnet-ado
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: c119657a-9ce6-4940-91e4-ac1d5f0d9584
caps.latest.revision: 7
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 8fec055db7069a213b31b9f4443b2f0e7467dd7b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="adonet-code-examples"></a><span data-ttu-id="7ad4c-102">ADO.NET 코드 예제</span><span class="sxs-lookup"><span data-stu-id="7ad4c-102">ADO.NET code examples</span></span>
<span data-ttu-id="7ad4c-103">이 항목에 나열된 코드에서는 다음과 같은 ADO.NET 기술을 사용하여 데이터베이스에서 데이터를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-103">The code listings in this topic demonstrate how to retrieve data from a database by using the following ADO.NET technologies:</span></span>

- <span data-ttu-id="7ad4c-104">ADO.NET 데이터 공급자</span><span class="sxs-lookup"><span data-stu-id="7ad4c-104">ADO.NET data providers:</span></span>

  - <span data-ttu-id="7ad4c-105">[SqlClient](#sqlclient) (`System.Data.SqlClient`)</span><span class="sxs-lookup"><span data-stu-id="7ad4c-105">[SqlClient](#sqlclient) (`System.Data.SqlClient`)</span></span>

  - <span data-ttu-id="7ad4c-106">[OleDb](#oledb) (`System.Data.OleDb`)</span><span class="sxs-lookup"><span data-stu-id="7ad4c-106">[OleDb](#oledb) (`System.Data.OleDb`)</span></span>

  - <span data-ttu-id="7ad4c-107">[Odbc](#odbc) (`System.Data.Odbc`)</span><span class="sxs-lookup"><span data-stu-id="7ad4c-107">[Odbc](#odbc) (`System.Data.Odbc`)</span></span>

  - <span data-ttu-id="7ad4c-108">[OracleClient](#oracleclient) (`System.Data.OracleClient`)</span><span class="sxs-lookup"><span data-stu-id="7ad4c-108">[OracleClient](#oracleclient) (`System.Data.OracleClient`)</span></span>

- <span data-ttu-id="7ad4c-109">ADO.NET Entity Framework:</span><span class="sxs-lookup"><span data-stu-id="7ad4c-109">ADO.NET Entity Framework:</span></span>

  - [<span data-ttu-id="7ad4c-110">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="7ad4c-110">LINQ to Entities</span></span>](#linq-to-entities)

  - [<span data-ttu-id="7ad4c-111">형식화 된 ObjectQuery</span><span class="sxs-lookup"><span data-stu-id="7ad4c-111">Typed ObjectQuery</span></span>](#typed-objectquery)

  - <span data-ttu-id="7ad4c-112">[EntityClient](#entityclient) (`System.Data.EntityClient`)</span><span class="sxs-lookup"><span data-stu-id="7ad4c-112">[EntityClient](#entityclient) (`System.Data.EntityClient`)</span></span>

- [<span data-ttu-id="7ad4c-113">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="7ad4c-113">LINQ to SQL</span></span>](#linq-to-sql)

## <a name="adonet-data-provider-examples"></a><span data-ttu-id="7ad4c-114">ADO.NET 데이터 공급자 예제</span><span class="sxs-lookup"><span data-stu-id="7ad4c-114">ADO.NET data provider examples</span></span>
<span data-ttu-id="7ad4c-115">다음에 나열된 코드에서는 ADO.NET 데이터 공급자를 사용하여 데이터베이스에서 데이터를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-115">The following code listings demonstrate how to retrieve data from a database using ADO.NET data providers.</span></span> <span data-ttu-id="7ad4c-116">데이터는 `DataReader`에서 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-116">The data is returned in a `DataReader`.</span></span> <span data-ttu-id="7ad4c-117">자세한 내용은 참조 [DataReader를 사용 하 여 데이터 검색](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-117">For more information, see [Retrieving Data Using a DataReader](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md).</span></span>

### <a name="sqlclient"></a><span data-ttu-id="7ad4c-118">SqlClient</span><span class="sxs-lookup"><span data-stu-id="7ad4c-118">SqlClient</span></span>
<span data-ttu-id="7ad4c-119">이 예제 코드에서는에 연결할 수 있는지는 `Northwind` 에서 Microsoft SQL Server 예제 데이터베이스.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-119">The code in this example assumes that you can connect to the `Northwind` sample database on Microsoft SQL Server.</span></span> <span data-ttu-id="7ad4c-120">이 코드에서는 Products 테이블에서 행을 선택하는 <xref:System.Data.SqlClient.SqlCommand>를 만들고 <xref:System.Data.SqlClient.SqlParameter>를 추가하여 UnitPrice가 지정한 매개 변수 값(이 경우 5)보다 큰 행만 반환되도록 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-120">The code creates a <xref:System.Data.SqlClient.SqlCommand> to select rows from the Products table, adding a <xref:System.Data.SqlClient.SqlParameter> to restrict the results to rows with a UnitPrice greater than the specified parameter value, in this case 5.</span></span> <span data-ttu-id="7ad4c-121"><xref:System.Data.SqlClient.SqlConnection> 내부에서 열리면는 `using` 블록 리소스가 닫히고 삭제 코드가 종료 될 때 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-121">The <xref:System.Data.SqlClient.SqlConnection> is opened inside a `using` block, which ensures that resources are closed and disposed when the code exits.</span></span> <span data-ttu-id="7ad4c-122">이 코드에서는 <xref:System.Data.SqlClient.SqlDataReader>를 사용하여 명령을 실행하고 결과를 콘솔 창에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-122">The code executes the command by using a <xref:System.Data.SqlClient.SqlDataReader>, and displays the results in the console window.</span></span>

 [!code-csharp[DataWorks SampleApp.SqlClient#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.SqlClient/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.SqlClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.SqlClient/VB/source.vb#1)]

### <a name="oledb"></a><span data-ttu-id="7ad4c-123">OleDb</span><span class="sxs-lookup"><span data-stu-id="7ad4c-123">OleDb</span></span>
<span data-ttu-id="7ad4c-124">이 예제 코드에서는 Microsoft Access Northwind 샘플 데이터베이스에 연결할 수 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-124">The code in this example assumes that you can connect to the Microsoft Access Northwind sample database.</span></span> <span data-ttu-id="7ad4c-125">이 코드에서는 Products 테이블에서 행을 선택하는 <xref:System.Data.OleDb.OleDbCommand>를 만들고 <xref:System.Data.OleDb.OleDbParameter>를 추가하여 UnitPrice가 지정한 매개 변수 값(이 경우 5)보다 큰 행만 반환되도록 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-125">The code creates a <xref:System.Data.OleDb.OleDbCommand> to select rows from the Products table, adding a <xref:System.Data.OleDb.OleDbParameter> to restrict the results to rows with a UnitPrice greater than the specified parameter value, in this case 5.</span></span> <span data-ttu-id="7ad4c-126">코드가 종료될 때 리소스가 닫히고 삭제되도록 <xref:System.Data.OleDb.OleDbConnection>이 `using` 블록 안에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-126">The <xref:System.Data.OleDb.OleDbConnection> is opened inside of a `using` block, which ensures that resources are closed and disposed when the code exits.</span></span> <span data-ttu-id="7ad4c-127">이 코드에서는 <xref:System.Data.OleDb.OleDbDataReader>를 사용하여 명령을 실행하고 결과를 콘솔 창에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-127">The code executes the command by using a <xref:System.Data.OleDb.OleDbDataReader>, and displays the results in the console window.</span></span>

 [!code-csharp[DataWorks SampleApp.OleDb#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.OleDb/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.OleDb#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.OleDb/VB/source.vb#1)]

### <a name="odbc"></a><span data-ttu-id="7ad4c-128">Odbc</span><span class="sxs-lookup"><span data-stu-id="7ad4c-128">Odbc</span></span>
<span data-ttu-id="7ad4c-129">이 예제 코드에서는 Microsoft Access Northwind 샘플 데이터베이스에 연결할 수 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-129">The code in this example assumes that you can connect to the Microsoft Access Northwind sample database.</span></span> <span data-ttu-id="7ad4c-130">이 코드에서는 Products 테이블에서 행을 선택하는 <xref:System.Data.Odbc.OdbcCommand>를 만들고 <xref:System.Data.Odbc.OdbcParameter>를 추가하여 UnitPrice가 지정한 매개 변수 값(이 경우 5)보다 큰 행만 반환되도록 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-130">The code creates a <xref:System.Data.Odbc.OdbcCommand> to select rows from the Products table, adding a <xref:System.Data.Odbc.OdbcParameter> to restrict the results to rows with a UnitPrice greater than the specified parameter value, in this case 5.</span></span> <span data-ttu-id="7ad4c-131"><xref:System.Data.Odbc.OdbcConnection> 내부에서 열리면는 `using` 블록 리소스가 닫히고 삭제 코드가 종료 될 때 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-131">The <xref:System.Data.Odbc.OdbcConnection> is opened inside a `using` block, which ensures that resources are closed and disposed when the code exits.</span></span> <span data-ttu-id="7ad4c-132">이 코드에서는 <xref:System.Data.Odbc.OdbcDataReader>를 사용하여 명령을 실행하고 결과를 콘솔 창에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-132">The code executes the command by using a <xref:System.Data.Odbc.OdbcDataReader>, and displays the results in the console window.</span></span>

[!code-csharp[DataWorks SampleApp.Odbc#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.Odbc/CS/source.cs#1)] 
[!code-vb[DataWorks SampleApp.Odbc#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.Odbc/VB/source.vb#1)] 

### <a name="oracleclient"></a><span data-ttu-id="7ad4c-133">OracleClient</span><span class="sxs-lookup"><span data-stu-id="7ad4c-133">OracleClient</span></span>
<span data-ttu-id="7ad4c-134">이 예제 코드에서는 Oracle 서버에서 DEMO.CUSTOMER에 연결할 수 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-134">The code in this example assumes a connection to DEMO.CUSTOMER on an Oracle server.</span></span> <span data-ttu-id="7ad4c-135">또한 System.Data.OracleClient.dll에 대한 참조를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-135">You must also add a reference to the System.Data.OracleClient.dll.</span></span> <span data-ttu-id="7ad4c-136">이 코드는 <xref:System.Data.OracleClient.OracleDataReader>에 데이터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-136">The code returns the data in an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>

 [!code-csharp[DataWorks SampleApp.Oracle#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.Oracle/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.Oracle#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.Oracle/VB/source.vb#1)]

## <a name="entity-framework-examples"></a><span data-ttu-id="7ad4c-137">Entity Framework 예제</span><span class="sxs-lookup"><span data-stu-id="7ad4c-137">Entity Framework examples</span></span>
<span data-ttu-id="7ad4c-138">다음에 나열된 코드에서는 EDM(엔터티 데이터 모델)의 엔터티를 쿼리하여 데이터 소스에서 데이터를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-138">The following code listings demonstrate how to retrieve data from a data source by querying entities in an Entity Data Model (EDM).</span></span> <span data-ttu-id="7ad4c-139">이러한 예에서 사용 된 [Northwind 모델](http://msdn.microsoft.com/74521f8c-e974-48cb-8858-c08deff52638)합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-139">These examples use the [Northwind model](http://msdn.microsoft.com/74521f8c-e974-48cb-8858-c08deff52638).</span></span> <span data-ttu-id="7ad4c-140">자세한 내용은 참조 [Entity Framework 개요](../../../../docs/framework/data/adonet/ef/overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-140">For more information, see [Entity Framework Overview](../../../../docs/framework/data/adonet/ef/overview.md).</span></span>

### <a name="linq-to-entities"></a><span data-ttu-id="7ad4c-141">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="7ad4c-141">LINQ to Entities</span></span>
<span data-ttu-id="7ad4c-142">이 예제 코드에서는 LINQ 쿼리를 사용하여 CategoryID와 CategoryName 속성만 포함된 익명 형식으로 프로젝션된 Categories 개체로 데이터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-142">The code in this example uses a LINQ query to return data as Categories objects, which are projected as an anonymous type that contains only the CategoryID and CategoryName properties.</span></span> <span data-ttu-id="7ad4c-143">자세한 내용은 참조 [LINQ to Entities 개요](http://msdn.microsoft.com/86d87a27-c17a-45ac-b28d-72c8500333c6)합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-143">For more information, see [LINQ to Entities Overview](http://msdn.microsoft.com/86d87a27-c17a-45ac-b28d-72c8500333c6).</span></span>

```csharp
using System;
using System.Linq;
using System.Data.Objects;
using NorthwindModel;

class LinqSample
{
    public static void ExecuteQuery()
    {
        using (NorthwindEntities context = new NorthwindEntities())
        {
            try
            {
                var query = from category in context.Categories
                            select new
                            {
                                categoryID = category.CategoryID,
                                categoryName = category.CategoryName
                            };

                foreach (var categoryInfo in query)
                {
                    Console.WriteLine("\t{0}\t{1}",
                        categoryInfo.categoryID, categoryInfo.categoryName);
                }
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
        }
    }
}
```

```vb
Option Explicit On
Option Strict On

Imports System
Imports System.Linq
Imports System.Data.Objects
Imports NorthwindModel

Class LinqSample
    Public Shared Sub ExecuteQuery()
        Using context As NorthwindEntities = New NorthwindEntities()
            Try
                Dim query = From category In context.Categories _
                            Select New With _
                            { _
                                .categoryID = category.CategoryID, _
                                .categoryName = category.CategoryName _
                            }

                For Each categoryInfo In query
                    Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                        categoryInfo.categoryID, categoryInfo.categoryName)
                Next
            Catch ex As Exception
                Console.WriteLine(ex.Message)
            End Try
        End Using
    End Sub
End Class
```

### <a name="typed-objectquery"></a><span data-ttu-id="7ad4c-144">형식화된 ObjectQuery</span><span class="sxs-lookup"><span data-stu-id="7ad4c-144">Typed ObjectQuery</span></span>
<span data-ttu-id="7ad4c-145">이 예제 코드에서는 <xref:System.Data.Objects.ObjectQuery%601>을 사용하여 데이터를 Categories 개체로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-145">The code in this example uses an <xref:System.Data.Objects.ObjectQuery%601> to return data as Categories objects.</span></span> <span data-ttu-id="7ad4c-146">자세한 내용은 참조 [개체 쿼리](http://msdn.microsoft.com/0768033c-876f-471d-85d5-264884349276)합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-146">For more information, see [Object Queries](http://msdn.microsoft.com/0768033c-876f-471d-85d5-264884349276).</span></span>

```csharp
using System;
using System.Data.Objects;
using NorthwindModel;

class ObjectQuerySample
{
    public static void ExecuteQuery()
    {
        using (NorthwindEntities context = new NorthwindEntities())
        {
            ObjectQuery<Categories> categoryQuery = context.Categories;

            foreach (Categories category in 
                categoryQuery.Execute(MergeOption.AppendOnly))
            {
                Console.WriteLine("\t{0}\t{1}",
                    category.CategoryID, category.CategoryName);
            }
        }
    }
}
```

```vb
Option Explicit On
Option Strict On

Imports System
Imports System.Data.Objects
Imports NorthwindModel

Class ObjectQuerySample
    Public Shared Sub ExecuteQuery()
        Using context As NorthwindEntities = New NorthwindEntities()
            Dim categoryQuery As ObjectQuery(Of Categories) = context.Categories

            For Each category As Categories In _
                categoryQuery.Execute(MergeOption.AppendOnly)
                Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                    category.CategoryID, category.CategoryName)
            Next
        End Using
    End Sub
End Class
```

### <a name="entityclient"></a><span data-ttu-id="7ad4c-147">EntityClient</span><span class="sxs-lookup"><span data-stu-id="7ad4c-147">EntityClient</span></span>
<span data-ttu-id="7ad4c-148">이 예제 코드에서는 <xref:System.Data.EntityClient.EntityCommand>를 사용하여 Entity SQL 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-148">The code in this example uses an <xref:System.Data.EntityClient.EntityCommand> to execute an Entity SQL query.</span></span> <span data-ttu-id="7ad4c-149">이 쿼리는 Categories 엔터티 형식의 인스턴스를 나타내는 레코드 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-149">This query returns a list of records that represent instances of the Categories entity type.</span></span> <span data-ttu-id="7ad4c-150"><xref:System.Data.EntityClient.EntityDataReader>를 사용하여 결과 집합의 데이터 레코드에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-150">An <xref:System.Data.EntityClient.EntityDataReader> is used to access data records in the result set.</span></span> <span data-ttu-id="7ad4c-151">자세한 내용은 참조 [Entity Framework 용 EntityClient 공급자](../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-151">For more information, see [EntityClient Provider for the Entity Framework](../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).</span></span>

```csharp
using System;
using System.Data;
using System.Data.Common;
using System.Data.EntityClient;
using NorthwindModel;

class EntityClientSample
{
    public static void ExecuteQuery()
    {
        string queryString =
            @"SELECT c.CategoryID, c.CategoryName 
                FROM NorthwindEntities.Categories AS c";

        using (EntityConnection conn =
            new EntityConnection("name=NorthwindEntities"))
        {
            try
            {
                conn.Open();
                using (EntityCommand query = new EntityCommand(queryString, conn))
                {
                    using (DbDataReader rdr = 
                        query.ExecuteReader(CommandBehavior.SequentialAccess))
                    {
                        while (rdr.Read())
                        {
                            Console.WriteLine("\t{0}\t{1}", rdr[0], rdr[1]);
                        }
                    }
                }
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
        }
    }
}
```

```vb
Option Explicit On
Option Strict On

Imports System
Imports System.Data
Imports System.Data.Common
Imports System.Data.EntityClient
Imports NorthwindModel

Class EntityClientSample
    Public Shared Sub ExecuteQuery()
        Dim queryString As String = _
            "SELECT c.CategoryID, c.CategoryName " & _
                "FROM NorthwindEntities.Categories AS c"

        Using conn As EntityConnection = _
            New EntityConnection("name=NorthwindEntities")

            Try
                conn.Open()
                Using query As EntityCommand = _
                New EntityCommand(queryString, conn)
                    Using rdr As DbDataReader = _
                        query.ExecuteReader(CommandBehavior.SequentialAccess)
                        While rdr.Read()
                            Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                                              rdr(0), rdr(1))
                        End While
                    End Using
                End Using
            Catch ex As Exception
                Console.WriteLine(ex.Message)
            End Try
        End Using 
    End Sub
End Class
```

## <a name="linq-to-sql"></a><span data-ttu-id="7ad4c-152">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="7ad4c-152">LINQ to SQL</span></span>
<span data-ttu-id="7ad4c-153">이 예제 코드에서는 LINQ 쿼리를 사용하여 CategoryID와 CategoryName 속성만 포함된 익명 형식으로 프로젝션된 Categories 개체로 데이터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-153">The code in this example uses a LINQ query to return data as Categories objects, which are projected as an anonymous type that contains only the CategoryID and CategoryName properties.</span></span> <span data-ttu-id="7ad4c-154">이 예제는 Northwind 데이터 컨텍스트를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-154">This example is based on the Northwind data context.</span></span> <span data-ttu-id="7ad4c-155">자세한 내용은 [시작](../../../../docs/framework/data/adonet/sql/linq/getting-started.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-155">For more information, see [Getting Started](../../../../docs/framework/data/adonet/sql/linq/getting-started.md).</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using Northwind;

    class LinqSqlSample
    {
        public static void ExecuteQuery()
        {
            using (NorthwindDataContext db = new NorthwindDataContext())
            {
                try
                {
                    var query = from category in db.Categories
                                select new
                                {
                                    categoryID = category.CategoryID,
                                    categoryName = category.CategoryName
                                };

                    foreach (var categoryInfo in query)
                    {
                        Console.WriteLine("vbTab {0} vbTab {1}",
                            categoryInfo.categoryID, categoryInfo.categoryName);
                    }
                }
                catch (Exception ex)
                {
                    Console.WriteLine(ex.Message);
                }
            }
        }
    }
```

```vb
Option Explicit On
Option Strict On

Imports System
Imports System.Collections.Generic
Imports System.Linq
Imports System.Text
Imports Northwind

Class LinqSqlSample
    Public Shared Sub ExecuteQuery()
        Using db As NorthwindDataContext = New NorthwindDataContext()
            Try
                Dim query = From category In db.Categories _
                                Select New With _
                                { _
                                    .categoryID = category.CategoryID, _
                                    .categoryName = category.CategoryName _
                                }

                For Each categoryInfo In query
                    Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                            categoryInfo.categoryID, categoryInfo.categoryName)
                Next
            Catch ex As Exception
                Console.WriteLine(ex.Message)
            End Try
            End Using 
    End Sub
End Class
```

## <a name="see-also"></a><span data-ttu-id="7ad4c-156">참고자료</span><span class="sxs-lookup"><span data-stu-id="7ad4c-156">See also</span></span>
 [<span data-ttu-id="7ad4c-157">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="7ad4c-157">ADO.NET Overview</span></span>](../../../../docs/framework/data/adonet/ado-net-overview.md)  
 [<span data-ttu-id="7ad4c-158">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="7ad4c-158">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="7ad4c-159">데이터 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="7ad4c-159">Creating Data Applications</span></span>](http://msdn.microsoft.com/library/ab334d5f-4f49-4346-bce0-3325d6130b3e)  
 [<span data-ttu-id="7ad4c-160">엔터티 데이터 모델 (Entity Framework 작업)를 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad4c-160">Querying an Entity Data Model (Entity Framework Tasks)</span></span>](http://msdn.microsoft.com/187f1caa-e4d3-4e31-bd99-5d5c2b329c77)  
 [<span data-ttu-id="7ad4c-161">방법: 익명 형식 개체를 반환 하는 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="7ad4c-161">How to: Execute a Query that Returns Anonymous Type Objects</span></span>](http://msdn.microsoft.com/3b264025-e911-4d73-90ce-992d2b9d189d)  
 [<span data-ttu-id="7ad4c-162">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="7ad4c-162">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)  
