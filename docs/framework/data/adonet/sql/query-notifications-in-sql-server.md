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
# <a name="query-notifications-in-sql-server"></a><span data-ttu-id="cbaf4-102">SQL Server에서 쿼리 알림</span><span class="sxs-lookup"><span data-stu-id="cbaf4-102">Query Notifications in SQL Server</span></span>
<span data-ttu-id="cbaf4-103">쿼리 알림은 Service Broker 인프라를 기반으로 하며 데이터가 변경된 경우 응용 프로그램에 이를 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbaf4-103">Built upon the Service Broker infrastructure, query notifications allow applications to be notified when data has changed.</span></span> <span data-ttu-id="cbaf4-104">이 기능은 웹 응용 프로그램 같이 데이터베이스의 정보 캐시를 제공하고 원본 데이터가 변경되면 알림을 받아야 하는 응용 프로그램에 매우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaf4-104">This feature is particularly useful for applications that provide a cache of information from a database, such as a Web application, and need to be notified when the source data is changed.</span></span>  
  
 <span data-ttu-id="cbaf4-105">ADO.NET을 사용하여 쿼리 알림을 구현하는 방법은 세 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbaf4-105">There are three ways you can implement query notifications using ADO.NET:</span></span>  
  
1.  <span data-ttu-id="cbaf4-106">하위 수준 구현은 서버측 기능을 노출하여 알림 요청으로 명령을 실행할 수 있도록 하는 `SqlNotificationRequest` 클래스에서 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaf4-106">The low-level implementation is provided by the `SqlNotificationRequest` class that exposes server-side functionality, enabling you to execute a command with a notification request.</span></span>  
  
2.  <span data-ttu-id="cbaf4-107">상위 수준 구현은 원본 응용 프로그램과 SQL Server 간에 알림 기능의 상위 수준 추상화를 제공하여 종속성을 통해 서버의 변경 내용을 감지할 수 있게 해주는 `SqlDependency` 클래스에서 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaf4-107">The high-level implementation is provided by the `SqlDependency` class, which is a class that provides a high-level abstraction of notification functionality between the source application and SQL Server, enabling you to use a dependency to detect changes in the server.</span></span> <span data-ttu-id="cbaf4-108">이는 일반적으로 관리 클라이언트 응용 프로그램에서 .NET Framework Data Provider for SQL Server를 사용하여 SQL Server 알림 기능을 가장 간단하고 효과적으로 활용하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="cbaf4-108">In most cases, this is the simplest and most effective way to leverage SQL Server notifications capability by managed client applications using the .NET Framework Data Provider for SQL Server.</span></span>  
  
3.  <span data-ttu-id="cbaf4-109">또한 ASP.NET 2.0 이상을 사용하여 작성된 웹 응용 프로그램에서는 `SqlCacheDependency` 도우미 클래스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbaf4-109">In addition, Web applications built using ASP.NET 2.0 or later can use the `SqlCacheDependency` helper classes.</span></span>  
  
 <span data-ttu-id="cbaf4-110">쿼리 알림은 원본으로 사용하는 데이터의 변경에 대한 응답으로 표시나 캐시를 새로 고쳐야 하는 응용 프로그램에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaf4-110">Query notifications are used for applications that need to refresh displays or caches in response to changes in underlying data.</span></span> <span data-ttu-id="cbaf4-111">.NET Framework 응용 프로그램에서 Microsoft SQL Server를 사용하여 SQL Server에 명령을 보낼 수 있을 뿐 아니라 동일한 명령을 실행했을 때 처음 검색한 것과 다른 결과 집합이 나오면 알림을 생성하도록 요청할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbaf4-111">Microsoft SQL Server allows .NET Framework applications to send a command to SQL Server and request notification if executing the same command would produce result sets different from those initially retrieved.</span></span> <span data-ttu-id="cbaf4-112">서버에서 생성되는 알림은 나중에 처리되도록 큐를 통해 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbaf4-112">Notifications generated at the server are sent through queues to be processed later.</span></span>  
  
 <span data-ttu-id="cbaf4-113">SELECT 및 EXECUTE 문에 대해 알림을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbaf4-113">You can set up notifications for SELECT and EXECUTE statements.</span></span> <span data-ttu-id="cbaf4-114">EXECUTE 문을 사용할 경우 SQL Server에서는 EXECUTE 문 자체가 아니라 실행되는 명령에 대해 알림을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaf4-114">When using an EXECUTE statement, SQL Server registers a notification for the command executed rather than the EXECUTE statement itself.</span></span> <span data-ttu-id="cbaf4-115">명령은 SELECT 문의 요구 사항과 제한 사항을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaf4-115">The command must meet the requirements and limitations for a SELECT statement.</span></span> <span data-ttu-id="cbaf4-116">알림을 등록하는 명령에 문이 두 개 이상 포함되어 있으면 데이터베이스 엔진은 일괄 처리에 있는 각 문에 대해 알림을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cbaf4-116">When a command that registers a notification contains more than one statement, the Database Engine creates a notification for each statement in the batch.</span></span>  
  
 <span data-ttu-id="cbaf4-117">을 개발 하는 응용 프로그램 데이터가 변경 될 때 신뢰할 수 있는 하위 보조 알림이 필요한 경우 검토 섹션 **효율적인 쿼리 알림 방법 계획** 및 **쿼리에 대 한 대안 알림** 에 [알림 계획](http://go.microsoft.com/fwlink/?LinkId=211984) SQL Server 온라인 설명서의 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="cbaf4-117">If you are developing an application where you need reliable sub-second notifications when data changes, review the sections **Planning an Efficient Query Notifications Strategy** and **Alternatives to Query Notifications** in the [Planning for Notifications](http://go.microsoft.com/fwlink/?LinkId=211984) topic in SQL Server Books Online.</span></span> <span data-ttu-id="cbaf4-118">쿼리 알림 및 SQL Server Service Broker에 대한 자세한 내용은 다음 SQL Server 온라인 설명서의 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cbaf4-118">For more information about Query Notifications and SQL Server Service Broker, see the following links to topics in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="cbaf4-119">**SQL Server 온라인 설명서**</span><span class="sxs-lookup"><span data-stu-id="cbaf4-119">**SQL Server Books Online**</span></span>  
  
-   [<span data-ttu-id="cbaf4-120">쿼리 알림 사용</span><span class="sxs-lookup"><span data-stu-id="cbaf4-120">Using Query Notifications</span></span>](http://msdn.microsoft.com/library/ms175110.aspx)  
  
-   [<span data-ttu-id="cbaf4-121">알림에 대 한 쿼리 만들기</span><span class="sxs-lookup"><span data-stu-id="cbaf4-121">Creating a Query for Notification</span></span>](http://msdn.microsoft.com/library/ms181122.aspx)  
  
-   [<span data-ttu-id="cbaf4-122">Service Broker</span><span class="sxs-lookup"><span data-stu-id="cbaf4-122">Service Broker</span></span>](http://msdn.microsoft.com/library/bb522889.aspx)  
  
-   [<span data-ttu-id="cbaf4-123">Service Broker 개발자 정보 센터</span><span class="sxs-lookup"><span data-stu-id="cbaf4-123">Service Broker Developer InfoCenter</span></span>](http://msdn.microsoft.com/library/ms166100.aspx)  
  
-   [<span data-ttu-id="cbaf4-124">개발 (Service Broker)</span><span class="sxs-lookup"><span data-stu-id="cbaf4-124">Development (Service Broker)</span></span>](http://msdn.microsoft.com/library/bb522908.aspx)  
  
## <a name="in-this-section"></a><span data-ttu-id="cbaf4-125">단원 내용</span><span class="sxs-lookup"><span data-stu-id="cbaf4-125">In This Section</span></span>  
 [<span data-ttu-id="cbaf4-126">쿼리 알림 사용</span><span class="sxs-lookup"><span data-stu-id="cbaf4-126">Enabling Query Notifications</span></span>](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md)  
 <span data-ttu-id="cbaf4-127">쿼리 알림 활성화 및 사용에 필요한 요구 사항 등 쿼리 알림 사용 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaf4-127">Discusses how to use query notifications, including the requirements for enabling and using them.</span></span>  
  
 [<span data-ttu-id="cbaf4-128">ASP.NET 응용 프로그램에서 SqlDependency</span><span class="sxs-lookup"><span data-stu-id="cbaf4-128">SqlDependency in an ASP.NET Application</span></span>](../../../../../docs/framework/data/adonet/sql/sqldependency-in-an-aspnet-app.md)  
 <span data-ttu-id="cbaf4-129">ASP.NET 응용 프로그램에서 쿼리 알림을 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaf4-129">Demonstrates how to use query notifications from an ASP.NET application.</span></span>  
  
 [<span data-ttu-id="cbaf4-130">SqlDependency로 변경 내용 감지</span><span class="sxs-lookup"><span data-stu-id="cbaf4-130">Detecting Changes with SqlDependency</span></span>](../../../../../docs/framework/data/adonet/sql/detecting-changes-with-sqldependency.md)  
 <span data-ttu-id="cbaf4-131">쿼리 결과가 원래 수신된 결과와 다를 때 감지하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaf4-131">Demonstrates how to detect when query results will be different from those originally received.</span></span>  
  
 [<span data-ttu-id="cbaf4-132">SqlNotificationRequest 사용 하 여 SqlCommand 실행</span><span class="sxs-lookup"><span data-stu-id="cbaf4-132">SqlCommand Execution with a SqlNotificationRequest</span></span>](../../../../../docs/framework/data/adonet/sql/sqlcommand-execution-with-a-sqlnotificationrequest.md)  
 <span data-ttu-id="cbaf4-133">쿼리 알림을 사용하기 위해 <xref:System.Data.SqlClient.SqlCommand> 개체를 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaf4-133">Demonstrates configuring a <xref:System.Data.SqlClient.SqlCommand> object to work with a query notification.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="cbaf4-134">참조</span><span class="sxs-lookup"><span data-stu-id="cbaf4-134">Reference</span></span>  
 <xref:System.Data.Sql.SqlNotificationRequest>  
 <span data-ttu-id="cbaf4-135"><xref:System.Data.Sql.SqlNotificationRequest> 클래스와 해당 멤버 전체에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaf4-135">Describes the <xref:System.Data.Sql.SqlNotificationRequest> class and all of its members.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDependency>  
 <span data-ttu-id="cbaf4-136"><xref:System.Data.SqlClient.SqlDependency> 클래스와 해당 멤버 전체에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaf4-136">Describes the <xref:System.Data.SqlClient.SqlDependency> class and all of its members.</span></span>  
  
 <xref:System.Web.Caching.SqlCacheDependency>  
 <span data-ttu-id="cbaf4-137"><xref:System.Web.Caching.SqlCacheDependency> 클래스와 해당 멤버 전체에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cbaf4-137">Describes the <xref:System.Web.Caching.SqlCacheDependency> class and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbaf4-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cbaf4-138">See Also</span></span>  
 [<span data-ttu-id="cbaf4-139">SQL Server 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="cbaf4-139">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)  
 [<span data-ttu-id="cbaf4-140">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="cbaf4-140">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
