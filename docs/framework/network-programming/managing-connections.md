---
title: "연결 관리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Internet, connections
- HTTP, classes for connecting
- requesting data from Internet, connections
- sending data, connections
- receiving data, connections
- ServicePoint class, about ServicePoint class
- response to Internet request, connections
- connections [.NET Framework], classes
- network resources, connections
- downloading Internet resources, connections
- ServicePointManager class, about ServicePointManager class
ms.assetid: 9b3d3de7-189f-4f7d-81ae-9c29c441aaaa
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: f3a8900aca9ebfa14fbf49d4d3634bc486793c0a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="managing-connections"></a><span data-ttu-id="0ad00-102">연결 관리</span><span class="sxs-lookup"><span data-stu-id="0ad00-102">Managing Connections</span></span>
<span data-ttu-id="0ad00-103">HTTP를 사용하여 데이터 리소스에 연결하는 응용 프로그램은 .NET Framework의 <xref:System.Net.ServicePoint> 및 <xref:System.Net.ServicePointManager> 클래스를 사용하여 인터넷에 대한 연결을 관리하고 최적의 규모 및 성능을 달성하도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0ad00-103">Applications that use HTTP to connect to data resources can use the .NET Framework's <xref:System.Net.ServicePoint> and <xref:System.Net.ServicePointManager> classes to manage connections to the Internet and to help them achieve optimum scale and performance.</span></span>  
  
 <span data-ttu-id="0ad00-104">**ServicePoint** 클래스는 응용 프로그램이 인터넷 리소스에 액세스하기 위해 연결할 수 있는 끝점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0ad00-104">The **ServicePoint** class provides an application with an endpoint to which the application can connect to access Internet resources.</span></span> <span data-ttu-id="0ad00-105">각 **ServicePoint**에는 성능을 향상시키기 위해 연결 간 최적화 정보를 공유하여 인터넷 서버와의 연결을 최적화시킬 수 있는 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad00-105">Each **ServicePoint** contains information that helps optimize connections with an Internet server by sharing optimization information between connections to improve performance.</span></span>  
  
 <span data-ttu-id="0ad00-106">각 **ServicePoint**는 URI(Uniform Resource Identifier)로 식별되며 URI의 구성표 식별자 및 호스트 조각에 따라 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ad00-106">Each **ServicePoint** is identified by a Uniform Resource Identifier (URI) and is categorized according to the scheme identifier and host fragments of the URI.</span></span> <span data-ttu-id="0ad00-107">예를 들어 동일한 **ServicePoint** 인스턴스에는 동일한 구성표 식별자(http) 및 호스트 조각(www.contoso.com)이 있으므로 이 인스턴스에서는 URI(http://www.contoso.com/index.htm and http://www.contoso.com/news.htm?date=today)에 요청을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0ad00-107">For example, the same **ServicePoint** instance would provide requests to the URIs http://www.contoso.com/index.htm and http://www.contoso.com/news.htm?date=today since they have the same scheme identifier (http) and host fragments (www.contoso.com).</span></span> <span data-ttu-id="0ad00-108">응용 프로그램이 이미 www.contoso.com 서버에 영구적으로 연결되어 있는 경우 해당 연결을 사용하여 두 요청을 모두 검색하므로 두 연결을 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad00-108">If the application already has a persistent connection to the server www.contoso.com, it uses that connection to retrieve both requests, avoiding the need to create two connections.</span></span>  
  
 <span data-ttu-id="0ad00-109">**ServicePointManager**는 **ServicePoint** 인스턴스의 생성과 소멸을 관리하는 정적 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="0ad00-109">**ServicePointManager** is a static class that manages the creation and destruction of **ServicePoint** instances.</span></span> <span data-ttu-id="0ad00-110">응용 프로그램에서 기존 **ServicePoint** 인스턴스의 컬렉션에 없는 인터넷 리소스를 요청하면 **ServicePointManager**에서 **ServicePoint**를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0ad00-110">The **ServicePointManager** creates a **ServicePoint** when the application requests an Internet resource that is not in the collection of existing **ServicePoint** instances.</span></span> <span data-ttu-id="0ad00-111">**ServicePoint** 인스턴스는 최대 유휴 시간이 초과되거나 기존 **ServicePoint** 인스턴스의 수가 응용 프로그램의 **ServicePoint** 인스턴스 최대 수를 초과할 때 소멸됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ad00-111">**ServicePoint** instances are destroyed when they have exceeded their maximum idle time or when the number of existing **ServicePoint** instances exceeds the maximum number of **ServicePoint** instances for the application.</span></span> <span data-ttu-id="0ad00-112">**ServicePointManager**에서 <xref:System.Net.ServicePointManager.MaxServicePointIdleTime%2A> 및 <xref:System.Net.ServicePointManager.MaxServicePoints%2A> 속성을 설정하여 유휴 시간의 기본 최대값과 **ServicePoint** 인스턴스의 최대 수를 모두 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad00-112">You can control both the default maximum idle time and the maximum number of **ServicePoint** instances by setting the <xref:System.Net.ServicePointManager.MaxServicePointIdleTime%2A> and <xref:System.Net.ServicePointManager.MaxServicePoints%2A> properties on the **ServicePointManager**.</span></span>  
  
 <span data-ttu-id="0ad00-113">클라이언트와 서버 사이의 연결 수는 응용 프로그램 처리량에 상당한 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad00-113">The number of connections between a client and server can have a dramatic impact on application throughput.</span></span> <span data-ttu-id="0ad00-114">기본적으로 <xref:System.Net.HttpWebRequest> 클래스를 사용하는 응용 프로그램에서는 지정된 서버에 대한 영구적 연결을 최대 2개 사용하지만 응용 프로그램별로 최대 연결 수를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad00-114">By default, an application using the <xref:System.Net.HttpWebRequest> class uses a maximum of two persistent connections to a given server, but you can set the maximum number of connections on a per-application basis.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ad00-115">HTTP/1.1 사양에 따르면 응용 프로그램으로부터의 연결은 서버당 두 개의 연결로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ad00-115">The HTTP/1.1 specification limits the number of connections from an application to two connections per server.</span></span>  
  
 <span data-ttu-id="0ad00-116">최적의 연결 수는 응용 프로그램이 실행되는 실제 조건에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="0ad00-116">The optimum number of connections depends on the actual conditions in which the application runs.</span></span> <span data-ttu-id="0ad00-117">응용 프로그램에 사용 가능한 연결 수를 늘려도 응용 프로그램 성능에 영향을 미치지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad00-117">Increasing the number of connections available to the application may not affect application performance.</span></span> <span data-ttu-id="0ad00-118">연결이 추가되는 경우 미치는 영향을 판별하려면 연결 수를 변경하면서 성능 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0ad00-118">To determine the impact of more connections, run performance tests while varying the number of connections.</span></span> <span data-ttu-id="0ad00-119">다음 코드 샘플에 표시된 대로 응용 프로그램 초기화 시 **ServicePointManager** 클래스의 정적 <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A> 속성을 변경하여 해당 응용 프로그램에서 사용하는 연결 수를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad00-119">You can change the number of connections that an application uses by changing the static <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A> property on the **ServicePointManager** class at application initialization, as shown in the following code sample.</span></span>  
  
```csharp  
// Set the maximum number of connections per server to 4.  
ServicePointManager.DefaultConnectionLimit = 4;  
```  
  
```vb  
' Set the maximum number of connections per server to 4.  
ServicePointManager.DefaultConnectionLimit = 4  
```  
  
 <span data-ttu-id="0ad00-120">**ServicePointManager.DefaultConnectionLimit** 속성을 변경해도 이전에 초기화된 **ServicePoint** 인스턴스에는 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ad00-120">Changing the **ServicePointManager.DefaultConnectionLimit** property does not affect previously initialized **ServicePoint** instances.</span></span> <span data-ttu-id="0ad00-121">다음 코드에서는 http://www.contoso.com 서버의 기존 **ServicePoint**에 대한 연결 한계를 `newLimit`에 저장된 값으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="0ad00-121">The following code demonstrates changing the connection limit on an existing **ServicePoint** for the server http://www.contoso.com to the value stored in `newLimit`.</span></span>  
  
```csharp  
Uri uri = new Uri("http://www.contoso.com/");  
ServicePoint sp = ServicePointManager.FindServicePoint(uri);  
sp.ConnectionLimit = newLimit;  
```  
  
```vb  
Dim uri As New Uri("http://www.contoso.com/")  
Dim sp As ServicePoint = ServicePointManager.FindServicePoint(uri)  
sp.ConnectionLimit = newLimit  
```  
  
## <a name="see-also"></a><span data-ttu-id="0ad00-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0ad00-122">See Also</span></span>  
 [<span data-ttu-id="0ad00-123">연결 그룹화</span><span class="sxs-lookup"><span data-stu-id="0ad00-123">Connection Grouping</span></span>](../../../docs/framework/network-programming/connection-grouping.md)  
 [<span data-ttu-id="0ad00-124">응용 프로그램 프로토콜 사용</span><span class="sxs-lookup"><span data-stu-id="0ad00-124">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
