---
title: "Oracle 데이터 형식 매핑 | Microsoft Docs"
ms.custom: ""
ms.date: "02/15/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d2521bcc-0051-4f35-8be3-e8723edeaf6f
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
---
# Oracle 데이터 형식 매핑
다음 표에서는 .NET Framework Data Provider for Oracle\([!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\)의 데이터 형식에 대해 유추된 <xref:System.Data.OracleClient> 형식을 보여 줍니다. 또한 이 표에는 <xref:System.Data.OracleClient.OracleDataReader>의 형식화된 접근자 메서드도 나열되어 있습니다.  
  
|Oracle 형식|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 형식|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]의 형식화된 접근자|OracleType의 형식화된 접근자|  
|---------------|--------------------------------------------------------------------|---------------------------------------------------------------------------|--------------------------|  
|BFILE|Byte\[\]|GetBytes\(\)|GetOracleBFile\(\)|  
|BLOB|Byte\[\]|GetBytes\(\)|GetOracleLob\(\)|  
|CHAR|문자열<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleString\(\)|  
|CLOB|문자열<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleLob\(\)|  
|DATE|DateTime|GetDateTime\(\)|GetOracleDateTime\(\)|  
|FLOAT|Decimal|GetDecimal\(\)|GetOracleNumber\(\) \*\*|  
|INTEGER|Decimal|GetDecimal\(\)|GetOracleNumber\(\) \*\*|  
|INTERVAL YEAR TO MONTH \*|Int32|GetInt32\(\)|GetOracleMonthSpan\(\)|  
|INTERVAL DAY TO SECOND \*|TimeSpan|GetTimeSpan\(\)|GetOracleTimeSpan\(\)|  
|LONG|문자열<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleString\(\)|  
|LONG RAW|Byte\[\]|GetBytes\(\)|GetOracleBinary\(\)|  
|NCHAR|문자열<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleString\(\)|  
|NCLOB|문자열<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleLob\(\)|  
|NUMBER|Decimal|GetDecimal\(\)|GetOracleNumber\(\) \*\*|  
|NVARCHAR2|문자열<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleString\(\)|  
|RAW|Byte\[\]|GetBytes\(\)|GetOracleBinary\(\)|  
|REF CURSOR||||  
|ROWID|문자열<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleString\(\)|  
|TIMESTAMP \*|DateTime|GetDateTime\(\)|GetOracleDateTime\(\)|  
|TIMESTAMP WITH LOCAL TIME ZONE \*|DateTime|GetDateTime\(\)|GetOracleDateTime\(\)|  
|TIMESTAMP WITH TIME ZONE \*|DateTime|GetDateTime\(\)|GetOracleDateTime\(\)|  
|UNSIGNED INTEGER|Decimal|GetDecimal\(\)|GetOracleNumber\(\) \*\*|  
|VARCHAR2|문자열<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleString\(\)|  
  
 \* 이 표시가 있는 Oracle 형식은 클라이언트와 서버 모두에서 Oracle 9i 소프트웨어를 사용하는 경우에만 적용됩니다.  
  
 \*\* Oracle NUMBER에는 최대 38개의 유효 숫자가 포함될 수 있습니다.[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]`decimal` 형식은 28자리로 제한됩니다. Oracle NUMBER를 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]`decimal` 형식으로 읽으면 28자리를 초과하는 NUMBER 값의 경우 `OverflowException`이 발생합니다.`OracleDataReader`에서 Oracle NUMBER 값을 읽는 경우에는 형식화된 접근자 메서드 `GetOracleNumber`를 호출하여 Oracle NUMBER 값을 `OracleNumber`로 반환하는 것이 좋습니다.`DataSet`을 채우는 경우에는 `FillError` 이벤트를 사용하여 `OverflowException`이 발생했는지 여부를 확인하고, 예외가 발생한 경우 적절한 조치를 취할 수 있습니다.`FillError` 이벤트에 대한 자세한 내용은 [DataAdapter 이벤트 처리](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)를 참조하세요.  
  
## 참고 항목  
 [Oracle 및 ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)   
 [ADO.NET에서 데이터 검색 및 수정](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)