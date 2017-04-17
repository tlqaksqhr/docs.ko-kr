---
title: "Oracle 데이터 형식 매핑 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ec34ae21-bbbb-4adb-b672-83865e2a8451
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Oracle 데이터 형식 매핑
다음 표에는 Oracle 데이터 형식과 <xref:System.Data.OracleClient.OracleDataReader>에 대한 해당 데이터 형식의 매핑이 나열되어 있습니다.  
  
|Oracle 데이터 형식|OracleDataReader.GetValue에 의해 반환되는 .NET Framework 데이터 형식|OracleDataReader.GetOracleValue에 의해 반환되는 OracleClient 데이터 형식|설명|  
|-------------------|--------------------------------------------------------------|------------------------------------------------------------------|--------|  
|**BFILE**|**Byte\[\]**|<xref:System.Data.OracleClient.OracleBFile>||  
|**BLOB**|**Byte\[\]**|<xref:System.Data.OracleClient.OracleLob>||  
|**CHAR**|**문자열**|<xref:System.Data.OracleClient.OracleString>||  
|**CLOB**|**문자열**|<xref:System.Data.OracleClient.OracleLob>||  
|**DATE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**FLOAT**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|이 데이터 형식은 **NUMBER** 데이터 형식의 별칭이며 <xref:System.Data.OracleClient.OracleDataReader>에서 부동 소수점 값 대신 **System.Decimal** 또는 <xref:System.Data.OracleClient.OracleNumber>를 반환하도록 디자인되었습니다.  .NET Framework 데이터 형식을 사용하면 오버플로가 발생할 수 있습니다.|  
|**INTEGER**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|이 데이터 형식은 **NUMBER\(38\)** 데이터 형식의 별칭이며 <xref:System.Data.OracleClient.OracleDataReader>에서 정수 값 대신 **System.Decimal** 또는 <xref:System.Data.OracleClient.OracleNumber>를 반환하도록 디자인되었습니다.  .NET Framework 데이터 형식을 사용하면 오버플로가 발생할 수 있습니다.|  
|**INTERVAL YEAR TO MONTH**|**Int32**|<xref:System.Data.OracleClient.OracleMonthSpan>||  
|**INTERVAL DAY TO SECOND**|**TimeSpan**|<xref:System.Data.OracleClient.OracleTimeSpan>||  
|**LONG**|**문자열**|<xref:System.Data.OracleClient.OracleString>||  
|**LONG RAW**|**Byte\[\]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**NCHAR**|**문자열**|<xref:System.Data.OracleClient.OracleString>||  
|**NCLOB**|**문자열**|<xref:System.Data.OracleClient.OracleLob>||  
|**NUMBER**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|.NET Framework 데이터 형식을 사용하면 오버플로가 발생할 수 있습니다.|  
|**NVARCHAR2**|**문자열**|<xref:System.Data.OracleClient.OracleString>||  
|**RAW**|**Byte\[\]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**REF CURSOR**|||Oracle **REF CURSOR** 데이터 형식은 <xref:System.Data.OracleClient.OracleDataReader> 개체에서 지원되지 않습니다.|  
|**ROWID**|**문자열**|<xref:System.Data.OracleClient.OracleString>||  
|**TIMESTAMP**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**TIMESTAMP WITH LOCAL TIME ZONE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**TIMESTAMP WITH TIME ZONE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**UNSIGNED INTEGER**|**숫자**|<xref:System.Data.OracleClient.OracleNumber>|이 데이터 형식은 **NUMBER\(38\)** 데이터 형식의 별칭이며 <xref:System.Data.OracleClient.OracleDataReader>에서 부호 없는 정수 값 대신 **System.Decimal** 또는 <xref:System.Data.OracleClient.OracleNumber>를 반환하도록 디자인되었습니다.  .NET Framework 데이터 형식을 사용하면 오버플로가 발생할 수 있습니다.|  
|**VARCHAR2**|**문자열**|<xref:System.Data.OracleClient.OracleString>||  
  
 다음 표에는 매개 변수로 바인딩할 때 사용하는 Oracle 데이터 형식과 .NET Framework 데이터 형식\(**System.Data.DbType** 및 <xref:System.Data.OracleClient.OracleType>\)이 나열되어 있습니다.  
  
|Oracle 데이터 형식|매개 변수로 바인딩하는 DbType 열거형|매개 변수로 바인딩하는 OracleType 열거형|설명|  
|-------------------|-----------------------------|---------------------------------|--------|  
|**BFILE**||**BFile**|Oracle에서만 **BFILE**을 **BFILE** 매개 변수로 바인딩할 수 있습니다.  .NET Data Provider for Oracle에서는 **byte\[\]** 또는 <xref:System.Data.OracleClient.OracleBinary> 같은 **BFILE**이 아닌 값을 바인딩하려는 경우 이를 자동으로 생성하지 않습니다.|  
|**BLOB**||**Blob**|Oracle에서만 **BLOB**를 **BLOB** 매개 변수로 바인딩할 수 있습니다.  .NET Data Provider for Oracle에서는 **byte\[\]** 또는 <xref:System.Data.OracleClient.OracleBinary> 같은 **BLOB**이 아닌 값을 바인딩하려는 경우 이를 자동으로 생성하지 않습니다.|  
|**CHAR**|**AnsiStringFixedLength**|**Char**||  
|**CLOB**||**Clob**|Oracle에서만 **CLOB**를 **CLOB** 매개 변수로 바인딩할 수 있습니다.  .NET Data Provider for Oracle에서는 **System.String** 또는 <xref:System.Data.OracleClient.OracleString> 같은 **CLOB**이 아닌 값을 바인딩하려는 경우 이를 자동으로 생성하지 않습니다.|  
|**DATE**|**DateTime**|**DateTime**||  
|**FLOAT**|**Single, Double, Decimal**|**Float, Double, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A>는 **System.Data.DBType** 및 <xref:System.Data.OracleClient.OracleType>을 결정합니다.|  
|**INTEGER**|**SByte, Int16, Int32, Int64, Decimal**|**SByte, Int16, Int32, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A>는 **System.Data.DBType** 및 <xref:System.Data.OracleClient.OracleType>을 결정합니다.|  
|**INTERVAL YEAR TO MONTH**|**Int32**|**IntervalYearToMonth**|<xref:System.Data.OracleClient.OracleType>은 Oracle 9i 클라이언트 및 서버 소프트웨어를 모두 사용할 때만 사용할 수 있습니다.|  
|**INTERVAL DAY TO SECOND**|**개체**|**IntervalDayToSecond**|<xref:System.Data.OracleClient.OracleType>은 Oracle 9i 클라이언트 및 서버 소프트웨어를 모두 사용할 때만 사용할 수 있습니다.|  
|**LONG**|**AnsiString**|**LongVarChar**||  
|**LONG RAW**|**이항**|**LongRaw**||  
|**NCHAR**|**StringFixedLength**|**NChar**||  
|**NCLOB**||**NClob**|Oracle에서만 **NCLOB**를 **NCLOB** 매개 변수로 바인딩할 수 있습니다.  .NET Data Provider for Oracle에서는 **System.String** 또는 <xref:System.Data.OracleClient.OracleString> 같은 **NCLOB**이 아닌 값을 바인딩하려는 경우 이를 자동으로 생성하지 않습니다.|  
|**NUMBER**|**VarNumeric**|**숫자**||  
|**NVARCHAR2**|**문자열**|**NVarChar**||  
|**RAW**|**이항**|**Raw**||  
|**REF CURSOR**||**Cursor**|자세한 내용은 [Oracle REF CURSOR](../../../../docs/framework/data/adonet/oracle-ref-cursors.md)을 참조하세요.|  
|**ROWID**|**AnsiString**|**Rowid**||  
|**TIMESTAMP**|**DateTime**|**타임스탬프**|<xref:System.Data.OracleClient.OracleType>은 Oracle 9i 클라이언트 및 서버 소프트웨어를 모두 사용할 때만 사용할 수 있습니다.|  
|**TIMESTAMP WITH LOCAL TIME ZONE**|**DateTime**|**TimestampLocal**|<xref:System.Data.OracleClient.OracleType>은 Oracle 9i 클라이언트 및 서버 소프트웨어를 모두 사용할 때만 사용할 수 있습니다.|  
|**TIMESTAMP WITH TIME ZONE**|**DateTime**|**TimestampWithTz**|<xref:System.Data.OracleClient.OracleType>은 Oracle 9i 클라이언트 및 서버 소프트웨어를 모두 사용할 때만 사용할 수 있습니다.|  
|**UNSIGNED INTEGER**|**Byte, UInt16, UInt32, UInt64, Decimal**|**Byte, UInt16, Uint32, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A>는 **System.Data.DBType** 및 <xref:System.Data.OracleClient.OracleType>을 결정합니다.|  
|**VARCHAR2**|**AnsiString**|**VarChar**||  
  
 <xref:System.Data.OracleClient.OracleParameter> 개체의 <xref:System.Data.OracleClient.OracleParameter.Value%2A> 속성에서 사용되는 **InputOutput**, **Output** 및 **ReturnValue** **ParameterDirection** 값은 입력 값이 <xref:System.Data.OracleClient.OracleNumber> 또는 <xref:System.Data.OracleClient.OracleString>과 같은 Oracle 데이터 형식이 아닌 경우 .NET Framework 데이터 형식입니다.  이는 **REF CURSOR**, **BFILE** 또는 **LOB** 데이터 형식에는 적용되지 않습니다.  
  
## 참고 항목  
 [Oracle 및 ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)