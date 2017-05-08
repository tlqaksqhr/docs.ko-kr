---
title: "ODBC 데이터 형식 매핑 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 43c35d32-831d-480f-a150-78f7e869d17f
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# ODBC 데이터 형식 매핑
다음 표에서는 .NET Framework Data Provider for ODBC\(<xref:System.Data.Odbc>\)의 데이터 형식에 대해 유추된 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 형식을 보여 줍니다.  또한 이 표에는 <xref:System.Data.Odbc.OdbcDataReader>의 형식화된 접근자 메서드도 나열되어 있습니다.  
  
|ODBC 형식|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 형식|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]의 형식화된 접근자|  
|-------------|--------------------------------------------------------------------|---------------------------------------------------------------------------|  
|SQL\_BIGINT|Int64|GetInt64\(\)|  
|SQL\_BINARY|Byte\[\]|GetBytes\(\)|  
|SQL\_BIT|Boolean|GetBoolean\(\)|  
|SQL\_CHAR|문자열<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|  
|SQL\_DECIMAL|Decimal|GetDecimal\(\)|  
|SQL\_DOUBLE|Double|GetDouble\(\)|  
|SQL\_GUID|Guid|GetGuid\(\)|  
|SQL\_INTEGER|Int32|GetInt32\(\)|  
|SQL\_LONG\_VARCHAR|문자열<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|  
|SQL\_LONGVARBINARY|Byte\[\]|GetBytes\(\)|  
|SQL\_NUMERIC|Decimal|GetDecimal\(\)|  
|SQL\_REAL|Single|GetFloat\(\)|  
|SQL\_SMALLINT|Int16|GetInt16\(\)|  
|SQL\_TINYINT|Byte|GetByte\(\)|  
|SQL\_TYPE\_TIMES|DateTime|GetDateTime\(\)|  
|SQL\_TYPE\_TIMESTAMP|DateTime|GetDateTime\(\)|  
|SQL\_VARBINARY|Byte\[\]|GetBytes\(\)|  
|SQL\_WCHAR|문자열<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|  
|SQL\_WLONGVARCHAR|문자열<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|  
|SQL\_WVARCHAR|문자열<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|  
  
## 참고 항목  
 [ADO.NET에서 데이터 검색 및 수정](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)