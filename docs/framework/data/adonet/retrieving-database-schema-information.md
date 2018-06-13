---
title: 데이터베이스 스키마 정보 검색
ms.date: 03/30/2017
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
ms.openlocfilehash: 1ac39a556fd7539550b12cb71b701c4bd3224a0b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33359691"
---
# <a name="retrieving-database-schema-information"></a>데이터베이스 스키마 정보 검색
데이터베이스에서 스키마 정보를 가져오려면 스키마 검색 프로세스를 사용합니다. 스키마 검색을 사용 하면 응용 프로그램 관리 되는 공급자 찾기 및 데이터베이스 스키마에 대 한 정보를 라고도 반환을 요청 하도록 *메타 데이터*, 지정된 된 데이터베이스의 합니다. 테이블, 열 및 저장 프로시저 같은 다양한 데이터베이스 스키마 요소는 스키마 컬렉션을 통해 노출됩니다. 각 스키마 컬렉션에는 사용하는 공급자와 관련된 다양한 스키마 정보가 들어 있습니다.  
  
 각.NET Framework 관리 공급자 구현에서 **GetSchema** 에서 메서드는 **연결** 클래스 및에서 반환 되는 스키마 정보는 **GetSchema**의 형태로 제공 메서드는 <xref:System.Data.DataTable>합니다. **GetSchema** 메서드는 스키마 컬렉션이 반환 되도록 지정 하 고 반환 될 정보의 양을 제한 하기 위한 선택적 매개 변수를 제공 하는 오버 로드 메서드입니다.  
  
 OLE DB, ODBC, Oracle 및 SqlClient에 대 한.NET Framework 데이터 공급자가 제공 된 **GetSchemaTable** 의 열 메타 데이터를 설명 하는 DataTable을 반환 하는 메서드는 **DataReader**합니다.  
  
 또한 .NET Framework Data Provider for OLE DB에서는 <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> 개체의 <xref:System.Data.OleDb.OleDbConnection> 메서드를 사용하여 스키마 정보를 노출합니다. 인수로 **GetOleDbSchemaTable** 사용는 <xref:System.Data.OleDb.OleDbSchemaGuid> 반환할 스키마 정보를 식별 하 고 하는 것에 대 한 제한 배열을 반환 된 열입니다. **GetOleDbSchemaTable** 반환는 <xref:System.Data.DataTable> 요청한 스키마 정보로 채워집니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [GetSchema 및 Schema 컬렉션](../../../../docs/framework/data/adonet/getschema-and-schema-collections.md)  
 설명의 **GetSchema** 메서드와 방법을 검색 하 고 제한 된 데이터베이스에서 스키마 정보를 사용할 수 있습니다.  
  
 스키마 제한  
 와 함께 사용할 수 있는 스키마 제한을 설명 **GetSchema**합니다.  
  
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
  
## <a name="reference"></a>참조  
 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 설명의 **GetSchema** 의 메서드는 <xref:System.Data.Common.DbConnection> 클래스입니다.  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 설명의 **GetSchema** 의 메서드는 <xref:System.Data.Odbc.OdbcConnection> 클래스입니다.  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 설명의 **GetSchema** 의 메서드는 <xref:System.Data.OleDb.OleDbConnection> 클래스입니다.  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 설명의 **GetSchema** 의 메서드는 <xref:System.Data.OracleClient.OracleConnection> 클래스입니다.  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 설명의 **GetSchema** 의 메서드는 <xref:System.Data.SqlClient.SqlConnection> 클래스입니다.  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 설명의 **GetSchemaTable** 의 메서드는 <xref:System.Data.Common.DbDataReader> 클래스입니다.  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 설명의 **GetSchemaTable** 의 메서드는 <xref:System.Data.Odbc.OdbcDataReader> 클래스입니다.  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 설명의 **GetSchemaTable** 의 메서드는 <xref:System.Data.OleDb.OleDbDataReader> 클래스입니다.  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 설명의 **GetSchemaTable** 의 메서드는 <xref:System.Data.OracleClient.OracleDataReader> 클래스입니다.  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 설명의 **GetSchemaTable** 의 메서드는 <xref:System.Data.SqlClient.SqlDataReader> 클래스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [ADO.NET에서 데이터 검색 및 수정](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
