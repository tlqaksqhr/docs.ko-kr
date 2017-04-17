---
title: "데이터베이스 스키마 정보 검색 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# 데이터베이스 스키마 정보 검색
데이터베이스에서 스키마 정보를 가져오려면 스키마 검색 프로세스를 사용합니다.  스키마 검색을 사용하면 응용 프로그램에서 관리되는 공급자가 지정된 데이터베이스의 데이터베이스 스키마\(*메타데이터*라고도 함\)에 대한 정보를 찾아 반환하도록 요청할 수 있습니다.  테이블, 열 및 저장 프로시저 같은 다양한 데이터베이스 스키마 요소는 스키마 컬렉션을 통해 노출됩니다.  각 스키마 컬렉션에는 사용하는 공급자와 관련된 다양한 스키마 정보가 들어 있습니다.  
  
 각 .NET Framework 관리 공급자는 **Connection** 클래스에 **GetSchema** 메서드를 구현하고 **GetSchema** 메서드에서 반환되는 스키마 정보는 <xref:System.Data.DataTable>의 형태로 제공됩니다.  **GetSchema** 메서드는 스키마 컬렉션이 반환되도록 지정하고 반환되는 정보의 양을 제한하기 위한 선택적 매개 변수를 제공하는 오버로드 메서드입니다.  
  
 .NET Framework Data Provider for OLE DB, ODBC, Oracle 및 SqlClient에서는 **GetSchemaTable** 메서드를 제공합니다. 이 메서드는 **DataReader**의 열 메타데이터를 설명하는 DataTable을 반환합니다.  
  
 또한 .NET Framework Data Provider for OLE DB에서는 <xref:System.Data.OleDb.OleDbConnection> 개체의 <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> 메서드를 사용하여 스키마 정보를 노출합니다.  **GetOleDbSchemaTable**은 반환할 스키마 정보를 식별하는 <xref:System.Data.OleDb.OleDbSchemaGuid> 및 반환된 해당 열에 대한 제한 배열을 인수로 사용합니다.  **GetOleDbSchemaTable**은 요청한 스키마 정보로 채워진 <xref:System.Data.DataTable>을 반환합니다.  
  
## 단원 내용  
 [GetSchema 및 스키마 컬렉션](../../../../docs/framework/data/adonet/getschema-and-schema-collections.md)  
 **GetSchema** 메서드와 이를 사용하여 데이터베이스에서 스키마 정보를 검색하고 제한하는 방법을 설명합니다.  
  
 스키마 제한  
 **GetSchema**와 함께 사용할 수 있는 스키마 제한을 설명합니다.  
  
 [공통 스키마 컬렉션](../../../../docs/framework/data/adonet/common-schema-collections.md)  
 모든 .NET Framework 관리 공급자에서 지원하는 모든 공통 스키마 컬렉션에 대해 설명합니다.  
  
 [SQL Server 스키마 컬렉션](../../../../docs/framework/data/adonet/sql-server-schema-collections.md)  
 .NET Framework Provider for SQL Server에서 지원하는 스키마 컬렉션에 대해 설명합니다.  
  
 [Oracle 스키마 컬렉션](../../../../docs/framework/data/adonet/oracle-schema-collections.md)  
 .NET Framework Provider for Oracle에서 지원하는 스키마 컬렉션에 대해 설명합니다.  
  
 [ODBC 스키마 컬렉션](../../../../docs/framework/data/adonet/odbc-schema-collections.md)  
 ODBC 드라이버의 스키마 컬렉션에 대해 설명합니다.  
  
 [OLE DB 스키마 컬렉션](../../../../docs/framework/data/adonet/ole-db-schema-collections.md)  
 OLE DB 공급자의 스키마 컬렉션에 대해 설명합니다.  
  
## 참조  
 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 <xref:System.Data.Common.DbConnection> 클래스의 **GetSchema** 메서드에 대해 설명합니다.  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 <xref:System.Data.Odbc.OdbcConnection> 클래스의 **GetSchema** 메서드에 대해 설명합니다.  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 <xref:System.Data.OleDb.OleDbConnection> 클래스의 **GetSchema** 메서드에 대해 설명합니다.  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 <xref:System.Data.OracleClient.OracleConnection> 클래스의 **GetSchema** 메서드에 대해 설명합니다.  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 <xref:System.Data.SqlClient.SqlConnection> 클래스의 **GetSchema** 메서드에 대해 설명합니다.  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 <xref:System.Data.Common.DbDataReader> 클래스의 **GetSchemaTable** 메서드에 대해 설명합니다.  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 <xref:System.Data.Odbc.OdbcDataReader> 클래스의 **GetSchemaTable** 메서드에 대해 설명합니다.  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 <xref:System.Data.OleDb.OleDbDataReader> 클래스의 **GetSchemaTable** 메서드에 대해 설명합니다.  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 <xref:System.Data.OracleClient.OracleDataReader> 클래스의 **GetSchemaTable** 메서드에 대해 설명합니다.  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 <xref:System.Data.SqlClient.SqlDataReader> 클래스의 **GetSchemaTable** 메서드에 대해 설명합니다.  
  
## 참고 항목  
 [ADO.NET에서 데이터 검색 및 수정](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)