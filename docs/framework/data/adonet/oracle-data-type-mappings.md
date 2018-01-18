---
title: "Oracle 데이터 형식 Mappings1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec34ae21-bbbb-4adb-b672-83865e2a8451
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: adb0fc332e00e766a62d0af1c110c5a7ce2d42c3
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="oracle-data-type-mappings"></a>Oracle 데이터 형식 매핑
다음 표에는 Oracle 데이터 형식과 <xref:System.Data.OracleClient.OracleDataReader>에 대한 해당 데이터 형식의 매핑이 나열되어 있습니다.  
  
|Oracle 데이터 형식|OracleDataReader.GetValue에 의해 반환되는 .NET Framework 데이터 형식|OracleDataReader.GetOracleValue에 의해 반환되는 OracleClient 데이터 형식|설명|  
|----------------------|--------------------------------------------------------------------|------------------------------------------------------------------------|-------------|  
|**BFILE**|**Byte[]**|<xref:System.Data.OracleClient.OracleBFile>||  
|**BLOB**|**Byte[]**|<xref:System.Data.OracleClient.OracleLob>||  
|**CHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**CLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**DATE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**FLOAT**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|이 데이터 형식은 대 한 별칭입니다.는 **번호** 데이터 형식으로 디자인 되었습니다 있도록는 <xref:System.Data.OracleClient.OracleDataReader> 반환는 **System.Decimal** 또는 <xref:System.Data.OracleClient.OracleNumber> 부동 소수점 값을 대신 합니다. .NET Framework 데이터 형식을 사용하면 오버플로가 발생할 수 있습니다.|  
|**INTEGER**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|이 데이터 형식은 대 한 별칭입니다.는 **number (38)** 데이터 형식으로 디자인 되었습니다 있도록는 <xref:System.Data.OracleClient.OracleDataReader> 반환는 **System.Decimal** 또는 <xref:System.Data.OracleClient.OracleNumber> 정수 값 대신 합니다. .NET Framework 데이터 형식을 사용하면 오버플로가 발생할 수 있습니다.|  
|**월 간격 연도**|**Int32**|<xref:System.Data.OracleClient.OracleMonthSpan>||  
|**두 번째 간격 일**|**TimeSpan**|<xref:System.Data.OracleClient.OracleTimeSpan>||  
|**LONG**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**긴 원시**|**Byte[]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**NCHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**NCLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**NUMBER**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|.NET Framework 데이터 형식을 사용하면 오버플로가 발생할 수 있습니다.|  
|**NVARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**RAW**|**Byte[]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**REF CURSOR**|||Oracle **REF CURSOR** 데이터 형식에서 지원 되지 않습니다는 <xref:System.Data.OracleClient.OracleDataReader> 개체입니다.|  
|**ROWID**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**타임 스탬프**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**현지 표준 시간대 포함 된 타임 스탬프**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**표준 시간대와 타임 스탬프**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**부호 없는 정수**|**숫자**|<xref:System.Data.OracleClient.OracleNumber>|이 데이터 형식은 대 한 별칭입니다.는 **number (38)** 데이터 형식으로 디자인 되었습니다 있도록는 <xref:System.Data.OracleClient.OracleDataReader> 반환는 **System.Decimal** 또는 <xref:System.Data.OracleClient.OracleNumber> 부호 없는 정수 값 대신 합니다. .NET Framework 데이터 형식을 사용하면 오버플로가 발생할 수 있습니다.|  
|**VARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
  
 다음 표에서 Oracle 데이터 형식과.NET Framework 데이터 형식 (**System.Data.DbType** 및 <xref:System.Data.OracleClient.OracleType>) 매개 변수로 바인딩할 때 사용할 수 있습니다.  
  
|Oracle 데이터 형식|매개 변수로 바인딩하는 DbType 열거형|매개 변수로 바인딩하는 OracleType 열거형|설명|  
|----------------------|-----------------------------------------------|---------------------------------------------------|-------------|  
|**BFILE**||**BFile**|Oracle에만 바인딩할 수 있습니다는 **BFILE** 로 **BFILE** 매개 변수입니다. .NET Data Provider for Oracle 생성 하지 않습니다 자동으로 구독을 하나를 바인딩하려면가 아닌 경우**BFILE** 같은 값 **byte** 또는 <xref:System.Data.OracleClient.OracleBinary>합니다.|  
|**BLOB**||**Blob**|Oracle에만 바인딩할 수 있습니다는 **BLOB** 로 **BLOB** 매개 변수입니다. .NET Data Provider for Oracle 생성 하지 않습니다 자동으로 구독을 하나를 바인딩하려면가 아닌 경우**BLOB** 같은 값 **byte** 또는 <xref:System.Data.OracleClient.OracleBinary>합니다.|  
|**CHAR**|**AnsiStringFixedLength**|**Char**||  
|**CLOB**||**Clob**|Oracle에만 바인딩할 수 있습니다는 **CLOB** 로 **CLOB** 매개 변수입니다. .NET Data Provider for Oracle 생성 하지 않습니다 자동으로 구독을 하나를 바인딩하려면가 아닌 경우**CLOB** 같은 값 **System.String** 또는 <xref:System.Data.OracleClient.OracleString>합니다.|  
|**DATE**|**DateTime**|**DateTime**||  
|**FLOAT**|**Single, Double, Decimal**|**Float, 두 번, 번호**|<xref:System.Data.OracleClient.OracleParameter.Size%2A>결정는 **System.Data.DBType** 및 <xref:System.Data.OracleClient.OracleType>합니다.|  
|**INTEGER**|**SByte, Int16, Int32, Int64, Decimal**|**SByte, Int16, Int32, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A>결정는 **System.Data.DBType** 및 <xref:System.Data.OracleClient.OracleType>합니다.|  
|**월 간격 연도**|**Int32**|**IntervalYearToMonth**|<xref:System.Data.OracleClient.OracleType>은 Oracle 9i 클라이언트 및 서버 소프트웨어를 모두 사용할 때만 사용할 수 있습니다.|  
|**두 번째 간격 일**|**개체**|**IntervalDayToSecond**|<xref:System.Data.OracleClient.OracleType>은 Oracle 9i 클라이언트 및 서버 소프트웨어를 모두 사용할 때만 사용할 수 있습니다.|  
|**LONG**|**AnsiString**|**LongVarChar**||  
|**긴 원시**|**Binary**|**LongRaw**||  
|**NCHAR**|**StringFixedLength**|**NChar**||  
|**NCLOB**||**NClob**|Oracle에만 바인딩할 수 있습니다는 **NCLOB** 로 **NCLOB** 매개 변수입니다. .NET Data Provider for Oracle 생성 하지 않습니다 자동으로 구독을 하나를 바인딩하려면가 아닌 경우**NCLOB** 같은 값 **System.String** 또는 <xref:System.Data.OracleClient.OracleString>합니다.|  
|**NUMBER**|**VarNumeric**|**숫자**||  
|**NVARCHAR2**|**String**|**NVarChar**||  
|**RAW**|**Binary**|**Raw**||  
|**REF CURSOR**||**커서**|자세한 내용은 참조 [Oracle REF Cursor](../../../../docs/framework/data/adonet/oracle-ref-cursors.md)합니다.|  
|**ROWID**|**AnsiString**|**Rowid**||  
|**타임 스탬프**|**DateTime**|**타임스탬프**|<xref:System.Data.OracleClient.OracleType>은 Oracle 9i 클라이언트 및 서버 소프트웨어를 모두 사용할 때만 사용할 수 있습니다.|  
|**현지 표준 시간대 포함 된 타임 스탬프**|**DateTime**|**TimestampLocal**|<xref:System.Data.OracleClient.OracleType>은 Oracle 9i 클라이언트 및 서버 소프트웨어를 모두 사용할 때만 사용할 수 있습니다.|  
|**표준 시간대와 타임 스탬프**|**DateTime**|**TimestampWithTz**|<xref:System.Data.OracleClient.OracleType>은 Oracle 9i 클라이언트 및 서버 소프트웨어를 모두 사용할 때만 사용할 수 있습니다.|  
|**부호 없는 정수**|**Byte, UInt16, UInt32, UInt64, Decimal**|**Byte, UInt16, Uint32, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A>결정는 **System.Data.DBType** 및 <xref:System.Data.OracleClient.OracleType>합니다.|  
|**VARCHAR2**|**AnsiString**|**VarChar**||  
  
 **InputOutput**, **출력**, 및 **ReturnValue** **ParameterDirection** 사용 하는 값은 <xref:System.Data.OracleClient.OracleParameter.Value%2A> 는 의속성<xref:System.Data.OracleClient.OracleParameter> 입력된 값이 Oracle 데이터 형식 개체는.NET Framework 데이터 형식 (예를 들어 <xref:System.Data.OracleClient.OracleNumber> 또는 <xref:System.Data.OracleClient.OracleString>). 에 적용 되지 않습니다 **REF CURSOR**, **BFILE**, 또는 **LOB** 데이터 형식입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Oracle 및 ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
