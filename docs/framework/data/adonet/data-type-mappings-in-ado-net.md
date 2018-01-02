---
title: "ADO.NET에서 데이터 형식 매핑"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4afab94-ada6-4c77-a73c-41f17bae6b5a
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: b30f4e36ffd98289bb971e04b55b0249138e0efd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="data-type-mappings-in-adonet"></a>ADO.NET에서 데이터 형식 매핑
.NET Framework는 런타임에 형식이 선언, 사용 및 관리되는 방법을 정의하는 공용 형식 시스템을 기반으로 합니다. .NET Framework는 값 형식과 참조 형식으로 구성되며, 두 형식 모두 <xref:System.Object> 기본 형식에서 파생됩니다. 데이터 소스로 작업할 경우 데이터 형식을 명시적으로 지정하지 않으면 데이터 공급자에서 데이터 형식이 유추됩니다. 예를 들어 <xref:System.Data.DataSet> 개체는 모든 데이터 소스에 대해 독립적입니다. `DataSet`의 데이터는 데이터 소스에서 검색되며 변경 내용은 `DataAdapter`를 사용하여 데이터 소스에 다시 적용됩니다. 즉, `DataAdapter`가 <xref:System.Data.DataTable>의 `DataSet`을 데이터 소스의 값으로 채울 때 `DataTable` 열의 결과 데이터 형식은 데이터 소스에 연결하는 데 사용되는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 데이터 공급자별 형식이 아닌, [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 형식입니다.  
  
 마찬가지로 `DataReader`가 데이터 소스의 값을 반환할 때 결과 값은 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 형식의 지역 변수에 저장됩니다. `Fill`의 `DataAdapter` 작업과 `Get`의 `DataReader` 메서드 모두에서 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 형식은 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 데이터 공급자로부터 반환된 값에서 유추됩니다.  
  
 반환되는 값의 형식을 알고 있는 경우에는 유추되는 데이터 형식을 사용하는 대신 `DataReader`의 형식화된 접근자 메서드를 사용할 수 있습니다. 형식화된 접근자 메서드는 값을 특정 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 형식으로 반환하여 추가로 형식을 변환할 필요가 없도록 하므로 더 나은 성능을 얻을 수 있습니다.  
  
> [!NOTE]
>  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 데이터 공급자 데이터 형식의 Null 값은 `DBNull.Value`로 표시됩니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [SQL Server 데이터 형식 매핑](../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 <xref:System.Data.SqlClient>의 유추된 데이터 형식 매핑과 데이터 접근자 메서드 목록을 제공합니다.  
  
 [OLE DB 데이터 형식 매핑](../../../../docs/framework/data/adonet/ole-db-data-type-mappings.md)  
 <xref:System.Data.OleDb>의 유추된 데이터 형식 매핑과 데이터 접근자 메서드 목록을 제공합니다.  
  
 [ODBC 데이터 형식 매핑](../../../../docs/framework/data/adonet/odbc-data-type-mappings.md)  
 <xref:System.Data.Odbc>의 유추된 데이터 형식 매핑과 데이터 접근자 메서드 목록을 제공합니다.  
  
 [Oracle 데이터 형식 매핑](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 <xref:System.Data.OracleClient>의 유추된 데이터 형식 매핑과 데이터 접근자 메서드 목록을 제공합니다.  
  
 [부동 소수점 숫자](../../../../docs/framework/data/adonet/floating-point-numbers.md)  
 개발자가 부동 소수점 숫자를 사용할 때 자주 발생하는 문제에 대해 설명합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQL Server 데이터 형식 및 ADO.NET](../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [매개 변수 및 매개 변수 데이터 형식 구성](../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 [데이터베이스 스키마 정보 검색](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [공용 형식 시스템](../../../../docs/standard/base-types/common-type-system.md)  
 [형식 변환](http://msdn.microsoft.com/en-us/6038316e-bdaf-4f55-8006-407f591ce156)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
