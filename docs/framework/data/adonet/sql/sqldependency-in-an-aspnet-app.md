---
title: ASP.NET 응용 프로그램에서 SqlDependency
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ff226ce3-f6b5-47a1-8d22-dc78b67e07f5
ms.openlocfilehash: 51df8ad695b3e59b368499d35ac76cc7ac0cd6e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33363366"
---
# <a name="sqldependency-in-an-aspnet-application"></a><span data-ttu-id="9ec84-102">ASP.NET 응용 프로그램에서 SqlDependency</span><span class="sxs-lookup"><span data-stu-id="9ec84-102">SqlDependency in an ASP.NET Application</span></span>
<span data-ttu-id="9ec84-103">이 단원의 예제에서는 ASP.NET <xref:System.Data.SqlClient.SqlDependency> 개체를 활용하여 <xref:System.Web.Caching.SqlCacheDependency>를 간접적으로 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9ec84-103">The example in this section shows how to use <xref:System.Data.SqlClient.SqlDependency> indirectly by leveraging the ASP.NET <xref:System.Web.Caching.SqlCacheDependency> object.</span></span> <span data-ttu-id="9ec84-104"><xref:System.Web.Caching.SqlCacheDependency> 개체에서는 <xref:System.Data.SqlClient.SqlDependency>를 사용하여 알림을 수신하고 캐시를 올바르게 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec84-104">The <xref:System.Web.Caching.SqlCacheDependency> object uses a <xref:System.Data.SqlClient.SqlDependency> to listen for notifications and correctly update the cache.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ec84-105">스크립트를 실행 하 여 쿼리 알림 활성화 샘플 코드에서는 [쿼리 알림을 사용 하도록 설정](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec84-105">The sample code assumes that you have enabled query notifications by executing the scripts in [Enabling Query Notifications](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md).</span></span>  
  
## <a name="about-the-sample-application"></a><span data-ttu-id="9ec84-106">샘플 응용 프로그램 정보</span><span class="sxs-lookup"><span data-stu-id="9ec84-106">About the Sample Application</span></span>  
 <span data-ttu-id="9ec84-107">샘플 응용 프로그램 단일 ASP.NET 웹 페이지를 사용 하 여 제품 정보를 표시 하는 **AdventureWorks** SQL Server 데이터베이스에는 <xref:System.Web.UI.WebControls.GridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec84-107">The sample application uses a single ASP.NET Web page to display product information from the **AdventureWorks** SQL Server database in a <xref:System.Web.UI.WebControls.GridView> control.</span></span> <span data-ttu-id="9ec84-108">페이지가 로드되면 코드에서 <xref:System.Web.UI.WebControls.Label> 컨트롤에 현재 시간을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="9ec84-108">When the page loads, the code writes the current time to a <xref:System.Web.UI.WebControls.Label> control.</span></span> <span data-ttu-id="9ec84-109">그런 다음 <xref:System.Web.Caching.SqlCacheDependency> 개체를 정의하고 최대 3분 동안 캐시 데이터를 저장하도록 <xref:System.Web.Caching.Cache> 개체의 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec84-109">It then defines a <xref:System.Web.Caching.SqlCacheDependency> object and sets properties on the <xref:System.Web.Caching.Cache> object to store the cache data for up to three minutes.</span></span> <span data-ttu-id="9ec84-110">그런 다음 코드에서는 데이터베이스에 연결하여 데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec84-110">The code then connects to the database and retrieves the data.</span></span> <span data-ttu-id="9ec84-111">페이지가 로드되고 응용 프로그램이 실행되면 ASP.NET이 캐시에서 데이터를 검색합니다. 여기서 페이지의 시간이 변경되지 않는지를 보고 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ec84-111">When the page is loaded and the application is running ASP.NET will retrieve data from the cache, which you can verify by noting that the time on the page does not change.</span></span> <span data-ttu-id="9ec84-112">모니터링되는 데이터가 변경되면 ASP.NET은 캐시를 무효화한 다음 `GridView` 컨트롤을 새 데이터로 다시 채우고 `Label` 컨트롤에 표시된 시간을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec84-112">If the data being monitored changes, ASP.NET invalidates the cache and repopulate the `GridView` control with fresh data, updating the time displayed in the `Label` control.</span></span>  
  
## <a name="creating-the-sample-application"></a><span data-ttu-id="9ec84-113">샘플 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="9ec84-113">Creating the Sample Application</span></span>  
 <span data-ttu-id="9ec84-114">샘플 응용 프로그램을 만들고 실행하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="9ec84-114">Follow these steps to create and run the sample application:</span></span>  
  
1.  <span data-ttu-id="9ec84-115">새 ASP.NET 웹 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9ec84-115">Create a new ASP.NET Web site.</span></span>  
  
2.  <span data-ttu-id="9ec84-116"><xref:System.Web.UI.WebControls.Label> 및 <xref:System.Web.UI.WebControls.GridView> 컨트롤을 Default.aspx 페이지에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec84-116">Add a <xref:System.Web.UI.WebControls.Label> and a <xref:System.Web.UI.WebControls.GridView> control to the Default.aspx page.</span></span>  
  
3.  <span data-ttu-id="9ec84-117">페이지의 클래스 모듈을 열고 다음 지시문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec84-117">Open the page's class module and add the following directives:</span></span>  
  
    ```vb  
    Option Strict On  
    Option Explicit On  
  
    Imports System.Data.SqlClient  
    ```  
  
    ```csharp  
    using System.Data.SqlClient;  
    using System.Web.Caching;  
    ```  
  
4.  <span data-ttu-id="9ec84-118">페이지의 `Page_Load` 이벤트에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec84-118">Add the following code in the page's `Page_Load` event:</span></span>  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#1)]
     [!code-vb[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#1)]  
  
5.  <span data-ttu-id="9ec84-119">`GetConnectionString` 및 `GetSQL`의 두 가지 도우미 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec84-119">Add two helper methods, `GetConnectionString` and `GetSQL`.</span></span> <span data-ttu-id="9ec84-120">정의된 연결 문자열은 통합 보안을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec84-120">The connection string defined uses integrated security.</span></span> <span data-ttu-id="9ec84-121">사용 중인 계정에 필요한 데이터베이스 권한이 있는지 확인 해야 합니다는 예제 데이터베이스를 **AdventureWorks**, 알림을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec84-121">You will need to verify that the account you are using has the necessary database permissions and that the sample database, **AdventureWorks**, has notifications enabled.</span></span> <span data-ttu-id="9ec84-122">자세한 내용은 참조 [특별 한 고려 사항 때 사용 하 여 쿼리 알림을](http://msdn.microsoft.com/library/a83c8dc8-4fb9-4ffd-a2a5-c07cf4a203c7)합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec84-122">For more information, see [Special Considerations When Using Query Notifications](http://msdn.microsoft.com/library/a83c8dc8-4fb9-4ffd-a2a5-c07cf4a203c7).</span></span>  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#2)]
     [!code-vb[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#2)]  
  
### <a name="testing-the-application"></a><span data-ttu-id="9ec84-123">응용 프로그램 테스트</span><span class="sxs-lookup"><span data-stu-id="9ec84-123">Testing the Application</span></span>  
 <span data-ttu-id="9ec84-124">응용 프로그램에서는 Web Form에 표시된 데이터를 캐시하고 활동이 없으면 3분마다 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="9ec84-124">The application caches the data displayed on the Web form and refreshes it every three minutes if there is no activity.</span></span> <span data-ttu-id="9ec84-125">데이터베이스가 변경되면 즉시 캐시를 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="9ec84-125">If a change occurs to the database, the cache is refreshed immediately.</span></span> <span data-ttu-id="9ec84-126">Visual Studio에서 응용 프로그램을 실행합니다. 그러면 페이지가 브라우저로 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ec84-126">Run the application from Visual Studio, which loads the page into the browser.</span></span> <span data-ttu-id="9ec84-127">표시된 캐시 새로 고침 시간은 캐시가 마지막으로 새로 고쳐진 시간을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9ec84-127">The cache refresh time displayed indicates when the cache was last refreshed.</span></span> <span data-ttu-id="9ec84-128">3분을 기다렸다 페이지를 다시 고쳐서 포스트백 이벤트가 발생하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec84-128">Wait three minutes, and then refresh the page, causing a postback event to occur.</span></span> <span data-ttu-id="9ec84-129">페이지에 표시된 시간이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ec84-129">Note that the time displayed on the page has changed.</span></span> <span data-ttu-id="9ec84-130">3분이 지나기 전에 페이지를 새로 고치면 페이지에 표시된 시간이 동일하게 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ec84-130">If you refresh the page in less than three minutes, the time displayed on the page will remain the same.</span></span>  
  
 <span data-ttu-id="9ec84-131">이제 Transact-SQL UPDATE 명령을 사용하여 데이터베이스의 데이터를 업데이트하고 페이지를 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="9ec84-131">Now update the data in the database, using a Transact-SQL UPDATE command and refresh the page.</span></span> <span data-ttu-id="9ec84-132">이제 표시된 시간을 보면 캐시가 데이터베이스의 새 데이터로 새로 고쳐졌음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ec84-132">The time displayed now indicates that the cache was refreshed with the new data from the database.</span></span> <span data-ttu-id="9ec84-133">캐시가 업데이트되었지만 포스트백 이벤트가 발생할 때까지는 페이지에 표시된 시간이 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ec84-133">Note that although the cache is updated, the time displayed on the page does not change until a postback event occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ec84-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ec84-134">See Also</span></span>  
 [<span data-ttu-id="9ec84-135">SQL Server에서 쿼리 알림</span><span class="sxs-lookup"><span data-stu-id="9ec84-135">Query Notifications in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)  
 [<span data-ttu-id="9ec84-136">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="9ec84-136">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
