---
title: "SQL Server에서 쿼리 알림"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f0ba1a1-3180-4af8-87f7-c795dc8f8f55
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 854407d2e6d1341d5917cc78664c1f653e55fa35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="query-notifications-in-sql-server"></a>SQL Server에서 쿼리 알림
쿼리 알림은 Service Broker 인프라를 기반으로 하며 데이터가 변경된 경우 응용 프로그램에 이를 알릴 수 있습니다. 이 기능은 웹 응용 프로그램 같이 데이터베이스의 정보 캐시를 제공하고 원본 데이터가 변경되면 알림을 받아야 하는 응용 프로그램에 매우 유용합니다.  
  
 ADO.NET을 사용하여 쿼리 알림을 구현하는 방법은 세 가지가 있습니다.  
  
1.  하위 수준 구현은 서버측 기능을 노출하여 알림 요청으로 명령을 실행할 수 있도록 하는 `SqlNotificationRequest` 클래스에서 제공합니다.  
  
2.  상위 수준 구현은 원본 응용 프로그램과 SQL Server 간에 알림 기능의 상위 수준 추상화를 제공하여 종속성을 통해 서버의 변경 내용을 감지할 수 있게 해주는 `SqlDependency` 클래스에서 제공합니다. 이는 일반적으로 관리 클라이언트 응용 프로그램에서 .NET Framework Data Provider for SQL Server를 사용하여 SQL Server 알림 기능을 가장 간단하고 효과적으로 활용하는 방법입니다.  
  
3.  또한 ASP.NET 2.0 이상을 사용하여 작성된 웹 응용 프로그램에서는 `SqlCacheDependency` 도우미 클래스를 사용할 수 있습니다.  
  
 쿼리 알림은 원본으로 사용하는 데이터의 변경에 대한 응답으로 표시나 캐시를 새로 고쳐야 하는 응용 프로그램에 유용합니다. .NET Framework 응용 프로그램에서 Microsoft SQL Server를 사용하여 SQL Server에 명령을 보낼 수 있을 뿐 아니라 동일한 명령을 실행했을 때 처음 검색한 것과 다른 결과 집합이 나오면 알림을 생성하도록 요청할 수도 있습니다. 서버에서 생성되는 알림은 나중에 처리되도록 큐를 통해 전송됩니다.  
  
 SELECT 및 EXECUTE 문에 대해 알림을 설정할 수 있습니다. EXECUTE 문을 사용할 경우 SQL Server에서는 EXECUTE 문 자체가 아니라 실행되는 명령에 대해 알림을 등록합니다. 명령은 SELECT 문의 요구 사항과 제한 사항을 따라야 합니다. 알림을 등록하는 명령에 문이 두 개 이상 포함되어 있으면 데이터베이스 엔진은 일괄 처리에 있는 각 문에 대해 알림을 만듭니다.  
  
 을 개발 하는 응용 프로그램 데이터가 변경 될 때 신뢰할 수 있는 하위 보조 알림이 필요한 경우 검토 섹션 **효율적인 쿼리 알림 방법 계획** 및 **쿼리에 대 한 대안 알림** 에 [알림 계획](http://go.microsoft.com/fwlink/?LinkId=211984) SQL Server 온라인 설명서의 항목입니다. 쿼리 알림 및 SQL Server Service Broker에 대한 자세한 내용은 다음 SQL Server 온라인 설명서의 항목을 참조하세요.  
  
 **SQL Server 온라인 설명서**  
  
-   [쿼리 알림 사용](http://msdn.microsoft.com/library/ms175110.aspx)  
  
-   [알림에 대 한 쿼리 만들기](http://msdn.microsoft.com/library/ms181122.aspx)  
  
-   [Service Broker](http://msdn.microsoft.com/library/bb522889.aspx)  
  
-   [Service Broker 개발자 정보 센터](http://msdn.microsoft.com/library/ms166100.aspx)  
  
-   [개발 (Service Broker)](http://msdn.microsoft.com/library/bb522908.aspx)  
  
## <a name="in-this-section"></a>단원 내용  
 [쿼리 알림 사용](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md)  
 쿼리 알림 활성화 및 사용에 필요한 요구 사항 등 쿼리 알림 사용 방법을 설명합니다.  
  
 [ASP.NET 응용 프로그램에서 SqlDependency](../../../../../docs/framework/data/adonet/sql/sqldependency-in-an-aspnet-app.md)  
 ASP.NET 응용 프로그램에서 쿼리 알림을 사용하는 방법에 대해 설명합니다.  
  
 [SqlDependency로 변경 내용 감지](../../../../../docs/framework/data/adonet/sql/detecting-changes-with-sqldependency.md)  
 쿼리 결과가 원래 수신된 결과와 다를 때 감지하는 방법에 대해 설명합니다.  
  
 [SqlNotificationRequest 사용 하 여 SqlCommand 실행](../../../../../docs/framework/data/adonet/sql/sqlcommand-execution-with-a-sqlnotificationrequest.md)  
 쿼리 알림을 사용하기 위해 <xref:System.Data.SqlClient.SqlCommand> 개체를 구성하는 방법에 대해 설명합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.Data.Sql.SqlNotificationRequest>  
 <xref:System.Data.Sql.SqlNotificationRequest> 클래스와 해당 멤버 전체에 대해 설명합니다.  
  
 <xref:System.Data.SqlClient.SqlDependency>  
 <xref:System.Data.SqlClient.SqlDependency> 클래스와 해당 멤버 전체에 대해 설명합니다.  
  
 <xref:System.Web.Caching.SqlCacheDependency>  
 <xref:System.Web.Caching.SqlCacheDependency> 클래스와 해당 멤버 전체에 대해 설명합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQL Server 및 ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
