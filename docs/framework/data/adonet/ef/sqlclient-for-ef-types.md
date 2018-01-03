---
title: "Entity FrameworkTypes용 SqlClient"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2a95ead-c845-4e97-9fb3-04b444f7ed81
caps.latest.revision: "9"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: b04a7199fefc5df93d5e3472163d16c66e9279c1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="sqlclient-for-entity-frameworktypes"></a>Entity FrameworkTypes용 SqlClient
.NET Framework Data Provider for SQL Server(SqlClient) 공급자 매니페스트 파일에는 공급자 기본 형식의 목록, 각 형식의 패싯, 개념적 모델과 저장소 모델 기본 형식 간의 매핑, 개념적 모델과 저장소 모델 기본 형식 간의 승격과 변환 규칙이 포함되어 있습니다.  
  
 다음 표에서 SQL Server 2008에 대 한 유형을 설명 [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)], 및 [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)] 데이터베이스 및 이러한 형식을 개념적에 매핑하는 방법에 대 한 모델 유형을 합니다. 이후 버전의 SQL Server에서 도입된 몇 가지 새로운 형식은 이전 버전의 SQL Server에서는 지원되지 않습니다. 해당 형식은 다음 표에 나와 있습니다.  
  
|공급자 형식<br /><br /> name|공급자 형식<br /><br /> 특성|`EDMSimpleType`<br /><br /> name|패싯|  
|----------------------------|----------------------------------|------------------------------|------------|  
|`bit`|해당 없음|`Edm.Boolean`|해당 없음|  
|`tinyint`|해당 없음|`Edm.Byte`|해당 없음|  
|`smallint`|해당 없음|`Edm.Int16`|해당 없음|  
|`int`|해당 없음|`Edm.Int32`|해당 없음|  
|`bigint`|해당 없음|`Edm.Int64`|해당 없음|  
|`float`|해당 없음|`Edm.Double`|해당 없음|  
|`real`|해당 없음|`Edm.Double`|해당 없음|  
|`decimal`|N/A|`Edm.Decimal`|전체 자릿수:<br /><br /> -최소: 1<br /><br /> -최대: 38<br /><br /> -기본: 18<br /><br /> -상수: False<br /><br /> 배율:<br /><br /> -최소: 0<br /><br /> -최대: 38<br /><br /> -기본: 0<br /><br /> -상수: False|  
|`numeric`|N/A|`Edm.Decimal`|전체 자릿수:<br /><br /> -최소: 1<br /><br /> -최대: 38<br /><br /> -기본: 18<br /><br /> -상수: False<br /><br /> 배율:<br /><br /> -최소: 0<br /><br /> -최대: 38<br /><br /> -기본: 0<br /><br /> -상수: False|  
|`smallmoney`|N/A|`Edm.Decimal`|전체 자릿수:<br /><br /> -기본: 10<br /><br /> -상수: True<br /><br /> 배율:<br /><br /> -기본: 4<br /><br /> -상수: True|  
|`money`|N/A|`Edm.Decimal`|전체 자릿수:<br /><br /> -기본: 19<br /><br /> -상수: True<br /><br /> 배율:<br /><br /> -기본: 4<br /><br /> -상수: True|  
|`binary`|N/A|`Edm.Binary`|최대 길이:<br /><br /> -최소: 1<br /><br /> -최대: 8000<br /><br /> -기본: 8000<br /><br /> -상수: False<br /><br /> FixedLength:<br /><br /> -기본: True<br /><br /> -상수: True|  
|`varbinary`|N/A|`Edm.Binary`|최대 길이:<br /><br /> -최소: 1<br /><br /> -최대: 8000<br /><br /> -기본: 8000<br /><br /> -상수: False<br /><br /> FixedLength:<br /><br /> -기본값: False<br /><br /> -상수: True|  
|`varbinary(max)`<br /><br /> 참고:이 형식에서 지원 되지 않습니다 [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)]합니다.|N/A|`Edm.Binary`|최대 길이:<br /><br /> -기본: 214748364780<br /><br /> -상수: True<br /><br /> FixedLength:<br /><br /> -기본값: False<br /><br /> -상수: True|  
|`image`|N/A|`Edm.Binary`|최대 길이:<br /><br /> -기본: 2147483647<br /><br /> -상수: True<br /><br /> FixedLength:<br /><br /> -기본값: False<br /><br /> -상수: True|  
|`timestamp`|N/A|`Edm.Binary`|최대 길이:<br /><br /> -기본: 8<br /><br /> -상수: True<br /><br /> FixedLength:<br /><br /> -기본: True<br /><br /> -상수: True|  
|`rowversion`|N/A|`Edm.Binary`|최대 길이:<br /><br /> -기본: 8<br /><br /> -상수: True<br /><br /> FixedLength:<br /><br /> -기본: True<br /><br /> -상수: True|  
|`smalldatetime`|N/A|`Edm.DateTime`|전체 자릿수:<br /><br /> -기본: 0<br /><br /> -상수: True|  
|`datetime`|N/A|`Edm.DateTime`|전체 자릿수:<br /><br /> -기본: 3<br /><br /> -상수: True|  
|`date`<br /><br /> 참고:이 형식은 SQL Server 2005 및 SQL Server 2000에서 지원 되지 않습니다.|N/A|`Edm.DateTime`|전체 자릿수:<br /><br /> -기본: 0<br /><br /> -상수: False|  
|`time`<br /><br /> 참고:이 형식은 SQL Server 2005 및 SQL Server 2000에서 지원 되지 않습니다.|N/A|`Edm.Time`|전체 자릿수:<br /><br /> -기본: 7<br /><br /> -상수: False|  
|`datetime2`<br /><br /> 참고:이 형식은 SQL Server 2005 및 SQL Server 2000에서 지원 되지 않습니다.|N/A|`Edm.DateTime`|전체 자릿수:<br /><br /> -기본: 7<br /><br /> -상수: False|  
|`datetimeoffset`<br /><br /> 참고:이 형식은 SQL Server 2005 및 SQL Server 2000에서 지원 되지 않습니다.|N/A|`Edm.DateTimeOffset`|전체 자릿수:<br /><br /> -기본: 7<br /><br /> -상수: False|  
|`nvarchar`<br /><br /> 참고:이 형식에서 지원 되지 않습니다 [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)]합니다.|N/A|`Edm.String`|최대 길이:<br /><br /> -최소: 1<br /><br /> -최대: 4000<br /><br /> -기본: 4000<br /><br /> -상수: False<br /><br /> 유니코드:<br /><br /> -기본: True<br /><br /> -상수: True<br /><br /> FixedLength:<br /><br /> -기본값: False<br /><br /> -상수: True|  
|`varchar`<br /><br /> 참고:이 형식에서 지원 되지 않습니다 [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)]합니다.|N/A|`Edm.String`|최대 길이:<br /><br /> -최소: 1<br /><br /> -최대: 8000<br /><br /> -기본: 8000<br /><br /> -상수: False<br /><br /> 유니코드:<br /><br /> -기본값: False<br /><br /> -상수: True<br /><br /> FixedLength:<br /><br /> -기본값: False<br /><br /> -상수: True|  
|`char`|N/A|`Edm.String`|최대 길이:<br /><br /> -최소: 1<br /><br /> -최대: 8000<br /><br /> -기본: 8000<br /><br /> -상수: False<br /><br /> 유니코드:<br /><br /> -기본값: False<br /><br /> -상수: True<br /><br /> FixedLength:<br /><br /> -기본: True<br /><br /> -상수: True|  
|`nchar`|N/A|`Edm.String`|최대 길이:<br /><br /> -최소: 1<br /><br /> -최대: 4000<br /><br /> -기본: 4000<br /><br /> -상수: False<br /><br /> 유니코드:<br /><br /> -기본: True<br /><br /> -상수: True<br /><br /> FixedLength:<br /><br /> -기본: True<br /><br /> -상수: True|  
|`varchar`(`max`)|N/A|`Edm.String`|최대 길이:<br /><br /> -기본: 2147483647<br /><br /> -상수: True<br /><br /> 유니코드:<br /><br /> -기본값: False<br /><br /> -상수: True<br /><br /> FixedLength:<br /><br /> -기본값: False<br /><br /> -상수: True|  
|`nvarchar`(`max`)|N/A|`Edm.String`|최대 길이:<br /><br /> -기본: 1073741823<br /><br /> -상수: True<br /><br /> 유니코드:<br /><br /> -기본: True<br /><br /> -상수: True<br /><br /> FixedLength:<br /><br /> -기본값: False<br /><br /> -상수: True|  
|`ntext`|같음 비교 가능한: False<br /><br /> 순서를 비교할 수: False|`Edm.String`|최대 길이:<br /><br /> -기본: 1073741823<br /><br /> -상수: True<br /><br /> 유니코드:<br /><br /> -기본값: False<br /><br /> -상수: True<br /><br /> FixedLength:<br /><br /> -기본값: False<br /><br /> -상수: True|  
|`text`|같음 비교 가능한: False<br /><br /> 순서를 비교할 수: False|`Edm.String`|최대 길이:<br /><br /> -기본: 2147483647<br /><br /> -상수: True<br /><br /> 유니코드:<br /><br /> -기본값: False<br /><br /> -상수: True<br /><br /> FixedLength:<br /><br /> -기본값: False<br /><br /> -상수: True|  
|`Unique`<br /><br /> `identifier`|같음 비교 가능한: True<br /><br /> 순서를 비교할 수: True|`Edm.Guid`|N/A|  
|`xml`|같음 비교 가능한: False<br /><br /> 순서를 비교할 수: False|`Edm.String`|최대 길이:<br /><br /> -기본: 1073741823<br /><br /> -상수: True<br /><br /> 유니코드:<br /><br /> -기본: True<br /><br /> -상수: True<br /><br /> FixedLength:<br /><br /> -기본값: False<br /><br /> -상수: True|  
  
## <a name="see-also"></a>참고 항목  
 [CSDL, SSDL 및 MSL 사양](../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
