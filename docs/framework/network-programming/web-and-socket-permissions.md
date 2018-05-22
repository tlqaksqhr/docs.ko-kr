---
title: 웹 및 소켓 사용 권한
ms.date: 03/30/2017
helpviewer_keywords:
- Networking
- positions [.NET Framework], accepting
- sockets, permissions
- network, permissions
- Internet, permissions
- Network Resources
- SocketPermission class, about SocketPermission class
- positions [.NET Framework], connecting
- WebPermission class, about WebPermission class
- permissions [.NET Framework], sockets
- security [.NET Framework], Internet
- positions [.NET Framework], granting
ms.assetid: d51ad8cb-03ae-4a51-bfcd-cfcf6b98afa9
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 4353f029d2e82460ab413bc8ccc248577a505504
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="web-and-socket-permissions"></a><span data-ttu-id="0d29d-102">웹 및 소켓 사용 권한</span><span class="sxs-lookup"><span data-stu-id="0d29d-102">Web and Socket Permissions</span></span>
<span data-ttu-id="0d29d-103"><xref:System.Net> 네임스페이스를 사용하는 응용 프로그램에 대한 인터넷 보안은 <xref:System.Net.WebPermission> 및 <xref:System.Net.SocketPermission> 클래스에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d29d-103">Internet security for applications using the <xref:System.Net> namespace is provided by the <xref:System.Net.WebPermission> and <xref:System.Net.SocketPermission> classes.</span></span> <span data-ttu-id="0d29d-104">**WebPermission** 클래스는 URI의 데이터를 요청하거나 인터넷에 URI를 제공하는 응용 프로그램의 권한을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="0d29d-104">The **WebPermission** class controls an application's right to request data from a URI or to serve a URI to the Internet.</span></span> <span data-ttu-id="0d29d-105">**SocketPermission** 클래스는 <xref:System.Net.Sockets.Socket>을 사용하여 로컬 포트에서 데이터를 허용하거나 호스트, 포트 번호 및 전송 프로토콜에 따라 다른 주소에서 전송 프로토콜을 사용하여 원격 장치에 연결하는 응용 프로그램의 권한을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="0d29d-105">The **SocketPermission** class controls an application's right to use a <xref:System.Net.Sockets.Socket> to accept data on a local port or to contact remote devices using a transport protocol at another address, based on the host, port number, and transport protocol of the socket.</span></span>  
  
 <span data-ttu-id="0d29d-106">사용하는 권한 클래스는 응용 프로그램 유형에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="0d29d-106">Which permission class you use depends on your application type.</span></span> <span data-ttu-id="0d29d-107"><xref:System.Net.WebRequest> 및 해당 하위 항목을 사용하는 응용 프로그램은 **WebPermission** 클래스를 사용하여 권한을 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d29d-107">Applications that use <xref:System.Net.WebRequest> and its descendants should use the **WebPermission** class to manage permissions.</span></span> <span data-ttu-id="0d29d-108">소켓 수준 액세스를 사용하는 응용 프로그램은 **SocketPermission** 클래스를 사용하여 권한을 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d29d-108">Applications that use socket-level access should use the **SocketPermission** class to manage permissions.</span></span>  
  
 <span data-ttu-id="0d29d-109">**WebPermission** 및 **SocketPermission**은 두 개의 권한인 허용과 연결을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0d29d-109">**WebPermission** and **SocketPermission** define two permissions: accept and connect.</span></span> <span data-ttu-id="0d29d-110">허용은 다른 파티에서 들어오는 연결에 응답하는 권한을 응용 프로그램에 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="0d29d-110">Accept grants the application the right to answer an incoming connection from another party.</span></span> <span data-ttu-id="0d29d-111">연결은 다른 파티에 대한 연결을 시작하는 권한을 응용 프로그램에 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="0d29d-111">Connect grants the application the right to initiate a connection to another party.</span></span>  
  
 <span data-ttu-id="0d29d-112">**SocketPermission** 인스턴스의 경우 허용은 응용 프로그램이 로컬 전송 주소에서 들어오는 연결을 허용할 수 있음을 의미하고, 연결은 응용 프로그램이 일부 원격(또는 로컬) 전송 주소에 연결할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="0d29d-112">For **SocketPermission** instances, accept means that an application can accept incoming connections on a local transport address; connect means that an application can connect to some remote (or local) transport address.</span></span>  
  
 <span data-ttu-id="0d29d-113">**WebPermission** 인스턴스의 경우 허용은 응용 프로그램이 **WebPermission**에 의해 제어되는 URI을 전 세계에 내보낼 수 있음을 의미합니다. 연결은 응용 프로그램이 원격 또는 로컬 여부에 관계없이 해당 URI에 액세스할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="0d29d-113">For **WebPermission** instances, accept means that an application can export the URI controlled by the **WebPermission** to the world; connect means that an application can access that URI (whether it is remote or local).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d29d-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0d29d-114">See Also</span></span>  
 [<span data-ttu-id="0d29d-115">보안</span><span class="sxs-lookup"><span data-stu-id="0d29d-115">Security</span></span>](../../../docs/standard/security/index.md)  
 [<span data-ttu-id="0d29d-116">네트워크 프로그래밍의 보안</span><span class="sxs-lookup"><span data-stu-id="0d29d-116">Security in Network Programming</span></span>](../../../docs/framework/network-programming/security-in-network-programming.md)
