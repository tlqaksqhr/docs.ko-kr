---
title: "쿼리 알림 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a5333e19-8e55-4aa9-82dc-ca8745e516ed
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 473f1ca54d54a1d852edaed424729778e5a7513d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="enabling-query-notifications"></a><span data-ttu-id="d0388-102">쿼리 알림 사용</span><span class="sxs-lookup"><span data-stu-id="d0388-102">Enabling Query Notifications</span></span>
<span data-ttu-id="d0388-103">쿼리 알림을 사용하는 응용 프로그램에는 공통적인 요구 사항이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0388-103">Applications that consume query notifications have a common set of requirements.</span></span> <span data-ttu-id="d0388-104">SQL 쿼리 알림을 지원하도록 데이터 소스를 올바르게 구성해야 하며, 사용자는 올바른 클라이언트측 및 서버측 권한을 가지고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0388-104">Your data source must be correctly configured to support SQL query notifications, and the user must have the correct client-side and server-side permissions.</span></span>  
  
 <span data-ttu-id="d0388-105">쿼리 알림을 사용하려면 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0388-105">To use query notifications you must:</span></span>  
  
-   <span data-ttu-id="d0388-106">데이터베이스에 대해 쿼리 알림을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="d0388-106">Enable query notifications for your database.</span></span>  
  
-   <span data-ttu-id="d0388-107">데이터베이스 연결에 사용되는 사용자 ID에 필요한 권한이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d0388-107">Ensure that the user ID used to connect to the database has the necessary permissions.</span></span>  
  
-   <span data-ttu-id="d0388-108"><xref:System.Data.SqlClient.SqlCommand> 개체를 사용하여 <xref:System.Data.SqlClient.SqlDependency> 또는 <xref:System.Data.Sql.SqlNotificationRequest>와 같은 관련된 알림 개체로 올바른 SELECT 문을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d0388-108">Use a <xref:System.Data.SqlClient.SqlCommand> object to execute a valid SELECT statement with an associated notification object—either <xref:System.Data.SqlClient.SqlDependency> or <xref:System.Data.Sql.SqlNotificationRequest>.</span></span>  
  
-   <span data-ttu-id="d0388-109">모니터링하는 데이터가 변경될 경우 알림을 처리하는 코드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d0388-109">Provide code to process the notification if the data being monitored changes.</span></span>  
  
## <a name="query-notifications-requirements"></a><span data-ttu-id="d0388-110">쿼리 알림 요구 사항</span><span class="sxs-lookup"><span data-stu-id="d0388-110">Query Notifications Requirements</span></span>  
 <span data-ttu-id="d0388-111">다음과 같은 요구 사항을 충족하는 SELECT 문에 대해 쿼리 알림을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0388-111">Query notifications are supported only for SELECT statements that meet a list of specific requirements.</span></span> <span data-ttu-id="d0388-112">다음 표에는 SQL Server 온라인 설명서의 Service Broker 및 쿼리 알림 문서에 대한 링크가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0388-112">The following table provides links to the Service Broker and Query Notifications documentation in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="d0388-113">**SQL Server 온라인 설명서**</span><span class="sxs-lookup"><span data-stu-id="d0388-113">**SQL Server Books Online**</span></span>  
  
-   [<span data-ttu-id="d0388-114">알림에 대 한 쿼리 만들기</span><span class="sxs-lookup"><span data-stu-id="d0388-114">Creating a Query for Notification</span></span>](http://msdn.microsoft.com/library/ms181122.aspx)  
  
-   [<span data-ttu-id="d0388-115">Service Broker에 대 한 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="d0388-115">Security Considerations for Service Broker</span></span>](http://msdn.microsoft.com/library/ms166059.aspx)  
  
-   [<span data-ttu-id="d0388-116">보안 및 보호 (Service Broker)</span><span class="sxs-lookup"><span data-stu-id="d0388-116">Security and Protection (Service Broker)</span></span>](http://msdn.microsoft.com/library/bb522911.aspx)  
  
-   [<span data-ttu-id="d0388-117">알림 서비스에 대 한 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="d0388-117">Security Considerations for Notifications Services</span></span>](http://msdn.microsoft.com/library/ms172604.aspx)  
  
-   [<span data-ttu-id="d0388-118">쿼리 알림 사용 권한</span><span class="sxs-lookup"><span data-stu-id="d0388-118">Query Notification Permissions</span></span>](http://msdn.microsoft.com/library/ms188311.aspx)  
  
-   [<span data-ttu-id="d0388-119">Service Broker에 대 한 국가별 고려 사항</span><span class="sxs-lookup"><span data-stu-id="d0388-119">International Considerations for Service Broker</span></span>](http://msdn.microsoft.com/library/ms166028.aspx)  
  
-   [<span data-ttu-id="d0388-120">솔루션 디자인 고려 사항 (Service Broker)</span><span class="sxs-lookup"><span data-stu-id="d0388-120">Solution Design Considerations (Service Broker)</span></span>](http://msdn.microsoft.com/library/bb522899.aspx)  
  
-   [<span data-ttu-id="d0388-121">Service Broker 개발자 정보 센터</span><span class="sxs-lookup"><span data-stu-id="d0388-121">Service Broker Developer InfoCenter</span></span>](http://msdn.microsoft.com/library/ms166100.aspx)  
  
-   [<span data-ttu-id="d0388-122">개발자 가이드 (Service Broker)</span><span class="sxs-lookup"><span data-stu-id="d0388-122">Developer's Guide (Service Broker)</span></span>](http://msdn.microsoft.com/library/bb522908.aspx)  
  
## <a name="enabling-query-notifications-to-run-sample-code"></a><span data-ttu-id="d0388-123">쿼리 알림 활성화 샘플 코드</span><span class="sxs-lookup"><span data-stu-id="d0388-123">Enabling Query Notifications to Run Sample Code</span></span>  
 <span data-ttu-id="d0388-124">Service Broker를 사용 하도록 설정 하는 **AdventureWorks** SQL Server Management Studio를 사용 하 여 데이터베이스에서 다음 TRANSACT-SQL 문을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0388-124">To enable Service Broker on the **AdventureWorks** database by using SQL Server Management Studio, execute the following Transact-SQL statement:</span></span>  
  
 `ALTER DATABASE AdventureWorks SET ENABLE_BROKER;`  
  
 <span data-ttu-id="d0388-125">쿼리 알림 샘플을 올바르게 실행하려면 데이터베이스 서버에서 다음 Transact-SQL 문을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0388-125">For the query notification samples to run correctly, the following Transact-SQL statements must be executed on the database server.</span></span>  
  
```  
CREATE QUEUE ContactChangeMessages;  
  
CREATE SERVICE ContactChangeNotifications  
  ON QUEUE ContactChangeMessages  
([http://schemas.microsoft.com/SQL/Notifications/PostQueryNotification]);  
```  
  
## <a name="query-notifications-permissions"></a><span data-ttu-id="d0388-126">쿼리 알림 권한</span><span class="sxs-lookup"><span data-stu-id="d0388-126">Query Notifications Permissions</span></span>  
 <span data-ttu-id="d0388-127">알림 요청 명령을 실행하는 사용자는 서버에 대해 SUBSCRIBE QUERY NOTIFICATIONS 데이터베이스 권한을 가지고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0388-127">Users who execute commands requesting notification must have SUBSCRIBE QUERY NOTIFICATIONS database permission on the server.</span></span>  
  
 <span data-ttu-id="d0388-128">부분 신뢰 상황에서 실행되는 클라이언트측 코드의 경우에는 <xref:System.Data.SqlClient.SqlClientPermission>이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d0388-128">Client-side code that runs in a partial trust situation requires the <xref:System.Data.SqlClient.SqlClientPermission>.</span></span>  
  
 <span data-ttu-id="d0388-129">다음 코드에서는 <xref:System.Data.SqlClient.SqlClientPermission> 개체를 만들고 <xref:System.Security.Permissions.PermissionState>를 <xref:System.Security.Permissions.PermissionState.Unrestricted>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d0388-129">The following code creates a <xref:System.Data.SqlClient.SqlClientPermission> object, setting the <xref:System.Security.Permissions.PermissionState> to <xref:System.Security.Permissions.PermissionState.Unrestricted>.</span></span> <span data-ttu-id="d0388-130"><xref:System.Security.CodeAccessPermission.Demand%2A>는 호출 스택의 상위 호출자에게 권한이 없는 경우 런타임에 <xref:System.Security.SecurityException>을 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="d0388-130">The <xref:System.Security.CodeAccessPermission.Demand%2A> will force a <xref:System.Security.SecurityException> at run time if all callers higher in the call stack have not been granted the permission.</span></span>  
  
 [!code-csharp[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/CS/source.cs#1)]
 [!code-vb[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/VB/source.vb#1)]  
  
## <a name="choosing-a-notification-object"></a><span data-ttu-id="d0388-131">알림 개체 선택</span><span class="sxs-lookup"><span data-stu-id="d0388-131">Choosing a Notification Object</span></span>  
 <span data-ttu-id="d0388-132">쿼리 알림 API에서는 알림을 처리하기 위한 두 개의 개체인 <xref:System.Data.SqlClient.SqlDependency> 및 <xref:System.Data.Sql.SqlNotificationRequest>를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d0388-132">The query notifications API provides two objects to process notifications: <xref:System.Data.SqlClient.SqlDependency> and <xref:System.Data.Sql.SqlNotificationRequest>.</span></span> <span data-ttu-id="d0388-133">일반적으로 대부분의 비 ASP.NET 응용 프로그램에서는 <xref:System.Data.SqlClient.SqlDependency> 개체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d0388-133">In general, most non-ASP.NET applications should use the <xref:System.Data.SqlClient.SqlDependency> object.</span></span> <span data-ttu-id="d0388-134">ASP.NET 응용 프로그램에서는 상위 수준의 <xref:System.Web.Caching.SqlCacheDependency>를 사용하여 <xref:System.Data.SqlClient.SqlDependency>를 래핑하고 알림 및 캐시 개체를 관리하기 위한 프레임워크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d0388-134">ASP.NET applications should use the higher-level <xref:System.Web.Caching.SqlCacheDependency>, which wraps <xref:System.Data.SqlClient.SqlDependency> and provides a framework for administering the notification and cache objects.</span></span>  
  
### <a name="using-sqldependency"></a><span data-ttu-id="d0388-135">SqlDependency 사용</span><span class="sxs-lookup"><span data-stu-id="d0388-135">Using SqlDependency</span></span>  
 <span data-ttu-id="d0388-136"><xref:System.Data.SqlClient.SqlDependency>를 사용하려면 사용 중인 SQL Server 데이터베이스에 대해 Service Broker를 활성화해야 하며 사용자는 알림을 수신할 수 있는 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0388-136">To use <xref:System.Data.SqlClient.SqlDependency>, Service Broker must be enabled for the SQL Server database being used, and users must have permissions to receive notifications.</span></span> <span data-ttu-id="d0388-137">알림 큐 같은 Service Broker 개체는 미리 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0388-137">Service Broker objects, such as the notification queue, are predefined.</span></span>  
  
 <span data-ttu-id="d0388-138">또한 <xref:System.Data.SqlClient.SqlDependency>는 작업자 스레드를 자동으로 실행하여 큐에 게시되는 알림을 처리하고, Service Broker 메시지를 구문 분석하여 해당 정보를 이벤트 인수 데이터로 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="d0388-138">In addition, <xref:System.Data.SqlClient.SqlDependency> automatically launches a worker thread to process notifications as they are posted to the queue; it also parses the Service Broker message, exposing the information as event argument data.</span></span> <span data-ttu-id="d0388-139"><xref:System.Data.SqlClient.SqlDependency>는 `Start` 메서드를 호출하여 데이터베이스에 대해 종속성을 설정함으로써 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0388-139"><xref:System.Data.SqlClient.SqlDependency> must be initialized by calling the `Start` method to establish a dependency to the database.</span></span> <span data-ttu-id="d0388-140">이 메서드는 응용 프로그램을 초기화하는 동안 필요한 데이터베이스 연결마다 한 번씩만 호출해야 하는 정적 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="d0388-140">This is a static method that needs to be called only once during application initialization for each database connection required.</span></span> <span data-ttu-id="d0388-141">만들어진 각 종속성 연결에 대해 응용 프로그램이 종료될 때 `Stop` 메서드를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0388-141">The `Stop` method should be called at application termination for each dependency connection that was made.</span></span>  
  
### <a name="using-sqlnotificationrequest"></a><span data-ttu-id="d0388-142">SqlNotificationRequest 사용</span><span class="sxs-lookup"><span data-stu-id="d0388-142">Using SqlNotificationRequest</span></span>  
 <span data-ttu-id="d0388-143">이와 반대로 <xref:System.Data.Sql.SqlNotificationRequest>를 사용하려면 전체 수신 인프라를 직접 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0388-143">In contrast, <xref:System.Data.Sql.SqlNotificationRequest> requires you to implement the entire listening infrastructure yourself.</span></span> <span data-ttu-id="d0388-144">또한 큐, 서비스, 큐에서 지원하는 메시지 유형 같은 모든 지원되는 Service Broker 개체를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0388-144">In addition, all the supporting Service Broker objects such as the queue, service, and message types supported by the queue must be defined.</span></span> <span data-ttu-id="d0388-145">이 수동 접근 방식은 응용 프로그램에 특별한 알림 메시지 또는 알림 동작이 필요하거나 응용 프로그램이 보다 큰 Service Broker 응용 프로그램에 속해 있는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d0388-145">This manual approach is useful if your application requires special notification messages or notification behaviors, or if your application is part of a larger Service Broker application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0388-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d0388-146">See Also</span></span>  
 [<span data-ttu-id="d0388-147">SQL Server에서 쿼리 알림</span><span class="sxs-lookup"><span data-stu-id="d0388-147">Query Notifications in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)  
 [<span data-ttu-id="d0388-148">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="d0388-148">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
