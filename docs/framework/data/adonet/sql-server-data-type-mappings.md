---
title: "SQL Server 데이터 형식 매핑"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fafdc31a-f435-4cd3-883f-1dfadd971277
caps.latest.revision: "8"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 1a2fbbdc2ad89c562ef6fd0e0174ef0b06a93408
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="sql-server-data-type-mappings"></a>SQL Server 데이터 형식 매핑
SQL Server와 .NET Framework는 서로 다른 형식 시스템을 기반으로 합니다. 예를 들어 .NET Framework <xref:System.Decimal> 구조의 최대 자릿수는 28인 반면 SQL Server decimal 및 숫자 데이터 형식의 최대 자릿수는 38입니다. 데이터를 읽거나 쓸 때 데이터 무결성을 유지하기 위해 <xref:System.Data.SqlClient.SqlDataReader>는 <xref:System.Data.SqlTypes>의 개체를 반환하는 SQL Server 관련 형식화된 접근자 메서드 및 .NET Framework 형식을 반환하는 접근자 메서드를 노출합니다. SQL Server 형식 및 .NET Framework 형식 모두 <xref:System.Data.DbType> 데이터 형식을 지정할 때 사용할 수 있는 <xref:System.Data.SqlDbType> 및 <xref:System.Data.SqlClient.SqlParameter> 클래스에 열거형으로 표시됩니다.  
  
 다음 표에서는 유추된 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 형식, <xref:System.Data.DbType>과 <xref:System.Data.SqlDbType> 열거형 및 <xref:System.Data.SqlClient.SqlDataReader>의 접근자 메서드를 보여 줍니다.  
  
|SQL Server 데이터베이스 엔진 형식|.NET Framework 형식|SqlDbType 열거형|SqlDataReader SqlTypes 형식화된 접근자|DbType 열거형|SqlDataReader DbType 형식화된 접근자|  
|-------------------------------------|-------------------------|---------------------------|-------------------------------------------|------------------------|-----------------------------------------|  
|bigint|Int64|<xref:System.Data.SqlDbType.BigInt>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlInt64%2A>|<xref:System.Data.DbType.Int64>|<xref:System.Data.SqlClient.SqlDataReader.GetInt64%2A>|  
|이진|Byte[]|<xref:System.Data.SqlDbType.VarBinary>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlBinary%2A>|<xref:System.Data.DbType.Binary>|<xref:System.Data.SqlClient.SqlDataReader.GetBytes%2A>|  
|비트|Boolean|<xref:System.Data.SqlDbType.Bit>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlBoolean%2A>|<xref:System.Data.DbType.Boolean>|<xref:System.Data.SqlClient.SqlDataReader.GetBoolean%2A>|  
|char|문자열<br /><br /> Char[]|<xref:System.Data.SqlDbType.Char>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlString%2A>|<xref:System.Data.DbType.AnsiStringFixedLength>,<br /><br /> <xref:System.Data.DbType.String>|<xref:System.Data.SqlClient.SqlDataReader.GetString%2A><br /><br /> <xref:System.Data.SqlClient.SqlDataReader.GetChars%2A>|  
|date<br /><br /> (SQL Server 2008 이상)|DateTime|<xref:System.Data.SqlDbType.Date>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlDateTime%2A>|<xref:System.Data.DbType.Date>|<xref:System.Data.SqlClient.SqlDataReader.GetDateTime%2A>|  
|datetime|DateTime|<xref:System.Data.SqlDbType.DateTime>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlDateTime%2A>|<xref:System.Data.DbType.DateTime>|<xref:System.Data.SqlClient.SqlDataReader.GetDateTime%2A>|  
|datetime2<br /><br /> (SQL Server 2008 이상)|DateTime|<xref:System.Data.SqlDbType.DateTime2>|없음|<xref:System.Data.DbType.DateTime2>|<xref:System.Data.SqlClient.SqlDataReader.GetDateTime%2A>|  
|datetimeoffset<br /><br /> (SQL Server 2008 이상)|DateTimeOffset|<xref:System.Data.SqlDbType.DateTimeOffset>|없음|<xref:System.Data.DbType.DateTimeOffset>|<xref:System.Data.SqlClient.SqlDataReader.GetDateTimeOffset%2A>|  
|decimal|Decimal|<xref:System.Data.SqlDbType.Decimal>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlDecimal%2A>|<xref:System.Data.DbType.Decimal>|<xref:System.Data.SqlClient.SqlDataReader.GetDecimal%2A>|  
|FILESTREAM 특성(varbinary(max))|Byte[]|<xref:System.Data.SqlDbType.VarBinary>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlBytes%2A>|<xref:System.Data.DbType.Binary>|<xref:System.Data.SqlClient.SqlDataReader.GetBytes%2A>|  
|float|Double|<xref:System.Data.SqlDbType.Float>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlDouble%2A>|<xref:System.Data.DbType.Double>|<xref:System.Data.SqlClient.SqlDataReader.GetDouble%2A>|  
|이미지|Byte[]|<xref:System.Data.SqlDbType.Binary>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlBinary%2A>|<xref:System.Data.DbType.Binary>|<xref:System.Data.SqlClient.SqlDataReader.GetBytes%2A>|  
|int|Int32|<xref:System.Data.SqlDbType.Int>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlInt32%2A>|<xref:System.Data.DbType.Int32>|<xref:System.Data.SqlClient.SqlDataReader.GetInt32%2A>|  
|money|Decimal|<xref:System.Data.SqlDbType.Money>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlMoney%2A>|<xref:System.Data.DbType.Decimal>|<xref:System.Data.SqlClient.SqlDataReader.GetDecimal%2A>|  
|nchar|문자열<br /><br /> Char[]|<xref:System.Data.SqlDbType.NChar>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlString%2A>|<xref:System.Data.DbType.StringFixedLength>|<xref:System.Data.SqlClient.SqlDataReader.GetString%2A><br /><br /> <xref:System.Data.SqlClient.SqlDataReader.GetChars%2A>|  
|ntext|문자열<br /><br /> Char[]|<xref:System.Data.SqlDbType.NText>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlString%2A>|<xref:System.Data.DbType.String>|<xref:System.Data.SqlClient.SqlDataReader.GetString%2A><br /><br /> <xref:System.Data.SqlClient.SqlDataReader.GetChars%2A>|  
|숫자|Decimal|<xref:System.Data.SqlDbType.Decimal>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlDecimal%2A>|<xref:System.Data.DbType.Decimal>|<xref:System.Data.SqlClient.SqlDataReader.GetDecimal%2A>|  
|nvarchar|문자열<br /><br /> Char[]|<xref:System.Data.SqlDbType.NVarChar>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlString%2A>|<xref:System.Data.DbType.String>|<xref:System.Data.SqlClient.SqlDataReader.GetString%2A><br /><br /> <xref:System.Data.SqlClient.SqlDataReader.GetChars%2A>|  
|실수|Single|<xref:System.Data.SqlDbType.Real>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlSingle%2A>|<xref:System.Data.DbType.Single>|<xref:System.Data.SqlClient.SqlDataReader.GetFloat%2A>|  
|rowversion|Byte[]|<xref:System.Data.SqlDbType.Timestamp>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlBinary%2A>|<xref:System.Data.DbType.Binary>|<xref:System.Data.SqlClient.SqlDataReader.GetBytes%2A>|  
|smalldatetime|DateTime|<xref:System.Data.SqlDbType.DateTime>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlDateTime%2A>|<xref:System.Data.DbType.DateTime>|<xref:System.Data.SqlClient.SqlDataReader.GetDateTime%2A>|  
|smallint|Int16|<xref:System.Data.SqlDbType.SmallInt>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlInt16%2A>|<xref:System.Data.DbType.Int16>|<xref:System.Data.SqlClient.SqlDataReader.GetInt16%2A>|  
|smallmoney|Decimal|<xref:System.Data.SqlDbType.SmallMoney>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlMoney%2A>|<xref:System.Data.DbType.Decimal>|<xref:System.Data.SqlClient.SqlDataReader.GetDecimal%2A>|  
|sql_variant|Object*|<xref:System.Data.SqlDbType.Variant>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlValue%2A> *|<xref:System.Data.DbType.Object>|<xref:System.Data.SqlClient.SqlDataReader.GetValue%2A> *|  
|텍스트|문자열<br /><br /> Char[]|<xref:System.Data.SqlDbType.Text>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlString%2A>|<xref:System.Data.DbType.String>|<xref:System.Data.SqlClient.SqlDataReader.GetString%2A><br /><br /> <xref:System.Data.SqlClient.SqlDataReader.GetChars%2A>|  
|시간<br /><br /> (SQL Server 2008 이상)|TimeSpan|<xref:System.Data.SqlDbType.Time>|없음|<xref:System.Data.DbType.Time>|<xref:System.Data.SqlClient.SqlDataReader.GetDateTime%2A>|  
|타임스탬프|Byte[]|<xref:System.Data.SqlDbType.Timestamp>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlBinary%2A>|<xref:System.Data.DbType.Binary>|<xref:System.Data.SqlClient.SqlDataReader.GetBytes%2A>|  
|tinyint|Byte|<xref:System.Data.SqlDbType.TinyInt>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlByte%2A>|<xref:System.Data.DbType.Byte>|<xref:System.Data.SqlClient.SqlDataReader.GetByte%2A>|  
|uniqueidentifier|Guid|<xref:System.Data.SqlDbType.UniqueIdentifier>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlGuid%2A>|<xref:System.Data.DbType.Guid>|<xref:System.Data.SqlClient.SqlDataReader.GetGuid%2A>|  
|varbinary|Byte[]|<xref:System.Data.SqlDbType.VarBinary>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlBinary%2A>|<xref:System.Data.DbType.Binary>|<xref:System.Data.SqlClient.SqlDataReader.GetBytes%2A>|  
|varchar|문자열<br /><br /> Char[]|<xref:System.Data.SqlDbType.VarChar>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlString%2A>|<xref:System.Data.DbType.AnsiString>, <xref:System.Data.DbType.String>|<xref:System.Data.SqlClient.SqlDataReader.GetString%2A><br /><br /> <xref:System.Data.SqlClient.SqlDataReader.GetChars%2A>|  
|xml|Xml|<xref:System.Data.SqlDbType.Xml>|<xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A>|<xref:System.Data.DbType.Xml>|없음|  
  
 \*기본 형식을 알고 있으면 형식화 된 특정 접근자를 사용 하 여는 `sql_variant`합니다.  
  
## <a name="includessnoversionincludesssnoversion-mdmd-books-online-reference"></a>[!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] 온라인 설명서 참조  
 에 대 한 자세한 내용은 [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] 데이터 형식을 참조 [데이터 형식 (데이터베이스 엔진)](http://go.microsoft.com/fwlink/?LinkID=107468)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQL Server 데이터 형식 및 ADO.NET](../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [SQL Server 이진 및 큰 값 데이터](../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [ADO.NET에서 데이터 형식 매핑](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)  
 [매개 변수 및 매개 변수 데이터 형식 구성](../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
