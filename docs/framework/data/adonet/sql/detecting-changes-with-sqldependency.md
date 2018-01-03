---
title: "SqlDependency로 변경 내용 감지"
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
ms.assetid: e6a58316-f005-4477-92e1-45cc2eb8c5b4
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 1d3fd662ace71d77a185cd996c05960d026ef691
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="detecting-changes-with-sqldependency"></a><span data-ttu-id="fda9d-102">SqlDependency로 변경 내용 감지</span><span class="sxs-lookup"><span data-stu-id="fda9d-102">Detecting Changes with SqlDependency</span></span>
<span data-ttu-id="fda9d-103"><xref:System.Data.SqlClient.SqlDependency> 개체를 <xref:System.Data.SqlClient.SqlCommand>와 연결하여 쿼리 결과가 원래 검색한 결과와 달라지는 시기를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda9d-103">A <xref:System.Data.SqlClient.SqlDependency> object can be associated with a <xref:System.Data.SqlClient.SqlCommand> in order to detect when query results differ from those originally retrieved.</span></span> <span data-ttu-id="fda9d-104">또한 연결된 명령에 대한 결과가 변경될 때 발생하는 `OnChange` 이벤트에 대리자를 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda9d-104">You can also assign a delegate to the `OnChange` event, which will fire when the results change for an associated command.</span></span> <span data-ttu-id="fda9d-105">명령을 실행하기 전에 먼저 <xref:System.Data.SqlClient.SqlDependency>와 해당 명령을 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda9d-105">You must associate the <xref:System.Data.SqlClient.SqlDependency> with the command before you execute the command.</span></span> <span data-ttu-id="fda9d-106">`HasChanges`의 <xref:System.Data.SqlClient.SqlDependency> 속성을 사용하여 쿼리 결과가 데이터를 처음 검색했을 때의 결과와 달라졌는지 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda9d-106">The `HasChanges` property of the <xref:System.Data.SqlClient.SqlDependency> can also be used to determine if the query results have changed since the data was first retrieved.</span></span>  
  
## <a name="security-considerations"></a><span data-ttu-id="fda9d-107">보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="fda9d-107">Security Considerations</span></span>  
 <span data-ttu-id="fda9d-108">종속성 인프라는 원본으로 사용하는 데이터가 특정 명령에 대해 변경된 경우 알림을 받기 위해 <xref:System.Data.SqlClient.SqlConnection>가 호출되면 열리는 <xref:System.Data.SqlClient.SqlDependency.Start%2A>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fda9d-108">The dependency infrastructure relies on a <xref:System.Data.SqlClient.SqlConnection> that is opened when <xref:System.Data.SqlClient.SqlDependency.Start%2A> is called in order to receive notifications that the underlying data has changed for a given command.</span></span> <span data-ttu-id="fda9d-109">클라이언트가 `SqlDependency.Start` 호출을 시작할 수 있는지 여부는 <xref:System.Data.SqlClient.SqlClientPermission>의 사용 및 코드 액세스 보안 특성을 통해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="fda9d-109">The ability for a client to initiate the call to `SqlDependency.Start` is controlled through the use of <xref:System.Data.SqlClient.SqlClientPermission> and code access security attributes.</span></span> <span data-ttu-id="fda9d-110">자세한 내용은 참조 [쿼리 알림을 사용 하도록 설정](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md) 및 [코드 액세스 보안 및 ADO.NET](../../../../../docs/framework/data/adonet/code-access-security.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fda9d-110">For more information, see [Enabling Query Notifications](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md) and [Code Access Security and ADO.NET](../../../../../docs/framework/data/adonet/code-access-security.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="fda9d-111">예</span><span class="sxs-lookup"><span data-stu-id="fda9d-111">Example</span></span>  
 <span data-ttu-id="fda9d-112">다음 단계에서는 종속성을 선언하고, 명령을 실행하고, 결과 집합이 변경될 때 알림을 받는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fda9d-112">The following steps illustrate how to declare a dependency, execute a command, and receive a notification when the result set changes:</span></span>  
  
1.  <span data-ttu-id="fda9d-113">서버에 대한 `SqlDependency` 연결을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="fda9d-113">Initiate a `SqlDependency` connection to the server.</span></span>  
  
2.  <span data-ttu-id="fda9d-114"><xref:System.Data.SqlClient.SqlConnection> 및 <xref:System.Data.SqlClient.SqlCommand> 개체를 만들어 서버에 연결하고 Transact-SQL 문을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fda9d-114">Create <xref:System.Data.SqlClient.SqlConnection> and <xref:System.Data.SqlClient.SqlCommand> objects to connect to the server and define a Transact-SQL statement.</span></span>  
  
3.  <span data-ttu-id="fda9d-115">새 `SqlDependency` 개체를 만들거나 기존 개체를 사용하여 `SqlCommand` 개체에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="fda9d-115">Create a new `SqlDependency` object, or use an existing one, and bind it to the `SqlCommand` object.</span></span> <span data-ttu-id="fda9d-116">그러면 내부적으로 <xref:System.Data.Sql.SqlNotificationRequest> 개체가 만들어져 필요에 따라 명령 개체에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="fda9d-116">Internally, this creates a <xref:System.Data.Sql.SqlNotificationRequest> object and binds it to the command object as needed.</span></span> <span data-ttu-id="fda9d-117">이 알림 요청에는 이 `SqlDependency` 개체를 고유하게 식별하는 내부 ID가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fda9d-117">This notification request contains an internal identifier that uniquely identifies this `SqlDependency` object.</span></span> <span data-ttu-id="fda9d-118">또한 이를 통해 아직 활성화되지 않은 클라이언트 수신기가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="fda9d-118">It also starts the client listener if it is not already active.</span></span>  
  
4.  <span data-ttu-id="fda9d-119">`OnChange` 개체의 `SqlDependency` 이벤트에 이벤트 처리기를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="fda9d-119">Subscribe an event handler to the `OnChange` event of the `SqlDependency` object.</span></span>  
  
5.  <span data-ttu-id="fda9d-120">`Execute` 개체의 `SqlCommand` 메서드를 사용하여 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fda9d-120">Execute the command using any of the `Execute` methods of the `SqlCommand` object.</span></span> <span data-ttu-id="fda9d-121">명령이 알림 개체에 바인딩되기 때문에 서버에서는 알림을 생성해야 하는 것으로 인식하며 대기열 정보는 종속성 대기열을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="fda9d-121">Because the command is bound to the notification object, the server recognizes that it must generate a notification, and the queue information will point to the dependencies queue.</span></span>  
  
6.  <span data-ttu-id="fda9d-122">서버에 대한 `SqlDependency` 연결을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="fda9d-122">Stop the `SqlDependency` connection to the server.</span></span>  
  
 <span data-ttu-id="fda9d-123">사용자가 나중에 원본으로 사용하는 데이터를 변경하는 경우 Microsoft SQL Server에서는 해당 변경 내용에 대해 알림이 보류 중인 것을 감지하고 처리 후 `SqlConnection`를 호출하여 만들어진 기본 `SqlDependency.Start`을 통해 클라이언트로 전달되는 알림을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="fda9d-123">If any user subsequently changes the underlying data, Microsoft SQL Server detects that there is a notification pending for such a change, and posts a notification that is processed and forwarded to the client through the underlying `SqlConnection` that was created by calling `SqlDependency.Start`.</span></span> <span data-ttu-id="fda9d-124">클라이언트 수신기는 무효화 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="fda9d-124">The client listener receives the invalidation message.</span></span> <span data-ttu-id="fda9d-125">그러면 클라이언트 수신기는 연결된 `SqlDependency` 개체를 찾아 `OnChange` 이벤트를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="fda9d-125">The client listener then locates the associated `SqlDependency` object and fires the `OnChange` event.</span></span>  
  
 <span data-ttu-id="fda9d-126">다음 코드 조각에서는 샘플 응용 프로그램을 만드는 데 사용할 수 있는 디자인 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fda9d-126">The following code fragment shows the design pattern you would use to create a sample application.</span></span>  
  
```vb  
Sub Initialization()  
    ' Create a dependency connection.  
    SqlDependency.Start(connectionString, queueName)  
End Sub  
  
Sub SomeMethod()   
    ' Assume connection is an open SqlConnection.  
    ' Create a new SqlCommand object.  
    Using command As New SqlCommand( _  
      "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers", _  
      connection)  
  
        ' Create a dependency and associate it with the SqlCommand.  
        Dim dependency As New SqlDependency(command)  
        ' Maintain the refence in a class member.  
        ' Subscribe to the SqlDependency event.  
        AddHandler dependency.OnChange, AddressOf OnDependencyChange  
  
        ' Execute the command.  
        Using reader = command.ExecuteReader()  
            ' Process the DataReader.  
        End Using  
    End Using  
End Sub   
  
' Handler method  
Sub OnDependencyChange(ByVal sender As Object, _  
    ByVal e As SqlNotificationEventArgs)   
    ' Handle the event (for example, invalidate this cache entry).  
End Sub  
  
Sub Termination()  
    ' Release the dependency  
    SqlDependency.Stop(connectionString, queueName)  
End Sub  
```  
  
```csharp  
void Initialization()  
{  
    // Create a dependency connection.  
    SqlDependency.Start(connectionString, queueName);  
}  
  
void SomeMethod()  
{  
    // Assume connection is an open SqlConnection.  
  
    // Create a new SqlCommand object.  
    using (SqlCommand command=new SqlCommand(  
        "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers",   
        connection))  
    {  
  
        // Create a dependency and associate it with the SqlCommand.  
        SqlDependency dependency=new SqlDependency(command);  
        // Maintain the refence in a class member.  
  
        // Subscribe to the SqlDependency event.  
        dependency.OnChange+=new  
           OnChangeEventHandler(OnDependencyChange);  
  
        // Execute the command.  
        using (SqlDataReader reader = command.ExecuteReader())  
        {  
            // Process the DataReader.  
        }  
    }  
}  
  
// Handler method  
void OnDependencyChange(object sender,   
   SqlNotificationEventArgs e )  
{  
  // Handle the event (for example, invalidate this cache entry).  
}  
  
void Termination()  
{  
    // Release the dependency.  
    SqlDependency.Stop(connectionString, queueName);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="fda9d-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fda9d-127">See Also</span></span>  
 [<span data-ttu-id="fda9d-128">SQL Server에서 쿼리 알림</span><span class="sxs-lookup"><span data-stu-id="fda9d-128">Query Notifications in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)  
 [<span data-ttu-id="fda9d-129">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="fda9d-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
