---
title: 어떤&#39;ADO.NET의 새로운 s
ms.date: 03/30/2017
ms.assetid: 3bb65d38-cce2-46f5-b979-e5c505e95e10
ms.openlocfilehash: eb06681a55f1bd2abffb2e7169fa3bf892cd7313
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33366036"
---
# <a name="what39s-new-in-adonet"></a>어떤&#39;ADO.NET의 새로운 s
다음은 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]에서 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]의 새로운 기능입니다.  
  
## <a name="sqlclient-data-provider"></a>SqlClient Data Provider  
 다음 기능은의 새로운는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for SQL Server에서 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]:  
  
-   ConnectRetryCount 및 ConnectRetryInterval 연결 문자열 키워드(<xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>)를 사용하면 유휴 연결 복원 기능을 제어할 수 있습니다.  
  
-   에서 스트리밍 지원은 SQL Server 응용 프로그램에 서버에서 데이터를 구조화 하는 시나리오를 지원 합니다.  참조 [SqlClient 스트리밍 지원](../../../../docs/framework/data/adonet/sqlclient-streaming-support.md) 자세한 정보에 대 한 합니다.  
  
-   비동기 프로그래밍에 대한 지원이 추가되었습니다.  참조 [비동기 프로그래밍](../../../../docs/framework/data/adonet/asynchronous-programming.md) 자세한 정보에 대 한 합니다.  
  
-   이제 연결 실패가 확장 이벤트 로그에 기록됩니다. 자세한 내용은 [ADO.NET의 데이터 추적](../../../../docs/framework/data/adonet/data-tracing.md)을 참조하세요.  
  
-   이제 SqlClient에서는 SQL Server의 고가용성, 재해 복구 기능, AlwaysOn 지원 합니다. 자세한 내용은 참조 [고가용성, 재해 복구에 대 한 SqlClient 지원](../../../../docs/framework/data/adonet/sql/sqlclient-support-for-high-availability-disaster-recovery.md)합니다.  
  
-   암호를 변수로 전달할 수 있습니다는 <xref:System.Security.SecureString> SQL Server 인증을 사용 하는 경우. 자세한 내용은 <xref:System.Data.SqlClient.SqlCredential>를 참조하세요.  
  
-   때 `TrustServerCertificate` false 및 `Encrypt` 가 true 이면 연결 문자열에 지정 된 서버 이름 (또는 IP 주소)는 SQL Server SSL 인증서에 서버 이름 (또는 IP 주소) 정확히 일치 해야 합니다. 그렇지 않으면 연결을 시도할 경우 실패합니다. 자세한 내용은 `Encrypt`의 <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> 연결 옵션에 대한 설명을 참조하세요.  
  
     이러한 변경으로 인해 기존 응용 프로그램이 더 이상 연결되지 않는 경우 다음 중 하나를 사용하여 응용 프로그램을 수정하면 됩니다.  
  
    -   CN(일반 이름) 또는 SAN(주체 대체 이름) 필드에 약식 이름을 지정하는 인증서를 발급합니다. 이 방법은 데이터베이스 미러링에 적용됩니다.  
  
    -   정규화된 도메인 이름에 약식 이름을 매핑하는 별칭을 추가합니다.  
  
    -   연결 문자열에서 정규화된 도메인 이름을 사용합니다.  
  
-   SqlClient는 확장된 보호를 지원합니다. 확장 된 보호에 대 한 자세한 내용은 참조 [는 데이터베이스를 사용 하 여 확장 된 보호 엔진에 연결](http://go.microsoft.com/fwlink/?LinkId=219978)합니다.  
  
-   SqlClient는 LocalDB 데이터베이스에 대한 연결을 지원합니다. 자세한 내용은 참조 [LocalDB에 대 한 SqlClient 지원](../../../../docs/framework/data/adonet/sql/sqlclient-support-for-localdb.md)합니다.  
  
-   `Type System Version=SQL Server 2012;`는 `Type System Version` 연결 속성에 전달되는 새로운 값입니다. `Type System Version=Latest;` 값은 더 이상 사용되지 않으며 `Type System Version=SQL Server 2008;`과 동일해졌습니다. 자세한 내용은 <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>을 참조하세요.  
  
-   SqlClient에서는 SQL Server 2008에 추가된 기능인 스파스 열에 대한 추가 지원을 제공합니다. 응용 프로그램이 이미 스파스 열을 사용하는 테이블의 데이터에 액세스하는 경우 성능이 향상됩니다. <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>의 IsColumnSet 열은 해당 열이 열 집합의 멤버인 스파스 열인지 여부를 나타냅니다. <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> 열이 스파스 열인지 여부를 나타냅니다 (참조 [SQL Server 스키마 컬렉션](../../../../docs/framework/data/adonet/sql-server-schema-collections.md) 자세한 정보에 대 한). 스파스 열에 대 한 자세한 내용은 참조 [스파스 열 사용](http://go.microsoft.com/fwlink/?LinkId=224244)합니다.  
  
-   공간 데이터 형식이 포함되어 있는 Microsoft.SqlServer.Types.dll 어셈블리가 버전 10.0에서 버전 11.0으로 업그레이드되었습니다. 이 어셈블리를 참조하는 응용 프로그램은 제대로 실행되지 않을 수 있습니다. 자세한 내용은 참조 [데이터베이스 엔진 기능의 주요 변경 내용](http://go.microsoft.com/fwlink/?LinkId=224367)합니다.  
  
## <a name="adonet-entity-framework"></a>ADO.NET Entity Framework  
 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]에는 Entity Framework 5.0을 사용할 경우 새로운 시나리오를 사용할 수 있게 하는 API가 추가되었습니다. Entity Framework 5.0에 추가 된 기능과 개선 사항에 대 한 자세한 내용은 다음 항목을 참조 하십시오.: [새로운](http://go.microsoft.com/fwlink/?LinkID=251106) 및 [Entity Framework 릴리스 및 버전 관리](http://go.microsoft.com/fwlink/?LinkId=234899)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ADO.NET](../../../../docs/framework/data/adonet/index.md)  
 [ADO.NET 개요](../../../../docs/framework/data/adonet/ado-net-overview.md)  
 [SQL Server 및 ADO.NET](../../../../docs/framework/data/adonet/sql/index.md)  
 [WCF Data Services의 새로운 기능](http://msdn.microsoft.com/library/cf22cad5-b8d9-472b-8d7c-b863b64eaae8)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
