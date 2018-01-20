---
title: "고가용성 및 재해 복구에 대한 SqlClient 지원"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 61e0b396-09d7-4e13-9711-7dcbcbd103a0
caps.latest.revision: "13"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 4f6ede253f52682cfe5a698cf4fb02841dc4c1e0
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="sqlclient-support-for-high-availability-disaster-recovery"></a>고가용성 및 재해 복구에 대한 SqlClient 지원
이 항목에서는 고가용성, 재해 복구, AlwaysOn 가용성 그룹에 대한 SqlClient 지원([!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)]에 추가됨)에 대해 설명합니다.  [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012에는 AlwaysOn 가용성 그룹 기능이 추가되었습니다. AlwaysOn 가용성 그룹에 대한 자세한 내용은 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 온라인 설명서를 참조하세요.  
  
 이제 연결 속성에 고가용성 재해 복구 AG(가용성 그룹)의 가용성 그룹 수신기 또는 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012 장애 조치(Failover) 클러스터 인스턴스를 지정할 수 있습니다. SqlClient 응용 프로그램이 장애 조치되는 AlwaysOn 데이터베이스에 연결되면 원래 연결이 끊어지고 응용 프로그램이 장애 조치 후 작업을 계속할 수 있도록 새 연결을 열어야 합니다.  
  
 가용성 그룹 수신기 또는 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012 장애 조치 클러스터 인스턴스에 연결하지 않는 경우와 여러 IP 주소가 하나의 호스트 이름에 연결되어 있는 경우에는 SqlClient가 DNS 항목과 연결된 모든 IP 주소를 순차적으로 반복합니다. 이 경우 DNS 서버에서 반환된 첫 번째 IP 주소가 NIC(네트워크 인터페이스 카드)에 바인딩되지 않으면 시간이 많이 걸릴 수 있습니다. 가용성 그룹 수신기 또는 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012 장애 조치 클러스터 인스턴스에 연결할 때 SqlClient는 모든 IP 주소에 병렬로 연결하려고 시도하며 연결에 성공할 경우 드라이버는 보류 중인 연결 시도를 모두 취소합니다.  
  
> [!NOTE]
>  연결 제한 시간을 늘리고 연결 재시도 논리를 구현하면 응용 프로그램이 가용성 그룹에 연결될 가능성이 높아집니다. 그리고 장애 조치 때문에 연결되지 못할 수 있으므로 다시 연결될 때까지 실패한 연결을 다시 시도하는 연결 재시도 논리를 구현해야 합니다.  
  
 [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)]에서 SqlClient에 다음 연결 속성이 추가되었습니다.  
  
-   `ApplicationIntent`  
  
-   `MultiSubnetFailover`  
  
 다음 항목을 사용하여 연결 문자열 키워드를 프로그래밍 방식으로 수정할 수 있습니다.  
  
1.  <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ApplicationIntent%2A>  
  
2.  <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A>  

> [!NOTE]
>  설정 `MultiSubnetFailover` 를 `true` 으로 필요 하지 않습니다 [!INCLUDE[net_v461](../../../../../includes/net-v461-md.md)]) 또는 이후 버전입니다.
  
## <a name="connecting-with-multisubnetfailover"></a>MultiSubnetFailover를 사용하여 연결  
 `MultiSubnetFailover=True` 2012 가용성 그룹 수신기 또는 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012 장애 조치 클러스터 인스턴스에 연결할 때 항상 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]를 지정합니다. `MultiSubnetFailover`를 사용하면 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012의 장애 조치 클러스터 인스턴스 또는 모든 가용성 그룹에 대해 신속하게 장애 조치를 수행하고 단일 및 다중 서브넷 AlwaysOn 토폴로지에 대한 장애 조치에 걸리는 시간을 많이 줄일 수 있습니다. 다중 서브넷 장애 조치가 수행되는 동안 클라이언트는 병렬로 연결을 시도합니다. 서브넷 장애 조치가 수행되는 동안 적극적으로 TCP 연결을 다시 시도합니다.  
  
 `MultiSubnetFailover` 연결 속성은 응용 프로그램이 가용성 그룹 또는 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012 장애 조치 클러스터 인스턴스에 배포되고 SqlClient가 모든 IP 주소에 연결하려고 시도하여 주 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 인스턴스에서 데이터베이스에 연결하려고 시도할 것임을 나타냅니다. 연결에 대해 `MultiSubnetFailover=True`가 지정되어 있으면 클라이언트는 운영 체제의 기본 TCP 재전송 간격보다 빠르게 TCP 연결을 다시 시도합니다. 따라서 AlwaysOn 가용성 그룹 또는 AlwaysOn 장애 조치 클러스터 인스턴스의 장애 조치 후 더 빠르게 다시 연결할 수 있으며, 이는 단일 및 다중 서브넷 가용성 그룹 또는 장애 조치 클러스터 인스턴스 모두에 적용됩니다.  
  
 SqlClient의 연결 문자열 키워드에 대한 자세한 내용은 <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>을 참조하십시오.  
  
 가용성 그룹 수신기 또는 `MultiSubnetFailover=True` 2012 장애 조치 클러스터 인스턴스 이외의 대상에 연결할 때 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]를 지정하면 성능이 저하될 수 있으므로 이는 지원되지 않습니다.  
  
 가용성 그룹의 서버 또는 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012 장애 조치 클러스터 인스턴스에 연결할 때 다음 지침을 따르십시오.  
  
-   단일 서브넷 또는 다중 서브넷에 연결할 때 `MultiSubnetFailover` 연결 속성을 사용합니다. 그러면 두 경우 모두 성능이 향상됩니다.  
  
-   가용성 그룹에 연결하려면 가용성 그룹의 가용성 그룹 수신기를 연결 문자열의 서버로 지정합니다.  
  
-   64개가 넘는 IP 주소로 구성된 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 인스턴스에 연결하면 연결 오류가 발생합니다.  
  
-   `MultiSubnetFailover` 연결 속성을 사용하는 응용 프로그램의 동작은 인증 형식([!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 인증, Kerberos 인증 또는 Windows 인증)에 따라 영향을 받지 않습니다.  
  
-   장애 조치 시간을 수용하고 응용 프로그램 연결 재시도를 줄이도록 `Connect Timeout` 값을 늘립니다.  
  
-   분산 트랜잭션은 지원되지 않습니다.  
  
 읽기 전용 라우팅이 적용되지 않는 경우 다음과 같은 경우 보조 복제본 위치에 연결하면 실패합니다.  
  
1.  보조 복제본 위치가 연결을 수락하도록 구성되어 있지 않은 경우  
  
2.  응용 프로그램이 `ApplicationIntent=ReadWrite`(아래에 설명)를 사용하고 보조 복제본 위치가 읽기 전용 액세스용으로 구성되어 있는 경우  
  
 <xref:System.Data.SqlClient.SqlDependency>는 읽기 전용 보조 복제본에서 지원되지 않습니다.  
  
 주 복제본이 읽기 전용 작업을 거부하도록 구성되어 있고 연결 문자열에 `ApplicationIntent=ReadOnly`가 포함되어 있으면 연결이 실패합니다.  
  
## <a name="upgrading-to-use-multi-subnet-clusters-from-database-mirroring"></a>데이터베이스 미러링에서 다중 서브넷 클러스터를 사용하도록 업그레이드  
 연결 문자열에 <xref:System.ArgumentException> 및 `MultiSubnetFailover` 연결 키워드가 없거나 `Failover Partner`이고 TCP 이외의 프로토콜을 사용하는 경우 연결 오류(`MultiSubnetFailover=True`)가 발생합니다. <xref:System.Data.SqlClient.SqlException>를 사용하고 `MultiSubnetFailover`에서 데이터베이스 미러링 쌍의 일부임을 나타내는 장애 조치 파트너 응답을 반환하는 경우에도 오류([!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)])가 발생합니다.  
  
 현재 데이터베이스 미러링을 사용하는 SqlClient 응용 프로그램을 다중 서브넷 시나리오로 업그레이드하는 경우 `Failover Partner` 연결 속성을 제거하고 해당 속성을 `MultiSubnetFailover`로 설정된 `True`로 바꾼 다음 연결 문자열의 서버 이름을 가용성 그룹 수신기로 바꿉니다. 연결 문자열에 `Failover Partner` 및 `MultiSubnetFailover=True`를 사용하는 경우 드라이버에서 오류가 발생합니다. 그러나 연결 문자열에 `Failover Partner` 및 `MultiSubnetFailover=False` 또는 `ApplicationIntent=ReadWrite`를 사용하는 경우 응용 프로그램에서 데이터베이스 미러링을 사용합니다.  
  
 AG의 주 데이터베이스에서 데이터베이스 미러링이 사용되는 경우 가용성 그룹 수신기 대신 주 데이터베이스에 연결되는 연결 문자열에 `MultiSubnetFailover=True`를 사용하면 드라이버에서 오류를 반환합니다.  
  
## <a name="specifying-application-intent"></a>응용 프로그램 의도 지정  
 `ApplicationIntent=ReadOnly`인 경우 클라이언트는 AlwaysOn 사용 데이터베이스에 연결할 때 읽기 작업을 요청합니다. 서버는 연결할 때와 USE 데이터베이스 문을 수행할 때 AlwaysOn 사용 데이터베이스에만 의도를 적용합니다.  
  
 레거시 읽기 전용 데이터베이스에는 `ApplicationIntent` 키워드를 사용할 수 없습니다.  
  
 데이터베이스는 대상 AlwaysOn 데이터베이스에 대한 읽기 작업을 허용하거나 허용하지 않을 수 있습니다. `ALLOW_CONNECTIONS` 및 `PRIMARY_ROLE``SECONDARY_ROLE` 문의 [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] 절을 사용하여 이를 수행할 수 있습니다.  
  
 `ApplicationIntent` 키워드를 사용하여 읽기 전용 라우팅을 사용하도록 설정할 수 있습니다.  
  
## <a name="read-only-routing"></a>읽기 전용 라우팅  
 읽기 전용 라우팅은 데이터베이스의 읽기 전용 복제본의 가용성을 보장할 수 있는 기능입니다. 읽기 전용 라우팅을 사용하도록 설정하려면  
  
1.  AlwaysOn 가용성 그룹의 가용성 그룹 수신기에 연결해야 합니다.  
  
2.  `ApplicationIntent` 연결 문자열 키워드를 `ReadOnly`로 설정해야 합니다.  
  
3.  읽기 전용 라우팅을 사용할 수 있도록 데이터베이스 관리자가 가용성 그룹을 구성해야 합니다.  
  
 읽기 전용 라우팅을 사용하는 여러 연결이 모두 동일한 읽기 전용 복제본에 연결되지 않을 수 있습니다. 데이터베이스 동기화 또는 서버 라우팅 구성의 변경으로 인해 클라이언트가 서로 다른 읽기 전용 복제본에 연결될 수 있습니다. 모든 읽기 전용 요청을 동일한 읽기 전용 복제본에 연결하도록 하려면 가용성 그룹 수신기를 `Data Source` 연결 문자열 키워드에 전달하지 마십시오. 대신 읽기 전용 인스턴스의 이름을 지정하십시오.  
  
 읽기 전용 라우팅은 먼저 주 복제본에 연결한 다음 사용 가능한 최상의 읽기 가능 보조 복제본을 찾으므로 읽기 전용 라우팅의 경우 주 복제본에 연결하는 경우보다 시간이 더 걸릴 수 있습니다. 따라서 로그인 제한 시간을 늘려야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQL Server 기능 및 ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-features-and-adonet.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
