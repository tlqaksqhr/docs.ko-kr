---
title: "OLE DB 데이터 형식 매핑 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 04bcb259-59d3-4fd7-894d-4f0dd0c68069
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# OLE DB 데이터 형식 매핑
다음 표에서는 .NET Framework Data Provider ADO 및 OLE DB\(<xref:System.Data.OleDb>\)의 데이터 형식에 대해 유추된 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 형식을 보여 줍니다.  또한 이 표에는 <xref:System.Data.OleDb.OleDbDataReader>의 형식화된 접근자 메서드도 나열되어 있습니다.  
  
|ADO 형식|OLE DB 형식|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 형식|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]의 형식화된 접근자|  
|------------|---------------|--------------------------------------------------------------------|---------------------------------------------------------------------------|  
|adBigInt|DBTYPE\_I8|Int64|GetInt64\(\)|  
|adBinary|DBTYPE\_BYTES|Byte\[\]|GetBytes\(\)|  
|adBoolean|DBTYPE\_BOOL|Boolean|GetBoolean\(\)|  
|adBSTR|DBTYPE\_BSTR|문자열|GetString\(\)|  
|adChapter|DBTYPE\_HCHAPTER|`DataReader`를 통해 지원됩니다.  [DataReader를 사용하여 데이터 검색](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md)을 참조하세요.|GetValue\(\)|  
|adChar|DBTYPE\_STR|문자열|GetString\(\)|  
|adCurrency|DBTYPE\_CY|Decimal|GetDecimal\(\)|  
|adDate|DBTYPE\_DATE|DateTime|GetDateTime\(\)|  
|adDBDate|DBTYPE\_DBDATE|DateTime|GetDateTime\(\)|  
|adDBTime|DBTYPE\_DBTIME|DateTime|GetDateTime\(\)|  
|adDBTimeStamp|DBTYPE\_DBTIMESTAMP|DateTime|GetDateTime\(\)|  
|adDecimal|DBTYPE\_DECIMAL|Decimal|GetDecimal\(\)|  
|adDouble|DBTYPE\_R8|Double|GetDouble\(\)|  
|adError|DBTYPE\_ERROR|ExternalException|GetValue\(\)|  
|adFileTime|DBTYPE\_FILETIME|DateTime|GetDateTime\(\)|  
|adGUID|DBTYPE\_GUID|Guid|GetGuid\(\)|  
|adIDispatch|DBTYPE\_IDISPATCH \*|개체|GetValue\(\)|  
|adInteger|DBTYPE\_I4|Int32|GetInt32\(\)|  
|adIUnknown|DBTYPE\_IUNKNOWN \*|개체|GetValue\(\)|  
|adNumeric|DBTYPE\_NUMERIC|Decimal|GetDecimal\(\)|  
|adPropVariant|DBTYPE\_PROPVARIANT|개체|GetValue\(\)|  
|adSingle|DBTYPE\_R4|Single|GetFloat\(\)|  
|adSmallInt|DBTYPE\_I2|Int16|GetInt16\(\)|  
|adTinyInt|DBTYPE\_I1|Byte|GetByte\(\)|  
|adUnsignedBigInt|DBTYPE\_UI8|UInt64|GetValue\(\)|  
|adUnsignedInt|DBTYPE\_UI4|UInt32|GetValue\(\)|  
|adUnsignedSmallInt|DBTYPE\_UI2|UInt16|GetValue\(\)|  
|adUnsignedTinyInt|DBTYPE\_UI1|Byte|GetByte\(\)|  
|adVariant|DBTYPE\_VARIANT|개체|GetValue\(\)|  
|adWChar|DBTYPE\_WSTR|문자열|GetString\(\)|  
|adUserDefined|DBTYPE\_UDT|지원되지 않음||  
|adVarNumeric|DBTYPE\_VARNUMERIC|지원되지 않음||  
  
 \* OLE DB 형식의 `DBTYPE_IUNKNOWN` 및 `DBTYPE_IDISPATCH`의 경우 개체 참조는 포인터의 마샬링된 표현입니다.  
  
## 참고 항목  
 [ADO.NET에서 데이터 검색 및 수정](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)