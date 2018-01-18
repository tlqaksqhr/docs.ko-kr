---
title: "데이터베이스 스키마 정보 검색"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 09a0ec444801d1fe2caccf9e25a68e3c6ae8f5c2
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="retrieving-database-schema-information"></a><span data-ttu-id="28767-102">데이터베이스 스키마 정보 검색</span><span class="sxs-lookup"><span data-stu-id="28767-102">Retrieving Database Schema Information</span></span>
<span data-ttu-id="28767-103">데이터베이스에서 스키마 정보를 가져오려면 스키마 검색 프로세스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="28767-103">Obtaining schema information from a database is accomplished with the process of schema discovery.</span></span> <span data-ttu-id="28767-104">스키마 검색을 사용 하면 응용 프로그램 관리 되는 공급자 찾기 및 데이터베이스 스키마에 대 한 정보를 라고도 반환을 요청 하도록 *메타 데이터*, 지정된 된 데이터베이스의 합니다.</span><span class="sxs-lookup"><span data-stu-id="28767-104">Schema discovery allows applications to request that managed providers find and return information about the database schema, also known as *metadata*, of a given database.</span></span> <span data-ttu-id="28767-105">테이블, 열 및 저장 프로시저 같은 다양한 데이터베이스 스키마 요소는 스키마 컬렉션을 통해 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="28767-105">Different database schema elements such as tables, columns, and stored-procedures are exposed through schema collections.</span></span> <span data-ttu-id="28767-106">각 스키마 컬렉션에는 사용하는 공급자와 관련된 다양한 스키마 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28767-106">Each schema collection contains a variety of schema information specific to the provider being used.</span></span>  
  
 <span data-ttu-id="28767-107">각.NET Framework 관리 공급자 구현에서 **GetSchema** 에서 메서드는 **연결** 클래스 및에서 반환 되는 스키마 정보는 **GetSchema**의 형태로 제공 메서드는 <xref:System.Data.DataTable>합니다.</span><span class="sxs-lookup"><span data-stu-id="28767-107">Each of the .NET Framework managed providers implement the **GetSchema** method in the **Connection** class, and the schema information that is returned from the **GetSchema** method comes in the form of a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="28767-108">**GetSchema** 메서드는 스키마 컬렉션이 반환 되도록 지정 하 고 반환 될 정보의 양을 제한 하기 위한 선택적 매개 변수를 제공 하는 오버 로드 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="28767-108">The **GetSchema** method is an overloaded method that provides optional parameters for specifying the schema collection to return, and restricting the amount of information returned.</span></span>  
  
 <span data-ttu-id="28767-109">OLE DB, ODBC, Oracle 및 SqlClient에 대 한.NET Framework 데이터 공급자가 제공 된 **GetSchemaTable** 의 열 메타 데이터를 설명 하는 DataTable을 반환 하는 메서드는 **DataReader**합니다.</span><span class="sxs-lookup"><span data-stu-id="28767-109">The .NET Framework Data Providers for OLE DB, ODBC, Oracle, and SqlClient provide a **GetSchemaTable** method that returns a DataTable describing the column metadata of the **DataReader**.</span></span>  
  
 <span data-ttu-id="28767-110">또한 .NET Framework Data Provider for OLE DB에서는 <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> 개체의 <xref:System.Data.OleDb.OleDbConnection> 메서드를 사용하여 스키마 정보를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="28767-110">The .NET Framework Data Provider for OLE DB also exposes schema information by using the <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> method of the <xref:System.Data.OleDb.OleDbConnection> object.</span></span> <span data-ttu-id="28767-111">인수로 **GetOleDbSchemaTable** 사용는 <xref:System.Data.OleDb.OleDbSchemaGuid> 반환할 스키마 정보를 식별 하 고 하는 것에 대 한 제한 배열을 반환 된 열입니다.</span><span class="sxs-lookup"><span data-stu-id="28767-111">As arguments, **GetOleDbSchemaTable** takes an <xref:System.Data.OleDb.OleDbSchemaGuid> that identifies the schema information to return, and an array of restrictions on those returned columns.</span></span> <span data-ttu-id="28767-112">**GetOleDbSchemaTable** 반환는 <xref:System.Data.DataTable> 요청한 스키마 정보로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="28767-112">**GetOleDbSchemaTable** returns a <xref:System.Data.DataTable> populated with the requested schema information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="28767-113">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="28767-113">In This Section</span></span>  
 [<span data-ttu-id="28767-114">GetSchema 및 Schema 컬렉션</span><span class="sxs-lookup"><span data-stu-id="28767-114">GetSchema and Schema Collections</span></span>](../../../../docs/framework/data/adonet/getschema-and-schema-collections.md)  
 <span data-ttu-id="28767-115">설명의 **GetSchema** 메서드와 방법을 검색 하 고 제한 된 데이터베이스에서 스키마 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28767-115">Describes the **GetSchema** method and how it can be used to retrieve and restrict schema information from a database.</span></span>  
  
 <span data-ttu-id="28767-116">스키마 제한</span><span class="sxs-lookup"><span data-stu-id="28767-116">Schema Restrictions</span></span>  
 <span data-ttu-id="28767-117">와 함께 사용할 수 있는 스키마 제한을 설명 **GetSchema**합니다.</span><span class="sxs-lookup"><span data-stu-id="28767-117">Describes schema restrictions that can be used with **GetSchema**.</span></span>  
  
 [<span data-ttu-id="28767-118">공통 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="28767-118">Common Schema Collections</span></span>](../../../../docs/framework/data/adonet/common-schema-collections.md)  
 <span data-ttu-id="28767-119">모든 .NET Framework 관리 공급자에서 지원하는 모든 공통 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28767-119">Describes all of the common schema collections supported by all of the .NET Framework managed providers.</span></span>  
  
 [<span data-ttu-id="28767-120">SQL Server 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="28767-120">SQL Server Schema Collections</span></span>](../../../../docs/framework/data/adonet/sql-server-schema-collections.md)  
 <span data-ttu-id="28767-121">.NET Framework Provider for SQL Server에서 지원하는 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28767-121">Describes the schema collection supported by the .NET Framework provider for SQL Server.</span></span>  
  
 [<span data-ttu-id="28767-122">Oracle 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="28767-122">Oracle Schema Collections</span></span>](../../../../docs/framework/data/adonet/oracle-schema-collections.md)  
 <span data-ttu-id="28767-123">.NET Framework Provider for Oracle에서 지원하는 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28767-123">Describes the schema collection supported by the .NET Framework provider for Oracle.</span></span>  
  
 [<span data-ttu-id="28767-124">ODBC 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="28767-124">ODBC Schema Collections</span></span>](../../../../docs/framework/data/adonet/odbc-schema-collections.md)  
 <span data-ttu-id="28767-125">ODBC 드라이버의 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28767-125">Describes the schema collections for ODBC drivers.</span></span>  
  
 [<span data-ttu-id="28767-126">OLE DB 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="28767-126">OLE DB Schema Collections</span></span>](../../../../docs/framework/data/adonet/ole-db-schema-collections.md)  
 <span data-ttu-id="28767-127">OLE DB 공급자의 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28767-127">Describes the schema collections for OLE DB providers.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="28767-128">참조</span><span class="sxs-lookup"><span data-stu-id="28767-128">Reference</span></span>  
 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 <span data-ttu-id="28767-129">설명의 **GetSchema** 의 메서드는 <xref:System.Data.Common.DbConnection> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="28767-129">Describes the **GetSchema** method of the <xref:System.Data.Common.DbConnection> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 <span data-ttu-id="28767-130">설명의 **GetSchema** 의 메서드는 <xref:System.Data.Odbc.OdbcConnection> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="28767-130">Describes the **GetSchema** method of the <xref:System.Data.Odbc.OdbcConnection> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 <span data-ttu-id="28767-131">설명의 **GetSchema** 의 메서드는 <xref:System.Data.OleDb.OleDbConnection> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="28767-131">Describes the **GetSchema** method of the <xref:System.Data.OleDb.OleDbConnection> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 <span data-ttu-id="28767-132">설명의 **GetSchema** 의 메서드는 <xref:System.Data.OracleClient.OracleConnection> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="28767-132">Describes the **GetSchema** method of the <xref:System.Data.OracleClient.OracleConnection> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 <span data-ttu-id="28767-133">설명의 **GetSchema** 의 메서드는 <xref:System.Data.SqlClient.SqlConnection> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="28767-133">Describes the **GetSchema** method of the <xref:System.Data.SqlClient.SqlConnection> class.</span></span>  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="28767-134">설명의 **GetSchemaTable** 의 메서드는 <xref:System.Data.Common.DbDataReader> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="28767-134">Describes the **GetSchemaTable** method of the <xref:System.Data.Common.DbDataReader> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="28767-135">설명의 **GetSchemaTable** 의 메서드는 <xref:System.Data.Odbc.OdbcDataReader> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="28767-135">Describes the **GetSchemaTable** method of the <xref:System.Data.Odbc.OdbcDataReader> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="28767-136">설명의 **GetSchemaTable** 의 메서드는 <xref:System.Data.OleDb.OleDbDataReader> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="28767-136">Describes the **GetSchemaTable** method of the <xref:System.Data.OleDb.OleDbDataReader> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="28767-137">설명의 **GetSchemaTable** 의 메서드는 <xref:System.Data.OracleClient.OracleDataReader> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="28767-137">Describes the **GetSchemaTable** method of the <xref:System.Data.OracleClient.OracleDataReader> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="28767-138">설명의 **GetSchemaTable** 의 메서드는 <xref:System.Data.SqlClient.SqlDataReader> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="28767-138">Describes the **GetSchemaTable** method of the <xref:System.Data.SqlClient.SqlDataReader> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28767-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="28767-139">See Also</span></span>  
 [<span data-ttu-id="28767-140">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="28767-140">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="28767-141">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="28767-141">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
